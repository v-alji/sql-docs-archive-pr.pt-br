---
title: Tarefa Executar Trabalho do SQL Server Agent (Plano de Manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.executejob.f1
helpviewer_keywords:
- Execute SQL Server Agent Job Task dialog box
ms.assetid: 4ed75956-ebb8-4d8c-9c16-fc0eb00bd3a0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b997d5144b113102ba0ed2d9d1df59b6707acbee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576358"
---
# <a name="execute-sql-server-agent-job-task-maintenance-plan"></a><span data-ttu-id="ee762-102">Tarefa Executar Trabalho do SQL Server Agent (Plano de Manutenção)</span><span class="sxs-lookup"><span data-stu-id="ee762-102">Execute SQL Server Agent Job Task (Maintenance Plan)</span></span>
  <span data-ttu-id="ee762-103">Use a caixa de diálogo **Tarefa Executar Trabalho do SQL Server Agent** para executar trabalhos do Microsoft SQL Server Agent dentro de um plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="ee762-103">Use the **Execute SQL Server Agent Job Task** dialog to execute Microsoft SQL Server Agent jobs within a maintenance plan.</span></span> <span data-ttu-id="ee762-104">Essa opção não estará disponível se você não tiver nenhum trabalho do SQL Server Agent na conexão selecionada.</span><span class="sxs-lookup"><span data-stu-id="ee762-104">This option will not be available if you have no SQL Server Agent jobs on the selected connection.</span></span>  
  
 <span data-ttu-id="ee762-105">Essa tarefa usa a instrução **.sp_start_job** .</span><span class="sxs-lookup"><span data-stu-id="ee762-105">This task uses the **.sp_start_job** statement.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ee762-106">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="ee762-106">UI element list</span></span>  
 <span data-ttu-id="ee762-107">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="ee762-107">**Connection**</span></span>  
 <span data-ttu-id="ee762-108">Selecione a conexão de servidor a ser usada na execução desta tarefa.</span><span class="sxs-lookup"><span data-stu-id="ee762-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="ee762-109">**Novo**</span><span class="sxs-lookup"><span data-stu-id="ee762-109">**New**</span></span>  
 <span data-ttu-id="ee762-110">Crie uma nova conexão com o servidor para usar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="ee762-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="ee762-111">A caixa de diálogo **Nova Conexão** é descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="ee762-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="ee762-112">**Trabalhos do SQL Agent disponíveis**</span><span class="sxs-lookup"><span data-stu-id="ee762-112">**Available SQL Agent jobs**</span></span>  
 <span data-ttu-id="ee762-113">Seleciona o trabalho a ser executado.</span><span class="sxs-lookup"><span data-stu-id="ee762-113">Select the job to execute.</span></span> <span data-ttu-id="ee762-114">A grade fornece o **Nome de trabalho** e a **Descrição** para identificar os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="ee762-114">The grid provides the **Job name** and **Description** to identify the jobs.</span></span>  
  
 <span data-ttu-id="ee762-115">**Exibir T-SQL**</span><span class="sxs-lookup"><span data-stu-id="ee762-115">**View T-SQL**</span></span>  
 <span data-ttu-id="ee762-116">Exiba as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas no servidor para esta tarefa, com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="ee762-116">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ee762-117">Quando o número de objetos afetados é grande, essa exibição pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="ee762-117">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="ee762-118">Caixa de diálogo Nova Conexão</span><span class="sxs-lookup"><span data-stu-id="ee762-118">New Connection Dialog Box</span></span>  
 <span data-ttu-id="ee762-119">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="ee762-119">**Connection name**</span></span>  
 <span data-ttu-id="ee762-120">Digite um nome para a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="ee762-120">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="ee762-121">**Selecione ou digite um nome de servidor**</span><span class="sxs-lookup"><span data-stu-id="ee762-121">**Select or enter a server name**</span></span>  
 <span data-ttu-id="ee762-122">Selecione um servidor com o qual se conectar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="ee762-122">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="ee762-123">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="ee762-123">**Refresh**</span></span>  
 <span data-ttu-id="ee762-124">Atualize a lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ee762-124">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="ee762-125">**Digite as informações para fazer logon no servidor**</span><span class="sxs-lookup"><span data-stu-id="ee762-125">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="ee762-126">Especifica como autenticar no servidor.</span><span class="sxs-lookup"><span data-stu-id="ee762-126">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="ee762-127">**Use a segurança integrada do Windows**</span><span class="sxs-lookup"><span data-stu-id="ee762-127">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="ee762-128">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] com a Autenticação do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="ee762-128">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="ee762-129">**Usar nome de usuário e senha específicos**</span><span class="sxs-lookup"><span data-stu-id="ee762-129">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="ee762-130">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee762-130">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="ee762-131">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="ee762-131">This option is not available.</span></span>  
  
 <span data-ttu-id="ee762-132">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="ee762-132">**User name**</span></span>  
 <span data-ttu-id="ee762-133">Forneça um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usado na autenticação.</span><span class="sxs-lookup"><span data-stu-id="ee762-133">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="ee762-134">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="ee762-134">This option is not available.</span></span>  
  
 <span data-ttu-id="ee762-135">**Senha**</span><span class="sxs-lookup"><span data-stu-id="ee762-135">**Password**</span></span>  
 <span data-ttu-id="ee762-136">Forneça uma senha a ser usada na autenticação.</span><span class="sxs-lookup"><span data-stu-id="ee762-136">Provide a password to use when authenticating.</span></span> <span data-ttu-id="ee762-137">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="ee762-137">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee762-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ee762-138">See Also</span></span>  
 <span data-ttu-id="ee762-139">[sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ee762-139">[sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span></span>  
 <span data-ttu-id="ee762-140">[Criar um trabalho](../../ssms/agent/create-a-job.md) </span><span class="sxs-lookup"><span data-stu-id="ee762-140">[Create a Job](../../ssms/agent/create-a-job.md) </span></span>  
 [<span data-ttu-id="ee762-141">sp_start_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ee762-141">sp_start_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql)  
  
  
