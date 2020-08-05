---
title: Exibir e resolver conflitos de dados para publicações de mesclagem (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], viewing conflicts
- viewing conflict information
- conflict resolution [SQL Server replication], merge replication
ms.assetid: aeee9546-4480-49f9-8b1e-c71da1f056c7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 77aa9ece0073149c017f6eca35a756b22751a74b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572477"
---
# <a name="view-and-resolve-data-conflicts-for-merge-publications-sql-server-management-studio"></a><span data-ttu-id="b4c6c-102">Exibir e resolver conflitos de dados para publicações de mesclagem (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b4c6c-102">View and Resolve Data Conflicts for Merge Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b4c6c-103">Os conflitos em replicação de mesclagem são resolvidos baseado no resolvedor especificado para cada artigo.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-103">Conflicts in merge replication are resolved based on the resolver specified for each article.</span></span> <span data-ttu-id="b4c6c-104">Por padrão, os conflitos são resolvidos sem a necessidade da intervenção do usuário.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-104">By default, conflicts are resolved without the need for user intervention.</span></span> <span data-ttu-id="b4c6c-105">Mas os conflitos podem ser exibidos e o resultado da resolução poderá ser alterado no Visualizador de Conflitos de Replicação da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4c6c-105">But conflicts can be viewed, and the outcome of the resolution can be changed, in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Replication Conflict Viewer.</span></span>  
  
 <span data-ttu-id="b4c6c-106">Os dados de conflito são disponíveis no Visualizador de Conflitos de Replicação pelo período de tempo especificado para o período de retenção de conflito (com um padrão de 14 dias).</span><span class="sxs-lookup"><span data-stu-id="b4c6c-106">Conflict data is available in the Replication Conflict Viewer for the amount of time specified for the conflict retention period (with a default of 14 days).</span></span> <span data-ttu-id="b4c6c-107">Para definir o período de retenção de conflito, ou:</span><span class="sxs-lookup"><span data-stu-id="b4c6c-107">To set the conflict retention period, either:</span></span>  
  
-   <span data-ttu-id="b4c6c-108">Especifique um valor de retenção para o **@conflict_retention** parâmetro de [sp_addmergepublication &#40;&#41;TRANSACT-SQL ](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b4c6c-108">Specify a retention value for the **@conflict_retention** parameter of [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span></span>  
  
-   <span data-ttu-id="b4c6c-109">Especifique um valor de **conflict_retention** para o **@property** parâmetro e um valor de retenção para o **@value** parâmetro de [sp_changemergepublication &#40;&#41;do Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b4c6c-109">Specify a value of **conflict_retention** for the **@property** parameter and a retention value for the **@value** parameter of [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span>  
  
 <span data-ttu-id="b4c6c-110">Por padrão, as informações sobre conflitos são armazenadas:</span><span class="sxs-lookup"><span data-stu-id="b4c6c-110">By default, conflict information is stored:</span></span>  
  
-   <span data-ttu-id="b4c6c-111">No Publicador e no Assinante, caso o nível de compatibilidade da publicação for 90RTM ou superior.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-111">At the Publisher and Subscriber if the publication compatibility level is 90RTM or higher.</span></span>  
  
-   <span data-ttu-id="b4c6c-112">No Publicador, caso o nível de compatibilidade da publicação seja inferior a 80RTM.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-112">At the Publisher if the publication compatibility level is lower than 80RTM.</span></span>  
  
-   <span data-ttu-id="b4c6c-113">No Publicador, caso os Assinantes estejam executando [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4c6c-113">At the Publisher if Subscribers are running [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="b4c6c-114">Os dados de conflito não podem ser armazenados nos Assinantes do [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4c6c-114">Conflict data cannot be stored on [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscribers.</span></span>  
  
 <span data-ttu-id="b4c6c-115">O armazenamento de informações sobre conflitos é controlado pela propriedade de publicação de **conflict_logging** .</span><span class="sxs-lookup"><span data-stu-id="b4c6c-115">Storage of conflict information is controlled by the **conflict_logging** publication property.</span></span> <span data-ttu-id="b4c6c-116">Para obter mais informações, consulte [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql) e [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b4c6c-116">For more information, see [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql) and [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span>  
  
 <span data-ttu-id="b4c6c-117">Os conflitos também podem ser resolvidos interativamente durante a sincronização usando o Resolvedor Interativo da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4c6c-117">Conflicts can also be resolved interactively during synchronization using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Interactive Resolver.</span></span> <span data-ttu-id="b4c6c-118">O Resolvedor Interativo está disponível pelo Gerenciador de Sincronização do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-118">The Interactive Resolver is available through the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Synchronization Manager.</span></span> <span data-ttu-id="b4c6c-119">Para obter mais informações, consulte [Como sincronizar uma assinatura usando o Gerenciador de Sincronização do Windows &#40;Gerenciador de Sincronização do Windows&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b4c6c-119">For more information, see [Synchronize a Subscription Using Windows Synchronization Manager &#40;Windows Synchronization Manager&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md).</span></span>  
  
### <a name="to-view-and-resolve-conflicts-for-merge-publications"></a><span data-ttu-id="b4c6c-120">Para exibir e resolver conflitos para publicações de mesclagem</span><span class="sxs-lookup"><span data-stu-id="b4c6c-120">To view and resolve conflicts for merge publications</span></span>  
  
1.  <span data-ttu-id="b4c6c-121">Conecte-se ao Publicador (ou assinante, se apropriado) em [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e, em seguida, expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-121">Connect to the Publisher (or Subscriber if appropriate) in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b4c6c-122">Expanda a pasta **Replicação** e, em seguida, a pasta **Publicações Locais** .</span><span class="sxs-lookup"><span data-stu-id="b4c6c-122">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="b4c6c-123">Clique com o botão direito do mouse na publicação para a qual você quer exibir conflitos e então clique em **Exibir Conflitos**.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-123">Right-click the publication for which you want to view conflicts, and then click **View Conflicts**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b4c6c-124">Se você tiver especificado um valor de **'subscriber'** para a propriedade **conflict_logging** , a opção de menu **Exibir Conflitos** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-124">If you specified a value of **'subscriber'** for the **conflict_logging** property, the **View Conflicts** menu option is not available.</span></span> <span data-ttu-id="b4c6c-125">Para exibir conflitos, inicie o ConflictViewer.exe no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-125">To view conflicts, start ConflictViewer.exe from the command prompt.</span></span> <span data-ttu-id="b4c6c-126">Por padrão, o ConflictViewer.exe está localizado no seguinte diretório: Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-126">By default, ConflictViewer.exe is located in the following directory: Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE.</span></span> <span data-ttu-id="b4c6c-127">Para obter uma lista de parâmetros de inicialização válidos, execute o ConflictViewer.exe -?.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-127">For a list of valid startup parameters, run ConflictViewer.exe -?.</span></span>  
  
4.  <span data-ttu-id="b4c6c-128">Na caixa de diálogo **Selecionar Tabela de Conflito** , selecione um banco de dados, publicação e tabela para os quais quer exibir conflitos.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-128">In the **Select Conflict Table** dialog box, select a database, publication, and table for which to view conflicts.</span></span>  
  
5.  <span data-ttu-id="b4c6c-129">No Visualizador de Conflitos de Replicação, é possível:</span><span class="sxs-lookup"><span data-stu-id="b4c6c-129">In the Replication Conflict Viewer, you can:</span></span>  
  
    -   <span data-ttu-id="b4c6c-130">Filtrar linhas com os botões à direita da grade superior.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-130">Filter rows with the buttons to the right of the upper grid.</span></span>  
  
    -   <span data-ttu-id="b4c6c-131">Selecionar uma linha na grade superior para exibir informações sobre aquela linha na grade inferior.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-131">Select a row in the upper grid to display information on that row in the lower grid.</span></span>  
  
    -   <span data-ttu-id="b4c6c-132">Selecionar uma ou mais linhas na grade superior e então clicar em **Remover**, que equivale a clicar no botão **Enviar Vencedor** (sem fazer nenhuma alteração nos dados).</span><span class="sxs-lookup"><span data-stu-id="b4c6c-132">Select one or more rows in the upper grid, and then click **Remove**, which is equivalent to clicking the **Submit Winner** button (without making any changes to the data).</span></span>  
  
    -   <span data-ttu-id="b4c6c-133">Clique no botão de Propriedades (**...**) para exibir mais informações sobre uma coluna envolvida em um conflito.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-133">Click the properties button (**...**) to view more information on a column involved in a conflict.</span></span>  
  
    -   <span data-ttu-id="b4c6c-134">Edite dados na coluna **Vencedor do Conflito** ou **Perdedor do Conflito** antes de enviar os dados (os dados são de somente leitura se a coluna estiver cinza).</span><span class="sxs-lookup"><span data-stu-id="b4c6c-134">Edit data in the **Conflict winner** or **Conflict loser** column before submitting the data (data is read-only if the column is gray).</span></span>  
  
    -   <span data-ttu-id="b4c6c-135">Clique em **Enviar Vencedor** para aceitar a linha designada como o vencedor do conflito.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-135">Click **Submit Winner** to accept the row designated as the winner of the conflict.</span></span>  
  
    -   <span data-ttu-id="b4c6c-136">Clique em **Enviar Perdedor** para substituir a resolução e propagar o valor designado como o perdedor do conflito para todos os nós da topologia.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-136">Click **Submit Loser** to override the resolution and to propagate the value designated as the loser of the conflict to all nodes in the topology.</span></span>  
  
    -   <span data-ttu-id="b4c6c-137">Selecione **Registrar os detalhes deste conflito** para registrar dados de conflito em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-137">Select **Log the details of this conflict** to log conflict data to a file.</span></span> <span data-ttu-id="b4c6c-138">Para especificar um local para o arquivo, aponte para o menu **Exibir** e então clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-138">To specify a location for the file, point to the **View** menu, and then click **Options**.</span></span> <span data-ttu-id="b4c6c-139">Insira um valor ou clique no botão procurar (**...**) e então navegue até o arquivo apropriado.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-139">Enter a value, or click the browse button (**...**), and then navigate to the appropriate file.</span></span> <span data-ttu-id="b4c6c-140">Clique em **OK** para sair da caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="b4c6c-140">Click **OK** to exit the **Options** dialog box.</span></span>  
  
6.  <span data-ttu-id="b4c6c-141">Feche o Visualizador de Conflitos de Replicação.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-141">Close the Replication Conflict Viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c6c-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4c6c-142">See Also</span></span>  
 <span data-ttu-id="b4c6c-143">[Detecção e resolução de conflito de replicação de mesclagem avançada](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="b4c6c-143">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span></span>  
 [<span data-ttu-id="b4c6c-144">Especificar um resolvedor de artigo de mesclagem</span><span class="sxs-lookup"><span data-stu-id="b4c6c-144">Specify a Merge Article Resolver</span></span>](publish/specify-a-merge-article-resolver.md)  
  
  
