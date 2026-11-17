#include <Arduino.h>

const int ledPin_red = 16;
const int ledPin_blue = 17;  
const int ledPin_green = 18;    
const int buttonPin = 15;  

bool flag = false;
bool isBlinking = false;           
int lastButtonState = HIGH;      
unsigned long previousMillis = 0; 
unsigned long currentMillis = 0;       

void setup() {
  pinMode(ledPin_red, OUTPUT);
  pinMode(ledPin_blue, OUTPUT);
  pinMode(ledPin_green, OUTPUT);
  pinMode(buttonPin, INPUT_PULLUP);
  Serial.begin(115200); 
}

boolean curr_Millis(int c) {
  currentMillis = millis();
  if (currentMillis - previousMillis >= c) {
      return true;
  } 
  else {
      return false;
}}

void loop() {
  int currentButtonState = digitalRead(buttonPin);
  if (lastButtonState == HIGH && currentButtonState == LOW) {
    isBlinking = !isBlinking; 
    delay(50);                
  }
  lastButtonState = currentButtonState;
  flag=false;
  if (isBlinking) {
    if (curr_Millis(1500)) {
      digitalWrite(ledPin_green, HIGH);
      digitalWrite(ledPin_red, HIGH);
      flag = true;
    }
    else if (curr_Millis(1250)) {
      digitalWrite(ledPin_green, HIGH);
      digitalWrite(ledPin_blue, LOW);
    }
    else if (curr_Millis(1000)) {
      digitalWrite(ledPin_blue, HIGH);
      digitalWrite(ledPin_green, HIGH);
    }
    else if (curr_Millis(750)) {
      digitalWrite(ledPin_blue, HIGH);
      digitalWrite(ledPin_red, LOW);
    }
    else if (curr_Millis(500)) {
      digitalWrite(ledPin_red, HIGH);
      digitalWrite(ledPin_blue, HIGH);
    }
    else if (curr_Millis(250)) {
      digitalWrite(ledPin_red, HIGH);
      digitalWrite(ledPin_green, LOW);
    }
    if(flag){
     previousMillis = millis();}
  } 
  else {
    digitalWrite(ledPin_red, LOW); 
    digitalWrite(ledPin_green, LOW);
    digitalWrite(ledPin_blue, LOW);
  }
}
