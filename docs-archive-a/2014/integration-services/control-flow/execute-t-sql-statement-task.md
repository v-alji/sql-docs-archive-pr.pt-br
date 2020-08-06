---
title: Tarefa Executar Instrução T-SQL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executetsqlstatementtask.f1
helpviewer_keywords:
- Transact-SQL statements, SSIS
- statements [Integration Services]
- Execute T-SQL Statement task [Integration Services]
ms.assetid: 7e9086ca-d27e-46c0-bfad-d61333ebd55e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7ebc73ad843ac7fcf1dfbe7699ecd8ea53edcdad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679468"
---
# <a name="execute-t-sql-statement-task"></a><span data-ttu-id="9c445-102">Tarefa Executar Instrução T-SQL</span><span class="sxs-lookup"><span data-stu-id="9c445-102">Execute T-SQL Statement Task</span></span>
  <span data-ttu-id="9c445-103">A tarefa Executar Instrução T-SQL executa instruções Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="9c445-103">The Execute T-SQL Statement task runs Transact-SQL statements.</span></span> <span data-ttu-id="9c445-104">Para obter mais informações, consulte [Referência do Transact-SQL &#40;Mecanismo de Banco de Dados&#41;](/sql/t-sql/language-reference) e [Integration Services &#40;SSIS&#41; Consultas](../integration-services-ssis-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9c445-104">For more information, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference) and [Integration Services &#40;SSIS&#41; Queries](../integration-services-ssis-queries.md).</span></span>  
  
 <span data-ttu-id="9c445-105">Essa tarefa é semelhante à tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="9c445-105">This task is similar to the Execute SQL task.</span></span> <span data-ttu-id="9c445-106">Porém, a tarefa Executar Instrução T-SQL só dá suporte à versão Transact-SQL da linguagem SQL e, por isso, você não pode usá-la para executar instruções em servidores que usam outros dialetos de linguagem SQL.</span><span class="sxs-lookup"><span data-stu-id="9c445-106">However, the Execute T-SQL Statement task supports only the Transact-SQL version of the SQL language and you cannot use this task to run statements on servers that use other dialects of the SQL language.</span></span> <span data-ttu-id="9c445-107">Se for necessário executar consultas parametrizadas, salvar resultados de consulta em variáveis ou usar expressões de propriedade, você deverá usar a tarefa Executar SQL em vez de a tarefa Executar Instrução T-SQL.</span><span class="sxs-lookup"><span data-stu-id="9c445-107">If you need to run parameterized queries, save the query results to variables, or use property expressions, you should use the Execute SQL task instead of the Execute T-SQL Statement task.</span></span> <span data-ttu-id="9c445-108">Para obter mais informações, consulte [Execute SQL Task](execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="9c445-108">For more information, see [Execute SQL Task](execute-sql-task.md).</span></span>  
  
## <a name="configuration-of-the-execute-t-sql-task"></a><span data-ttu-id="9c445-109">Configuração da Tarefa Executar T-SQL</span><span class="sxs-lookup"><span data-stu-id="9c445-109">Configuration of the Execute T-SQL Task</span></span>  
 <span data-ttu-id="9c445-110">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="9c445-110">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="9c445-111">Esta tarefa está na seção **Tarefas do Plano de Manutenção** da **Caixa de Ferramentas** , no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c445-111">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="9c445-112">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="9c445-112">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="9c445-113">Tarefa Executar Instrução T-SQL &#40;Plano de Manutenção&#41;</span><span class="sxs-lookup"><span data-stu-id="9c445-113">Execute T-SQL Statement Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/execute-t-sql-statement-task-maintenance-plan.md)  
  
 <span data-ttu-id="9c445-114">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="9c445-114">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="9c445-115">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="9c445-115">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="9c445-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9c445-116">See Also</span></span>  
 <span data-ttu-id="9c445-117">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="9c445-117">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="9c445-118">[Fluxo de Controle](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="9c445-118">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="9c445-119">MERGE em pacotes do Integration Services</span><span class="sxs-lookup"><span data-stu-id="9c445-119">MERGE in Integration Services Packages</span></span>](merge-in-integration-services-packages.md)  
  
  
