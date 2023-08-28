---
title: Problembehebung bei Headless Adaptive Forms
description: Problembehebung bei Headless Adaptive Forms
keywords: Headless, adaptives Formular, Fehlerbehebung
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
hide: false
exl-id: bfb7e688-d2be-4aaa-ac9b-147cbd74b516
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 7%

---

# Fehlerbehebung

## Das Archetyp-Projekt kann nicht in der lokalen Entwicklungsumgebung bereitgestellt werden

### Problem

Wenn Sie `mvn -PautoInstallPackage clean install` oder ähnliche Befehle zum Bereitstellen eines AEM Archetypprojekts verwenden, kann das Projekt nicht bereitgestellt werden.

### Grund

Dies kann aufgrund einer nicht unterstützten Version oder einer beschädigten Installation von node.js oder NPM geschehen.

### Lösung

1. Vollständig [vorhandene Installationen von Node.JS entfernen](https://khushwantsehgal.wordpress.com/2022/06/28/how-to-remove-node-js-completely-from-windows-10/) aus Ihrer Umgebung.

1. Installieren Sie Node.JS 16.13.0 oder höher mit NPM.

1. Starten Sie den Computer neu.


## Die `mvn clean install` Befehl schlägt fehl

### Problem

Wenn Sie `mvn clean install` oder ähnliche Befehle zum Bereitstellen eines AEM Archetypprojekts verwenden, kann der Befehl nicht ausgeführt werden.

### Grund

Dies kann vorkommen, wenn Git nicht installiert ist.

### Lösung

Laden Sie die [neueste Version von Git](https://git-scm.com/downloads). Wenn Sie mit Git noch nicht vertraut sind, lesen Sie [Installieren von Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
