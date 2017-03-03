# robotprojekt
Kod till robotprojektet!
#include <Servo.h>

//Pins på shielden
int dirA = 12;
int brkA = 9;
int dirB = 13;
int brkB = 8;

//Full ström till motorn
int full = 255;

//den frekvens i microsekunder då servon står still
int servostop = 1465;

Servo servon;



void setup() {
 
  
pinMode(12, OUTPUT);
pinMode(brkA, OUTPUT);  
pinMode(dirB, OUTPUT);
pinMode(brkB, OUTPUT);
digitalWrite(dirA, LOW);
digitalWrite(brkA, LOW);

digitalWrite(dirB, LOW);
digitalWrite(brkB, LOW);

servon.attach(5);


}
//
void loop() {
  //servon.writeMicroseconds(1465);
 forward();
 delay(500);
 stanna();
delay(500);
//servon.writeMicroseconds(1000);
turnLeft();
delay(1500);
  stanna();

delay(500);
//servon.writeMicroseconds(2200);
 turnRight();
 delay(500);
   stanna();
 delay(500);

}

void forward(){
  digitalWrite(brkA, LOW);
  digitalWrite(brkB, LOW);
  
  digitalWrite(dirA, LOW);
  digitalWrite(dirB, LOW);
  
  analogWrite(3, full);
  analogWrite(11, full);
}
void stanna(){
  digitalWrite(brkA, HIGH);
  digitalWrite(brkB, HIGH);
  digitalWrite(dirA, LOW);
  digitalWrite(dirB, LOW);
}

void turnLeft(){
    digitalWrite(brkA, HIGH);
    digitalWrite(brkB, LOW);
    digitalWrite(dirA, LOW);
  digitalWrite(dirB, LOW);
     analogWrite(11, full);
}

void turnRight(){
  digitalWrite(brkA, LOW);
  digitalWrite(brkB, LOW);
  digitalWrite(dirA, LOW);
  digitalWrite(dirB, HIGH);
  analogWrite(3, full);
  analogWrite(11, full);
}
