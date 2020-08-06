---
title: Tarefa Reduzir Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.shrinkdatabasetask.f1
helpviewer_keywords:
- Shrink Database task
- database shrinking [Integration Services]
- shrinking databases
ms.assetid: e66286f8-97b1-4e5a-86b4-e56f1932b7d5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 587777928e362e87e4b691e3c46167c1239984cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582075"
---
# <a name="shrink-database-task"></a><span data-ttu-id="12e01-102">Tarefa Reduzir Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="12e01-102">Shrink Database Task</span></span>
  <span data-ttu-id="12e01-103">A tarefa Reduzir Banco de Dados reduz o tamanho de dados de bancos de dados e de arquivos de log do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="12e01-103">The Shrink Database task reduces the size of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database data and log files.</span></span>  
  
 <span data-ttu-id="12e01-104">Usando a tarefa Reduzir Banco de Dados, um pacote pode reduzir os arquivos de um único banco de dados ou de vários bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="12e01-104">By using the Shrink Database task, a package can shrink files for a single database or multiple databases.</span></span>  
  
 <span data-ttu-id="12e01-105">A redução de arquivos de dados recupera espaço com a movimentação de páginas de dados do final do arquivo para o espaço desocupado mais próximo à frente do arquivo.</span><span class="sxs-lookup"><span data-stu-id="12e01-105">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="12e01-106">Quando espaço livre suficiente é criado no final do arquivo, as páginas de dados no final do arquivo podem ser desalocadas e retornadas para o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="12e01-106">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="12e01-107">Os dados movidos para reduzir um arquivo podem ser espalhados para qualquer local disponível no arquivo.</span><span class="sxs-lookup"><span data-stu-id="12e01-107">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="12e01-108">Isso provoca uma fragmentação do índice e pode reduzir a velocidade do desempenho de consultas que pesquisam um intervalo do índice.</span><span class="sxs-lookup"><span data-stu-id="12e01-108">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="12e01-109">Para eliminar a fragmentação, considere a recompilação dos índices no arquivo após a redução.</span><span class="sxs-lookup"><span data-stu-id="12e01-109">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="commands"></a><span data-ttu-id="12e01-110">Comandos</span><span class="sxs-lookup"><span data-stu-id="12e01-110">Commands</span></span>  
 <span data-ttu-id="12e01-111">A tarefa Reduzir Banco de Dados encapsula um comando DBCC SHRINKDATABASE, inclusive os seguintes argumentos e opções:</span><span class="sxs-lookup"><span data-stu-id="12e01-111">The Shrink Database task encapsulates a DBCC SHRINKDATABASE command, including the following arguments and options:</span></span>  
  
-   <span data-ttu-id="12e01-112">*database_name*</span><span class="sxs-lookup"><span data-stu-id="12e01-112">*database_name*</span></span>  
  
-   <span data-ttu-id="12e01-113">*target_percent*</span><span class="sxs-lookup"><span data-stu-id="12e01-113">*target_percent*</span></span>  
  
-   <span data-ttu-id="12e01-114">NOTRUNCATE ou TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="12e01-114">NOTRUNCATE or TRUNCATEONLY.</span></span>  
  
 <span data-ttu-id="12e01-115">Se a tarefa Reduzir Banco de Dados reduzir vários bancos de dados, a tarefa executará vários comandos SHRINKDATABASE, um para cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="12e01-115">If the Shrink Database task shrinks multiple databases, the task runs multiple SHRINKDATABASE commands, one for each database.</span></span> <span data-ttu-id="12e01-116">Todas as instâncias do comando SHRINKDATABASE usam os mesmos valores de argumento, exceto para o argumento *database_name* .</span><span class="sxs-lookup"><span data-stu-id="12e01-116">All instances of the SHRINKDATABASE command use the same argument values, except for the *database_name* argument.</span></span> <span data-ttu-id="12e01-117">Para obter mais informações, consulte [DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12e01-117">For more information, see [DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span></span>  
  
## <a name="configuration-of-the-shrink-database-task"></a><span data-ttu-id="12e01-118">Configuração da tarefa Reduzir Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="12e01-118">Configuration of the Shrink Database Task</span></span>  
 <span data-ttu-id="12e01-119">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="12e01-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="12e01-120">Esta tarefa está na seção **Tarefas do Plano de Manutenção** da **Caixa de Ferramentas** , no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="12e01-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="12e01-121">Para obter mais informações sobre as propriedades que podem ser definidas no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , clique no seguinte tópico:</span><span class="sxs-lookup"><span data-stu-id="12e01-121">For more information about the properties that you can set in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="12e01-122">Tarefa Reduzir Banco de Dados &#40;Plano de Manutenção&#41;</span><span class="sxs-lookup"><span data-stu-id="12e01-122">Shrink Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/shrink-database-task-maintenance-plan.md)  
  
 <span data-ttu-id="12e01-123">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="12e01-123">For more information about setting these properties in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="12e01-124">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="12e01-124">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
