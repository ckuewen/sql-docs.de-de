---
description: Hybridbefehle
title: Hybrid Befehle | Microsoft-Dokumentation
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- shape commands [ADO]
- hybrid commands [ADO]
- data shaping [ADO], hybrid commands
ms.assetid: e8ca40e8-459c-40e2-8dd3-3ec6d5ee7b51
author: rothja
ms.author: jroth
ms.openlocfilehash: ec23a74b26be84684965c8e81fffbfd827a9981a
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "88980511"
---
# <a name="hybrid-commands"></a>Hybridbefehle
Hybrid Befehle sind teilweise parametrisierte Befehle. Beispiel:  
  
```  
SHAPE {select * from plants}   
   APPEND( {select * from customers where country = ?}   
           RELATE PlantCountry TO PARAMETER 0,   
             PlantRegion TO CustomerRegion )   
```  
  
 Das zwischen Speicherungs Verhalten für einen Hybriden Befehl ist identisch mit dem von regulären parametrisierten Befehlen.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Beispiel für Daten Strukturierung](./data-shaping-example.md)   
 [Formale Form Grammatik](./formal-shape-grammar.md)   
 [Shape-Befehle im Allgemeinen](./shape-commands-in-general.md)