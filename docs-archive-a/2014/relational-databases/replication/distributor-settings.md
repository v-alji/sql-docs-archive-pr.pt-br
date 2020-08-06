---
title: Caixa de diálogo ' configurações do distribuidor ' | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.DistributorSettings.f1
helpviewer_keywords:
- Distributor Settings dialog box
ms.assetid: 8276a521-bdd1-4783-bdb6-7ab43499c0ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b864620f155e899868c95f58350f98e2b659c4e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569920"
---
# <a name="sql-server-replication-distributor-settings-dialog-box"></a><span data-ttu-id="adf8f-102">Caixa de diálogo Replicação do SQL Server ' configurações do distribuidor '</span><span class="sxs-lookup"><span data-stu-id="adf8f-102">SQL Server Replication 'Distributor Settings' dialog box</span></span>
  <span data-ttu-id="adf8f-103">A caixa de diálogo **Configurações do Distribuidor** permite alterar configurações para Distribuidores que foram adicionados ao painel esquerdo no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="adf8f-103">The **Distributor Settings** dialog box enables you to change settings for Distributors that were added to the left pane in Replication Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="adf8f-104">Opções</span><span class="sxs-lookup"><span data-stu-id="adf8f-104">Options</span></span>  
 <span data-ttu-id="adf8f-105">**Conectar automaticamente quando o Replication Monitor for iniciado**</span><span class="sxs-lookup"><span data-stu-id="adf8f-105">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="adf8f-106">Selecione para permitir que o Monitor de Replicação conecte-se ao Distribuidor e recupere informações de status.</span><span class="sxs-lookup"><span data-stu-id="adf8f-106">Select to let Replication Monitor connect to the Distributor and retrieve status information.</span></span>  
  
 <span data-ttu-id="adf8f-107">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="adf8f-107">**Connection**</span></span>  
 <span data-ttu-id="adf8f-108">Clique para exibir a caixa de diálogo **Conectar ao Servidor** .</span><span class="sxs-lookup"><span data-stu-id="adf8f-108">Click to display the **Connect to Server** dialog box.</span></span> <span data-ttu-id="adf8f-109">Isso permite que você visualize e altere as credenciais e propriedades de conexão que o Replication Monitor usa para se conectar ao Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="adf8f-109">This enables you to view and change the connection properties and credentials that Replication Monitor uses to connect to the Distributor.</span></span>  
  
 <span data-ttu-id="adf8f-110">**Atualizar automaticamente o status deste Distribuidor e de suas publicações**</span><span class="sxs-lookup"><span data-stu-id="adf8f-110">**Automatically refresh the status of this Distributor and its publications**</span></span>  
 <span data-ttu-id="adf8f-111">Selecione para permitir que o Monitor de Replicação atualize automaticamente o status para o Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="adf8f-111">Select to let Replication Monitor automatically refresh the status for the Distributor.</span></span> <span data-ttu-id="adf8f-112">Se essa opção for selecionada, o Replication Monitor pesquisará no Distribuidor informações de status com base no intervalo de sondagem pela opção **Taxa de atualização** .</span><span class="sxs-lookup"><span data-stu-id="adf8f-112">If this option is selected, Replication Monitor polls the Distributor for status information based on the polling interval set by the **Refresh rate** option.</span></span> <span data-ttu-id="adf8f-113">Para obter mais informações sobre atualização no Replication Monitor, consulte [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="adf8f-113">For more information about refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="adf8f-114">**Taxa de atualização**</span><span class="sxs-lookup"><span data-stu-id="adf8f-114">**Refresh rate**</span></span>  
 <span data-ttu-id="adf8f-115">Insira um valor (em segundos) para especificar a frequência de sondagem do Replication Monitor no Distribuidor, por status.</span><span class="sxs-lookup"><span data-stu-id="adf8f-115">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="adf8f-116">Valores inferiores resultam em sondagem mais frequente.</span><span class="sxs-lookup"><span data-stu-id="adf8f-116">Lower values result in more frequent polling.</span></span> <span data-ttu-id="adf8f-117">Isto poderá afetar o desempenho no Distribuidor se você estiver monitorando muitos Publicadores.</span><span class="sxs-lookup"><span data-stu-id="adf8f-117">This can affect performance at the Distributor if you are monitoring many Publishers.</span></span> <span data-ttu-id="adf8f-118">Recomendamos que você teste seu sistema para determinar um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="adf8f-118">We recommend that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="adf8f-119">A configuração da **Taxa de Atualização** será também usada se você selecionar **Atualização Automática** em qualquer uma das janelas de detalhes no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="adf8f-119">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="adf8f-120">**Mostre para todos os Publicadores deste Distribuidor no grupo a seguir**</span><span class="sxs-lookup"><span data-stu-id="adf8f-120">**Show all Publishers of this Distributor in the following group**</span></span>  
 <span data-ttu-id="adf8f-121">Selecione um grupo de Publicadores na lista.</span><span class="sxs-lookup"><span data-stu-id="adf8f-121">Select a Publisher group from the list.</span></span> <span data-ttu-id="adf8f-122">O Publicador é exibido nesse grupo no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="adf8f-122">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="adf8f-123">Grupos fornecem uma forma de organizar Publicadores e não afetam a maneira como a replicação funciona.</span><span class="sxs-lookup"><span data-stu-id="adf8f-123">Groups provide a way for you to organize Publishers and do not affect how replication functions.</span></span>  
  
 <span data-ttu-id="adf8f-124">**Novo grupo**</span><span class="sxs-lookup"><span data-stu-id="adf8f-124">**New Group**</span></span>  
 <span data-ttu-id="adf8f-125">Clique para criar um novo grupo de Publicadores.</span><span class="sxs-lookup"><span data-stu-id="adf8f-125">Click to create a new Publisher group.</span></span> <span data-ttu-id="adf8f-126">Um grupo de Publicadores é um modo conveniente de organizar Publicadores no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="adf8f-126">A Publisher group provides a way for you to conveniently organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="adf8f-127">Grupos não afetam a replicação de dados ou a relação entre servidores em uma topologia de replicação.</span><span class="sxs-lookup"><span data-stu-id="adf8f-127">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adf8f-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="adf8f-128">See Also</span></span>  
 <span data-ttu-id="adf8f-129">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="adf8f-129">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="adf8f-130">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="adf8f-130">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
