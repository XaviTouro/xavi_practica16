# xavi_practica16
/******************************************************************************************************************************
* Reaproveita a montaxe da prática a anterior e o código da mesma. Nesta práctica imos complicar un pouco a programación 
* para simplificar a condición do IF-ELSE da práctica anterior.
*
* Como a condición responde a función lóxica:imos dividir a condición en tres subcondición (xa o tés feito da práctica
* anterior): eCada unha delas vai corresponder a unha estructura IF-ELSE. No primeiro bloque IF-ELSE vas pór a primeira 
* subcondición, o segundo bloque IF-ELSE vai ir dentro do bloque ELSE anterior (si, un IF-ELSE dentro dun ELSE).
* Neste segundo bloque IF-ELSE vás por a segunda subcondición na parte correspondente do IF.
* O último IF-ELSE irá no ELSE que aínda estaba baleiro. E por suposto a terceira subcondición na parte correspondente deste IF.
*
* En relación cos bloques de código que se van executar: (a) no ELSE final vai o código correspondente ao ELSE da práctica 
* anterior (apagar o LED), (b) en cada un dos IF restantes irá o código do que queremos que faga: pór o LED a ON. 
* É máis fácil facelo que explicalo.
*
* A parte de montaxe é a mesma que a práctica anterior, o que muda é o código do programa.
*
*   AUTOR: Xavi Figueiro
*
*   DATA: 16/12/2023
*
*******************************************************************************************************************************/




// Identificar entradas e saídas.
// Declarar entradas e saídas
// Declarar variables globais ou sentenzas do preprocesador.
// Intentar descompoñer o problema en tarefas máis simples.
//  Secuenciar ou ordear as tarefas.

#define pinA 10  // Entrada A
#define pinB 9   // Entrada B
#define pinC 8   // Entrada C
#define pinS 11  // Saída a Relay 


int tempo = 4000;         // tempo espera aceso ou apagado.
bool condicion = -1;      // condición para o acendido  ou apagado bombeo.
bool cond01, cond02, cond03 = -1;

bool a, b, c = -1;        // variables que gardan o valor de cada interruptor.

void setup(){
  pinMode(pinA, INPUT);
  pinMode(pinB, INPUT);
  pinMode(pinC, INPUT);
  pinMode(pinS, OUTPUT);
  //serial.begin(9600);
  
 }

void loop(){
  a = digitalRead(pinA);
  b = digitalRead(pinB);
  c = digitalRead(pinC);
  
  //condicion = (!a && b && !c) || (a && b && !c) || (a && b && c);
  cond01 = (!a && b && !c);
  cond02 = (a && b && !c);
  cond03 = (a && b && c);
  
   //serial.printín(condicion);
  
   if(cond01){
    digitalWrite(pinS, HIGH);
    delay(tempo);
  }
  else if(cond02){
    digitalWrite(pinS, HIGH);
    delay(tempo);
  }
  else if(cond03){
    digitalWrite(pinS, HIGH);
    delay(tempo);
  }
  else {
    digitalWrite(pinS, LOW);
    delay(tempo);
  }
}

