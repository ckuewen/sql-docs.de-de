---
title: Übersicht über Sicherheitserweiterungen | Microsoft-Dokumentation
description: Hier erfahren Sie mehr über Sicherheitserweiterungen in den Reporting Services. Sehen Sie sich die Situationen an, für die benutzerdefinierte Authentifizierung und Autorisierung geeignet sind.
ms.date: 05/24/2018
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: extensions
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
ms.assetid: 24ccd795-6506-457c-93ac-6a9dd6bb9a46
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 72eaf9b5c47d19da6b7f1893e473031cd6ebc615
ms.sourcegitcommit: 2f166e139f637d6edfb5731510d632a13205eb25
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84529196"
---
# <a name="security-extensions-overview---reporting-services-ssrs"></a>Übersicht über Sicherheitserweiterungen – Reporting Services (SSRS)
  Eine [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Sicherheitserweiterung ermöglicht die Authentifizierung und Autorisierung von Benutzern oder Gruppen. Das heißt, verschiedene Benutzer können sich bei einem Berichtsserver anmelden und anhand ihrer Identitäten verschiedene Aufgaben oder Vorgänge ausführen. [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] verwendet standardmäßig eine Windows-basierte Authentifizierungserweiterung, die mit Windows-Kontoprotokollen die Identitäten von Benutzern überprüft, die angeben, im System über Konten zu verfügen. In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] werden Benutzer mithilfe eines rollenbasierten Sicherheitssystems authentifiziert. Das rollenbasierte Sicherheitsmodell von [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] ähnelt den rollenbasierten Sicherheitsmodellen anderer Technologien.  
  
 Da Sicherheitserweiterungen auf einer offenen und erweiterbaren API beruhen, können Sie neue Authentifizierungs- und Autorisierungserweiterungen in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] erstellen. Im Folgenden sehen Sie ein Beispiel einer typischen Sicherheitserweiterungsimplementierung, die mit formularbasierter Authentifizierung und Autorisierung arbeitet:  
  
 ![Reporting Services-Sicherheitserweiterungsprozess](../../../reporting-services/extensions/security-extension/media/rosettasecurityextensionflow.gif "Reporting Services-Sicherheitserweiterungsprozess")  
  
 Wie in der Abbildung dargestellt, treten Authentifizierung und Autorisierung folgendermaßen auf:  
  
1.  Ein Benutzer versucht über eine URL auf das Webportal zuzugreifen und wird zu einem Formular umgeleitet, das Anmeldeinformationen von Benutzern für die Clientanwendung sammelt.  
  
2.  Der Benutzer gibt die Anmeldeinformationen an das Formular.  
  
3.  Die Anmeldeinformationen des Benutzers werden mithilfe der <xref:ReportService2010.ReportingService2010.LogonUser%2A>-Methode an den Reporting Services-Webdienst übermittelt.  
  
4.  Der Webdienst ruft die vom Benutzer angegebene Sicherheitserweiterung auf und überprüft, ob der Benutzername und das Kennwort in der benutzerdefinierten Sicherheitsinstanz vorhanden sind.  
  
5.  Nach der Authentifizierung erstellt der Webdienst für die Startseite des Webportals ein Authentifizierungsticket (auch „Cookie“ genannt), verwaltet es und überprüft die Rolle des Benutzers.  
  
6.  Der Webdienst gibt das Cookie an den Browser zurück und zeigt die entsprechende Benutzeroberfläche im Webportal an.  
  
7.  Nachdem der Benutzer authentifiziert wurde, sendet der Browser Anforderungen an das Webportal, während das Cookie im HTTP-Header übertragen wird. Diese Anforderungen sind Reaktionen auf Benutzeraktionen im Webportal.  
  
8.  Das Cookie wird zusammen mit der angeforderten Benutzeroperation im HTTP-Header an den Webdienst übertragen.  
  
9. Das Cookie wird überprüft. Wenn es gültig ist, gibt der Berichtsserver die Sicherheitsbeschreibung und andere im Zusammenhang mit der angeforderten Operation stehende Informationen aus der Berichtsserver-Datenbank zurück.  
  
10. Wenn das Cookie gültig ist, ruft der Berichtsserver die Sicherheitserweiterung auf und überprüft, ob der Benutzer zur Ausführung der bestimmten Operation autorisiert ist.  
  
11. Wenn der Benutzer autorisiert ist, führt der Berichtsserver die angeforderte Operation aus und gibt die Steuerung an den Aufrufer zurück.  
  
12. Nach der Authentifizierung des Benutzers verwendet der URL-Zugriff des Berichtsservers dasselbe Cookie. Das Cookie wird im HTTP-Header übertragen.  
  
13. Der Benutzer fordert so lange Operationen auf dem Berichtsserver an, bis die Sitzung beendet ist.  
  
## <a name="when-to-implement-a-security-extension"></a>Sinnvolles Implementieren von Sicherheitserweiterungen  
 Es wird empfohlen, immer die Windows-Authentifizierung zu verwenden. In den folgenden Fällen ist jedoch möglicherweise eine benutzerdefinierte Authentifizierung und Autorisierung für [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] angemessener:  
  
-   Sie haben eine Internet- oder Extranetanwendung, die keine Windows-Konten nutzen kann.  
  
-   Sie haben benutzerdefinierte Benutzer und Rollen, die ein übereinstimmendes Autorisierungsschema in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]bereitstellen müssen.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Implementieren von Sicherheitserweiterungen](../../../reporting-services/extensions/security-extension/implementing-a-security-extension.md)   
  
  
