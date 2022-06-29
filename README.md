# Exe
#include<stdio.h>
#include<stdlib.h>
#include<time.h>

struct aparecer{
	int N,n2,n3;
	double d,d2;
};
struct Car{
	int C;
};

void exibir(aparecer *nume, int p);
void gavar(aparecer *vetor, int Tam, char *ArqM);
int main(){
	int Tam;
  aparecer *Dados;
aparecer le;
  FILE *Arq;
  FILE *A;
  Car *V;
  Car aux;
  int i;
  int Soma;
int No;
  bool Trocou;
printf("Arquires Souza dos Anjos Stoco\n");
printf("1680482112005\n");
  Tam = 0;
  Dados = NULL;
  Arq = fopen("entrada.txt", "r");
  while (fscanf(Arq,"%d;%d;%d;%lf;%lf", &le.N,&le.n2,&le.n3,&le.d,&le.d2) != EOF) {
  
    Tam++;
    Dados = (aparecer *)realloc(Dados, sizeof(aparecer) * Tam);
    Dados[Tam-1] = le;
  }
  fclose(Arq);
  	printf("Vetor com valor inteiro:\n");
  exibir(Dados,Tam);
  do{
  
  printf("\ndigite um numero\n");
  scanf("%d", &No);
}while(No < 1|| No >= 9);

 for(int t = 0;t <Tam; t++){
 	if( Dados[t].N == No){
 	
 		printf("\n%d %d %d %2.2lf %2.2lf", Dados[t].N,Dados[t].n2,Dados[t].n3,Dados[t].d,Dados[t].d2);
 for(int t = 0;t <Tam; t++){
 	if( Dados[t].N == No){
 	A = fopen("saida.txt", "w");
 	fprintf(A,"\n%d %d %d %2.2lf %2.2lf", Dados[t].N,Dados[t].n2,Dados[t].n3,Dados[t].d,Dados[t].d2);
 	fclose(A);
 }
 }
	 }
	 
 }
  

   free(Dados);
  printf("\n\nFim do Programa");
  return(0);
}
void exibir(aparecer *nume, int p){


	int i;
  
  for (i = 0; i < p; i++) {
  
    printf("\n%d %d %d %2.2lf %2.2lf", nume[i].N,nume[i].n2,nume[i].n3,nume[i].d,nume[i].d2);
  }  
}

void gavar(aparecer *vetor, int Tam, char *ArqM){
	int i;
    FILE *Arq;
	 Arq = fopen(ArqM, "w");
	 for(i=0;i<Tam;i++){
	 
	 fprintf(Arq,"\n%d %d %d %2.2lf %2.2lf", vetor[i].N,vetor[i].n2,vetor[i].n3,vetor[i].d,vetor[i].d2);
}
}
