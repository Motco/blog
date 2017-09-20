## <a name="jp0">Chrome 开发者工具</a>
#### Chrome 开发者工具是一套内置于Google Chrome中的Web开发和调试工具，可用来对网站进行迭代、调试和分析<br/>
*see more at [Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/?utm_campaign=2016q3&utm_medium=redirect&utm_source=dcc)*
- 打开方式
  - 在Chrome菜单中选择 更多工具 > 开发者工具
  - 在页面元素上右键点击，选择 “检查”
  - 使用 快捷键 Ctrl+Shift+I/F12 (Windows) 或 Cmd+Opt+I (Mac)

- 了解面板Overview
  - 设备模式(Device Mode)，使用设备模式构建完全响应式，模拟移动设备
    - [Device Mode](https://developers.google.com/web/tools/chrome-devtools/device-mode/)
    - [测试自适应和设备特定的视口](https://developers.google.com/web/tools/chrome-devtools/device-mode/emulate-mobile-viewports)
    - [模拟传感器：地理定位与加速度计](https://developers.google.com/web/tools/chrome-devtools/device-mode/device-input-and-sensors)
  - 元素面板(Elements)，使用元素面板可以自由的操作DOM和CSS来迭代布局和设计页面
    - [检查和调整页面](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/)
    - [编辑样式](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/edit-styles)
    - [编辑DOM](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/edit-dom)
![元素面板](http://www.z4a.net/images/2017/09/18/40-34.png)

  - 控制台面板(Console)，在开发期间，可以使用控制台面板记录诊断信息，或者使用它作为 shell在页面上与JavaScript交互
    - [使用控制台面板](https://developers.google.com/web/tools/chrome-devtools/console/)
    - [命令行交互](https://developers.google.com/web/tools/chrome-devtools/console/)
![控制台](http://www.z4a.net/images/2017/09/18/49-02.png)

  - 源代码面板(Sources)，在源代码面板中设置断点来调试 JavaScript ，或者通过Workspaces连接本地文件来使用开发者工具的实时编辑器
    - [断点调试](https://developers.google.com/web/tools/chrome-devtools/javascript/add-breakpoints)
    - [调试混淆的代码](https://developers.google.com/web/tools/chrome-devtools/javascript/add-breakpoints)
    - [使用开发者工具的Workspaces进行持久化保存](https://developers.google.com/web/tools/setup/setup-workflow)
  - 网络面板(Network)，使用网络面板了解请求和下载的资源文件并优化网页加载性能
    - [测量网站网络性能](https://developers.google.com/web/tools/chrome-devtools/network-performance/resource-loading)
    - [查看资源时间轴](https://developers.google.com/web/tools/chrome-devtools/network-performance/understanding-resource-timing)
    - [查看网络带宽限制](https://developers.google.com/web/tools/chrome-devtools/network-performance/network-conditions)
  - 性能面板(Performance)，在 Chrome 57 之后时间线面板更名为性能面板，使用时间轴面板可以通过记录和查看网站生命周期内发生的各种事件来提高页面的运行时性能
    - [查看性能](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/timeline-tool)
    - [分析运行时性能](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/)
    - [调试强制同步布局](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/forced-synchronous-layouts)
  - 内存面板(Memory)，在 Chrome 57 之后分析面板更名为内存面板，如果需要比时间轴面板提供的更多信息，可以使用内存下“配置”面板，例如跟踪内存泄漏
    - [JavaScript CPU 分析器](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution)
    - [内存堆区分析器](https://developers.google.com/web/tools/chrome-devtools/memory-problems/)
  - 应用面板(Application)，在 Chrome 52 之后资源面板更名为应用面板，使用资源面板检查加载的所有资源，包括IndexedDB与Web SQL数据库，本地和会话存储，cookie，应用程序缓存，图像，字体和样式表
    - [检查和管理存储、数据库与缓存](https://developers.google.com/web/tools/chrome-devtools/manage-data/local-storage)
  - 安全面板(Security)，使用安全面板调试混合内容问题，证书问题等等
    - [调试安全问题](https://developers.google.com/web/tools/chrome-devtools/security)
  - 审查应用(Audits)，可使用 Lighthouse 扩展审查网络应用，为 Lighthouse 提供一个要审查的网址，它将针对此页面运行一连串的测试，然后生成一个有关页面性能的报告
    - [使用 Lighthouse 审查网络应用](https://developers.google.com/web/tools/lighthouse/)<br/><br/>

- 快捷键参考 [**TOP**](#jp0) <br/><br/>
![快捷键](http://www.z4a.net/images/2017/09/18/2017-09-17_23-15-00.png)
[**TOP**](#jp0)
