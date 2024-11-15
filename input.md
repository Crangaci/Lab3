
# **Sarcina** **nr.1.** **Pregătirea** **pentru** **lucru**

Am instalat MySQL , si am creat o baza de date pentru aplicatia mea todo-app

```CREATE DATABASE todo_app;```

Am configurat variabilele de mediu in fisierul ```.env``` ca sa ma conectez la baza de date
<img src="./4znxkl5s.png"
style="width:3.9375in;height:1.35417in" />

# **Sarcina** **nr.2.** **Crearea** **modelelor** **și** **migrațiilor**

Am creat modelul ```Category```
<img src="./ecczlx0g.png"
style="width:4.11458in;height:0.71875in"/>
<img src="./mortfwtg.png"
style="width:3.9375in;height:1.35417in" />

Am creat modelul ```Task```
<img src="./qs1fvl0j.png"
style="width:4.11458in;height:0.71875in" />
<img src="./dgeg3o33.png"
style="width:3.9375in;height:1.35417in"  />

Am creat modelul ```Tags```
<img src="./ztrxp240.png"
style="width:4.125in;height:0.71875in" />
<img src="./qjnw5lw1.png"
style="width:3.9375in;height:1.35417in"  />

Am adaugat ```\$fillable``` in ```Task```, ```Category ```si ```Tag ```ca sa se permita atribuirea in masa a datelor ```app/Models/Task.php```
<img src="./aca4evhk.png"
style="width:3.9375in;height:1.35417in"/>

```app/Models/Category.php```
<img src="./skp1cehz.png"
style="width:3.9375in;height:1.35417in" />

```app/Models/Tag.php```
<img src="./cndvnzp0.png"
style="width:3.94792in;height:1.36458in" />

Pentru ca am creat modelele si migratiile pentru toate tabelele , am rulat migrarea pentru a crea tabelele in baza de date
<img src="./iaptvuuc.png"
style="width:4.04167in;height:1.64583in" />

# **Sarcina** **nr.3.** **Relația** **dintre** **tabele**

Am creat o migrare pentru a adauga cimpul ```category_id``` in tabela ```task```
<img src="./w2cnahft.png"
style="width:3.88542in;height:0.58333in" />

Am definit structura cimpului ```category_id``` si am adaugat cheia externa pentru a face legatura cu tabela
<img src="./fqhbuuzz.png"
style="width:3.97917in;height:2.61458in" />

In modelul ```Category``` am adaugat relatia cu ```Task```
<img src="./rmzgjdxr.png"
style="width:4.01042in;height:1.78125in" />

In modelul ```Task``` am adaugat relatia cu ```Category```
<img src="./yvyvjehn.png"
style="width:3.96875in;height:1.92708in" />

Am rulat migratia , ca sa se creeze tabela ```task_tag``` in baza de date
<img src="./rppklvj1.png" style="width:4.125in;height:1.375in" />

Am definit migratia pentru ```task_tag```
<img src="./12vzgwqk.png"
style="width:4.38542in;height:2.19792in" />

Dupa ce am editat migrarea ,am rulat comanda ca sa creez tabela ```task_tag```
<img src="./bzav1r5d.png"
style="width:4.375in;height:0.67708in" />

# **Sarcina** **nr.4.** **Relația** **dintre** **modele**

Am adaugat relatia in modelul ```Category```
<img src="./qjaxxz0o.png"
style="width:4.5625in;height:2.21875in" />
**tasks()**: Metoda ```hasMany``` defineste relatia "one-to-many"
(unu-la-multe), o categorie poate avea multe sarcini

Am adaugat relatia in modelul ```Tag```
<img src="./mbja24n1.png"
style="width:4.36458in;height:2.125in" />
**tasks()**: Metoda ```belongsToMany``` defineste relatia **"Many-to-Many"**
între Tag și Task, o eticheta poate fi asociata cu multe sarcini, iar
fiecare sarcina poate avea multe etichete.

Am adaugat relatia in modelul ```Task```
<img src="./fdvsnzkt.png"
style="width:4.23958in;height:2.05208in" />
**category()**: Metoda ```belongsTo``` definesc relatia de tip
**"Many-to-One"**, asta înseamna ca fiecare sarcina va avea o categorie
asociata.

**tags()**: Metoda ```belongsToMany``` defineste relatia de tip
**"Many-to-Many"** intre Task și Tag, o sarcina poate avea multe
etichete, iar o eticheta poate fi legata de multe sarcini.

Am adaugat cimpurile corespunzatoare in ```\$fillable``` ale modelelor

Câmpul ```\$fillable``` este utilizat pentru a specifica ce cimpuri pot fi
atribuite în masa. Asta inseamna ca atunci cind creez sau actualizez o
instanta a unui model, Laravel va permite atribuirea valorilor doar
pentru câmpurile specificate în ```\$fillable.```

# **Sarcina** **nr.5.** **Crearea** **fabricilor** **si** **seed-urilor**

Am creat o fabrica pentru modelul ```Category```
<img src="./ar2teuuq.png"
style="width:4.23958in;height:0.65625in" />

```database/factories/CategoryFactory.php```
<img src="./cfrrf4j4.png"
style="width:4.125in;height:1.83333in" />

Am creat o fabrica pentru modelul ```Task```
<img src="./kseu2yos.png"
style="width:4.20833in;height:0.6875in" />

```database/factories/TaskFactory.php```
<img src="./s5kwwsdi.png"
style="width:4.21875in;height:2.125in" />

Am creat o fabrica pentru modelul ```Tag```
<img src="./0pcr44v3.png"
style="width:3.53125in;height:0.48958in" />

```database/factories/TagFactory.php ```
<img src="./v01wuhlg.png"
style="width:3.66667in;height:1.57292in" />

Am creat seed-uri pentru a popula tabelele cu date initiale pentru modelul ```Category```
<img src="./oh4fxa1i.png"
style="width:4.07292in;height:0.42708in" />

```database/seeders/CategorySeeder.php```
<img src="./xgg02a5r.png"
style="width:4.03125in;height:1.54167in" />

Am creat seed-uri pentru a popula tabelele cu date initiale pentru
modelul ```Task```
<img src="./vy5hlsew.png" 
  style="width:4.25in;height:0.45833in" />

```database/seeders/TaskSeeder.php```
<img src="./lah5flej.png"
style="width:4.10417in;height:1.53125in" />

Am creat seed-uri pentru a popula tabelele cu date initiale pentru modelul ```Tag```
<img src="./hpk5xsm5.png"
style="width:3.94792in;height:0.42708in" />

```database/seeders/TagSeeder.php```
<img src="./3fhoraox.png"
style="width:3.88542in;height:1.44792in" />

Am actulizat fisierul ```DatabaseSeeder.php``` ca sa se lanseze seed-urile
create
```database/seeders/DatabaseSeeder.php```
<img src="./ojmqpbap.png"
style="width:3.29167in;height:1.40625in" />

# **Sarcina** **nr.6.** **Lucrul** **cu** **controlere** **și**
**vizualizări**

Am deschis fisierul ```app/Http/Controllers/TaskController.php```
<img src="./ta0qxxgc.png"
style="width:3.66667in;height:2.38542in" />
<img src="./li15hbn5.png"
style="width:3.6875in;height:2.15625in" />
<img src="./u0hc3u2z.png"
style="width:3.90625in;height:2.51042in" />

**1.** **Metoda** **index**

Afiseaza lista tuturor sarcinilor, incarcind si categoriile si
etichetele asociate.

**2.** **Metoda** **show**

Afiseaza detaliile unei sarcini, incluzind categoria si etichetele
asociate.

**3.** **Metoda** **create**

Afiseaza formularul pentru crearea unei noi sarcini, cu optiuni pentru
categorie si etichete.

**4.** **Metoda** **store**

Salveaza o noua sarcina in baza de date și ataseaza etichetele
selectate.

**5.** **Metoda** **edit**

Afiseaza formularul pentru editarea unei sarcini existente, cu optiuni
pentru a modifica categoria si etichetele.

**6.** **Metoda** **update**

Actualizeaza informatiile unei sarcini si sincronizeaza etichetele
selectate.

**7.** **Metoda** **destroy**

Sterge o sarcina din baza de date.

Am deschis fisierul ```resources/views/tasks/index.blade.php```
<img src="./dbtcaddf.png"
style="width:3.85417in;height:1.66667in" />

Am deschis fisierul ```resources/views/tasks/show.blade.php```
<img src="./weijpbrh.png"
style="width:3.89583in;height:1.70833in" />

Am deschis fisierul ```resources/views/tasks/create.blade.php```
<img src="./co4wjm34.png"
style="width:4.02083in;height:2.54167in" />

Am deschis fisierul ```resources/views/tasks/edit.blade.php```
<img src="./ic5luull.png"
style="width:4.16667in;height:3.20833in" />

Am deschis fisierul ```routes/web.php```
<img src="./xaz0nqtx.png"
style="width:4.20833in;height:1.80208in" />


## **Sarcini** **suplimentare**

**1.** **Ce** **sunt** **migratiile** **si** **la** **ce** **se**
**folosesc?**

Migratiile sunt fisiere care descriu structura bazei de date (tabele,
coloane, relatii). Ele ajuta sa creezi sau sa modifici baza de date
intr-un mod organizat, usor de gestionat si reversibil.

**2.** **Ce** **sunt** **fabricile** **si** **seed-urile** **si**
**cum** **simplifica** **procesul** **de** **dezvoltare** **si**
**testare?**

Fabricile sunt un fel de "retete" care creeaza date falsificate pentru
teste, iar seed-urile sunt un set de date initiale care populeaza baza
de date la inceput. Ele economisesc timp si ajuta la testarea rapida a
aplicatiei.

**3.** **Ce** **este** **ORM?** **Care** **sunt** **diferentele**
**dintre** **pattern-urile** **DataMapper** **si** **ActiveRecord?**

ORM (Object-Relational Mapping) este un mod de a lucra cu datele din
baza de date folosind obiecte. DataMapper tine logica de business si
logica de stocare separat, in timp ce ActiveRecord combina ambele
intr-un singur obiect.

**4.** **Care** **sunt** **avantajele** **utilizarii** **unui** **ORM**
**comparativ** **cu** **interogarile** **SQL** **directe?**

ORM-urile simplifica lucrul cu baza de date, evitand scrierea de SQL
complicat. Ele sunt mai sigure (protejeaza de atacuri SQL Injection) si
mai usor de folosit, mai ales cand vrei sa schimbi baza de date.

**5.** **Ce** **sunt** **tranzactiile** **si** **de** **ce** **sunt**
**importante** **in** **lucrul** **cu** **bazele** **de** **date?**

Tranzactiile sunt un mod de a face mai multe operatiuni intr-un singur
bloc, ca sa fie toate sau niciuna. Daca ceva nu merge bine, tranzactia
se opreste si totul revine la starea initiala, pentru a proteja datele.
