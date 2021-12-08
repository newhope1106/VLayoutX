# XVLayout
Extend From VLayout, and it will support Android X <br/>
从VLayout库克隆，支持Android X的RecyclerView <br/>

详细使用说明，参考：https://github.com/alibaba/vlayout

# Main Feature
Provide default common layout implementation, decouple the View and Layout. Default layout implementations are:
* LinearLayoutHelper: provide linear layout as LinearLayoutManager.
* GridLayoutHelper: provide grid layout as GridLayoutManager, but with more feature.
* FixLayoutHelper: fix the view at certain position of screen, the view does not scroll with whole page.
* ScrollFixLayoutHelper: fix the view at certain position of screen, but the view does not show until it scrolls to it position.
* FloatLayoutHelper: float the view on top of page, user can drag and drop it.
* ColumnLayoutHelper: perform like GridLayoutHelper but layouts all child views in one line.
* SingleLayoutHelper: contain only one child view.
* OnePlusNLayoutHelper: a custom layout with one child view layouted at left and the others at right, you may not need this.
* StickyLayoutHelper: scroll the view when its position is inside the screen, but fix the view at start or end when its position is outside the screen.
* StaggeredGridLayoutHelper: provide waterfall like layout as StaggeredGridLayoutManager.

LayoutHelpers provided by default can be generally divided into two categories. One is non-fix LayoutHelper such as LinearLayoutHelper, GridLayoutHelper, etc which means the children of these LayoutHelper will be layouted in the flow of parent container and will be scrolled with the container scrolling. While the other is fix LayoutHelper which means the child of these is always fix in parent container.

# 主要功能
默认通用布局实现，解耦所有的View和布局之间的关系: Linear, Grid, 吸顶, 浮动, 固定位置等。
* LinearLayoutHelper: 线性布局
* GridLayoutHelper: Grid布局， 支持横向的colspan
* FixLayoutHelper: 固定布局，始终在屏幕固定位置显示
* ScrollFixLayoutHelper: 固定布局，但之后当页面滑动到该图片区域才显示, 可以用来做返回顶部或其他书签等
* FloatLayoutHelper: 浮动布局，可以固定显示在屏幕上，但用户可以拖拽其位置
* ColumnLayoutHelper: 栏格布局，都布局在一排，可以配置不同列之间的宽度比值
* SingleLayoutHelper: 通栏布局，只会显示一个组件View
* OnePlusNLayoutHelper: 一拖N布局，可以配置1-5个子元素
* StickyLayoutHelper: stikcy布局， 可以配置吸顶或者吸底
* StaggeredGridLayoutHelper: 瀑布流布局，可配置间隔高度/宽度
上述默认实现里可以大致分为两类：一是非fix类型布局，像线性、Grid、栏格等，它们的特点是布局在整个页面流里，随页面滚动而滚动；另一类就是fix类型的布局，它们的子节点往往不随页面滚动而滚动。
所有除布局外的组件复用，VirtualLayout将用来管理大的模块布局组合，扩展了RecyclerView，使得同一RecyclerView内的组件可以复用，减少View的创建和销毁过程。