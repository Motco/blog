title: CSS 规范
---

#### 1. `CSS` 书写规范
- 格式规范
  - 分号，每个属性定义末尾都要加分号
  - 缩进，使用 `soft tab`（2个空格），不要使用 `tab` 或者混合 `tab` 和空格的缩进
  - 换行
    + 选择符 `{` 后和 `}` 前
    + 每个属性 `;` 后
    + 多个规则的分隔符 `,` 后
  - 空格
    + 属性值前
    + 属性值中的 `,` 后
    + 选择器 `>`, `+`, `~` 前后
    + 选择器与 `{` 之间
    + 注释 `/*` 后和 `*/` 前
  - 去掉小数点前的 `0`
  - 属性值 `0` 后不要加单位
  - 属性书写顺序，同一 `rule set` 下按功能分组，并以 `布局` > `尺寸` > `文本相关` > `视觉效果` 的顺序书写

- 命名范例
  - `.wrap`，`.wrapper` 外侧包裹
  - `.container`，`.ct` 包裹容器
  - `.header` 页面头部
  - `.body` 页面主体
  - `.footer` 页面尾部
  - `.aside`，`.sidebar` 侧边栏
  - `.content` 主要内容
  - `.navigation` 导航元素
  - `.pagination` 分页
  - `.tab` 切换
  - `.breadcrumbs` 导航列表、面包屑
  - `.dropdown` 下拉菜单
  - `.article` 文章
  - `.main` 用于主体
  - `.thumbnail` 头像，小图像
  - `.media` 媒体资源
  - `.panel` 面板
  - `.tooltip` 鼠标放置上去的提示
  - `.popup` 鼠标点击弹出的提示
  - `.button`，`.btn` 按钮
  - `.ad` 广告
  - `.subnav` 二级导航
  - `.menu` 菜单
  - `.tag ` 标签
  - `.message`，`.notice` 提示消息
  - `.summary` 摘要
  - `.logo` 图标
  - `.search` 搜索框
  - `.login` 登录
  - `.register` 注册
  - `.username` 用户名
  - `.password` 密码
  - `.banner` 广告条
  - `.copyright` 版权
  - `.modal`，`.dialog` 弹窗

  ```
    var 名字 = {
      状态: [
        'inverse',
        'toggled',
        'switched',
        'original',
        'initial',
        'identified',
        'disabled',
        'loading',
        'pending',
        'syncing',
        'default'
      ],
      修饰: [
        'dark',
        'light',
        'shaded',
        'flat',
        'ghost',
        'maroon',
        'pale',
        'intense',
        'twisted',
        'narrow',
        'wide',
        'smooth',
        'separate',
        'clean',
        'sharp',
        'aligned'
      ],
      元素: [
        'pagination',
        'modal',
        'popup',
        'article',
        'story',
        'flash',
        'status',
        'state',
        'media',
        'block',
        'card',
        'teaser',
        'badge',
        'label',
        'sheet',
        'poster',
        'notice',
        'record',
        'entry',
        'item',
        'figure',
        'square',
        'module',
        'bar',
        'button',
        'action',
        'knob'
      ],
      布局: [
        'navigation',
        'wrapper',
        'inner',
        'header',
        'footer',
        'aside',
        'section',
        'divider',
        'content',
        'container',
        'panel',
        'pane',
        'construct',
        'composition',
        'spacing',
        'frame'
      ]
    }
  ```
  *refer to [编码规范 @mdo](http://codeguide.bootcss.com/)，[编码规范 @jrg-team](http://book.jirengu.com/jrg-team/frontend-knowledge-ppt/CSS-%E7%BC%96%E7%A0%81%E8%A7%84%E8%8C%83.md.html)，[Code Guide @AlloyTeam](http://alloyteam.github.io/CodeGuide/)，[styleguide @fex-team](https://github.com/fex-team/styleguide)*
