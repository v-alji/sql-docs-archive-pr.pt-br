---
title: Depurar um manipulador de lógica de negócios | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- merge replication business logic handlers [SQL Server replication]
- business logic handlers [SQL Server replication]
- BusinessLogicModule class
ms.assetid: edd0d17a-0e9c-4c28-8395-a7d47e8ce3d6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7b255407783b1e52a376e562ec910f8b123e42c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569944"
---
# <a name="debug-a-business-logic-handler-replication-programming"></a><span data-ttu-id="5a0fe-102">Depurar um manipulador de lógica de negócios (Programação de replicação)</span><span class="sxs-lookup"><span data-stu-id="5a0fe-102">Debug a Business Logic Handler (Replication Programming)</span></span>
  <span data-ttu-id="5a0fe-103">Use um manipulador de lógica de negócios para invocar a lógica de negócios personalizada quando uma assinatura de mesclagem for sincronizada.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-103">Use a business logic handler to invoke custom business logic when a merge subscription is synchronized.</span></span> <span data-ttu-id="5a0fe-104">Para obter mais informações, consulte [Executar lógica de negócios durante a sincronizações de mesclagem](merge/execute-business-logic-during-merge-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="5a0fe-104">For more information, see [Execute Business Logic During Merge Synchronization](merge/execute-business-logic-during-merge-synchronization.md).</span></span>  
  
 <span data-ttu-id="5a0fe-105">O Reconciliador de replicação de mesclagem (replrec.dll) chama o assembly de código gerenciado que contém a lógica comercial.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-105">The Merge Replication Reconciler (replrec.dll) calls the managed code assembly containing the business logic.</span></span> <span data-ttu-id="5a0fe-106">Na maior parte dos casos, o replrec.dll e a lógica comercial personalizada são executados no computador em que o Agente de Mesclagem é executado (no Assinante para a assinatura pull ou no Distribuidor da assinatura push).</span><span class="sxs-lookup"><span data-stu-id="5a0fe-106">In most cases, replrec.dll and the custom business logic is executed on the computer where the Merge Agent runs (at the Subscriber for a pull subscription or at the Distributor for a push subscription).</span></span> <span data-ttu-id="5a0fe-107">Com relação à sincronização da Web ou a um Assinante [!INCLUDE[ssEW](../../includes/ssew-md.md)] , o reconciliador e a lógica comercial personalizada são executados no servidor Web.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-107">In the case of Web synchronization, or in the case of a [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscriber, the reconciler and the custom business logic is executed on the Web server.</span></span>  
  
### <a name="to-debug-a-business-logic-handler-on-a-local-computer"></a><span data-ttu-id="5a0fe-108">Para depurar um manipulador de lógica de negócios em um computador local</span><span class="sxs-lookup"><span data-stu-id="5a0fe-108">To debug a business logic handler on a local computer</span></span>  
  
1.  <span data-ttu-id="5a0fe-109">Configure a publicação e a distribuição, crie uma publicação e crie uma assinatura para a publicação.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-109">Configure publishing and distribution, create a publication, and create a subscription to the publication.</span></span> <span data-ttu-id="5a0fe-110">Para obter mais informações, confira [Configurar publicação e distribuição](configure-publishing-and-distribution.md) e [Criar uma publicação](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="5a0fe-110">For more information, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md) and [Create a Publication](publish/create-a-publication.md).</span></span>  
  
2.  <span data-ttu-id="5a0fe-111">Crie e registre um manipulador de lógica de negócios.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-111">Create and register a business logic handler.</span></span> <span data-ttu-id="5a0fe-112">Para obter mais informações, consulte [Implementar um manipulador de lógica de negócios para um artigo de mesclagem](implement-a-business-logic-handler-for-a-merge-article.md).</span><span class="sxs-lookup"><span data-stu-id="5a0fe-112">For more information, see [Implement a Business Logic Handler for a Merge Article](implement-a-business-logic-handler-for-a-merge-article.md).</span></span>  
  
3.  <span data-ttu-id="5a0fe-113">Crie um projeto RMO (Replication Management Objects) no [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio, que iniciará o Agente de Mesclagem em sincronia, programaticamente.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-113">Create a Replication Management Objects (RMO) project in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio that programmatically starts the Merge Agent synchronously.</span></span> <span data-ttu-id="5a0fe-114">Para obter mais informações, consulte [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="5a0fe-114">For more information, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span></span>  
  
4.  <span data-ttu-id="5a0fe-115">Defina um ponto de interrupção no código do manipulador de lógica de negócios, tanto no método sendo depurado como no construtor da classe.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-115">Set a breakpoint in the business logic handler code, either in the method being debugged or in the class constructor.</span></span> <span data-ttu-id="5a0fe-116">Para obter mais informações sobre os métodos que podem ser implementados no manipulador de lógica de negócios, consulte o tópico dos métodos <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> .</span><span class="sxs-lookup"><span data-stu-id="5a0fe-116">For more information about the methods that can be implemented in a business logic handler, see the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> methods topic.</span></span>  
  
5.  <span data-ttu-id="5a0fe-117">Crie o manipulador de lógica de negócios no modo de depuração e implante o assembly e o arquivo de símbolo de depuração (.pdb) no local registrado na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-117">Build the business logic handler in debug mode and deploy the assembly and debugging symbol file (.pdb) in the location registered in step 1.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5a0fe-118">Para simplificar a depuração, crie uma solução única de Visual Studio .NET que contenha ambos o projeto do manipulador de lógica de negócios e o projeto que sincroniza a assinatura.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-118">To simplify debugging, create a single Visual Studio .NET solution that contains both the business logic handler project and the project that synchronizes the subscription.</span></span> <span data-ttu-id="5a0fe-119">Nesse caso, defina o projeto de sincronização como projeto de inicialização e configure o ambiente de compilação para implantar o assembly da lógica comercial no local registrado na Etapa 1, durante a depuração.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-119">In this case, set the synchronization project as the startup project, and configure the build environment to deploy the business logic assembly to the location registered in step 1 during debugging.</span></span>  
  
6.  <span data-ttu-id="5a0fe-120">Execute a inserção, atualize ou exclua comandos de acordo com a assinatura ou banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-120">Execute insert, update, or delete commands against the subscription or publication database.</span></span> <span data-ttu-id="5a0fe-121">O comando e o local da execução dependem do método que é depurado.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-121">The command and execution location depends on the method being debugged.</span></span>  
  
7.  <span data-ttu-id="5a0fe-122">Inicie o projeto na Etapa 3, em modo de depuração, para sincronizar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-122">Start the project from step 3 in debug mode to synchronize the subscription.</span></span>  
  
8.  <span data-ttu-id="5a0fe-123">Supondo que nenhum outro ponto de interrupção esteja definido e que os comandos tenham sido replicados, a execução para quando alcança o ponto de interrupção do manipulador de lógica de negócios.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-123">Assuming that no other breakpoints are set and the proper commands are replicated, the execution stops when it reaches the breakpoint in the business logic handler.</span></span>  
  
### <a name="to-debug-a-business-logic-handler-on-a-web-server-using-web-synchronization-or-for-a-sql-server-compact-subscriber"></a><span data-ttu-id="5a0fe-124">Para depurar um manipulador de lógica de negócios em um servidor Web usando a sincronização da Web ou para um assinante do SQL Server Compact</span><span class="sxs-lookup"><span data-stu-id="5a0fe-124">To debug a business logic handler on a Web server using Web synchronization, or for a SQL Server Compact Subscriber</span></span>  
  
1.  <span data-ttu-id="5a0fe-125">Configure a publicação e a distribuição, crie uma publicação e crie uma assinatura pull para a publicação.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-125">Configure publishing and distribution, create a publication, and create a pull subscription to the publication.</span></span> <span data-ttu-id="5a0fe-126">A publicação deve oferecer suporte para sincronização da Web ou Assinantes [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a0fe-126">The publication must support Web synchronization or [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscribers.</span></span>  
  
2.  <span data-ttu-id="5a0fe-127">Crie e registre um manipulador de lógica de negócios.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-127">Create and register a business logic handler.</span></span> <span data-ttu-id="5a0fe-128">Para obter mais informações, consulte [Implementar um manipulador de lógica de negócios para um artigo de mesclagem](implement-a-business-logic-handler-for-a-merge-article.md).</span><span class="sxs-lookup"><span data-stu-id="5a0fe-128">For more information, see [Implement a Business Logic Handler for a Merge Article](implement-a-business-logic-handler-for-a-merge-article.md).</span></span>  
  
3.  <span data-ttu-id="5a0fe-129">Defina um ponto de interrupção no código do manipulador de lógica de negócios, tanto no método sendo depurado como no construtor da classe.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-129">Set a breakpoint in the business logic handler code, either in the method being debugged or in the class constructor.</span></span> <span data-ttu-id="5a0fe-130">Para obter mais informações sobre os métodos que podem ser implementados no manipulador de lógica de negócios, consulte o tópico dos métodos <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> .</span><span class="sxs-lookup"><span data-stu-id="5a0fe-130">For more information about the methods that can be implemented in a business logic handler, see the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> methods topic.</span></span>  
  
4.  <span data-ttu-id="5a0fe-131">Crie o manipulador de lógica de negócios no modo de depuração e implante o assembly e o arquivo de símbolo de depuração (.pdb) no local registrado na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-131">Build the business logic handler in debug mode and deploy the assembly and debugging symbol file (.pdb) at the Web server in the location registered in step 1.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5a0fe-132">Se o manipulador de lógica de negócios falhar em criar por causa do assembly que está em uso, digite o comando `iisreset` no servidor Web, no prompt de comando do servidor Web.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-132">If the business logic handler fails to build because the assembly is in use, type the command `iisreset` on the Web server at the command prompt to reset the Web server.</span></span>  
  
5.  <span data-ttu-id="5a0fe-133">Sincronize a assinatura com sincronização da Web ativada.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-133">Synchronize the subscription with Web synchronization enabled.</span></span> <span data-ttu-id="5a0fe-134">Durante a sincronização, o servidor Web carrega o assembly registrado.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-134">During synchronization, the Web server loads the registered assembly.</span></span>  
  
6.  <span data-ttu-id="5a0fe-135">Usando o depurador do Visual Studio .NET, anexe a um dos processos seguintes no servidor Web:</span><span class="sxs-lookup"><span data-stu-id="5a0fe-135">Using the Visual Studio .NET debugger, attach to the one of the following processes on the Web server:</span></span>  
  
    -   <span data-ttu-id="5a0fe-136">w3wp.exe - Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-136">w3wp.exe - Windows Server 2003.</span></span>  
  
    -   <span data-ttu-id="5a0fe-137">inetinfo.exe - Windows 2000 e Windows XP.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-137">inetinfo.exe - Windows 2000 and Windows XP.</span></span>  
  
7.  <span data-ttu-id="5a0fe-138">Na janela de **Saída** , verifique a saída da depuração para confirmar se os símbolos do assembly registrado foram carregados corretamente.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-138">In the **Output** window, check the debug output to verify that the symbols for the registered assembly loaded properly.</span></span> <span data-ttu-id="5a0fe-139">Se os símbolos não estiverem carregados, confirme se o arquivo .pdb correto foi copiado na Etapa 4, e repita a Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-139">If the symbols were not loaded, ensure that the correct .pdb file was copied in step 4, and repeat step 5.</span></span>  
  
8.  <span data-ttu-id="5a0fe-140">Execute a inserção, atualize ou exclua comandos de acordo com a assinatura ou banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-140">Execute insert, update, or delete commands against the subscription or publication database.</span></span> <span data-ttu-id="5a0fe-141">O comando e o local da execução dependem do método que é depurado.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-141">The command and execution location depends on the method being debugged.</span></span>  
  
9. <span data-ttu-id="5a0fe-142">Usando o depurador do Visual Studio, anexe ao processo w3wp.exe.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-142">Using the Visual Studio debugger, attach to the w3wp.exe process.</span></span>  
  
10. <span data-ttu-id="5a0fe-143">Sincronize a assinatura novamente usando a sincronização da Web.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-143">Synchronize the subscription again, using Web synchronization.</span></span>  
  
11. <span data-ttu-id="5a0fe-144">Supondo que nenhum outro ponto de interrupção esteja definido e que os comandos tenham sido replicados, a execução para quando alcança o ponto de interrupção do manipulador de lógica de negócios.</span><span class="sxs-lookup"><span data-stu-id="5a0fe-144">Assuming that no other breakpoints are set and the proper commands are replicated, the execution stops when it reaches the breakpoint in the business logic handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a0fe-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5a0fe-145">See Also</span></span>  
 [<span data-ttu-id="5a0fe-146">Implementar um manipulador de lógica de negócios para um artigo de mesclagem</span><span class="sxs-lookup"><span data-stu-id="5a0fe-146">Implement a Business Logic Handler for a Merge Article</span></span>](implement-a-business-logic-handler-for-a-merge-article.md)  
  
  
