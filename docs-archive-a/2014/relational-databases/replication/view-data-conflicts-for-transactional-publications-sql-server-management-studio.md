---
title: Exibir conflitos de dados para publicações transacionais (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- conflict resolution [SQL Server replication], queued updating subscriptions
- queued updating subscriptions [SQL Server replication]
- viewing conflict information
ms.assetid: 9977dd75-b0de-4376-9c13-86d80567d8aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 228753c113bcf43ed276d989a3996e9bf23bfc16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581757"
---
# <a name="view-data-conflicts-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="071f1-102">Exibir conflitos de dados para publicações transacionais (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="071f1-102">View Data Conflicts for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="071f1-103">É possível exibir conflitos para replicação transacional ponto a ponto e replicação transacional com assinaturas de atualização enfileiradas no Visualizador de Conflitos de Replicação [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="071f1-103">You can view conflicts for peer-to-peer transactional replication and transactional replication with queued updating subscriptions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Replication Conflict Viewer.</span></span> <span data-ttu-id="071f1-104">Para obter informações sobre como os conflitos são detectados e resolvidos, consulte [Detecção de conflitos em replicação ponto a ponto](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) e [Definir opções de resolução de conflitos em atualização na fila &#40;SQL Server Management Studio&#41;](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="071f1-104">For information about how conflicts are detected and resolved, see [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) and [Set Queued Updating Conflict Resolution Options &#40;SQL Server Management Studio&#41;](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span></span>  
  
 <span data-ttu-id="071f1-105">A disponibilidade de dados de conflito depende do tipo de replicação e do período de retenção de conflito:</span><span class="sxs-lookup"><span data-stu-id="071f1-105">The availability of conflict data depends on the type of replication and the conflict retention period:</span></span>  
  
-   <span data-ttu-id="071f1-106">Para replicação ponto a ponto, por padrão, o Distribution Agent falha ao detectar um conflito.</span><span class="sxs-lookup"><span data-stu-id="071f1-106">For peer-to-peer replication, by default, the Distribution Agent fails when it detects a conflict.</span></span> <span data-ttu-id="071f1-107">Um erro de conflito é registrado no log de erros, mas nenhum dado de conflito é registrado na tabela de conflito; assim, não está disponível para exibição.</span><span class="sxs-lookup"><span data-stu-id="071f1-107">A conflict error is logged into the error log, but no conflict data is logged into the conflict table; therefore it is not available for viewing.</span></span> <span data-ttu-id="071f1-108">Se o Distribution Agent tiver permissão para continuar, um conflito será registrado localmente em cada nó onde ele for detectado.</span><span class="sxs-lookup"><span data-stu-id="071f1-108">If the Distribution Agent is allowed to continue, a conflict is logged locally on each node where it was detected.</span></span> <span data-ttu-id="071f1-109">Para obter mais informações, consulte “Controlando conflitos” em [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span><span class="sxs-lookup"><span data-stu-id="071f1-109">For more information, see "Handling Conflicts" in [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span></span>  
  
-   <span data-ttu-id="071f1-110">Para assinatura de atualização enfileirada, dados estão disponíveis para cada conflito.</span><span class="sxs-lookup"><span data-stu-id="071f1-110">For queued updating subscriptions, data is available for every conflict.</span></span> <span data-ttu-id="071f1-111">Conflitos de dados estão disponíveis no Visualizador de Conflitos de Replicação pelo período de tempo especificado para o período de retenção de conflito, com um padrão de 14 dias.</span><span class="sxs-lookup"><span data-stu-id="071f1-111">Conflict data is available in the Replication Conflict Viewer for the amount of time specified for the conflict retention period, with a default of 14 days.</span></span> <span data-ttu-id="071f1-112">Para definir o período de retenção de conflito, execute qualquer uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="071f1-112">To set the conflict retention period, perform either of the following:</span></span>  
  
    -   <span data-ttu-id="071f1-113">Especificar um valor de retenção para o parâmetro @conflict_retention de [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="071f1-113">Specify a retention value for the @conflict_retention parameter of [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span>  
  
    -   <span data-ttu-id="071f1-114">Especifique um valor de `'conflict_retention'` para o @property parâmetro e um valor de retenção para o @value parâmetro de [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="071f1-114">Specify a value of `'conflict_retention'` for the @property parameter and a retention value for the @value parameter of [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span>  
  
### <a name="to-view-conflicts"></a><span data-ttu-id="071f1-115">Para exibir conflitos</span><span class="sxs-lookup"><span data-stu-id="071f1-115">To view conflicts</span></span>  
  
1.  <span data-ttu-id="071f1-116">Conecte-se ao servidor adequado em [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e, então, expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="071f1-116">Connect to the appropriate server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="071f1-117">Para replicação ponto a ponto, esse é o nó no qual o conflito aconteceu.</span><span class="sxs-lookup"><span data-stu-id="071f1-117">For peer-to-peer replication, this is the node at which the conflict occurred.</span></span>  
  
    -   <span data-ttu-id="071f1-118">Para assinaturas de atualização em fila, esse é o Publicador.</span><span class="sxs-lookup"><span data-stu-id="071f1-118">For queued updating subscriptions, this is the Publisher.</span></span>  
  
2.  <span data-ttu-id="071f1-119">Expanda a pasta **Replicação** e, em seguida, a pasta **Publicações Locais** .</span><span class="sxs-lookup"><span data-stu-id="071f1-119">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="071f1-120">Clique com o botão direito do mouse na publicação para a qual você quer exibir conflitos e então clique em **Exibir Conflitos**.</span><span class="sxs-lookup"><span data-stu-id="071f1-120">Right-click the publication for which you want to view conflicts, and then click **View Conflicts**.</span></span>  
  
4.  <span data-ttu-id="071f1-121">Na caixa de diálogo **Selecionar Tabela de Conflito** , selecione um banco de dados, publicação e tabela para os quais quer exibir conflitos.</span><span class="sxs-lookup"><span data-stu-id="071f1-121">In the **Select Conflict Table** dialog box, select a database, publication, and table for which to view conflicts.</span></span>  
  
5.  <span data-ttu-id="071f1-122">No Visualizador de Conflitos de Replicação, é possível:</span><span class="sxs-lookup"><span data-stu-id="071f1-122">In the Replication Conflict Viewer, you can:</span></span>  
  
    -   <span data-ttu-id="071f1-123">Filtrar linhas com os botões à direita da grade superior.</span><span class="sxs-lookup"><span data-stu-id="071f1-123">Filter rows with the buttons to the right of the upper grid.</span></span>  
  
    -   <span data-ttu-id="071f1-124">Selecionar uma linha na grade superior para exibir informações sobre aquela linha na grade inferior.</span><span class="sxs-lookup"><span data-stu-id="071f1-124">Select a row in the upper grid to display information on that row in the lower grid.</span></span>  
  
    -   <span data-ttu-id="071f1-125">Selecione uma ou mais linhas na grade superior e, então, clique em **Remover**para remover as linhas da tabela de metadados de conflito.</span><span class="sxs-lookup"><span data-stu-id="071f1-125">Select one or more rows in the upper grid, and then click **Remove**, which removes the row from the conflicts metadata table.</span></span>  
  
    -   <span data-ttu-id="071f1-126">Clique no botão de Propriedades (**...**) para exibir mais informações sobre uma coluna envolvida em um conflito.</span><span class="sxs-lookup"><span data-stu-id="071f1-126">Click the properties button (**...**) to view more information on a column involved in a conflict.</span></span>  
  
    -   <span data-ttu-id="071f1-127">Selecione **Registrar os detalhes deste conflito** para registrar dados de conflito em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="071f1-127">Select **Log the details of this conflict** to log conflict data to a file.</span></span> <span data-ttu-id="071f1-128">Para especificar um local para o arquivo, aponte para o menu **Exibir** e então clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="071f1-128">To specify a location for the file, point to the **View** menu, and then click **Options**.</span></span> <span data-ttu-id="071f1-129">Insira um valor ou clique no botão procurar (**...**) e então navegue até o arquivo apropriado.</span><span class="sxs-lookup"><span data-stu-id="071f1-129">Enter a value, or click the browse button (**...**), and then navigate to the appropriate file.</span></span> <span data-ttu-id="071f1-130">Clique em **OK** para fechar a caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="071f1-130">Click **OK** to close the **Options** dialog box.</span></span>  
  
6.  <span data-ttu-id="071f1-131">Feche o Visualizador de Conflitos de Replicação.</span><span class="sxs-lookup"><span data-stu-id="071f1-131">Close the Replication Conflict Viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="071f1-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="071f1-132">See Also</span></span>  
 <span data-ttu-id="071f1-133">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="071f1-133">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="071f1-134">Detecção e resolução de conflitos na atualização na fila</span><span class="sxs-lookup"><span data-stu-id="071f1-134">Queued Updating Conflict Detection and Resolution</span></span>](transactional/updatable-subscriptions-queued-updating-conflict-resolution.md)  
  
  
