---
title: Tarefa Limpeza de Manutenção | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.maintenancecleanuptask.f1
helpviewer_keywords:
- deleting files
- removing files
- Maintenance Cleanup task
ms.assetid: 73ad3cd6-9a6d-44cf-905f-c56aa658bf42
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4d39dd775402adadbe51eaadc530f4feb288ab9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572621"
---
# <a name="maintenance-cleanup-task"></a><span data-ttu-id="39f98-102">Tarefa Limpeza de Manutenção</span><span class="sxs-lookup"><span data-stu-id="39f98-102">Maintenance Cleanup Task</span></span>
  <span data-ttu-id="39f98-103">A tarefa de Limpeza de Manutenção remove arquivos relacionados a planos de manutenção, inclusive arquivos de backup de banco de dados e relatórios criados por planos de manutenção.</span><span class="sxs-lookup"><span data-stu-id="39f98-103">The Maintenance Cleanup task removes files related to maintenance plans, including database backup files and reports created by maintenance plans.</span></span> <span data-ttu-id="39f98-104">Para obter mais informações, consulte [Planos de manutenção](../../relational-databases/maintenance-plans/maintenance-plans.md) e [Fazer backup e restaurar bancos de dados do SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="39f98-104">For more information, see [Maintenance Plans](../../relational-databases/maintenance-plans/maintenance-plans.md) and [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="39f98-105">Usando a tarefa de Limpeza de Manutenção, um pacote pode remover os arquivos de backup ou relatórios de plano de manutenção do servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="39f98-105">By using the Maintenance Cleanup task, a package can remove the backup files or maintenance plan reports on the specified server.</span></span> <span data-ttu-id="39f98-106">A tarefa de Limpeza de Manutenção inclui uma opção para remover um arquivo específico ou remover um grupo de arquivos em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="39f98-106">The Maintenance Cleanup task includes an option to remove a specific file or remove a group of files in a folder.</span></span> <span data-ttu-id="39f98-107">Opcionalmente, você pode especificar a extensão dos arquivos a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="39f98-107">Optionally you can specify the extension of the files to delete.</span></span>  
  
 <span data-ttu-id="39f98-108">Quando você configura a tarefa de Limpeza de Manutenção para remover arquivos de backup, a extensão de nome de arquivo padrão é BAK.</span><span class="sxs-lookup"><span data-stu-id="39f98-108">When you configure the Maintenance Cleanup task to remove backup files, the default file name extension is BAK.</span></span> <span data-ttu-id="39f98-109">Para arquivos de relatório, a extensão de nome de arquivo padrão é TXT.</span><span class="sxs-lookup"><span data-stu-id="39f98-109">For report files, the default file name extension is TXT.</span></span> <span data-ttu-id="39f98-110">Você pode atualizar as extensões para serem adequadas a suas necessidades; a única limitação é que as extensões devem ter menos de 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="39f98-110">You can update the extensions to suit your needs; the only limitation is that extensions must be less than 256 characters long.</span></span>  
  
 <span data-ttu-id="39f98-111">Geralmente, você quer remover arquivos antigos que não são mais necessários e a tarefa de Limpeza de Manutenção pode ser configurada para excluir arquivos que alcançaram uma determinada idade.</span><span class="sxs-lookup"><span data-stu-id="39f98-111">Typically, you want to remove old files that are no longer needed, and the Maintenance Cleanup task can be configured to delete files that have reached a specified age.</span></span> <span data-ttu-id="39f98-112">Por exemplo, a tarefa pode ser configurada para excluir arquivos que têm mais de quatro semanas.</span><span class="sxs-lookup"><span data-stu-id="39f98-112">For example, the task can be configured to delete files that are older than four weeks.</span></span> <span data-ttu-id="39f98-113">Você pode especificar a idade dos arquivos a excluir usando dias, semanas, meses ou anos.</span><span class="sxs-lookup"><span data-stu-id="39f98-113">You can specify the age of files to delete by using days, weeks, months, or years.</span></span> <span data-ttu-id="39f98-114">Se você não especificar a idade mínima de arquivos para excluir, todos os arquivos do tipo especificado serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="39f98-114">If you do not specify the minimum age of files to delete, all files of the specified type are deleted.</span></span>  
  
 <span data-ttu-id="39f98-115">Em contraste com versões anteriores da tarefa de Limpeza de Manutenção, a versão da tarefa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não exclui automaticamente arquivos nos subdiretórios do diretório especificado.</span><span class="sxs-lookup"><span data-stu-id="39f98-115">In contrast to earlier versions of the Maintenance Cleanup task, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version of the task does not automatically delete files in the subdirectories of the specified directory.</span></span> <span data-ttu-id="39f98-116">Essa restrição reduz a área da superfície de qualquer ataque que poderia explorar a funcionalidade da tarefa de Limpeza de Manutenção para excluir arquivos maliciosamente.</span><span class="sxs-lookup"><span data-stu-id="39f98-116">This constraint reduces the surface area of any attack that could exploit the functionality of the Maintenance Cleanup task to delete files maliciously.</span></span> <span data-ttu-id="39f98-117">Para excluir as subpastas do primeiro nível, você deve optar explicitamente por fazer isso com a marcação da opção **Incluir subpastas de primeiro nível** na caixa de diálogo **Tarefa Limpeza de Manutenção** .</span><span class="sxs-lookup"><span data-stu-id="39f98-117">To delete the first-level subfolders, you must explicitly elect to do this by checking the **Include first-level subfolders** option in the **Maintenance Cleanup Task** dialog box.</span></span>  
  
## <a name="configuration-of-the-maintenance-cleanup-task"></a><span data-ttu-id="39f98-118">Configuração da tarefa Limpeza de Manutenção</span><span class="sxs-lookup"><span data-stu-id="39f98-118">Configuration of the Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="39f98-119">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="39f98-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="39f98-120">Esta tarefa está na seção **Tarefas do Plano de Manutenção** da **Caixa de Ferramentas** , no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39f98-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="39f98-121">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="39f98-121">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="39f98-122">Tarefa Limpeza de manutenção &#40;Plano de manutenção&#41;</span><span class="sxs-lookup"><span data-stu-id="39f98-122">Maintenance Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/maintenance-cleanup-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="39f98-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="39f98-123">Related Tasks</span></span>  
 <span data-ttu-id="39f98-124">Para obter detalhes sobre como definir essas propriedades no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Definir as propriedades de uma tarefa ou de um contêiner](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="39f98-124">For details about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f98-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39f98-125">See Also</span></span>  
 <span data-ttu-id="39f98-126">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="39f98-126">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="39f98-127">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="39f98-127">Control Flow</span></span>](control-flow.md)  
  
  
