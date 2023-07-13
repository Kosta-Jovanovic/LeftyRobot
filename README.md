# LeftyRobot
Modular rover mecanum wheel vehicle that can add different modules for different purposes 
# Zimski seminar
Projekat je rađen u Istraživačkoj stanici Petnica (01.07- 07.07.2023.), na seminaru elektronike. 
<ol></ol>
<p>Prvi dan (02.06.2023):</p>
<li>napravljen 3D model osnovnog dela robota</li> 
<li>napravljen 3D model Mecanum Wheels-a</li>  
<ol></ol>
<p>Drugi dan (03.06.2023):</p>
<li>štampanje delova pomoću 3D štampača</li>
<ol></ol>
<p>Treći dan (04.07.2023.):</p>
<li>započeta izrada aplikacije</li>
<li>rešavanje problema u vezi nedostatka bakarne šipke, koja služi za spajanje rolera sa osnovom Mecanum Wheels-a</li>
<ol></ol>
<p>Četvrti dan (05.07.2023.):</p>
<li>sklapanje Mecanum Wheels-a</li>
<li>dovršavanje aplikacije i koda za Arduino</li>
<p><li>ostala nam je šasija za isprintovati, ali zbog nefunkcionisanja 3d štampača je to trenutno neizvodljivo</li></p>
<p>Za početak smo hteli da se robot kreće uz pomoć aplikacije, a kada završimo osnovni deo robota kao i kada odredimo module koje će posedovati, napisaćemo kod za ml.</p>
<p>Kraći opis koda za Arduino:</p>
Koristili smo dve biblioteke SoftwareSerial i AccelStepper. Prvu biblioteku koristimo jer nam omogućava korišćenje serijske komunikacije na bilo kojem digitalnom pinu, u našem slučaju komunikacije putem Bluetooth modula. Dok AccelStepper biblioteka omogućava upravljanje stepper motorima. Omogućava jednostavnu kontrolu brzine i smera, podržava i ubrzanje i usporavanje motora. Digitalni pinovi 40 do 47 su odabrani jer se nalaze na skupini „Port C“ na Arduino Mega ploči. Ovi pinovi su povezani sa odgovarajućim pinovima na mikrokontroleru, što omogućuje laku upotrebu s digitalnim ulaznim/izlaznim funkcijama, a pinovi 8 i 9 su odabrani kao standardni pinovi za serijsku komunikaciju. Postavljanje maksimalne brzine motora koristi se kako bi se ograničila brzina motora i time sprečilo da robot prebrzo ide i izgubi kontrolu. „dataIn“ su svi podaci koje šalje drugi uređaj, a koje ovaj kod čita i koristi za kontrolu robota. Kada uz pomoć „dataIn“ odredimo postojeća „m“, određujemo za svako „m“ određenu funkciju, naprimer if(m==4), poziva funkciju „moveSidewaysLeft()“ koja pokreće robota da se kreće bočno ulevo. Dok kada je varijabla „m“ jednaka 12 ili 14 postoji malo više uslova za pokretanje određenih funkcija. Funkcija „moveTo()“ postavlja poziciju kju točak treba dostići, „setSpeed()“ se koristi za postavljanje brzine točkova, a ako neki točak nije dostigao dobru poziciju koristi se funkcija „runSpeedToPosition()“ kako bi povećala brzinu i približila ih ciljnoj poziciji. Poslednjih osam funkcija zapravo upravljaju kretanjem robota u različitim smerovima. Svaka funkcija određena je kombinacijom „wheelSpeed“, „-wheelSpeed“ i „0“ kako bi dobili različite smerove.
