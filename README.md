Pierwszy łańcuch korzysta z docker scouta
Na wcześniejszych etapach obraz jest przesyłany do dockerhuba

Docker scout skanuje obraz w poszukiwaniu zagrożeń sklasyfikowanych jako critical i high co zapewnia nam only-severities
W przypadku znalezienia zagrożeń o takiej klasyfikacji łańcuch kończy pracę z exit kodem 1
W przeciwnym razie obraz zostaje przesłany do ghcr.io (github image registry)

W ramach wyzwania stworzyłem też drugi łańcuch w którym używam trivy zamiast docker scouta

Działa na podobnej zasadzie, tylko tutaj korzystam z komend run, za pomocą których instaluje trivy, a następnie skanuje obraz, jeśli nie ma zagrożeń 
o klasyfikacji high lub critical obraz jest pushowany do ghcr.io

Łańcuch został utworzony na podstawie przykładu z laboratorium 9 dlatego w dockerhubie korzystam z repo example

Uruchamić można z poziomu githuba lub za pomocą narzędzia gh w shellu używając polecenia w katalogu z zainicjowanym repo
```
gh workflow run
```
po czym wybrać jeden z plików 

![image](https://github.com/patryczeko/zadanie2final/assets/106553021/ffb8b5f9-c5e6-4c35-b0fb-3bbeb6afc87f)

![image](https://github.com/patryczeko/zadanie2ultimate/assets/106553021/4e9676d8-c6eb-4043-a93c-dd7b6129c410)

![image](https://github.com/patryczeko/zadanie2ultimate/assets/106553021/b2d6fcb4-31a8-4dc6-84b6-24fa871fc2ef)








