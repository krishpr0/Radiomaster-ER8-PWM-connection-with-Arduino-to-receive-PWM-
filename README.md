# Radiomaster-ER8-PWM-connection-with-Arduino-to-receive-PWM-

```
// Define pin numbers for the 5 channels
const int ch1Pin = 2;  // Connect Channel 1 to digital pin 2
const int ch2Pin = 3;  // Connect Channel 2 to digital pin 3
const int ch3Pin = 4;  // Connect Channel 3 to digital pin 4
const int ch4Pin = 5;  // Connect Channel 4 to digital pin 5
const int ch5Pin = 6;  // Connect Channel 5 to digital pin 6

// Variables to store pulse widths (PWM values)
unsigned long ch1PWM, ch2PWM, ch3PWM, ch4PWM, ch5PWM;

void setup() {
  // Start serial communication to display PWM values
  Serial.begin(9600);

  // Set pins as input
  pinMode(ch1Pin, INPUT);
  pinMode(ch2Pin, INPUT);
  pinMode(ch3Pin, INPUT);
  pinMode(ch4Pin, INPUT);
  pinMode(ch5Pin, INPUT);
}

void loop() {
  // Read PWM values using pulseIn()
  ch1PWM = pulseIn(ch1Pin, HIGH);
  ch2PWM = pulseIn(ch2Pin, HIGH);
  ch3PWM = pulseIn(ch3Pin, HIGH);
  ch4PWM = pulseIn(ch4Pin, HIGH);
  ch5PWM = pulseIn(ch5Pin, HIGH);

  // Display the PWM values for each channel
  Serial.print("Ch1: "); Serial.print(ch1PWM);
  Serial.print(" Ch2: "); Serial.print(ch2PWM);
  Serial.print(" Ch3: "); Serial.print(ch3PWM);
  Serial.print(" Ch4: "); Serial.print(ch4PWM);
  Serial.print(" Ch5: "); Serial.println(ch5PWM);

  // Add a delay to make the output more readable
  delay(100);
}
