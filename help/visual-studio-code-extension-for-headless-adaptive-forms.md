---
title: Visual Studio Code-Erweiterung für Headless-adaptive Formulare
description: Visual Studio Code-Erweiterung für Headless-adaptive Formulare
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: Headless, adaptive Formulare, Visual Studio Code-Erweiterung
hide: false
exl-id: 11960e91-6c09-48d4-9d57-37537f808cd4
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Microsoft Visual Studio Code-Erweiterung für Headless-adaptive Formulare

Wenn Sie Microsoft® Visual Studio Code als IDE verwenden, können Sie die Adaptive Forms-Erweiterung für Microsoft Visual Studio Code verwenden. Die Erweiterung:

* Fügt IntelliSense-Funktionen für Adaptive Forms zu Visual Studio-Code hinzu
* Hilft bei der Validierung und automatischen Vervollständigung der JSON-Syntax für Headless-adaptive Formularkomponenten
* Bietet ein Bedienfeld zum einfachen Navigieren in der Struktur für ein adaptives Headless-Formular
* Hilft bei der Übersetzung eines Headless-adaptiven Formulars

<!-- 

The extension o easily navigate the structure 

Adobe provides an extension for Microsoft&reg; Visual Studio Code to make it easier for you to navigate structure and develop Headless adaptive forms in Visual Studio Code. The extension adds Adaptive Forms related IntelliSense capabilities and helps auto-complete Headless adaptive forms JSON syntax. It also adds a panel, titled Forms Tree, to help navigate structure of Headless adaptive form. 

-->

## Voraussetzungen

* Herunterladen und installieren [Microsoft Visual Studio Code 1.62.0 oder höher](https://code.visualstudio.com/docs/supporting/FAQ#_how-do-i-find-the-version). Wenn Sie eine ältere Version oder keine Version installiert haben, laden Sie die neueste Version von [Microsoft-Website](https://code.visualstudio.com/docs/setup/setup-overview). Informationen zur Verwendung von Visual Studio über die Befehlszeile in Apple macOS finden Sie unter [Starten über die Befehlszeile](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line).
* Laden Sie die [Adaptive Forms Builder-Erweiterung](/help/assets/adaptive-form-builder-0.12.0.vsix).

## Installieren der Erweiterung

1. Öffnen Sie die Eingabeaufforderung und navigieren Sie zum Ordner, der die heruntergeladene Erweiterungsdatei enthält. *adaptive-form-builder-[version].vsix*.

1. Führen Sie den folgenden Befehl aus, um die Erweiterung zu installieren:

   `code -–install-extension adaptive-form-builder-0.12.0.vsix`

   <br>

   ![Installieren der Erweiterung](/help/assets/install-extension.png)


   Weitere Informationen zu .vsix -Dateien finden Sie unter [Hilfe zu Microsoft Visual Studio Code](https://code.visualstudio.com/docs/editor/extension-marketplace#_install-from-a-vsix).
