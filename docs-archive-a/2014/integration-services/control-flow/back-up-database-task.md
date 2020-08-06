---
title: Tarefa Backup de Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.backupdatabasetask.f1
helpviewer_keywords:
- database backups [Integration Services]
- Back Up Database task [Integration Services]
- backing up databases [Integration Services]
- transaction log backups [Integration Services]
- backing up transaction logs [Integration Services]
ms.assetid: b8839d71-13b7-41f2-a434-cb95020e79d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b0980d89cc915121414dd7d3c89be6f4d72eb715
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571508"
---
# <a name="back-up-database-task"></a><span data-ttu-id="d85d4-102">Tarefa de Backup de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="d85d4-102">Back Up Database Task</span></span>
  <span data-ttu-id="d85d4-103">A tarefa Backup de Banco de Dados executa vários tipos de backups de bancos de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d85d4-103">The Back Up Database task performs different types of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database backups.</span></span> <span data-ttu-id="d85d4-104">Para obter mais informações, consulte [Fazer backup e restaurar bancos de dados do SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d85d4-104">For more information, see [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="d85d4-105">Usando a tarefa de Backup de Banco de Dados, um pacote poderá fazer backup de um único ou de vários bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="d85d4-105">By using the Back Up Database task, a package can back up a single database or multiple databases.</span></span> <span data-ttu-id="d85d4-106">Se a tarefa fizer backup de um único banco de dados, você poderá escolher o componente de backup: o banco de dados ou seus arquivos e grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d85d4-106">If the task backs up only a single database, you can choose the backup component: the database, or its files and filegroups.</span></span>  
  
## <a name="supported-recover-models-and-backup-types"></a><span data-ttu-id="d85d4-107">Modelos de recuperação e tipos de backup com suporte</span><span class="sxs-lookup"><span data-stu-id="d85d4-107">Supported Recover Models and Backup Types</span></span>  
 <span data-ttu-id="d85d4-108">A tabela a seguir relaciona os modelos de recuperação e tipos de backup que a tarefa de Backup de Banco de Dados oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="d85d4-108">The following table lists the recovery models and backup types that the Back Up Database task supports.</span></span>  
  
|<span data-ttu-id="d85d4-109">modelo de recuperação</span><span class="sxs-lookup"><span data-stu-id="d85d4-109">Recovery model</span></span>|<span data-ttu-id="d85d4-110">Banco de dados</span><span class="sxs-lookup"><span data-stu-id="d85d4-110">Database</span></span>|<span data-ttu-id="d85d4-111">Diferenciais de bancos de dados</span><span class="sxs-lookup"><span data-stu-id="d85d4-111">Database differential</span></span>|<span data-ttu-id="d85d4-112">Log de transações</span><span class="sxs-lookup"><span data-stu-id="d85d4-112">Transaction log</span></span>|<span data-ttu-id="d85d4-113">Arquivo ou diferencial de arquivo</span><span class="sxs-lookup"><span data-stu-id="d85d4-113">File or file differential</span></span>|  
|--------------------|--------------|---------------------------|---------------------|-------------------------------|  
|<span data-ttu-id="d85d4-114">Simples</span><span class="sxs-lookup"><span data-stu-id="d85d4-114">Simple</span></span>|<span data-ttu-id="d85d4-115">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d85d4-115">Required</span></span>|<span data-ttu-id="d85d4-116">Opcional</span><span class="sxs-lookup"><span data-stu-id="d85d4-116">Optional</span></span>|<span data-ttu-id="d85d4-117">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="d85d4-117">Not supported</span></span>|<span data-ttu-id="d85d4-118">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="d85d4-118">Not supported</span></span>|  
|<span data-ttu-id="d85d4-119">Completo</span><span class="sxs-lookup"><span data-stu-id="d85d4-119">Full</span></span>|<span data-ttu-id="d85d4-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d85d4-120">Required</span></span>|<span data-ttu-id="d85d4-121">Opcional</span><span class="sxs-lookup"><span data-stu-id="d85d4-121">Optional</span></span>|<span data-ttu-id="d85d4-122">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d85d4-122">Required</span></span>|<span data-ttu-id="d85d4-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="d85d4-123">Optional</span></span>|  
|<span data-ttu-id="d85d4-124">Bulk-logged</span><span class="sxs-lookup"><span data-stu-id="d85d4-124">Bulk-logged</span></span>|<span data-ttu-id="d85d4-125">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d85d4-125">Required</span></span>|<span data-ttu-id="d85d4-126">Opcional</span><span class="sxs-lookup"><span data-stu-id="d85d4-126">Optional</span></span>|<span data-ttu-id="d85d4-127">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d85d4-127">Required</span></span>|<span data-ttu-id="d85d4-128">Opcional</span><span class="sxs-lookup"><span data-stu-id="d85d4-128">Optional</span></span>|  
  
 <span data-ttu-id="d85d4-129">A tarefa de Backup de Banco de Dados encapsula uma instrução BACKUP Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="d85d4-129">The Back Up Database task encapsulates a Transact-SQL BACKUP statement.</span></span> <span data-ttu-id="d85d4-130">Para obter mais informações, veja [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d85d4-130">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
## <a name="configuration-of-the-back-up-database-task"></a><span data-ttu-id="d85d4-131">Configuração da tarefa de Backup de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="d85d4-131">Configuration of the Back Up Database Task</span></span>  
 <span data-ttu-id="d85d4-132">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="d85d4-132">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="d85d4-133">Esta tarefa está na seção **Tarefas do Plano de Manutenção** da **Caixa de Ferramentas** , no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d85d4-133">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="d85d4-134">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="d85d4-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="d85d4-135">Tarefa Backup de Banco de Dados &#40;Plano de Manutenção&#41;</span><span class="sxs-lookup"><span data-stu-id="d85d4-135">Back Up Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/options-in-the-back-up-database-task-for-maintenance-plan.md)  
  
 <span data-ttu-id="d85d4-136">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="d85d4-136">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="d85d4-137">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="d85d4-137">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
