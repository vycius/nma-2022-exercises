# „Flutter“ dirbtuvės

Ar kada susimastei iš kur atsiranda viešojo transporto maršrutai, atvykimo laikai, stotelės Trafi, Google Maps,
Apple Maps ir kitose kelionių planavimo priemonėse? „Flutter“ dirbtuvių metu sieksime sužinoti apie viešojo
transporto duomenų standartais, susipažinti su „Flutter“ ir išmokti kurti skirtingose platfomose veikiančias programas.

Kurso metu tobulinsime viešojo transporto programėlę „BUS“.

```{figure} /images/bus-app.png
---
width: 250
---

Programėlės BUS pavyzdys
```

## Viešojo transporto duomenys

### Statiniai duomenys (GTFS)

Statiniai viešojo transporto duomenys yra prieinami [GTFS](https://developers.google.com/transit/gtfs) (_General
Transit Feed
Specification_) standartu, kuris yra ypač plačiai
naudojamas ir yra skirtas teikti viešojo transporto statinę informaciją.

#### GTFS duomenų rinkiniai

GTFS duomenų rinkinys būna suspaustas į `.zip` failą susidedantį iš keleto `.csv` failų. Kiekvieną
iš šių failų gali atsisiųsti ir į savo kompiuterį bei panagrinėti detaliau.

```{table} GTFS duomenų rinkinių pavyzdžiai Lietuvoje
:name: gtfs-files
| Apimtis                                                | GTFS                                                            |
|--------------------------------------------------------|-----------------------------------------------------------------|
| [Vilniaus m. sav.](https://www.stops.lt/vilnius/)      | [GTFS](https://www.stops.lt/vilnius/vilnius/gtfs.zip)           |
| [Kauno m. sav.](https://www.stops.lt/kaunas/)          | [GTFS](https://www.stops.lt/kaunas/kaunas/gtfs.zip)             |
| [Klaipėdos m. sav.](https://www.stops.lt/klaipeda/)    | [GTFS](https://www.stops.lt/klaipeda/klaipeda/gtfs.zip)         |
| [Panevėžio m. sav.](https://www.stops.lt/panevezys/)   | [GTFS](https://www.stops.lt/panevezys/panevezys/gtfs.zip)       |
| [Druskininkų sav.](https://www.stops.lt/druskininkai/) | [GTFS](https://www.stops.lt/druskininkai/druskininkai/gtfs.zip) |
| [Tolimasis susiekimas](https://www.visimarsrutai.lt/)  | [GTFS](https://www.visimarsrutai.lt/gtfs/LTSAR.zip)             |
```

#### Struktūra

Kiekviename GTFS duomenų rinkinio faile saugoma informacija apie konkretų transporto sistemos elementą pvz.,
stoteles ([_stops.txt_](https://developers.google.com/transit/gtfs/reference#stopstxt)), maršrutus
([_routes.txt_](https://developers.google.com/transit/gtfs/reference#routestxt)),
reisus ([_trips.txt_](https://developers.google.com/transit/gtfs/reference#tripstxt)), atvykimo bei išvykimo laikus
([_stop_times.txt_](https://developers.google.com/transit/gtfs/reference#stop_timestxt))ir t.t. Detalų failų sąrašą
ir dokumentaciją rasite [čia](https://developers.google.com/transit/gtfs/reference).

Taip pat svarbu suvokti ryšius tarp GTFS duomenų rinkinio failų.

```{figure} /images/gtfs-files-relationship.png
:name: gtfs-files-relationships

Ryšiai tarp GTFS duomenų rinkinio failų. [Šaltinis](https://github.com/christianroman/df-gtfs)
```

### Dinaminai duomenys (GTFS Realtime)

Statiniai duomenys keleiviui suteikia bazinę informaciją, tad vien jų neužtenka, nes transporto priemonės genda,
miestuose vyksta renginiai, gatvėse atsiranda kamščiai ar įvyksta avarijos. Siekiant reaguoti į trumpalaikiais pokyčius
transporto sistemoje būtini dinaminiai duomenys. Dažnai šių duomenų šaltinių gali tapti viešajame transporte įrengta GPS
įranga, keleivių skaičiavimo įranga, eismo stebėjimo sistemos.

```{figure} /images/google-maps-dynamic-information.jpg
:name: google-maps-dynamic-information

Dinaminiai viešojo transporto duomenys Google Maps. [Šaltinis](https://www.techspot.com/news/76700-google-maps-adds-new-commute-tab-music-streaming.html)
```

#### GTFS Realtime

[GTFS Realtime](https://developers.google.com/transit/gtfs-realtime) (_General Transit Feed Specification Realtime_) yra
de facto standartinis atvirų duomenų formatas
skirtas dinaminei viešojo transporto informacijai perduoti. Šis formatas papildo papildo GTFS teikiamą statinę
informaciją.

#### Struktūra

GTFS Realtime duomenys yra prieinami
[Protobuf](https://developers.google.com/transit/gtfs-realtime/gtfs-realtime-proto).

Šio formato taip paprastai, kaip GTFS savo kompiuteryje panagrinėti nepavyks, nes duomenų formatas nėra suprantamas
žmogui (pvz., priešingai nei JSON). Paprasčiausias būdas pasižaisti su šiuo formatu yra naudojant
https://transport.data.gouv.fr/validation?type=gtfs-rt ir suvedus GTFS ir GTFS-RT (GTFS Realtime nuorodas)
pvz., https://www.stops.lt/vilnius/vilnius/gtfs.zip ir https://www.stops.lt/vilnius/gtfs_realtime.pb Tuomet _Decoded
GTFS-RT feed_ dalyje
matysite kokie duomenys yra gražinami.

```{table} GTFS Realtime pavyzdžiai Lietuvoje
:name: gtfs-realtime-files
| Apimtis                                                | GTFS Realtime                                                    |
|--------------------------------------------------------|------------------------------------------------------------------|
| [Vilniaus m. sav.](https://www.stops.lt/vilnius/)      | [GTFS Realtime](https://www.stops.lt/vilnius/gtfs_realtime.pb)   |
| [Kauno m. sav.](https://www.stops.lt/kaunas/)          | [GTFS Realtime](https://www.stops.lt/kaunas/gtfs_realtime.pb)    |
| [Klaipėdos m. sav.](https://www.stops.lt/klaipeda/)    | [GTFS Realtime](https://www.stops.lt/klaipeda/gtfs_realtime.pb)  |
| [Panevėžio m. sav.](https://www.stops.lt/panevezys/)   | [GTFS Realtime](https://www.stops.lt/panevezys/gtfs_realtime.pb) |
```