---
description: sys.pdw_health_components (Transact-SQL)
title: sys.pdw_health_components (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: conceptual
ms.assetid: d5c7589b-09b0-4f12-ab84-feb3ec3fbaaa
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 2b27f535bbe440e3ce09602b4c1098a33d3883f2
ms.sourcegitcommit: 22dacedeb6e8721e7cdb6279a946d4002cfb5da3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92034809"
---
# <a name="syspdw_health_components-transact-sql"></a>sys.pdw_health_components (Transact-SQL)
[!INCLUDE [pdw](../../includes/applies-to-version/pdw.md)]

  Speichert Informationen zu allen Komponenten und Geräten, die im System vorhanden sind. Dazu zählen Hardware, Speichergeräte und Netzwerkgeräte.  
  
|Spaltenname|Datentyp|BESCHREIBUNG|Range|  
|-----------------|---------------|-----------------|-----------|  
|component_id|**int**|Eindeutiger Bezeichner einer Komponente oder eines Geräts.<br /><br /> Der Schlüssel für diese Ansicht.|NOT NULL|  
|group_id|**Int**|Die logische Komponentengruppe, zu der diese Komponente gehört. Weitere Informationen finden Sie unter [sys.pdw_health_components (Parallel Data Warehouse)](../../relational-databases/system-catalog-views/sys-pdw-health-components-transact-sql.md).|NOT NULL|  
|component_name|**nvarchar(255)**|Der Name der Komponente.|NOT NULL|  
  
## <a name="see-also"></a>Weitere Informationen  
 [Katalogsichten von Azure Synapse Analytics und Parallel Data Warehouse Catalog](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)  
  
  
