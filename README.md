# As-Salah für Android

Download-Seite und Update-Feed für **As-Salah** (Gebetszeiten & Qibla-Kompass).

**Seite:** <https://shoaib87-ger.github.io/As-Salah-Andorid/>

---

## Was hier liegt — und was nicht

| Datei | Zweck |
|---|---|
| `index.html` | Die Download-Seite, vierprachig (DE / EN / ES / دری), nur heller Modus |
| `latest.json` | Version, Datum, Größe und „Was ist neu" — wird von der Seite **und** von der App gelesen |
| `downloads/AsSalah.apk` | Die App. Der Dateiname bleibt bei jedem Update gleich, damit der Link stabil ist |
| `screenshots/*.png` | Bilder aus der laufenden App für die Seite |

Kein Quellcode, keine Schlüssel. Die App wird aus einem separaten,
**privaten** Repository gebaut und signiert. Die `.gitignore` hier ist eine
Positivliste: alles außer den obigen Dateien ist ausgeschlossen, damit
versehentlich nichts anderes hochgeladen werden kann.

## Wie ein Update abläuft

1. Im privaten Repo `versionCode` +1 setzen und die signierte Release-APK bauen
   (`scripts/build-release-apk.sh` prüft dabei den Signatur-Fingerprint).
2. `downloads/AsSalah.apk` hier ersetzen.
3. `latest.json` aktualisieren: `versionName`, `versionCode`, `sizeMb`, `date`
   und `notes` in allen vier Sprachen.
4. Pushen.

Danach zeigt die Seite die neue Version automatisch an, und die installierte
App blendet höchstens einmal pro 24 Stunden eine Hinweiskarte ein, die auf
diese Seite führt. **Android erkennt ein Update ausschließlich am
`versionCode`** — ein neuer `versionName` allein bewirkt nichts.

## Stand

Version **1.5 (versionCode 7)**, Android 8.0 oder neuer.

Die App bietet: Gebetszeiten für den eigenen Standort mit laufendem Gebet und
Restzeit, Qibla-Kompass, Einstellungen (Sprache, Berechnungsmethode,
Rechtsschule, Datenquelle), Erinnerungen pro Gebet mit optionaler
15-Minuten-Vorwarnung, ein Home-Screen-Widget, vier Sprachen und
Offline-Betrieb. Kein Tracking, keine Werbung, kein Konto.

© Dr. Shoaib Seddiqi
