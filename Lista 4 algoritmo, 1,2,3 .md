Questão 1


#include<stdlib.h>//declaração de bibliotecas
#include<stdio.h>

 typedef struct ingresso{ //estrutura 
 	float preco;
 	char atracao;
 	char local;	
 }ingresso;
  void preenche(ingresso *i);
  void imprime(ingresso *i);
  	
 int main (void){
 	ingresso*i;
 	i=(ingresso*)malloc(sizeof(ingresso));//alocacao de memoria
 	preenche (i);
 	imprime(i);
 	return 0;
 }
 void preenche(ingresso *i){//prototipo 
printf("digite o valor do preco");//pede ao usuario o valor do preco
scanf("%f", &i->preco);//lendo o preco 
 printf("digite a atracao");//pedindo a atracao
 scanf("% [^\n]", &i->atracao);//lendo a atracao 
 printf("digite o endereco do local");//pedindo o local
 scanf("% [^\n]", &i->local);//lendo o local 
 }
 
//b


void imprime(ingresso *i){//prototipo 
	printf("digite a atracao: %s\n",i->atracao);//solicitando a atracao 
	printf("digite o preco: %f\n",i->preco);//solicitando o preco 
	printf("digite o endereco do local: %s\n", i->local);//solicitando o local
	
}
	
	
//c

	void altera_preco(ingresso* i, float valor){//chamando a funcao
	i->preco=valor;
}

	//d
	void imprime_menor_maior_preco(int n, ingresso* vet){//chamando a funcao
	int maior=0, menor=0,i;	
	for(i=0;i<n;i++){//laco de repeticao
		if(maior<vet[i].preco){
			maior=vet[i].preco;
			if(menor>vet[i].preco){
			menor>vet[i].preco;

			}
		}
	}
		
		
		
		
		
		
		
		
		
		
	}






Questão 2

#include <stdio.h> //declaração de todas as bibliotecas que vai ser utilizadas 
#include <stdlib.h>
#include <string.h>

#define MAX 5 //definindo meu define como max 5 e fixando ele
typedef struct aluno{ //comecando minha funçao com typedef e nomeando como aluno
    int matricula; //declarando variaveis 
    char nome[81];//declarando  variaveis
    char turma;//declarando variaveis
    float nota[3];//declarando variaveis
    float media;//declarando variaveis
}Aluno;

void inicializa(Aluno **alunos, int n){ // prototipo 
	int i; //declarando variavel 
	for(i=0; i<n; i++)
		alunos[i] = NULL; 
}

void matricula(int n, Aluno** alunos){//meu prototipo da função 
    static int i = 0;
    if(i<n){ //chamando o if para verificar 
                alunos[i] = (Aluno*) malloc(n*sizeof(Aluno));//alocando memoria 
                if(alunos[i]==NULL){
                        printf("Memoria cheia \n");
                        exit(1);
                }
                else{
                    printf("Insira a matricula: \n Insira a turma: \n Insira o nome: \n"); //solicitando para o usuario digitar seus dados da turma
                    scanf(" %d ", &alunos[i]->matricula); //leitura de dados usando ponteiro
                    scanf(" %c", &alunos[i]->turma);
                    scanf(" %80[^\n]", alunos[i]->nome);
                    alunos[i]->nota[0]=0; 
                    alunos[i]->nota[1]=0;
                    alunos[i]->nota[2]=0;
                    alunos[i]->media=0;
                    i++;
                }
            }

    else
    {
      printf("Nao ha vagas"); //chamando o printf para saber se ainda tem vagas, caso as de cima não tiverem sido verdadeiras 
    }

}

void lanca_notas(int n, Aluno** alunos){//prototipo
    int i; //declarando variavel
    for(i=0;i<n;i++){
            if(alunos[i]!=NULL){
                printf("Aluno %d", i+1);
                    printf("\n Digite as nota:\n");
                    scanf("%f %f %f", &alunos[i]->nota[0], &alunos[i]->nota[1], &alunos[i]->nota[2]);
                    alunos[i]->media=(alunos[i]->nota[0] + alunos[i]->nota[1] + alunos[i]->nota[2])/3;
                    printf("Media: %.2f \n", alunos[i]->media);
               }
    }
}

void imprime_tudo(int n, Aluno** alunos){// prototipo da função 
    int i; //definindo variavel
    for(i=0; i<n; i++){ //soma no laco de repeticao 
            if(alunos[i]!=NULL){// funcao nula
                printf("\n Matricula:  %d \n", alunos[i]->matricula );//solicitando que o usuario digite sua matricula
                printf("Nome: %s \n", alunos[i]->nome);//solicitando que o usuario digite seu nome
                printf("Turma: %c \n", alunos[i]->turma);//solicitando que o usuario digite sua turma
                printf("Media: %f \n", alunos[i]->media);//solicitando que o usuario digite sua media
                }

    }
}

void imprime_turma(int n, Aluno** alunos, char turma){//prototipo da 
    int i;//declarando variavel
    for(i=0;i<n;i++){
        if(alunos[i]!=NULL && alunos[i]->turma==turma){
            printf("\n Matricula:  %d \n", alunos[i]->matricula );//solicita que o usuario digite sua matricula
            printf("Nome: %s \n", alunos[i]->nome);//solicita que o usuario digite seu nome
            printf("Turma: %c \n", alunos[i]->turma);//solicita que o usuario digite sua turma
        }
    }
}

void imprime_turma_aprovados(int n, Aluno**alunos, char turma){//meu prototipo da função 
    int i; //declarando variavel
    for(i=0;i<n;i++){
        if(alunos[i]!=NULL && alunos[i]->turma==turma){ //verificando se a situação sera verdadeira
           if(alunos[i]->media>=7){
                printf("\n Matricula:  %d \n", alunos[i]->matricula);
                printf("Nome: %s \n", alunos[i]->nome);
                printf("Media: %f \n, APROVADO \n", alunos[i]->media);//solicitação da sua media e exibindo aluno aprovado
           }
        }
    }
}
int main(void){
    Aluno *aluno[MAX]; //Vetores de ponteiros de struct
    inicializa(aluno,MAX); //renomeando a função aluno, max
    matricula(MAX,aluno);
    lanca_notas(MAX, aluno);
    imprime_tudo(MAX,aluno);
    imprime_turma(MAX, aluno, 'a');
    imprime_turma_aprovados(MAX,aluno, 'a');

return 0; //para retornar algo 

}




Questão 3


#include <stdio.h>  //declaração de biblioteca
#include <stdlib.h>
#include <math.h>
/*Defina estruturas para representar retângulos (dadas a base e a altura) e círculos (dado o raio) */

typedef struct retangulo{ 
    float base; //declaração de variavel
    float altura;//declaração de variavel
} Ret; //renomeando minha estrutura 

typedef struct circulo{
    float raio; //declarando variavel 
} Circ;//renomeando minha estrutura 

/* Dado um círculo, crie e retorne o maior retângulo circunscrito de altura h. Considere que h é menor do
que o diâmetro do círculo*/

Ret * ret_circunscrito(Circ *c, float h){ //função 
    Ret *r= malloc(sizeof(Ret)); //função malloc para alocar ret
    r->base = 2 * sqrt(pow(c->raio, 2) - pow(h, 2));
    r->altura = h;
    return r; //retorno em r
}

/* Dado um retângulo, crie e retorne o maior círculo interno ao retângulo*/

Circ * circ_interno(Ret *r){ //função
    Circ *c = malloc(sizeof(Circ)); //função malloc para alocar circ
    c->raio = sqrt(pow(r->base, 2) + pow(r->altura, 2)) / 2;
    return c; //retorno em c
}


int main(void){   
    Circ *c = malloc(sizeof(Circ)); //função malloc para alocar circ
    c->raio = 5;
    Ret *r = ret_circunscrito(c, 3);
    printf("Base: %f ", r->base); //solicitando a base
    printf("Altura: %f ", r->altura);//solicitando a altura
    free(c); //liberacao de memoria
    free(r); //liberacao de memoria
    return 0; //retornando algo
}

