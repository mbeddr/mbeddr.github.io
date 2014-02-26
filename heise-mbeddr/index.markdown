---
layout: span5
title: Heise Beispiel
---

Hier finden sie weiterführende Informationen zum iX Artikel. Unter anderem finden
sie hier den Quellcode und eine Hinweise wie sie ihren Arduino konfigurieren müssen
damit das Beispiel Projekt darauf funktioniert.

 **Abhängigkeiten:**
 * mbeddr ([Anleitung](http://mbeddr.com/download.html))
 * mbeddr.arduino ([Anleitung](https://github.com/coolya/mbeddr.arduino/blob/master/Readme.md))
 * Arduino Uno (optional)

Nach dem sie die mbeddr und mbeddr.arduino installiert haben finden sie den
Quellcode des Beispiels hier. Nach dem Download öffnen sie das Projekt in mbeddr /
MPS.


Möchten sie den Code auf einem Arduino Uno ausführen benötigen Sie noch einiges
an zusätzlicher Hardware:

* Heißleiter (Nennwiederstand 4,5 kOHM, aber auch andere Werte sind möglich)
* Ein Widerstand gleich zum Nennwiederstand des Heißleiters
* Zwei Widerstände mit beliebigem Wert
* Eine Leuchtdiode
* Ein Schalter

Hier finden sie den Schaltplan:

[![Schaltplan](/images/Schaltplan.png "Schaltplan")](/images/Schaltplan.png)

Den Heißleiter verbinden Sie mit dem Analogeingagn 5 des Ardunio ([Anleitung](http://www.nextit.de/2011/07/thermometer-mit-arduino/)). Die Leuchtdiode mit
dem Digitalenausgang 5 ([Anleitug](http://arduino.cc/en/Tutorial/Blink?from=Tutorial.BlinkingLED)) und den Schalter mit Digitialausgang 6 ([Anleitung](http://www.arduino-tutorial.de/2010/06/digital-in/)). Anschließend
können sie das Programm von der Komandozeile aus auf den Arduino spielen.