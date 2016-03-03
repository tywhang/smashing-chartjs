# dashing-chartjs

###### An easy interface to use all of [chartjs.org](http://www.chartjs.org/)'s charts.

Inspired by my own pain and suffering of trying to add a simple chart to [dashing](http://dashing.io)

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

`<script type="text/javascript" src="//cdnjs.cloudflare.com/ajax/libs/Chart.js/1.0.2/Chart.min.js"></script>`

before this script tag:

`<script type="text/javascript" src="/assets/application.js"></script>`

##### 2. Import Dashing.Chartjs Widget

Copy and paste the contents of [this file](https://raw.githubusercontent.com/tywhang/dashing-chartjs/master/dashing-chartjs.js.coffee) into: `assets/javascripts/dashing-chartjs.coffee`

Then in `assets/javascripts/application.coffee`, add `#= require dashing-chartjs` right after `#= require dashing.js` so it looks like this:

```
# dashing.js is located in the dashing framework
# It includes jquery & batman for you.
#= require dashing.js
#= require dashing-chartjs
```

##### 3. Create a your widget!
Simply inherit from `Dashing.Chartjs` (instead of Dashing.Widget)

```
class Dashing.MyCharts extends Dashing.Chartjs
```

Now you have access to all the functions!!!

## Example
#### Let's create a simple line chart!

##### 1. Add your html
###### widgets/example/example.html
`<canvas id="myChart" width="400" height="300"></canvas>`

##### 2. Call the lineChart function and pass in parameters
###### widgets/example/example.coffee
```
class Dashing.Example extends Dashing.Chartjs
  ready: ->
    @lineChart 'myChart', # The ID of your html element
      ["Week 1", "Week 2", "Week 3", "Week 4", "Week 5"], # Horizontal labels
      [
        label: 'Number of pushups' # Text displayed when hovered
        colorName: 'blue' # Color of data
        data: [10, 39, 20, 49, 87] # Vertical points
      ]
```

##### 3. Awe at your beautiful chart
<div><img src="http://i.imgur.com/VJDvbwV.png" width="400"></div>

#### Displaying multiple data in one chart is a breeze too!
```
@lineChart 'myChart', # Horizontal labels
  ["Week 1", "Week 2", "Week 3", "Week 4", "Week 5"],
  [{
      # First data points
      label: 'Number of pushups'
      colorName: 'blue'
      data: [10, 39, 20, 49, 87]
    }, {
      # Second data points
      label: 'Number of pullups'
      colorName: 'red'
      data: [3, 2, 10, 12, 20]
    }
  ]
```
<div><img src="http://i.imgur.com/mWlAndA.png" width="400"></div>


## Usage

### Line Chart

`@lineChart(elementId, horizontalLabels, dataSets)`

```
class Dashing.Line extends Dashing.Chartjs
  ready: ->
    @lineChart 'myChart',
      ["Week 1", "Week 2", "Week 3", "Week 4", "Week 5"],
      [
        label: 'Number of pushups'
        colorName: 'blue'
        data: [10, 39, 20, 49, 87]
      ]
```
<div><img src="http://i.imgur.com/VJDvbwV.png" width="400"></div>

### Bar Charts

`@barChart(elementId, horizontalLabels, dataSets)`

```
class Dashing.Bar extends Dashing.Chartjs
  ready: ->
    @lineChart 'myChart',
      ["Day 1", "Day 2", "Day 3", "Day 4", "Day 5"],
      [
        label: 'Customer count'
        colorName: 'blue'
        data: [210, 339, 220, 494, 109]
      ]
```
<div><img src="http://i.imgur.com/1xy9d9u.png" width="400"></div>

### Radar Charts

`@radarChart(elementId, horizontalLabels, dataSets)`

```
class Dashing.Radar extends Dashing.Chartjs
  ready: ->
    @radarChart 'myChart',
      ["Crossfit", "Yoga", "Weight Lifting", "Running", "Swimming", "Watching TV"],
      [
        label: 'Favorite Workout'
        colorName: 'yellow'
        data: [210, 339, 220, 234, 311, 494]
      ]
```
<div><img src="http://i.imgur.com/2xG1kFp.png" width="400"></div>

### Polar Area Charts

`@polarAreaChart(elementId, dataSets)`

```
class Dashing.Polar extends Dashing.Chartjs
  ready: ->
    @polarAreaChart("otherChart",
      [{
        value: 300
        colorName: 'red'
        label: "Red"
      }, {
        value: 50
        colorName: 'green'
        label: "Green"
      }, {
        value: 88
        colorName: 'yellow'
        label: "Yellow"
      }])
```
<div><img src="http://i.imgur.com/pW1SlcB.png" width="400"></div>

### Pie Charts

`@pieChart(elementId, dataSets)`

```
class Dashing.Pie extends Dashing.Chartjs
  ready: ->
    @pieChart("otherChart",
      [{
        value: 13
        colorName: 'red'
        label: "Pumpkim"
      }, {
        value: 32
        colorName: 'green'
        label: "Apple"
      }, {
        value: 40
        colorName: 'yellow'
        label: "Pizza"
      }, {
        value: 20
        colorName: 'gray'
        label: "Rhubarb"
      }])
```

<div><img src="http://i.imgur.com/mYeuXcp.png" width="400"></div>

### Doughnut Charts

`@doughnutChart(elementId, dataSets)`

```
class Dashing.Doughnut extends Dashing.Chartjs
  ready: ->
    @doughnutChart("otherChart",
      [{
        value: 20
        colorName: 'green'
        label: "Apple Fritter"
      }, {
        value: 13
        colorName: 'blue'
        label: "Chocolate"
      }, {
        value: 12
        colorName: 'darkgray'
        label: "Maple"
      }])
```

<div><img src="http://i.imgur.com/iNILDun.png" width="400"></div>