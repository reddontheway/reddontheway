# -*- coding: utf-8 -*-
import urllib3
from lxml import etree
import html
import re

blogUrl = 'https://xindoo.blog.csdn.net/'

headers={'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.89 Safari/537.36'} 

def addIntro(f):
	txt = ''' 
9年技术博主，CSDN认证博客专家，新晋视频up主  
曾在阿里做过2年运维+1年开发，现为某厂Java后端开发工程师，拥有丰富的 挖坑 踩坑 填坑 背锅经验     
专注于Java，对操作系统、网络、编译原理也有涉猎，目前正在写一门简易的脚本语言   
''' 
	f.write(txt)

def addProjectInfo(f):
	txt ='''
### 开源项目  
- [eng-practices-cn](https://github.com/xindoo/eng-practices-cn)谷歌工程实践中文版    
- [regex](https://github.com/xindoo/regex)Java实现的正则引擎表达式    
- [redis](https://github.com/xindoo/redis) Redis中文注解版  
- [slowjson](https://github.com/xindoo/slowjson) 用antlr实现的json解析器  
- [leetcode](https://github.com/xindoo/leetcode) 我的Leetcode题解   
   
[查看更多](https://github.com/xindoo/)     
	''' 
	f.write(txt) 


def addBlogInfo(f):  
	http = urllib3.PoolManager(num_pools=5, headers = headers)
	resp = http.request('GET', blogUrl)
	resp_tree = etree.HTML(resp.data.decode("utf-8"))
	html_data = resp_tree.xpath(".//div[@class='article-item-box csdn-tracking-statistics']/h4") 
	f.write("\n### 我的博客\n")
	cnt = 0
	for i in html_data: 
		if cnt >= 5:
			break
		title = i.xpath('./a/text()')[1].strip()
		url = i.xpath('./a/@href')[0] 
		item = '- [%s](%s)\n' % (title, url)
		f.write(item)
		cnt = cnt + 1
	f.write('\n[查看更多](https://xindoo.blog.csdn.net/)\n')

f = open('README.md', 'w+')
addIntro(f)
f.write('<table><tr>\n')
f.write('<td valign="top" width="50%">\n')

addProjectInfo(f)
f.write('\n</td>\n')
f.write('<td valign="top" width="50%">\n')
addBlogInfo(f)
f.write('\n</td>\n')
f.write('</tr></table>\n')
f.close
