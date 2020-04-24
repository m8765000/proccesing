# proccesing
##컴퓨터공학과 20171138 허민재

#1장 펜만들기

```
void setup(){
  size(500,500);
  background(255);
  stroke(0,0,255);
  strokeWeight(16);
}
float f;
void draw(){
  if(mousePressed)
  line(pmouseX,pmouseY,mouseX,mouseY);
}
```
#2장 위에서 아래로 왔다갔다하는 간판
글씨체를 "바탕체"로 만들어준다.
텍스트가 위에서 아래로 갔다가 끝에가면 다시 위로 올라간다
숫자키를 누르면 속도가 조절 된다.
```
PFont f;
void setup(){
  size(900,500);
  f = createFont("바탕체", 77);
  textFont(f);
}
int i, dir=1, sp=1;
void draw(){
  background(0);
  text("안동대 컴공 사랑합니다",30,i);
  if(i>height) i=0;
  i=i+dir*sp;
  if (keyPressed) sp = key-'0';
}
```
#3장 프로세싱 Examples선택 random
랜덤하게 원과 색상이 찍히는 코드
x와y좌표를 선언하고 색상r,g,b를 선언한다
랜덤하게 x,y좌표에 원을 생성한다.
색상은 255까지 랜덤하게 생성하고 흐리게 한다.
```
int x,y;
int r,g,b;

void setup(){
  size(700,700);
  background(255);
}
void draw(){
  x=int(random(700));
  y=int(random(700));
  r=int(random(255));
  g=int(random(255));
  b=int(random(255));
  
  fill(r,g,b,50);
  noStroke();
  ellipse(x,y,70,70);
}
  
```
#4장 나의 도형 만들기 라이언
```
void setup() {
  size(1000,1000);
  background(255);
  noStroke();
 

  fill(248,155,0);
  ellipse(500,250,350,350);
 

  fill(0);

  ellipse(410,187,100,15);

 

  fill(0);
  ellipse(420,225,20,20);
 

  fill(0);
  ellipse(580,187,100,15);


  fill(0);
  ellipse(570,225,20,20);


  fill(248,155,0);
  ellipse(400,90,70,70);

 
  fill(248,155,0);
  ellipse(600,90,70,70);
 
  fill(255);
  noStroke();
  ellipse(480,278,60,60);
 

  fill(255);
  ellipse(520,278,60,60);

  fill(0);
  ellipse(500,260,30,30);
 

  fill(248,155,0);
  rect(410,400,180,190);

 
  fill(245,245,220);
  ellipse(500,470,100,100);

  fill(248,155,0);
  ellipse(435,600,50,180);
 

  fill(248,155,0);
  ellipse(565,600,50,180);

 
  stroke(248,155,0);
  strokeWeight(40);
  line(588,400,641,550);
 
  stroke(248,155,0);
  strokeWeight(40);
  line(300,450,440,400);
}
```
#5장 글씨 레이어 PGraphics활용
1을 누르면 회색 2를 누르면 진한 회색이 나온다.
다른색의 선들이 곂쳐 쓸 수 있다.
```
PGraphics pg1;
PGraphics pg2;

int Layer =1;

void setup(){
  size(800,800);
  pg1 = createGraphics(width,height);
  pg2 = createGraphics(width,height);
}
void draw(){
  background(255);
  
 if(Layer ==1){
    drawLayer(pg1,color(200));
} else if (Layer ==2){
   drawLayer(pg2, color (100,200));
}
  image(pg1,0,0);
  image(pg2,0,0);
}
void keyPressed(){
  if(key == '1'){
    Layer = 1;
} else if (key == '2'){
  Layer = 2;
}
}
void drawLayer(PGraphics pg, color col){
  pg.beginDraw();
  pg.fill(col);
  pg.noStroke();
  if (mousePressed) pg.ellipse(mouseX, mouseY, 40, 40);
  pg.endDraw();
}
```
