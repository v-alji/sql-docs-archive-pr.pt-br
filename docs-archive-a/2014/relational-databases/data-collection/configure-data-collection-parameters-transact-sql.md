---
title: Configurar parâmetros de coleta de dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
ms.assetid: 850905b6-35d2-4ed1-ab51-de64daa832b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a8333b47612b4fbd933ef132e886b8125ffb58a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681691"
---
# <a name="configure-data-collection-parameters-transact-sql"></a><span data-ttu-id="a4270-102">Configurar parâmetros de coleta de dados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a4270-102">Configure Data Collection Parameters (Transact-SQL)</span></span>
  <span data-ttu-id="a4270-103">Antes de criar um conjunto de coleta personalizado, primeiro configure os parâmetros da coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="a4270-103">Before you create a custom collection set, you must first configure data collection parameters.</span></span> <span data-ttu-id="a4270-104">Isso pode ser feito usando os procedimentos armazenados fornecidos com o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="a4270-104">You can do this by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="a4270-105">A realização dessa tarefa envolve o uso do Editor de Consultas no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para aplicar o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="a4270-105">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4270-106">Você configura apenas uma vez os parâmetros de coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="a4270-106">You only configure data collection parameters once.</span></span> <span data-ttu-id="a4270-107">Depois da configuração, esses parâmetros são usados para qualquer conjunto de coleta adicional que você criar.</span><span class="sxs-lookup"><span data-stu-id="a4270-107">After configuration, these parameters are used for any additional collection sets that you create.</span></span>  
  
### <a name="configure-data-collection-parameters"></a><span data-ttu-id="a4270-108">Configurar parâmetros de coleta de dados</span><span class="sxs-lookup"><span data-stu-id="a4270-108">Configure data collection parameters</span></span>  
  
1.  <span data-ttu-id="a4270-109">Em [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte ao banco de dados onde você quer criar um conjunto de coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="a4270-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the database where you want to create a custom collection set.</span></span>  
  
2.  <span data-ttu-id="a4270-110">No Editor de Consultas, emita as seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="a4270-110">In Query Editor, issue the following statements.</span></span>  
  
    ```sql  
    USE msdb;  
    EXEC sp_syscollector_set_warehouse_instance_name N'INSTANCE_NAME';-- where instance name is the name of the SQL Server instance  
    EXEC sp_syscollector_set_warehouse_database_name N'MDW';  
    EXEC sp_syscollector_set_cache_directory N'D:\tempdata';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a4270-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4270-111">See Also</span></span>  
 <span data-ttu-id="a4270-112">[Coleta de Dados](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="a4270-112">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="a4270-113">Procedimentos armazenados de coletor de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a4270-113">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
