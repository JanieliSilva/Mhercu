Questão 1 
 
#include<stdio.h>
#include<stdlib.h> 
int main(){ 		
int tamanho , soma, maior, menor,j; //variáveis 	
printf(" digite o tamanho do vetor"); 		
scanf("%d",&tamanho); //lendo o tamanho do vetor	 		
int*vetor=(int*) malloc(tamanho*sizeof(int)); //alocando memoria 		
for(j=0;j<tamanho;j++){ //laço de repetição 		
printf("digite o valor do vetor"); 			
scanf("%d",&vetor[j]); 			
     } 			
for(j=0;j<tamanho;j++){ 			 		
if(maior<vetor[j]){ 	//comparação 	 				
maior=vetor[j]; 				 		
if(menor>vetor[j]){ 			
menor=vetor[j]; 	
     } 	 	
  } 
} 	
soma=maior+menor; //soma dos vetores
printf("digite a soma dos vetores, %d",soma); 		
free(vetor);// liberando espaço no vetor		
return 0; //retornar algo
 }


Questão 2


#include<stdio.h> //biblioteca
#include<stdlib.h> //biblioteca

int main(void){
	int quant, i;//variáveis declaradas
	float med;
	med=0.0;	
 	printf("\tquantidade de alunos e: "); // solicitação da quantidade de alunos ao usuario
		scanf("%d", &quant);//lendo a quantidade de alunos 
	float*vetor_notas=(float*)malloc(quant*sizeof(float)); //alocação dinamica
	if(vetor_notas==NULL){ //laço de repetição que verifica se a memoria
		printf("sem memoria!");
		exit(1); // finaliza o programa caso não haja espaço suficiante na memoria
 }
 	for(i=0;i<quant;i++){  // passando pela quantidade de notas digitadas no primeiro printf
 		printf("\tDigite a %d.o notas ", i+1);
 		scanf("%f", &vetor_notas[i]);
 		med=med+vetor_notas[i]; // soma da media
		 	 }
		med=med/quant; //divisão da media pela quantidade de alunos da sala
		printf("\tA média do aluno e =%.2f", med); //exibição da média final da sala
		free(vetor_notas); //libera o vetor
 return (0);
}


Questão 3


#include<stdio.h> //biblioteca
#include<stdlib.h> //biblioteca

void preenche_ordenado(int n, int *c); // protoripo da função

int main(void){ // programa principal
	int n, i; //declaração de variavel
 	
 	printf("quantidade de elementos dos vetores: "); // solicitação ao usuarios pela quantidade de numeros do vetor 
 		scanf("%d", &n); // leitura dos valores
 	int*vetor=(int*)malloc(n*sizeof(int)); // alocação dinamica dos valores
 		if(vetor==NULL){ //verifica se há espaço na memoria suficiente
 			printf("Sem memoria!");
 		exit(1); // finaliza o programa caso haja espaço insuficiente na memoria 
	 }
	
		for(i=0;i<n;i++){ //laço de repetição que pede e passa por cada um dos numeros que o usuario digitou
			printf("quantidade de números: "); // solicita ao usuario a quantidade de numeros 
			scanf("%d", &vetor[i]); //recebe dos valores
			preenche_ordenado(n, vetor);  // chama do vetor 
		}
		for(int j=n-1;j>=0;j--){ // decremento dos numeros para exibir ao contrario
			printf("[%d]\n", vetor[j]); //apresenta os vetores aleatorios 
		}
	free(vetor); //liberando memoria
	return 0; //fim de programa
}
	 
void preenche_ordenado(int n, int *c){ //função que preenche os vetores aleatorios 
 int j, aux; //declaração de variavel
 for(int i=0;i<n;i++){ // laço de repetição passando pelo vetor
 	for( j=0;j<n;j++);
 	 aux=c[j]; //  armazena em uma nova varivavel e recebe o vetor
 	if(aux>c[j]){
 		c[i]=c[j]; //troca de posição
 		c[j]=aux;
	 }
 }
}



Questão 4


// QUESTÃO 4

#include<stdio.h> //biblioteca
#include<stdlib.h> //biblioteca

#define macro RAND_MAX 	//definição de uma variavel fixa para os numeros aleatorios

int main(void){		
	int l;						
	double n, *vetor;//variáveis 

	printf("quantidades dos numeros dos vetores e: ");	//pede ao usuário o numero de vetores
	scanf("%f", &n);					
	
	vetor=(double*) malloc(n*sizeof(double));		//abrindo o espaço da memoria com uso do malloc
	
	printf("intervalo randomico = [0,%d] \n", RAND_MAX);	//informando o intervalo de rand
	
	for(l=1; l<=10; l++){ // laço de repetição que passa pelos num de reptição de 10 fixos
		printf("Numero %d = %d \n", l, rand());	 // numeros aleatorios
	}
	
    for(l=1; l<=n; l++){ //  laço de repetição 
        printf("Numero %d = %d \n", l, rand());     // exibição de numeros aleatorios 
	free(vetor);	// liberação de espaço da memoria
	return 0; //retornar algo

}
}
