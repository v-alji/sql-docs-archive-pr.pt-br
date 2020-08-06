---
title: Caixa de diálogo Adicionar Endereço IP (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygrouplistener.addipaddress.f1
ms.assetid: 98c9ad3b-ff3c-4c1d-b344-59a72fca137c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5192e6414b34bee6de09d45a7284f25404235dc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570262"
---
# <a name="add-ip-address-dialog-box-sql-server-management-studio"></a><span data-ttu-id="2e6d3-102">Caixa de diálogo Adicionar Endereço IP (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2e6d3-102">Add IP Address Dialog Box (SQL Server Management Studio)</span></span>
  <span data-ttu-id="2e6d3-103">Este tópico da Ajuda F1 descreve as opções especificadas da caixa de diálogo **Adicionar Endereço IP** .</span><span class="sxs-lookup"><span data-stu-id="2e6d3-103">This F1 help topic describes the options of the **Add IP Address** dialog box.</span></span> <span data-ttu-id="2e6d3-104">Essa caixa de diálogo acessada na caixa de diálogo **Novo Ouvinte de Grupo de Disponibilidade** e na guia **Ouvinte** da página **Especificar Réplicas** do [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] ou [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e6d3-104">This dialog box accessed from the **New Availability Group Listener** dialog box and the **Listener** tab of the **Specify Replicas** page of the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2e6d3-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2e6d3-105">Prerequisites</span></span>  
 <span data-ttu-id="2e6d3-106">Antes de você começar a adicionar sub-redes a um ouvinte do grupo de disponibilidade, verifique se você sabe o endereço IP de cada sub-rede e, para um endereço IPv4, a máscara de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-106">Before you begin to add subnets to an availability group listener, ensure that know the IP address for each subnet and, for an IPv4 address, the subnet mask.</span></span>  
  
##  <a name="add-ip-address-options"></a><a name="PageOptions"></a> <span data-ttu-id="2e6d3-107">Adicionar opções de endereço IP</span><span class="sxs-lookup"><span data-stu-id="2e6d3-107">Add IP Address Options</span></span>  
 <span data-ttu-id="2e6d3-108">**Sub-rede**</span><span class="sxs-lookup"><span data-stu-id="2e6d3-108">**Subnet**</span></span>  
 <span data-ttu-id="2e6d3-109">Use a lista suspensa para selecionar um endereço para a sub-rede que você está adicionando ao ouvinte do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-109">Use the drop list to select an address for the subnet that you are adding to the availability group listener.</span></span> <span data-ttu-id="2e6d3-110">Por padrão, uma sub-rede possui um endereço IPv4 e um endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-110">By default a subnet possesses both an IPv4 address and an IPv6 address.</span></span> <span data-ttu-id="2e6d3-111">Na primeira vez que você usa a caixa de diálogo **Adicionar Endereço IP** , a lista suspensa **Sub-rede** exibe os endereços de sub-rede de cada sub-rede que hospeda uma réplica para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-111">The first time you use the **Add IP Address** dialog,  the **Subnet** drop list displays both subnet addresses for each subnet that hosts a replica for the availability group.</span></span> <span data-ttu-id="2e6d3-112">Para adicionar uma determinada sub-rede ao ouvinte, selecione um de seus endereços de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-112">To add a given subnet to the listener, select one of its subnet addresses.</span></span>  
  
 <span data-ttu-id="2e6d3-113">Depois de concluir a caixa de diálogo **Adicionar Endereço IP** e clicar em **OK** para adicionar um endereço de sub-rede selecionado ao ouvinte, a lista suspensa **Sub-rede** filtra esse endereço de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-113">After you complete the **Add IP Address** dialog box and click **OK** to add a selected subnet address to the listener, the **Subnet** drop list filters out that subnet address.</span></span> <span data-ttu-id="2e6d3-114">Todos os endereços de sub-rede selecionados permanecem na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-114">All unselected subnet addresses remain on the drop list.</span></span> <span data-ttu-id="2e6d3-115">Adicione um e apenas um endereço de sub-rede por sub-rede ao ouvinte, caso contrário, haverá falha na criação do ouvinte.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-115">Be sure that you add one and only one subnet address per subnet to the listener, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="2e6d3-116">**Endereços**</span><span class="sxs-lookup"><span data-stu-id="2e6d3-116">**Addresses**</span></span>  
 <span data-ttu-id="2e6d3-117">Use esse campo para inserir um endereço IP estático para o endereço de sub-rede selecionado.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-117">Use this field to enter a static IP address for the selected subnet address.</span></span> <span data-ttu-id="2e6d3-118">Entre em contato com o administrador de rede para obter esse endereço IP.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-118">Contact your network administrator for this IP address.</span></span> <span data-ttu-id="2e6d3-119">Insira um endereço válido para o endereço de sub-rede selecionado, caso contrário, haverá falha na criação.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-119">Ensure that you enter a valid address for the selected subnet address, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="2e6d3-120">**Endereço IPv4**</span><span class="sxs-lookup"><span data-stu-id="2e6d3-120">**IPv4 Address**</span></span>  
 <span data-ttu-id="2e6d3-121">Se você tiver selecionado o endereço de sub-rede IPv4 de uma sub-rede, insira um endereço IPv4 estático válido aqui.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-121">If you selected the IPv4 subnet address of a subnet, enter a valid IPv4 static address here.</span></span>  
  
 <span data-ttu-id="2e6d3-122">**Máscara de sub-rede**</span><span class="sxs-lookup"><span data-stu-id="2e6d3-122">**Subnet Mask**</span></span>  
 <span data-ttu-id="2e6d3-123">Para um endereço IPv4, este campo somente leitura exibe a máscara de sub-rede da sub-rede selecionada.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-123">For an IPv4 address, this read-only field displays the subnet mask of the selected subnet.</span></span>  
  
 <span data-ttu-id="2e6d3-124">**Endereço IPv6**</span><span class="sxs-lookup"><span data-stu-id="2e6d3-124">**IPv6 Address**</span></span>  
 <span data-ttu-id="2e6d3-125">Se você tiver selecionado o endereço de sub-rede IPv6 de uma sub-rede, insira um endereço IPv6 estático válido aqui.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-125">If you selected the IPv6 subnet address of a subnet, enter a valid IPv6 static address here.</span></span>  
  
 <span data-ttu-id="2e6d3-126">**OK**</span><span class="sxs-lookup"><span data-stu-id="2e6d3-126">**OK**</span></span>  
 <span data-ttu-id="2e6d3-127">Clique para criar e adicionar a sub-rede cujo endereço selecionado, junto com o endereço IP estático que você especificou.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-127">Click to create add the subnet whose address you selected, along with the static IP address that you specified.</span></span> <span data-ttu-id="2e6d3-128">Uma linha contendo esses valores será adicionada à grade de sub-redes da caixa de diálogo **Novo Ouvinte de Grupo de Disponibilidade** ou **Especificar Réplicas** .</span><span class="sxs-lookup"><span data-stu-id="2e6d3-128">A row containing these values will be added to the subnet grid of the **New Availability Group Listener** or **Specify Replicas** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2e6d3-129">A caixa de diálogo **Adicionar Endereço IP** não verifica o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-129">The **Add IP Address** dialog does not verify the IP address.</span></span> <span data-ttu-id="2e6d3-130">Além disso, a caixa de diálogo não impede que você adicione o segundo endereço de sub-rede para uma sub-rede que você já adicionou ao ouvinte de grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-130">Also the dialog does not prevent you from adding the second subnet address for a subnet that you have already added to the availability group listener.</span></span>  
  
 <span data-ttu-id="2e6d3-131">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="2e6d3-131">**Cancel**</span></span>  
 <span data-ttu-id="2e6d3-132">Clique para cancelar suas seleções e retornar à caixa de diálogo **Novo Ouvinte do Grupo de disponibilidade** ou à guia **Ouvinte** sem adicionar um endereço IP estático a nenhuma sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2e6d3-132">Click to cancel your selections, and return to the **New Availability Group Listener** dialog box or **Listener** tab without adding a static IP address for any subnet.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2e6d3-133">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2e6d3-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2e6d3-134">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2e6d3-134">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="2e6d3-135">Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2e6d3-135">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="2e6d3-136">Usar o Assistente para Adicionar Réplica ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2e6d3-136">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="2e6d3-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2e6d3-137">See Also</span></span>  
 <span data-ttu-id="2e6d3-138">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2e6d3-138">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="2e6d3-139">[Ouvintes do grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="2e6d3-139">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="2e6d3-140">Conectividade de Cliente AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2e6d3-140">AlwaysOn Client Connectivity (SQL Server)</span></span>](always-on-client-connectivity-sql-server.md)  
  
  
