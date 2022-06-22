# Atividade-Avaliatia-4-
3 Sensores, com cilindro e um soprador
![download](https://user-images.githubusercontent.com/103466894/175140698-949ce958-4802-4de8-a2f3-df241884a886.png)

Código
 
int liga = 3;
//Sensores
int a0 = 4;
int a1 = 5;
int b1 = 6;

// Estados
int sliga = 0;
int sa0 = 0;
int sa1 = 0;
int sb1 = 0;

int a_mais = 13;
int a_menos = 12;
int b_mais = 11;
//=========================================================================================================================================
void setup() {
  pinMode (liga, INPUT);
  pinMode (a0, INPUT);
  pinMode (a1, INPUT);
  pinMode (b1, INPUT);

  pinMode (a_mais, OUTPUT);
  pinMode (a_menos, OUTPUT);
  pinMode (b_mais, OUTPUT);
}
//+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
void loop() {
  sliga = digitalRead (liga);
  sa0 = digitalRead (a0);
  sa1 = digitalRead (a1);
  sb1 = digitalRead (b1);

  if (sliga == 1 && sa0 == 1)
  {
    digitalWrite (a_mais, HIGH);
  }
  if (sa1 == 1)
  {
    digitalWrite (b_mais, HIGH);
  }
  else ((sb1 == 1) && (sa0 == 0));
    {
      digitalWrite (a_menos, HIGH);
  }
}
