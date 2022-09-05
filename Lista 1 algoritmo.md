Questão 1



#include<stdio.h>

Int x, y, *p;
y=0;
P=&y;
x=*p;
x=4;
(*P)++;
--x;
(*P)+= x;
}

X=  3;
Y=4;
P=4;
//Saída da variáveis x=3,y:4, p=4


Questão 2
int main(void){
int x,*p;
X=100;
p=x;// falta o & comercial
printf("valor de p% p%/t valor de *p=%d",p*,p);{
}





Questão 3
#include<stdio.h>
int main (void){
int a,b,c;
int *p1;
int *p2=&a;
int *p3=&b;
p1=p2;
*p2=10;
b=20;
int **pp;
pp=&p1;
*p3=**pp;
*p2=b+(*p1)++
printf("%d\t%d\t%d\n", a,b,c);
Return 0;
}

Saída:
a=30
b=20
c=10

//p2 armazena o endereço de a;
//p3 armazena o endereço de c;
//p1 armazena o endereço de valor de p2 e p1 armazena o valor de a;
// declara-se que b tem valor 20;
//p2 é igual b mais o valor de *p1++,depois de se ler a função vai retornar os resultados:30,20,10;



Questão 4

#include<stdio.h> //declarando minhas bibliotecas
#include<math.h>
#include<stdlib.h>

    void calcula_hexagono(float l, float *area, float *perimetro); //prototipo da função
    int main(void){
    float l;// variavel do tipo real
    float perimetro, area; //declaração de variaveis do tipo real
    
 printf("digite o lado do hexagono: ");//solicita o lado do hexagano
     scanf("%f", &l); //lendo os dados de l
     calcula_hexagono(l, &perimetro, &area);//chamando a funçao
    printf("digite o lado do hexagono= %f%f", perimetro, area);// exibição dos lados do hexagano
     	  return 0; //para retornar algo
 }
      
       void calcula_hexagono(float l, float *area, float *perimetro){ //prototipo 
    
      *area = (3*pow (l,2)*sqrt(3))/ 2; //calculando a area 
      *perimetro=6*l; //calculando o perimetro
	 
	   }
