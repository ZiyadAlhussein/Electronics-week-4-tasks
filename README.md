# Electronics-week-4-tasks

**Task 1: Building an arduino circuit for Analog input (Photoresistor sensor)**  
(https://www.tinkercad.com/things/f8GjqwAGnAG)

**Building the Arduino circuit with analog input:**

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

**Task 2: Building an arduino circuit for Digital input (Push button)**  
(https://www.tinkercad.com/things/lNZnM33t4k2)

**Building the Arduino circuit with digital input**

  1) Click on create new Circuit.
  2) From the search tool, get:
  
    i. Breadboard 
    
    ii. Arduino uno r3
    
    iii. resistor 1k ohm
    
    iv. resistors 10k ohm
    
    v. push button
    
    vi. LED
  
  3) Connect the circuit as shown below:
  
![Copy of Blink and Read Digital Signal](https://user-images.githubusercontent.com/108147030/187032266-8a66dfff-ce11-43f5-9226-4c803072b222.png)
 

  4) use the following code to simulate the Analog input arduino circuit:
 
```ruby
// C++ code
//
/*
  This program blinks pin 13 of the Arduino (the
  built-in LED)
*/

int buttonPin = 12;
int ledPin = 13;
int val = 0;

void setup()
{
  pinMode(ledPin, OUTPUT);
  pinMode(buttonPin, INPUT);
}

void loop()
{
  val = digitalRead(buttonPin);
  
  if(val == 1) // daca butonul este apasat
  	digitalWrite(ledPin, HIGH); // alimentam in continuare LED-u;
  else // altfel, daca butonul nu este apasat
  	digitalWrite(ledPin, LOW); // oprim alimentarea LED-ului
}
  ```
  
5) Click on start Simulation if you change the light indicator on the Photoresistor, the osoloscope will show a signal for the analog input.

![output](https://user-images.githubusercontent.com/108147030/187032354-dc2f3ca7-77a1-46e7-91e6-31a38a4b7870.png)
