---
title: Lotes de instruções | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC], batches
- batches [ODBC]
- ODBC applications, statements
- multiple statements, batches
- SQLMoreResults function
- SQLExecDirect function
ms.assetid: 057d7c1c-1428-4780-9447-a002ea741188
author: rothja
ms.author: jroth
ms.openlocfilehash: 4818b67766dafe851035041c8fd5137a0dfade73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569418"
---
# <a name="batches-of-statements"></a>Lotes de instruções
  Um lote de [!INCLUDE[tsql](../../../includes/tsql-md.md)] instruções contém duas ou mais instruções, separadas por um ponto-e-vírgula (;), criado em uma única cadeia de caracteres passada para a função **SQLExecDirect** ou [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360). Por exemplo:  
  
```  
SQLExecDirect(hstmt,   
    "SELECT * FROM Authors; SELECT * FROM Titles",  
    SQL_NTS);  
```  
  
 Os lotes podem ser mais eficientes do que enviar instruções separadamente porque o tráfego de rede costuma ser reduzido. Use [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) para ficar posicionado no próximo conjunto de resultados quando terminar com o conjunto de resultados atual.  
  
 Os lotes sempre podem ser usados quando os atributos de cursor ODBC são definidos como os padrões de um cursor de somente encaminhamento, somente leitura, com um tamanho do conjunto de linhas igual a 1.  
  
 Caso um lote seja executado durante o uso de cursores de servidor no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], o cursor de servidor é convertido implicitamente em um conjunto de resultados padrão. **SQLExecDirect** ou **SQLExecute** retornam SQL_SUCCESS_WITH_INFO e uma chamada para **SQLGetDiagRec** retorna:  
  
```  
szSqlState = "01S02", pfNativeError = 0  
szErrorMsg = "[Microsoft][SQL Server Native Server Native Client]Cursor type changed."  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Executando instruções &#40;&#41;ODBC](executing-statements-odbc.md)  
  
  
