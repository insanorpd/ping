# ping

let xBall = 370;
let yBall = 250;
let dBall = 20;
let ray = dBall / 2;
let speedxBall = 3;
let speedyBall = 3;
let xleftrect = 5;
let yleftrect = 5;
let wleftrect = 10;
let hleftrect = 70;
let xrightrect = 785;
let yrightrect = 5;
let wrightrect = 10;
let hrightrect = 70;

function setup() {
  createCanvas(800, 500);
}
function draw() {
  background(0);
  showBall();
  moveBall();
  colisionBall();  
  leftRect();
  rightRect();
  moveleftRect();
  moverightRect();
  leftrectballcolision();
 // rightrectballcolision();
}
function showBall(){
  circle(xBall, yBall, dBall)  
}
function moveBall(){
  xBall += speedxBall;
  yBall += speedyBall;  
}
function colisionBall(){
  if (xBall + ray > width || xBall - ray < 0){
    speedxBall*= -1;
  }
  if (yBall + ray > height || yBall - ray < 0){
    speedyBall*= -1;
  }
}
function leftRect(){
  rect(xleftrect, yleftrect, wleftrect, hleftrect)
}
function rightRect(){
  rect(xrightrect, yrightrect, wrightrect, hrightrect)
}
function moveleftRect(){
  if (keyIsDown(UP_ARROW)){
    yleftrect -= 10;
  }
   if (keyIsDown(DOWN_ARROW)) {
        yleftrect += 10;
   }
}
function moverightRect(){
    if (keyIsDown(87)){
    yrightrect -= 10;
  }
   if (keyIsDown(83)) {
        yrightrect += 10;
   }
}
function leftrectballcolision(){
  if (xBall - ray < xleftrect + wleftrect && yBall - ray < yleftrect + wleftrect && yBall + ray > yleftrect){
    speedyBall*= -1;
  }
}
function rightrectballcolision(){
  if (xBall - ray < xrightrect + wrightrect && yBall - ray < yrightrect + wrightrect && yBall + ray > yrightrect){
    speedyBall*= -1;
  }
}
