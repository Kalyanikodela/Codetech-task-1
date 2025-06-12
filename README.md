# Codetech-task-1

NAME : KODELA KALYANI

INTERN ID : CTO4DF1753

DOMAIM : EMBEDDED SYSTEMS

DURATION : 4 WEEKS

MENTOR : NEELA SANTHOSH

DESCRIPTION : A counter is a device that counts the number of times when a particular event occurs.
Here we count the number of times the push switch has been pressed. The Arduino detects a transition of input from a LOW state to the HIGH state during switch press; that is the value of counting variable increments for a positive edge triggering.n the circuit, the push switch is connected to a digital pin of the Arduino; here at pin 9. When the push switch has pressed the LED ON for half a seconds and then OFF, it is provided just for an indication that the switch press has been detected or the value has been incremented by one.

CIRCUIT DIAGRAM : 
![image](https://github.com/user-attachments/assets/e9159388-7393-428a-9111-f69a7bf24558)

CODE :
const int buttonPin = 2;     // the number of the pushbutton pin
const int ledPin =  9;      // the number of the LED pin

// variables will change:
int buttonState = 0;         // variable for reading the pushbutton status
int count_value =0;
int prestate =0;
void setup() {
  // initialize the LED pin as an output:
  pinMode(ledPin, OUTPUT);
  // initialize the pushbutton pin as an input:
  pinMode(buttonPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  // read the state of the pushbutton value:
  buttonState = digitalRead(buttonPin);

  // check if the pushbutton is pressed. If it is, then the buttonState is HIGH:
  if (buttonState == HIGH && prestate == 0) {
    count_value++;
    Serial.println(count_value);
    // turn LED on
    digitalWrite(ledPin, HIGH);
    delay(100);
    // turn LED off
    digitalWrite(ledPin, LOW);

    prestate = 1;
  } else if(buttonState == LOW) {
    prestate = 0;
  }
}

OUTPUT :
![image](https://github.com/user-attachments/assets/56d6ce84-c02e-473c-98a4-34324921469f)

