Programa em linguagem C que utiliza vetores unidimensionais para armazenar códigos de produtos e suas respectivas quantidades. Simula um controle básico de estoque com entrada de dados via usuário e exibição das informações cadastradas.

codigo:

#include <stdio.h>
#include <stdlib.h>

int produtos;
int detalhe = 0;

int armazenar(){

    printf("Quantos produtos? ");
    scanf("%d",&produtos);

    int codigo[produtos];
    int quantidade[produtos];

    for(int i=0;i<produtos;i++){
        printf("Insira o codigo do produto: ");
        scanf("%d",&codigo[i]);

        printf("Insira a quantidade: ");
        scanf("%d",&quantidade[i]);
    }

    printf("\n\n");

    for(int i=0;i<produtos;i++){
        printf("Codigo: %d - ",codigo[i]);
        printf("Quantidade: %d\n",quantidade[i]);
    }

    printf("\n\n");
    detalhe++;

    return 0;
}

int main()
{
    int input = 5;

    while(input != 0){
        printf("-------Gerenciador de estoque-------\n");

        if(detalhe != 0){
            printf("Digite 1 para armazenar (o armazenamento anterior sera apagado).\n");
        }else{
            printf("Digite 1 para armazenar.\n");
        }

        printf("Digite 0 para sair.\n\n");

        printf("Valor: ");
        scanf("%d",&input);

        if(input != 0 && input != 1){
            printf("INSIRA UM VALOR VALIDO!\n\n");
            continue;
        }

        switch(input){
            case 1:
                armazenar();
                break;

            case 0:
                printf("Saindo...\n");
                break;
        }
    }

    return 0;
}
