---
title: Tarefa Reorganizar Índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.reorganizeindextask.f1
helpviewer_keywords:
- reorganizing indexes
- Reorganize Index task [Integration Services]
- indexes [Integration Services]
ms.assetid: 9ed87861-e5c3-4fcd-8760-d112f4c0af0c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3f910391bd3a5a35770bb677bc17c91a00ace457
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575261"
---
# <a name="reorganize-index-task"></a><span data-ttu-id="2c8c9-102">Tarefa Reorganizar Índice</span><span class="sxs-lookup"><span data-stu-id="2c8c9-102">Reorganize Index Task</span></span>
  <span data-ttu-id="2c8c9-103">A tarefa Reorganizar Índice reorganiza índices em tabelas e exibições de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c8c9-103">The Reorganize Index task reorganizes indexes in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database tables and views.</span></span> <span data-ttu-id="2c8c9-104">Para obter mais informações sobre o gerenciamento de índices, consulte [Reorganizar e recriar índices](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="2c8c9-104">For more information about managing indexes, see [Reorganize and Rebuild Indexes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="2c8c9-105">Utilizando a tarefa Reorganizar Índice, um pacote pode reorganizar índices em um único ou em vários banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2c8c9-105">By using the Reorganize Index task, a package can reorganize indexes in a single database or multiple databases.</span></span> <span data-ttu-id="2c8c9-106">Se a tarefa reorganizar só os índices em um único banco de dados, você poderá escolher as exibições e as tabelas cujos índices a tarefa reorganizará.</span><span class="sxs-lookup"><span data-stu-id="2c8c9-106">If the task reorganizes only the indexes in a single database, you can choose the views or the tables whose indexes the task reorganizes.</span></span> <span data-ttu-id="2c8c9-107">A tarefa Reorganizar Índice também inclui uma opção de compactar dados de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="2c8c9-107">The Reorganize Index task also includes an option to compact large object data.</span></span> <span data-ttu-id="2c8c9-108">Dados de objetos grandes são dados com o tipo de dados `image`, `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)` ou `xml`.</span><span class="sxs-lookup"><span data-stu-id="2c8c9-108">Large object data is data with the `image`, `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, or `xml` data type.</span></span> <span data-ttu-id="2c8c9-109">Para obter mais informações, veja [Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c8c9-109">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
 <span data-ttu-id="2c8c9-110">A tarefa Reorganizar Índice encapsula a instrução Transact-SQL ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="2c8c9-110">The Reorganize Index task encapsulates the Transact-SQL ALTER INDEX statement.</span></span> <span data-ttu-id="2c8c9-111">Se você escolher compactar dados de objeto grandes, a instrução usará a cláusula REORGANIZE WITH (LOB_COMPACTION = ON); caso contrário, LOB_COMPACTION será definido como OFF.</span><span class="sxs-lookup"><span data-stu-id="2c8c9-111">If you choose to compact large object data, the statement uses the REORGANIZE WITH (LOB_COMPACTION = ON) clause, otherwise LOB_COMPACTION is set to OFF.</span></span> <span data-ttu-id="2c8c9-112">Para obter mais informações, consulte [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c8c9-112">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2c8c9-113">O tempo que a tarefa necessita para criar a instrução Transact-SQL que ela executa é proporcional ao número de índices reorganizados pela tarefa.</span><span class="sxs-lookup"><span data-stu-id="2c8c9-113">The time the task takes to create the Transact-SQL statement that the task runs is proportionate to the number of indexes the task reorganizes.</span></span> <span data-ttu-id="2c8c9-114">Se a tarefa for configurada para reorganizar índices em todas as tabelas e exibições em um banco de dados com um grande número de índices ou em vários bancos de dados, ela poderá levar um tempo considerável para gerar a instrução Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="2c8c9-114">If the task is configured to reorganize indexes in all the tables and views in a database that holds a large number of indexes, or to reorganize indexes in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-reorganize-index-task"></a><span data-ttu-id="2c8c9-115">Configuração da tarefa Reorganizar Índice</span><span class="sxs-lookup"><span data-stu-id="2c8c9-115">Configuration of the Reorganize Index Task</span></span>  
 <span data-ttu-id="2c8c9-116">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="2c8c9-116">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="2c8c9-117">Esta tarefa está na seção **Tarefas do Plano de Manutenção** da **Caixa de Ferramentas** , no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c8c9-117">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="2c8c9-118">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="2c8c9-118">For information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="2c8c9-119">Tarefa de Reorganização de Índice &#40;Plano de Manutenção&#41;</span><span class="sxs-lookup"><span data-stu-id="2c8c9-119">Reorganize Index Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/reorganize-index-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="2c8c9-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="2c8c9-120">Related Tasks</span></span>  
 <span data-ttu-id="2c8c9-121">Para obter mais informações sobre como definir essas propriedades no Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , consulte [Definir as propriedades de uma tarefa ou um contêiner](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="2c8c9-121">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c8c9-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2c8c9-122">See Also</span></span>  
 <span data-ttu-id="2c8c9-123">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="2c8c9-123">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="2c8c9-124">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="2c8c9-124">Control Flow</span></span>](control-flow.md)  
  
  
