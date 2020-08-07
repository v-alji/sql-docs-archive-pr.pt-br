---
title: Pontos de interrupção Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoints
ms.assetid: c234430f-bd94-4d0d-9e74-2bf11681fa50
author: rothja
ms.author: jroth
ms.openlocfilehash: c9595c9627ac3cc445b1193881c2d5b772e9b71d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581743"
---
# <a name="transact-sql-breakpoints"></a><span data-ttu-id="8bbd6-102">Pontos de interrupção Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8bbd6-102">Transact-SQL Breakpoints</span></span>
  <span data-ttu-id="8bbd6-103">Os pontos de interrupção especificam que o depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] pause a execução em uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] específica, para que você possa ver o estado dos elementos do código nesse ponto.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-103">Breakpoints specify that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, you can then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="8bbd6-104">Pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="8bbd6-104">Breakpoints</span></span>  
 <span data-ttu-id="8bbd6-105">Ao executar o depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] , você pode alternar um ponto de interrupção em instruções específicas.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-105">When running the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can toggle a breakpoint on specific statements.</span></span> <span data-ttu-id="8bbd6-106">Quando a execução alcançar uma instrução com um ponto de interrupção, o depurador pausará a execução para que você possa exibir informações de depuração, como os valores presentes em variáveis e parâmetros.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-106">When execution reaches a statement with a breakpoint, the debugger pauses execution so you can view debugging information, such as the values present in variables and parameters.</span></span>  
  
 <span data-ttu-id="8bbd6-107">Você pode gerenciar pontos de interrupção individualmente na janela de editor, ou em conjunto, usando a janela **Pontos de interrupção** .</span><span class="sxs-lookup"><span data-stu-id="8bbd6-107">You can manage breakpoints individually in the editor window, or collectively by using the **Breakpoints** window.</span></span> <span data-ttu-id="8bbd6-108">Você pode editar pontos de interrupção para especificar itens, como as condições específicas sob as quais a execução deve pausar, ou as ações a serem adotadas se o ponto de interrupção for executado.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-108">You can edit breakpoints to specify items such as specific conditions under which execution should pause, or the actions to be taken if the breakpoint is executed.</span></span>  
  
## <a name="breakpoint-tasks"></a><span data-ttu-id="8bbd6-109">Tarefas de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="8bbd6-109">Breakpoint Tasks</span></span>  
  
|<span data-ttu-id="8bbd6-110">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="8bbd6-110">Task Description</span></span>|<span data-ttu-id="8bbd6-111">Tópico</span><span class="sxs-lookup"><span data-stu-id="8bbd6-111">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="8bbd6-112">Descreve como especificar a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] na qual você deseja que o depurador pause.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-112">Describes how to specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement on which you want the debugger to pause.</span></span>|[<span data-ttu-id="8bbd6-113">Alternar um ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="8bbd6-113">Toggle a Breakpoint</span></span>](../spatial/point.md)|  
|<span data-ttu-id="8bbd6-114">Descreve como desativar um ponto de interrupção temporariamente e, posteriormente, reativá-lo.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-114">Describes how to temporarily deactivate a breakpoint, and later reactivate it.</span></span> <span data-ttu-id="8bbd6-115">Também descreve como excluir um ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-115">Also describes how to delete a breakpoint.</span></span>|[<span data-ttu-id="8bbd6-116">Habilitar, desabilitar e excluir pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="8bbd6-116">Enable, Disable, and Delete Breakpoints</span></span>](enable-disable-and-delete-breakpoints.md)|  
|<span data-ttu-id="8bbd6-117">Descreve como especificar uma condição, que define se o ponto de interrupção é interrompido com base na avaliação de uma expressão Transact-SQL especificada.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-117">Describes how to specify a condition, which defines whether breakpoint breaks based on the evaluation of a specified Transact-SQL expression.</span></span>|[<span data-ttu-id="8bbd6-118">Especificar uma condição de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="8bbd6-118">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)|  
|<span data-ttu-id="8bbd6-119">Descreve como especificar uma contagem de ocorrências, que leva um ponto de interrupção a ser interrompido somente quando a instrução que contém o ponto de interrupção é executada um número especificado de vezes.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-119">Describes how to specify a hit count, which causes a breakpoint to break only when the statement containing the breakpoint has been executed a specified number of times.</span></span>|[<span data-ttu-id="8bbd6-120">Especificar uma contagem de ocorrências</span><span class="sxs-lookup"><span data-stu-id="8bbd6-120">Specify a Hit Count</span></span>](specify-a-hit-count.md)|  
|<span data-ttu-id="8bbd6-121">Descreve como especificar um filtro, o que leva um ponto de interrupção a ser interrompido somente para processos ou threads especificados.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-121">Describes how to specify a filter, which causes a breakpoint to break for only specified processes or threads.</span></span>|[<span data-ttu-id="8bbd6-122">Especificar um filtro de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="8bbd6-122">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)|  
|<span data-ttu-id="8bbd6-123">Descreve como especificar uma ação **When Hit** , que é uma operação personalizada executada quando a instrução de ponto de interrupção é executada.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-123">Describes how to specify a **When Hit** action, which is a custom operation that is performed when the breakpoint statement is executed.</span></span> <span data-ttu-id="8bbd6-124">Um exemplo seria a impressão de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-124">An example would be to print a message.</span></span>|[<span data-ttu-id="8bbd6-125">Especificar uma ação de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="8bbd6-125">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)|  
|<span data-ttu-id="8bbd6-126">Descreve como editar o local de um ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="8bbd6-126">Describes how to edit the location of a breakpoint.</span></span>|[<span data-ttu-id="8bbd6-127">Editar um local de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="8bbd6-127">Edit a Breakpoint Location</span></span>](edit-a-breakpoint-location.md)|  
  
## <a name="see-also"></a><span data-ttu-id="8bbd6-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8bbd6-128">See Also</span></span>  
 [<span data-ttu-id="8bbd6-129">Informações do depurador Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8bbd6-129">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
