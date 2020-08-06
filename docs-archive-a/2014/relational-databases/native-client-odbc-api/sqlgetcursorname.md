---
title: SQLGetCursorName | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetCursorName function
ms.assetid: 3a427a23-28ef-49aa-b9ec-6cab0914bdf3
author: rothja
ms.author: jroth
ms.openlocfilehash: 01ce6e42b4e8753d07309ec7ce298d4f743d4a6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568552"
---
# <a name="sqlgetcursorname"></a>SQLGetCursorName
  Se o aplicativo não especificar um nome de cursor, o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client irá gerar um nome durante a criação do cursor. O aplicativo pode usar **SQLGetCursorName** para recuperar o nome de cursor definido pelo driver para as instruções UPDATE e DELETE posicionadas. O aplicativo não precisa chamar **SQLSetCursorName** para aproveitar as instruções de manipulação de dados posicionadas.  
  
## <a name="see-also"></a>Consulte Também  
 [Função SQLGetCursorName](https://go.microsoft.com/fwlink/?LinkId=59349)   
 [ODBC API Implementation Details](odbc-api-implementation-details.md)  
  
  
