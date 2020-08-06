---
title: Tarefa Atualizar Estatísticas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.updatestatisticstask.f1
helpviewer_keywords:
- updating statistics
- Update Statistics task [Integration Services]
ms.assetid: 0247483b-f092-4511-8fa8-3610108bd1bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1507ada1e4fa087901383930fce4996c191fb553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568715"
---
# <a name="update-statistics-task"></a><span data-ttu-id="7d3bb-102">Tarefa Atualizar Estatísticas</span><span class="sxs-lookup"><span data-stu-id="7d3bb-102">Update Statistics Task</span></span>
  <span data-ttu-id="7d3bb-103">A tarefa Atualizar Estatísticas atualiza informações sobre a distribuição de valores de chaves para um ou mais grupos de estatísticas (coleções) na tabela ou na exibição indexada especificada.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-103">The Update Statistics task updates information about the distribution of key values for one or more statistics groups (collections) in the specified table or indexed view.</span></span> <span data-ttu-id="7d3bb-104">Para obter mais informações, consulte [Estatísticas](../../relational-databases/statistics/statistics.md).</span><span class="sxs-lookup"><span data-stu-id="7d3bb-104">For more information, see [Statistics](../../relational-databases/statistics/statistics.md).</span></span>  
  
 <span data-ttu-id="7d3bb-105">Utilizando-se a tarefa Atualizar Estatísticas, um pacote pode atualizar as estatísticas de um único banco de dados ou de vários bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-105">By using the Update Statistics task, a package can update statistics for a single database or multiple databases.</span></span> <span data-ttu-id="7d3bb-106">Se a tarefa atualizar só as estatísticas em um único banco de dados, você poderá escolher as exibições e as tabelas cujas estatísticas a tarefa atualizará.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-106">If the task updates only the statistics in a single database, you can choose the views or the tables whose statistics the task updates.</span></span> <span data-ttu-id="7d3bb-107">É possível configurar a atualização para atualizar todas as estatísticas, apenas as estatísticas de coluna, ou apenas as estatísticas de índice.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-107">You can configure the update to update all statistics, column statistics only, or index statistics only.</span></span>  
  
 <span data-ttu-id="7d3bb-108">Esta tarefa encapsula uma instrução UPDATE STATISTICS, inclusive os seguintes argumentos e cláusulas:</span><span class="sxs-lookup"><span data-stu-id="7d3bb-108">This task encapsulates an UPDATE STATISTICS statement, including the following arguments and clauses:</span></span>  
  
-   <span data-ttu-id="7d3bb-109">Os argumentos *table_name* ou *view_name* .</span><span class="sxs-lookup"><span data-stu-id="7d3bb-109">The *table_name* or *view_name* argument.</span></span>  
  
-   <span data-ttu-id="7d3bb-110">Se a atualização se aplicar a todas as estatísticas, a cláusula WITH ALL estará implícita.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-110">If the update applies to all statistics, the WITH ALL clause is implied.</span></span>  
  
-   <span data-ttu-id="7d3bb-111">Se a atualização se aplicar apenas a colunas, a cláusula WITH COLUMN será incluída.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-111">If the update applies only to columns, the WITH COLUMN clause is included.</span></span>  
  
-   <span data-ttu-id="7d3bb-112">Se a atualização se aplicar apenas a índices, a cláusula WITH COLUMN será incluída.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-112">If the update applies only to indexes, the WITH INDEX clause is included.</span></span>  
  
 <span data-ttu-id="7d3bb-113">Se a tarefa Atualizar Estatísticas atualizar estatísticas em vários bancos de dados, a tarefa executará várias instruções UPDATE STATISTICS, uma para cada tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-113">If the Update Statistics task updates statistics in multiple databases, the task runs multiple UPDATE STATISTICS statements, one for each table or view.</span></span> <span data-ttu-id="7d3bb-114">Todas as instâncias de UPDATE STATISTICS usam a mesma cláusula, mas têm valores diferentes para *table_name* ou *view_name* .</span><span class="sxs-lookup"><span data-stu-id="7d3bb-114">All instances of UPDATE STATISTICS use the same clause, but different *table_name* or *view_name* values.</span></span> <span data-ttu-id="7d3bb-115">Para obter mais informações, veja [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql) e [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7d3bb-115">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql) and [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7d3bb-116">O tempo que a tarefa necessita para criar a instrução Transact-SQL que ela executa é proporcional ao número de estatísticas que a tarefa atualiza.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-116">The time the task takes to create the Transact-SQL statement that the task runs is proportionate to the number of statistics the task updates.</span></span> <span data-ttu-id="7d3bb-117">Se a tarefa for configurada para atualizar estatísticas em todas as tabelas e exibições em um banco de dados com um grande número de índices ou em vários bancos de dados, ela pode levar um tempo considerável para gerar a instrução Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-117">If the task is configured to update statistics in all the tables and views in a database with a large number of indexes, or to update statistics in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-update-statistics-task"></a><span data-ttu-id="7d3bb-118">Configuração da tarefa Atualizar Estatísticas</span><span class="sxs-lookup"><span data-stu-id="7d3bb-118">Configuration of the Update Statistics Task</span></span>  
 <span data-ttu-id="7d3bb-119">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="7d3bb-120">Esta tarefa está na seção **Tarefas do Plano de Manutenção** da **Caixa de Ferramentas** , no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d3bb-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="7d3bb-121">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="7d3bb-121">For information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7d3bb-122">Tarefa Atualização de Estatísticas &#40;Plano de manutenção&#41;</span><span class="sxs-lookup"><span data-stu-id="7d3bb-122">Update Statistics Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/update-statistics-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="7d3bb-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="7d3bb-123">Related Tasks</span></span>  
 <span data-ttu-id="7d3bb-124">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="7d3bb-124">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7d3bb-125">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="7d3bb-125">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="7d3bb-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7d3bb-126">See Also</span></span>  
 <span data-ttu-id="7d3bb-127">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="7d3bb-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="7d3bb-128">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="7d3bb-128">Control Flow</span></span>](control-flow.md)  
  
  
