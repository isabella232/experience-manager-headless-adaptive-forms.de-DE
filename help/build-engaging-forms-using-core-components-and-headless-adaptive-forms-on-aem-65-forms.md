---
title: Erstellen ansprechender Formulare mithilfe von Kernkomponenten und Headless
seo-title: Build Engaging Forms Using Core Components and Headless
description: Erstellen ansprechender Formulare mithilfe von Kernkomponenten und Headless
seo-description: Build Engaging Forms Using Core Components and Headless
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
topic-tags: develop
hide: true
exl-id: 46df943c-0622-4b3b-a802-85c39ac6a734
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '2189'
ht-degree: 63%

---

# Erstellen ansprechender Formulare mithilfe von Kernkomponenten und Headless Adaptives Forms auf AEM 6.5 Forms {#build-engaging-forms-using-core-components-and-headless}

## Labor-Übersicht {#lab-overview}

In diesem praktischen Labor lernen Sie:

Verwendung von AEM Forms zur einfachen Erstellung von Adaptive Forms mithilfe der neuesten Kernkomponenten, die mit AEM Sites konsistent sind, Aktivierung von Omnichannel-Datenerfassungserlebnissen durch Bereitstellung der adaptiven Forms als Headless-Formulare für Web, Mobile und Chat. Außerdem lernen Sie Best Practices rund um die Formatierung, Anpassungen und Frontend-Entwicklung kennen.

## Haupterkenntnisse {#key-takeaways}

* **Geschäftliche Agilität**: Als Business-Anwenderin bzw. -Anwender kann ich mühelos Formularerlebnisse für mehrere Kanäle erstellen.

* **Unterstützung für Frontend-Entwickler**: Als Frontend-Entwicklungsperson kann ich das Anwendererlebnis mit Headless-Formularen steuern.

* **Entwicklergeschindigkeit**: Als Entwicklungsperson kann ich mühelos und konsistent Sites- und Forms-Komponenten anpassen.

## Bevor Sie beginnen {#pre-requisites}

Gehen Sie wie folgt vor:

* Installieren Sie die [neueste Version von Git](https://git-scm.com/downloads). Wenn Sie mit Git noch nicht vertraut sind, lesen Sie [Installieren von Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

* Installieren [Node.js 16.13.0 oder höher](https://nodejs.org/de/download/). Wenn Sie mit Node.js noch nicht vertraut sind, lesen Sie [Installieren von Node.js](https://nodejs.dev/en/learn/how-to-install-nodejs).

* [Aktivieren von Headless Adaptive Forms](enable-headless-adaptive-forms-and-core-components.md) in Ihrer AEM 6.5 Forms-Umgebung.

* Installieren [Microsoft Visual Studio Code](https://code.visualstudio.com/download) oder einem Texteditor. Beispiele im Dokument verwenden Microsoft Visual Studio Code.

## Lektion 1 {#lesson-1}

### Ziel {#lesson-1-objectives}

Machen Sie sich mit AEM Forms-Umgebung 6.5 vertraut.

### Lektionskontext {#lesson-1-context}

In dieser Lektion können Sie sich mit AEM 6.5 Forms vertraut machen, indem Sie in die Benutzeroberfläche navigieren.

### Übung {#lesson-1-excercise}

1. Öffnen Sie den Browser und geben Sie die URL der Autorenumgebung von ein. Zum Beispiel:
   [https://localhost:4502](https://localhost:4502).

1. Nachdem Sie angemeldet sind, navigieren Sie zur AEM Forms-Benutzeroberfläche. Klicken Sie auf **Formulare**.

   ![](/help/assets/screenshot2028113829.png){width="50%" align="left"}

1. Klicken Sie auf **Formulare und Dokumente**. Schließen Sie alle Popups, die sich auf Voreinstellungen oder Informationen beziehen.

   ![](/help/assets/screenshot2028113929.png){width="50%" align="left"}

   Alle verfügbaren Formulare werden angezeigt.

   ![](/help/assets/screenshot2028114029.png){width="50%" align="left"}

## Lektion 2

### Ziel

Verfassen Sie ein adaptives Formular mit den neuesten Kernkomponenten, konfigurieren und senden Sie es.

### Lektionskontext

In dieser Lektion erstellen Sie als Geschäftsbenutzer ein adaptives Formular für mehrere Kanäle wie Web, Mobile und Chat mit dem adaptiven Forms-Editor mit standardisierten nativen Kernkomponenten, um Daten zu erfassen.

### Übung

1. Erstellen Sie einen Übermittlungsendpunkt für das Formular:

   1. Öffnen Sie <https://requestbin.com/> in einer neuen Browser-Registerkarte.
      ![](/help/assets/screenshot2028114329.png){width="50%" align="left"}

   1. Klicken Sie auf **Öffentlichen Container erstellen** und kopieren Sie die Endpunkt-URL.
      ![](/help/assets/screenshot202023-03-0120at206.10.0020pm.png){width="50%" align="left"}

   Dieser bestimmte Endpunkt dient als Beispiel für das Senden und Anzeigen von Daten. In der eigentlichen Produktion verwenden Sie Ihren eigenen Endpunkt oder Ihre eigenen Datenquellen, um die erfassten Daten zu speichern.

1. Erstellen eines adaptiven Formulars:

   1. Navigieren Sie auf der in Lektion 1 verwendeten Browser-Registerkarte zur AEM Forms-Web-Benutzeroberfläche und navigieren Sie zu **Forms** > **Forms und Dokumente**.

   1. Klicken Sie auf **Erstellen** und wählen Sie „Adaptives Formular“.
      ![](/help/assets/creating-adaptive-form-6-5.png){width="50%" align="left"}

   1. Wählen Sie die **Leer mit Kernkomponenten** Vorlage auf dem Bildschirm zur Vorlagenauswahl wie unten gezeigt, und klicken Sie auf **Nächste**.
      ![](/help/assets/creating-adaptive-form-6-5-select-blank-template.png){width="50%" align="left"}

   1. Angeben `Contact us` als **Titel** des Formulars. Stellen Sie sicher, dass **Name** der Form `contact-us`.
      ![](/help/assets/creating-adaptive-form-65-specify-title.png){width="50%" align="left"}

   1. Klicken Sie auf **Erstellen**. Ein Dialogfeld wird angezeigt.

   1. Klicken Sie im Dialogfeld auf **Bearbeiten**. Das Formular wird im Editor für adaptive Formulare geöffnet. Schließen Sie alle Popups oder Dialogfelder für Voreinstellungen oder Informationen.

   1. Öffnen Sie den Komponenten-Browser und ziehen Sie die Bedienfeldkomponente in die Mitte des Bildschirms.

      ![](/help/assets/lab65-add-panel.png){width="50%" align="left"}

   1. Ziehen Sie Komponenten per Drag-and-Drop aus dem Komponenten-Browser, um ein Formular ähnlich dem folgenden zu erstellen:

      ![](/help/assets/contact-us-headless-adaptive-form.png){width="50%" align="left"}


   1. Öffnen Sie den Inhaltsbrowser, klicken Sie auf das Symbol Guide Container properties und öffnen Sie die **Einsendung** Registerkarte. Wählen Sie die **An REST-Endpunkt übermitteln** Übermittlungsaktion: Wählen Sie die **POST-Anfrage aktivieren** und geben Sie den in Lektion 2 erstellten REST-Endpunkt im **URL für POST-Anfrage** und klicken Sie auf das **Fertig** Symbol.

      ![](/help/assets/configure-submit-action.png){width="50%" align="left"}

1. Veröffentlichen eines adaptiven Formulars:

   1. Öffnen Sie AEM Benutzeroberfläche und navigieren Sie zu **Forms** > **Forms und Dokumente**. Wählen Sie das im vorherigen Schritt erstellte Formular aus und klicken Sie auf **Veröffentlichen**.

   1. Klicken Sie im Dialogfeld Assets veröffentlichen auf **Veröffentlichen**. Die Erfolgsmeldung wird angezeigt.

## Lektion 3

### Ziel

Aktualisieren Sie Stile mithilfe der Best Practices für die Frontend-Entwicklung.

### Lektionskontext

In dieser Lektion erfahren Sie als Frontend-Entwickler, wie Sie die Formatierung für das zuvor erstellte adaptive Formular einfach aktualisieren können.

### Übung

Richten Sie ein lokales Repository des Designs ein:

1. Öffnen Sie die Eingabeaufforderung oder Shell mit Administratorrechten:

   ![](/help/assets/screenshot2028115829.png){width="50%" align="left"}

1. Verwenden Sie in der Eingabeaufforderung den folgenden Befehl, um zum Ordner `c:\git` zu navigieren.

   ```Shell
   cd git
   ```

   Wenn der Ordner nicht vorhanden ist, verwenden Sie die `md git` -Befehl, um ihn zu erstellen.

1. Verwenden Sie den folgenden Befehl, um den Frontend-Code des Designs zu klonen:

   ```Shell
   git clone -b WKND https://github.com/adobe/aem-forms-theme-canvas
   ```

1. Verwenden Sie den folgenden Befehl in der angegebenen Reihenfolge, um zum Verzeichnis **aem-forms-theme-canvas** zu navigieren und Visual Studio Code zu öffnen.

   ```Shell
   cd aem-forms-theme-canvas
   code .
   ```

   ![](/help/assets/screenshot2028126029.png){width="50%" align="left"}

1. Wählen Sie **Trust the authors of all files in the parent folder** und klicken Sie auf **Yes, I trust the authors**.

   ![](/help/assets/screenshot2028116229.png){width="50%" align="left"}

1. Benennen Sie die `env_template` Datei in .env.  Um die Datei umzubenennen, klicken Sie mit der rechten Maustaste auf die Datei **env_template** und wählen Sie die Option **Umbenennen**.

   ![](/help/assets/screenshot2028116429.png){width="30%" align="left"}

   </br>

   ![](/help/assets/screenshot2028116529.png){width="50%" align="left"}

1. Legen Sie die folgenden Werte für die Variablen in der .env-Datei fest und speichern Sie die Datei:

   * **AEM_URL**: Geben Sie die URL eines **publish** -Instanz. Zum Beispiel: `https://localhost:4502/`

   * **AEM_ADAPTIVE_FORM**: Geben Sie den Namen des Formulars an. Zum Beispiel: `contact-us`.

   </br>

   ![](/help/assets/lab65-theme-environment-variable.png)


1. Führen Sie im Eingabeaufforderungsfenster den folgenden Befehl aus:

   ```Shell
   npm install
   ```

   ![](/help/assets/screenshot2028117029.png)

   >[!NOTE]
   >
   > * Wenn Sie eine Meldung erhalten, in der Sie aufgefordert werden, npm über den Befehl `npm notice Run npm nstall -g npm@9.6.0`zu aktualisieren, ignorieren Sie die Meldung.
   > * Führen Sie keine anderen npm-Befehle aus, es sei denn, Sie werden dazu in der Arbeitsmappe angewiesen.

1. Führen Sie nun den folgenden Befehl aus, um eine Vorschau des Formulars anzuzeigen.

   ```Shell
   npm run live
   ```

   ![](/help/assets/screenshot2028117229.png)

   Warten Sie nach Ausführung des oben genannten Befehls auf die Nachricht `webpack compiled`. Das Formular wird auf einer Browser-Registerkarte angezeigt.

   >[!NOTE]
   >
   >Wenn nach der Ausführung des Befehls `npm run live` für mehr als 3–4 Minuten ein leerer Browser-Bildschirm erscheint, ändern Sie `localhost` in der Browser-URL zu 127.0.0.1 und betätigen Sie die **Eingabetaste**.


   ![](/help/assets/contact-us-headless-adaptive-form-with-canvas-theme.png){width="50%" align="left"}


1. Öffnen Sie in Visual Studio Code die Datei `PROJECT\src\site\_variables.scss`. Beachten Sie, dass die Farbe `$error` ein Farbton von ROT ist.

   ![](/help/assets/screenshot2028120729.png){width="50%" align="left"}

1. Übermitteln Sie das Formular im Browser, um die rote Farbe im Feld **Vorname** zu sehen.

   ![](/help/assets/error-color-before.png)

1. Legen Sie die Farbe für **$error** auf **#5736eb** fest und speichern Sie die Datei.

1. Aktualisieren Sie den Browser und übermitteln Sie das Formular. Sie sehen, dass sich die Fehlerfarbe im Vorname-Feld entsprechend geändert hat.

   ![](/help/assets/error-color-after.png)

1. Drücken Sie in der Eingabeaufforderung **Strg+C**, geben Sie **Y** ein und drücken Sie die **Eingabetaste** zum Beenden des npm-Prozesses. Es ist wichtig, den npm-Server anzuhalten, damit er nicht mit dem nächsten Satz von Übungen in Konflikt gerät.
1. Schließen Sie Visual Studio Code und das Eingabeaufforderungsfenster.

## Lektion 4

### Ziel

Rendern Sie das Formular auf Web-/Mobile- und anderen Benutzeroberflächen als Headless-Formular.

### Lektionskontext

In dieser Lektion erfahren Sie als Frontend-Entwickler, wie Sie das zuvor erstellte adaptive Formular mithilfe des Framework für die React-Frequenzgestaltung als Headless-Formular rendern können.

### Übung

Richten Sie ein lokales Repository mithilfe des React-Starter-Projekts ein:

1. Öffnen Sie die Eingabeaufforderung mit Administratorrechten.

   ![](/help/assets/screenshot2028115829.png){width="30%" align="left"}

1. Verwenden Sie in der Eingabeaufforderung den folgenden Befehl, um zum Ordner `c:\git` zu navigieren.

   ```Shell
   cd git
   ```

1. Verwenden Sie den folgenden Befehl, um das React-Starter-Projekt des adaptiven Formulars zu klonen:

   ```Shell
   git clone https://github.com/adobe/react-starter-kit-aem-headless-forms
   ```

   ![](/help/assets/screenshot2028117329.png)

1. Verwenden Sie die folgenden Befehle in der angegebenen Reihenfolge, um zum Verzeichnis **react-starter-kit-aem-headless-forms** zu navigieren, und öffnen Sie Visual Studio Code.

   ```Shell
   cd react-starter-kit-aem-headless-forms
   
   code .
   ```

   ![](/help/assets/screenshot2028117529.png)


   Das Fenster „Visual Studio Code“ wird geöffnet.

   ![](/help/assets/screenshot2028117429.png){width="50%" align="left"}

So rendern Sie das in Ihrer Veröffentlichungsumgebung gehostete Formular:

1. Benennen Sie die Datei „env_template“ in eine Datei „.env“ um. Klicken Sie zum Umbenennen mit der rechten Maustaste auf die Datei **env_template** und wählen Sie die Option **Umbenennen**.

   ![](/help/assets/screenshot2028117629.png){width="30%" align="left"}

   ![](/help/assets/screenshot2028117729.png)

1. Legen Sie die folgenden Werte für die Variablen in der .env-Datei fest. Speichern Sie die Datei nach dem Aktualisieren der Variablen.

   * **AEM_URL**: Geben Sie die URL der Veröffentlichungsumgebung an. Zum Beispiel: `https://localhost:4503/`

   * **AEM_FORM_PATH**: Geben Sie den Pfad des in der vorherigen Lektion erstellten adaptiven Formulars an. Zum Beispiel: `/content/forms/af/contact-us/`

   </br>

   ![](/help/assets/lab65-starter-kit-environment-variable.png)

1. Öffnen Sie das Befehlsfenster, stellen Sie sicher, dass Sie sich im Verzeichnis **react-starter-kit-aem-headless-forms** befinden, und führen Sie den folgenden Befehl aus:

   ```Shell
   npm install
   ```

   ![](/help/assets/screenshot2028118029.png)


1. Führen Sie im Eingabeaufforderungsfenster den folgenden Befehl aus:

   ```Shell
   npm start
   ```

   ![](/help/assets/lab65-starter-kit-start.png)

   Der obige Befehl startet einen lokalen Entwicklungs-Server, der die von AEM abgerufene Formulardefinition mithilfe der Frontend-Bibliothek von React Spectrum auf eine Headless-Weise rendert.

   >[!NOTE]
   >
   > 
   > Wenn nach der Ausführung des Befehls `npm start` für mehr als 3–4 Minuten ein leerer Browser-Bildschirm erscheint, ändern Sie `localhost` in der Browser-URL zu 127.0.0.1 und drücken Sie die **Eingabetaste**.

   ![](/help/assets/headless-adaptive-form-lab.png)

Jetzt nehmen wir als Business-Anwenderin bzw. -Anwender Änderungen am Formular auf dem Server vor und zeigen die Änderungen automatisch im Headless-Formular an.

1. Öffnen Sie die AEM Forms-Verwaltungsoberfläche im Browser. Beispiel: [http://localhost:4502/aem/forms.html/content/dam/formsanddocuments](http://localhost:4502/aem/forms.html/content/dam/formsanddocuments).

1. Wählen Sie die **Kontakt** Formular und klicken Sie **Bearbeiten.** Das Formular wird im adaptiven Forms-Editor geöffnet.


1. Wählen Sie die **Kontaktnummer** und klicken Sie auf **Symbol &quot;Bearbeiten&quot;(Bleistiftsymbol)** in der Symbolleiste. Wenn Sie die Popup-Symbolleiste nicht sehen können, wechseln Sie in den Bearbeitungsmodus, indem Sie auf die Schaltfläche **Bearbeiten** oben rechts, links von der Schaltfläche **Vorschau**, klicken.

   ![](/help/assets/change-field-title.png){width="50%" align="left"}

1. Ändern Sie den Titel in **Mobiltelefonnummer**. Klicken Sie auf eine leere Stelle im Formular, damit die am Formular vorgenommenen Änderungen gespeichert werden.

Veröffentlichen wir das aktualisierte Formular, um die Änderungen in die Publishing-Umgebung zu übertragen.

1. Wählen Sie im Tab Verwaltungsoberfläche von AEM Forms das Kontaktformular aus und klicken Sie auf **Veröffentlichung rückgängig machen**. Wenn Sie die Schaltfläche **Veröffentlichung rückgängig machen** nicht sehen, fahren Sie mit Schritt 3 fort, um die Änderungen direkt zu veröffentlichen.


1. Klicken Sie auf **Veröffentlichung aufheben**. Klicken Sie auf **Schließen** im entsprechenden Dialogfeld.

1. Nachdem der Browser aktualisiert wurde, wählen Sie das Kontaktformular aus und klicken Sie auf **Veröffentlichen**.


1. Klicken Sie auf **Veröffentlichen**. Klicken Sie auf **Schließen** im entsprechenden Dialogfeld.

1. Aktualisieren Sie die Browser-Registerkarte mit dem angezeigten Headless-Formular. Beachten Sie, dass der Titel der Kontaktnummer in Mobiltelefonnummer geändert wurde.

   ![](/help/assets/headless-adaptive-form.png)

1. Öffnen Sie das Eingabeaufforderungsfenster, das zum Starten des Projekts **react-starter-kit-aem-headless-forms** genutzt wird, drücken Sie **Strg+C**,
geben Sie **Y** ein und drücken Sie die Eingabetaste, um den npm-Prozess zu beenden. Es ist wichtig, den npm-Server anzuhalten, damit er nicht mit dem nächsten Satz von Übungen in Konflikt gerät.

1. Schließen Sie Visual Studio Code und das Eingabeaufforderungsfenster.


## Lektion 5

### Ziel

Rendern des Formulars als Headless-Formular mithilfe der Google Material-Benutzeroberfläche

### Lektionskontext

In dieser Lektion erfahren Sie als Frontend-Entwickler, wie Sie das zuvor erstellte adaptive Formular mithilfe der Google Material-Benutzeroberfläche als Headless-Formular rendern.

### Übung

Richten Sie das lokale Repository mithilfe des Ausgangsprojekts der Material-Benutzeroberfläche ein:

1. Öffnen Sie die Eingabeaufforderung mit Administratorrechten.

   ![](/help/assets/screenshot2028115829.png){width="30%" align="left"}

1. Verwenden Sie in der Eingabeaufforderung den folgenden Befehl, um zum Ordner `c:\git` zu navigieren.

   ```Shell
   cd git
   ```

1. Führen Sie die folgenden Befehle in der angegebenen Reihenfolge aus, um einen Ordner mit dem Namen „mui“ zu erstellen und zu diesem Ordner zu navigieren:

   ```Shell
   mkdir mui
   
   cd mui
   ```

1. Verwenden Sie den folgenden Befehl, um das React-Starter-Projekt des adaptiven Formulars zu klonen:

   ```Shell
   git clone -b mui-lab https://github.com/adobe/react-starter-kit-aem-headless-forms
   ```

   ![](/help/assets/screenshot2028126529.png)

1. Verwenden Sie die folgenden Befehle in der aufgeführten Reihenfolge, um zum Ordner **react-starter-kit-aem-headless-forms** zu navigieren und den Code in Visual Studio Code zu öffnen:

   ```Shell
   cd react-starter-kit-aem-headless-forms
   
   code .
   ```

   ![](/help/assets/screenshot2028126829.png)

So rendern Sie das in Ihrer Veröffentlichungsumgebung gehostete Formular:

1. Benennen Sie die Datei **env_template** in eine Datei **.env** um. Klicken Sie zum Umbenennen mit der rechten Maustaste auf die Datei **env_template** und wählen Sie **Umbenennen**.

   ![](/help/assets/screenshot2028126629.png){width="30%" align="left"}

1. Legen Sie die folgenden Werte für die Variablen in der .env-Datei fest. Speichern Sie die Datei nach dem Aktualisieren der Variablen. Verwenden Sie die Tastenkombination **Strg+S**, um die Datei zu speichern.

   * **AEM_URL**: Geben Sie die URL der Veröffentlichungsumgebung an. Beispiel: [https://localhost:4503](https://localhost:4503)

   * **AEM_FORM_PATH**: Geben Sie den Pfad des in der vorherigen Lektion erstellten adaptiven Formulars an. Beispiel: /content/forms/af/contact-us/


1. Öffnen Sie das Befehlsfenster, stellen Sie sicher, dass Sie sich im Verzeichnis **react-starter-kit-aem-headless-forms** befinden, und führen Sie den folgenden Befehl aus:

   ```Shell
   npm install
   ```

   ![](/help/assets/screenshot2028127029.png)

1. Führen Sie im Eingabeaufforderungsfenster den folgenden Befehl aus:

   ```Shell
   npm start
   ```

   ![](/help/assets/lab65-mui-starter-kit-start.png)

   Der Befehl startet einen lokalen Entwicklungs-Server und rendert die von AEM abgerufene Formulardefinition mithilfe der 
Frontend-Bibliothek der Google Material-Benutzeroberfläche auf eine Headless-Weise.

   >[!NOTE]
   >
   >Wenn nach der Ausführung des Befehls `npm start` für mehr als 3–4 Minuten ein leerer Browser-Bildschirm erscheint, ändern Sie `localhost` in der Browser-URL zu 127.0.0.1 und betätigen Sie die **Eingabetaste**.

   ![](/help/assets/google-mui-form.png)

## Lektion 6

### Ziel

Erstellen Sie ein alternatives Look-and-Feel des Headless-Formulars mithilfe der Komponentenvarianten der Material-Benutzeroberfläche

### Lektionskontext

In dieser Lektion erfahren Sie als Frontend-Entwickler, wie Sie mithilfe der Materialbenutzeroberfläche eine alternative Darstellung verschiedener Komponenten für das adaptive Formular erstellen, das zuvor vom Business-Anwender erstellt wurde.

### Übung

Aktualisieren Sie die Variation der Komponenten im Headless-Projekt. So ändern Sie die Variante der Texteingabekomponente der materiellen Benutzeroberfläche in `OutlinedInput`:

1. Navigieren Sie in Visual Code zur Texteingabekomponente, indem Sie die Datei `index.tsx` unter `src/components/textinput/index.tsx` öffnen.

1. Fügen Sie `//` am Anfang der Code-Zeile 104 hinzu. Die Zeile wird dadurch in einen Kommentar umgewandelt.

   ```Shell
   //const Cmp = \'outlined\' === appliedCssClassNames ? OutlinedInput: Input;
   ```

1. Fügen Sie in Zeile 105 Folgendes hinzu, um eine andere Variante der Komponente zu verwenden und die Datei zu speichern. Verwenden Sie die Tastenkombination **Strg+S**, um die Datei zu speichern.

   ```Shell
   const Cmp = OutlinedInput;
   ```

   ![](/help/assets/aem65-lab-code-update.png)

   Es ist wichtig, die richtige Groß-/Kleinschreibung für die Variante „OutlinedInput“ zu verwenden, da die Kompilierung andernfalls fehlschlagen würde. Die Kompilierung der lokalen Entwicklungsumgebung beginnt automatisch in der Eingabeaufforderung. Warten Sie, bis die folgende Meldung angezeigt wird

   `webpack 5.75.0 compiled with 3 warnings in 6659 ms`
   `inside proxy req`
   `setting new origin header`

1. Aktualisieren Sie den Browser, wenn er nicht automatisch aktualisiert wird, um zu sehen, wie die Texteingabe-Komponente eine andere Variante verwendet.

   ![](/help/assets/screenshot2028127729.png){width="50%" align="left"}


   Diese Änderung erfolgt für Endbenutzerinnen und -benutzer ohne Änderung der Formulardefinition auf dem AEM Forms-Server und ist spezifisch für den betreffenden Headless-Kanal. Beispiel: Web-Kanal in diesem Labor.

   ![](/help/assets/aem65-lab-mui-style-update.png)


1. Schließen Sie Visual Studio Code und das Eingabeaufforderungsfenster.

## Häufig gestellte Fragen (FAQs)

+++ Sind Kernkomponenten öffentlich verfügbar?

Ja, die adaptiven Forms-Kernkomponenten sind mit AEM 6.5 Forms und Forms als Cloud Service verfügbar. Sie benötigen AEM Forms 6.5 Service Pack 16 oder höher, um die Kernkomponenten des adaptiven Forms verwenden zu können.

+++

+++ Benötigen Headless-Formulare eine separate Lizenz?

Nein, Headless-Formulare verwenden dieselbe Metrik für den Lizenzwert, nämlich die Anzahl der Formularübertragungen.

+++




## Nächste Schritte

Nachdem Sie nun gelernt haben, wie Sie adaptive Forms erstellen und über Headless-Formulare an mehrere Kanäle senden, sollten Sie versuchen, Ihre neuen Fähigkeiten in die Tat umzusetzen. Viel Spaß beim Erstellen und Bereitstellen von umfangreichen, außergewöhnlichen Datenerfassungserlebnissen für Ihre Endbenutzerinnen und -benutzer, wo auch immer sie sich befinden!

## Ressourcen

* [Einführung in Kernkomponenten für adaptive Formulare](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=de)

* [Erstellen eines adaptiven Formulars mit Kernkomponenten](https://experienceleague.corp.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=de)

* [Aktualisierungsstile für die auf Kernkomponenten basierenden adaptiven Formulare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=de)

* [Headless Adaptive Forms](https://experienceleague.adobe.com/docs/experience-manager-headless-adaptive-forms/using/overview.html?lang=de)

* [Verwenden des Headless-React-Starter-Kits](https://experienceleague.adobe.com/docs/experience-manager-headless-adaptive-forms/using/get-started/create-and-publish-a-headless-form.html?lang=de)
