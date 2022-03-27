# td2
```C
#include <stdio.h>
#include <stdlib.h>

/* run this program using the console pauser or add your own getch, system("pause") or input loop */
typedef struct liste { 
 int taille; 
 int lmax; 
 float *tab;

 
}LISTE; 
//----------- QUESTION 1 ---------------
LISTE *inintialize(LISTE*m)
{
	m = malloc(sizeof(LISTE*));		
	LISTE* element = m;
	printf("taille : \n");
	scanf("%d",&element->taille);
	printf("lmax : \n");
	scanf("%d",&element->lmax);
    remplirTab(element);
    return m;
}
//----------- QUESTION 3 ---------------
void showliste(LISTE *header){ 
   int i;

 printf("taille de la liste %d \n",header->taille); 
 printf("taille max %d\n",header->lmax); 
 printf("tab: ");
 for(i=0;i<header->taille;i++){
 	printf("%f \n",header->tab[i]);
 }
 

}
//----------- QUESTION  ---------------
void remplirTab(LISTE *head){
	int i;
	for(i=0;i<head->taille; i++){
		printf("donner votre valeur:%d",i);
		scanf("%f", &head->tab[i]);
	}
}
//----------- QUESTION 2 ---------------
void insertbegin(LISTE *m,int a){
	int i;
	if(m->lmax==m->taille+1){
		m->lmax=m->lmax*2;    	
	}
	for(i=m->taille;i>0; i--){
		m->tab[i]=m->tab[i-1];
	}
	m->tab[0]=a;
	m->taille++;
}
//----------- QUESTION 4 ---------------
void detruire(LISTE *m){
	m->lmax=0;
	m->taille=0;
	free(m->tab);
	m->tab=NULL;
}
//----------- QUESTION 5 ---------------
void  supprimerEltListePos(LISTE *m,int pos){
	int i;
	for(i=pos;i<m->taille-1; i++){
		m->tab[i]=m->tab[i+1];
	}
	m->taille--;
}
//----------- QUESTION 6 ---------------
void supprimerOccurListe(LISTE *m,int a){
	int i;
	int count;
	for(i=0;i<m->taille; i++){
		if(m->tab[i]==a){
			supprimerEltListePos(m,i);
			count++;
		}
	}
	m->taille=m->taille-count;
}
//----------- QUESTION 7 ---------------
LISTE clonerListe(LISTE m){
	LISTE clone;
	clone.lmax=m.lmax;
	clone.taille=m.taille;
	int i;
	for(i=0;i<m.taille; i++){
		clone.tab[i]=m.tab[i];
	}
	return clone;
}

int main(int argc, char *argv[]) {
	LISTE *m;
	m=inintialize(m);
	showliste(m);
	return 0;
}
````
