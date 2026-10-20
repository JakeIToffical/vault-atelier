# Drittquellen

Die Formatimplementierung orientiert sich an:

- LedgerHQ/app-passwords, Commit bf2319b8ed8abcb9c77173945d27c33d7927155b
  https://github.com/LedgerHQ/app-passwords/tree/bf2319b8ed8abcb9c77173945d27c33d7927155b
- LedgerHQ/ledgerjs, WebUSB-Transport und HID-Framing
  https://github.com/LedgerHQ/ledgerjs/tree/master/packages/hw-transport-webusb
  https://github.com/LedgerHQ/ledgerjs/blob/master/packages/devices/src/hid-framing.ts

Ledger-Quellen: Apache License 2.0, siehe LICENSE.
Copyright der zugrunde liegenden Ledger-Quellen: Ledger / Ledger SAS und die jeweiligen Beitragenden.

Diese Anwendung ist eine eigenständige Implementierung mit einer eigenen Oberfläche. Der minimale USB-Transport wurde an die Einzeldatei-Anwendung angepasst; der offizielle Vergleichscodec ist nicht Teil dieses Release-Pakets. Keine Verbindung zu oder Unterstützung durch Ledger wird behauptet.
