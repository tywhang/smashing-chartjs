# smashing-chartjs

###### An easy interface to use all of [chartjs.org](http://www.chartjs.org/)'s charts.

Inspired by my own pain and suffering of trying to add a simple chart to [smashing](https://smashing.github.io/)

#### Make awesome charts like these:
<div>
  <img src="http://i.imgur.com/pW1SlcB.png" height="200">
  <img src="http://i.imgur.com/1xy9d9u.png" height="200">
  <img src="http://i.imgur.com/iNILDun.png" height="200">
</div>
<div>
  <img src="http://i.imgur.com/VJDvbwV.png" height="200">
  <img src="http://i.imgur.com/mYeuXcp.png" height="200">
  <img src="http://i.imgur.com/2xG1kFp.png" height="200">
</div>
## Installation
##### 1. Import Chartjs library
In `dashboards/layout.erb`, add this script tag:

`<script type="text/javascript" src="//cdnjs.cloudflare.com/ajax/libs/Chart.js/2.7.2/Chart.min.js"></script>`

before this script tag:

`<script type="text/javascript" src="/assets/application.js"></script>`

##### 2. Import Dashing.Chartjs Widget

`smashing install b4a67180da816eb0695f`

## Example
#### Let's create a simple line chart!

## Usage

### Line Chart

```
<div
  data-id="line-chart"
  data-view="Chartjs"
  data-type="line"
  data-labels="Week 1,Week 2,Week 3,Week 4,Week 5"
  data-colornames="blue,blue,blue,blue,blue"
  data-datasets="10,39,20,49,87"
  data-height="400"
  data-width="400"
></div>
```
<div><img src="http://i.imgur.com/VJDvbwV.png" width="400"></div>

### Bar Charts

```
<div
  data-id="bar-chart"
  data-view="Chartjs"
  data-type="bar"
  data-labels="Day 1,Day 2,Day 3,Day 4,Day 5"
  data-colornames="yellow,yellow,yellow,yellow,yellow"
  data-datasets="210,339,220,494,109"
  data-height="400"
  data-width="400"
></div>
```
<div><img src="http://i.imgur.com/1xy9d9u.png" width="400"></div>

### Radar Charts

```
<div
  data-id="radar-chart"
  data-view="Chartjs"
  data-type="radar"
  data-labels="Crossfit,Yoga,Weight Lifting,Running,Swimming,Watching TV"
  data-colornames="yellow,yellow,yellow,yellow,yellow,yellow"
  data-datasets="210,339,220,234,311,494"
  data-height="400"
  data-width="400"
></div>
```
<div><img src="http://i.imgur.com/2xG1kFp.png" width="400"></div>

### Polar Area Charts


```
<div
  data-id="chart-polarArea"
  data-view="Chartjs"
  data-type="polarArea"
  data-labels="Week 1,Week 2,Week 3,Week 4,Week 5"
  data-colornames="blue,yellow,green,cyan,gray"
  data-datasets="10,39,20,49,87"
  data-height="400"
  data-width="400"
></div>
```
<div><img src="http://i.imgur.com/pW1SlcB.png" width="400"></div>

### Pie Charts

`@pieChart(elementId, dataSets)`

```
<div
  data-id="chart-pie"
  data-view="Chartjs"
  data-type="pie"
  data-labels="Pumpkin,Apple,Pizza,Rhubarb"
  data-colornames="red,green,yellow,gray"
  data-datasets="13,32,40,20"
  data-height="400"
  data-width="400"
></div>
```

<div><img src="http://i.imgur.com/mYeuXcp.png" width="400"></div>

### Doughnut Charts

`@doughnutChart(elementId, dataSets)`

```
<div
  data-id="doughnut-pie"
  data-view="Chartjs"
  data-type="doughnut"
  data-labels="Apple Fritter,Chocolate,Maple"
  data-colornames="green,blue,darkgray"
  data-datasets="20,13,12"
  data-height="400"
  data-width="400"
></div>
```

<div><img src="http://i.imgur.com/iNILDun.png" width="400"></div>

## Colors

###### Currently available colors
blue | cyan | darkgray | gray | green | lightgray | magenta | red | yellow
