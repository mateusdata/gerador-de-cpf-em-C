# gerador-de-cpf-em-C
Gerador de digitos verificadores
#include <stdio.h>
int main(){
    int n1=0, n2=0, n3=0, n4=0, n5=0, n6=0, n7=0, n8=0, n9=0, pvd=0;
    int consttante=11,calculo_pvd, calculo_sdv,sdv;
    printf("validação de cpf\nInforme 9 numeros um de cada vez:\n");
    scanf(" %d %d %d %d %d %d %d %d %d", &n1, &n2, &n3, &n4, &n5, &n6, &n7, &n8, &n9);
    pvd= (n1*10)+(n2*9)+(n3*8)+(n4*7)+(n5*6)+(n6*5)+(n7*4)+(n8*3)+(n9*2);
    calculo_pvd=(11- (pvd % consttante));
    sdv= (n1*11)+(n2*10)+(n3*9)+(n4*8)+(n5*7)+(n6*6)+(n7*5)+(n8*4)+(n9*3)+(calculo_pvd*2);
    calculo_sdv=(11 -(sdv % consttante));


    if (calculo_sdv>=10) {
        printf("cpf gerado...\n");
        printf("%d%d%d.%d%d%d.%d%d%d-%d0",n1,n2,n3,n4,n5,n6,n7,n8,n9,calculo_pvd);
        printf("\nConsulte em: https://www.4devs.com.br/validador_cpf\n");
    }
    else if(calculo_sdv<=9){
        printf("cpf gerado...\n");
        printf("%d%d%d.%d%d%d.%d%d%d-%d%d",n1,n2,n3,n4,n5,n6,n7,n8,n9,calculo_pvd,calculo_sdv);
        printf("\nConsulte em: https://www.4devs.com.br/validador_cpf\n");
    }
    else if(calculo_pvd>=10){
        printf("cpf gerado...\n");
        printf("%d%d%d.%d%d%d.%d%d%d-%d0",n1,n2,n3,n4,n5,n6,n7,n8,n9,calculo_pvd);
        printf("\nConsulte em: https://www.4devs.com.br/validador_cpf\n");
    }
    else if (calculo_pvd<=9){
        printf("cpf gerado...\n");
        printf("%d%d%d.%d%d%d.%d%d%d-%d%d",n1,n2,n3,n4,n5,n6,n7,n8,n9,calculo_pvd,calculo_sdv);
        printf("\nConsulte em: https://www.4devs.com.br/validador_cpf\n");
    }
    else {
        printf("Cpf inexistente...\n");
    }

}
