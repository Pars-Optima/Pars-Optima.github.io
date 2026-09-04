# Strona aplikacji Emaus (GitHub Pages)

Statyczna strona bez budowania: `index.html`, dokumenty prawne i `assets/`.

## Publikacja

1. Repozytorium `Pars-Optima/Pars-Optima.github.io` (strona organizacji), adres
   `https://pars-optima.github.io/`. Nie włączaj Pages w repozytorium z kodem `emaus`,
   bo jego strona projektowa zajęłaby ścieżkę `/emaus/`.
2. Wrzuć zawartość tego katalogu do gałęzi `main` (plik `.nojekyll` wyłącza Jekylla,
   więc nic nie jest przetwarzane).
3. Settings → Pages → Source: „Deploy from a branch”, gałąź `main`, katalog `/ (root)`.
4. Adresy dokumentów do wpisania w Google Play Console i w aplikacji:
   `https://pars-optima.github.io/emaus/polityka-prywatnosci.html` oraz
   `https://pars-optima.github.io/emaus/regulamin.html`. Nie zmieniaj tych ścieżek po
   publikacji, bo linki lądują w sklepie.

## Układ na przyszłość

Strona główna opisuje dziś Emaus. Dokumenty prawne są per aplikacja i leżą w `emaus/`.
Gdy pojawi się kolejna aplikacja: `index.html` zamienia się w stronę wydawcy Pars Optima
z listą aplikacji, obecna treść trafia do `emaus/index.html`, a nowa aplikacja dostaje
własny katalog z własną polityką i regulaminem. Adresy dokumentów Emaus się nie zmieniają.

## Do uzupełnienia przed publikacją

- Wszystkie fragmenty `[[DO UZUPEŁNIENIA: ...]]` w `index.html`, `polityka-prywatnosci.html`
  i `regulamin.html` (e-mail, link wsparcia, administrator danych, okresy retencji).
- Dokumenty prawne są **makietami** do przekazania agentowi prawnemu
  (`prawne/HANDOFF_emaus_google_play.md`). Po otrzymaniu finalnych wersji podmień treść,
  zachowując strukturę HTML i klasę `.doc`.
- Odznaki sklepów w sekcji hero: po publikacji podmień na oficjalne badge Google Play / App Store
  z linkami do listingu.

## Zrzuty ekranu

Pliki w `assets/img/` pochodzą z aplikacji debug na telefonie (adb screencap), przycięte
bez paska statusu i nawigacji, zmniejszone do 614 px szerokości. Aby odświeżyć:

```bash
adb exec-out screencap -p > shot.png
python3 -c "from PIL import Image; im=Image.open('shot.png').crop((6,112,1234,2630)); im.resize((614,1259)).save('assets/img/NAZWA.png', optimize=True)"
```

Współrzędne przycięcia dotyczą ekranu 1240×2772 (OnePlus CPH2493).
