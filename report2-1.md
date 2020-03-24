### 컴퓨터공학과 20171138 허민재
```
void setup(){
  size(800,500);
  textSize(125);
}
int i, dir=1, sp=1;
void draw(){
  fill(255);
  background(0,0,0);
  text("Graphics", i,200);
  if(i>250) dir=-1;
  if(i<0) dir=1;
  i=i+dir*sp;
}
void keyPressed(){
  sp = key-'0';
}
```
### 코로나19를 이겨내서 4월에 좋은 모습으로 수업을 들을수 있으면 좋겠습니다. 파이팅!!
