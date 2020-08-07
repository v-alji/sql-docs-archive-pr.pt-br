---
title: Tarefa recompilar índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rebuildindextask.f1
helpviewer_keywords:
- rebuilding indexes
- indexes [Integration Services]
- Rebuild Index task
ms.assetid: 021884dd-e72d-47b2-99e8-b741410509c3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33bbe25bc8c47f4f749f95dbb7096c3a76c25297
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575263"
---
# <a name="rebuild-index-task"></a><span data-ttu-id="dbc11-102">Tarefa Recriar Índice</span><span class="sxs-lookup"><span data-stu-id="dbc11-102">Rebuild Index Task</span></span>
  <span data-ttu-id="dbc11-103">A tarefa Recriar Índice recria índices em tabelas e exibições de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dbc11-103">The Rebuild Index task rebuilds indexes in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database tables and views.</span></span> <span data-ttu-id="dbc11-104">Para obter mais informações sobre o gerenciamento de índices, consulte [Reorganizar e recriar índices](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="dbc11-104">For more information about managing indexes, see [Reorganize and Rebuild Indexes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="dbc11-105">Utilizando a tarefa Recriar Índice, um pacote pode reconstruir índices em um único banco de dados ou em vários bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="dbc11-105">By using the Rebuild Index task, a package can rebuild indexes in a single database or multiple databases.</span></span> <span data-ttu-id="dbc11-106">Se a tarefa recriar somente os índices em um único banco de dados, você poderá escolher as exibições e as tabelas cujos índices a tarefa recriará.</span><span class="sxs-lookup"><span data-stu-id="dbc11-106">If the task rebuilds only the indexes in a single database, you can choose the views and tables whose indexes the task rebuilds.</span></span>  
  
 <span data-ttu-id="dbc11-107">Essa tarefa encapsula uma instrução ALTER INDEX REBUILD com as seguintes opções de recriação de índice:</span><span class="sxs-lookup"><span data-stu-id="dbc11-107">This task encapsulates an ALTER INDEX REBUILD statement with the following index rebuild options:</span></span>  
  
-   <span data-ttu-id="dbc11-108">Especificar uma porcentagem de FILLFACTOR ou utilizar a quantidade original de FILLFACTOR.</span><span class="sxs-lookup"><span data-stu-id="dbc11-108">Specify a FILLFACTOR percentage or use the original FILLFACTOR amount.</span></span>  
  
-   <span data-ttu-id="dbc11-109">Definir PAD_INDEX = ON para alocar o espaço livre especificado pelo FILLFACTOR nas páginas de nível intermediário do índice.</span><span class="sxs-lookup"><span data-stu-id="dbc11-109">Set PAD_INDEX = ON to allocate the free space specified by FILLFACTOR to the intermediate-level pages of the index.</span></span>  
  
-   <span data-ttu-id="dbc11-110">Definir SORT_IN_TEMPDB = ON para armazenar o resultado de classificação intermediário utilizado para recriar o índice em tempdb.</span><span class="sxs-lookup"><span data-stu-id="dbc11-110">Set SORT_IN_TEMPDB = ON to store the intermediate sort result used to rebuild the index in tempdb.</span></span> <span data-ttu-id="dbc11-111">Quando o resultado de classificação intermediário for definido como OFF, ele será armazenado no mesmo banco de dados do índice.</span><span class="sxs-lookup"><span data-stu-id="dbc11-111">When the intermediate sort result is set to OFF, the result is stored in the same database as the index.</span></span>  
  
-   <span data-ttu-id="dbc11-112">Definir IGNORE_DUP_KEY = ON para permitir uma operação de inserção de várias linhas que inclui registros que violam restrições exclusivas para inserir os registros que não as violam.</span><span class="sxs-lookup"><span data-stu-id="dbc11-112">Set IGNORE_DUP_KEY = ON to allow a multirow insert operation that includes records that violate unique constraints to insert the records that do not violate the unique constraints.</span></span>  
  
-   <span data-ttu-id="dbc11-113">Definir ONLINE = ON para não manter os bloqueios das tabelas, de forma que se possa prosseguir com consultas ou atualizações na tabela subjacente, durante a reindexação.</span><span class="sxs-lookup"><span data-stu-id="dbc11-113">Set ONLINE = ON to not hold table locks so that queries or updates to the underlying table can proceed during re-indexing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dbc11-114">As operações de índice online não estão disponíveis em todas as edições de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbc11-114">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dbc11-115">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="dbc11-115">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="dbc11-116">Para obter mais informações sobre a instrução ALTER INDEX e as opções de recriação de índice, consulte [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dbc11-116">For more information about the ALTER INDEX statement and index rebuild options, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dbc11-117">O tempo que a tarefa leva para criar a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] por ela executada é proporcional ao número de índices recriados pela tarefa.</span><span class="sxs-lookup"><span data-stu-id="dbc11-117">The time the task takes to create the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that the task runs is proportionate to the number of indexes the task rebuilds.</span></span> <span data-ttu-id="dbc11-118">Se a tarefa for configurada para recompilar índices em todas as tabelas e exibições em um banco de dados com um grande número de índices ou em vários bancos de dados, ela poderá levar um tempo considerável para gerar a instrução Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="dbc11-118">If the task is configured to rebuild indexes in all the tables and views in a database with a large number of indexes, or to rebuild indexes in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-rebuild-index-task"></a><span data-ttu-id="dbc11-119">Configuração da tarefa Recompilar Índice</span><span class="sxs-lookup"><span data-stu-id="dbc11-119">Configuration of the Rebuild Index Task</span></span>  
 <span data-ttu-id="dbc11-120">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="dbc11-120">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="dbc11-121">Esta tarefa está na seção **Tarefas do Plano de Manutenção** da **Caixa de Ferramentas** , no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dbc11-121">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="dbc11-122">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="dbc11-122">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
 [<span data-ttu-id="dbc11-123">Tarefa Recriar Índice &#40;Plano de manutenção&#41;</span><span class="sxs-lookup"><span data-stu-id="dbc11-123">Rebuild Index Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/rebuild-index-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="dbc11-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="dbc11-124">Related Tasks</span></span>  
 <span data-ttu-id="dbc11-125">Para obter mais informações sobre como definir essas propriedades no Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , consulte [Definir as propriedades de uma tarefa ou um contêiner](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="dbc11-125">For more about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc11-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dbc11-126">See Also</span></span>  
 <span data-ttu-id="dbc11-127">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="dbc11-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="dbc11-128">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="dbc11-128">Control Flow</span></span>](control-flow.md)  
  
  
