Erlang:
Rekurz�v f�ggv�nyh�v�ssal val�s�tom meg az automat�t.
Egy f�ggv�ny egy szab�lynak felel meg.
A bemeneti stringet egy list�val �br�zolom, melybol az elso elemet a szab�lyalkalmaz�s ut�n elhagyom, a k�vetkez� f�ggv�nyt a lista v�g�vel hivom. 
Egy ilyen automat�t funkcion�lis nyelvekben viszonylag k�nnyen meg lehet val�s�tani.
Neh�zs�get az elso szab�ly alkalmaz�sa okozta, hiszen az elso szab�lyt�l f�gg, hogy a lista elso karakter�t is ki�rjuk-e elfogad�s eset�n. Emiatt az S f�ggv�ny �ltal visszaadott list�t k�l�n elmentem egy v�ltoz�ba.

Java (kezdo):
Legfobb neh�zs�get az okozta, hogy a k�zelm�ltban ink�bb funkcion�lis nyelveket haszn�ltam �s az objektumorient�lt szeml�let h�tt�rbe szorult. 
A BSc elso f�l�v�ben tanultak segits�g�vel egy felsorol� felhaszn�l�s�val implement�ltam a string olvas�s�t. Az automat�t egy oszt�ly val�s�tja meg, mely a felsorol� oszt�lyt haszn�lva lek�rdezheti a bemenet k�vetkezo elem�t.
A program a bemenet minden karakter�re alkalmazza a soron k�vetkezo szab�lyt. A szab�lyok itt helyes input eset�n megadj�k a k�vetkezo alkalmazand� szab�lyt.