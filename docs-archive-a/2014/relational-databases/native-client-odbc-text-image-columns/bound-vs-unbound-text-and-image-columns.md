---
title: Colunas de texto e imagem acopladas versus não associadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: ffd3442e-d880-46e9-b848-2365a09a2406
author: rothja
ms.author: jroth
ms.openlocfilehash: 20a91d26ac8c2d1201386cb19bde13b49a3dbada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685620"
---
# <a name="bound-vs-unbound-text-and-image-columns"></a>Colunas de texto e imagem associadas vs. não associadas
  Ao usar cursores de servidor, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client é otimizado para não transmitir os dados para colunas **Text**, **ntext**ou **Image** não associadas no momento em que **SQLFetch** é executado. Os dados **Text**, **ntext**ou **Image** não são realmente recuperados do servidor até que o aplicativo emita [SQLGetData](../native-client-odbc-api/sqlgetdata.md) para a coluna.  
  
 Muitos aplicativos podem ser escritos para que nenhum dado de **Text**, **ntext**ou **Image** seja exibido enquanto um usuário está simplesmente rolando para cima e para baixo em um cursor. Quando um usuário seleciona uma linha para obter mais detalhes, o aplicativo pode chamar **SQLGetData** para recuperar os dados de **Text**, **ntext**ou **Image** . Isso impedirá a transmissão dos dados **Text**, **ntext**ou **Image** para qualquer uma das linhas que o usuário não selecionar e, portanto, poderá impedir a transmissão de grandes quantidades de dados.  
  
## <a name="see-also"></a>Consulte Também  
 [Gerenciando colunas de texto e imagem](managing-text-and-image-columns.md)   
 [Comportamentos de cursor](../native-client-odbc-cursors/cursor-behaviors.md)  
  
  
