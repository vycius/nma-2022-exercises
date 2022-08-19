# 5. Maršrutų sąrašas

Kaip sužinoti kokių maršrutų autobusai egzistuoja?

## Užduotis

RoutesTab atvaizduok visus mieste egzistuojančius maršrutus. Duomenis maršrutų atvaizdavimui gali gauti iš
`DatabaseService` funkcijos `getAllRoutes`. Taip pat paspaudus ant konkretaus maršruto pridėk perėjimą į maršruto
ekraną (RouteScreen).

Tau gali padėti `NearbyStopsTab` tabo pavyzdys bei `AppFutureBuilder` (atitikmuo
[FutureBuilder](https://api.flutter.dev/flutter/widgets/FutureBuilder-class.html)) ir
[ListView](https://api.flutter.dev/flutter/widgets/ListView-class.html) widget'ai.

## Pavyzdinis rezultatas

```{figure} /images/exercises/5-marsrutu-sarasas.png

Maršrutų sąrašo pavyzdys
```

## Naudinga informacija

- FutureBuilder https://api.flutter.dev/flutter/widgets/FutureBuilder-class.html
- ListView https://api.flutter.dev/flutter/widgets/ListView-class.html
- GTFS routes.txt https://developers.google.com/transit/gtfs/reference#routestxt
