# Read: 12 - Docs for the HTML `<canvas>` Element & Chart.js

## Setting up

- [download Chart.js](https://github.com/chartjs/Chart.js)

```bash
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <title>Chart.js demo</title>
        <script src='Chart.min.js'></script>
    </head>
    <body>
    </body>
</html>
```

`Drawing a line chart`

```bash
<canvas id="buyers" width="600" height="400"></canvas>
```

```bash
<script>
    var buyers = document.getElementById('buyers').getContext('2d');
    new Chart(buyers).Line(buyerData);
</script>
```

```bash
var buyerData = {
 labels : ["January","February","March","April","May","June"],
 datasets : [
  {
   fillColor : "rgba(172,194,132,0.4)",
   strokeColor : "#ACC26D",
   pointColor : "#fff",
   pointStrokeColor : "#9DB86D",
   data : [203,156,99,251,305,247]
  }
 ]
}
```

#### Drawing a pie chart

```bash
<canvas id="countries" width="600" height="400"></canvas>

#----------

var countries= document.getElementById("countries").getContext("2d");
new Chart(countries).Pie(pieData, pieOptions);

#----------

var pieData = [
 {
  value: 20,
  color:"#878BB6"
 },
 {
  value : 40,
  color : "#4ACAB4"
 },
 {
  value : 10,
  color : "#FF8153"
 },
 {
  value : 30,
  color : "#FFEA88"
 }
];

```

#### for more information [Reference](https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/)

#### [documentation](https://www.chartjs.org/docs/latest/)

#### its a toll to draw things on your page without the need to design it as programer out side your code:)