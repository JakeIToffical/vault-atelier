# Vault Atelier — Ledger Backup Studio

[**Web-App direkt öffnen**](https://jakeitoffical.github.io/vault-atelier/Ledger-Backup-Studio.html) · [HTML-Datei herunterladen](https://github.com/JakeIToffical/vault-atelier/raw/refs/heads/master/Ledger-Backup-Studio.html)

Maintainer: [JakeIToffical](https://github.com/JakeIToffical).

Eigenständiger Browser-Client zum Bearbeiten von Ledger-Passwords-Backups. Dieses Repository entwickelt keine Ledger-Geräte-App und enthält in seinem aktuellen Stand keine Firmware, Firmware-Build-Dateien oder Firmware-Tests. Kein offizielles Ledger-Produkt.

`Ledger-Backup-Studio.html` in Chrome oder Edge öffnen. Die App ist vollständig in dieser einen Datei enthalten; keine Installation und keine externen Bibliotheken nötig.

- Backup öffnen oder per USB vom Ledger sichern.
- Nicknames hinzufügen, entfernen oder sortieren.
- Entwurf als neue Backup-Datei herunterladen.
- Für Restore den Entwurf prüfen, die separate Sicherheitskopie speichern und am Ledger bestätigen. Restore ersetzt die gesamte Liste.
- Deutsch, Englisch, Französisch und Spanisch oben rechts auswählen.

Nicknames und Ableitungsparameter bestimmen die Passwörter. Erhaltene Einträge werden unverändert übernommen. Die tatsächlichen Passwörter erzeugt der Ledger. Niemals eine Recovery Phrase oder private Schlüssel eingeben.

## USB und eigenes Hosting

Nano X entsperren, Passwords öffnen und Ledger Live sowie andere Ledger-Tabs schließen. WebUSB benötigt Chrome/Edge und einen sicheren Kontext. Falls USB beim direkten Öffnen nicht verfügbar ist, die HTML-Datei unter eigenem HTTPS hosten oder aus diesem Ordner lokal starten:

```sh
python3 -m http.server 8765 --bind 127.0.0.1
```

Dann `http://localhost:8765/Ledger-Backup-Studio.html` öffnen. Nur die App hosten, keine persönlichen Backups. Die App sendet keine Backup-Daten an einen Server.

## Verwendung auf eigene Gefahr

Unabhängiges Werkzeug ohne Gewähr; kein offizielles Ledger-Produkt. Fehler oder unterbrochene Restores können Datenverlust oder nicht mehr erreichbare Passwörter verursachen. Vor jedem Restore eine separate, unveränderte Sicherung behalten und das Ergebnis am Gerät prüfen. Ein vollständiger Hardware-Restore wurde nicht bestätigt.

## Quellen und Lizenz

Format und USB-Protokoll folgen LedgerHQ/app-passwords und LedgerHQ/ledgerjs. Details in THIRD-PARTY.md; die Ledger-Lizenz liegt bei. Das Paket enthält keine persönlichen Backups und keine Entwicklungswerkzeuge.

## Lizenz

Apache License 2.0 — siehe [LICENSE](LICENSE). Quellen und Änderungen sind in [NOTICE](NOTICE) und [THIRD-PARTY.md](THIRD-PARTY.md) dokumentiert. Die Lizenz gewährt keine allgemeinen Rechte an Ledger-Marken.

## Kompatibilität

Geprüfter Stand: Backup-Format und USB-Protokoll aus LedgerHQ/app-passwords, Commit `bf2319b8ed8abcb9c77173945d27c33d7927155b`; Geräteabfrage an Nano X mit Passwords 1.4.1 erfolgreich. Unterstützte Generationsversionen: 0 und 1. Ein vollständiger Hardware-Backup-/Restore-Durchlauf ist nicht bestätigt.

Ziel ist die Kompatibilität mit aktuellen Ledger-Passwords-Versionen. Eine automatische Garantie für zukünftige Versionen gibt es nicht. Unbekannte Generationsversionen, beschädigte oder widersprüchliche Backups werden abgelehnt. Vor Freigabe einer neuen Ledger-Version müssen Format, Protokoll und Restore erneut geprüft werden. Solange diese Schnittstellen gleich bleiben, ist in der Regel keine Änderung am Client nötig.
