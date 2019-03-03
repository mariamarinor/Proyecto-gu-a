#### Materiales
Placa ARDUINO
Protoboard
Resistencias 200ohm
Diodo led
Sensor PIR para ARDUINO 
Cables de timbre.
#### Funcionamiento 
La placa arduino funciona como una batería al ser conectada al computador, dicha energía llega al sensor y luego pasa por el LED 
el cual se enciende cuando percibe un movimiento cerca de el.

#### Diagrama pictórico
![sesquematico1](https://user-images.githubusercontent.com/47117506/52676410-0e686300-2ef8-11e9-8d37-e5c59829e6a6.png)

#### Diagrama esquemático
![untitled sketch_esquematico 3](https://user-images.githubusercontent.com/47117506/52676468-4079c500-2ef8-11e9-897d-a026e86dce58.png)
==================
#### Código
const int trigPin = 3;
const int echoPin = 2;
int ledPin1 = 4;
int ledPin2 = 5;
int ledPin3 = 8;
int ledPin4 = 6;
int ledPin5 = 7;

long duration;
int distance;

void setup(){
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
pinMode(ledPin1, OUTPUT);
pinMode(ledPin2, OUTPUT);

Serial.begin(9608);

}

void loop(){
digitalWrite(trigPin, LOW);
delayMicroseconds(2);

digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

duration = pulseIn(echoPin, HIGH);
ditance = 0.034 * duration/2;
Serial.print("distancia:");
Serial.printIn(distance);

if((distance <= 2) (distance > 2000)){
  digitalWrite(ledPin1, HIGH);
  digitalWrite(ledPin2, HIGH);
  digitalWrite(ledPin3, HIGH);
  digitalWrite(ledPin4, HIGH);
  digitalWrite(ledPin5, HIGH);
  }
  else if((distance > 2)&&(distance<=4)){
  digitalWrite(ledPin1, HIGH);
  digitalWrite(ledPin2, HIGH);
  digitalWrite(ledPin3, HIGH);
  digitalWrite(ledPin4, HIGH);
  digitalWrite(ledPin5, LOW);
  }
  else if((distance > 4)&&(distance <=6)){
  digitalWrite(ledPin1, HIGH);
  digitalWrite(ledPin2, HIGH);
  digitalWrite(ledPin3, HIGH);
  digitalWrite(ledPin4, LOW);
  digitalWrite(ledPin5, LOW);
  }
  else if((distance > 6)&&(distance<=8)){
  digitalWrite(ledPin1, HIGH);
  digitalWrite(ledPin2, HIGH);
  digitalWrite(ledPin3, LOW);
  digitalWrite(ledPin4, LOW);
  digitalWrite(ledPin5, LOW);
  }
  else if((distance > 8)&&(distance<=10)){
  digitalWrite(ledPin1, HIGH);
  digitalWrite(ledPin2, LOW);
  digitalWrite(ledPin3, LOW);
  digitalWrite(ledPin4, LOW);
  digitalWrite(ledPin5, LOW);
  }
  else if(distance > 10){
  digitalWrite(ledPin1, LOW);
  digitalWrite(ledPin2, LOW);
  digitalWrite(ledPin3, LOW);
  digitalWrite(ledPin4, LOW);
  digitalWrite(ledPin5, LOW);
  }
}
  
  
  
