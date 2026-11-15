# PixelStudio Mobile 1.0 – kostenlose PWA für iPhone und Android

## Inhalt
- `index.html`: mobile Oberfläche
- `app.js`: Bildeditor und `.pxstudio`-Projektformat
- `manifest.webmanifest`, `icon-*.png`: installierbare App
- `sw.js`: Offline-Cache nach erstem Online-Aufruf

## Installieren ohne PC (iPhone oder Android)

1. Lade das ZIP herunter und entpacke es in der Dateien-App.
2. Lege ein **kostenloses GitHub-Konto** an und erstelle ein öffentliches Repository, beispielsweise `pixelstudio-mobile`.
3. Lade **alle sechs Dateien** aus dem ZIP in das Stammverzeichnis des Repositorys hoch (nicht nur das ZIP). Das geht auf dem Smartphone im Browser über GitHubs Website; ggf. Desktop-Website anfordern.
4. Öffne in GitHub **Settings > Pages**, wähle **Deploy from a branch**, `main` und `/ (root)`, und speichere. Warte, bis GitHub die HTTPS-Adresse anzeigt, etwa `https://DEIN-NAME.github.io/pixelstudio-mobile/`.
5. **iPhone:** Öffne diese Adresse in Safari, tippe auf Teilen > **Zum Home-Bildschirm** > Hinzufügen. **Android:** Öffne sie in Chrome und wähle Menü > **App installieren** oder **Zum Startbildschirm hinzufügen**.
6. Öffne die installierte App einmal mit Internetverbindung; anschließend können die Kern-Dateien offline geladen werden. Die App benötigt keinen Server zur Bildbearbeitung.

GitHub Pages ist für öffentliche Repositories verfügbar. Deine Projektdateien werden nicht automatisch auf GitHub hochgeladen; nur der App-Code ist öffentlich.

## Bedienung
- **Bild**: Foto als neue Ebene hinzufügen; **Malebene**: transparente Ebene.
- **Text**: Schrift, Kontur, Schatten, Farbe und Größe festlegen.
- **Verschieben**: Ebene durch Ziehen positionieren; **zwei Finger**: zoomen und schwenken.
- **Pinsel, Radierer, Retusche**: ausgewählte Bildebene bearbeiten. Retusche ist ein einfacher Farbabtast-Pinsel.
- **Rechteck, Ellipse, Verlauf**: direkt auf die aktive Bildebene zeichnen.
- **Auswahl**: rechteckigen Bereich aufziehen; daraus eine Maske erzeugen oder Ebene freistellen.
- **Hintergrund entfernen**: ähnlich gefärbte Pixel transparent machen, **kein KI-Freisteller**.
- **Farbkorrektur**: Helligkeit, Kontrast, Graustufen, Negativ, Sättigung, Farbtemperatur, Gamma.
- **Ebenen**: sortieren mit ↑/↓, sperren, ein-/ausblenden, duplizieren, löschen, Deckkraft und Mischmodus.
- **Projekt**: `.pxstudio` speichern (Datei wird heruntergeladen) und später über **Projekt öffnen** laden.
- **PNG/JPG**: fertiges Bild exportieren.

## Projekt-Kompatibilität
Mobile `.pxstudio` speichert Ebenen und Pixelbilder als JSON mit eingebetteten PNG-Daten. Die mobilen Dateien sind innerhalb dieser Version wieder ladbar. Ältere Desktop-Projekte können teilweise importiert werden (Bildebenen), aber Qt-Schriftangaben, Koordinaten und Effekte können anders dargestellt werden. Ein verlustfreier Austausch mit der C++-Desktopversion ist noch **nicht garantiert**.

## Grenzen und Datenschutz
- Kein App Store und kein Apple-Entwicklerkonto nötig. HTTPS ist für Installation und Service Worker erforderlich; das bloße Öffnen der HTML-Datei aus der Dateien-App ist nicht die installierbare PWA.
- Fotos und Projekte werden lokal im Browser bearbeitet; die App hat keine Upload- oder Cloud-Funktion. Der kostenlose Hostinganbieter liefert lediglich die App-Dateien aus.
- **Projekt regelmäßig manuell speichern!** Es gibt noch keine dauerhafte automatische Projektwiederherstellung. Auf iPhones können große Bilder wegen Arbeitsspeicherlimits problematisch sein.
- Farbkorrektur ist destruktiv. Mischmodi sind im Canvas gerendert. Ebenenmasken sind derzeit rechteckig. Der mobile Editor ist kein vollständiger Photoshop-Ersatz.
- Noch nicht auf echten iOS-/Android-Geräten getestet. JavaScript-Syntaxprüfung wurde ausgeführt; bitte zuerst mit Testbildern ausprobieren.

## Lokal am Computer testen (optional)
Im Ordner `PixelStudio_Mobile` `python -m http.server 8000` ausführen und `http://localhost:8000` öffnen. Eine echte PWA-Installation auf dem Smartphone braucht HTTPS.
