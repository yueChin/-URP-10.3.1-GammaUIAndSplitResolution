<div id="top"></div>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->




<!-- ABOUT THE PROJECT -->
## 简单概述

* 本库主要解决了在  线性工作流下，如何保持UI 相机还能够保持在 Gamma 颜色空间下工作
* UI 相机的渲染不应该受到 任何 postprocess 和 finalProcess( 例如 fxaa 和 fsr) 的影响
* 充分利用URP内置RenderTargetSwapBuff ,保持了原本代码一致性

<p align="right">(<a href="#top">back to top</a>)</p>




## 使用
* UniversalRenderer.cs 有2个功能开关
* public static bool sUISplitEnable = true; // 分辨率分离 ,场景相机可自由调节分辨率，ui相机为屏幕大小
* public static bool sIsGammaCorrectEnable = true; // ui gamma校对

* 阅读本库对URP12的修改， 修改你的URP12 ，最好用对比工具和源码进行对比，例如：Beyond Compare 
* 把本库shader/URP-UI-Default.shader 拖到  Project Setting/Graphic/BuildinShader 里面，#替换#掉原来的 UI/Default shader
* 如果你打开了gamma ui 功能，而且UI相机不止使用UI/Default shade,还使用了TextMeshPro等的shader,请在最后的shader的 ps 里面，加上 lineToSRGB，做一次颜色校对，参考本库里面的 shader/TMP_SDF-Mobile.shader
<p align="right">(<a href="#top">back to top</a>)</p>



<!-- ROADMAP -->
## 路线图

- [ ]  gamma ui 在scen view 下的 和 game view 下的色差



<p align="right">(<a href="#top">back to top</a>)</p>





<!-- ACKNOWLEDGMENTS -->
## 参考
* [UniversalRP](https://github.com/devagame/UniversalRP )
* https://github.com/killop/URP-12-GammaUIAndSplitResolution

<p align="right">(<a href="#top">back to top</a>)</p>
