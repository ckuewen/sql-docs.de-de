---
description: Änderungsnachverfolgung Katalog Sichten-sys.change_tracking_databases
title: sys.change_tracking_databases (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/08/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- change_tracking_databases
- sys.change_tracking_databases_TSQL
- sys.change_tracking_databases
- change_tracking_databases_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.change_tracking_databases
- change tracking [SQL Server], sys.change_tracking_databases
ms.assetid: bb233baa-2991-4904-a0eb-3772b81121a4
author: markingmyname
ms.author: maghan
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 05421e215b41fcf0f1be93b189873c3f0d2aa51c
ms.sourcegitcommit: 04cf7905fa32e0a9a44575a6f9641d9a2e5ac0f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "91810366"
---
# <a name="change-tracking-catalog-views---syschange_tracking_databases"></a>Änderungsnachverfolgung Katalog Sichten-sys.change_tracking_databases
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Gibt eine Zeile für jede Datenbank zurück, für die die Änderungsnachverfolgung aktiviert ist.  

|Spaltenname|Datentyp|Beschreibung|  
|-----------------|---------------|-----------------|  
|database_id|**int**|Die ID der Datenbank. Sie ist innerhalb einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eindeutig.|  
|is_auto_cleanup_on|**bit**|Gibt an, ob Änderungsnachverfolgungsdaten nach der konfigurierten Beibehaltungsdauer automatisch bereinigt werden.<br /><br /> 0 = Aus<br /><br /> 1 = Ein|  
|retention_period|**int**|Wenn die automatische Bereinigung verwendet wird, gibt die Beibehaltungsdauer an, wie lange die Änderungsnachverfolgungsdaten in der Datenbank beibehalten werden.|  
|retention_period_units_desc|**nvarchar(60)**|Gibt die Beschreibung der Aufbewahrungsdauer an:<br /><br /> Minuten<br /><br /> Stunden<br /><br /> Tage|  
|retention_period_units|**tinyint**|Zeiteinheit für die Beibehaltungsdauer:<br /><br /> 1 = Minuten<br /><br /> 2 = Stunden<br /><br /> 3 = Tage|  
  
## <a name="permissions"></a>Berechtigungen  
 Für sys.change_tracking_databases werden die gleichen Berechtigungsprüfungen wie für sys.databases durchgeführt. Wenn der Aufrufer von sys.change_tracking_databases nicht der Besitzer der Datenbank ist, sind zum Anzeigen der entsprechenden Zeile mindestens die Berechtigungen ALTER ANY DATABASE oder VIEW ANY DATABASE auf Serverebene oder die CREATE DATABASE-Berechtigung für die Masterdatenbank oder aktuelle Datenbank erforderlich.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Änderungsnachverfolgung Katalog Sichten &#40;Transact-SQL-&#41;](./catalog-views-transact-sql.md)   
 [Nachverfolgen von Datenänderungen &#40;SQL Server&#41;](../../relational-databases/track-changes/track-data-changes-sql-server.md)  
  
