---
title: Tarefa Executar Instrução T-SQL (Plano de Manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.tsql.f1
helpviewer_keywords:
- Execute T-SQL Statement Task dialog box
ms.assetid: fef3e259-0c47-4f6e-ade0-aee95e3d6c1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63738758ce228a51ab6c75eb11a681eec3b27352
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576359"
---
# <a name="execute-t-sql-statement-task-maintenance-plan"></a><span data-ttu-id="32231-102">Tarefa Executar Instrução T-SQL (Plano de Manutenção)</span><span class="sxs-lookup"><span data-stu-id="32231-102">Execute T-SQL Statement Task (Maintenance Plan)</span></span>
  <span data-ttu-id="32231-103">Use a caixa de diálogo **Tarefa Executar Instrução T-SQL** para personalizar seu plano de manutenção adicionando instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] de sua escolha a esse plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="32231-103">Use the **Execute T-SQL Statement Task** dialog to customize your maintenance plan by adding [!INCLUDE[tsql](../../includes/tsql-md.md)] statements of your choice to this maintenance plan.</span></span>  
  
## <a name="options"></a><span data-ttu-id="32231-104">Opções</span><span class="sxs-lookup"><span data-stu-id="32231-104">Options</span></span>  
 <span data-ttu-id="32231-105">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="32231-105">**Connection**</span></span>  
 <span data-ttu-id="32231-106">Selecione a conexão de servidor a ser usada na execução desta tarefa.</span><span class="sxs-lookup"><span data-stu-id="32231-106">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="32231-107">**Novo**</span><span class="sxs-lookup"><span data-stu-id="32231-107">**New**</span></span>  
 <span data-ttu-id="32231-108">Crie uma nova conexão com o servidor para usar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="32231-108">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="32231-109">A caixa de diálogo **Nova Conexão** é descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="32231-109">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="32231-110">**Tempo limite de execução**</span><span class="sxs-lookup"><span data-stu-id="32231-110">**Execution time out**</span></span>  
 <span data-ttu-id="32231-111">Hora (segundos) a aguardar pela conclusão da tarefa antes do tempo limite (término da tarefa).</span><span class="sxs-lookup"><span data-stu-id="32231-111">Time (seconds) to wait for task completion before timing out (terminating task).</span></span>  
  
 <span data-ttu-id="32231-112">**Instrução T-SQL**</span><span class="sxs-lookup"><span data-stu-id="32231-112">**T-SQL statement**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="32231-113">instruções a serem executadas.</span><span class="sxs-lookup"><span data-stu-id="32231-113">statements to execute.</span></span>  
  
 <span data-ttu-id="32231-114">**Exibir T-SQL**</span><span class="sxs-lookup"><span data-stu-id="32231-114">**View T-SQL**</span></span>  
 <span data-ttu-id="32231-115">Exiba as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas no servidor para esta tarefa, com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="32231-115">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32231-116">Quando o número de objetos afetados é grande, essa exibição pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="32231-116">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="32231-117">Caixa de diálogo Nova Conexão</span><span class="sxs-lookup"><span data-stu-id="32231-117">New Connection Dialog Box</span></span>  
 <span data-ttu-id="32231-118">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="32231-118">**Connection name**</span></span>  
 <span data-ttu-id="32231-119">Digite um nome para a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="32231-119">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="32231-120">**Selecione ou digite um nome de servidor**</span><span class="sxs-lookup"><span data-stu-id="32231-120">**Select or enter a server name**</span></span>  
 <span data-ttu-id="32231-121">Selecione um servidor com o qual se conectar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="32231-121">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="32231-122">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="32231-122">**Refresh**</span></span>  
 <span data-ttu-id="32231-123">Atualize a lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="32231-123">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="32231-124">**Digite as informações para fazer logon no servidor**</span><span class="sxs-lookup"><span data-stu-id="32231-124">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="32231-125">Especifica como autenticar no servidor.</span><span class="sxs-lookup"><span data-stu-id="32231-125">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="32231-126">**Use a segurança integrada do Windows**</span><span class="sxs-lookup"><span data-stu-id="32231-126">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="32231-127">Conecte-se a uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] com a Autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="32231-127">Connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="32231-128">**Usar nome de usuário e senha específicos**</span><span class="sxs-lookup"><span data-stu-id="32231-128">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="32231-129">Conecte-se com uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32231-129">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="32231-130">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="32231-130">This option is not available.</span></span>  
  
 <span data-ttu-id="32231-131">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="32231-131">**User name**</span></span>  
 <span data-ttu-id="32231-132">Forneça um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usado na autenticação.</span><span class="sxs-lookup"><span data-stu-id="32231-132">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="32231-133">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="32231-133">This option is not available.</span></span>  
  
 <span data-ttu-id="32231-134">**Senha**</span><span class="sxs-lookup"><span data-stu-id="32231-134">**Password**</span></span>  
 <span data-ttu-id="32231-135">Forneça uma senha a ser usada na autenticação.</span><span class="sxs-lookup"><span data-stu-id="32231-135">Provide a password to use when authenticating.</span></span> <span data-ttu-id="32231-136">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="32231-136">This option is not available.</span></span>  
  
  
