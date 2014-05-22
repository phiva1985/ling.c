ling.c
======
#include <stdio.h>
int main() {
  FILE *arq1, *arq2, *arq3;
  char nome1[101], nome2[101], nome3[101];
  int x1, x2, f1, f2;
printf("Entre com nome do primeiro arquivo de entrada: ");
scanf("%s", nome1);
arq1 = fopen(nome1, "r");
printf("Entre com nome do segundo arquivo de entrada: ");
scanf("%s", nome2);
arq2 = fopen(nome2, "r");
printf("Entre com nome do arquivo de saida: ");
scanf("%s", nome3);
arq3 = fopen(nome3, "w");
if (arq1 && arq2 && arq3) {
f1 = fscanf(arq1, "%d", &x1);
f2 = fscanf(arq2, "%d", &x2);
while ((f1 !=EOF) && (f2 != EOF))
if (x1 < x2) {
fprintf(arq3, "%d\n", x1);
f1 = fscanf(arq1, "%d", &x1);
} else {
fprintf(arq3, "%d\n", x2);
f2 = fscanf(arq2, "%d", &x2);
}
while (f1 != EOF) {
fprintf(arq3, "%d\n", x1);
f1 = fscanf(arq1, "%d", &x1);
}
while (f2 != EOF) {
fprintf(arq3, "%d\n", x2);
f2 = fscanf(arq2, "%d", &x2);
}
} 
else {
printf("Erro ao abrir os arquivos.\n");
}
if (arq1)
fclose(arq1);
if (arq2)
fclose(arq2);
if (arq3)
fclose(arq3);
return 0;
}
