---
description: How to set the title and axis-titles in R
display_as: file_settings
language: r
layout: base
name: Axes Labels
order: 3
output:
  html_document:
    keep_md: true
page_type: example_index
permalink: r/figure-labels/
thumbnail: thumbnail/figure-labels.png
---


### New to Plotly?

Plotly's R library is free and open source!<br>
[Get started](https://plot.ly/r/getting-started/) by downloading the client and [reading the primer](https://plot.ly/r/getting-started/).<br>
You can set up Plotly to work in [online](https://plot.ly/r/getting-started/#hosting-graphs-in-your-online-plotly-account) or [offline](https://plot.ly/r/offline/) mode.<br>
We also have a quick-reference [cheatsheet](https://images.plot.ly/plotly-documentation/images/r_cheat_sheet.pdf) (new!) to help you get started!

### Version Check

Version 4 of Plotly's R package is now [available](https://plot.ly/r/getting-started/#installation)!<br>
Check out [this post](http://moderndata.plot.ly/upgrading-to-plotly-4-0-and-above/) for more information on breaking changes and new features available in this version.

```r
library(plotly)
packageVersion('plotly')
```

```
## [1] '4.9.1'
```

#### Figure Labels for 2D Charts

```r
library(plotly)
f <- list(
  family = "Courier New, monospace",
  size = 18,
  color = "#7f7f7f"
)
x <- list(
  title = "x Axis",
  titlefont = f
)
y <- list(
  title = "y Axis",
  titlefont = f
)
p <- plot_ly(x = ~rnorm(10), y = ~rnorm(10), mode = "markers") %>%
  layout(xaxis = x, yaxis = y)

p
```

<div id="htmlwidget-2a02baa414203feb7960" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-2a02baa414203feb7960">{"x":{"visdat":{"166b1feaa9c6":["function () ","plotlyVisDat"]},"cur_data":"166b1feaa9c6","attrs":{"166b1feaa9c6":{"x":{},"y":{},"mode":"markers","alpha_stroke":1,"sizes":[10,100],"spans":[1,20]}},"layout":{"margin":{"b":40,"l":60,"t":25,"r":10},"xaxis":{"domain":[0,1],"automargin":true,"title":"x Axis","titlefont":{"family":"Courier New, monospace","size":18,"color":"#7f7f7f"}},"yaxis":{"domain":[0,1],"automargin":true,"title":"y Axis","titlefont":{"family":"Courier New, monospace","size":18,"color":"#7f7f7f"}},"hovermode":"closest","showlegend":false},"source":"A","config":{"showSendToCloud":false},"data":[{"x":[-0.648081509232254,-0.780018219202772,-0.196300260802734,-0.883538580033763,-0.851785568321704,-0.454677527754975,0.48584562438806,-0.6362038482548,1.55081194291805,0.29096081049606],"y":[-0.578328204988257,0.637673271090965,0.686084786260081,-0.888773036782917,-1.06935081705634,-1.50470591308157,-0.161173595943807,-0.140845374996017,0.184593239218131,1.37066608255108],"mode":"markers","type":"scatter","marker":{"color":"rgba(31,119,180,1)","line":{"color":"rgba(31,119,180,1)"}},"error_y":{"color":"rgba(31,119,180,1)"},"error_x":{"color":"rgba(31,119,180,1)"},"line":{"color":"rgba(31,119,180,1)"},"xaxis":"x","yaxis":"y","frame":null}],"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>

#### Figure Labels for 3D Charts


```r
library(plotly)
set.seed(123)

n <- 100
theta <- runif(n, 0, 2*pi)
u <- runif(n, -1, 1)

p <- plot_ly(x = ~sqrt(1 - u^2) * cos(theta), y = ~sqrt(1 - u^2) * sin(theta), z = ~u) %>%
  layout(
    title = "Layout options in a 3d scatter plot",
    scene = list(
      xaxis = list(title = "Cos"),
      yaxis = list(title = "Sin"),
      zaxis = list(title = "Z")
    ))

p
```

<div id="htmlwidget-1d0cbb04274684b24dcc" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-1d0cbb04274684b24dcc">{"x":{"visdat":{"166b1ea1f38e":["function () ","plotlyVisDat"]},"cur_data":"166b1ea1f38e","attrs":{"166b1ea1f38e":{"x":{},"y":{},"z":{},"alpha_stroke":1,"sizes":[10,100],"spans":[1,20]}},"layout":{"margin":{"b":40,"l":60,"t":25,"r":10},"title":"Layout options in a 3d scatter plot","scene":{"xaxis":{"title":"Cos"},"yaxis":{"title":"Sin"},"zaxis":{"title":"Z"}},"hovermode":"closest","showlegend":false},"source":"A","config":{"showSendToCloud":false},"data":[{"x":[-0.229193883311357,0.224643206870548,-0.840648021692964,0.309270326241757,0.930308914800237,0.599479480719512,-0.550731595660337,0.761441854442743,-0.932982244771507,-0.682242717521781,0.47400677151706,-0.878422321773199,-0.209939564222654,-0.399596542634172,0.716206651388937,0.564810975341935,0.0244593193514911,0.40404324059619,-0.46334057987687,0.941759908722391,0.734270219783496,-0.328062131401671,-0.586138167692072,0.827641566344769,-0.539051512435482,-0.0642131573355019,-0.694776432926075,-0.477591728090637,-0.169991704412012,0.557171076246214,0.945048274325303,0.508672698362255,-0.341518304871486,0.248117254510656,0.987181973255833,-0.938320416136226,0.0406615263136733,0.171762073552492,-0.116820984877701,0.114344010836886,0.577846989724385,-0.845086838932023,-0.174362869066048,-0.526223546323014,0.418874755415653,0.542303237528664,0.0907648096723945,-0.520077004840287,-0.0862672674979793,0.555195477919049,0.689490306480688,-0.934764819348956,0.294883622327619,0.621202590354263,-0.582978941297419,0.263129081393406,0.688531533575101,0.0171300815709318,0.785492941136622,-0.581927667574728,-0.508412909639382,0.79152458081207,-0.711468245497092,-0.147739786542687,0.378200113437339,-0.945980064925153,0.32313889681922,0.317086930565473,0.270800526081547,-0.821016769768906,0.0271480557358623,-0.533068055139599,-0.169921889729938,0.869945524043923,-0.930356487562022,0.181373673304158,-0.704005501218815,-0.757945994082825,-0.39523300604511,0.755639131017689,0.0294038798384566,-0.456468042091779,-0.790086900069836,0.209809347271936,0.783967250380178,-0.916844172289507,0.878761323821062,0.776033494933612,0.425820423787695,0.269934808359163,0.607895112915124,-0.53421320359281,-0.131897617929592,-0.536754588840618,-0.207443533633373,0.380717996784998,0.197992149765311,0.788692612892845,-0.703112813518284,-0.986739825624741],"y":[0.952616919833917,-0.915283319479935,0.541102810577297,-0.279581876695709,-0.365179422959334,0.176440269081981,-0.098278514733586,-0.610666125457578,-0.312472185764466,0.190725577036477,-0.131810112086581,0.265206379615944,-0.429021811025028,-0.196175818522034,0.540737615763852,-0.411308981528312,0.994829549421663,0.109332739806886,0.869531996189479,-0.276794380642386,-0.611029720577994,-0.873222078191382,-0.713130893659194,-0.029811335255629,-0.800806370090485,-0.240839619638166,-0.197437365319556,-0.320820979888779,0.676890072060438,0.738342466132962,-0.22359634136471,-0.358461526787403,-0.873870987767307,-0.8447570140191,0.15389891507682,0.131762956414749,-0.764271956543943,0.801666565795103,0.255805723049756,0.986028038130152,0.724063956879287,0.50303985711426,0.105013311045814,0.568580940074179,0.595558893121832,0.645609207531069,0.848225451611652,0.112953224876055,0.856698410704728,-0.690080405976799,0.204226123487346,0.355232705244387,-0.928862803066335,0.597457020599783,-0.234844000053652,0.939339230212891,0.710792212731195,-0.824079928953325,-0.60893229921135,0.585869557156408,-0.861101133054217,0.536761903887355,0.635476784933227,0.956758373258511,-0.879420560627406,0.317146978683707,-0.815192513592513,-0.76702124696848,-0.946685859092964,0.326068319343436,-0.965241422940453,-0.562121655547707,-0.664964955665109,0.00341504661632662,0.145457597653526,0.954667856898849,0.662633987382977,-0.649582325384626,0.531265883253406,0.63425325258815,0.733053119421766,-0.806804910230533,0.449692402670062,-0.857387608944795,0.591432834128285,0.397487707326718,-0.083307062245213,-0.617320271562981,-0.36848193454671,0.530210429446609,0.653039564127736,-0.766252326631552,0.198027129632175,-0.808888702726281,0.438169750280007,0.922265453581195,-0.962329697098106,0.525877150844332,0.148932441685354,-0.0714568669404884],"z":[0.19997791852802,-0.334352919366211,-0.0227739326655865,0.908947654999793,-0.0341952056623995,0.780700444243848,0.828876373823732,0.217469964642078,-0.178620446939021,-0.705810618121177,0.870599606540054,-0.397542200051248,-0.878558856900781,0.895453880075365,0.441192546859384,-0.715411408804357,0.098569312132895,0.908182477112859,0.170966706238687,-0.190979436505586,0.29578695865348,-0.360358765814453,-0.384559978265315,-0.560464737471193,-0.261022268328816,0.96843840694055,-0.691595398355275,-0.817912000231445,-0.716186184436083,0.380014203023165,0.238512966781855,0.782788234297186,0.345998185221106,0.474155475851148,0.0422714515589178,0.31967689935118,0.643610920291394,0.572563103400171,0.959643834736198,-0.121136927511543,-0.376595595851541,-0.181050094775856,-0.979065776336938,-0.63230095198378,0.685458637773991,-0.537676435895264,-0.521800088696182,-0.846617669332772,-0.508552643936127,0.46427041105926,0.694906330201775,-0.00494546582922339,-0.224181940313429,-0.507102011702955,-0.777807077392936,-0.220011129509658,0.143870627973229,-0.566214474383742,-0.110463995952159,-0.564018662553281,0.00459912652149796,-0.292190856300294,0.29997031763196,-0.250572086777538,-0.289109238423407,0.0673758909106255,0.480668720789254,-0.557794124353677,-0.1745077627711,-0.468626626301557,0.259946106933057,-0.632343018427491,0.727288222871721,0.493136008270085,0.336569299455732,0.236035746522248,-0.255523879546672,0.0596713717095554,0.749364685732871,0.163500199560076,0.679535529576242,-0.375103670172393,0.416580644436181,-0.469964387826622,0.188686388079077,-0.0374203990213573,-0.46993453707546,0.129180869553238,0.826376446057111,0.803748778998852,-0.451666756998748,-0.357034487184137,0.971281768754125,0.239986620377749,0.874628178309649,-0.0669345953501761,-0.186334813479334,0.318460648413748,-0.695306766312569,0.145734116435051],"type":"scatter3d","mode":"markers","marker":{"color":"rgba(31,119,180,1)","line":{"color":"rgba(31,119,180,1)"}},"error_y":{"color":"rgba(31,119,180,1)"},"error_x":{"color":"rgba(31,119,180,1)"},"line":{"color":"rgba(31,119,180,1)"},"frame":null}],"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>