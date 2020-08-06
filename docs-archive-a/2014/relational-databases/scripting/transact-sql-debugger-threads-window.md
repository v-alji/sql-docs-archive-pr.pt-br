---
title: Janela Threads
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Threads Window [Transact-SQL]
ms.assetid: e153f619-0049-4162-9076-c24a454f3278
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f3460c892c182996a753c2a16076418a6b2008f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679844"
---
# <a name="threads-window"></a><span data-ttu-id="edfe7-102">Janela Threads</span><span class="sxs-lookup"><span data-stu-id="edfe7-102">Threads Window</span></span>
  <span data-ttu-id="edfe7-103">A janela **Threads** exibe informações sobre o thread do [!INCLUDE[ssDE](../../includes/ssde-md.md)] usado antes da sessão do Editor de Consultas [!INCLUDE[ssDE](../../includes/ssde-md.md)] que está sendo depurada.</span><span class="sxs-lookup"><span data-stu-id="edfe7-103">The **Threads** window displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] thread that is used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor session that is being debugged.</span></span> <span data-ttu-id="edfe7-104">Você deve estar no modo de depuração para exibir as informações sobre thread.</span><span class="sxs-lookup"><span data-stu-id="edfe7-104">You must be in debug mode to display the thread information.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="edfe7-105">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="edfe7-105">Task List</span></span>  
 <span data-ttu-id="edfe7-106">**Para acessar a janela Threads**</span><span class="sxs-lookup"><span data-stu-id="edfe7-106">**To access the Threads window**</span></span>  
  
-   <span data-ttu-id="edfe7-107">No menu **Depurar** , clique em **Janelas**e em **Threads**.</span><span class="sxs-lookup"><span data-stu-id="edfe7-107">On the **Debug** menu, click **Windows**, and then click **Threads**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="edfe7-108">Colunas</span><span class="sxs-lookup"><span data-stu-id="edfe7-108">Columns</span></span>  
 <span data-ttu-id="edfe7-109">**ID**</span><span class="sxs-lookup"><span data-stu-id="edfe7-109">**ID**</span></span>  
 <span data-ttu-id="edfe7-110">É um número de identificação exclusiva que o depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] atribui ao thread.</span><span class="sxs-lookup"><span data-stu-id="edfe7-110">Is a unique identifying number that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger assigns to the thread.</span></span> <span data-ttu-id="edfe7-111">Você pode localizar mais informações sobre o thread selecionando uma linha da exibição de gerenciamento dinâmico sys.dm_os_threads.</span><span class="sxs-lookup"><span data-stu-id="edfe7-111">You can find more information about the thread by selecting a row from the sys.dm_os_threads dynamic management view.</span></span>  
  
 <span data-ttu-id="edfe7-112">Se você não estiver executando em modo lightweight pooling, selecione a linha na qual o valor em os_thread_id corresponde ao valor da coluna **ID** .</span><span class="sxs-lookup"><span data-stu-id="edfe7-112">If you are not running in lightweight pooling mode, select the row in which the value in os_thread_id matches the value in the **ID** column.</span></span> <span data-ttu-id="edfe7-113">Se você estiver executando em modo lightweight pooling, selecione a linha na qual o valor em fiber_context_address corresponde ao valor na coluna **ID** .</span><span class="sxs-lookup"><span data-stu-id="edfe7-113">If you are running in lightweight pooling mode, select the row in which the value in fiber_context_address matches the value in the **ID** column.</span></span>  
  
 <span data-ttu-id="edfe7-114">**Nome**</span><span class="sxs-lookup"><span data-stu-id="edfe7-114">**Name**</span></span>  
 <span data-ttu-id="edfe7-115">Exibe informações sobre a sessão do [!INCLUDE[ssDE](../../includes/ssde-md.md)] no formato **ComputerName/InstanceName [SPID]** .</span><span class="sxs-lookup"><span data-stu-id="edfe7-115">Displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] session in the format **ComputerName/InstanceName [SPID]**.</span></span>  
  
 <span data-ttu-id="edfe7-116">**ComputerName**</span><span class="sxs-lookup"><span data-stu-id="edfe7-116">**ComputerName**</span></span>  
 <span data-ttu-id="edfe7-117">O nome do computador que está executando a instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] ao qual a sessão do Editor de Consultas está conectada.</span><span class="sxs-lookup"><span data-stu-id="edfe7-117">The name of the computer that is running the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="edfe7-118">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="edfe7-118">**InstanceName**</span></span>  
 <span data-ttu-id="edfe7-119">O nome da instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] à qual a sessão do Editor de Consultas está conectada.</span><span class="sxs-lookup"><span data-stu-id="edfe7-119">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="edfe7-120">**[SPID]**</span><span class="sxs-lookup"><span data-stu-id="edfe7-120">**[SPID]**</span></span>  
 <span data-ttu-id="edfe7-121">A sessão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processa a ID que identifica com exclusividade esta sessão.</span><span class="sxs-lookup"><span data-stu-id="edfe7-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session process ID that uniquely identifies this session.</span></span> <span data-ttu-id="edfe7-122">Você pode obter mais informações sobre a sessão selecionando a linha da exibição sys.sysprocesses que tem o mesmo valor na coluna spid.</span><span class="sxs-lookup"><span data-stu-id="edfe7-122">You can obtain more information about the session by selecting the row in the sys.sysprocesses view that has the same value in the spid column.</span></span>  
  
 <span data-ttu-id="edfe7-123">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="edfe7-123">**Location**</span></span>  
 <span data-ttu-id="edfe7-124">Exibe o nome do arquivo de script usado pela sessão em depuração do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="edfe7-124">Displays the name of the script file that is used in the Query Editor session that is being debugged.</span></span>  
  
 <span data-ttu-id="edfe7-125">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="edfe7-125">**Priority**</span></span>  
 <span data-ttu-id="edfe7-126">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] não dá suporte a este recurso.</span><span class="sxs-lookup"><span data-stu-id="edfe7-126">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="edfe7-127">**Suspend**</span><span class="sxs-lookup"><span data-stu-id="edfe7-127">**Suspend**</span></span>  
 <span data-ttu-id="edfe7-128">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] não dá suporte a este recurso.</span><span class="sxs-lookup"><span data-stu-id="edfe7-128">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edfe7-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="edfe7-129">See Also</span></span>  
 <span data-ttu-id="edfe7-130">[Depurador do Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="edfe7-130">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="edfe7-131">[Informações do depurador Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="edfe7-131">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="edfe7-132">[sys.dm_os_threads &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="edfe7-132">[sys.dm_os_threads &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span></span>  
 [<span data-ttu-id="edfe7-133">sys.sysprocesses &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="edfe7-133">sys.sysprocesses &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysprocesses-transact-sql)  
