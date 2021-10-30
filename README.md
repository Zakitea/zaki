# zaki 
1197070079 A1

#include <LiquidCrystal.h>
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);
const int pir1=6,pir2=7;
const int red=8,green=9;
int in=0,out=0;

void setup() 
{  
  lcd.begin(16, 2); 
  lcd.print("   RUANG RAPAT");
  lcd.setCursor(2,1);
  lcd.print("Jaga Jarak!!!!");
  delay(1000);
  pinMode(pir1, INPUT);
  pinMode(pir2, INPUT);
  pinMode(green, OUTPUT);
  pinMode(red, OUTPUT);
  lcd.begin(16, 2);
  

}

void loop() 
{
 if (digitalRead(pir1))
 {
   digitalWrite(red,HIGH);
   in = in+1;
   delay(1000);
 }
  else  
   digitalWrite(red,LOW);
     
  if (digitalRead(pir2))
 {
   digitalWrite(green,HIGH);
   out = out+1;      
   delay(1000); 
 }
  
  else
   digitalWrite(green,LOW);
  
  
  lcd.clear();
  
  lcd.setCursor(1,0); //(mengatur lokasi tata letak awal huruf
  lcd.print("Jumlah Visitor");
  
  //lcd.setCursor(5,0);
  lcd.setCursor(0,1); //mengatur Letak huruf
  lcd.print("IN:");
  
  lcd.setCursor(3,1);
  lcd.print(in); //mengatur letak angka
  
  lcd.setCursor(5,1); //mengatur Letak huruf
  lcd.print("OUT:");
  
  lcd.setCursor(9,1); //mengatur letak angka
  lcd.print(out);
 
  
  lcd.setCursor(11,1); //mengatur Letak huruf
  lcd.print("T:");
  
  lcd.setCursor(13,1); //mengatur letak angka
  lcd.print(in - out);
  delay(1000); 
}

