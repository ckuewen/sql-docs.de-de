---
description: SQLParamData
title: SQLParamData | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLParamData function
ms.assetid: 92349482-ea22-4a6a-8484-e9c6566794fa
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: af2f9651ad0bc8986df1c688e4d94084ddeac0df
ms.sourcegitcommit: 04cf7905fa32e0a9a44575a6f9641d9a2e5ac0f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "91810922"
---
# <a name="sqlparamdata"></a>SQLParamData
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Wenn SQLParamData den einem Tabellenwert Parameter zugeordneten *ValuePtrPtr* -Wert zurückgibt, sollte die Anwendung SQLPutData mit *StrLen_Or_Ind*aufrufen. Wenn *StrLen_Or_Ind* einen Wert größer als 0 (null) aufweist, bedeutet dies, dass die Anwendung bereit ist, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Parameterdaten für die nächste Tabellenwert Parameter-Zeile sammelt. Wenn *StrLen_Or_Ind* den Wert 0 aufweist, bedeutet dies, dass es keine weiteren Daten Zeilen für den Tabellenwert Parameter gibt. Weitere Informationen finden Sie unter [binden und Datenübertragung von Tabellenwert Parametern und Spaltenwerten](../../relational-databases/native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).  
  
 Weitere Informationen zu Tabellenwert Parametern finden Sie unter [Tabellenwert Parameter &#40;ODBC-&#41;](../../relational-databases/native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).  
  
## <a name="see-also"></a>Weitere Informationen  
 [SQLParamData](../../odbc/reference/syntax/sqlparamdata-function.md)   
 [ODBC API Implementation Details](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
