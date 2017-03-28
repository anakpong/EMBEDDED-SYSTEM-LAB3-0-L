# EMBEDDED-SYSTEM-LAB3 แสดงผลตั้งแต่ 0-L
int led_array[18][7] = {   
                         { 1,1,1,1,1,1,0 },  // = 0
                         { 0,1,1,0,0,0,0 },  // = 1
                         { 1,1,0,1,1,0,1 },  // = 2
                         { 1,1,1,1,0,0,1 },  // = 3
                         { 0,1,1,0,0,1,1 },  // = 4
                         { 1,0,1,1,0,1,1 },  // = 5
                         { 1,0,1,1,1,1,1 },  // = 6
                         { 1,1,1,0,0,0,0 },  // = 7
                         { 1,1,1,1,1,1,1 },  // = 8
                         { 1,1,1,0,0,1,1 },  // = 9
                         { 1,1,1,0,1,1,1 },  // = A
                         { 0,0,1,1,1,1,1 },  // = b
                         { 1,0,0,1,1,1,0 },  // = C
                         { 0,1,1,1,1,0,1 },  // = d
                         { 1,0,0,1,1,1,1 },  // = E
                         { 1,0,0,0,1,1,1 },  // = F
                         { 0,1,1,0,1,1,1 },  // = H
                         { 0,0,0,1,1,1,0 }   // = L
                          };    
int digit1 = 13;
int digit2 = 12;

void setup() {
  pinMode(2, OUTPUT);      
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(7, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(9, OUTPUT);
  pinMode(digit1, OUTPUT);
  pinMode(digit2, OUTPUT);
}

void loop() {
  for (int counter = 0; counter < 18; ++counter) 
 {
  digitalWrite(digit2, 1);
   delay(2000);
   led_Write(counter); 
     for (int i = counter; i > 18; i= i + 1){
    digitalWrite(digit1, 1);
   led_Write(i); 
    }
  }
}
void led_Write(int number){
    int pin= 2;
    for (int j = 0; j < 18; j++) {
   digitalWrite(pin, led_array[number][j]);
   pin++;
  }
}

