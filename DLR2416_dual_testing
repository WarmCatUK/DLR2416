//**************************************************************//
//  Name    : DLR2416 Display Driver                                
//  Author  : Wayne K Jones
//  Date    : 21 Oct 2014   
//  Modified: 21 Oct 2014                                
//  Version : 0.2.0                                            
//  Notes   : Code for using a 74HC595 Shift Register           //
//          : to drive Siemens DLR2416 intelligentdisplay                          
//****************************************************************

//Pin connected to ST_CP of 74HC595
int latchPin = 8;
//Pin connected to SH_CP of 74HC595
int clockPin = 12;
////Pin connected to DS of 74HC595
int dataPin = 11;
// Pin connected to "A0 digital select" on display
int digitSel0Pin = 5;
// Pin connected to "A1 digital select" on display 
int digitSel1Pin = 6;
// Pin connected to "WR Write" on display
int displayWritePin = 7;
// Pin connected to CS1 on left display
int displayLeftPin = 4;
// Pin connected to CS1 on right display
int displayRightPin = 3;

// AI for temp sensor
int tempSensPin = 0;

// Global Variables
int charToWrite;
int altCount = 0;

// Functions
void displayChar(char, int);
void displayWord(String);
void scrollWord(String);
void selectDisplay(int);

void setup() {
  //set pins to output so you can control the shift register
  pinMode(latchPin, OUTPUT);
  pinMode(clockPin, OUTPUT);
  pinMode(dataPin, OUTPUT);
  pinMode(digitSel0Pin, OUTPUT);
  pinMode(digitSel1Pin, OUTPUT);
  pinMode(displayWritePin, OUTPUT); 
  pinMode(displayLeftPin, OUTPUT);
  pinMode(displayRightPin, OUTPUT);
  Serial.begin(9600);
}


void loop() {
  

  selectDisplay(0);
  displayWord(" Ter");
  selectDisplay(1);
  displayWord("esa ");
  delay(1000);
  
  selectDisplay(0);
  displayWord("  is");
  selectDisplay(1);
  displayWord(" a  ");
  delay(1000);


  selectDisplay(0);
  displayWord("  Fa");
  selectDisplay(1);
  displayWord("rt  ");
  delay(1000);
  
  selectDisplay(0);
  displayWord(" Mag");
  selectDisplay(1);
  displayWord("net ");
  delay(2000);


  /*
  // **** Temp Sensor bit ****
  int tempReading = analogRead(tempSensPin);
  float voltage = tempReading*5.0;
  voltage /= 1024.0;
  float tempC = (voltage - 0.58)*100;
  //converting from 10 mv per degree wit 500 mV offset to degrees ((voltage - 500mV) times 100)
  //round to nearest whole number and convert to int then output to serial monitor
  int tempCint = tempC+0.5;
  //Serial.print(tempCint); Serial.println(" degrees C");  
  //convert int to string
  char tempChar[4];
  sprintf(tempChar, "%d  ",tempCint);
  
  // display temp
  selectDisplay(0);
  displayWord(tempChar);
  displayChar(0x1B,2); //display degrees C 
  */
    // whirl
   /*
  for (int spin=0; spin<10; spin++)
  {
    displayChar(0x5C,3); delay(50); 
    displayChar(0x7C,3); delay(50); 
    displayChar(0x2F,3); delay(50); 
    displayChar(0x2D,3); delay(50);
  }
  
  //delay(2000);
  */
  
  /*
  // count from 0 to 255 and display the number 
  // on the LEDs
  for (int numberToDisplay = 0x39; numberToDisplay > 0x2F; numberToDisplay--) {
    // take the latchPin low so 
    // the LEDs don't change while you're sending in bits:
    digitalWrite(latchPin, LOW);
    // shift out the bits:
    shiftOut(dataPin, clockPin, MSBFIRST, numberToDisplay);  

    
    for (int digitSel = 0; digitSel < 4; digitSel++) {
      
    // - select display character
     switch (digitSel) {
   case 0:
     digitalWrite(digitSel0Pin, LOW);
     digitalWrite(digitSel1Pin, LOW);
     break;
   case 1:
     digitalWrite(digitSel0Pin, HIGH);
     digitalWrite(digitSel1Pin, LOW);
     break;
   case 2:
     digitalWrite(digitSel0Pin, LOW);
     digitalWrite(digitSel1Pin, HIGH);
     break;
   case 3:
     digitalWrite(digitSel0Pin, HIGH);
     digitalWrite(digitSel1Pin, HIGH);
     break;
       }

    // - set WR LOW to enable writing to the display
    digitalWrite(displayWritePin, LOW);
    delay(2);
    //take the latch pin high so we write send out contents of shift register:
    digitalWrite(latchPin, HIGH);   
    // - set WR HIGH to enable display
    digitalWrite(displayWritePin, HIGH);
    //delay(2);
    }

    // pause before next value:
    delay(80);
  }
  */
  // End Bit

  /*
     delay(1000);
     displayWord("Give");
     displayWord(" me ");
     displayWord("more");
     displayWord("food");
     displayWord("plz!");
     displayWord(" :) ");
     delay(500);
     */
     /*
     charToWrite = 0x4C; // "L"
     digitalWrite(digitSel0Pin, HIGH); delay(4);
     digitalWrite(digitSel1Pin, HIGH);
     digitalWrite(latchPin, LOW); delay(2);
     shiftOut(dataPin, clockPin, MSBFIRST, charToWrite); 
     digitalWrite(displayWritePin, LOW); delay(2);
     digitalWrite(latchPin, HIGH);
     digitalWrite(displayWritePin, HIGH); delay(2);
     charToWrite = 0x4F; // "O"
     digitalWrite(digitSel0Pin, LOW); delay(4);
     digitalWrite(digitSel1Pin, HIGH);
     digitalWrite(latchPin, LOW);
     shiftOut(dataPin, clockPin, MSBFIRST, charToWrite);
     digitalWrite(displayWritePin, LOW); delay(2);
     digitalWrite(latchPin, HIGH);
     digitalWrite(displayWritePin, HIGH); delay(2);
     charToWrite = 0x4C; // "L"
     digitalWrite(digitSel0Pin, HIGH); delay(4);
     digitalWrite(digitSel1Pin, LOW);
     digitalWrite(latchPin, LOW);
     shiftOut(dataPin, clockPin, MSBFIRST, charToWrite);
     digitalWrite(displayWritePin, LOW); delay(2);
     digitalWrite(latchPin, HIGH);
     digitalWrite(displayWritePin, HIGH); delay(2);
     charToWrite = 0x21; // "!"
     digitalWrite(digitSel0Pin, LOW); delay(4);
     digitalWrite(digitSel1Pin, LOW);
     digitalWrite(latchPin, LOW);
     shiftOut(dataPin, clockPin, MSBFIRST, charToWrite);
     digitalWrite(displayWritePin, LOW); delay(2);
     digitalWrite(latchPin, HIGH);
     digitalWrite(displayWritePin, HIGH); delay(2);
     */
     //delay(2000);
}


// function displayChar
void displayChar(char myChar, int myPos)
{
  switch (myPos)
  {
    case 3:
    digitalWrite(digitSel0Pin, LOW);
    digitalWrite(digitSel1Pin, LOW);
    break;
    case 2:
    digitalWrite(digitSel0Pin, HIGH);
    digitalWrite(digitSel1Pin, LOW);
    break;    
    case 1:
    digitalWrite(digitSel0Pin, LOW);
    digitalWrite(digitSel1Pin, HIGH);
    break;
    case 0:
    digitalWrite(digitSel0Pin, HIGH);
    digitalWrite(digitSel1Pin, HIGH);
    break;
  }
  // set shift register
  digitalWrite(latchPin, LOW);
  shiftOut(dataPin, clockPin, MSBFIRST, myChar);
  digitalWrite(displayWritePin, LOW); delay(2);
  digitalWrite(latchPin, HIGH);
  digitalWrite(displayWritePin, HIGH); //delay(2);
}

void displayWord(String myString)
{
  for (int x = 0; x < 4; x++) {
    displayChar(myString.charAt(x),x);
  }
}

void scrollWord(String myString)
{
  int stringLength = myString.length(); //what is length of string?
  for (int x = 0; x<(stringLength -3); x++)
  {
    displayChar(myString.charAt(x),0); 
    displayChar(myString.charAt(x+1),1);
    displayChar(myString.charAt(x+2),2);
    displayChar(myString.charAt(x+3),3);
    delay(150);
  }
}

void selectDisplay(int myDisplay)
{
  if (myDisplay == 0) {
    digitalWrite(displayLeftPin, LOW);
    digitalWrite(displayRightPin, HIGH);
  } else {
    digitalWrite(displayLeftPin, HIGH);
    digitalWrite(displayRightPin, LOW);
  }
}
