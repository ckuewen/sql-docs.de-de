---
title: 'azdata notebook: Referenz'
titleSuffix: SQL Server big data clusters
description: Referenzartikel zu azdata notebook-Befehlen.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: seanw
ms.date: 09/22/2020
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: 4a0e171861d01d7a3afe7904905d373aa5e57639
ms.sourcegitcommit: 22e97435c8b692f7612c4a6d3fe9e9baeaecbb94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92678731"
---
# <a name="azdata-notebook"></a>azdata notebook

Gilt für [!INCLUDE [azure-data-cli-azdata](../../includes/azure-data-cli-azdata.md)]e

Der folgende Artikel enthält Referenzinformationen zu den **sql** -Befehlen im **azdata** -Tool. Weitere Informationen zu anderen **azdata** -Befehlen finden Sie unter [azdata](reference-azdata.md).

## <a name="commands"></a>Befehle

|Get-Help|BESCHREIBUNG|
| --- | --- |
[azdata notebook view](#azdata-notebook-view) | Anzeigen eines Notebooks.  Option zum Anhalten beim ersten Zellenausführungsfehler.
[azdata notebook run](#azdata-notebook-run) | Ausführen eines Notebooks.  Die Ausführung wird beim ersten Fehler angehalten.
## <a name="azdata-notebook-view"></a>azdata notebook view
Dieser Befehl kann eine Notebook-Datei einlesen und den Markdown, den Code und die Ausgabe in das Format für ein Farbterminal konvertieren.
```bash
azdata notebook view --path -p 
                     [--continue-on-error -c]
```
### <a name="examples"></a>Beispiele
Zeigen Sie ein Notebook an.  Hiermit werden alle Zellen angezeigt.
```bash
azdata notebook view --path "/home/me/notebooks/demo_notebook.ipynb"
```
Zeigen Sie ein Notebook an.  Hiermit werden alle Zellen angezeigt, es sei denn, es wird eine Zelle festgestellt, in deren Ausgabe ein Fehler vorliegt.  In diesem Fall wird die Ausgabe angehalten.
```bash
azdata notebook view --path "/home/me/notebooks/demo_notebook.ipynb" --stop-on-error
```
### <a name="required-parameters"></a>Erforderliche Parameter
#### `--path -p`
Der Pfad zu dem Notebook, das angezeigt werden soll.
### <a name="optional-parameters"></a>Optionale Parameter
#### `--continue-on-error -c`
Das Anzeigen weiterer Zellen wird fortgesetzt, und alle Zellenfehler, die in der Notebook-Ausgabe gefunden werden, werden ignoriert.  Das Standardverhalten ist, dass bei einem Fehler angehalten wird.  Durch das Anhalten ist es einfacher, die erste Zelle zu sehen, für ein Fehler aufgetreten ist.
### <a name="global-arguments"></a>Globale Argumente
#### `--debug`
Ausführlichkeit der Protokollierung erhöhen, um alle Debugprotokolle anzuzeigen.
#### `--help -h`
Zeigen Sie diese Hilfemeldung an, und schließen Sie sie.
#### `--output -o`
Ausgabeformat.  Zulässige Werte: json, jsonc, table, tsv.  Standardwert: json.
#### `--query -q`
JMESPath-Abfragezeichenfolge. Weitere Informationen und Beispiele finden Sie unter [http://jmespath.org/](http://jmespath.org).
#### `--verbose`
Ausführlichkeit der Protokollierung erhöhen. „--debug“ für vollständige Debugprotokolle verwenden.
## <a name="azdata-notebook-run"></a>azdata notebook run
Dieser Befehl erstellt ein temporäres Verzeichnis und führt das angegebene Notebook in diesem Verzeichnis aus, das als Arbeitsverzeichnis fungiert.
```bash
azdata notebook run --path -p 
                    [--output-path]  
                    
[--output-html]  
                    
[--arguments -a]  
                    
[--interactive -i]  
                    
[--clear -c]  
                    
[--timeout -t]
```
### <a name="examples"></a>Beispiele
Führen Sie das Notebook aus.
```bash
azdata notebook run --path "/home/me/notebooks/demo_notebook.ipynb"
```
### <a name="required-parameters"></a>Erforderliche Parameter
#### `--path -p`
Der Dateipfad zu dem Notebook, das ausgeführt werden soll.
### <a name="optional-parameters"></a>Optionale Parameter
#### `--output-path`
Der Verzeichnispfad, der für die Notebook-Ausgabe verwendet werden soll.  Das Notebook mit Ausgabedaten und alle vom Notebook erstellten Dateien werden relativ zu diesem Verzeichnis generiert.
#### `--output-html`
Optionales Flag, das angibt, ob das ausgegebene Notebook zusätzlich in das HTML-Format konvertiert werden soll.  Erstellt eine zweite Ausgabedatei.
#### `--arguments -a`
Optionale Liste mit Notebookargumenten, die in die Notebookausführung eingefügt werden sollen  Als JSON-Wörterbuch codiert  Beispiel: '{"Name":"Wert", "Name2":"Wert2"}'
#### `--interactive -i`
Führen Sie ein Notebook in einem interaktiven Modus aus.
#### `--clear -c`
Deaktivieren Sie im interaktiven Modus die Konsole, bevor Sie eine Zelle rendern.
#### `--timeout -t`
Dauer in Sekunden, bis die Ausführung beendet ist Der Wert „-1“ gibt an, dass die Wartezeit unbegrenzt ist.
`600`
### <a name="global-arguments"></a>Globale Argumente
#### `--debug`
Ausführlichkeit der Protokollierung erhöhen, um alle Debugprotokolle anzuzeigen.
#### `--help -h`
Zeigen Sie diese Hilfemeldung an, und schließen Sie sie.
#### `--output -o`
Ausgabeformat.  Zulässige Werte: json, jsonc, table, tsv.  Standardwert: json.
#### `--query -q`
JMESPath-Abfragezeichenfolge. Weitere Informationen und Beispiele finden Sie unter [http://jmespath.org/](http://jmespath.org).
#### `--verbose`
Ausführlichkeit der Protokollierung erhöhen. „--debug“ für vollständige Debugprotokolle verwenden.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu anderen **azdata** -Befehlen finden Sie unter [azdata](reference-azdata.md). 

Weitere Informationen zur Installation des Tools **azdata** finden Sie unter [Installieren von azdata](..\install\deploy-install-azdata.md).

