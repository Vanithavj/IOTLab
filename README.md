# IOTLab


1.Blinking LED                             ==>https://wokwi.com/projects/333714013359702612<br>
2.Traffic signal                           ==>https://wokwi.com/projects/333798899249578578<br>
3.RGBled                                   ==>https://wokwi.com/projects/333802704403956307<br>
4.LCD                                      ==>https://wokwi.com/projects/322062421191557714<br>
5.servomotor                               ==>https://wokwi.com/projects/334978204470084179<br>
6.servomotor using for loop                ==>https://wokwi.com/projects/334981399090037332<br>
7.servometer with potentiometer            ==>https://wokwi.com/projects/334983168624951890<br>
8.Buzzer                                   ==>https://wokwi.com/projects/335065985356661332<br>
9.Buzzer with pushbutton                   ==>https://wokwi.com/projects/335068472263311956<br>
10.Ultrasonic sensor                       ==>https://wokwi.com/projects/335072171637342802<br>
11.Servomotor with buzzer                  ==>https://wokwi.com/projects/335635909331386963<br>
12.Ultrasonic sensor with buzzer           ==>https://wokwi.com/projects/335073264458007124<br>
13.Ultrasonic sensor with buzzer and LED   ==>https://wokwi.com/projects/335612428882543188<br>
14.Multiple Ultrasonic sensor with buzzer  ==>https://wokwi.com/projects/335699909427593812<br> 
15.Potentiometer with led                  ==>https://wokwi.com/projects/335701631590990420<br>
16.servomotor with pushbutton              ==>https://wokwi.com/projects/335703833682379347<br>
17.lablist1                                ==>https://wokwi.com/projects/338148483867345490<br>
18.lablist2                                ==>https://wokwi.com/projects/337602684471214674<br>
19.lablist1  with ESP32                    ==>https://wokwi.com/projects/338225981441442386<br>


#define BLYNK_PRINT Serial
const int trigPin = D6;
const int echoPin = D5;
// defines variables
long duration;
int distance;
float inch;
void setup() {
  pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output
  pinMode(echoPin, INPUT); // Sets the echoPin as an Input
  Serial.begin(9600); // Starts the serial communication
}
void loop() {
  // Clears the trigPin
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  // Sets the trigPin on HIGH state for 10 micro seconds
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  // Reads the echoPin, returns the sound wave travel time in microseconds
  duration = pulseIn(echoPin, HIGH);
  // Calculating the distance
  distance = duration * 0.034 / 2;
  // Prints the distance on the Serial Monitor
  inch = distance / 2.54;
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm ");
  Serial.print("Inch    : ");
  Serial.print(inch);
  Serial.println(" inches ");
  delay(500);
}
