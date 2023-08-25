![](./demo/images/preview.png)

<p align="center">
  <sub>
    Buil by
    <a href="https://github.com/reddontheway">redd</a>
  </sub>
</p>

[![支付宝赞助按钮](https://camo.githubusercontent.com/f4874996db5ac421925db08778d800d76d36abbc/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f2545362539342541462545342542422539382545352541452539442d25453525393025393154412545362538442539302545352538412541392d677265656e2e737667)](https://i.postimg.cc/ts1p5fYZ/20230825161816.jpg)

[![微信赞助按钮](https://camo.githubusercontent.com/26101aa838286ad0d45a6f71b25fdc6e14e7668c/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f2545352542452541452545342542462541312d25453525393025393154412545362538442539302545352538412541392d677265656e2e737667)](https://i.postimg.cc/2SgrywS7/20230825161816-1.jpg)

<p align="center">
  <a href="https://github.com/nsfw-filter/nsfw-filter/releases/" target="_blank">
    <img alt="GitHub release" src="https://img.shields.io/github/v/release/navendu-pottekkat/nsfw-filter?include_prereleases&style=flat-square">
  </a>

  <a href="https://github.com/navendu-pottekkat/nsfw-filter/commits/master" target="_blank">
    <img src="https://img.shields.io/github/last-commit/navendu-pottekkat/nsfw-filter?style=flat-square" alt="GitHub last commit">
  </a>

  <a href="https://github.com/navendu-pottekkat/nsfw-filter/issues" target="_blank">
    <img src="https://img.shields.io/github/issues/navendu-pottekkat/nsfw-filter?style=flat-square&color=red" alt="GitHub issues">
  </a>

  <a href="https://github.com/navendu-pottekkat/nsfw-filter/pulls" target="_blank">
    <img src="https://img.shields.io/github/issues-pr/navendu-pottekkat/nsfw-filter?style=flat-square&color=blue" alt="GitHub pull requests">
  </a>

  </br>

  <a href="https://github.com/nsfw-filter/nsfw-filter#contribute" target="_blank">
    <img alt="Contributors" src="https://img.shields.io/badge/all_contributors-10-orange.svg?style=flat-square">
  </a>

  <a href="https://standardjs.com" target="_blank">
    <img alt="ESLint" src="https://img.shields.io/badge/code_style-standard-brightgreen.svg?style=flat-square">
  </a>

  <a href="https://www.producthunt.com/posts/nsfw-filter?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-nsfw-filter" target="_blank">
    <img alt="ProductHunt" src="https://img.shields.io/badge/ProductHunt-210-green.svg?style=flat-square">
  <a/>

  <a href="https://github.com/nsfw-filter/nsfw-filter/blob/master/LICENSE" target="_blank">
    <img alt="LICENSE" src="https://img.shields.io/github/license/navendu-pottekkat/nsfw-filter?style=flat-square&color=yellow">
  <a/>

  <a href="https://ctt.ac/4e4Jt" target="_blank">
    <img src="https://img.shields.io/twitter/url?style=flat-square&logo=twitter&url=https://ctt.ac/4e4Jt" alt="GitHub tweet">
  </a>
</p>
<hr>

A browser extension that blocks NSFW images from the web pages that you load using TensorFlowJS.

*This extension **does NOT** collect/send any user data. All the operations on the images are done locally on the browser. No user data is being sent to a server for processing.*

<p align="center">
  <img alt="GitHub release" src="https://raw.githubusercontent.com/nsfw-filter/nsfw-filter/master/demo/images/demo_v3.gif">
</p>

When a web page is loaded, all the images remain hidden until they are found to be NSFW or not. If they are found to be NSFW, they remain hidden. Otherwise, they become visible.

It is free and is currently supported on Google Chrome and is featured on the Chrome Webstore. We are working on porting this to Safari also (we need help!).
</br>
<p align="center">
  <a href="https://chrome.google.com/webstore/detail/chatgpt-prompts-tool-prom/dafkkimnoemanmhikhkpbfaahfhjgdnb" target="_blank">
    <img src="./demo/images/chrome.gif" alt="Download now" width="160">
  </a>
</p>

<p align="center">
<a href="https://chrome.google.com/webstore/detail/chatgpt-prompts-tool-prom/dafkkimnoemanmhikhkpbfaahfhjgdnb" target="_blank"><strong>Download for Chrome</strong></a>
</p>

Read about the release in [**Hacker Noon**](https://hackernoon.com/nsfw-filter-introduction-building-a-safer-internet-using-ai-jq1e3u2f) or in [**Towards Data Science**](https://towardsdatascience.com/building-a-safer-internet-for-everyone-using-ai-175df5e02cee).

Model used - [**nsfwjs**](https://github.com/infinitered/nsfwjs) developed by [**Infinite Red, Inc.**](https://github.com/infinitered)

Storing settings - [**reduxed-chrome-storage**](https://github.com/hindmost/reduxed-chrome-storage)

Reach out to us! Join the [**Slack channel**](https://join.slack.com/t/nsfwfilter/shared_invite/zt-gt1lgdiv-K2VR~UVUxwaTPWCLSmDiug).

# Table of contents

- [Table of contents](#table-of-contents)
- [Usage](#usage)
- [Development](#development)
    - [Adding to Chrome](#adding-to-chrome)
- [Contribute](#contribute)

# Usage

After adding the extension to your browser, it will light-up every time you load a compatible website.

When a page is loaded, the extension would hide all the images in the page and only show images that have been classified as **NOT NSFW**.

You can toggle(off/on) the extension from the ```chrome://extensions``` page in Chrome.

Open the popup window to change NSFW Filter settings.

<table>
  <tr>
    <td vlign="center">
      <img src="./demo/images/pin_popup.png" alt="Pin popup window">
    </td>
    <td vlign="center">
      <img src="./demo/images/popup.png" alt="Popup window">
    </td>
  </tr>
</table>


# Development

Clone this repository and navigate inside the project folder and install the dependencies by running:

```sh
npm ci
```

After installing the dependencies, build the project by executing:

```sh
npm run build
```

Run the tests

```sh
npm run test
```

### Adding to Chrome

To install the developer version follow the steps below. To just use the extension download from [**chrome.google.com/webstore/nsfw-filter**](https://chrome.google.com/webstore/detail/nsfw-filter/kmgagnlkckiamnenbpigfaljmanlbbhh).

To run development version in clean environment use command:

```sh
npm run dev:chrome
```

Or open Google Chrome and open the Extension Management page by navigating to ```chrome://extensions``` or by opening Settings and clicking Extensions from the bottom left.

Enable Developer Mode by clicking the toggle switch next to Developer mode.

Click the "Load Unpacked" button and select the extension directory(```.../dist```).

<p align="center">
  <img src="./demo/images/install_instructions.png" alt="Install Instructions">
<p/>

Voila! The extension is now installed and ready to be used!


  </tbody>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
	
