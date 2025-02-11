# For-shortcircuit-induction-
tinkercad link: https://www.tinkercad.com/things/6WwJeXQV1FH-traffic-light-shortcircut-task?sharecode=7kE63SZ-uOMmaI1EO7-HnpMc-Usn90hRNnxueg4WeIQ
code:










int b=0;
void setup()
{
  Serial.begin(9600);
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(1,INPUT_PULLUP);
}

void loop()
{
 int a=millis();
 int c=digitalRead(1);
 Serial.println(c);
 if(c==1)
 {
   if((a-b)<=500)
	 {
 	  digitalWrite(4,HIGH);
 	  digitalWrite(3,LOW);
 	  digitalWrite(2,LOW);
	 }
	 if((a-b)>500 && (a-b)<=1000)
	 {
	   digitalWrite(4,LOW);
	   digitalWrite(3,HIGH);
 	  digitalWrite(2,LOW);
 	 }
	 if((a-b)>1000)
	 {
	  digitalWrite(4,LOW);
 	  digitalWrite(3,LOW);
 	  digitalWrite(2,HIGH);
	 }
	 if((a-b)>=1500)
	 {
 	  b=a;
 	 }
 }
 else
 {
   digitalWrite(4,HIGH);
   digitalWrite(3,LOW);
   digitalWrite(2,LOW);
 }
}
