---
description: sp_delete_database_firewall_rule (Azure SQL-Datenbank)
title: sp_delete_database_firewall_rule (Azure SQL-Datenbank) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/04/2017
ms.service: sql-database
ms.reviewer: ''
ms.topic: language-reference
f1_keywords:
- sp_delete_database_firewall_rule
- sp_delete_database_firewall_rule_TSQL
- sys.sp_delete_database_firewall_rule
- sys.sp_delete_database_firewall_rule_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_delete_database_firewall_rule procedure
ms.assetid: ed295312-e586-4fc2-9e80-806b490ee7bd
author: VanMSFT
ms.author: vanto
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.openlocfilehash: f4a3a7a16ed2f222a7d179cbae17b6bdfb2982f5
ms.sourcegitcommit: 04cf7905fa32e0a9a44575a6f9641d9a2e5ac0f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "91810332"
---
# <a name="sp_delete_database_firewall_rule-azure-sql-database"></a>sp_delete_database_firewall_rule (Azure SQL-Datenbank)
[!INCLUDE[Azure SQL Database](../../includes/applies-to-version/asdb.md)]

  Entfernt die Firewalleinstellung auf Datenbankebene aus dem [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] . Datenbank-Firewallregeln können für die Master Datenbank und für Benutzer Datenbanken unter konfiguriert und gelöscht werden [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] .   
  
 
## <a name="syntax"></a>Syntax  
  
```    
sp_delete_database_firewall_rule [@name =] [N]'name'
[ ; ]  
```  
  
## <a name="arguments"></a>Argumente  
 `[@name =] [N]'name'`  
 Der Name der Firewalleinstellung auf Datenbankebene, die entfernt wird. *Name ist vom Datentyp* **nvarchar (128)** und hat keinen Standardwert. Der Unicode-Bezeichner `N` ist optional für [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] . 
  
## <a name="permissions"></a>Berechtigungen  
 Firewallregeln auf Datenbankebene können nur von der Prinzipal Anmeldung auf Serverebene oder einem Azure Active Directory Prinzipal, der als Administrator zugewiesen wurde, gelöscht werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Firewalleinstellung auf Datenbankebene mit dem Namen entfernt `Example DB Setting 1` .
  
```  
-- Remove database-level firewall setting  
EXECUTE sp_delete_database_firewall_rule N'Example DB Setting 1';  
  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [Azure SQL-Daten Bank Firewall](/azure/azure-sql/database/firewall-configure)   
 [Vorgehensweise: Konfigurieren von Firewalleinstellungen (Azure SQL-Datenbank)](/azure/azure-sql/database/firewall-configure)   
 [sp_set_firewall_rule &#40;Azure SQL-Datenbank&#41;](../../relational-databases/system-stored-procedures/sp-set-firewall-rule-azure-sql-database.md)   
 [sp_set_database_firewall_rule &#40;Azure SQL-Datenbank&#41;](../../relational-databases/system-stored-procedures/sp-set-database-firewall-rule-azure-sql-database.md)   
 [sys.database_firewall_rules &#40;Azure SQL-Datenbank&#41;](../../relational-databases/system-catalog-views/sys-database-firewall-rules-azure-sql-database.md)  
  
