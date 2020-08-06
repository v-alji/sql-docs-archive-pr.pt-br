---
title: Usar o Assistente para Adicionar Réplica do Azure (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.azurereplica.f1
ms.assetid: b89cc41b-07b4-49f3-82cc-bc42b2e793ae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f7ee9e80f0511fe23aebb887b15b5e8b7e9cabf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678966"
---
# <a name="use-the-add-azure-replica-wizard-sql-server"></a><span data-ttu-id="5be94-102">Use o Assistente para Adicionar Réplica do Azure (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5be94-102">Use the Add Azure Replica Wizard (SQL Server)</span></span>
  <span data-ttu-id="5be94-103">Use o assistente para adicionar réplica do Azure para ajudá-lo a criar uma nova VM do Azure em ti híbrida e configurá-la como uma réplica secundária para um grupo de disponibilidade AlwaysOn novo ou existente.</span><span class="sxs-lookup"><span data-stu-id="5be94-103">Use the Add Azure Replica Wizard to help you create a new Azure VM in hybrid IT and configure it as a secondary replica for a new or existing AlwaysOn availability group.</span></span>  
  
-   <span data-ttu-id="5be94-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="5be94-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5be94-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5be94-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="5be94-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="5be94-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5be94-107">**Para adicionar uma réplica usando:**  [Assistente para Adicionar Réplica do Azure (SQL Server Management Studio)](#SSMSProcedure)</span><span class="sxs-lookup"><span data-stu-id="5be94-107">**To add a replica, using:**  [Add Azure Replica Wizard (SQL Server Management Studio)](#SSMSProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5be94-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5be94-108">Before You Begin</span></span>  
 <span data-ttu-id="5be94-109">Se você nunca adicionou nenhuma réplica de disponibilidade a um grupo de disponibilidade, consulte as seções "instâncias de servidor" e "grupos de disponibilidade e réplicas" em [pré-requisitos, restrições e recomendações para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="5be94-109">If you have never added any availability replica to an availability group, see the "Server instances" and "Availability groups and replicas" sections in [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="5be94-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5be94-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="5be94-111">Você deve estar conectado à instância do servidor que hospeda a réplica primária atual.</span><span class="sxs-lookup"><span data-stu-id="5be94-111">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
-   <span data-ttu-id="5be94-112">Você precisa ter um ambiente de TI híbrido onde sua sub-rede local tenha um VPN site a site com o Azure.</span><span class="sxs-lookup"><span data-stu-id="5be94-112">You must have a hybrid-IT environment where your on-premise subnet has a site-to-site VPN with Azure.</span></span> <span data-ttu-id="5be94-113">Para obter mais informações, veja [Configurar um VPN de site a site no Portal de Gerenciamento](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span><span class="sxs-lookup"><span data-stu-id="5be94-113">For more information, see [Configure a Site-to-Site VPN in the Management Portal](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span></span>  
  
-   <span data-ttu-id="5be94-114">Seu grupo de disponibilidade deve conter réplicas de disponibilidade locais.</span><span class="sxs-lookup"><span data-stu-id="5be94-114">Your availability group must contain on-premise availability replicas.</span></span>  
  
-   <span data-ttu-id="5be94-115">Os clientes para o ouvinte do grupo de disponibilidade precisarão ter conectividade com a Internet se quiserem manter a conectividade com o ouvinte quando o grupo de disponibilidade tiver feito o failover em uma réplica do Azure.</span><span class="sxs-lookup"><span data-stu-id="5be94-115">Clients to the availability group listener must have connectivity to the Internet if they want to maintain connectivity with the listener when the availability group is failed over to an Azure replica.</span></span>  
  
-   <span data-ttu-id="5be94-116">**Pré-requisitos para usar sincronização de dados inicial total** Você precisará especificar um compartilhamento de rede para que o assistente crie e acesse backups.</span><span class="sxs-lookup"><span data-stu-id="5be94-116">**Prerequisites for using full initial data synchronization** You will need to specify a network share in order for the wizard to create and access backups.</span></span> <span data-ttu-id="5be94-117">Para a réplica primária, a conta usada para iniciar o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] deve ter permissões de leitura e gravação no sistema de arquivos em um compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="5be94-117">For the primary replica, the account used to start the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must have read and write file-system permissions on a network share.</span></span> <span data-ttu-id="5be94-118">Para réplicas secundárias, a conta deve ter permissão de leitura no compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="5be94-118">For secondary replicas, the account must have read permission on the network share.</span></span>  
  
     <span data-ttu-id="5be94-119">Se você não puder usar o assistente para executar a sincronização de dados inicial completa, precisará preparar seus bancos de dados secundários manualmente.</span><span class="sxs-lookup"><span data-stu-id="5be94-119">If you are unable to use the wizard to perform full initial data synchronization, you need to prepare your secondary databases manually.</span></span> <span data-ttu-id="5be94-120">Você pode fazer isto antes de ou depois de executar o assistente.</span><span class="sxs-lookup"><span data-stu-id="5be94-120">You can do this before or after running the wizard.</span></span> <span data-ttu-id="5be94-121">Para obter mais informações, consulte [Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5be94-121">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5be94-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="5be94-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5be94-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="5be94-123">Permissions</span></span>  
 <span data-ttu-id="5be94-124">Consulte [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span><span class="sxs-lookup"><span data-stu-id="5be94-124">See [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span></span>  
  
##  <a name="using-the-add-azure-replica-wizard-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5be94-125">Usando o Assistente para Adicionar Réplica do Azure (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5be94-125">Using the Add Azure Replica Wizard (SQL Server Management Studio)</span></span>  
 <span data-ttu-id="5be94-126">O Assistente para Adicionar Réplica do Azure pode ser iniciado a partir da [Página Especificar Réplicas](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5be94-126">The Add Azure Replica Wizard can be launched from the [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md).</span></span> <span data-ttu-id="5be94-127">Há duas maneiras de chegar a essa página:</span><span class="sxs-lookup"><span data-stu-id="5be94-127">There are two ways to reach this page:</span></span>  
  
-   [<span data-ttu-id="5be94-128">Usar o Assistente de Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5be94-128">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="5be94-129">Usar o Assistente para Adicionar Réplica ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5be94-129">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
 <span data-ttu-id="5be94-130">Quando você tiver iniciado o Assistente para Adicionar Réplica do Azure, siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="5be94-130">Once you have launched the Add Azure Replica Wizard, follow the steps below:</span></span>  
  
1.  <span data-ttu-id="5be94-131">Primeiro, baixe um certificado de gerenciamento para a sua assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="5be94-131">First, download a management certificate for your Azure subscription.</span></span> <span data-ttu-id="5be94-132">Clique em **Download** para abrir a página de entrada.</span><span class="sxs-lookup"><span data-stu-id="5be94-132">Click **Download** to open the sign-in page.</span></span>  
  
2.  <span data-ttu-id="5be94-133">Na página de entrada, entre na sua assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="5be94-133">In the sign-in page, sign in to your Azure subscription.</span></span> <span data-ttu-id="5be94-134">Quando você estiver conectado, o assistente instalará um certificado de gerenciamento no computador local.</span><span class="sxs-lookup"><span data-stu-id="5be94-134">Once you are signed in, the wizard installs a management certificate onto your local machine.</span></span> <span data-ttu-id="5be94-135">Esse certificado de gerenciamento é carregado automaticamente quando você usa esse assistente novamente.</span><span class="sxs-lookup"><span data-stu-id="5be94-135">This management certificate is automatically loaded when you use this wizard again.</span></span> <span data-ttu-id="5be94-136">Se você baixou vários certificados de gerenciamento, poderá clicar no botão **...** para selecionar o que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="5be94-136">If you have downloaded multiple management certificates, you can click the **...** button to select the one you want to use.</span></span>  
  
3.  <span data-ttu-id="5be94-137">Em seguida, conecte-se à sua assinatura clicando em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="5be94-137">Next, connect to your subscription by clicking **Connect**.</span></span> <span data-ttu-id="5be94-138">Quando você estiver conectado, as listas suspensas serão preenchidas com seus parâmetros do Azure, como **Rede Virtual** e **Sub-Rede de Rede Virtual**.</span><span class="sxs-lookup"><span data-stu-id="5be94-138">Once you are connected, the drop-down lists are populated with your Azure parameters, such as **Virtual Network** and **Virtual Network Subnet**.</span></span>  
  
4.  <span data-ttu-id="5be94-139">Especifique as configurações da máquina virtual do Azure que hospedará a nova réplica secundária:</span><span class="sxs-lookup"><span data-stu-id="5be94-139">Specify the settings for the Azure VM that will host the new secondary replica:</span></span>  
  
     <span data-ttu-id="5be94-140">Imagem</span><span class="sxs-lookup"><span data-stu-id="5be94-140">Image</span></span>  
     <span data-ttu-id="5be94-141">O nome da imagem do SQL Server a ser usada para a máquina virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="5be94-141">The name of the SQL Server image to use for the Azure VM</span></span>  
  
     <span data-ttu-id="5be94-142">Tamanho da VM</span><span class="sxs-lookup"><span data-stu-id="5be94-142">VM Size</span></span>  
     <span data-ttu-id="5be94-143">O tamanho da máquina virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="5be94-143">The size of the Azure VM</span></span>  
  
     <span data-ttu-id="5be94-144">Nome da VM</span><span class="sxs-lookup"><span data-stu-id="5be94-144">VM Name</span></span>  
     <span data-ttu-id="5be94-145">O nome DNS da máquina virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="5be94-145">The DNS name of the Azure VM</span></span>  
  
     <span data-ttu-id="5be94-146">Nome de usuário da máquina virtual</span><span class="sxs-lookup"><span data-stu-id="5be94-146">VM Username</span></span>  
     <span data-ttu-id="5be94-147">O nome de usuário do administrador padrão da máquina virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="5be94-147">The username of the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="5be94-148">Senha do administrador da máquina virtual (e confirmar senha)</span><span class="sxs-lookup"><span data-stu-id="5be94-148">VM Administrator Password (and Confirm Password)</span></span>  
     <span data-ttu-id="5be94-149">A senha do administrador padrão da máquina virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="5be94-149">The password for the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="5be94-150">Rede Virtual</span><span class="sxs-lookup"><span data-stu-id="5be94-150">Virtual Network</span></span>  
     <span data-ttu-id="5be94-151">A rede virtual em que a máquina virtual do Azure será colocada</span><span class="sxs-lookup"><span data-stu-id="5be94-151">The virtual network in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="5be94-152">Sub-Rede de Rede Virtual</span><span class="sxs-lookup"><span data-stu-id="5be94-152">Virtual Network Subnet</span></span>  
     <span data-ttu-id="5be94-153">A sub-rede da rede virtual em que a máquina virtual do Azure será colocada</span><span class="sxs-lookup"><span data-stu-id="5be94-153">The virtual network subnet in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="5be94-154">Domínio</span><span class="sxs-lookup"><span data-stu-id="5be94-154">Domain</span></span>  
     <span data-ttu-id="5be94-155">O domínio do AD (Active Directory) para adicionar a máquina virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="5be94-155">The Active Directory (AD) domain to join the Azure VM</span></span>  
  
     <span data-ttu-id="5be94-156">Nome de usuário de domínio</span><span class="sxs-lookup"><span data-stu-id="5be94-156">Domain Username</span></span>  
     <span data-ttu-id="5be94-157">O nome de usuário do AD usado para adicionar a máquina virtual do Azure ao domínio</span><span class="sxs-lookup"><span data-stu-id="5be94-157">The AD username used to join the Azure VM to the domain</span></span>  
  
     <span data-ttu-id="5be94-158">Senha</span><span class="sxs-lookup"><span data-stu-id="5be94-158">Password</span></span>  
     <span data-ttu-id="5be94-159">A senha usada para adicionar a máquina virtual do Azure ao domínio</span><span class="sxs-lookup"><span data-stu-id="5be94-159">The password used to join the Azure VM to the domain</span></span>  
  
5.  <span data-ttu-id="5be94-160">Clique em **OK** para confirmar as configurações e sair do Assistente para Adicionar Réplica do Azure.</span><span class="sxs-lookup"><span data-stu-id="5be94-160">Click **OK** to commit your settings and exit the Add Azure Replica Wizard.</span></span>  
  
6.  <span data-ttu-id="5be94-161">Continue com o restante das etapas de configuração para a [Página Especificar Réplicas](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) da mesma maneira que faria para qualquer nova réplica.</span><span class="sxs-lookup"><span data-stu-id="5be94-161">Continue with the rest of the configuration steps for [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) as you do for any new replica.</span></span>  
  
     <span data-ttu-id="5be94-162">Depois de concluir o assistente de grupo de disponibilidade ou o assistente para adicionar réplica ao grupo de disponibilidade, o processo de configuração executará todas as operações no Azure para criar a nova VM, associá-la ao domínio do AD, adicioná-la ao cluster do Windows, habilitar a alta disponibilidade AlwaysOn e adicionar a nova réplica ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="5be94-162">Once you are finished with the Availability Group Wizard or the Add Replica to Availability Group Wizard, the configuration process performs all operations in Azure to create the new VM, join it to the AD domain, add it to the Windows cluster, enable AlwaysOn High Availability, and add the new replica to the availability group.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5be94-163">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="5be94-163">Related Tasks</span></span>  
  
-   [<span data-ttu-id="5be94-164">Adicionar uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5be94-164">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="5be94-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5be94-165">See Also</span></span>  
 <span data-ttu-id="5be94-166">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5be94-166">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="5be94-167">[Pré-requisitos, restrições e recomendações para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="5be94-167">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 [<span data-ttu-id="5be94-168">Adicionar uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5be94-168">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
  
