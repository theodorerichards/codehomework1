//square slowly draws two parallel lines across the screen horizonally

int clickableX;
int clickableY;
int clickableSize;

boolean clickablePressed;

float squareX;
float squareY;

float squareSize;

float speedX;
float speedY;

//square slowly draws two parallel lines across the screen vertically

float square2X;
float square2Y;

float square2Size;

float speed2X;
float speed2Y;

void setup() {
  size(500, 500);
  background(255);
  noStroke();
  rectMode(CENTER);
  textMode(CENTER);
  
  clickableX = width/2;
  clickableY = height/2;
  clickableSize = 400;
  
  squareX = (25);
  squareY = (25);
  
  speedX = (.5);
  speedY = (450);
  
  squareSize = 50;
  
  
  square2X = (25);
  square2Y = (25);
  
  speed2X = (450);
  speed2Y = (.5);
  
  square2Size = 50;
}

void draw() {
  
  

  float r = map(squareX, 0, height, 0, 255);
  float g = map(squareX, 0, height, 0, 255);
  
  fill(r, g, 255);
  rect(squareX, squareY, squareSize, squareSize);
  
 
  
  squareX += speedX;
  squareY += speedY;
  
 
  if (squareX > width -squareSize/2 || squareX < squareSize/2) {
    squareX -= speedX;
    speedX = -speedX;
  }
  
  if (squareY > height - squareSize/2 || squareY < squareSize/2) {
    squareY -= speedY;
    speedY = -speedY;
  }
  
  float r2 = map(square2X, 0, width, 255, 0);
  float g2 = map(square2Y, 0, height, 255, 0);
  
   fill(r2, g2, 200);
  rect(square2X, square2Y, square2Size, square2Size);
  
  square2X += speed2X;
  square2Y += speed2Y;
  
  
  if (square2X > width - square2Size/2 || square2X < square2Size/2) {
    square2X -= speed2X;
    speed2X = -speed2X;
  }
  
  if (square2Y > height - square2Size/2 || square2Y < square2Size/2) {
    square2Y -= speed2Y;
    speed2Y = -speed2Y;
  }
  
  //
  
  if (clickablePressed) {
    println("true");
    fill(r2, g2, 100);
    rect(square2X, square2Y, square2Size, square2Size);
    square2X += speed2X;
    square2Y += speed2Y;
    fill(r, g, 170);
    rect(squareX, squareY, squareSize, squareSize);
    squareX += speedX;
    squareY += speedY;
  } else {
    println("false");
    
  }
  
  
 
  fill(#F09D9D);
  rect(clickableX, clickableY, clickableSize, clickableSize);
  
  fill(0);
  text("CLICK HERE",  220, 240);
  text("CLICK HERE",  120, 340);
  text("CLICK HERE",  330, 274);
  text("CLICK HERE",  290, 368);
  text("CLICK HERE",  365, 134);
  text("CLICK HERE",  298, 139);
  text("CLICK HERE",  356, 219);
  text("CLICK HERE",  138, 139);
  text("CLICK HERE",  62, 232);
  text("CLICK HERE",  145, 167);
  text("CLICK HERE",  319, 333);
  text("CLICK HERE",  122, 265);
  text("CLICK HERE",  67, 73);
  text("CLICK HERE",  330, 82);
  text("CLICK HERE",  91, 294);
  text("CLICK HERE",  54, 425);
  text("CLICK HERE",  354, 435);
  text("CLICK HERE",  234, 405);
}
  


void mousePressed() {
  float button = dist(mouseX, mouseY, clickableX, clickableY);

  if (button < clickableSize/2) {
    clickablePressed = !clickablePressed;
  }
}

