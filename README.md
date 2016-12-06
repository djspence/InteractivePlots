# Interactive Plots
D. Spence  
December 5, 2016  



## Overview

### A Few Powerful R Libraries  

- googleVis
- plotly
- leaflet


```r
library(googleVis)
library(plotly)
library(leaflet)
```

## googleVis Motion Chart - The Data

This example uses the Fruits data set.


```r
data("Fruits")
Fruits
```

```
##     Fruit Year Location Sales Expenses Profit       Date
## 1  Apples 2008     West    98       78     20 2008-12-31
## 2  Apples 2009     West   111       79     32 2009-12-31
## 3  Apples 2010     West    89       76     13 2010-12-31
## 4 Oranges 2008     East    96       81     15 2008-12-31
## 5 Bananas 2008     East    85       76      9 2008-12-31
## 6 Oranges 2009     East    93       80     13 2009-12-31
## 7 Bananas 2009     East    94       78     16 2009-12-31
## 8 Oranges 2010     East    98       91      7 2010-12-31
## 9 Bananas 2010     East    81       71     10 2010-12-31
```

## googleVis Motion Chart - The Code


```r
M <- gvisMotionChart(data = Fruits, 
                     idvar = "Fruit", 
                     timevar = "Year", 
                     options = list(width=600, height=400))
#OR
M <- gvisMotionChart(Fruits, "Fruit", "Year", 
                     options = list(width=600, height=400))
```

To save the chart as a stand-alone HTML file:  

```r
print(M, file="FruitMotionPlot.html")
```

To embed plot in RMarkdown document:  
Use results='asis' in r chunk options.  

```r
print(M, tag='chart')
```

## googleVis Motion Chart - The Plot

<!-- MotionChart generated in R 3.3.2 by googleVis 0.6.1 package -->
<!-- Mon Dec 05 21:32:09 2016 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartID201c6dab7d70 () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
"Apples",
2008,
"West",
98,
78,
20,
"2008-12-31"
],
[
"Apples",
2009,
"West",
111,
79,
32,
"2009-12-31"
],
[
"Apples",
2010,
"West",
89,
76,
13,
"2010-12-31"
],
[
"Oranges",
2008,
"East",
96,
81,
15,
"2008-12-31"
],
[
"Bananas",
2008,
"East",
85,
76,
9,
"2008-12-31"
],
[
"Oranges",
2009,
"East",
93,
80,
13,
"2009-12-31"
],
[
"Bananas",
2009,
"East",
94,
78,
16,
"2009-12-31"
],
[
"Oranges",
2010,
"East",
98,
91,
7,
"2010-12-31"
],
[
"Bananas",
2010,
"East",
81,
71,
10,
"2010-12-31"
] 
];
data.addColumn('string','Fruit');
data.addColumn('number','Year');
data.addColumn('string','Location');
data.addColumn('number','Sales');
data.addColumn('number','Expenses');
data.addColumn('number','Profit');
data.addColumn('string','Date');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartMotionChartID201c6dab7d70() {
var data = gvisDataMotionChartID201c6dab7d70();
var options = {};
options["width"] = 600;
options["height"] = 400;
options["state"] = "";

    var chart = new google.visualization.MotionChart(
    document.getElementById('MotionChartID201c6dab7d70')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "motionchart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartMotionChartID201c6dab7d70);
})();
function displayChartMotionChartID201c6dab7d70() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartID201c6dab7d70"></script>
 
<!-- divChart -->
  
<div id="MotionChartID201c6dab7d70" 
  style="width: 600; height: 400;">
</div>

