# Cod-task-3#include <LiquidCrystal.h>

// Initialize LCD display
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

// LM35 Pin
const int tempPin = A0;

void setup() {
  lcd.begin(16, 2);
  lcd.setCursor(0, 0);
  lcd.print("Temperature:");
}

void loop() {
  int tempValue = analogRead(tempPin);
  float temperature = (tempValue * 5.0 / 1024.0) * 100;
  lcd.setCursor(0, 1);
  lcd.print("Temp: ");
  lcd.print(temperature);
  lcd.print(" C");
  delay(1000);
}
