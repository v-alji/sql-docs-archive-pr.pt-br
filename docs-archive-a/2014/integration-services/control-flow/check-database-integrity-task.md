---
title: Tarefa Verificar Integridade do Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.checkdatabaseintegritytask.f1
helpviewer_keywords:
- data integrity [Integration Services]
- Check Database Integrity task [Integration Services]
- checking database consistency
- database consistency checks [Integration Services]
- verifying database consistency
- integrity checking [Integration Services]
ms.assetid: 5a82fe99-4503-429f-9337-e6bac7649fe4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 99a2620a6f3f6a9a73c27fe6bb1abd34af73707d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573242"
---
# <a name="check-database-integrity-task"></a><span data-ttu-id="7ec3b-102">Tarefa Verificar Integridade do Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="7ec3b-102">Check Database Integrity Task</span></span>
  <span data-ttu-id="7ec3b-103">A tarefa Verificar Integridade do Banco de Dados verifica a alocação e integridade estrutural de todos os objetos no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="7ec3b-103">The Check Database Integrity task checks the allocation and structural integrity of all the objects in the specified database.</span></span> <span data-ttu-id="7ec3b-104">A tarefa pode verificar um único ou vários bancos de dados, e você também pode optar por verificar os índices de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7ec3b-104">The task can check a single database or multiple databases, and you can choose whether to also check the database indexes.</span></span>  
  
 <span data-ttu-id="7ec3b-105">A tarefa Verificar Integridade do Banco de Dados encapsula a instrução DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="7ec3b-105">The Check Database Integrity task encapsulates the DBCC CHECKDB statement.</span></span> <span data-ttu-id="7ec3b-106">Para obter mais informações, veja [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ec3b-106">For more information, see [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql).</span></span>  
  
## <a name="configuration-of-the-check-database-integrity-task"></a><span data-ttu-id="7ec3b-107">Configuração da tarefa Verificar Integridade do Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="7ec3b-107">Configuration of the Check Database Integrity Task</span></span>  
 <span data-ttu-id="7ec3b-108">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="7ec3b-108">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="7ec3b-109">Esta tarefa está na seção **Tarefas do Plano de Manutenção** da **Caixa de Ferramentas** , no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ec3b-109">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="7ec3b-110">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="7ec3b-110">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7ec3b-111">Tarefa Verificar Integridade do Banco de Dados &#40;Plano de Manutenção&#41;</span><span class="sxs-lookup"><span data-stu-id="7ec3b-111">Check Database Integrity Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/check-database-integrity-task-maintenance-plan.md)  
  
 <span data-ttu-id="7ec3b-112">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="7ec3b-112">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7ec3b-113">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="7ec3b-113">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
