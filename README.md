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
*******************************************************************************************************************************************************************
#HUMIDITY AND TEMPERATURE SENSOR<br>
 #include <Adafruit_Sensor.h><br>
#include <DHT.h>;<br>
#define DHTPIN D7 // what pin we're connected to<br>
#define DHTTYPE DHT11 // DHT 22 (AM2302)<br>
DHT dht(DHTPIN, DHTTYPE); //// Initialize DHT sensor for normal 16mhz Arduino<br>
//Variables<br>
int chk; float hum; //Stores humidity value<br>
float temp; //Stores temperature value<br>
void setup()<br>
{<br>
Serial.begin(9600);<br>
dht.begin();<br>
}<br>
void loop()<br>
{<br>
delay(2000);<br>
//Read data and store it to variables hum and temp<br>
hum = dht.readHumidity();<br>
temp= dht.readTemperature();<br>
//Print temp and humidity values to serial monitor<br>
Serial.print("Humidity: ");<br>
Serial.print(hum);<br>
Serial.print(" %, Temp: ");<br>
Serial.print(temp);<br>
Serial.println(" Celsius");<br>
delay(1000); //Delay 2 sec.<br>
}<br>
**********************************************************************************************************************************************************************
//IR sensor<br>
int ir=D6;<br>
int led=D3;<br>
void setup() {<br>
  // put your setup code here, to run once:<br>
  pinMode(ir,INPUT);<br>
    pinMode(led,OUTPUT);<br>
    Serial.begin(115200);<br>
    
}<br>

void loop() {<br>
  // put your main code here, to run repeatedly:<br>
  int irvalue=digitalRead(ir);<br>
  if(irvalue==LOW)<br>
  {<br>
    Serial.println("LOW");<br>
    digitalWrite(led,HIGH);<br>
  }<br>
  else<br>
  {<br>
    Serial.println("HIGH");<br>
    digitalWrite(led,LOW);<br>
  }<br>
delay(100);<br>
}<br><br>
