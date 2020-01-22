---
name: geom_errorbar
permalink: ggplot2/geom_errorbar/
description: Examples of geom_errobar in R and ggplot2
layout: base
thumbnail: thumbnail/error-bar.jpg
language: ggplot2
page_type: example_index
display_as: statistics
order: 2
output:
  html_document:
    keep_md: true
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

### Basic Error Bar


```r
library(plotly)

df <- data.frame(x = 1:10,
                 y = 1:10,
                 ymin = (1:10) - runif(10),
                 ymax = (1:10) + runif(10),
                 xmin = (1:10) - runif(10),
                 xmax = (1:10) + runif(10))

p <- ggplot(data = df,aes(x = x,y = y)) + 
    geom_point() + 
    geom_errorbar(aes(ymin = ymin,ymax = ymax)) + 
    geom_errorbarh(aes(xmin = xmin,xmax = xmax))

p <- ggplotly(p)

p
```

<div id="htmlwidget-14c1e96fdd40d2708e03" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-14c1e96fdd40d2708e03">{"x":{"data":[{"x":[1,2,3,4,5,6,7,8,9,10],"y":[1,2,3,4,5,6,7,8,9,10],"text":["x:  1<br />y:  1","x:  2<br />y:  2","x:  3<br />y:  3","x:  4<br />y:  4","x:  5<br />y:  5","x:  6<br />y:  6","x:  7<br />y:  7","x:  8<br />y:  8","x:  9<br />y:  9","x: 10<br />y: 10"],"type":"scatter","mode":"markers","marker":{"autocolorscale":false,"color":"rgba(0,0,0,1)","opacity":1,"size":5.66929133858268,"symbol":"circle","line":{"width":1.88976377952756,"color":"rgba(0,0,0,1)"}},"hoveron":"points","showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[1,2,3,4,5,6,7,8,9,10],"y":[1,2,3,4,5,6,7,8,9,10],"text":["ymin: 0.3141282<br />ymax:  1.010890<br />x:  1<br />y:  1","ymin: 1.9577362<br />ymax:  2.283940<br />x:  2<br />y:  2","ymin: 2.3337996<br />ymax:  3.988620<br />x:  3<br />y:  3","ymin: 3.8956715<br />ymax:  4.353248<br />x:  4<br />y:  4","ymin: 4.6428314<br />ymax:  5.293204<br />x:  5<br />y:  5","ymin: 5.7111372<br />ymax:  6.402205<br />x:  6<br />y:  6","ymin: 6.8251430<br />ymax:  7.302166<br />x:  7<br />y:  7","ymin: 7.5178008<br />ymax:  8.461275<br />x:  8<br />y:  8","ymin: 8.6921776<br />ymax:  9.539338<br />x:  9<br />y:  9","ymin: 9.9936697<br />ymax: 10.235341<br />x: 10<br />y: 10"],"type":"scatter","mode":"lines","opacity":1,"line":{"color":"transparent"},"error_y":{"array":[0.010889996541664,0.28394024935551,0.988619947806001,0.353247926570475,0.293204418383539,0.402204852085561,0.302166128298268,0.461275323294103,0.539337899768725,0.23534105787985],"arrayminus":[0.68587180878967,0.0422638223972172,0.666200395207852,0.104328502435237,0.357168646994978,0.28886278020218,0.174857016419992,0.48219919227995,0.307822422357276,0.00633031968027353],"type":"data","width":17.5425210390064,"symmetric":false,"color":"rgba(0,0,0,1)"},"showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"x":[1,2,3,4,5,6,7,8,9,10],"y":[1,2,3,4,5,6,7,8,9,10],"text":["xmin: 0.002657405<br />xmax:  1.726768<br />x:  1<br />y:  1","xmin: 1.295398031<br />xmax:  2.000198<br />x:  2<br />y:  2","xmin: 2.813929986<br />xmax:  3.570520<br />x:  3<br />y:  3","xmin: 3.181886821<br />xmax:  4.302012<br />x:  4<br />y:  4","xmin: 4.322320751<br />xmax:  5.551382<br />x:  5<br />y:  5","xmin: 5.743630086<br />xmax:  6.847205<br />x:  6<br />y:  6","xmin: 6.854053044<br />xmax:  7.489619<br />x:  7<br />y:  7","xmin: 7.048401819<br />xmax:  8.394063<br />x:  8<br />y:  8","xmin: 8.067423981<br />xmax:  9.935457<br />x:  9<br />y:  9","xmin: 9.787628314<br />xmax: 10.081867<br />x: 10<br />y: 10"],"type":"scatter","mode":"lines","opacity":1,"line":{"color":"transparent"},"error_x":{"array":[0.726768156746402,0.000198018038645387,0.570520496694371,0.302011734107509,0.551382361678407,0.847205142956227,0.489619404543191,0.394063252024353,0.935457240790129,0.0818674545735121],"arrayminus":[0.997342594899237,0.70460196887143,0.186070014489815,0.818113178713247,0.677679248852655,0.256369913928211,0.145946955541149,0.95159818069078,0.932576019316912,0.212371685542166],"type":"data","width":12.9154248769769,"symmetric":false,"color":"rgba(0,0,0,1)"},"showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null}],"layout":{"margin":{"t":26.2283105022831,"r":7.30593607305936,"b":40.1826484018265,"l":48.9497716894977},"plot_bgcolor":"rgba(235,235,235,1)","paper_bgcolor":"rgba(255,255,255,1)","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[-0.519709724644199,10.972367129745],"tickmode":"array","ticktext":["0.0","2.5","5.0","7.5","10.0"],"tickvals":[0,2.5,5,7.5,10],"categoryorder":"array","categoryarray":["0.0","2.5","5.0","7.5","10.0"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"y","title":{"text":"x","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"yaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[-0.192665399229154,10.9567935904395],"tickmode":"array","ticktext":["0.0","2.5","5.0","7.5","10.0"],"tickvals":[0,2.5,5,7.5,10],"categoryorder":"array","categoryarray":["0.0","2.5","5.0","7.5","10.0"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"x","title":{"text":"y","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"shapes":[{"type":"rect","fillcolor":null,"line":{"color":null,"width":0,"linetype":[]},"yref":"paper","xref":"paper","x0":0,"x1":1,"y0":0,"y1":1}],"showlegend":false,"legend":{"bgcolor":"rgba(255,255,255,1)","bordercolor":"transparent","borderwidth":1.88976377952756,"font":{"color":"rgba(0,0,0,1)","family":"","size":11.689497716895}},"hovermode":"closest","barmode":"relative"},"config":{"doubleClick":"reset","showSendToCloud":false},"source":"A","attrs":{"395b39584521":{"x":{},"y":{},"type":"scatter"},"395b47434cc5":{"ymin":{},"ymax":{},"x":{},"y":{}},"395b28283a07":{"xmin":{},"xmax":{},"x":{},"y":{}}},"cur_data":"395b39584521","visdat":{"395b39584521":["function (y) ","x"],"395b47434cc5":["function (y) ","x"],"395b28283a07":["function (y) ","x"]},"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>

### Margin Error Bar


```r
library(plotly)

population <- data.frame(Year=seq(1790, 1970, length.out=length(uspop)), 
                         Population=uspop, 
                         Error=rnorm(length(uspop), 5))

library(ggplot2)
p <- ggplot(population, aes(x=Year, y=Population, 
                       ymin=Population-Error, ymax=Population+Error))+
  geom_line()+
  geom_point(pch=2)+
  geom_errorbar(width=0.9)

p <- ggplotly(p)

p
```

<div id="htmlwidget-1faffc77daa607f5364e" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-1faffc77daa607f5364e">{"x":{"data":[{"x":[1790,1800,1810,1820,1830,1840,1850,1860,1870,1880,1890,1900,1910,1920,1930,1940,1950,1960,1970],"y":[3.93,5.31,7.24,9.64,12.9,17.1,23.2,31.4,39.8,50.2,62.9,76,92,105.7,122.8,131.7,151.3,179.3,203.2],"text":["Year: 1790<br />Population:   3.93<br />Population - Error:  -3.7583216<br />Population + Error:  11.61832","Year: 1800<br />Population:   5.31<br />Population - Error:  -0.7149679<br />Population + Error:  11.33497","Year: 1810<br />Population:   7.24<br />Population - Error:   0.3270041<br />Population + Error:  14.15300","Year: 1820<br />Population:   9.64<br />Population - Error:   5.9165817<br />Population + Error:  13.36342","Year: 1830<br />Population:  12.90<br />Population - Error:   7.9533401<br />Population + Error:  17.84666","Year: 1840<br />Population:  17.10<br />Population - Error:  11.5987934<br />Population + Error:  22.60121","Year: 1850<br />Population:  23.20<br />Population - Error:  17.0307084<br />Population + Error:  29.36929","Year: 1860<br />Population:  31.40<br />Population - Error:  28.3304186<br />Population + Error:  34.46958","Year: 1870<br />Population:  39.80<br />Population - Error:  35.2340047<br />Population + Error:  44.36600","Year: 1880<br />Population:  50.20<br />Population - Error:  46.0696674<br />Population + Error:  54.33033","Year: 1890<br />Population:  62.90<br />Population - Error:  58.6356055<br />Population + Error:  67.16439","Year: 1900<br />Population:  76.00<br />Population - Error:  70.4721298<br />Population + Error:  81.52787","Year: 1910<br />Population:  92.00<br />Population - Error:  88.5338634<br />Population + Error:  95.46614","Year: 1920<br />Population: 105.70<br />Population - Error: 101.2458003<br />Population + Error: 110.15420","Year: 1930<br />Population: 122.80<br />Population - Error: 117.0973784<br />Population + Error: 128.50262","Year: 1940<br />Population: 131.70<br />Population - Error: 125.9571372<br />Population + Error: 137.44286","Year: 1950<br />Population: 151.30<br />Population - Error: 145.8608506<br />Population + Error: 156.73915","Year: 1960<br />Population: 179.30<br />Population - Error: 176.4443248<br />Population + Error: 182.15568","Year: 1970<br />Population: 203.20<br />Population - Error: 199.1237833<br />Population + Error: 207.27622"],"type":"scatter","mode":"lines+markers","line":{"width":1.88976377952756,"color":"transparent","dash":"solid"},"hoveron":"points","showlegend":false,"xaxis":"x","yaxis":"y","hoverinfo":"text","marker":{"autocolorscale":false,"color":"rgba(0,0,0,1)","opacity":1,"size":5.66929133858268,"symbol":"triangle-up-open","line":{"width":1.88976377952756,"color":"rgba(0,0,0,1)"}},"opacity":1,"error_y":{"array":[7.6883215716518,6.02496792896645,6.91299594229051,3.72341830075409,4.94665987169411,5.50120663434397,6.16929157257926,3.06958136411827,4.56599525624659,4.13033257030776,4.26439448798345,5.52787021145036,3.46613659264615,4.45419974092113,5.70262157589177,5.7428627725896,5.43914943456906,2.85567524038532,4.07621669514552],"arrayminus":[7.6883215716518,6.02496792896645,6.91299594229051,3.7234183007541,4.94665987169411,5.50120663434397,6.16929157257926,3.06958136411827,4.56599525624659,4.13033257030776,4.26439448798345,5.52787021145036,3.46613659264615,4.45419974092113,5.70262157589177,5.74286277258959,5.43914943456906,2.85567524038532,4.07621669514552],"type":"data","width":1.01311623699693,"symmetric":false,"color":"rgba(0,0,0,1)"},"frame":null}],"layout":{"margin":{"t":26.2283105022831,"r":7.30593607305936,"b":40.1826484018265,"l":43.1050228310502},"plot_bgcolor":"rgba(235,235,235,1)","paper_bgcolor":"rgba(255,255,255,1)","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[1780.505,1979.495],"tickmode":"array","ticktext":["1800","1850","1900","1950"],"tickvals":[1800,1850,1900,1950],"categoryorder":"array","categoryarray":["1800","1850","1900","1950"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"y","title":{"text":"Year","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"yaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[-14.3100484849917,217.827943608485],"tickmode":"array","ticktext":["0","50","100","150","200"],"tickvals":[0,50,100,150,200],"categoryorder":"array","categoryarray":["0","50","100","150","200"],"nticks":null,"ticks":"outside","tickcolor":"rgba(51,51,51,1)","ticklen":3.65296803652968,"tickwidth":0.66417600664176,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(255,255,255,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"x","title":{"text":"Population","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"shapes":[{"type":"rect","fillcolor":null,"line":{"color":null,"width":0,"linetype":[]},"yref":"paper","xref":"paper","x0":0,"x1":1,"y0":0,"y1":1}],"showlegend":false,"legend":{"bgcolor":"rgba(255,255,255,1)","bordercolor":"transparent","borderwidth":1.88976377952756,"font":{"color":"rgba(0,0,0,1)","family":"","size":11.689497716895}},"hovermode":"closest","barmode":"relative"},"config":{"doubleClick":"reset","showSendToCloud":false},"source":"A","attrs":{"395b7e5eda6c":{"x":{},"y":{},"ymin":{},"ymax":{},"type":"scatter"},"395b79d5d801":{"x":{},"y":{},"ymin":{},"ymax":{}},"395b31dbfe2c":{"x":{},"y":{},"ymin":{},"ymax":{}}},"cur_data":"395b7e5eda6c","visdat":{"395b7e5eda6c":["function (y) ","x"],"395b79d5d801":["function (y) ","x"],"395b31dbfe2c":["function (y) ","x"]},"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>
