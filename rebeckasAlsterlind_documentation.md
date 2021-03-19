Skapar ett repo i github. Bjuder in de andra via invite collaborators.
Klonar ner repot lokalt:
cd  (dra in mappen jag vill klona repot till)
git clone länk-till-repo
cd (drar in nedklonade mappen till terminalen för att hoppa in i den mappen)
ls (för att se att jag står i rätt mapp)
För att öppna i vsc: 
code . 

git checkout -b feature-rebeckaAlsterlind (skapa egen branch och hoppa in i den)
git add . (lägga till (alla) nya filer/ändringar)
git commit -m “msg”  (spara ändringarna i ett meddelande)
git push -u origin feature-rebeckaAlsterlind (för att pusha upp till remote och bestämma vart det i fortsättningen ska pushas (nästa gång kan jag bara skriva git push).

En person i gruppen skapade branch “staging” som vi lokalt kan merga till från våra egna feature-branches för att resten av gruppen sedan ska få tillgång till det som en gruppmedlem har mergat innan det att det mergas med main-branchen. 

En person i gruppen lägger till index.html + style.css i staging:
touch fil-man-vill-lägga-till.filändelse (för att skapa ny fil direkt i terminalen) 

git fetch –all (för att se alla branches som finns i repot)
git branch (kollar vikla branches som finns i repot)
Såg inte staging bland brancher men nedanför de listade brancherna så fanns den med som “new branch”.  
Git checkout -b staging (skapade egen branch med samma namn)
git pull origin staging (då hämtades det från remote staging branch till lokal staging branch och därefter fungerade de som en och samma branch. 
git checkout staging (hoppa in i staging-branchen)

git pull (hämta det senaste från staging)
git checkout feature-rebeckaAlsterlind (hoppa in i min branch)
git merge staging (hämtar in det nya från staging till min branch)
git status (kollar så allt är up to date/working tree clean)
Gör ändringar i min branch.
git status (kollar om nya filer/ändringar behöver läggas till alt commitas/är redo att pushas)
git add . (lägger till ändringar)
git commit -m “msg” 
git push (pushar upp till github)
Efter fler ändringar skickar jag till staging: 
git checkout staging 
git pull (ifall det finns nytt i remote staging)
git merge feature-rebeckaAlsterlind
Inga konflikter än så länge.

Jag gjorde ändringar i css dokumentet och som jag inte commitat men som jag lagt till i staging area (git add .) och det visade sig att det inte riktigt fungerade så bra så jag gjorde en restore för att komma tillbaka till senast commitade läget: 
Git restore style.css

Står i staging: 
git pull (hämtar senaste)
git merge feature-rebeckaAlsterlind (skicka nytt från egen branch till staging)
Fick conflikter i css. Accepterade några current changes och några incoming changes. 
git add . 
git commit -m “msg”
git push 

Testar revert: 
Ändrar bg color i css dokument i feature-branch. 
git add .
git commit “msg”
git push 
git log (för att hitta commit att gå tillbaka till)
Kopierar sha-nummer
git revert sha-nummer
i (gå in i edit mode och skriva meddelande)
esc
:q! (för att gå ur edit mode)
git log (se vad jag ändrat)
git push (pusha upp till github igen)

Däremellan gör jag en massa add ., commit, push, add ., commit, push, pull, merge, lösa konflikter, add ., commit push etc.

