Questão 1


#include <stdio.h>//bibliotecas declaradas
#include <stdlib.h>

int *soma_vetor_simples(int*A, int*B, int n);//prototipo
int **soma_vetor_ponteiros(int**A, int**B, int n);//prototipo

/*____________________________________________*/
int *soma_vetor_simples(int *A, int*B, int n){ //chamando a funcao 
    /* 
    Função que retorna a soma de duas matrizes, isto é, A+B
    Função implementada considerando a declaração dinâmica de matrizes como vetor simples 
        int *A: matriz 
        int *B: matriz 
        int n: dimensão das matrizes A e B considerando n x n (mesma quantidade de linhas e colunas)
    Return: 
        C: matriz que armazena a soma A+B 
    */
    int i,j;//declaração de variáveis 
    int *C;
    C = (int*) malloc(n*n*sizeof(int));
    for(i=0; i<n; i++){//percorrendo um laço de repetição 
        for(j=0; j<n; j++)
            C[i*n +j] = A[i*n +j] +B[i*n +j];
    }
    return C;
}

/*____________________________________________*/
int **soma_vetor_ponteiros(int **A, int **B, int n){ //chamando a funcao 
    /* 
    Função que retorna a soma de duas matrizes, isto é, A+B
    Função implementada considerando a declaração dinâmica de matrizes como vetor de ponteiros 
        int **A: matriz 
        int **B: matriz 
        int n: dimensão das matrizes A e B considerando n x n (mesma quantidade de linhas e colunas)
    Return: 
        C: matriz que armazena a soma A+B 
    */
    int i,j;
    //Alocação dinâmica de C
    int**C;
    C = (int**) malloc(n*sizeof(int*));// alocando espaço 
    for(i=0; i<n; i++)
        C[i] = (int*) malloc(n*sizeof(int));

    // Laço de repetição para somar C= A+B
    for(i=0;i<n;i++){//laço de repetição 
        for(j=0;j<n;j++)
            C[i][j] = A[i][j] + B[i][j]; //troca de valores
    }
    return C;
}


/*____________________________________________*/
int main(void){
    /* Função principal do programa em C*/ 

    int i,j, n;//declarando variáveis 

    printf("Insira a dimensão da matriz: \t");//pedindo ao usuario para inserir a dimensão da matriz
    scanf("%d", &n);//leitura da dimensão 

    int**A, **B;
    /*Alocação da matriz A*/
    A = (int**) malloc(n*sizeof(int*));
    for(i=0; i<n; i++){
        A[i] = (int*) malloc(n*sizeof(int));//alocando memoria 
    }

    /*Alocação da matriz B*/
    B = (int**) malloc(n*sizeof(int*));
    for(i=0; i<n; i++){
        B[i] = (int*) malloc(n*sizeof(int));//alocando memoria 
    }

    // Leitura dos elementos de A
    for(i=0;i<n;i++){
        for(j=0;j<n;j++){
            printf("Matriz A: Digite o elemento da posicao i=%d j=%d \n", i, j);
            scanf("%d", &A[i][j]);//lendo a posicao do elemento a
        }
    }

    // Leitura dos elementos de B
    for(i=0;i<n;i++){
        for(j=0;j<n;j++){
            printf("Matriz B: Digite o elemento da posicao i=%d j=%d \n", i, j);
            scanf("%d", &B[i][j]);//lendo a posicao do elemento b
        }
    }

    int**Soma = soma_vetor_ponteiros(A, B,n); //chamando a funcao

    // Imprimir o resultado da soma
    for(i=0;i<n;i++){
        for(j=0;j<n;j++){
        printf("\n %d \t", Soma[i][j]);
        }
    }
    return 0;//retornar a soma
}
