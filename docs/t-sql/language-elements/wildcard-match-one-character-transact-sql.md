---
description: _ (Platzhalterzeichen - einzelnes zu suchendes Zeichen) (Transact-SQL)
title: _ (Platzhalterzeichen – einzelnes zu suchendes Zeichen) (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/06/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- Match
- wildcard
- _TSQL
- Match One
- _
dev_langs:
- TSQL
helpviewer_keywords:
- wildcard characters [SQL Server]
- _ (wildcard - match one character)
ms.assetid: 11a2ed36-9e21-4bdf-ae20-a31db1434b97
author: rothja
ms.author: jroth
ms.openlocfilehash: 3699c5d71de477cca95b1ec8bacaa3b56b9e438d
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88417076"
---
# <a name="_-wildcard---match-one-character-transact-sql"></a>_ (Platzhalterzeichen - einzelnes zu suchendes Zeichen) (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

Verwenden Sie den Unterstrich _ zum Abgleichen eines beliebigen einzelnen Zeichen bei einem Zeichenfolgenvergleich, der einen Mustervergleich wie `LIKE` oder `PATINDEX` umfasst.  
  
## <a name="examples"></a>Beispiele  

## <a name="a-simple-example"></a>A: Einfaches Beispiel   

Das folgende Beispiel gibt alle Datenbanknamen zurück, die mit dem Buchstaben `m` beginnen und `d` als dritten Buchstaben haben. Der Unterstrich gibt an, dass das zweite Zeichen ein beliebiger Buchstabe sein kann. Die Datenbanken `model` und `msdb` erfüllen diese Kriterien. Die Datenbank `master` erfüllt die Kriterien nicht.

```sql
SELECT name FROM sys.databases
WHERE name LIKE 'm_d%';
```   
[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]   
```
name
-----
model
msdb
```   
Sie verfügen möglicherweise über zusätzliche Datenbanken, die diese Kriterien erfüllen.

Mehrere Unterstriche können mehrere Zeichen darstellen. Wenn Sie die `LIKE`-Kriterien ändern, um zwei Unterstriche einzuschließen, fügt `'m__%` dem Ergebnis die Masterdatenbank hinzu.

### <a name="b-more-complex-example"></a>B: Komplexeres Beispiel
 Im folgenden Beispiel wird der Operator _ zum Suchen aller Personen in der `Person`-Tabelle verwendet, die über einen aus drei Buchstaben bestehenden Vornamen verfügen, der auf `an` endet.  
  
```sql  
-- USE AdventureWorks2012
  
SELECT FirstName, LastName  
FROM Person.Person  
WHERE FirstName LIKE '_an'  
ORDER BY FirstName;  
```  
## <a name="c-escaping-the-underscore-character"></a>C: Versehen von Unterstrichen mit Escapezeichen   
Im folgenden Beispiel werden die Namen von festen Datenbankrollen wie `db_owner` und `db_ddladmin` zurückgegeben, aber auch der Benutzer `dbo`. 

```sql
SELECT name FROM sys.database_principals
WHERE name LIKE 'db_%';
```

Der Unterstrich an der dritten Zeichenposition wird als Platzhalter verwendet und filtert nicht nur nach Prinzipalen, die mit den Buchstaben `db_` beginnen. Setzen Sie den Unterstrich in Klammern (`[_]`), um ihn mit dem Escapezeichen zu versehen. 

```sql
SELECT name FROM sys.database_principals
WHERE name LIKE 'db[_]%';
```   
Jetzt wird der Benutzer `dbo` ausgeschlossen.   
[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]   
```
name
-------------
db_owner
db_accessadmin
db_securityadmin
...
```

  
## <a name="see-also"></a>Weitere Informationen  
 [LIKE &#40;Transact-SQL&#41;](../../t-sql/language-elements/like-transact-sql.md)   
 [PATINDEX &#40;Transact-SQL&#41;](../../t-sql/functions/patindex-transact-sql.md)   
  [% (Platzhalterzeichen – zu suchende(s) Zeichen)](../../t-sql/language-elements/percent-character-wildcard-character-s-to-match-transact-sql.md)   
  [&#91; &#93; (Wildcard - Character(s) to Match) ([ ] (Platzhalterzeichen – zu suchende[s] Zeichen))](../../t-sql/language-elements/wildcard-character-s-to-match-transact-sql.md)   
 [&#91;^&#93; (Wildcard - Character(s) Not to Match) ([^] (Platzhalterzeichen – nicht zu suchende[s] Zeichen))](../../t-sql/language-elements/wildcard-character-s-not-to-match-transact-sql.md)     
  
