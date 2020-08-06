---
title: Caixa de diálogo 'Configurações do Editor' de Replicação do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publishersettings.f1
helpviewer_keywords:
- Publisher Settings dialog box
ms.assetid: 4fb70427-082d-4179-82a1-34b235accc43
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3a9a5ca5b0d7bfae895287708af159f3316e4474
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685051"
---
# <a name="sql-server-replication-publisher-settings-dialog-box"></a><span data-ttu-id="fa960-102">Caixa de diálogo 'Configurações do Editor' de Replicação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="fa960-102">SQL Server Replication 'Publisher Settings' dialog box</span></span>
  <span data-ttu-id="fa960-103">A caixa de diálogo **Configurações do Publicador** permite alterar configurações para Publicadores adicionados ao painel esquerdo no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="fa960-103">The **Publisher Settings** dialog box allows you to change settings for Publishers that have been added to the left pane in Replication Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa960-104">Opções</span><span class="sxs-lookup"><span data-stu-id="fa960-104">Options</span></span>  
 <span data-ttu-id="fa960-105">**Conexão do Publicador**</span><span class="sxs-lookup"><span data-stu-id="fa960-105">**Publisher Connection**</span></span>  
 <span data-ttu-id="fa960-106">Clique para iniciar a caixa de diálogo **Conectar ao Servidor** que permite que você visualize e altere as credenciais e propriedades de conexão que o Replication Monitor usa para se conectar a um Publicador.</span><span class="sxs-lookup"><span data-stu-id="fa960-106">Click to launch the **Connect to Server** dialog box, which allows you to view and change the connection properties and credentials Replication Monitor uses to connect to a Publisher.</span></span>  
  
 <span data-ttu-id="fa960-107">**Conexão do Distribuidor**</span><span class="sxs-lookup"><span data-stu-id="fa960-107">**Distributor Connection**</span></span>  
 <span data-ttu-id="fa960-108">Exibido somente se o Publicador usar um Distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="fa960-108">Displayed only if the Publisher uses a remote Distributor.</span></span> <span data-ttu-id="fa960-109">Clique para iniciar a caixa de diálogo **Conectar ao Servidor** que permite que você visualize e altere as credenciais e propriedades de conexão que o Replication Monitor usa para se conectar a um Distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="fa960-109">Click to launch the **Connect to Server** dialog box, which allows you to view and change the connection properties and credentials Replication Monitor uses to connect to the remote Distributor.</span></span>  
  
 <span data-ttu-id="fa960-110">**Conectar automaticamente quando o Replication Monitor for iniciado**</span><span class="sxs-lookup"><span data-stu-id="fa960-110">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="fa960-111">Selecione para permitir que o Replication Monitor faça conexão automática com o Distribuidor e recupere informações de status para o Publicador selecionado na grade, na parte superior da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fa960-111">Select to allow Replication Monitor to automatically connect to the Distributor and retrieve status information for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="fa960-112">Se essa caixa de seleção estiver desmarcada, você terá de fazer a conexão manualmente após iniciar o Replication Monitor: clique com o botão direito no Publicador no painel esquerdo do Replication Monitor, e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="fa960-112">If this checkbox is cleared, you must manually connect after launching Replication Monitor: right-click the Publisher in the left pane of Replication Monitor, and click **Connect**.</span></span>  
  
 <span data-ttu-id="fa960-113">**Atualizar automaticamente o status deste Publicador e de suas publicações**</span><span class="sxs-lookup"><span data-stu-id="fa960-113">**Automatically refresh the status of this Publisher and its publications**</span></span>  
 <span data-ttu-id="fa960-114">Selecione para permitir que o Replication Monitor atualize automaticamente o status do Publicador selecionado na grade, na parte superior da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fa960-114">Select to allow Replication Monitor to automatically refresh status for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="fa960-115">Se essa opção for selecionada, o Replication Monitor pesquisará no Distribuidor informações de status sobre o Publicador e suas publicações.</span><span class="sxs-lookup"><span data-stu-id="fa960-115">If this option is selected, Replication Monitor polls the Distributor for status information on the Publisher and its publications.</span></span> <span data-ttu-id="fa960-116">O intervalo da sondagem é definido pela opção **Taxa de Atualização** .</span><span class="sxs-lookup"><span data-stu-id="fa960-116">The polling interval is set by the **Refresh rate** option.</span></span> <span data-ttu-id="fa960-117">Para obter mais informações sobre a atualização no Replication Monitor, consulte [Cache, atualização e desempenho do Replication Monitor](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="fa960-117">For more information on refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="fa960-118">**Taxa de atualização**</span><span class="sxs-lookup"><span data-stu-id="fa960-118">**Refresh rate**</span></span>  
 <span data-ttu-id="fa960-119">Insira um valor (em segundos) para especificar a frequência de sondagem do Replication Monitor no Distribuidor, por status.</span><span class="sxs-lookup"><span data-stu-id="fa960-119">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="fa960-120">Valores mais baixos resultam em sondagens mais frequentes, que podem afetar o desempenho no Distribuidor se você estiver monitorando um grande número de Publicadores.</span><span class="sxs-lookup"><span data-stu-id="fa960-120">Lower values result in more frequent polling, which can affect performance at the Distributor if you are monitoring a large number of Publishers.</span></span> <span data-ttu-id="fa960-121">É recomendado que você teste seu sistema para determinar um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="fa960-121">It is recommended that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="fa960-122">A configuração da **Taxa de Atualização** será também usada se você selecionar **Atualização Automática** em qualquer uma das janelas de detalhes no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="fa960-122">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="fa960-123">**Mostrar este Publicador no grupo a seguir**</span><span class="sxs-lookup"><span data-stu-id="fa960-123">**Show this Publisher in the following group**</span></span>  
 <span data-ttu-id="fa960-124">Selecione um grupo de Publicadores na lista.</span><span class="sxs-lookup"><span data-stu-id="fa960-124">Select a Publisher group from the list.</span></span> <span data-ttu-id="fa960-125">O Publicador é exibido nesse grupo no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="fa960-125">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="fa960-126">Grupos fornecem uma forma de organizar Publicadores e não causam nenhum efeito em funções de replicação.</span><span class="sxs-lookup"><span data-stu-id="fa960-126">Groups provide a way to organize Publishers and have no effect on how replication functions.</span></span>  
  
 <span data-ttu-id="fa960-127">**Novo grupo**</span><span class="sxs-lookup"><span data-stu-id="fa960-127">**New Group**</span></span>  
 <span data-ttu-id="fa960-128">Clique para criar um novo grupo de Publicadores.</span><span class="sxs-lookup"><span data-stu-id="fa960-128">Click to create a new Publisher group.</span></span> <span data-ttu-id="fa960-129">Um grupo de Publicadores é um modo conveniente de organizar Publicadores no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="fa960-129">A Publisher group provides a convenient way to organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="fa960-130">Grupos não afetam a replicação de dados ou a relação entre servidores em uma topologia de replicação.</span><span class="sxs-lookup"><span data-stu-id="fa960-130">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa960-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fa960-131">See Also</span></span>  
 <span data-ttu-id="fa960-132">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="fa960-132">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="fa960-133">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="fa960-133">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
