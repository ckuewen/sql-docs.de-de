---
description: Herstellen einer Verbindung mit SQL Server (MySqlToSql)
title: Herstellen einer Verbindung mit SQL Server (mysqlto SQL) | Microsoft-Dokumentation
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: d73abd3a-80df-4293-b973-1723069db049
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: de3254b236dc03d7474aefe465aae91bef518f09
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88372826"
---
# <a name="connect-to-sql-server-mysqltosql"></a>Herstellen einer Verbindung mit SQL Server (MySqlToSql)
Verwenden Sie das Dialogfeld **mit SQL Server verbinden** , um eine Verbindung mit der Instanz von herzustellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , zu der Sie migrieren möchten. Um auf das Dialogfeld **Verbindung mit SQL Server herstellen** zuzugreifen, klicken Sie im Menü **Datei** auf **Verbinden mit SQL Server**.  
  
## <a name="options"></a>Tastatur  
**Servername**  
Geben Sie die SQL Server-Instanz ein, mit der eine Verbindung hergestellt werden soll. Standardmäßig wird die Instanz angezeigt, mit der Sie zuletzt eine Verbindung hergestellt haben.  
  
-   Wenn Sie eine Verbindung mit der Standard Instanz auf dem lokalen Computer herstellen, können Sie entweder **localhost** oder einen Punkt (**.**) eingeben.  
  
-   Wenn Sie eine Verbindung mit der Standard Instanz auf einem anderen Computer herstellen, geben Sie den Namen des Computers ein.  
  
-   Wenn Sie eine Verbindung mit einer benannten Instanz auf einem anderen Computer herstellen, geben Sie den Computernamen, einen umgekehrten Schrägstrich und den Instanznamen ein, z. b. *myserver* \\ *MyInstance*.  
  
**Serverport**  
Wenn die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht für die Annahme von Verbindungen am Standardport (1433) konfiguriert ist, geben Sie die Portnummer ein. Andernfalls lassen Sie diesen Wert leer.  
  
**Datenbank**  
Gibt die Datenbank an, zu der Objekte und Daten migriert werden sollen. Diese Option ist nicht verfügbar, wenn Sie eine erneute Verbindung mit herstellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
**Authentifizierung**  
Wählen Sie die Authentifizierungsmethode aus, die zum Herstellen einer Verbindung mit verwendet wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Um Ihr aktuelles Windows-Konto zu verwenden, wählen Sie Windows-Authentifizierung aus. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Wählen Sie Authentifizierung aus, um einen Anmelde Namen und ein Kennwort anzugeben [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
**Benutzername**  
Wenn Sie die- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentifizierung verwenden, geben Sie den-Anmelde Namen für diese Instanz von ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Wenn Sie die Windows-Authentifizierung verwenden, ist diese Option nicht verfügbar.  
  
**Kennwort**  
Wenn Sie die- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentifizierung verwenden, geben Sie das Kennwort für die Anmeldung in dieser Instanz von ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Wenn Sie die Windows-Authentifizierung verwenden, ist diese Option nicht verfügbar.  
  
**Verbindung verschlüsseln**  
Wenn Sie eine sichere Verbindung mit SQL Server herstellen möchten, verwenden Sie die Option Verbindung verschlüsseln, indem Sie das Kontrollkästchen **Verbindung verschlüsseln** aktivieren.  
  
**TrustServerCertificate**  
Wenn Sie diese Option verwenden möchten, aktivieren Sie das Kontrollkästchen **Server Zertifikat vertrauen** .  
  
> [!NOTE]  
> Zum Aktivieren des **Trust Server-Zertifikats**muss "verschlüsseln" auf " **true**" festgelegt sein.  
  
