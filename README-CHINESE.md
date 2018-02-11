# ChartCore
## 前言

***ChartCore*** 项目,是[Infographics](https://github.com/ChartModel/ChartCore-Swift)的 `Java` 语言版本,是在流行的开源前端图表库*Highcharts*的基础上,封装的面向对象的,一组简单易用,极其精美的图表绘制控件.可能是全网络 UI 最精致的第三方 Android 开源图表库了(✟我以无神论者的名义向上帝起誓🖐,我真的没有在说鬼话✟)

## 功能特性

***

1. **环境友好,兼容性强**. 支持 `Java`语言,配置简单.同时更有 Kotlin 版本[Infographics](https://github.com/ChartModel/ChartCore-Swift)可供使用.
1. **功能强大,类型多样**. 支持`柱状图` 、`条形图` 、`折线图` 、`曲线图` 、`折线填充图` 、`曲线填充图`、`雷达图`、`极地图`、`扇形图`、`气泡图`、`散点图`、`区域范围图`、`柱形范围图`、`面积范围图`、`面积范围均线图`、`直方折线图`、`直方折线填充图`、`箱线图`、`瀑布图`、`热力图`、`桑基图`、`金字塔图`、`漏斗图`、等二十几种类型的图形,不可谓之不多.
1. **交互式图形动画**. 有着清晰和充满细节的用户交互方式,与此同时,图形渲染`动画`效果细腻精致,流畅优美.有三十多种以上渲染动画效果可供选择,用户可自由设置渲染图形时的动画时间和动画类型,关于图形渲染动画类型,具体参见[ ChartCore 动画类型](https://github.com/ChartModel/ChartCore/blob/master/CHINESE-README.md#当前已支持的图表渲染动画类型有三十种以上说明如下).
1. **支持手势缩放**.支持图表的手势缩放和拖动阅览,手势缩放类型具体参见[ ChartCore 手势缩放类型](https://github.com/ChartModel/ChartCore/blob/master/CHINESE-README.md#当前已支持的图表手势缩放类型共有三种说明如下),默认禁用手势缩放功能.
1. **极简主义**. `ChartView + ChartModel = Chart`,在 ***ChartCore*** 封装库当中,遵循这样一个极简主义公式:`图表视图控件 + 图表模型 = 你想要的图表`.同另一款强大而又精美的图表库[Infographics](https://github.com/ChartModel/ChartCore-Swift)完全一致.
1. **链式编程语法**. 支持类 *Masonry* `链式编程语法`,一行代码即可配置完成 `ChartModel`模型对象实例.
1. **简洁清晰,轻便易用**. 最少仅仅需要 **五行代码** 即可完成整个图表的绘制工作(使用链式编程语法配置 `ChartModel` 实例对象时,无论你写多少行代码,理论上只能算作是一行). 😜😜😜


## 真机美图
| Column Chart 柱状图 | Stacked Bar Chart 堆积条形图 | Area Chart 区域填充图 |
| :----:  | :----: | :----: |
| ![image1](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/BeautyAppreciation/ColumnChart.png) | ![image1](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/BeautyAppreciation/BarChart.png) | ![image1](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/BeautyAppreciation/AreaChart.png) |

| Line Chart 折线图 | Step Area Chart 直方折线填充图 | Step Line Chart 直方折线图 |
| :----:  | :----: | :----: |
| ![image1](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/BeautyAppreciation/LineChart.png) | ![image1](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/BeautyAppreciation/StepAreaChart.png) | ![image1](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/BeautyAppreciation/StepLineChart.png) |

| Spline Chart 曲线图| Areaspline Chart 曲线填充图 | Stacked Polar Chart 堆积填充图 |
| :----:  | :----: | :----: |
| ![image1](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/BeautyAppreciation/SplineChart.png) | ![image1](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/BeautyAppreciation/AreasplineChart.png) | ![image1](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/BeautyAppreciation/StackedPolarChart.png) |


## 使用方法

### 准备工作
* 将项目`Demo`中的文件夹`ChartCore`拖入到所需项目中.

### 正式开始
1. 在你的视图控制器文件中添加
```java
#import "ChartView.java"
```
2. 在 xml 文件中创建视图`ChartView`
```xml
<com.jswym.cloud.statistics.ChartView
android:id="@+id/chartView"
android:layout_width="match_parent"
android:layout_height="match_parent" />
```
3. 配置视图模型`ChartModel`
```java
webView = (AAChartView) findViewById(R.id.shop_customer_info_chartView);
AAChartModel chartModel = new AAChartModel()
.setChartType(AAChartModel.AAChartType.Pie)
.setTitle("店内会员占比情况")
.setSubtitle("")
.setDataLabelEnabled(true)
.setLegendVerticalAlign(AAChartModel.AAChartLegendVerticalAlignType.Bottom)
.setSeries(
new AASeries[]{
new AASeries()
.setData(dataArr)
.setName("店内会员数量")
.setInnerSize("30%")
});
```
4.  绘制图形(创建 `ChartView` 实例对象后,首次绘制图形调用此方法)
```java
/*图表视图对象调用图表模型对象,绘制最终图形*/
webView.aa_drawChartWithChartModel(chartModel);
```

5.  仅仅刷新图形的数据(进行数据的动态更新操作时,建议使用此方法)
```java
/*仅仅更新 ChartModel 对象的 series 属性时,动态刷新图表*/
webView.aa_onlyRefreshTheChartDataWithChartModelSeries(chartModelSeriesArr);
```

6.  刷新图形除数据属性 `series` 以外的其他属性(首次绘制图形完成之后,后续刷新图表的属性均建议调用此方法 注意:仅仅刷新图形数据,则建议使用`aa_onlyRefreshTheChartDataWithChartModelSeries`方法)
```java
/*更新 ChartModel 内容之后,刷新图表*/
webView.aa_refreshChartWithChartModel(chartModel);
```

##  `ChartModel`一些重要属性经过配置之后的图形示例如下

-  ### line chart - 折线图

![IMG_1867.JPG](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/LineChart.png)

-  ### column chart - 柱状图

![IMG_1873.JPG](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/ColumnChart.png)

- ###  bar chart - 条形图

![IMG_1880.JPG](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/BarChart.png)

- ### special area chart one - 折线区域填充图

![IMG_1869.JPG](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/IMG_1482.JPG)

- ### special area chart two - 带有负数的曲线区域填充图

![IMG_1871.JPG](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/AreasplineChart.png)

- ### special area chart three - 堆积状态的折线区域填充图

![IMG_1863.JPG](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/PictureResources/屏幕快照%202017-05-06%20下午6.58.15.png)

- ### radar chart - 多组数据的雷达图

![IMG_1877.JPG](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/RadarChart.png)

- ### polar chart - 极地图

![IMG_1879.JPG](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/PolarChart.png)

- ### pie chart - 环形图(中间为空的扇形图)

![IMG_1878.JPG](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/PieChart.png)

- ### bubble chart - 气泡图

![IMG_1875.JPG](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAChartKit/BubbleChart.png)

- ### scatter chart - 散点图

![scatter chart](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAInfographics/ScatterChart.png)

- ### arearange chart - 区域范围填充图

![arearange chart](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAInfographics/ArearangeChart.png)

- ### step area chart - 直方区域填充图

![step area chart](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAInfographics/StepAreaChart.png)

- ### mixed chart - 混合图形(折线图&柱形范围图)

![mixed chart](https://github.com/AAChartModel/loadHtmlCssJsDemo-master/blob/master/AAInfographics/MixedChart.png)

### 当前已支持的图表类型有十种以上,说明如下
```java
public interface ChartType {
String Column      = "column";      //柱形图
String Bar         = "bar";         //条形图
String Area        = "area";        //折线区域填充
String AreaSpline  = "areaspline";  //曲线区域填充图
String Line        = "line";        //折线图
String Spline      = "spline";      //曲线图
String Scatter     = "scatter";     //散点图
String Pie         = "pie";         //扇形图
String Bubble      = "bubble";      //气泡图
String Pyramid     = "pyramid";     //金字塔图
String Funnel      = "funnel";      //漏斗图
String Columnrange = "columnrange"; //柱形范围图
String Arearange   = "arearange";   //区域范围图
}

```

### 当前已支持的图表手势缩放类型共有三种,说明如下
```java
public interface ChartZoomType {
String None  = "";   //禁用手势缩放功能(默认禁用手势缩放)
String X     = "x";  //支持图表 X轴横向缩放
String Y     = "y";  //支持图表 Y轴纵向缩放
String XY    = "xy"; //支持图表等比例缩放
}
```
NOTE:例如,设置了`ChartModel`的缩放属性`zoomType`为`ChartZoomTypeX`,并且将图表进行了手势放大之后,这时候如果想要左右滑动图表,可以使用 **双指点按** 屏幕中的`ChartView`视图区域进行 **左右拖动** 即可.同时屏幕的右上角会自动出现一个标题为 **"恢复缩放"** 的按钮,点击恢复缩放,图表大小和位置将会回归到原初的样式.

### 当前已支持的图表渲染动画类型有三十种以上,说明如下
```java
public interface ChartAnimationType {
String EaseInQuad     = "easeInQuad"
String EaseOutQuad    = "easeOutQuad"
String EaseInOutQuad  = "easeInOutQuad"
String EaseInCubic    = "easeInCubic"
String EaseOutCubic   = "easeOutCubic"
String EaseInOutCubic = "easeInOutCubic"
String EaseInQuart    = "easeInQuart"
String EaseOutQuart   = "easeOutQuart"
String EaseInOutQuart = "easeInOutQuart"
String EaseInQuint    = "easeInQuint"
String EaseOutQuint   = "easeOutQuint"
String EaseInOutQuint = "easeInOutQuint"
String EaseInSine     = "easeInSine"
String EaseOutSine    = "easeOutSine"
String EaseInOutSine  = "easeInOutSine"
String EaseInExpo     = "easeInExpo"
String EaseOutExpo    = "easeOutExpo"
String EaseInOutExpo  = "easeInOutExpo"
String EaseInCirc     = "easeInCirc"
String EaseOutCirc    = "easeOutCirc"
String EaseInOutCirc  = "easeInOutCirc"
String EaseOutBounce  = "easeOutBounce"
String EaseInBack     = "easeInBack"
String EaseOutBack    = "easeOutBack"
String EaseInOutBack  = "easeInOutBack"
String Elastic        = "elastic"
String SwingFromTo    = "swingFromTo"
String SwingFrom      = "swingFrom"
String SwingTo        = "swingTo"
String Bounce         = "bounce"
String BouncePast     = "bouncePast"
String EaseFromTo     = "easeFromTo"
String EaseFrom       = "easeFrom"
String EaseTo         = "easeTo"
}
```

### `AAChartModel` 属性配置列表
```java
private String  animationType;         //动画类型
private Integer animationDuration;     //动画时间
private String  title;                 //标题内容
private String  subtitle;              //副标题内容
private String  chartType;             //图表类型
private String  stacking;              //堆积样式
private String  symbol;                //折线曲线连接点的类型："circle", "square", "diamond", "triangle","triangle-down"，默认是"circle"
private String  zoomType;              //缩放类型 AAChartZoomTypeX表示可沿着 x 轴进行手势缩放
private Boolean pointHollow;           //折线或者曲线的连接点是否为空心的
private Boolean inverted;              //x 轴是否翻转(垂直)
private Boolean xAxisReversed;         //x 轴翻转
private Boolean yAxisReversed;         //y 轴翻转
private Boolean crosshairs;            //是否显示准星线(默认显示)
private Boolean gradientColorEnable;   //是否要为渐变色
private Boolean polar;                 //是否极化图形(变为雷达图)
private Boolean dataLabelEnabled;      //是否显示数据
private Boolean xAxisLabelsEnabled;    //x轴是否显示数据
private String[]categories;            //x轴是否显示数据
private Integer xAxisGridLineWidth;    //x轴网格线的宽度
private Boolean yAxisLabelsEnabled;    //y轴是否显示数据
private String  yAxisTitle;            //y轴标题
private Integer yAxisGridLineWidth;    //y轴网格线的宽度
private String[]colorsTheme;           //图表主题颜色数组
private Boolean legendEnabled;         //是否显示图例
private String  legendLayout;          //图例数据项的布局。布局类型： "horizontal" 或 "vertical" 即水平布局和垂直布局 默认是：horizontal.
private String  legendAlign;           //设定图例在图表区中的水平对齐方式，合法值有left，center 和 right。
private String  legendVerticalAlign;   //设定图例在图表区中的垂直对齐方式，合法值有 top，middle 和 bottom。垂直位置可以通过 y 选项做进一步设定。
private String  backgroundColor;       //图表背景色
private Boolean options3dEnable;       //是否3D化图形(仅对条形图,柱状图有效)
private Integer options3dAlphaInt;
private Integer options3dBetaInt;
private Integer options3dDepth;        //3D图形深度
private Integer borderRadius;          //柱状图长条图头部圆角半径(可用于设置头部的形状,仅对条形图,柱状图有效)
private Integer markerRadius;          //折线连接点的半径长度
private AASeries[] series;
```

