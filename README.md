# Electronics-week-4-tasks

**Task 1: Building an arduino circuit for Analog input (Photoresistor sensor)**  
(https://www.tinkercad.com/things/e5iy0LLD7KT)

**1. Make an account in TinkerCAD for Arduino simulations: https://www.tinkercad.com/**

  1) Click Sign Up on the Tinkercad homepage.
  2) Choose your country from the drop-down list.
  3) Enter your birthday. 
  4) Click the Next button.
  5) Add your email address and a password, accept the Tinkercad terms of service, and click Create Account.
  
  
**2. Building the Servo Motor:**

  1) Click on create new Circuit.
  2) From the search tool, get:
  
    i. Breadboard 
    
    ii. Arduino uno r3
    
    iii. Oscilloscope
    
    iv. resistor 220 ohm
    
    v. two resistors 1k ohm
    
    vi. Photoresistor
    
    vii. LED
  
  3) Connect the circuit as shown below:
  
![Analog circuit](https://user-images.githubusercontent.com/108147030/187031652-1c321a09-7078-407c-a990-4fa9bc39f544.png)  

  4) use the following code to simulate the Analog input arduino circuit:
 
```ruby
// Initialisation 
const int analogInPin = A0;     
const int analogOutPin = 9;     
const int analogBuzPin = 8;     

int sensorValue = 0;   
int outputValue = 0;  
int buzValue = 0;      

void setup() {
  
  Serial.begin(9600);
  
  
  pinMode(analogOutPin, OUTPUT);      
  
  pinMode(analogInPin, INPUT); 

  pinMode(analogBuzPin,OUTPUT);
}

void loop() {

  sensorValue = analogRead(analogInPin);            
  
  outputValue = map(sensorValue, 0, 1023, 0, 255);  
  
  analogWrite(analogOutPin, outputValue);           
  
  buzValue = map(sensorValue, 0, 1023, 50, 30000);     
  
  tone(analogBuzPin, buzValue);
  
 
  Serial.print("sensor = " );                       
  Serial.print(sensorValue);      
  Serial.print("\t output = ");      
  Serial.print(outputValue);
  Serial.print("\t frequence = ");
  Serial.println(buzValue);
}       
  ```
  
5) Click on start Simulation if you change the light indicator on the Photoresistor, the osoloscope will show a signal for the analog input.

![image](https://user-images.githubusercontent.com/108147030/187031789-8e748319-642b-4725-ac2d-16f347b169aa.png)
