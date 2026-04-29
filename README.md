#include <stdio.h>

/* Définition de la structure Heure
   Elle contient heures (hh), minutes (mm) et secondes (ss) */
typedef struct {
    int h;
    int m;
    int s;
} Heure;

/* 1. Convertir une heure en secondes
   Formule : h*3600 + m*60 + s */
int HeureEnSecondes(Heure t) {
    return t.h * 3600 + t.m * 60 + t.s;
}

/* 2. Convertir des secondes en heure
   On utilise la division et le modulo */
Heure SecondesEnHeure(int sec) {
    Heure t;

   h = s / 3600;          // nombre d'heures
    s = s % 3600;

  m = s / 60;            // nombre de minutes
    sec = s % 60;            // reste = secondes

  return t;
}

/* 3. Addition de deux heures
   On convertit en secondes puis on reconvertit */
Heure AdditionHeure(Heure t1, Heure t2) {
    int total = HeureEnSecondes(t1) + HeureEnSecondes(t2);
    return SecondesEnHeure(total);
}

/* 4. Différence entre deux heures
   On calcule la valeur absolue de la différence */
Heure DifferenceHeure(Heure t1, Heure t2) {
    int sec1 = HeureEnSecondes(t1);
    int sec2 = HeureEnSecondes(t2);

  int diff;

  if (sec1 > sec2)
        diff = sec1 - sec2;
    else
        diff = sec2 - sec1;

   return SecondesEnHeure(diff);
}

/* Fonction pour afficher une heure sous format hh:mm:ss */
void AfficherHeure(Heure t) {
    printf("%02d:%02d:%02d\n", t.h, t.m, t.s);
}

int main() {
    Heure t1, t2, somme, diff;

  /* Saisie de la première heure */
    printf("Entrer la premiere heure (h m s) : ");
    scanf("%d %d %d", &t1.h, &t1.m, &t1.s);

   /* Saisie de la deuxième heure */
    printf("Entrer la deuxieme heure (h m s) : ");
    scanf("%d %d %d", &t2.h, &t2.m, &t2.s);

  /* Affichage des heures */
    printf("\nHeure 1 : ");
    AfficherHeure(t1);

   printf("Heure 2 : ");
    AfficherHeure(t2);

  /* Conversion en secondes */
    printf("\nHeure 1 en secondes : %d\n", HeureEnSecondes(t1));
    printf("Heure 2 en secondes : %d\n", HeureEnSecondes(t2));

   /* Addition */
    somme = AdditionHeure(t1, t2);
    printf("\nSomme : ");
    AfficherHeure(somme);

   /* Différence */
    diff = DifferenceHeure(t1, t2);
    printf("Difference : ");
    AfficherHeure(diff);

  return 0;
}
