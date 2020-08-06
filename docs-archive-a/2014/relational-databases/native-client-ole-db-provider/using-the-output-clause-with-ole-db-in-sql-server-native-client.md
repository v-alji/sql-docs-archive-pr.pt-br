---
title: Usando a cláusula OUTPUT com OLE DB em SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 53deeb99-c088-4fde-844b-b2d91d6de1eb
author: rothja
ms.author: jroth
ms.openlocfilehash: a425ec6269040c72836571b8fa8b51bba4ed8c32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684174"
---
# <a name="using-the-output-clause-with-ole-db-in-sql-server-native-client"></a><span data-ttu-id="a534e-102">Usando a cláusula OUTPUT com OLE DB no SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="a534e-102">Using the OUTPUT Clause with OLE DB in SQL Server Native Client</span></span>
  <span data-ttu-id="a534e-103">Se você usar uma cláusula OUTPUT em um comando INSERT, UPDATE, DELETE ou MERGE, a contagem de linhas afetadas não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="a534e-103">If you use an OUTPUT clause in an INSERT, UPDATE, DELETE, or MERGE command, the count of affected rows is not available.</span></span> <span data-ttu-id="a534e-104">O aplicativo deve contar o número de linhas no conjunto de linhas retornado pela cláusula OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="a534e-104">The application must count the number of rows in the rowset that is returned by the OUTPUT clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a534e-105">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a534e-105">See Also</span></span>  
 [<span data-ttu-id="a534e-106">Criando um aplicativo provedor OLE DB do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="a534e-106">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
