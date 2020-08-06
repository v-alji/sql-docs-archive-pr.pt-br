---
title: Replicação de scripts | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server replication], replication objects
- merge replication scripting [SQL Server replication]
- replication [SQL Server], scripting
- snapshot replication [SQL Server], scripting
- scripts [SQL Server replication]
- transactional replication, scripting
ms.assetid: e50fac44-54c0-470c-a4ea-9c111fa4322b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e865e2664a399bca4738c1fc157bef176f35e96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569318"
---
# <a name="scripting-replication"></a><span data-ttu-id="cc180-102">Replicação de script</span><span class="sxs-lookup"><span data-stu-id="cc180-102">Scripting Replication</span></span>
  <span data-ttu-id="cc180-103">Todos os componentes de replicação em uma topologia devem ser incluídos no script como parte de um plano de recuperação de desastre  e os scripts também podem ser usados para automatizar tarefas repetitivas.</span><span class="sxs-lookup"><span data-stu-id="cc180-103">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="cc180-104">Um script contém os procedimentos armazenados do sistema Transact-SQL necessários para implementar os componentes de replicação incluídos no script, como uma publicação ou assinatura.</span><span class="sxs-lookup"><span data-stu-id="cc180-104">A script contains the Transact-SQL system stored procedures necessary to implement the replication component(s) scripted, such as a publication or subscription.</span></span> <span data-ttu-id="cc180-105">Os scripts podem ser criados em um assistente (como o Assistente para Nova Publicação) ou no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] depois de você criar um componente.</span><span class="sxs-lookup"><span data-stu-id="cc180-105">Scripts can be created in a wizard (such as the New Publication Wizard) or in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] after you create a component.</span></span> <span data-ttu-id="cc180-106">É possível exibir, modificar e executar o script por meio do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou do **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="cc180-106">You can view, modify, and run the script using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or **sqlcmd**.</span></span> <span data-ttu-id="cc180-107">Os scripts podem ser armazenados com arquivos de backup para serem usados no caso de uma topologia de replicação precisar ser reconfigurada.</span><span class="sxs-lookup"><span data-stu-id="cc180-107">Scripts can be stored with backup files to be used in case a replication topology must be reconfigured.</span></span>  
  
 <span data-ttu-id="cc180-108">O script de um componente deve ser refeito caso alguma propriedade seja alterada.</span><span class="sxs-lookup"><span data-stu-id="cc180-108">A component should be re-scripted if any property changes are made.</span></span> <span data-ttu-id="cc180-109">Se você usar procedimentos armazenados com replicação transacional, uma cópia de cada procedimento deve ser armazenada com os scripts; a cópia deve ser atualizada se o procedimento for alterado (os procedimentos são normalmente alterados devido a mudanças no esquema ou nos requisitos de aplicativo).</span><span class="sxs-lookup"><span data-stu-id="cc180-109">If you use custom stored procedures with transactional replication, a copy of each procedure should be stored with the scripts; the copy should be updated if the procedure changes (procedures are typically updated due to schema changes or changing application requirements).</span></span> <span data-ttu-id="cc180-110">Para mais informações sobre procedimentos personalizados, consulte [Especificar como as alterações são propagadas para artigos transacionais](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span><span class="sxs-lookup"><span data-stu-id="cc180-110">For more information about custom procedures, see [Specify How Changes Are Propagated for Transactional Articles](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span></span>  
  
 <span data-ttu-id="cc180-111">Para publicações de mesclagem que usam filtros com parâmetros, os scripts de publicação contêm as chamadas de procedimento armazenado para criar partições de dados.</span><span class="sxs-lookup"><span data-stu-id="cc180-111">For merge publications that use parameterized filters, publication scripts contain the stored procedure calls to create data partitions.</span></span> <span data-ttu-id="cc180-112">O script fornece uma referência para as partições criadas e um modo para recriar uma ou mais partições, caso seja necessário.</span><span class="sxs-lookup"><span data-stu-id="cc180-112">The script provides a reference for the partitions created and a way in which to re-create one or more partitions if necessary.</span></span>  
  
## <a name="example-of-automating-a-task-with-scripts"></a><span data-ttu-id="cc180-113">Exemplo de automatização de uma tarefa com scripts</span><span class="sxs-lookup"><span data-stu-id="cc180-113">Example of Automating a Task with Scripts</span></span>  
 <span data-ttu-id="cc180-114">Considere o [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)]que implementa a replicação de mesclagem para distribuir dados a sua força de vendas remota.</span><span class="sxs-lookup"><span data-stu-id="cc180-114">Consider [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], which implements merge replication to distribute data to its remote sales force.</span></span> <span data-ttu-id="cc180-115">Um representante de vendas baixa todos os dados que pertencem aos clientes em seu território usando assinaturas pull.</span><span class="sxs-lookup"><span data-stu-id="cc180-115">A sales representative downloads all the data that pertains to the customers in her territory using pull subscriptions.</span></span> <span data-ttu-id="cc180-116">Ao trabalhar offline, o representante de vendas atualiza os dados e digita novos clientes e pedidos.</span><span class="sxs-lookup"><span data-stu-id="cc180-116">When working offline, the sales representative updates data and enters new customers and orders.</span></span> <span data-ttu-id="cc180-117">Como o [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] tem mais de 50 representantes de vendas em territórios diferentes, a criação de diferentes assinaturas em cada Assinante com o Assistente para Nova Assinatura consumiria muito tempo.</span><span class="sxs-lookup"><span data-stu-id="cc180-117">Because [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] has more than fifty sales representatives in different territories, it would be time-consuming to create the different subscriptions at each Subscriber with the New Subscription Wizard.</span></span> <span data-ttu-id="cc180-118">Em vez disso, o administrador de replicação pode seguir essas etapas:</span><span class="sxs-lookup"><span data-stu-id="cc180-118">Instead, the replication administrator can follow these steps:</span></span>  
  
1.  <span data-ttu-id="cc180-119">Definir as publicações de mesclagem necessárias com partições baseadas nos representantes de vendas ou em seu território.</span><span class="sxs-lookup"><span data-stu-id="cc180-119">Set up the necessary merge publications with partitions based on the sales representative or their territory.</span></span>  
  
2.  <span data-ttu-id="cc180-120">Criar uma assinatura pull para um Assinante.</span><span class="sxs-lookup"><span data-stu-id="cc180-120">Create a pull subscription for one Subscriber.</span></span>  
  
3.  <span data-ttu-id="cc180-121">Gerar um script baseado naquela assinatura pull.</span><span class="sxs-lookup"><span data-stu-id="cc180-121">Generate a script based on that pull subscription.</span></span>  
  
4.  <span data-ttu-id="cc180-122">Modificar o script, alterando valores como o nome do Assinante.</span><span class="sxs-lookup"><span data-stu-id="cc180-122">Modify the script, changing such values as the name of the Subscriber.</span></span>  
  
5.  <span data-ttu-id="cc180-123">Executar o script em vários Assinantes para gerar as assinaturas pull exigidas.</span><span class="sxs-lookup"><span data-stu-id="cc180-123">Run the script at multiple Subscribers to generate the required pull subscriptions.</span></span>  
  
## <a name="script-replication-objects"></a><span data-ttu-id="cc180-124">Executar o script de objetos de replicação</span><span class="sxs-lookup"><span data-stu-id="cc180-124">Script Replication Objects</span></span>  
 <span data-ttu-id="cc180-125">Script de objetos de replicação dos assistentes de replicação ou da pasta **Replicação** no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc180-125">Script replication objects from the replication wizards or from the **Replication** folder in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cc180-126">Se você executar o script a partir dos assistentes, pode escolher criar objetos e então executar o script ou pode escolher somente executar o script.</span><span class="sxs-lookup"><span data-stu-id="cc180-126">If you script from the wizards, you can choose to create objects and script them, or you can choose only to script them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cc180-127">Todas as senhas têm o script executado como NULL.</span><span class="sxs-lookup"><span data-stu-id="cc180-127">All passwords are scripted as NULL.</span></span> <span data-ttu-id="cc180-128">Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="cc180-128">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="cc180-129">Se armazenar credenciais em um arquivo de script, proteja o arquivo para evitar acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="cc180-129">If you store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="cc180-130">Para obter mais informações sobre como usar os assistentes de replicação, consulte:</span><span class="sxs-lookup"><span data-stu-id="cc180-130">For more information about using the replication wizards, see:</span></span>  
  
-   [<span data-ttu-id="cc180-131">Configurar a publicação e a distribuição</span><span class="sxs-lookup"><span data-stu-id="cc180-131">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
-   [<span data-ttu-id="cc180-132">Criar uma publicação</span><span class="sxs-lookup"><span data-stu-id="cc180-132">Create a Publication</span></span>](publish/create-a-publication.md)  
  
-   [<span data-ttu-id="cc180-133">Criar uma Assinatura Push</span><span class="sxs-lookup"><span data-stu-id="cc180-133">Create a Push Subscription</span></span>](create-a-push-subscription.md)  
  
-   [<span data-ttu-id="cc180-134">Criar uma assinatura pull</span><span class="sxs-lookup"><span data-stu-id="cc180-134">Create a Pull Subscription</span></span>](create-a-pull-subscription.md)  
  
#### <a name="to-script-an-object-from-a-replication-wizard"></a><span data-ttu-id="cc180-135">Para executar um script de um objeto a partir de um assistente de replicação</span><span class="sxs-lookup"><span data-stu-id="cc180-135">To script an object from a replication wizard</span></span>  
  
1.  <span data-ttu-id="cc180-136">Na página **Ações do Assistente** de um assistente, marque a caixa de seleção apropriada para o assistente:</span><span class="sxs-lookup"><span data-stu-id="cc180-136">On the **Wizard Actions** page of a wizard, select the check box appropriate for the wizard:</span></span>  
  
    -   <span data-ttu-id="cc180-137">**Gere um arquivo de script com etapas para criar uma publicação**</span><span class="sxs-lookup"><span data-stu-id="cc180-137">**Generate a script file with steps to create a publication**</span></span>  
  
    -   <span data-ttu-id="cc180-138">**Gere um arquivo de script com etapas criar a assinatura(s)**</span><span class="sxs-lookup"><span data-stu-id="cc180-138">**Generate a script file with steps to create the subscription(s)**</span></span>  
  
    -   <span data-ttu-id="cc180-139">**Gere um arquivo de script com etapas para configurar a distribuição**</span><span class="sxs-lookup"><span data-stu-id="cc180-139">**Generate a script file with steps to configure distribution**</span></span>  
  
2.  <span data-ttu-id="cc180-140">Especifique opções na página **Propriedades do Arquivo de Script** .</span><span class="sxs-lookup"><span data-stu-id="cc180-140">Specify options on the **Script File Properties** page.</span></span>  
  
3.  <span data-ttu-id="cc180-141">Conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="cc180-141">Complete the wizard.</span></span>  
  
#### <a name="to-script-an-object-from-management-studio"></a><span data-ttu-id="cc180-142">Para executar o script de um objeto a partir do Management Studio</span><span class="sxs-lookup"><span data-stu-id="cc180-142">To script an object from Management Studio</span></span>  
  
1.  <span data-ttu-id="cc180-143">Conecte-se ao Distribuidor, Publicador ou Assinante no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="cc180-143">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="cc180-144">Expanda a pasta **Replicação** e então expanda a pasta **Publicações Locais** ou a pasta **Assinaturas Locais** .</span><span class="sxs-lookup"><span data-stu-id="cc180-144">Expand the **Replication** folder, and then expand the **Local Publications** folder or the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="cc180-145">Clique com o botão direito do mouse em uma publicação ou assinatura e então clique em **Gerar Scripts**.</span><span class="sxs-lookup"><span data-stu-id="cc180-145">Right-click a publication or subscription, and then click **Generate Scripts**.</span></span>  
  
4.  <span data-ttu-id="cc180-146">Especifique opções na caixa de diálogo **Gerar Script SQL – \<ReplicationObject>** .</span><span class="sxs-lookup"><span data-stu-id="cc180-146">Specify options in the **Generate SQL Script - \<ReplicationObject>** dialog box.</span></span>  
  
5.  <span data-ttu-id="cc180-147">Clique em **Script para Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="cc180-147">Click **Script to File**.</span></span>  
  
6.  <span data-ttu-id="cc180-148">Insira um nome de arquivo na caixa de diálogo **Local do Arquivo de Script** e então clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc180-148">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="cc180-149">Será exibida uma mensagem de status.</span><span class="sxs-lookup"><span data-stu-id="cc180-149">A status message is displayed.</span></span>  
  
7.  <span data-ttu-id="cc180-150">Clique em **OK**e então clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="cc180-150">Click **OK**, and then click **Close**.</span></span>  
  
#### <a name="to-script-multiple-objects-from-management-studio"></a><span data-ttu-id="cc180-151">Para executar script de vários objetos do Management Studio</span><span class="sxs-lookup"><span data-stu-id="cc180-151">To script multiple objects from Management Studio</span></span>  
  
1.  <span data-ttu-id="cc180-152">Conecte-se ao Distribuidor, Publicador ou Assinante no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="cc180-152">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="cc180-153">Clique com o botão direito do mouse na pasta **Replicação** e então clique em **Gerar Scripts**.</span><span class="sxs-lookup"><span data-stu-id="cc180-153">Right-click the **Replication** folder, and then click **Generate Scripts**.</span></span>  
  
3.  <span data-ttu-id="cc180-154">Especifique opções na caixa de diálogo **Gerar Script SQL** .</span><span class="sxs-lookup"><span data-stu-id="cc180-154">Specify options in the **Generate SQL Script** dialog box.</span></span>  
  
4.  <span data-ttu-id="cc180-155">Clique em **Script para Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="cc180-155">Click **Script to File**.</span></span>  
  
5.  <span data-ttu-id="cc180-156">Insira um nome de arquivo na caixa de diálogo **Local do Arquivo de Script** e então clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc180-156">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="cc180-157">Será exibida uma mensagem de status.</span><span class="sxs-lookup"><span data-stu-id="cc180-157">A status message is displayed.</span></span>  
  
6.  <span data-ttu-id="cc180-158">Clique em **OK** e então clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="cc180-158">Click **OK, and then** click **Close**.</span></span>  
  
  
