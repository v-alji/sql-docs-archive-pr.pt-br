---
title: Colunas de dados em execução e Text, ntext ou image | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
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
- data-at-execution
- ODBC data-at-execution
- image columns [ODBC]
ms.assetid: 67ffb1a6-f38d-4712-ba64-96bdd41ec2b2
author: rothja
ms.author: jroth
ms.openlocfilehash: 404fade34862fe4705ec440eef7f466a9073250b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685626"
---
# <a name="data-at-execution-and-text-ntext-or-image-columns"></a><span data-ttu-id="0c088-102">Dados em execução e colunas Text, ntext ou Image</span><span class="sxs-lookup"><span data-stu-id="0c088-102">Data-at-Execution and Text, ntext, or Image Columns</span></span>
  <span data-ttu-id="0c088-103">Os dados em execução ODBC são um recurso que permite aos aplicativos trabalhar com quantidades extremamente grandes de dados em parâmetros ou colunas associadas.</span><span class="sxs-lookup"><span data-stu-id="0c088-103">ODBC data-at-execution is a feature that enables applications to work with extremely large amounts of data on bound columns or parameters.</span></span> <span data-ttu-id="0c088-104">Ao recuperar colunas de **texto**, **ntext**ou **Image** muito grandes, um aplicativo pode não ser capaz de simplesmente alocar um buffer enorme, associar a coluna ao buffer e buscar a linha.</span><span class="sxs-lookup"><span data-stu-id="0c088-104">When retrieving very large **text**, **ntext**, or **image** columns, an application may not be able to simply allocate a huge buffer, bind the column into the buffer, and fetch the row.</span></span> <span data-ttu-id="0c088-105">Ao atualizar colunas de **texto**, **ntext**ou **Image** muito grandes, o aplicativo pode não ser capaz de simplesmente alocar um buffer enorme, associá-lo a um marcador de parâmetro em uma instrução SQL e, em seguida, executar a instrução.</span><span class="sxs-lookup"><span data-stu-id="0c088-105">When updating very large **text**, **ntext**, or **image** columns, the application might not be able to simply allocate a huge buffer, bind it to a parameter marker in an SQL statement, and then execute the statement.</span></span> <span data-ttu-id="0c088-106">Nesses casos, o aplicativo deve usar [SQLGetData](../native-client-odbc-api/sqlgetdata.md) ou [SQLPutData](../native-client-odbc-api/sqlputdata.md) com suas opções de dados em execução.</span><span class="sxs-lookup"><span data-stu-id="0c088-106">In these cases, the application must use [SQLGetData](../native-client-odbc-api/sqlgetdata.md) or [SQLPutData](../native-client-odbc-api/sqlputdata.md) with its data-at-execution options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c088-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0c088-107">See Also</span></span>  
 [<span data-ttu-id="0c088-108">Gerenciando colunas de texto e imagem</span><span class="sxs-lookup"><span data-stu-id="0c088-108">Managing Text and Image Columns</span></span>](managing-text-and-image-columns.md)  
  
  
