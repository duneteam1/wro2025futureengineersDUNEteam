#include <Servo.h> // подключаем библиотеку для работы с сервоприводом"
#include "HUSKYLENS.h"
#include "SoftwareSerial.h"

//husky
HUSKYLENS huskylens;
SoftwareSerial mySerial(10, 11); // RX, TX
//HUSKYLENS green line >> Pin 10; blue line >> Pin 11
void printResult(HUSKYLENSResult result);

//servo
Servo servo1; // объявляем переменную servo типа "servo1"
// dc motor
#define m1 3
#define m2 9
// sensors
//right
#define trigPin1 A3
#define echoPin1 A4
// left
#define trigPin2 A2
#define echoPin2 A1
//variables for sens
float Rdis;
float Ldis;
//variables for center
float total;
float angle;
float kof;
//variables for park
short count = 0;
int timer;
int timer1;
//flags for park
boolean flag = false;
boolean flag1 = false;

//husky
byte id;
short height;
HUSKYLENSResult result;

void setup() {
  Serial.begin(115200);
  servo1.attach(6);
  // innicialize pins mode for dc
  pinMode(m1, OUTPUT);
  pinMode(m2, OUTPUT);
  // innicialize pins mode for sensors
  pinMode(trigPin1, OUTPUT); // Sets the trigPin1 as an Output
  pinMode(echoPin1, INPUT); // Sets the echoPin1 as an Input
  pinMode(trigPin2, OUTPUT); // Sets the trigPin2 as an Output
  pinMode(echoPin2, INPUT); // Sets the echoPin2 as an Input
  //husky
  mySerial.begin(9600);
  while (!huskylens.begin(mySerial))// cheking husky
  {
    Serial.println(F("Begin failed!"));
    Serial.println(F("1.Please recheck the \"Protocol Type\" in HUSKYLENS (General Settings>>Protocol Type>>Serial 9600)"));
    Serial.println(F("2.Please recheck the connection."));
    delay(100);
  }
}

void loop() {
  //taking timer
  timer = millis();
  //guve voltage for pins
  analogWrite(m1, 180);
  analogWrite(m2, 0);
  // put your main code here, to run repeatedly:
  Rdis = dis(trigPin1, echoPin1);
  Ldis = dis(trigPin2, echoPin2) - 8;
  center();
  //  husky();
  rotate();
  park();
  servo1.write(angle);
  Serial.print("    Rdis = ");
  Serial.print(Rdis);
  Serial.print("    Ldis1 = ");
  Serial.print(Ldis);
  Serial.print("  anggle = ");
  Serial.println(String() + angle + F("  total = ") + total +  F("   kof = ") + kof + F("     id = ") + id + F("     height = ") + height + F("   co  unt =  ") + count + F("    timer = ") + timer + F("    timer1 = ") + timer1);
}


float dis(byte trigPin, byte echoPin) {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

  // Посылаем импульс на триггерный пин
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  // Считываем длительность импульса на эхо-пине
  long duration = pulseIn(echoPin, HIGH);

  // Переводим длительность в расстояние
  float distance = duration * 0.034 / 2;

  // Выводим расстояние в серийный монитор
  return (distance);
}

void center() {
  total = Rdis + Ldis;
  kof = Rdis / total;
  angle = 180 * kof;
  if (angle <= 35) {
    angle = 35;
  } else if (angle >= 135) {
    angle = 135;
  }



}
void rotate() {
  if (id == 1 && height > 100) {
    angle = 135;
  } else if (id == 2 && height > 100) {
    angle = 35;
  }
    if (angle <= 35) {
    angle = 35;
  } else if (angle >= 135) {
    angle = 135;
  }
}
void park() {
  if (!flag1) {
    timer1 = millis();
    flag1 = true;
  }
  if (Rdis > 1000 || Ldis > 1000 && flag == false) {
    count++;
    flag = true;
  } else if (timer - timer1 >= 1500) {
    flag = false;
    flag1 = false;
  }
  if (count >= 11 && timer - timer1 >= 2500) {
    digitalWrite(m1, 0);
    digitalWrite(m2, 0);
  }
   if (angle <= 35) {
    angle = 35;
  } else if (angle >= 135) {
    angle = 135;
  }
}


void husky() {
  if (!huskylens.request()) id = 0;
  else if (!huskylens.isLearned()) id = 0;
  else if (!huskylens.available()) id = 0;
  else
  {
    Serial.println(F("###########"));
    result = huskylens.read();
    id = result.ID;
    height = result.height; 
  }
}
