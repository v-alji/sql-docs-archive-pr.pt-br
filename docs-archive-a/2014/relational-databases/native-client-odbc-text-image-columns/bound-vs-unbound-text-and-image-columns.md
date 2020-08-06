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
# <a name="bound-vs-unbound-text-and-image-columns"></a><span data-ttu-id="345a5-102">Colunas de texto e imagem associadas vs. não associadas</span><span class="sxs-lookup"><span data-stu-id="345a5-102">Bound vs. Unbound Text and Image Columns</span></span>
  <span data-ttu-id="345a5-103">Ao usar cursores de servidor, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client é otimizado para não transmitir os dados para colunas **Text**, **ntext**ou **Image** não associadas no momento em que **SQLFetch** é executado.</span><span class="sxs-lookup"><span data-stu-id="345a5-103">When using server cursors, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is optimized to not transmit the data for unbound **text**, **ntext**, or **image** columns at the time **SQLFetch** is performed.</span></span> <span data-ttu-id="345a5-104">Os dados **Text**, **ntext**ou **Image** não são realmente recuperados do servidor até que o aplicativo emita [SQLGetData](../native-client-odbc-api/sqlgetdata.md) para a coluna.</span><span class="sxs-lookup"><span data-stu-id="345a5-104">The **text**, **ntext**, or **image** data is not actually retrieved from the server until the application issues [SQLGetData](../native-client-odbc-api/sqlgetdata.md) for the column.</span></span>  
  
 <span data-ttu-id="345a5-105">Muitos aplicativos podem ser escritos para que nenhum dado de **Text**, **ntext**ou **Image** seja exibido enquanto um usuário está simplesmente rolando para cima e para baixo em um cursor.</span><span class="sxs-lookup"><span data-stu-id="345a5-105">Many applications can be written so that no **text**, **ntext**, or **image** data is displayed while a user is simply scrolling up and down in a cursor.</span></span> <span data-ttu-id="345a5-106">Quando um usuário seleciona uma linha para obter mais detalhes, o aplicativo pode chamar **SQLGetData** para recuperar os dados de **Text**, **ntext**ou **Image** .</span><span class="sxs-lookup"><span data-stu-id="345a5-106">When a user selects a row to get more detail, the application can then call **SQLGetData** to retrieve the **text**, **ntext**, or **image** data.</span></span> <span data-ttu-id="345a5-107">Isso impedirá a transmissão dos dados **Text**, **ntext**ou **Image** para qualquer uma das linhas que o usuário não selecionar e, portanto, poderá impedir a transmissão de grandes quantidades de dados.</span><span class="sxs-lookup"><span data-stu-id="345a5-107">This will prevent transmitting the **text**, **ntext**, or **image** data for any of the rows the user does not select, and can therefore prevent the transmission of very large amounts of data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="345a5-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="345a5-108">See Also</span></span>  
 <span data-ttu-id="345a5-109">[Gerenciando colunas de texto e imagem](managing-text-and-image-columns.md) </span><span class="sxs-lookup"><span data-stu-id="345a5-109">[Managing Text and Image Columns](managing-text-and-image-columns.md) </span></span>  
 [<span data-ttu-id="345a5-110">Comportamentos de cursor</span><span class="sxs-lookup"><span data-stu-id="345a5-110">Cursor Behaviors</span></span>](../native-client-odbc-cursors/cursor-behaviors.md)  
  
  
