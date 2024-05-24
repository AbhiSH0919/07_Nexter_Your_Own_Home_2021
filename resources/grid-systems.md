/\*

<div class="container">
  <div class="header">header</div>
  <div class="box-0">box-0</div>
  <div class="box-1">box 1</div>
  <div class="box-2">box 2</div>
  <div class="side">side</div>
  <div class="main">main</div>
  <div class="foot">foot</div>
</div>
*/

/\*

body {
margin: 0;
padding: 0;
box-sizing: border-box;
}

\*/

# /\*

GRID AREA NAMEING SYSTEM========USE ONLY SMALL LAYOUTS============
.container {
width: 900px;
height: 900px;
margin: 10px auto;
background-color: green;
display: grid;
grid-template-rows: 100px 200px 400px 100px;
grid-template-columns: repeat(3, 1fr) 200px;
gap: 30px;
grid-template-areas:
"head head head head" "box-0 box-1 box-2 side" "main main main side"
"foot foot foot foot";
}

.container > \* {
background-color: red;
padding: 20px;
}

.header {
grid-area: head;
background-color: gold;
}

.box-0 {
grid-area: box-0;
}

.box-1 {
grid-area: box-1;
}

.box-2 {
grid-area: box-2;
}

.side {
grid-area: side;
background-color: brown;
}

.main {
grid-area: main;
background-color: blue;
}

.foot {
grid-area: foot;
background-color: black;
}
==================================================================
\*/

# /\*

GRID ROWS & COLUMNS = (LINES) NAMING SYSTEM=======================

.container {
width: 900px;
height: 900px;
margin: 10px auto;
background-color: green;
display: grid;
grid-template-rows: [head-start] 100px [head-end box-start] 200px [box-end main-start] 400px [main-end foot-start] 100px
[foot-end];

grid-template-columns: [grid-start] repeat(3, 1fr) [grid-side] 200px [grid-end];
gap: 30px;
}

.header {
background-color: yellow;
grid-row: head-start / head-end;
grid-column: grid-start / grid-end;
}

.side {
background-color: brown;
grid-row: box-start / main-end;
grid-column: grid-side / grid-end;
}

.main {
background-color: blue;
grid-row: main-start / main-end;
grid-column: grid-start / grid-side;
}

.foot {
background-color: black;
grid-row: foot-start / foot-end;
grid-column: grid-start / grid-end;
}

.box-0 {
background-color: red;
grid-row: foot-start / foot-end;
grid-column: grid-side / grid-start;
z-index: 11;
}

.box-1 {
background-color: blueviolet;
grid-row: box-start / box-end;
grid-column: grid-start / grid-end;
z-index: 10;
}

.box-2 {
background-color: aqua;
grid-row: box-start / main-end;
grid-column: grid-start / grid-end;
}
==================================================================
\*/

<!-- ============================================================= -->

body {
margin: 0;
padding: 0;
box-sizing: border-box;
font-size: 30px;
font-weight: bolder;
font-family: sans-serif;
color: darkblue;
}

<!-- ===============GRID CONTENT AND FUNCTION===================== -->

<!--

    <div class="container">
        <div class="item item--1">red is the brighest color <br> use for the grid min-content</div>
        <div class="item item--2">yellow</div>
        <div class="item item--3">blue</div>
        <div class="item item--4">green</div>
        <div class="item item--5">black</div>
        <div class="item item--6">violet color is great its awesome useing on minmax function</div>
        <div class="item item--7">gold</div>
        <div class="item item--8">aqua color is good or the best for the home walls
            <br> use for grid max-content
        </div>
    </div>

  -->
<!--

      <div class="container">
        <div class="item item--1">red</div>
        <div class="item item--2">yellow</div>
        <div class="item item--3">blue</div>
        <div class="item item--4">green</div>
        <div class="item item--5">black</div>
        <div class="item item--6">violet</div>
        <div class="item item--7">gold</div>
        <div class="item item--8">aqua
        </div>
    </div>

  -->
<!--

    <div class="grid">
      <div class="items item--1"></div>
      <div class="items item--2"></div>
      <div class="items item--3"></div>
      <div class="items item--4"></div>
      <div class="items item--5"></div>
      <div class="items item--6"></div>
      <div class="items item--7"></div>
      <div class="items item--8"></div>
  </div>

-->

<!--
.container {
  width: 700px;
  height: 500px;
  margin: 80px;
  background-color: #555;

  display: grid;

  /* ====================MIN-CONTENT AND MAX-CONTENT=================== */
  /* intire content text are wraped and tekes the mininum-space if I use min-content*/

  /* when I use max-content text are not wrap and take full of space intire content */
  /*grid-template-columns: min-content 1fr 1fr max-content;*/
  /*grid-template-rows: repeat(2, min-content);*/

  /* in this situation text are overflow out of the content  */
  /*grid-template-rows: repeat(2, 100px);*/

  /* =================MINMAX FUNCTION========================= */
  /* text overflow fixing with minmax function */
  grid-template-rows: repeat(2, minmax(100px, min-content));
  grid-template-columns: minmax(150px, 2fr) repeat(3, 1fr);
}
.items {
  padding: 40px;
}

.item--1 {
  background-color: red;
}
.item--2 {
  background-color: yellow;
}
.item--3 {
  background-color: blue;
}
.item--4 {
  background-color: green;
}
.item--5 {
  background-color: black;
}
.item--6 {
  background-color: violet;
}
.item--7 {
  background-color: gold;
}
.item--8 {
  background-color: aqua;
}

/*.grid {
  display: grid;
  grid-template-columns: minmax(200px, 1fr) 1fr 1fr;
  grid-template-rows: repeat(2, 100px);
  grid-auto-rows: 300px;
}*/

.grid {
  background-color: chocolate;
  display: grid;
  grid-template-rows: repeat(2, minmax(150px, min-content));
  grid-template-columns: repeat(auto-fill, 100px);
  grid-template-columns: repeat(auto-fit, 100px);
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
  grid-template-columns: repeat(auto-fit, minmax(max-content, 1fr));
  grid-auto-rows: 150px;
}

-->
