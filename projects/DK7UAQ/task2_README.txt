Varga Viktor - DK7UAQ, Prognyelvek �s paradigm�k 2. hf., B�V�T�S

Java - tapasztalt, Haskell - kev�sb� tapasztalt

Minden b�v�t�sn�l a task2_bovites.png automat�t val�s�tom meg. Ez az els� feladat 
automat�j�ra �p�l, ugyanolyan float sz�mokat ismer fel, mint az (azaz pl. a t�rtr�szben nem
lehet 0 �s az eg�szr�szben is csak az els� sz�mjegy lehet), plusz az opcion�lis 
exponens tag. Az exponens tag ki�r�sakor szigor�an van el�jel. Az exponens tagban 
tal�lhat� sz�m eg�sz �s nem kezd�dhet null�val (de lehet benne nulla).

Az eredeti feladat, illetve a b�v�t�sek sor�n sz�momra a legnagyobb gondolkodnival�t az adta,
hogy hogyan egyeztessem �ssze az automat�t a float sz�mot el��ll�t� parser f�ggv�nnyel.
Az automat�t szimul�l� k�dot �nmag�ban k�nny� megval�s�tani, illetve egy float parser 
algoritmust sem neh�z �rni, de a kett� �tv�zete nem igaz�n sz�p.
Az t�nik �rtelemszer� megold�snak, ha az outputot el��ll�t� f�ggv�nyt darabokra szedj�k �s
az automata egyes �tmeneteire osztjuk le valahogy. Bence (EJULOK) Java k�dja valami ilyesmit
val�s�t meg. B�r ez a megold�s nagyon sz�p, de a karbantart�sa, meg�rt�se j�val nehezebb, mint
a t�bbi k�d� �s a float-parser specifikus k�d el�g hossz�.
Az �n k�djaimban kicsit neccesnek �rzem az outputot el��ll�t� f�ggv�ny elhelyez�s�t. N�lam
ugyanis ez a f�ggv�ny nincs sz�tszedve. A Java k�domban j�l n�z ki, hogy egy �ltal�nos automata
csomagot terjesztek ki, amiben elhelyez�sre ker�l a float outputot el��ll�t� f�ggv�ny, de
�gy �rzem, mintha maga a lesz�rmazott oszt�ly (ami tartalmazza a float specifikus dolgokat)
alig lenne kisebb, mint egy olyan oszt�ly ami csak puszt�n megval�s�tan� a feladatot mindenf�le
�ltal�noss�gra val� tekintet n�lk�l. A Haskell k�domban is hasonl�an probl�m�snak �rzem az
outputot elk�sz�t� f�ggv�nyeket, hiszen a b�v�t�s ut�n ezek �sszesen k�zel 20 sort foglalnak,
ami szerintem nem sokkal kevesebb, mint egy b�rmilyen �ltal�noss�got mell�z� megold�s.

vvinston/EJULOK, Haskell:

Futtat�s (Win):

	ghc StateMachine.hs
	StateMachine.exe
	<lehet sz�mokat �rni>

B�r nem t�lzottan �ltal�nos megval�s�t�s, de logikusan fel�p�tett. Ez�rt is k�nny� volt kib�v�teni,
kb. 20 percbe ker�lt.

vvinston/EJULOK, Java:

Bonyolult, val�sz�n�leg el�g �ltal�nos megold�s. 
T�k�letes p�ld�ja az egy-k�t soros met�dusok ir�nyzatnak, enn�l t�bb oszt�lyra sz�tszedni
val�sz�n�leg nem is lehetne a k�dot.
Az, hogy a parse-ol�s k�l�nb�z� mechanizmusaira mind egy-egy felt�tel, akci�, stb. oszt�lyt 
sz�rmaztat �rdekes, sz�p, de a b�v�t�shez sz�ks�ges volt ezeket mind �tn�znem �s kital�lnom,
hogy leg�zzam �ssze a l�tez�kb�l a k�v�nt funkcionalit�st (2 oszt�lyt m�g hozz� is adtam).
Mivel �n az eredeti feladatot is kiss� m�shogy �rtelmeztem, �gy tov�bb tartott a b�v�t�s �s 
k�r�lbel�l 90 perc alatt lett k�sz.

saj�t, Haskell:

Futtat�s (Win):

	ghc pny2.hs
	pny2.exe
	<lehet sz�mokat �rni>

A m�dos�t�s kb. 20 percbe telt.
Az �ltal�nos automata futtat� mechanizmust nem kellett m�dos�tani.
Az �j �llapotokat �s szab�lyokat kellett hozz�adni: kb. 10 sor.
A floatParser �s finalizeParsed f�ggv�nyekben n�h�ny sort kellett �t�rni.

saj�t, Java:

Futtat�s (Win):

	mkdir bin
	javac -d bin *.java fsm\*.java
	java -cp bin pny2.Pny2
	<lehet sz�mokat �rni>

Csak az inicializ�l�son �s a FloatParser.java-n kellett v�ltoztatni, az �ltal�nos automat�t 
megval�s�t� csomagon egy�ltal�n nem. Kb. 10 percbe ker�lt.
