# Controller-One
#include <NewPing.h>
#include <Servo.h>

#define TRIGGER_PIN  12
#define ECHO_PIN     6
#define MAX_DISTANCE 200
 
NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);

Servo myservo; 

int val;  
int pos;  
 
void setup() {
  Serial.begin(115200);
   myservo.attach(9);
}
 
void loop() {
  delay(50);
  int uS = sonar.ping();
  //val = map(uS, 0, 1500, 0, 180);     // scale it to use it with the servo (value between 0 and 180)
  Serial.println(uS);
 /* if (uS<10){
      for (pos = 0; pos <= 180; pos += 1) { // goes from 0 degrees to 180 degrees
    // in steps of 1 degree
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    delay(15);                       // waits 15ms for the servo to reach the position
  }
  for (pos = 180; pos >= 0; pos -= 1) { // goes from 180 degrees to 0 degrees
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    delay(15);                       // waits 15ms for the servo to reach the position
  }
    
    }
  */
  delay(15);
 // myservo.write(val);                  // sets the servo position according to the scaled value
  //delay(15);  
  
}
