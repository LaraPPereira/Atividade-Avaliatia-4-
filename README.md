# Atividade-Avaliatia-4-
3 Sensores, com cilindro e um soprador
![download](https://user-images.githubusercontent.com/103466894/175140698-949ce958-4802-4de8-a2f3-df241884a886.png)

Código
 

// Ligar sistema
int button=13;

// Sensor - Caixa Baixa 
int s1=3; 
// Sensor - Caixa Média 
int s2=4;
// Sensor - caixa - Alta
int s3=5; 

// Sopro
int k1=6;
// Esteira Desvio
int k2=7;

// Tempo de sompro
int t_sopro=800; 
 // Tempo de desvio
int t_desvio=1500; 

//Estados
int sensor1=0;
int sensor2=0;
int sensor3=0;

//++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
void setup() {
  
pinMode(button, INPUT);
pinMode(sensor1, INPUT);
pinMode(sensor2, INPUT);
pinMode(sensor3, INPUT);

pinMode(k1, OUTPUT);
pinMode(k2, OUTPUT); 
}
//+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
void loop() {
  
sensor1 = digitalRead(s1);
sensor2 = digitalRead(s2);
sensor3 = digitalRead(s3);

// Soprador da caixa fora do padrão

    if  ((button==1)&& (sensor2==1)&&(sensor1==1)&&(sensor3==0)) {
  // Sopro
  digitalWrite(k1, HIGH); 
// t_sopro = tempo de sopro
delay(t_sopro); 
// Desligar o sopro
digitalWrite(k1, LOW); 
}
    else{
digitalWrite(k1, LOW);
}
// Acionar a esteira de desvio
    if ((button==1)&&(sensor1==1)&&(sensor2==1)&&(sensor3==1)) {
 //Desvio
digitalWrite(k2, HIGH); 
//t_desvio
delay(t_desvio);

//Desligar o desvio
digitalWrite(k2, LOW); 
}
    else {
  digitalWrite(k2, LOW); 
  }
}
