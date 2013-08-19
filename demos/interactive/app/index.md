---
title       : Interactive Documents with R
subtitle    : Slidify + Shiny
author      : Ramnath Vaidyanathan
job         : R Hacker
--- &radio

## Interactive Quiz

What is 1 + 1?

1. 1
2. _2_
3. 3
4. 4

*** .hint

This is a hint

*** .explanation

This is an explanation









---

## Interactive Chart


<div id = 'chart1' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart1()
    });
    function drawchart1(){  
      var opts = {
 "dom": "chart1",
"width":    800,
"height":    400,
"x": "Eye",
"y": "Freq",
"group": "Hair",
"type": "multiBarChart",
"id": "chart1" 
},
        data = [
 {
 "Hair": "Black",
"Eye": "Brown",
"Sex": "Female",
"Freq":     36 
},
{
 "Hair": "Brown",
"Eye": "Brown",
"Sex": "Female",
"Freq":     66 
},
{
 "Hair": "Red",
"Eye": "Brown",
"Sex": "Female",
"Freq":     16 
},
{
 "Hair": "Blond",
"Eye": "Brown",
"Sex": "Female",
"Freq":      4 
},
{
 "Hair": "Black",
"Eye": "Blue",
"Sex": "Female",
"Freq":      9 
},
{
 "Hair": "Brown",
"Eye": "Blue",
"Sex": "Female",
"Freq":     34 
},
{
 "Hair": "Red",
"Eye": "Blue",
"Sex": "Female",
"Freq":      7 
},
{
 "Hair": "Blond",
"Eye": "Blue",
"Sex": "Female",
"Freq":     64 
},
{
 "Hair": "Black",
"Eye": "Hazel",
"Sex": "Female",
"Freq":      5 
},
{
 "Hair": "Brown",
"Eye": "Hazel",
"Sex": "Female",
"Freq":     29 
},
{
 "Hair": "Red",
"Eye": "Hazel",
"Sex": "Female",
"Freq":      7 
},
{
 "Hair": "Blond",
"Eye": "Hazel",
"Sex": "Female",
"Freq":      5 
},
{
 "Hair": "Black",
"Eye": "Green",
"Sex": "Female",
"Freq":      2 
},
{
 "Hair": "Brown",
"Eye": "Green",
"Sex": "Female",
"Freq":     14 
},
{
 "Hair": "Red",
"Eye": "Green",
"Sex": "Female",
"Freq":      7 
},
{
 "Hair": "Blond",
"Eye": "Green",
"Sex": "Female",
"Freq":      8 
} 
]
  
      var data = d3.nest()
        .key(function(d){
          return opts.group === undefined ? 'main' : d[opts.group]
        })
        .entries(data)
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .x(function(d) { return d[opts.x] })
          .y(function(d) { return d[opts.y] })
          .width(opts.width)
          .height(opts.height)
         
        
          
        

        
        
        
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>
















--- &interactive

## Interactive Console

<textarea class='interactive' id='interactive{{slide.num}}' data-cell='{{slide.num}}' data-results='asis' style='display:none'>require(googleVis)
M1 <- gvisMotionChart(Fruits, idvar = 'Fruit', timevar = 'Year')
print(M1, tag = 'chart')
</textarea>


---

## Non-Interactive Console


```r
require(googleVis)
M1 <- gvisMotionChart(Fruits, idvar = "Fruit", timevar = "Year")
print(M1, tag = "chart")
```

<!-- MotionChart generated in R 3.0.1 by googleVis 0.4.3 package -->
<!-- Mon Aug 19 11:19:31 2013 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartID229c586b10a1 () {
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
function drawChartMotionChartID229c586b10a1() {
  var data = gvisDataMotionChartID229c586b10a1();
  var options = {};
options["width"] =    600;
options["height"] =    500;

     var chart = new google.visualization.MotionChart(
       document.getElementById('MotionChartID229c586b10a1')
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
  callbacks.push(drawChartMotionChartID229c586b10a1);
})();
function displayChartMotionChartID229c586b10a1() {
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
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartID229c586b10a1"></script>
 
<!-- divChart -->
  
<div id="MotionChartID229c586b10a1"
  style="width: 600px; height: 500px;">
</div>



















---

## Interactive Chart with Shiny Controls

<div class="row-fluid">
  <div class="span4">
    <form class="well">
      <label class="control-label" for="sex">Choose Sex</label>
      <select id="sex">
        <option value="Male" selected="selected">Male</option>
        <option value="Female">Female</option>
      </select>
      <label class="control-label" for="type">Choose Type</label>
      <select id="type">
        <option value="multiBarChart" selected="selected">multiBarChart</option>
        <option value="multiBarHorizontalChart">multiBarHorizontalChart</option>
      </select>
    </form>
  </div>
  <div class="span8">
    <div id="nvd3plot" class="shiny-html-output nvd3 rChart"></div>
  </div>
</div>















--- &interactive height:450

## Interactive Console 

<textarea class='interactive' id='interactive{{slide.num}}' data-cell='{{slide.num}}' data-results='asis' style='display:none'>require(rCharts)
a <- Highcharts$new()
a$chart(type = "spline")
a$series(data = c(1, 3, 2, 4, 5, 4, 6, 2, 3, 5, NA), dashStyle = "longdash")
a$series(data = c(NA, 4, 1, 3, 4, 2, 9, 1, 2, 3, 4), dashStyle = "shortdot")
a$legend(symbolWidth = 80)
a$print('chart3')
</textarea>


--- &interactive height:450

<textarea class='interactive' id='interactive{{slide.num}}' data-cell='{{slide.num}}' data-results='asis' style='display:none'>n1 <- nPlot(mpg ~ wt, 
  data = mtcars, 
  type = 'scatterChart', 
  group = 'gear'
)
n1$addControls("x", "wt", names(mtcars))
n1$set(width = 450, height = 350)
n1
</textarea>

















--- &interactive

## Results = Markup

<textarea class='interactive' id='interactive{{slide.num}}' data-cell='{{slide.num}}' data-results='markup' style='display:none'>require(xtable)
options(xtable.type = 'html')
xtable(head(mtcars))
</textarea>
























