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
18.lablist3                                ==>https://wokwi.com/projects/337602684471214674<br>
19.lablist1  with ESP32                    ==>https://wokwi.com/projects/338225981441442386<br>


************HARDWARE*************<br>
#Ultrasonic sensor<br>

#define BLYNK_PRINT Serial<br>
const int trigPin = D6;<br>
const int echoPin = D5;<br>
// defines variables<br>
long duration;<br>
int distance;<br>
float inch;<br>
void setup() {<br>
  pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output<br>
  pinMode(echoPin, INPUT); // Sets the echoPin as an Input<br>
  Serial.begin(9600); // Starts the serial communication<br>
}<br>
void loop() {<br>
  // Clears the trigPin<br>
  digitalWrite(trigPin, LOW);<br>
  delayMicroseconds(2);<br>
  // Sets the trigPin on HIGH state for 10 micro seconds<br>
  digitalWrite(trigPin, HIGH);<br>
  delayMicroseconds(10);<br>
  digitalWrite(trigPin, LOW);<br>
  // Reads the echoPin, returns the sound wave travel time in microseconds<br>
  duration = pulseIn(echoPin, HIGH);<br>
  // Calculating the distance<br>
  distance = duration * 0.034 / 2;<br>
  // Prints the distance on the Serial Monitor<br>
  inch = distance / 2.54;<br>
  Serial.print("Distance: ");<br>
  Serial.print(distance);<br>
  Serial.println(" cm ");<br>
  Serial.print("Inch    : ");<br>
  Serial.print(inch);<br>
  Serial.println(" inches ");<br>
  delay(500);<br>
}<br><br><br>
