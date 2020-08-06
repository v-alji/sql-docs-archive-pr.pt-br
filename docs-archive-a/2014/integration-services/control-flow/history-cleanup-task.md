---
title: Tarefa de limpeza de histórico | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.historycleanuptask.f1
helpviewer_keywords:
- history tables [SQL Server]
- History Cleanup task [Integration Services]
ms.assetid: 5defc5b9-dfd3-4859-a7fe-ac8c2b5480f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84bc697b7fb18269fc581cea51e111aebc82c15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568736"
---
# <a name="history-cleanup-task"></a><span data-ttu-id="e51e7-102">Tarefa Limpeza do Histórico</span><span class="sxs-lookup"><span data-stu-id="e51e7-102">History Cleanup Task</span></span>
  <span data-ttu-id="e51e7-103">A tarefa Limpeza do Histórico exclui entradas das seguintes tabelas de histórico do banco de dados msdb [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e51e7-103">The History Cleanup task deletes entries in the following history tables in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
-   <span data-ttu-id="e51e7-104">backupfile</span><span class="sxs-lookup"><span data-stu-id="e51e7-104">backupfile</span></span>  
  
-   <span data-ttu-id="e51e7-105">backupfilegroup</span><span class="sxs-lookup"><span data-stu-id="e51e7-105">backupfilegroup</span></span>  
  
-   <span data-ttu-id="e51e7-106">backupmediafamily</span><span class="sxs-lookup"><span data-stu-id="e51e7-106">backupmediafamily</span></span>  
  
-   <span data-ttu-id="e51e7-107">backupmediaset</span><span class="sxs-lookup"><span data-stu-id="e51e7-107">backupmediaset</span></span>  
  
-   <span data-ttu-id="e51e7-108">backupset</span><span class="sxs-lookup"><span data-stu-id="e51e7-108">backupset</span></span>  
  
-   <span data-ttu-id="e51e7-109">restorefile</span><span class="sxs-lookup"><span data-stu-id="e51e7-109">restorefile</span></span>  
  
-   <span data-ttu-id="e51e7-110">restorefilegroup</span><span class="sxs-lookup"><span data-stu-id="e51e7-110">restorefilegroup</span></span>  
  
-   <span data-ttu-id="e51e7-111">restorehistory</span><span class="sxs-lookup"><span data-stu-id="e51e7-111">restorehistory</span></span>  
  
 <span data-ttu-id="e51e7-112">Por meio da tarefa Limpeza do Histórico, um pacote pode excluir dados históricos relacionados a atividades de backup e restauração, a trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e a planos de manutenção do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e51e7-112">By using the History Cleanup task, a package can delete historical data related to backup and restore activities, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, and database maintenance plans.</span></span>  
  
 <span data-ttu-id="e51e7-113">Essa tarefa encapsula o procedimento armazenado do sistema sp_delete_backuphistory e transfere a data especificada ao procedimento como um argumento.</span><span class="sxs-lookup"><span data-stu-id="e51e7-113">This task encapsulates the sp_delete_backuphistory system stored procedure and passes the specified date to the procedure as an argument.</span></span> <span data-ttu-id="e51e7-114">Para obter mais informações, consulte [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e51e7-114">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
## <a name="configuration-of-the-history-cleanup-task"></a><span data-ttu-id="e51e7-115">Configuração da tarefa Limpeza do Histórico</span><span class="sxs-lookup"><span data-stu-id="e51e7-115">Configuration of the History Cleanup Task</span></span>  
 <span data-ttu-id="e51e7-116">A tarefa inclui uma propriedade para especificação da data mais antiga dos dados retidos nas tabelas de histórico.</span><span class="sxs-lookup"><span data-stu-id="e51e7-116">The task includes a property for specifying the oldest date of data retained in the history tables.</span></span> <span data-ttu-id="e51e7-117">Você pode indicar a data por número de dias, semanas, meses ou anos do dia atual, e a tarefa automaticamente converte o intervalo para uma data.</span><span class="sxs-lookup"><span data-stu-id="e51e7-117">You can indicate the date by number of days, weeks, months, or years from the current day, and the task automatically translates the interval to a date.</span></span>  
  
 <span data-ttu-id="e51e7-118">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="e51e7-118">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e51e7-119">Esta tarefa está na seção **Tarefas do Plano de Manutenção** da **Caixa de Ferramentas** , no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e51e7-119">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="e51e7-120">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="e51e7-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e51e7-121">Tarefa limpeza de histórico &#40;Plano de manutenção&#41;</span><span class="sxs-lookup"><span data-stu-id="e51e7-121">History Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/history-cleanup-task-maintenance-plan.md)  
  
 <span data-ttu-id="e51e7-122">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="e51e7-122">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e51e7-123">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="e51e7-123">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="e51e7-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e51e7-124">See Also</span></span>  
 <span data-ttu-id="e51e7-125">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="e51e7-125">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="e51e7-126">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="e51e7-126">Control Flow</span></span>](control-flow.md)  
  
  
