---
title: Herstellen einer Verbindung mit Azure Arc
titleSuffix: ''
description: Stellen Sie eine Verbindung zwischen einer SQL Server-Instanz und Azure Arc her.
author: anosov1960
ms.author: sashan
ms.reviewer: mikeray
ms.date: 09/10/2020
ms.topic: conceptual
ms.prod: sql
ms.openlocfilehash: e80892bfef7ee2c8cf22aef1b491ab5ea0c0addd
ms.sourcegitcommit: 442fbe1655d629ecef273b02fae1beb2455a762e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93235564"
---
# <a name="connect-your-sql-server-to-azure-arc"></a>Herstellen einer Verbindung zwischen Ihrer SQL Server-Instanz und Azure Arc

Mit den folgenden Schritten können Sie lokal eine Verbindung zwischen Ihrer SQL Server-Instanz und Azure Arc herstellen.

## <a name="prerequisites"></a>Voraussetzungen

* Auf Ihrem Computer ist mindestens eine Instanz von SQL Server installiert.
* Bei Windows-Computern ist Azure PowerShell installiert. Befolgen Sie die Anweisungen zum [Installieren von Azure PowerShell](/powershell/azure/install-az-ps).
* Bei Linux-Computern haben Sie die Azure CLI heruntergeladen und eine Verbindung mit Ihrem Azure-Konto hergestellt. Befolgen Sie die Anweisungen zum [Installieren der Azure CLI](/cli/azure/install-azure-cli-apt).
* Der Ressourcenanbieter **Microsoft.AzureData** wurde registriert. Weitere Informationen zu Ressourcenanbietern finden Sie unter „Azure-Ressourcenanbieter und -typen“.
    * Führen Sie in PowerShell `Register-AzResourceProvider -ProviderNamespace Microsoft.AzureData` aus.
    * Führen Sie unter Linux `az provider register --namespace 'Microsoft.AzureData` aus.



## <a name="generate-a-registration-script-for-sql-server"></a>Generieren eines Registrierungsskripts für SQL Server

In diesem Schritt generieren Sie ein Skript, mit dem alle auf dem Computer installierten SQL Server-Instanzen ermittelt und als Ressourcen vom Typ __SQL Server – Azure Arc__ registriert werden. Wenn der physische oder virtuelle Hostcomputer noch nicht bei Azure Arc registriert ist, holt das Skript dies automatisch nach.

1. Suchen Sie nach dem Ressourcentyp __SQL Server – Azure Arc__ , und fügen Sie über das Erstellungsblatt eine neue solche Ressource hinzu.

![Beginnen mit der Erstellung](media/join/start-creation-of-sql-server-azure-arc-resource.png)
    
2. Überprüfen Sie die Voraussetzungen, und wechseln Sie zur Registerkarte **Serverdetails**.  

3. Wählen Sie das Abonnement, die Ressourcengruppe, die Azure-Region und das Hostbetriebssystem aus. Geben Sie, sofern erforderlich, auch den Proxy an, den Ihr Netzwerk verwendet, um eine Verbindung mit dem Internet herzustellen.

> [!IMPORTANT]
> Wenn der Computer, auf dem die SQL Server-Instanz gehostet wird, bereits [mit Azure Arc verbunden](/azure/azure-arc/servers/onboard-portal) ist, stellen Sie sicher, dass Sie die Ressourcengruppe auswählen, die auch die entsprechende Ressource vom Typ __Computer – Azure Arc__ enthält.

![Serverdetails](media/join/server-details-sql-server-azure-arc.png)

4. Wechseln Sie zur Registerkarte **Skript ausführen** , und laden Sie das angezeigte Registrierungsskript herunter. Das Portal generiert das Skript für das von Ihnen angegebene Hostbetriebssystem.

![Herunterladen des Skripts](media/join/download-script-sql-server-azure-arc.png)

## <a name="connect-the-installed-sql-server-instances-to-azure-arc"></a>Herstellen einer Verbindung zwischen den installierten SQL Server-Instanzen und Azure Arc

In diesem Schritt führen Sie das im Azure-Portal heruntergeladene Skript auf dem physischen oder virtuellen Zielcomputer aus. Dadurch werden alle auf dem Computer installierten SQL Server-Instanzen als Ressourcen vom Typ __SQL Server – Azure Arc__ registriert. Darüber hinaus wird, falls auf dem Computer selbst noch nicht vorhanden, automatisch der Gastkonfigurations-Agent installiert, und der Computer wird als Ressource vom Typ __Computer – Azure Arc__ registriert.

> [!NOTE]
> Stellen Sie sicher, dass Sie das Skript mit einem Konto ausführen, das die unter [Voraussetzungen](overview.md#prerequisites) erläuterten Mindestanforderungen für Berechtigungen erfüllt.

### <a name="windows"></a>Windows

1. Starten Sie eine Administratorinstanz von __powershell.exe__ , und melden Sie sich mit Ihren Azure-Anmeldeinformationen bei Ihrem PowerShell-Modul an. Befolgen Sie hierbei die [Anleitung für die Anmeldung](/powershell/azure/install-az-ps#sign-in).

2. Führen Sie das heruntergeladene Skript aus.

   ```powershell
   & '.\RegisterSqlServerArc.ps1'
   ```

   > [!NOTE]
   > Möglicherweise treten beim ersten Mal Probleme auf, wenn Sie das Az-Modul für PowerShell noch nicht installiert haben. Befolgen Sie in diesem Fall die Anweisungen im Skript für die Installation und das Herstellen einer Verbindung mit Ihrem Azure-Konto, und führen Sie das Skript noch mal aus.

### <a name="linux"></a>Linux

1. Melden Sie sich über die Azure CLI mit Ihren Azure-Anmeldeinformationen an. Befolgen Sie hierbei die [Anleitung für die Anmeldung](/cli/azure/authenticate-azure-cli).

2. Erteilen Sie dem heruntergeladenen Skript die Ausführungsberechtigung, und führen Sie es aus.

   ```bash
   sudo chmod +x ./RegisterSqlServerArc.sh
   ./RegisterSqlServerArc.sh
   ```

## <a name="register-sql-server-instances-on-multiple-machines"></a>Registrieren von SQL Server-Instanzen auf mehreren Computern

Sie können das für einen einzelnen Computer generierte Skript auch verwenden, um mehrere SQL Server-Instanzen, die auf verschiedenen Windows- oder Linux-Computern installiert sind, mit Azure Arc zu verbinden. Befolgen Sie die Anweisungen zum [Herstellen einer Verbindung zwischen SQL Server-Instanzen und Azure Arc im großen Stil](connect-at-scale.md).

## <a name="validate-the-sql-server---azure-arc-resources"></a>Überprüfen der Ressourcen vom Typ „SQL Server – Azure Arc“

Wechseln Sie zum [Azure-Portal](https://ms.portal.azure.com/#home), und öffnen Sie die neu registrierte Ressource vom Typ __SQL Server – Azure Arc__ , um sie zu überprüfen.

![Überprüfen der verbundenen SQL Server-Instanz ](media/join/validate-sql-server-azure-arc.png)

## <a name="un-register-the-sql-server---azure-arc-resources"></a>Aufheben der Registrierung der Ressourcen vom Typ „SQL Server – Azure Arc“

Wenn Sie eine vorhandene Ressource vom Typ __SQL Server – Azure Arc__ entfernen möchten, navigieren Sie zu der Ressourcengruppe, in der sie enthalten ist, und entfernen Sie sie dort aus der Liste der Ressourcen.

![Aufheben der Registrierung einer SQL Server-Instanz](media/join/delete-sql-server-azure-arc.png)

## <a name="next-steps"></a>Nächste Schritte

* [Konfigurieren von erweiterter Datensicherheit für Ihre SQL Server-Instanz](configure-advanced-data-security.md)

* [Konfigurieren der bedarfsgesteuerten SQL-Bewertung für Ihre SQL Server-Instanz](assess.md)