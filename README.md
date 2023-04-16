# Ordenamiento
Métodos de ordenamiento en C++

#include <iostream>
#include <conio.h>
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <windows.h>

using namespace std;

struct are
{
	int avi,km,costo;
	struct are *sig, *ant;
};
struct are *nodo, *inicio=NULL, *fin=NULL, *aux;

void textcolor (int c)
{
    //SetConsoleTexAttribute (GetStdhandle (STD_OUT_HANDLE), c);
     SetConsoleTextAttribute (GetStdHandle (STD_OUTPUT_HANDLE),c);
}

void gotoxy (int x, int y)
{
    HANDLE hConsoleOutput;
    COORD coord;
    hConsoleOutput=GetStdHandle (STD_OUTPUT_HANDLE);
    coord.X=x;
    coord.Y=y;
    SetConsoleCursorPosition (hConsoleOutput,coord);
}

int menu()
{
    char opc[1];
    int numero;
    system("cls");
    printf("GRFOS\n");
    printf(" 1- Reservar un vuelo\n 2- mostrar la ruta\n 3- salir\n");
    printf("selecciona un numero: ");
    scanf("%S",opc);

    if(isdigit (opc[0])== true)
    {
        numero= atoi(opc);
        switch(numero)
        {
            case 1: numero=1;
            break;
            case 2: numero=2;
            break;
            case 3: numero=3;
            break;
            case 4: numero=4;
            break;
            case 5: numero=5;
            break;
            case 6: numero=6;
            break;
            default: printf("dato invalido intente de nuevo");
            system("PAUSE");
            menu();
        }
    }
    else
    {
        printf("error\n");
        system("PAUSE");
    }
    return (numero);
}

void vuelo()
{
	int a,b;
	printf("Bienvenidos al aeropuerto\n\n");

	int i;
    gotoxy(4,3);
    printf("             Rutas del avion");

    gotoxy(4,5);
    printf("1");
    gotoxy(4,6);
    printf("2");
    gotoxy(4,7);
    printf("3");
    gotoxy(4,8);
    printf("4");
    gotoxy(4,9);
    printf("5");
    gotoxy(4,10);
    printf("6");

    gotoxy(8,5);
    printf("los angeles-Guadalajara");
    gotoxy(8,6);
    printf("Monterrey-los angeles");
    gotoxy(8,7);
    printf("Toluca-las vegas");
    gotoxy(8,8);
    printf("Toluca-Monterrey");
    gotoxy(8,9);
    printf("Guadalajara-los angeles");
    gotoxy(8,10);
    printf("Ciudad de Mexico-Toluca");
    ///////////////////////////////////////////
    for(i=0;i<9;i++)
    {
        gotoxy(2,2+i);
        printf("%c",186);
    }

    for(i=0;i<7;i++)
    {
        gotoxy(6,4+i);
        printf("%c",186);
    }

    for(i=0;i<9;i++)
    {
        gotoxy(46,2+i);
        printf("%c",186);
    }
////////////////////////////////////////////////////
    for(i=0;i<45;i++)
    {
        gotoxy(2+i,4);
        printf("%c",205);
    }
    for(i=0;i<45;i++)
    {
        gotoxy(2+i,11);
        printf("%c",205);
    }

    for(i=0;i<45;i++)
    {
        gotoxy(2+i,2);
        printf("%c",205);
    }
    gotoxy(1,12);
    registro:
	printf("Hola seleccione un numero para su destino: ");
	scanf("%d",&a);

    if(a==1)
    {
        printf(" costo: 2443\n distancia: 2411 km\n tiempo: 1 dia 2 horas\n\n");
        printf("\n");
    }
    else
    if(a==2)
    {
        printf(" costo: 2443\n distancia: 2411 km\n tiempo: 1 dia 2 horas\n\n");
        printf("\n");
    }
    else
    if(a==3)
    {
        printf(" costo: 2443\n distancia: 2411 km\n tiempo: 1 dia 2 horas\n\n");
        printf("\n");
    }
    else
    if(a==4)
    {
        printf(" costo: 2443\n distancia: 2411 km\n tiempo: 1 dia 2 horas\n\n");
        printf("\n");
    }
    else
    if(a==5)
    {
        printf(" costo: 2443\n distancia: 2411 km\n tiempo: 1 dia 2 horas\n\n");
        printf("\n");
    }
    else
    if(a==6)
    {
        printf(" costo: 2443\n distancia: 2411 km\n tiempo: 1 dia 2 horas\n\n");
        printf("\n");
    }
    else
    if(a<1 || a>7)
    {
        printf("numero incorrecto");
        goto registro;

    }

    if(inicio==NULL)
    {
        nodo=new(struct are);
        nodo->avi=a;
        nodo->ant=NULL;
        nodo->sig=NULL;
        inicio=nodo;
        fin=nodo;
    }
    else
    {
        nodo=new(struct are);
        nodo->avi=a;
        nodo->sig=NULL;
        nodo->ant=fin;
        fin->sig=nodo;
        fin=nodo;
    }

    printf("quiere reservar otro vuelo: \n");
    printf("1- si 2- no ");
    scanf("%d",&b);
    if(b==1)
    {
        if(nodo->avi)
        goto registro;
    }
    getch();
}

void ruta()
{
    int i;
    aux=inicio;

    gotoxy(14,3);
    printf("V");
    gotoxy(14,7);
    printf("A");
    gotoxy(20,5);
    printf("M");
    gotoxy(20,9);
    printf("T");
    gotoxy(18,11);
    printf("G");
    gotoxy(22,11);
    printf("CM");
    getch();

    otra:
        if(aux->avi==1)
        {
            for(i=0; i<4; i++)
            {
                gotoxy(14,11-i);
                printf("%c",46);
            }
            for(i=0; i<3; i++)
            {
                gotoxy(14+i,11);
                printf("%c",46);
            }
            getch();
        }
        else
        if(aux->avi==2)
        {
            for(i=0; i<2; i++)
            {
                gotoxy(20,3+i);
                printf("%c",46);
            }
            for(i=0; i<5; i++)
            {
                gotoxy(20-i,3);
                printf("%c",46);
            }
            getch();
        }
        else
        if(aux->avi==3)
        {
            for(i=0; i<5; i++)
            {
                gotoxy(19-i,8-i);
                printf("%c",46);
            }
            getch();
        }
        else
        if(aux->avi==4)
        {
            for(i=0; i<2; i++)
            {
                gotoxy(20,6+i);
                printf("%c",46);
            }
            getch();
        }
        else
        if(aux->avi==5)
        {
            for(i=0; i<4; i++)
            {
                gotoxy(14,11-i);
                printf("%c",46);
            }
            for(i=0; i<3; i++)
            {
                gotoxy(14+i,11);
                printf("%c",46);
            }
            getch();
        }
        else
        if(aux->avi==6)
        {
            for(i=0; i<3; i++)
            {
                gotoxy(19+i,11);
                printf("%c",46);
            }
            getch();
        }
        if(aux!=NULL)
        {
            aux=aux->sig;
            goto otra;
        }
        else
        {
            printf("\n\n\n");
            getch();
        }
}


int main()
{
	int numMenu;
    do
    {
        numMenu=menu();
        if(numMenu==1)
        {
            system("cls");
            vuelo();
        }
        if(numMenu==2)
        {
            system("cls");
			printf("ruta...\n\n");
            ruta();
        }
    }while(numMenu!=3);

	getch();
    return 0;
}
