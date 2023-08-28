---
title: Aktivieren von Headless Adaptive Forms auf AEM Forms as a Cloud Service
seo-title: Step-by-Step Guide for enabling Headless Adaptive Forms on AEM Forms as a Cloud Service
description: In unserer schrittweisen Anleitung erfahren Sie, wie Sie in AEM Forms Headless-adaptive Formulare as a Cloud Service aktivieren können. Unser Tutorial führt Sie durch den Prozess, wodurch es einfach wird, diese leistungsstarke Funktion für Ihre AEM Forms-Umgebung zu aktivieren.
seo-description: Learn how to enable headless adaptive forms on AEM Forms as a Cloud Service with our step-by-step guide. Our tutorial walks you through the process, making it easy to enable this powerful feature for your AEM Forms environment.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin
level: Beginner, Intermediate
contentOwner: Khushwant Singh
docset: CloudService
hide: true
hidefromtoc: true
exl-id: 7c545ca6-cb2d-4d28-b9e8-b6efe3faee00
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 7%

---

# Aktivieren von Headless Adaptive Forms auf AEM Forms as a Cloud Service {#enable-headless-adaptive-forms-on-aem-forms-cloud-service}

Durch die Aktivierung von Headless Adaptive Forms auf AEM Forms as a Cloud Service können Sie mit der Erstellung, Veröffentlichung und Bereitstellung von Headless Forms mit Ihren AEM Forms Cloud Service-Instanzen für mehrere Kanäle beginnen. Sie benötigen eine Umgebung mit aktivierten adaptiven Forms-Kernkomponenten, um Headless Adaptive Forms zu verwenden.

## Überlegungen

* Wenn Sie ein neues as a Cloud Service AEM Forms-Programm erstellen, [Headless Adaptive Forms sind bereits für Ihre Umgebungen aktiviert](#are-adaptive-forms-core-components-enabled-for-my-environment).

* Wenn Sie über ein älteres as a Cloud Service Forms-Programm verfügen, in dem Kernkomponenten [nicht aktiviert](#enable-components), können Sie [Adaptive Forms-Kernkomponenten-Abhängigkeiten hinzufügen](#enable-headless-adaptive-forms-for-an-aem-forms-as-a-cloud-service-environment) in Ihr AEM as a Cloud Service Repository kopieren und das Repository in Ihren Cloud Service-Umgebungen bereitstellen, um Headless Adaptive Forms zu aktivieren.

* Wenn Ihre bestehende Cloud Service-Umgebung eine Option bietet, [Erstellen von auf Kernkomponenten basierenden adaptiven Forms](create-a-headless-adaptive-form.md), &quot;Headless Adaptive Forms&quot;sind bereits für Ihre Umgebung aktiviert und Sie können auf Kernkomponenten basierende adaptive Forms als Headless-Formulare für Kanäle wie Mobilgeräte, Web, native Apps und Dienste bereitstellen, für die eine Headless-Darstellung des adaptiven Forms erforderlich ist.


>[!NOTE]
>
>
> Adobe bietet Adaptive Forms [Starter-Kit (React App)](create-and-publish-a-headless-form.md) um Entwicklern zu helfen, schnell mit der Headless Adaptive Forms-Entwicklung zu beginnen, ohne Headless Adaptive Forms in der as a Cloud Service AEM Forms-Umgebung zu aktivieren. Sie können die Headless-Adaptive Forms in einer as a Cloud Service Forms-Umgebung später nach einem [Schnelles Handhaben mit der Entwicklung von Headless-Formularen](create-and-publish-a-headless-form.md).

## Aktivieren von Headless Adaptive Forms für eine as a Cloud Service AEM Forms-Umgebung

Führen Sie die folgenden Schritte in der angegebenen Reihenfolge aus, um Headless Adaptive Forms für eine as a Cloud Service AEM Forms-Umgebung zu aktivieren


![](/help/assets/enable-headless-adaptive-forms-on-aem-forms-cloud-service.png)


## 1. Klonen Sie Ihr as a Cloud Service AEM Forms-Git-Repository. {#clone-git-repository}

1. Anmelden bei [Cloud Manager](https://my.cloudmanager.adobe.com/) und wählen Sie Ihre Organisation und das Programm aus.

1. Navigieren Sie zum **Pipelines** Karte aus **Programmübersicht** klicken Sie auf die **Zugriff auf Repo Info** -Schaltfläche, um auf Ihr Git-Repository zuzugreifen und es zu verwalten. Die Seite enthält die folgenden Informationen:

   * URL zum Cloud Manager-Git-Repository.
   * Anmeldeinformationen des Git-Repositorys (Benutzername und Kennwort) Git-Benutzernamen.

   Klicks **Kennwort generieren** , um das Kennwort anzuzeigen oder zu generieren.

1. Öffnen Sie das Terminal oder die Eingabeaufforderung auf Ihrem lokalen Computer und führen Sie den folgenden Befehl aus:

   ```Shell
   git clone [Git Repository URL]
   ```

   Geben Sie bei Aufforderung die Anmeldeinformationen ein. Das Repository wird auf Ihrem lokalen Computer geklont.


## 2. Hinzufügen von Abhängigkeiten von adaptiven Forms-Kernkomponenten zu Ihrem Git-Repository {#add-adaptive-forms-core-components-dependencies}

1. Öffnen Sie den Ordner &quot;Git-Repository&quot;in einem Texteditor. Beispiel: VS Code.
1. Öffnen Sie die Datei `[AEM Repository Folder]\pom.xml`, um sie zu bearbeiten.
1. Ersetzen von Versionen der `core.forms.components.version`, `core.forms.components.af.version` und `core.wcm.components.version` Komponenten mit den in [Dokumentation zu Kernkomponenten](https://github.com/adobe/aem-core-forms-components). Wenn die Komponente nicht vorhanden ist, fügen Sie diese Komponenten hinzu.

   ```XML
   <!-- Replace the version with the latest released version at https://github.com/adobe/aem-core-forms-components/tags -->
   
   <properties>
       <core.forms.components.version>2.0.14</core.formscomponents.version>
       <core.forms.components.af.version>2.0.14</core.forms.components.af.version>  
       <core.wcm.components.version>2.21.2</core.wcmcomponents.version>
   </properties>
   ```

   ![Erwähnen der neuesten Version der Forms-Kernkomponenten](/help/assets/latest-forms-component-version.png)

1. Im Abschnitt Abhängigkeiten des `[AEM Repository Folder]\pom.xml` , fügen Sie die folgenden Abhängigkeiten hinzu und speichern Sie die Datei.

   ```XML
       <!-- WCM Core Component Examples Dependencies -->
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.apps</artifactId>
               <type>zip</type>
               <version>${core.wcm.components.version}</version>
           </dependency>
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.content</artifactId>
               <type>zip</type>
               <version>${core.wcm.components.version}</version>
           </dependency>
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.config</artifactId>
               <version>${core.wcm.components.version}</version>
               <type>zip</type>
           </dependency>    
           <!-- End of WCM Core Component Examples Dependencies -->
           <!-- Forms Core Component Dependencies -->
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-core</artifactId>
               <version>${core.forms.components.version}</version>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-apps</artifactId>
               <version>${core.forms.components.version}</version>
               <type>zip</type>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-af-core</artifactId>
               <version>${core.forms.components.version}</version>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-af-apps</artifactId>
               <version>${core.forms.components.version}</version>
               <type>zip</type>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-examples-apps</artifactId>
               <type>zip</type>
               <version>${core.forms.components.version}</version>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-examples-content</artifactId>
               <type>zip</type>
               <version>${core.forms.components.version}</version>
           </dependency>
   <!-- End of AEM Forms Core Component Dependencies -->
   ```

1. Öffnen Sie die Datei `[AEM Repository Folder]/all/pom.xml` zum Bearbeiten. Fügen Sie die folgenden Abhängigkeiten in die `<embeddeds>` und speichern Sie die Datei.

   ```XML
   <!-- WCM Core Component Examples Dependencies -->
   
   <!-- inside plugin config of filevault-package-maven-plugin -->  
   <!-- embed wcm core components examples artifacts -->
   
   <embedded>
       <groupId>com.adobe.cq</groupId>
       <artifactId>core.wcm.components.examples.ui.apps</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/content/install</target>
   </embedded>
   <embedded>
       <groupId>com.adobe.cq</groupId>
       <artifactId>core.wcm.components.examples.ui.content</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/content/install</target>
   </embedded>
   <embedded>
       <groupId>com.adobe.cq</groupId>
       <artifactId>core.wcm.components.examples.ui.config</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/content/install</target>
   </embedded>
   <!-- embed forms core components artifacts -->
   <embedded>
       <groupId>com.adobe.aem</groupId>
       <artifactId>core-forms-components-af-apps</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/application/install</target>
   </embedded>
   <embedded>
       <groupId>com.adobe.aem</groupId>
       <artifactId>core-forms-components-af-core</artifactId>
       <target>/apps/${appId}-vendor-packages/application/install</target>
   </embedded>
   <embedded>
       <groupId>com.adobe.aem</groupId>
       <artifactId>core-forms-components-examples-apps</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/content/install</target>
   </embedded>
   <embedded>
       <groupId>com.adobe.aem</groupId>
       <artifactId>core-forms-components-examples-content</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/content/install</target>
   </embedded>
   ```

   >[!NOTE]
   >
   >
   >  Ersetzen `${appId}` mit Ihrer appId.
   >
   >  Suchen Sie nach `${appId}`in der `[AEM Repository Folder]/all/pom.xml` -Datei, suchen Sie die `-packages/application/install` Begriff. Der Text vor dem `-packages/application/install` ist `${appId}`. Der folgende Code beispielsweise `myheadlessform` is `${appId}`.
   >
   >   ```
   >             <embedded>
   >                     <groupId>com.myheadlessform</groupId>
   >                     <artifactId>myheadlessform.ui.apps<artifactId>
   >                     <type>zip</type>
   >                   <target>/apps/myheadlessform-packages/application install</target>
   >             </embedded>
   >   ```

1. Im `<dependencies>` Abschnitt `[AEM Repository Folder]/all/pom.xml` , fügen Sie die folgenden Abhängigkeiten hinzu und speichern Sie die Datei:

   ```XML
           <!-- Other existing dependencies -->
           <!-- wcm core components examples dependencies -->
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.apps</artifactId>
               <type>zip</type>
           </dependency>
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.config</artifactId>
               <type>zip</type>
               </dependency>
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.content</artifactId>
               <type>zip</type>
           </dependency>
               <!-- forms core components dependencies -->
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-af-apps</artifactId>
               <type>zip</type>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-examples-apps</artifactId>
               <type>zip</type>
           </dependency>
               <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-examples-content</artifactId>
               <type>zip</type>
           </dependency>
   ```

1. Öffnen Sie `[AEM Repository Folder]/ui.apps/pom.xml` zur Bearbeitung. Fügen Sie die `af-core bundle` Abhängigkeiten erstellen und die Datei speichern.

   ```XML
       <dependency>
       <groupId>com.adobe.aem</groupId>
       <artifactId>core-forms-components-af-core</artifactId>
       </dependency>
   ```

   >[!NOTE]
   >
   >Achten Sie darauf, dass die folgenden Artefakte der Kernkomponenten von adaptiven Formularen nicht in Ihr Projekt eingeschlossen werden.
   >
   > `<dependency>`
   >
   >   `<groupId>com.adobe.aem</groupId>`
   >   `<artifactId>core-forms-components-apps</artifactId>`
   >
   > `</dependency>`
   >
   > und
   >
   > `<dependency>`
   >
   >   `<groupId>com.adobe.aem</groupId>`
   >   `<artifactId>core-forms-components-core</artifactId>`
   >
   > `</dependency>`


1. Speichern und schließen Sie die Datei.

## 3. Aktualisieren Sie das Projekt, um die neueste Version der Forms-Kernkomponenten einzuschließen:

1. Öffnen Sie die [AEM Archetyp-Projektordner]/pom.xml zur Bearbeitung.


1. Speichern und schließen Sie die Datei.

## 4. Übertragen Sie die Aktualisierungen in Ihr Git-Repository und führen Sie die Pipeline aus, um das Repository bereitzustellen. {#Commit-the-updates-to-your-git-repository}

1. So übertragen Sie Code in Ihr Git-Repository:
   1. Öffnen Sie das Terminal oder die Eingabeaufforderung.
   1. Navigieren Sie zu Ihrer `[AEM Repository Folder]` und führen Sie die folgenden Befehle in der angegebenen Reihenfolge aus

      ```Shell
      git add pom.xml
      git add all/pom.xml
      git add ui.apps/pom.xml
      git commit -m "Added dependencies for Adaptive Forms Core Components"
      git push origin
      ```

1. Nachdem die Dateien in das Git-Repository übertragen wurden, [Pipeline ausführen](https://experienceleague.adobe.com/docs/experience-manager-cloud-manager/using/how-to-use/deploying-code.html?lang=de).

   Nach erfolgreicher Pipelineausführung sind die adaptiven Forms-Kernkomponenten für die entsprechende Umgebung aktiviert. Außerdem werden Ihrer as a Cloud Service Forms-Umgebung eine Vorlage für adaptive Forms (Kernkomponenten) und ein Design für Arbeitsfläche 3.0 hinzugefügt, die Ihnen Optionen zum Anpassen und Erstellen von Kernkomponenten auf Basis von Adaptives Forms bietet.


## Häufig gestellte Fragen {#faq}

### Was sind Kernkomponenten? {#core-components}

Die [Kernkomponenten](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=de) sind eine Reihe standardisierter Web Content Management (WCM)-Komponenten, mit denen AEM die Entwicklungszeit verkürzen und die Wartungskosten Ihrer Websites reduzieren können.

### Welche Funktionen wurden zur Aktivierung von Kernkomponenten hinzugefügt? {#core-components-capabilities}

Wenn die adaptiven Forms-Kernkomponenten für Ihre Umgebung aktiviert sind, werden Ihrer Umgebung eine leere, auf Kernkomponenten basierende Vorlage für adaptive Formulare und ein Canvas 3.0-Design hinzugefügt. Nachdem Sie die adaptiven Forms-Kernkomponenten für Ihre Umgebung aktiviert haben, können Sie Folgendes tun:

* Erstellen Sie auf Kernkomponenten basierende adaptive Forms.
* Erstellen Sie auf Kernkomponenten basierende Vorlagen für adaptive Formulare.
* Erstellen Sie benutzerdefinierte Designs für auf Kernkomponenten basierende Vorlagen für adaptive Formulare.
* Bereitstellung der JSON-Darstellungen des auf Kernkomponenten basierenden adaptiven Formulars in Kanälen wie Mobilgeräten, Web, nativen Apps und Diensten, die die Headless-Darstellung eines Formulars erfordern.

### Sind adaptive Forms-Kernkomponenten für meine Umgebung aktiviert? {#enable-components}

So prüfen Sie, ob die Kernkomponenten der adaptiven Forms für Ihre Umgebung aktiviert sind:

1. [As a Cloud Service AEM Forms-Repository klonen](#1-clone-your-aem-forms-as-a-cloud-service-git-repository).

1. Öffnen Sie die `[AEM Repository Folder]/all/pom.xml` -Datei Ihres AEM Forms Cloud Service-Git-Repositorys.

1. Suchen Sie nach den folgenden Abhängigkeiten:

   * core-forms-components-af-core
   * core-forms-components-core
   * core-forms-components-apps
   * core-forms-components-af-apps
   * core-forms-components-example-apps
   * core-forms-components-examples-content


   ![Suchen Sie das Artefakt core-forms-components-af-core in all/pom.xml .](/help/assets/enable-headless-adaptive-forms-on-aem-forms-cloud-service-locate-core-af-artifact.png)

   Wenn die Abhängigkeiten vorhanden sind, sind die adaptiven Forms-Kernkomponenten für Ihre Umgebung aktiviert.
