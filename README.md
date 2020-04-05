# c-19-Project

//creating hero,villans and space

var bullet = createSprite();

var space = createSprite(200,0,400,400);
space.setAnimation("planet");
space.velocityY = 4;

var hero = createSprite(200,365,10,10);
hero.setAnimation("hero");
hero.scale = "0.5";

var villan1 = createSprite(randomNumber(50,234),randomNumber(50,238),10,10);
villan1.setAnimation("v1");
villan1.scale = "0.7";
villan1.velocityY = 3;

var villan2 = createSprite(randomNumber(50,332),randomNumber(50,215),10,10);
villan2.setAnimation("v2");
villan2.scale = "0.7";
villan2.velocityY = 2.6;

var villan3 = createSprite(randomNumber(50,150),randomNumber(50,323),10,10);
villan3.setAnimation("v3");
villan3.scale = "0.7";
villan3.velocityY = 3.4;

var villan4 = createSprite(randomNumber(50,230),randomNumber(50,234),10,10);
villan4.setAnimation("v4");
villan4.scale = "0.7";
villan4.velocityY = 4;

var vilan1 = createSprite(randomNumber(50,350),randomNumber(50,175),10,10);
vilan1.setAnimation("v1");
vilan1.scale = "0.7";
vilan1.velocityY = 3;

var vilan2 = createSprite(randomNumber(50,332),randomNumber(50,215),10,10);
vilan2.setAnimation("v2");
vilan2.scale = "0.7";
vilan2.velocityY = 2.6;

var vilan3 = createSprite(randomNumber(50,150),randomNumber(50,323),10,10);
vilan3.setAnimation("v3");
vilan3.scale = "0.7";
vilan3.velocityY = 3.4;

var vilan4 = createSprite(randomNumber(50,230),randomNumber(50,234),10,10);
vilan4.setAnimation("v4");
vilan4.scale = "0.7";
vilan4.velocityY = 4;

var villan = createSprite(200,100,10,40);

var BulletGroup = createGroup();

var count = 0;

//moving background

space.y = space.height/15;
textSize(20);

text.shapeColor ="white";


function draw() {
  
  console.log(World.frameCount);
  
 //moving hero and space
 hero.x = World.mouseX;
 
 if(space.y > 400){
   space.y = space.height/15;
 }
 
 
 text("score:" + count,320,50);
  
 //destroying villans
 
 if(hero.isTouching(vilan1)||BulletGroup.isTouching(vilan1)){
    vilan1.destroy();
    count = count + 2;
 }
 
 if(hero.isTouching(vilan2)||BulletGroup.isTouching(vilan2)){
    vilan2.destroy();
    count = count + 2;
 }
 
 if(hero.isTouching(vilan3)||BulletGroup.isTouching(vilan3)){
   vilan3.destroy();
   count = count +  2;
 }
 
 if(hero.isTouching(vilan4)||BulletGroup.isTouching(vilan4)){
    vilan4.destroy();
    count = count + 2;
    
 }
 
 if(hero.isTouching(villan)||BulletGroup.isTouching(villan)){
    villan.destroy();
    count = count + 2;
 }
 
 if(hero.isTouching(villan1)||BulletGroup.isTouching(villan1)){
     villan1.destroy();
     count = count + 2;
 }
 
 if(hero.isTouching(villan2)||BulletGroup.isTouching(villan2)){
     villan2.destroy();
     count = count + 2;
 }
 
 if(hero.isTouching(villan3)||BulletGroup.isTouching(villan3)){
     villan3.destroy();
     count = count + 2;
 }
 
 if(hero.isTouching(villan4)||BulletGroup.isTouching(villan4)){
     villan4.destroy();
     count = count + 2;
 }
 
 if(World.frameCount % 30 === 0) {
    villan.velocityY = 4.8;
    var rand = randomNumber(1,4);
    villan.setAnimation("v" + rand);
    villan.scale = 0.7;

 }
 
 //creating bullets
 
 if(keyDown("space")){
    bullet = createSprite(World.mouseX,350,5,10);
    bullet.velocityY = -3;
    bullet.shapeColor = "yellow";
    BulletGroup.add(bullet);
 
 }
 
 if(villan1.y > 400) {
   count = count - 1;
 }
 
 if(villan2.y > 400) {
   count = count - 1;
 }
 
  if(villan3.y > 400) {
   count = count - 1;
 }
 
 if(villan4.y > 400) {
   count = count - 1;
 } 
 
 if(vilan1.y > 400) {
   count = count - 1;
 }
 
  if(vilan2.y > 400) {
   count = count - 1;
 }
 
 if(vilan3.y > 400) {
   count = count - 1;
 } 
 
 if(villan4.y > 400) {
   count = count - 1;
 }

 drawSprites(); 

 }
 
 
