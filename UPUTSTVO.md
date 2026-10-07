# Tikva — uputstvo

Tikva je web aplikacija (PWA) za pripremu za ski sezonu: kalendar treninga, vježbe s videom, korekcija grešaka.
Radi i bez interneta i instalira se na telefon kao obična aplikacija.

**Adresa:** https://durmitor25.github.io/tikva/
**QR kod:** `tikva-qr.png` u korijenu projekta (izvan `pwa/`, ne ide na git) — vodi na istu adresu.

Folder `pwa/` je cijela aplikacija — svi fajlovi moraju biti zajedno:
`index.html` (omotač + dugme za instalaciju) · `app.html` (aplikacija) · `manifest.json` · `sw.js` (rad bez interneta) · `icon-192.png` · `icon-512.png` · `icon-512-maskable.png` · `UPUTSTVO.md`

---

## 1. Instalacija na telefon

### Android (Chrome)
1. Otvori adresu ili skeniraj QR kod.
2. Na vrhu se pojavi kartica **Tikva → Instaliraj** — jedan dodir i potvrdi.
3. Ako kartice nema (zatvorena je s ×, ili Chrome još provjerava stranicu): meni **⋮ → Instaliraj aplikaciju**.

### iPhone (Safari)
Apple ne dozvoljava dugme za instalaciju — ide ručno:
1. Otvori adresu u **Safariju**.
2. **Dijeli** (kvadrat sa strelicom gore; na novijim iOS-ima možda prvo **⋯** pored adrese).
3. Skrolaj nadolje → **Dodaj na početni ekran** → **Dodaj**.

Ako „Dodaj na početni ekran” nema:
- link je otvoren unutar druge aplikacije (WhatsApp, Instagram…) → **Otvori u Safariju**;
- uključen je privatni način → otvori u običnom tabu;
- opcija je skrivena → na dnu liste **Uredi radnje** i dodaj je.

### Podaci i backup
- Podaci (odrađeni treninzi, km, linkovi, izmjene plana) čuvaju se **samo na tom telefonu, za tu adresu**. Nova adresa ili novi telefon = aplikacija kreće prazna.
- Prije promjene telefona ili adrese: u aplikaciji **izvoz backupa** → na novom mjestu **uvoz**.
- Stari backupi (prije preimenovanja u Tikva) se normalno uvoze — aplikacija sama prebaci stare podatke.

---

## 2. Objava nove verzije (GitHub Pages)

Git repo je u `pwa/` folderu, remote je `https://github.com/durmitor25/tikva.git`, GitHub Pages servira granu `main`.

U VS Code-u (Source Control, `Ctrl+Shift+G`):
1. Upiši poruku → **Commit** (ako pita za sve izmjene → **Yes**).
2. **Sync Changes** / **Push**.
3. Za 1–10 minuta nova verzija je na adresi (napredak: repo → tab **Actions**).

Telefon povuče novu verziju sam pri sljedećem otvaranju; ako vidi staru — zatvori aplikaciju potpuno i otvori ponovo.

**Pravilo:** kad se mijenja `app.html` ili `index.html`, u `sw.js` se podiže verzija keša (`tikva-v29` → `tikva-v30` …), inače telefon može držati staru verziju.

Izvor dizajna je `Tikva.dc.html` u korijenu projekta — izmjene plana se upisuju i tamo i u `pwa/app.html`, da ostanu usklađeni.

---

## 3. Plan treninga

19 sedmica od 3. augusta do 13. decembra 2026, prvi spust 14. decembra.
Trening ponedjeljak (A), srijeda (B), petak (C); subota tura; nedjelja odmor.

| Faza | Sedmice | Cilj |
|---|---|---|
| 1 | 1–7 | Kod kuće: zglob, core, adukcija |
| 2 | 8–15 | Snaga u teretani |
| 3 | 16–19 | Eksplozivnost, skijaška izdržljivost, taper |

Od sedmice 10 (5. oktobar) A, B i C su različiti:

| Sedmica | Šta |
|---|---|
| 10 | Uvodna: novi raspored, 3 × 8 |
| 11 | Teže: goblet i RDL 4 × 6, prvi skok-čučnjevi |
| 12 | **Oporavak:** 2 serije, bez tega |
| 13 | Sporo spuštanje (4 s), deficit RDL, bočni skokovi, suitcase carry |
| 14 | Teško 3 × 4, petkom prvi intervali (15 s / 45 s) |
| 15 | Najteže u fazi (3 × 3); lateral bounds **samo ako zglob prođe test** |
| 16 | Lakši ulaz u Fazu 3, teški goblet 2 × 3–4 za održavanje snage |
| 17–18 | Najteži dio: skokovi preko kutije, krug zamora, brutalni finiš |
| 19 | **Taper:** pola volumena, zadnji teži trening u srijedu |

- **Pon (A):** skokovi + snaga nogu + klizna adukcija.
- **Sri (B):** snaga + tibialis + core (Pallof, Copenhagen, carry).
- **Pet (C):** jednonožna snaga (leg press) + adukcija + intervali / zamor.

**Test lijevog zgloba (prije sedmice 15):** 30 s na lijevoj nozi zatvorenih očiju, i koljeno dodiruje zid s prstima 7,5 cm od zida.

**Vikend kardio:** Faza 2 — duža tura u zoni 2 ili hill fartlek (u 12. samo lagano); Faza 3 — tempo intervali 4 × 5 min ili duža tura.

**U sezoni (od 14. decembra):** 1–2 kratka treninga sedmično (goblet, Pallof, Copenhagen, balans, zglob), najmanje 48 h prije skijanja.

### Lakši treninzi — A2, B2, C2
Svaki trening ima lakšu verziju. Po defaultu ide A/B/C; lakša ide **sama dan poslije ture**:

| Jučer | Noge | Ruke |
|---|---|---|
| Hiking, trčanje, fartlek, tempo, biciklo 40+ km | lakše | normalno |
| Penjanje | lakše | lakše |
| Ništa, ili tura prekjuče (npr. subota) | pun trening | pun trening |

- **Noge lakše:** bez skokova, listova, tibialisa i vježbi zamora; goblet, RDL, wall sit i leg press serija manje. Adukcija, core i mobilnost ostaju.
- **Ruke lakše (poslije penjanja):** bez farmer walka, suitcase carryja i bacanja medicinke; Pallof i chop serija manje.
- Da bi radilo, jučerašnji dan mora biti **označen kao odrađen s pravom vrstom** (npr. Penjanje, Hiking).
- Na ekranu treninga: **Vrati puni trening** / **Primijeni lakši**.
- U tabu **Vježbe** biraš A · A2 · B · B2 · C · C2. Dok A2 ne mijenjaš, pravi se sam od A; kad ga urediš, ostaje tvoja verzija (**Vrati original** ga vraća na automatski).
- Izmjene u tabu Vježbe imaju prednost nad planom iz koda — ako nova sedmica izgleda „po starom”, za nju klikni **Vrati original**.

YouTube linkovi su vezani za vježbu, ne za poziciju u treningu — ostaju i kad se plan mijenja.

---

## 4. APK (bez browsera)

Pravi Android `.apk` koji se šalje kao fajl:
1. https://www.pwabuilder.com → zalijepi adresu aplikacije → **Start**.
2. **Package for stores → Android**:
   - Package ID: `com.tikva.skiprep`
   - App name: `Tikva`
   - **Signing key: Create new** — obavezno sačuvaj `signing.keystore` i lozinke (bez njih nema update-a iste aplikacije).
3. **Download** → `app-release-signed.apk` (i `.aab` samo za Google Play).
4. Pošalji `.apk` na telefon → otvori → dozvoli „Instaliraj nepoznate aplikacije” → Instaliraj.

Sadržaj se i dalje ažurira sam s GitHub Pages-a — novi APK ne treba.

APK može pri pokretanju pokazati traku s adresom dok domen nije verificiran (`assetlinks.json` iz PWABuilder zipa mora biti na `https://durmitor25.github.io/.well-known/assetlinks.json`, tj. u repou `durmitor25.github.io`). Za ličnu upotrebu traka ne smeta.

Google Play: developerski račun (jednokratno 25 $) + Googleova provjera aplikacije.
