//Padrão de Teclas: https://www.arduino.cc/en/Reference/KeyboardModifiers
#include "Ultrasonic.h"
#include "Adafruit_APDS9960.h" 
#include "Keyboard.h"
Adafruit_APDS9960 apds; 

const int echoPin = 7; 
const int trigPin = 6;
Ultrasonic ultrasonic(trigPin,echoPin);
int distancia; 
String result;

void setup() {
  pinMode(echoPin, INPUT); 
  pinMode(trigPin, OUTPUT);
  Serial.begin(9600);
  Serial.println("Lendo dados do sensor...");

  if (!apds.begin()) { 
    Serial.println("Falha ao inicializar o dispositivo. Verifique as conexões!"); 
  }
  else Serial.println("Dispositivo inicializado!"); 
  
  apds.enableProximity(true);
  apds.enableGesture(true);

  Keyboard.begin();
}

void loop() 
{
  hcsr04();
  
ROTINA:
while (distancia <= 30)
 {
  uint8_t gesture = apds.readGesture();
  if (gesture == APDS9960_DOWN)
  {
    Serial.println("down");
    Keyboard.press(KEY_DOWN_ARROW);
    delay(100);
    Keyboard.releaseAll();
    delay(100);
    hcsr04();
    }

  if (gesture == APDS9960_UP) 
  {
    Serial.println("up");
    Keyboard.press(KEY_UP_ARROW);
    delay(100);
    Keyboard.releaseAll();
    delay(100);
    hcsr04();
    }

  if (gesture == APDS9960_LEFT) 
  {
    Serial.println("left");
    Keyboard.press(KEY_LEFT_ARROW);
    delay(100);
    Keyboard.releaseAll();
    delay(100);
    hcsr04();
    }
  
  if (gesture == APDS9960_RIGHT) 
  {
    Serial.println("right");
    Keyboard.press(KEY_RIGHT_ARROW);
    delay(100);
    Keyboard.releaseAll();
    delay(100);
    hcsr04();
    }
   goto ROTINA;
  }
}

void hcsr04() {
    digitalWrite(trigPin, LOW); //SETA O PINO 6 COM UM PULSO BAIXO "LOW"
    delayMicroseconds(2); //INTERVALO DE 2 MICROSSEGUNDOS
    digitalWrite(trigPin, HIGH); //SETA O PINO 6 COM PULSO ALTO "HIGH"
    delayMicroseconds(10); //INTERVALO DE 10 MICROSSEGUNDOS
    digitalWrite(trigPin, LOW); //SETA O PINO 6 COM PULSO BAIXO "LOW" NOVAMENTE
                                //FUNÇÃO RANGING, FAZ A CONVERSÃO DO TEMPO DE
                                //RESPOSTA DO ECHO EM CENTIMETROS, E ARMAZENA
                                //NA VARIAVEL "distancia"
    distancia = (ultrasonic.Ranging(CM)); //VARIÁVEL GLOBAL RECEBE O VALOR DA DISTÂNCIA MEDIDA
    result = String(distancia); //VARIÁVEL GLOBAL DO TIPO STRING RECEBE A DISTÂNCIA(CONVERTIDO DE INTEIRO PARA STRING)
     Serial.print("Distancia em cm: ");
     Serial.print(result);
     Serial.println();
     Keyboard.press(KEY_CAPS_LOCK);
     delay(1000);
     Keyboard.press(KEY_CAPS_LOCK);
     delay(100);
     Keyboard.releaseAll();
     delay(200);
}
