# Tikva — kako napraviti APK (Put 1, bez instalacije alata)

Folder `pwa/` je gotova web aplikacija. Sadrži:
index.html (naslovnica) · app.html (sama aplikacija) · manifest.json · sw.js · icon-192.png · icon-512.png · icon-512-maskable.png

Svih **7 fajlova** mora biti u istom folderu na sajtu.

## Korak 1 — objavi folder (2 min)
1. Otvori https://app.netlify.com/drop
2. Prevuci **cijeli raspakovani `pwa` folder** u prozor (ne .zip). Ako si već jednom deployao, prevuci ga na isti postojeći sajt da se prepiše.
3. Dobiješ link tipa `https://nesto-random.netlify.app` — kopiraj ga.

Test odmah: otvori link na telefonu → Chrome meni ⋮ → "Instaliraj aplikaciju".
Već tu imaš ikonu na ekranu i rad bez interneta.

## Korak 2 — napravi APK (10 min)
1. Otvori https://www.pwabuilder.com
2. Zalijepi Netlify link → **Start**.
3. Sačekaj analizu (manifest i service worker su već tu, ocjena treba biti zelena).
4. **Package for stores** → **Android**.
5. U opcijama:
   - Package ID: `com.tikva.skiprep`
   - App name: `Tikva`
   - **Signing key: Create new** — obavezno preuzmi i sačuvaj `signing.keystore` + lozinke
     (bez njih ne možeš objaviti update iste aplikacije)
   - Isključi "Include source code" ako ti ne treba
6. **Download** → dobiješ .zip sa `app-release-signed.apk` i `app-release-signed.aab`.

## Korak 3 — instaliraj na telefon
1. Pošalji `app-release-signed.apk` sebi (Drive, USB, WhatsApp na sebe).
2. Otvori fajl na telefonu → Android pita za dozvolu "Instaliraj nepoznate aplikacije" → dozvoli.
3. Instaliraj.

`.aab` fajl treba samo ako ćeš jednom ići na Google Play.

## Napomena o "Digital Asset Links"
PWABuilder APK je TWA — može pri prvom pokretanju pokazati traku sa adresom
ako domen nije verificiran. Rješenje: u PWABuilder zipu je `assetlinks.json`;
stavi ga na Netlify u putanju `/.well-known/assetlinks.json` i ponovo objavi.
Za ličnu upotrebu traka ne smeta.

## Ažuriranje kasnije
Sadržaj mijenjaš u ovom projektu → ja ponovo generišem `pwa/index.html` →
ti prevučeš folder na isti Netlify sajt. Aplikacija na telefonu se sama osvježi;
novi APK ne treba praviti.

## Za pravi native APK (Put 2)
Ako kasnije zatrebaju native notifikacije po rasporedu i offline video fajlovi:
Capacitor + Android Studio. Reci pa pripremim projekat.
