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

20.Liquid crystal                          ==>https://wokwi.com/projects/340855309309313619


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
******************************************************************************************************************************************************************

int red = D1;<br> 
int green = D6;<br> 
int blue = D7; //GROUND IS CONNECTED TO 3V <br>

void setup() <br>
{ <br>
pinMode(red, OUTPUT); <br>
pinMode(green, OUTPUT);<br>
pinMode(blue, OUTPUT);<br>

}<br>

void loop()<br>
{ <br>
displayColor(0b100); //RED <br>
delay(1000);<br>
displayColor(0b010);<br>
//GREEN delay(1000); <br>
displayColor(0b001); //BLUE<br>
delay(1000);<br>
displayColor(0b101); //MAGENTA <br>
delay(1000); <br>displayColor(0b011); //CYAN <br>
delay(1000); <br>displayColor(0b110); //YELLOW<br>
delay(1000);<br> displayColor(0b111); //WHITE<br>
delay(1000);<br> 
}<br>

void displayColor(byte color) <br>
{ <br>
digitalWrite(red, !bitRead(color, 2));<br>
digitalWrite(green, !bitRead(color, 1)); <br>
digitalWrite(blue, !bitRead(color, 0));<br>
}<br>
******************************************************************************************************************************************************************
IR_LED <br>
int ir=D7;<br>
int led=D5; <br>
void setup() <br>
{ // put your setup code here, to run once: <br>
pinMode(ir,INPUT); <br>
pinMode(led,OUTPUT); <br>
Serial.begin(9600);<br>
<br>
}

void loop() <br>
{ // put your main code here, to run repeatedly: <br>
int irvalue=digitalRead(ir); <br>
if(irvalue==LOW) <br>
{ <br>
Serial.println("LOW");<br>
digitalWrite(led,HIGH); <br>
} <br>
else <br>
{ Serial.println("HIGH"); <br>
digitalWrite(led,LOW);<br>
} <br>
delay(100);<br>
}<br>

*******************************************************************************************************************************************************************
LDR <br>
const int ldrPin=A0;<br>
void setup()<br>
{ <br>
Serial.begin(9600);<br>
pinMode(ldrPin,INPUT); <br>
} <br>
void loop() <br>
{ 
int rawData = analogRead(ldrPin);<br>
Serial.println(rawData); <br>
delay(1000);<br>
}<br>
<br><br><br>
**************************************************************************************************************************************************************************


**flood monitering system**<br>
<br><br>
#include "ThingSpeak.h"<br>
#include <ESP8266WiFi.h><br>
const int trigPin1 = D6;<br>
const int echoPin1 = D7;<br>
#define redled D2<br>
#define grnled D4<br>
#define BUZZER D1 //buzzer pin <br>
unsigned long ch_no = 1053193;//Replace with Thingspeak Channel number<br>
const char * write_api = "8JQGAAUOIA12K2MD";//Replace with Thingspeak write API<br>
char auth[] = "mwa0000027193738";<br>
char ssid[] = "OPPO A3s";<br>
char pass[] = "vanithavvj";<br>
unsigned long startMillis;<br>
unsigned long currentMillis;<br>
const unsigned long period = 10000;<br>
WiFiClient client;<br>
long duration1;<br>
int distance1;<br>
void setup() {<br>
pinMode(trigPin1, OUTPUT);<br>
pinMode(echoPin1, INPUT);<br>
pinMode(redled, OUTPUT);<br>
pinMode(grnled, OUTPUT);<br>
digitalWrite(redled, LOW);<br>
digitalWrite(grnled, LOW);<br>
Serial.begin(115200);<br>
WiFi.begin(ssid, pass);<br>
while (WiFi.status() != WL_CONNECTED)<br>
{<br>
delay(1000);<br>
Serial.print(".");<br>
Serial.println("WiFi co<br>nnected");<br>
Serial.println(WiFi.localIP());<br>
ThingSpeak.begin(client);<br>
startMillis = millis(); //initial start time<br>
}<br>
void loop()<br>
{<br>
digitalWrite(trigPin1, LOW);<br>
delayMicroseconds(2);<br>
digitalWrite(trigPin1, HIGH);<br>
delayMicroseconds(10);<br>
digitalWrite(trigPin1, LOW);<br>
duration1 = pulseIn(echoPin1, HIGH);<br>
distance1 = duration1 * 0.034 / 2;<br>
Serial.println(distance1);<br>
if (distance1 <= 400)<br>
{<br>
digitalWrite(D2, HIGH);<br>
tone(BUZZER, 300);<br>
digitalWrite(D4, LOW);<br>
delay(1500);<br>
noTone(BUZZER);<br>
}<br>
else<br>
{<br>
digitalWrite(D4, HIGH);<br>
digitalWrite(D2, LOW);<br>
}<br>
currentMillis = millis();<br>
if (currentMillis - startMillis >= period)<br>
{<br>
ThingSpeak.setField(1, distance1);<br>
ThingSpeak.writeFields(ch_no, write_api);<br>
startMillis = currentMillis;<br>
}<br>
}<br>
**************************************************************************************************************************************************************
**LED series**<br>

int pinsCount=5; // declaring the integer variable pinsCount<br>
int pins[] = {D1,D2,D3,D4,D5,}; // declaring the array pins[]<br>

void setup() {<br>
for (int i=0; i<pinsCount; i=i+1){ // counting the variable i from 0 to 9<br>
pinMode(pins[i], OUTPUT); // initialising the pin at index i of the array of pins as OUTPUT<br>
}<br>
}<br>
void loop() {<br>
for (int i=0; i<pinsCount; i=i+1){ // chasing right<br>
digitalWrite(pins[i], HIGH); // switching the LED at index i on<br>
delay(100); // stopping the program for 100 milliseconds<br>
digitalWrite(pins[i], LOW); // switching the LED at index i off<br>
}<br>
for (int i=pinsCount-1; i>0; i=i-1){ // chasing left (except the outer leds)<br>
digitalWrite(pins[i], HIGH); // switching the LED at index i on<br>
delay(100); // stopping the program for 100 milliseconds<br>
digitalWrite(pins[i], LOW); // switching the LED at index i off<br>

}<br>
}<br>
