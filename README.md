przedmioty= {}

while True:
  print("\nCo chcesz zrobić?\n1. Dodaj przedmiot.\n2. Dodaj ocene.\n3. Oblicz srednia dla danego przedmiotu\n4. Oblicz srednia koncowa.\n5. Wyswietl przedmioty wraz z ocenami\n")
  wybor = int(input())
  if wybor==1:
    nazwa=str(input("Podaj nazwe przedmiotu: "))
    if nazwa not in przedmioty:
      przedmioty[nazwa] = []
      print("Dodano",nazwa,"do bazy")
    else:
      print("Podany przedmiot istnieje w bazie!")

  elif wybor==2:
    nazwa=str(input("Podaj nazwe przedmiotu, dla ktorego chcesz dodac ocene: "))
    if nazwa in przedmioty:
      ocena = float(input("Podaj ocene: "))
      przedmioty[nazwa].append(ocena)
      print("Ocena zostala dodana pomyslnie")
    else:
      print("Nie ma takiego przedmiotu w bazie!")
      
  elif wybor==3:
    nazwa=str(input("Podaj nazwe przedmiotu: "))
    if nazwa in przedmioty:
      suma = float(sum(przedmioty[nazwa]))
      srednia = float(round(suma/len(przedmioty[nazwa]), 2))
      print("Srednia z",nazwa,"to:",srednia)

  elif wybor==4:
    dlugosc=float(0)
    sumy = float(0) 
    i=int(0)
    for i in przedmioty:
      sumy += sum(przedmioty[i])
      dlugosc += len(przedmioty[i])
      print(i)
    koncowa = float(sumy/dlugosc)
    print("Srednia koncowa to",koncowa)
  elif wybor==5:
    print(przedmioty)
