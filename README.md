# Tagowanie commitów w gicie
***
Tagowanie commitów umożliwia łatwe wersjonowanie oraz dostęp do wersji oprogramowania. Można wersjonować całe repozytorium jak również pojedyńcze pliki lub foldery. \
Wersjonując za pomocą tagów każda nowa wersja nie będzie się wiązała z kolejnym folderem, ale będzie kolejnym commitem w historii repozytorium, do którego będzie można zawsze łatwo wrócić. \
Jeśli commity są otagowane to można się do nich dostać nie tylko za pomocą id commita np. \
```7ec8a4422941d8aaf706494d1e2b6b3f33d4a1ef``` \
ale również za pomocą taga, np:\
```mój_plik@1.2.5```\
Po użyciu komendy ```git log``` można zobaczyć wszystkie commity wraz z flagami. \

mój_plik użyty powyżej może być też katalogiem albo nazwą projektu (co jest lepszą praktyką niż tagowanie bezpośrednio skryptów,cjeśli w repozytoium jest więcej niż jeden plik o takiej samej nazwie (np. test.sh albo Dockerfile). 

### Otagowanie pliku nadając mu wersjonowanie
Tworzę sobie sobie jakiś folder "plik": \
``` touch plik```\
Dodaję go:\
```git add plik```\
Commituję:\
```git commit -m "Moja pierwsza wersja"```\
Taguję:\
```git tag plik@0.0.1```\
Pushuję:\
```git push```\
Pushuję tagi:\
```git push --tags```\
Od teraz na repozytorium w zakładce /tags znajduje się mój tag. \
Mała uwaga: można sobie automatycznie ustawić w .gitconfig żeby tagi pushowały się zawsze przy komendzie ```git push``` żeby nie trzeba było używać \
```git push --tags```\
Komenda: \
```git config --global push.followTags true```\
***
### Sprawdzanie jakie są tagi były tworzone w repozytorium do tej pory?
Mogę sobie zobaczyć listę tagów jakie były do tej pory:\
```git tag```\
Lista dostępna jest też w repo na github, np. tutaj: https://github.com/muzic194/version-controll-using-commit-tag/tags
Jeśli chcę zobaczyć jakie do tej pory były wersję dla mojego pliku nad jakim pracuję, żeby wiedzieć jaką mu nadać to można użyć grep: \
```git tag | grep plik```.\
albo: \
```git show plik```\
***

### Chcę zobaczyć jak wyglądał mój plik w starszej wersji, np.v0.0.2
Chcę zobaczyć zawartość  pliku plik.py w wersji 0.0.2:\
```git show plik@0.0.2:plik.py```\
Mogę się dostać do commita z tą wersją poprzez:\
```git show plik@0.0.2```\
Jeśli chcę przywrócić starą wersję bo nowa nie działa i nie wiem jak naprawić: \
```git show plik@0.0.2:plik.py > plik.py```\
Oraz sobie pracować na starej wersji repozytorium kiedy była właśnie ta wersja: \
```git checkout plik@0.0.2```\
***
###### Dodałam zły tag, chcę usunąć i zrobić nowy
```git -d tag -d nazwa_folderu@x.y.z```\
***
