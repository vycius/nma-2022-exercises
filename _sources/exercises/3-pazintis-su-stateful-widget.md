# 2. Pažintis su StatefulWidget

Kaip keleiviui paspaudus ant tab'o pakeisti ekraną? Tam reikia, kad Widget'as galėtų pats save keisti.

Flutter turi dviejų tipų Widgetus:

- [StatelessWidget](https://api.flutter.dev/flutter/widgets/StatelessWidget-class.html) - tokie kurie neturi vidinio
  stat'o ir po sukūrimo nesikeičia.
- [StatefulWidget](https://api.flutter.dev/flutter/widgets/StatefulWidget-class.html) - tokie, kurie po sukūrimo gali
  save keisti (turi stat'ą).

## Užduotis

Pakeiskite MainScreen tipą iš StatelessWidget į StatefulWidget bei pasirūpinkite, kad
[BottomNavigationBar](https://api.flutter.dev/flutter/material/BottomNavigationBar-class.html) galėtų pakeisti tab'ą
(atributas: _currentIndex_).

## Pavyzdinis rezultatas

```{figure} /images/exercises/3-pazintis-su-stateful-widget.gif

Ekrano pasikeitimas paspaudus ant tab'o. 
```

## Naudinga informacija

- Adding interactivity to your Flutter app https://flutter.dev/docs/development/ui/interactive

## Platesnė informacija

- How Stateful Widgets Are Used Best - Flutter Widgets 101 https://www.youtube.com/watch?v=AqCMFXEmf3w