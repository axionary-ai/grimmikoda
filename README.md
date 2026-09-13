# Grimmikoda — teemameigi näidisleht

Ühelehe-veebisait teema- ja efektimeigi artistile (Halloween, SFX, fantaasia, UV, näomaalingud).
Eesti ja inglise keel, hinnakiri koos kestustega, vabade aegade kalender ja broneerimisvorm.

**Kõik brändiandmed on kohatäited.** Enne päris kasutust asenda:

| Mida | Kus |
|---|---|
| Brändinimi `Grimmikoda` | `index.html` — `<title>` ja `.brand` link |
| Telefon, e-post, Instagram | `index.html` — jaluse „Kontakt" veerg |
| E-post, kuhu broneeringud saadetakse | `index.html` — `var CONTACT_EMAIL` |
| Stuudio aadress (praegu „Kalamaja") | `index.html` — jaluse „Asukohad" veerg ja broneerimisvormi valik |
| Fotod ja videod | kaust `media/` — praegu vabakasutusega referentsmaterjal Pexelsist |
| Ülemine „näidisleht" riba | `index.html` — `<div class="demo">` (kustuta see plokk) |

## Broneeritud ajad

`bookings.json` hoiab hõivatud aegu. Kalender tõmbab need ajad maha ja arvestab ka kestusega —
90-minutiline broneering kell 13:00 blokeerib ka 13:30 ja 14:00 alguse.

```json
[{ "date": "2026-10-31", "time": "13:00", "mins": 120 }]
```

Praegused kirjed on **näidised** — kustuta need ja lisa oma broneeringud. Fail uueneb lehel kohe,
kui muudatuse üles laed.

## Lahtiolekuajad

`index.html` sees `DAY_HOURS` (0 = pühapäev). Praegu: K–R 11:00–21:00, L 10:00–17:00,
P–T kokkuleppel (katkendjoonega nupud). Viimane algusaeg arvutatakse nii, et teenus jõuab
enne sulgemist lõppeda.

## Päris broneerimissüsteem

Staatilisel hostingul pole andmebaasi, seega vorm avab täidetud e-kirja. Kui võtad kasutusele
Fresha, Calendly või muu süsteemi, pane selle aadress `index.html` sees muutujasse
`var BOOKING_URL = ""` — vormi kohale ilmub nupp, mis viib sinna.

## Hinnad

Hinnad ja kestused on ühes kohas: `SERVICES` massiiv `index.html` sees. Sealt joonistatakse
nii hinnakiri kui ka broneerimisvormi valikud ja hinnaarvestus — muuda ainult seda massiivi.

## Hostimine

Puhas staatiline sait, ehitust pole vaja. Piisab failide üleslaadimisest:
`index.html`, `bookings.json` ja kaust `media/`.
