---
title: Configurar um pacote para usar transações | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], configuring packages to use
ms.assetid: 8bf14957-27b4-456b-81d9-e1a0e0ca94b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f469c2439deb2d16ac9046a1628e82c34e39b31d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679476"
---
# <a name="configure-a-package-to-use-transactions"></a><span data-ttu-id="29b42-102">Configurar um pacote para usar transações</span><span class="sxs-lookup"><span data-stu-id="29b42-102">Configure a Package to Use Transactions</span></span>
  <span data-ttu-id="29b42-103">Quando você configura um pacote para usar transações, há duas opções:</span><span class="sxs-lookup"><span data-stu-id="29b42-103">When you configure a package to use transactions, you have two options:</span></span>  
  
-   <span data-ttu-id="29b42-104">Ter uma única transação para o pacote.</span><span class="sxs-lookup"><span data-stu-id="29b42-104">Have a single transaction for the package.</span></span> <span data-ttu-id="29b42-105">Nesse caso, é o próprio pacote que *inicia* a transação, enquanto tarefas e contêineres individuais do pacote participam desta única transação.</span><span class="sxs-lookup"><span data-stu-id="29b42-105">In this case, it is the package itself that *initiates* this transaction, whereas individual tasks and containers in the package participate in this single transaction.</span></span>  
  
-   <span data-ttu-id="29b42-106">Ter várias transações no pacote.</span><span class="sxs-lookup"><span data-stu-id="29b42-106">Have multiple transactions in the package.</span></span> <span data-ttu-id="29b42-107">Nesse caso, o pacote dá suporte a transações, mas na verdade são as tarefas e os contêineres individuais do pacote que iniciam as transações.</span><span class="sxs-lookup"><span data-stu-id="29b42-107">In this case, the package supports transactions, but individual tasks and containers in the package actually initiate the transactions.</span></span>  
  
 <span data-ttu-id="29b42-108">Os procedimentos a seguir descrevem como configurar ambas as opções.</span><span class="sxs-lookup"><span data-stu-id="29b42-108">The following procedures describe how to configure both options.</span></span>  
  
## <a name="configuring-a-single-transaction"></a><span data-ttu-id="29b42-109">Configurando uma única transação</span><span class="sxs-lookup"><span data-stu-id="29b42-109">Configuring a Single Transaction</span></span>  
 <span data-ttu-id="29b42-110">Nesta opção, o pacote propriamente dito inicia uma única transação.</span><span class="sxs-lookup"><span data-stu-id="29b42-110">In this option, the package itself initiates a single transaction.</span></span> <span data-ttu-id="29b42-111">Configure o pacote para iniciar essa transação definindo a propriedade TransactionOption do pacote como `Required` .</span><span class="sxs-lookup"><span data-stu-id="29b42-111">You configure the package to initiate this transaction by setting the TransactionOption property of the package to `Required`.</span></span>  
  
 <span data-ttu-id="29b42-112">Em seguida, inscreva as tarefas e os contêineres específicos desta única transação.</span><span class="sxs-lookup"><span data-stu-id="29b42-112">Next, you enlist specific tasks and containers in this single transaction.</span></span> <span data-ttu-id="29b42-113">Para inscrever uma tarefa ou um contêiner em uma transação, defina a propriedade TransactionOption da tarefa ou do contêiner como `Supported` .</span><span class="sxs-lookup"><span data-stu-id="29b42-113">To enlist a task or container in a transaction, you set the TransactionOption property of that task or container to `Supported`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-a-single-transaction"></a><span data-ttu-id="29b42-114">Para configurar um pacote para usar uma única transação</span><span class="sxs-lookup"><span data-stu-id="29b42-114">To configure a package to use a single transaction</span></span>  
  
1.  <span data-ttu-id="29b42-115">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote o qual você deseja configurar para usar uma transação.</span><span class="sxs-lookup"><span data-stu-id="29b42-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use a transaction.</span></span>  
  
2.  <span data-ttu-id="29b42-116">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="29b42-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="29b42-117">Clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="29b42-117">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="29b42-118">Clique com o botão direito do mouse em qualquer lugar da tela de fundo da superfície de design do fluxo de controle e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="29b42-118">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="29b42-119">Na janela **Propriedades** , defina a propriedade TransactionOption como `Required` .</span><span class="sxs-lookup"><span data-stu-id="29b42-119">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
6.  <span data-ttu-id="29b42-120">Na superfície de design da guia **Fluxo de Controle** , clique com o botão direito do mouse na tarefa ou no contêiner que deseja inserir na transação e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="29b42-120">On the design surface of the **ControlFlow** tab, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="29b42-121">Na janela **Propriedades** , defina a propriedade TransactionOption como `Supported` .</span><span class="sxs-lookup"><span data-stu-id="29b42-121">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="29b42-122">Para inscrever uma conexão em uma transação, inscreva as tarefas que usam a conexão na transação.</span><span class="sxs-lookup"><span data-stu-id="29b42-122">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="29b42-123">Para obter mais informações, consulte [Integration Services &#40;SSIS&#41; Conexões](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="29b42-123">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
8.  <span data-ttu-id="29b42-124">Repita as etapas 6 e 7 para cada tarefa e contêiner que você deseja inscrever na transação.</span><span class="sxs-lookup"><span data-stu-id="29b42-124">Repeat steps 6 and 7 for each task and container that you want to enroll in the transaction.</span></span>  
  
## <a name="configuring-multiple-transactions"></a><span data-ttu-id="29b42-125">Configurando várias transações</span><span class="sxs-lookup"><span data-stu-id="29b42-125">Configuring Multiple Transactions</span></span>  
 <span data-ttu-id="29b42-126">Nesta opção, o próprio pacote dá suporte a transações, mas não inicia uma transação.</span><span class="sxs-lookup"><span data-stu-id="29b42-126">In this option, the package itself supports transactions but does not start a transaction.</span></span> <span data-ttu-id="29b42-127">Configure o pacote para dar suporte a transações definindo a propriedade TransactionOption do pacote como `Supported` .</span><span class="sxs-lookup"><span data-stu-id="29b42-127">You configure the package to support transactions by setting the TransactionOption property of the package to `Supported`.</span></span>  
  
 <span data-ttu-id="29b42-128">Em seguida, configure as tarefas e os contêineres desejados do pacote para iniciar ou participar de transações.</span><span class="sxs-lookup"><span data-stu-id="29b42-128">Next, you configure the desired tasks and containers inside the package to initiate or participate in transactions.</span></span> <span data-ttu-id="29b42-129">Para configurar uma tarefa ou um contêiner para iniciar uma transação, defina a propriedade TransactionOption da tarefa ou do contêiner como `Required` .</span><span class="sxs-lookup"><span data-stu-id="29b42-129">To configure a task or container to initiate a transaction, you set the TransactionOption property of that task or container to `Required`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-multiple-transactions"></a><span data-ttu-id="29b42-130">Configurar um pacote para usar várias transações</span><span class="sxs-lookup"><span data-stu-id="29b42-130">To configure a package to use multiple transactions</span></span>  
  
1.  <span data-ttu-id="29b42-131">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote a ser configurado para usar transações.</span><span class="sxs-lookup"><span data-stu-id="29b42-131">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use transaction.s</span></span>  
  
2.  <span data-ttu-id="29b42-132">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="29b42-132">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="29b42-133">Clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="29b42-133">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="29b42-134">Clique com o botão direito do mouse em qualquer lugar da tela de fundo da superfície de design do fluxo de controle e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="29b42-134">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="29b42-135">Na janela **Propriedades** , defina a propriedade TransactionOption como `Supported` .</span><span class="sxs-lookup"><span data-stu-id="29b42-135">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="29b42-136">O pacote suporta transações, mas as transações são iniciadas por tarefa ou contêineres no pacote.</span><span class="sxs-lookup"><span data-stu-id="29b42-136">The package supports transactions, but the transactions are started by task or containers in the package.</span></span>  
  
6.  <span data-ttu-id="29b42-137">Na superfície de design da guia **Fluxo de Controle** , clique com o botão direito do mouse na tarefa ou no contêiner no pacote no qual deseja iniciar uma transação e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="29b42-137">On the design surface of the **ControlFlow** tab, right-click the task or the container in the package for which you want to start a transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="29b42-138">Na janela **Propriedades** , defina a propriedade TransactionOption como `Required` .</span><span class="sxs-lookup"><span data-stu-id="29b42-138">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
8.  <span data-ttu-id="29b42-139">Se a transação for iniciada por um contêiner, clique com o botão direito do mouse na tarefa ou no contêiner que deseja inserir na transação e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="29b42-139">If a transaction is started by a container, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
9. <span data-ttu-id="29b42-140">Na janela **Propriedades** , defina a propriedade TransactionOption como `Supported` .</span><span class="sxs-lookup"><span data-stu-id="29b42-140">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="29b42-141">Para inscrever uma conexão em uma transação, inscreva as tarefas que usam a conexão na transação.</span><span class="sxs-lookup"><span data-stu-id="29b42-141">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="29b42-142">Para obter mais informações, consulte [Integration Services &#40;SSIS&#41; Conexões](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="29b42-142">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
10. <span data-ttu-id="29b42-143">Repita as etapas de 6 a 9 para cada tarefa e contêiner que iniciam uma transação.</span><span class="sxs-lookup"><span data-stu-id="29b42-143">Repeat steps 6 through 9 for each task and container that starts a transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b42-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29b42-144">See Also</span></span>  
 [<span data-ttu-id="29b42-145">Transações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="29b42-145">Integration Services Transactions</span></span>](integration-services-transactions.md)  
  
  
