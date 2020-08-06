---
title: Tarefa de limpeza de histórico (plano de manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.historycleanup.f1
helpviewer_keywords:
- History Cleanup Task dialog box
ms.assetid: 66bb6c39-958c-4053-a27f-b1118d2567f5
ms.reviewer: ''
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 03ff35b14fc13d2b4446b15501114489b52c421e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576357"
---
# <a name="history-cleanup-task-maintenance-plan"></a><span data-ttu-id="0ed33-102">Tarefa limpeza de histórico (Plano de manutenção)</span><span class="sxs-lookup"><span data-stu-id="0ed33-102">History Cleanup Task (Maintenance Plan)</span></span>

  <span data-ttu-id="0ed33-103">Use a caixa de diálogo **Tarefa Limpeza de Histórico** para descartar informações antigas de histórico de tabelas no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="0ed33-103">Use the **History Cleanup Task** dialog to discard old historical information from tables in the msdb database.</span></span> <span data-ttu-id="0ed33-104">Essa tarefa oferece suporte a exclusão de backup e restauração de histórico, histórico de trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e histórico do plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="0ed33-104">This task supports deleting backup and restore history, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job history, and maintenance plan history.</span></span>  
  
 <span data-ttu-id="0ed33-105">Essa instrução usa as instruções **sp_purge_jobhistory** e **sp_delete_backuphistory** .</span><span class="sxs-lookup"><span data-stu-id="0ed33-105">This statement uses the **sp_purge_jobhistory** and **sp_delete_backuphistory** statements.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="0ed33-106">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="0ed33-106">UI element list</span></span>  
 <span data-ttu-id="0ed33-107">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="0ed33-107">**Connection**</span></span>  
 <span data-ttu-id="0ed33-108">Selecione a conexão de servidor a ser usada na execução desta tarefa.</span><span class="sxs-lookup"><span data-stu-id="0ed33-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="0ed33-109">**Novo**</span><span class="sxs-lookup"><span data-stu-id="0ed33-109">**New**</span></span>  
 <span data-ttu-id="0ed33-110">Crie uma nova conexão com o servidor para usar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="0ed33-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="0ed33-111">A caixa de diálogo **Nova Conexão** é descrita mais abaixo neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0ed33-111">The **New Connection** dialog box is described later in this topic.</span></span>  
  
 <span data-ttu-id="0ed33-112">**Histórico de backup e restauração**</span><span class="sxs-lookup"><span data-stu-id="0ed33-112">**Backup and restore history**</span></span>  
 <span data-ttu-id="0ed33-113">A retenção de registros de quando foram criados backups recentes pode ajudar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a criar um plano de recuperação quando você desejar restaurar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0ed33-113">Retaining records of when recent backups were created can help [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] create a recovery plan when you want to restore a database.</span></span> <span data-ttu-id="0ed33-114">O período de retenção deve ser pelo menos a frequência de backups de banco de dados completos.</span><span class="sxs-lookup"><span data-stu-id="0ed33-114">The retention period should be at least the frequency of full database back ups.</span></span>  
  
 <span data-ttu-id="0ed33-115">**Histórico de trabalho do SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="0ed33-115">**SQL Server Agent Job history**</span></span>  
 <span data-ttu-id="0ed33-116">Esse histórico pode ajudar a solucionar problemas de trabalhos com falha ou a determinar por que ações de banco de dados ocorreram.</span><span class="sxs-lookup"><span data-stu-id="0ed33-116">This history can help you troubleshoot failed jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="0ed33-117">**Histórico do plano de manutenção**</span><span class="sxs-lookup"><span data-stu-id="0ed33-117">**Maintenance plan history**</span></span>  
 <span data-ttu-id="0ed33-118">Esse histórico pode ajudar a solucionar problemas de trabalhos de plano de manutenção com falha ou a determinar por que ações de banco de dados ocorreram.</span><span class="sxs-lookup"><span data-stu-id="0ed33-118">This history can help you troubleshoot failed maintenance plan jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="0ed33-119">**Remover dados históricos com mais de**</span><span class="sxs-lookup"><span data-stu-id="0ed33-119">**Remove historical data older than**</span></span>  
 <span data-ttu-id="0ed33-120">Especifique a idade de itens que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="0ed33-120">Specify age of items that you want to delete.</span></span>  
  
 <span data-ttu-id="0ed33-121">**Exibir T-SQL**</span><span class="sxs-lookup"><span data-stu-id="0ed33-121">**View T-SQL**</span></span>  
 <span data-ttu-id="0ed33-122">Exiba as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas no servidor para esta tarefa, com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="0ed33-122">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ed33-123">Quando o número de objetos afetados é grande, essa exibição pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="0ed33-123">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="0ed33-124">Caixa de diálogo Nova Conexão</span><span class="sxs-lookup"><span data-stu-id="0ed33-124">New Connection Dialog Box</span></span>  
 <span data-ttu-id="0ed33-125">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="0ed33-125">**Connection name**</span></span>  
 <span data-ttu-id="0ed33-126">Digite um nome para a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="0ed33-126">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="0ed33-127">**Selecione ou digite um nome de servidor**</span><span class="sxs-lookup"><span data-stu-id="0ed33-127">**Select or enter a server name**</span></span>  
 <span data-ttu-id="0ed33-128">Selecione um servidor com o qual se conectar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="0ed33-128">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="0ed33-129">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="0ed33-129">**Refresh**</span></span>  
 <span data-ttu-id="0ed33-130">Atualize a lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0ed33-130">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="0ed33-131">**Digite as informações para fazer logon no servidor**</span><span class="sxs-lookup"><span data-stu-id="0ed33-131">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="0ed33-132">Especifica como autenticar no servidor.</span><span class="sxs-lookup"><span data-stu-id="0ed33-132">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="0ed33-133">**Use a segurança integrada do Windows**</span><span class="sxs-lookup"><span data-stu-id="0ed33-133">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="0ed33-134">Conecte a uma instância do SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] com Autenticação do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="0ed33-134">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="0ed33-135">**Usar nome de usuário e senha específicos**</span><span class="sxs-lookup"><span data-stu-id="0ed33-135">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="0ed33-136">Conecte a uma instância do SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] que usa a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0ed33-136">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="0ed33-137">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="0ed33-137">This option is not available.</span></span>  
  
 <span data-ttu-id="0ed33-138">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="0ed33-138">**User name**</span></span>  
 <span data-ttu-id="0ed33-139">Forneça um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usado na autenticação.</span><span class="sxs-lookup"><span data-stu-id="0ed33-139">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="0ed33-140">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="0ed33-140">This option is not available.</span></span>  
  
 <span data-ttu-id="0ed33-141">**Senha**</span><span class="sxs-lookup"><span data-stu-id="0ed33-141">**Password**</span></span>  
 <span data-ttu-id="0ed33-142">Forneça uma senha a ser usada na autenticação.</span><span class="sxs-lookup"><span data-stu-id="0ed33-142">Provide a password to use when authenticating.</span></span> <span data-ttu-id="0ed33-143">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="0ed33-143">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed33-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ed33-144">See Also</span></span>  
 <span data-ttu-id="0ed33-145">[sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ed33-145">[sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span></span>  
 [<span data-ttu-id="0ed33-146">sp_delete_backuphistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0ed33-146">sp_delete_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql)  
  
  
