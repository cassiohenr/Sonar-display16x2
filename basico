//Este código calcula a distância do obstáculo ao sensor sonar genérico e dispara um alarme de a medida em centimetros for menor que 30cm.
//Também exibe no display 16x2.

#include <LiquidCrystal.h>

LiquidCrystal lcd(12, 11, 5, 4, 3, 2);
#define setl 28
#define seth 30

const int insonar = 9;
const int outsonar = 8; 
int buzzer = 13;


void setup() 
{
  Serial.begin(9600);
  lcd.begin(16, 2);
  lcd.print("Distancia(cm): ");
  
}

void loop() 
{
long tempo, cm, pol; 
pinMode(buzzer, OUTPUT);
pinMode(insonar, OUTPUT);
digitalWrite(insonar, HIGH);
delayMicroseconds(5);
digitalWrite(insonar, LOW);
pinMode(outsonar, INPUT);

tempo = pulseIn(outsonar, HIGH);
cm = microsecondsToCentimeters(tempo);


Serial.print(cm);
Serial.print("cm");
Serial.println();

lcd.setCursor(8,1);
lcd.print(cm);
delay(200);

if(cm < 30)
{
    digitalWrite(buzzer, HIGH);
    delay(30);
    digitalWrite(buzzer, LOW);
    delay(20);
    digitalWrite(buzzer, HIGH);
    delay(30);
    digitalWrite(buzzer, LOW);   

}

lcd.setCursor(8,1);
lcd.print("                ");

}


long microsecondsToCentimeters(long microseconds)
{
  return microseconds / 29 / 2;
}





