# 7. Realaus laiko transporto priemonių pozicijos

Siekiant reaguoti į trumpalaikiais pokyčius transporto sistemoje prijunkime ir dinaminius duomenis.

## Užduotis

Pridėkite realaus laiko transporto priemonoių buvimo vietos informaciją į realaus laiko tab'ą. Ant transporto
priemonės markerio rodykite maršruto numerį, maršruto spalvą ir atvižvelkite į tai kaip pasisukusi
transporto priemonė (angl. _bearing_). Taip pat paspaudus ant transporto priemonės markerio atidarykite reiso ekraną 
(TripScreen). 

**Pastaba**: ne visos transporto priemonės turės priskirtą reisą. Taip pat GTFS Realtime modelyje `VehiclePosition` 
nebus gražinamas `route_id` idenfikatorius (reikia naudoti `trip_id`) 

## Pavyzdinis rezultatas

```{figure} /images/exercises/7-realus-laikas.gif

Realaus laiko transporto priemonių pozicijos
```

## Naudinga informacija

- GTFS Realtime: Vehicle Positions https://developers.google.com/transit/gtfs-realtime/guides/vehicle-positions
- StreamBuilder https://api.flutter.dev/flutter/widgets/StreamBuilder-class.html
- Transform https://api.flutter.dev/flutter/widgets/Transform-class.html

## Platesnė informacija

- Flutter Map https://pub.dev/packages/flutter_map
