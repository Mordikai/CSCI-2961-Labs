#Lab 10 Group Writeup
####Group Members
Ehsan Ahmed &
Max Walker
###Part 1
We loaded up the drivers, and compiled and ran the Blink example. Fiddling around with the timing was a simple matter of changing the delays within the loop. The board seems to work fine, and our settings are in order to comtinue onwards.
###Part 2
After some confusion over a compilation error, we loaded the Hello World program. No real hitches here.
###Part 3
We took a while on this one. Got way too occupied with cstring manipulation. Eventually realized that we should be working with the arduino String library, whaich simplified things greatly. We never managed to make the arduino register newlines properly, but it wasn't really neccessary for the timer, so we moved on.
###Part 4
The commands were a fairly quick fix. Once we knew how to work the String libary, implementing a crude command parser was straightforward.
###Part 5
Moving right along to the timer. We didn't do any fancy formatting, just gave the arduino a 1000-millisecond ticking integer that it would display facilitated by the commands we programmed in part 4. It definitely worked, at least.

Code for part 5:

#include <LiquidCrystal.h>
#include <String.h>
LiquidCrystal lcd(48, 46, 44, 42, 40, 38, 36, 34, 32, 30, 28);
int __counter = 0;
void init_LCD() {__init_LCD();}

void __init_LCD() {
  pinMode(24, OUTPUT);
  pinMode(26, OUTPUT);
  pinMode(54, OUTPUT);
  pinMode(52, OUTPUT);
  pinMode(50, OUTPUT);
  digitalWrite(24, LOW);
  digitalWrite(26, HIGH);
  digitalWrite(54, LOW);
  digitalWrite(52, HIGH);
  lcd.begin(16, 2);
  OCR0A = 0x01;
  TIMSK0 |= _BV(OCIE0A);
}
SIGNAL(TIMER0_COMPA_vect)
{
  __counter++;
  if(__counter > 14) {
    digitalWrite(50, HIGH);
    __counter = 0;
  }
  else if (__counter > 3) {
    digitalWrite(50, LOW);
  }
}

void lcd_off() {
  digitalWrite(26, LOW);
}

void lcd_on(){
  digitalWrite(26, HIGH);
}

void setup() {
  Serial.begin(9600);
  init_LCD();
}

void loop() {
  lcd.home();
  String input;
  String command;
  String param;
  int timer = 0;
  int ticking = 0;
  while (true) {
  while (Serial.available() > 0) {
    input = Serial.readString();
    input.trim();
  }
  int i = input.indexOf(" ");
  if (i != -1) {
    command = input.substring(0,i);
    param = input.substring(i+1);
  } else {
    command = input;
  }
  if (command == "\\t") {
    timer = param.toInt();
  } else if (command == "\\start") {
    ticking = 1;
  } else if (command == "\\stop") {
    ticking = 0;
  }

  if (timer == 0) {
    ticking = 0;
  }
  if (ticking) {
    delay(1000);
    --timer;
  } 

  lcd.setCursor(0,0);
  lcd.print("timer");
  lcd.setCursor(0,1);
  lcd.print(timer);
  }
}
