---
title: Caixa de diálogo ' Adicionar publicador '
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.addpublisher.f1
helpviewer_keywords:
- Add Publisher dialog box
ms.assetid: 4b57e298-655f-42c2-82bc-25cdad94a194
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c7e607c04aa74db7e5facf13051bf0c47c9dae0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569964"
---
# <a name="sql-server-replication-add-publisher-dialog-box"></a><span data-ttu-id="70850-102">Caixa de diálogo Replicação do SQL Server ' Adicionar publicador '</span><span class="sxs-lookup"><span data-stu-id="70850-102">SQL Server Replication 'Add Publisher' dialog box</span></span> 
  <span data-ttu-id="70850-103">A caixa de diálogo **Adicionar Publicador** permite a adição de um ou mais publicadores no painel esquerdo do Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="70850-103">The **Add Publisher** dialog box allows you to add to one or more Publishers to the left pane of Replication Monitor.</span></span> <span data-ttu-id="70850-104">Depois de adicionar um Publicador, selecioná-lo no painel esquerdo mostrará informações sobre o Publicador no painel à direita.</span><span class="sxs-lookup"><span data-stu-id="70850-104">After adding a Publisher, selecting the Publisher in the left pane shows information on the Publisher in the right pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="70850-105">Opções</span><span class="sxs-lookup"><span data-stu-id="70850-105">Options</span></span>  
 <span data-ttu-id="70850-106">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="70850-106">**Add**</span></span>  
 <span data-ttu-id="70850-107">Clique para selecionar um tipo de Publicador a ser adicionado que inicia a caixa de diálogo **Conectar ao Servidor** .</span><span class="sxs-lookup"><span data-stu-id="70850-107">Click to select a type of Publisher to add, which launches the **Connect to Server** dialog box.</span></span> <span data-ttu-id="70850-108">As opções são:</span><span class="sxs-lookup"><span data-stu-id="70850-108">The options are:</span></span>  
  
-   <span data-ttu-id="70850-109">**Adicionar SQL Server Publicador...**</span><span class="sxs-lookup"><span data-stu-id="70850-109">**Add SQL Server Publisher...**</span></span>  
  
     <span data-ttu-id="70850-110">Conectar-se ao Editor usando a caixa de diálogo **Conectar ao Servidor** .</span><span class="sxs-lookup"><span data-stu-id="70850-110">Connect to the Publisher using the **Connect to Server** dialog box.</span></span>  
  
-   <span data-ttu-id="70850-111">**Adicionar Publicador Oracle...**</span><span class="sxs-lookup"><span data-stu-id="70850-111">**Add Oracle Publisher...**</span></span>  
  
     <span data-ttu-id="70850-112">Conecte-se ao Distribuidor da [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com Editor Oracle usando a caixa de diálogo **Conectar ao Servidor**.</span><span class="sxs-lookup"><span data-stu-id="70850-112">Connect to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor associated with the Oracle Publisher using the **Connect to Server** dialog box.</span></span>  
  
-   <span data-ttu-id="70850-113">**Especifique um distribuidor e adicione seus Publicadores...**</span><span class="sxs-lookup"><span data-stu-id="70850-113">**Specify a Distributor and Add Its Publishers...**</span></span>  
  
     <span data-ttu-id="70850-114">Conecte-se ao Distribuidor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associado a um ou mais Publicadores usando a caixa de diálogo **Conectar ao Servidor** .</span><span class="sxs-lookup"><span data-stu-id="70850-114">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor associated with one or more Publishers using the **Connect to Server** dialog box.</span></span>  
  
 <span data-ttu-id="70850-115">Depois de se conectar com êxito ao Publicador ou ao Distribuidor, o nome de cada publicador e seu distribuidor serão exibidos na grade, na parte superior da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="70850-115">After successfully connecting to the Publisher or Distributor, the name of each Publisher and its Distributor are displayed in the grid at the top of the dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70850-116">O Distribuidor e o Publicador geralmente são executados na mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas o Distribuidor pode ser executado em outra instância (essa configuração é referenciada como Distribuidor remoto).</span><span class="sxs-lookup"><span data-stu-id="70850-116">The Distributor and Publisher often run on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but the Distributor can run on another instance (this configuration is referred to as a remote Distributor).</span></span>  
  
 <span data-ttu-id="70850-117">**Remover**</span><span class="sxs-lookup"><span data-stu-id="70850-117">**Remove**</span></span>  
 <span data-ttu-id="70850-118">Selecione um Publicador na grade, na parte superior da caixa de diálogo, e clique em **Remover** para remover o Publicador da lista de Publicadores a serem selecionados.</span><span class="sxs-lookup"><span data-stu-id="70850-118">Select a Publisher in the grid at the top of the dialog box, and click **Remove** to remove the Publisher from the list of Publishers to be added.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70850-119">Esse botão não pode ser usado para remover um Publicador já exibido no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="70850-119">This button cannot be used to remove a Publisher that is already displayed in Replication Monitor.</span></span> <span data-ttu-id="70850-120">Para remover um Publicador já exibido, clique no Publicador no painel esquerdo do Replication Monitor, e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="70850-120">To remove a Publisher that is already displayed right-click the Publisher in the left pane of Replication Monitor and click **Remove**.</span></span>  
  
 <span data-ttu-id="70850-121">**Conectar automaticamente quando o Replication Monitor for iniciado**</span><span class="sxs-lookup"><span data-stu-id="70850-121">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="70850-122">Selecione para permitir que o Replication Monitor faça conexão automática com o Distribuidor e recupere informações de status para o Publicador selecionado na grade, na parte superior da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="70850-122">Select to allow Replication Monitor to automatically connect to the Distributor and retrieve status information for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="70850-123">Se essa caixa de seleção estiver desmarcada, você terá de fazer a conexão manualmente após iniciar o Replication Monitor: clique com o botão direito no Publicador no painel esquerdo do Replication Monitor, e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="70850-123">If this checkbox is cleared, you must manually connect after launching Replication Monitor: right-click the Publisher in the left pane of Replication Monitor, and click **Connect**.</span></span>  
  
 <span data-ttu-id="70850-124">**Atualizar automaticamente o status deste Publicador e de suas publicações**</span><span class="sxs-lookup"><span data-stu-id="70850-124">**Automatically refresh the status of this Publisher and its publications**</span></span>  
 <span data-ttu-id="70850-125">Selecione para permitir que o Replication Monitor atualize automaticamente o status do Publicador selecionado na grade, na parte superior da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="70850-125">Select to allow Replication Monitor to automatically refresh status for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="70850-126">Se essa opção for selecionada, o Replication Monitor pesquisará no Distribuidor informações de status sobre o Publicador e suas publicações.</span><span class="sxs-lookup"><span data-stu-id="70850-126">If this option is selected, Replication Monitor polls the Distributor for status information on the Publisher and its publications.</span></span> <span data-ttu-id="70850-127">O intervalo da sondagem é definido pela opção **Taxa de Atualização** .</span><span class="sxs-lookup"><span data-stu-id="70850-127">The polling interval is set by the **Refresh rate** option.</span></span> <span data-ttu-id="70850-128">Para obter mais informações sobre a atualização no Replication Monitor, consulte [Cache, atualização e desempenho do Replication Monitor](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="70850-128">For more information on refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="70850-129">**Taxa de atualização**</span><span class="sxs-lookup"><span data-stu-id="70850-129">**Refresh rate**</span></span>  
 <span data-ttu-id="70850-130">Insira um valor (em segundos) para especificar a frequência de sondagem do Replication Monitor no Distribuidor, por status.</span><span class="sxs-lookup"><span data-stu-id="70850-130">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="70850-131">Valores mais baixos resultam em sondagens mais frequentes, que podem afetar o desempenho no Distribuidor se você estiver monitorando um grande número de Publicadores.</span><span class="sxs-lookup"><span data-stu-id="70850-131">Lower values result in more frequent polling, which can affect performance at the Distributor if you are monitoring a large number of Publishers.</span></span> <span data-ttu-id="70850-132">É recomendado que você teste seu sistema para determinar um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="70850-132">It is recommended that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="70850-133">A configuração da **Taxa de Atualização** será também usada se você selecionar **Atualização Automática** em qualquer uma das janelas de detalhes no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="70850-133">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="70850-134">**Mostrar este Publicador no grupo a seguir**</span><span class="sxs-lookup"><span data-stu-id="70850-134">**Show this Publisher in the following group**</span></span>  
 <span data-ttu-id="70850-135">Selecione um grupo de Publicadores na lista.</span><span class="sxs-lookup"><span data-stu-id="70850-135">Select a Publisher group from the list.</span></span> <span data-ttu-id="70850-136">O Publicador é exibido nesse grupo no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="70850-136">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="70850-137">Grupos fornecem uma forma de organizar Publicadores e não causam nenhum efeito em funções de replicação.</span><span class="sxs-lookup"><span data-stu-id="70850-137">Groups provide a way to organize Publishers and have no effect on how replication functions.</span></span> <span data-ttu-id="70850-138">Se nenhum grupo estiver definido ou você quer criar um novo, clique em **Novo Grupo**.</span><span class="sxs-lookup"><span data-stu-id="70850-138">If no groups are defined or you want to create a new one, click **New Group**.</span></span>  
  
 <span data-ttu-id="70850-139">**Novo grupo**</span><span class="sxs-lookup"><span data-stu-id="70850-139">**New Group**</span></span>  
 <span data-ttu-id="70850-140">Clique para criar um novo grupo de Publicadores.</span><span class="sxs-lookup"><span data-stu-id="70850-140">Click to create a new Publisher group.</span></span> <span data-ttu-id="70850-141">Um grupo de Publicadores é um modo conveniente de organizar Publicadores no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="70850-141">A Publisher group provides a convenient way to organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="70850-142">Grupos não afetam a replicação de dados ou a relação entre servidores em uma topologia de replicação.</span><span class="sxs-lookup"><span data-stu-id="70850-142">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70850-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="70850-143">See Also</span></span>  
 <span data-ttu-id="70850-144">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="70850-144">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="70850-145">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="70850-145">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
