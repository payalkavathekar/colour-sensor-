int redin = 3;
int greenin = 5;
int bluein = 6                                                                                 ;

int redvalue = 0;
int greenvalue = 0;
int bluevalue = 0;

int redout = 9;
int greenout = 10;
int blueout = 11;

int ldr = A0;






void setup() {
  // put your setup code here, to run once:
  pinMode(redin,OUTPUT);
  pinMode(greenin,OUTPUT);
  pinMode(bluein,OUTPUT);
  pinMode(redout,OUTPUT);
  pinMode(greenout,OUTPUT);
  pinMode(blueout,OUTPUT);
  pinMode(ldr,INPUT);
  Serial.begin(9600);
}
  
  void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(redin,HIGH);
  redvalue = analogRead(ldr);
  delay(1000);
  digitalWrite(redin,LOW);
  Serial.print("R=");
  Serial.print(redvalue);
  Serial.print("\n");

   digitalWrite(greenin,HIGH);
   delay(1000);
  greenvalue = analogRead(ldr);
  delay(1000);
  digitalWrite(greenin,LOW);
  Serial.print("G=");
  Serial.print(greenvalue);
  Serial.print("\n");

   digitalWrite(bluein,HIGH);
  bluevalue = analogRead(ldr);
  delay(1000);
  digitalWrite(bluein,LOW);
  Serial.print("B=");
  Serial.print(bluevalue);
  Serial.print("\n");


  if(redvalue>greenvalue&&redvalue>bluevalue)
  {
    digitalWrite(redout,HIGH);
    delay(1000);
    digitalWrite(redout,LOW);
  }
  else
  {
   digitalWrite(redout,LOW); 
  }
  
  if(greenvalue>redvalue&&greenvalue>bluevalue)
  {
    digitalWrite(greenout,HIGH);
    delay(1000);
    digitalWrite(greenout,LOW);
  }
  else
  {
   digitalWrite(greenout,LOW); 
  }

  if(bluevalue>redvalue&&bluevalue>greenvalue)
  {
    digitalWrite(blueout,HIGH);
    delay(1000);
    digitalWrite(blueout,LOW);
    
  }
  else
  {
   digitalWrite(blueout,LOW); 
  }
}
