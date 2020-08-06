---
title: Página assinaturas (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cf3a6bd0-e0b2-4875-a532-63ef34cfa860
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c67895babe99c92b7c09afd8cb75ca88d5cd7553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682080"
---
# <a name="subscriptions-page-report-manager"></a><span data-ttu-id="98db0-102">Página Assinaturas (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="98db0-102">Subscriptions Page (Report Manager)</span></span>
  <span data-ttu-id="98db0-103">Use a página Assinaturas para listar todas as assinaturas para o relatório atual ou fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="98db0-103">Use the Subscriptions page to list all of the subscriptions for the current report or shared data source.</span></span> <span data-ttu-id="98db0-104">Se você tiver permissão adequada (como a contida na tarefa "Gerenciar todas as assinaturas"), você poderá exibir as assinaturas de todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="98db0-104">If you have sufficient permission (as conveyed by the "Manage all subscriptions" task), you can view the subscriptions of all users.</span></span> <span data-ttu-id="98db0-105">Caso contrário, essa página só mostrará as assinaturas que você possui.</span><span class="sxs-lookup"><span data-stu-id="98db0-105">Otherwise, this page shows only the subscriptions that you own.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98db0-106">Outras páginas também contêm informações de assinatura.</span><span class="sxs-lookup"><span data-stu-id="98db0-106">Other pages also contain subscription information.</span></span> <span data-ttu-id="98db0-107">Para obter mais informações, consulte a [página minhas assinaturas &#40;Report Manager&#41;](../../2014/reporting-services/my-subscriptions-page-report-manager.md) para acessar todas as suas assinaturas em um único lugar ou a [página nova assinatura ou editar assinatura &#40;Report Manager&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md) para criar ou editar uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="98db0-107">For more information, see [My Subscriptions Page &#40;Report Manager&#41;](../../2014/reporting-services/my-subscriptions-page-report-manager.md) to access all your subscriptions in one place or the [New Subscription or Edit Subscription Page &#40;Report Manager&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md) to create or edit a subscription.</span></span>  
  
 <span data-ttu-id="98db0-108">Algumas opções só são visíveis se houver assinaturas existentes com as quais é possível trabalhar.</span><span class="sxs-lookup"><span data-stu-id="98db0-108">Some options are visible only if there are existing subscriptions to work with.</span></span> <span data-ttu-id="98db0-109">Se nenhuma assinatura estiver definida e você estiver acessando essa página de um relatório, **Nova Assinatura** e **Nova Assinatura Orientada por Dados** serão as únicas opções na página.</span><span class="sxs-lookup"><span data-stu-id="98db0-109">If no subscriptions are defined and you are accessing this page from a report, the **New Subscription** and **New Data-Driven Subscription** are the only options on the page.</span></span>  
  
 <span data-ttu-id="98db0-110">Antes de criar uma nova assinatura, você deve verificar se a fonte de dados do relatório armazena credenciais.</span><span class="sxs-lookup"><span data-stu-id="98db0-110">Before you can create a new subscription, you must verify that the report data source uses stored credentials.</span></span> <span data-ttu-id="98db0-111">Use a página de propriedades da Fonte de Dados para armazenar credenciais.</span><span class="sxs-lookup"><span data-stu-id="98db0-111">Use the Data Sources properties page to store credentials.</span></span> <span data-ttu-id="98db0-112">Para obter mais informações, consulte [página de propriedades de fontes de dados &#40;Report Manager&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="98db0-112">For more information, see [Data Sources Properties Page &#40;Report Manager&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98db0-113">Este recurso não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98db0-113">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="98db0-114">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="98db0-114">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="98db0-115">Navegação</span><span class="sxs-lookup"><span data-stu-id="98db0-115">Navigation</span></span>  
 <span data-ttu-id="98db0-116">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="98db0-116">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-subscriptions-page-for-report"></a><span data-ttu-id="98db0-117">Para abrir a página Assinaturas do relatório</span><span class="sxs-lookup"><span data-stu-id="98db0-117">To open the Subscriptions page for report</span></span>  
  
1.  <span data-ttu-id="98db0-118">Abra o Gerenciador de Relatórios e localize o relatório para o qual você deseja exibir ou configurar uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="98db0-118">Open Report Manager, and locate the report for which you want to view or configure a subscription.</span></span>  
  
2.  <span data-ttu-id="98db0-119">Focalize o relatório e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="98db0-119">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="98db0-120">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="98db0-120">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="98db0-121">Esse procedimento abre a página de propriedades Geral do relatório.</span><span class="sxs-lookup"><span data-stu-id="98db0-121">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="98db0-122">Selecione a guia **Assinaturas** .</span><span class="sxs-lookup"><span data-stu-id="98db0-122">Select the **Subscriptions** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="98db0-123">Opções</span><span class="sxs-lookup"><span data-stu-id="98db0-123">Options</span></span>  
 <span data-ttu-id="98db0-124">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="98db0-124">**Delete**</span></span>  
 <span data-ttu-id="98db0-125">Clique para excluir uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="98db0-125">Click to delete a subscription.</span></span> <span data-ttu-id="98db0-126">Antes de excluir uma assinatura, marque a caixa de seleção ao lado de cada assinatura que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="98db0-126">Before you can delete a subscription, select the check box next to each subscription that you want to delete.</span></span>  
  
 <span data-ttu-id="98db0-127">**Nova assinatura**</span><span class="sxs-lookup"><span data-stu-id="98db0-127">**New Subscription**</span></span>  
 <span data-ttu-id="98db0-128">Clique para criar uma nova assinatura para o relatório atual.</span><span class="sxs-lookup"><span data-stu-id="98db0-128">Click to create a new subscription to the current report.</span></span> <span data-ttu-id="98db0-129">Esse botão é habilitado quando o relatório usa credenciais armazenadas ou nenhuma credencial.</span><span class="sxs-lookup"><span data-stu-id="98db0-129">This button is enabled when the report uses stored credentials or no credentials.</span></span> <span data-ttu-id="98db0-130">Esse botão não está disponível quando você abre a página Assinaturas para uma fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="98db0-130">This button is not available when you open the Subscriptions page for a shared data source.</span></span>  
  
 <span data-ttu-id="98db0-131">**Nova Assinatura Orientada por Dados**</span><span class="sxs-lookup"><span data-stu-id="98db0-131">**New Data-Driven Subscription**</span></span>  
 <span data-ttu-id="98db0-132">Clique para gerar uma lista de assinantes e opções de entrega de um comando ou uma consulta em um repositório de dados que contenha essas informações.</span><span class="sxs-lookup"><span data-stu-id="98db0-132">Click to generate a subscriber list and delivery options from a command or query against a data store that contains this information.</span></span> <span data-ttu-id="98db0-133">Esse botão é habilitado quando o relatório usa credenciais armazenadas ou nenhuma credencial.</span><span class="sxs-lookup"><span data-stu-id="98db0-133">This button is enabled when the report uses stored credentials or no credentials.</span></span> <span data-ttu-id="98db0-134">Esse botão não está disponível quando você abre a página Assinaturas para uma fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="98db0-134">This button is not available when you open the Subscriptions page for a shared data source.</span></span>  
  
 <span data-ttu-id="98db0-135">**Editar**</span><span class="sxs-lookup"><span data-stu-id="98db0-135">**Edit**</span></span>  
 <span data-ttu-id="98db0-136">Clique para exibir ou editar a descrição.</span><span class="sxs-lookup"><span data-stu-id="98db0-136">Click to view or edit the description.</span></span>  
  
 <span data-ttu-id="98db0-137">**Report**</span><span class="sxs-lookup"><span data-stu-id="98db0-137">**Report**</span></span>  
 <span data-ttu-id="98db0-138">Quando você abre essa página a partir de uma fonte de dados compartilhada, essa coluna identifica o relatório para o qual a assinatura é definida.</span><span class="sxs-lookup"><span data-stu-id="98db0-138">When you open this page from a shared data source, this column identifies the report for which the subscription is defined.</span></span> <span data-ttu-id="98db0-139">A coluna **Pasta** identifica o local do relatório.</span><span class="sxs-lookup"><span data-stu-id="98db0-139">The **Folder** column identifies the location of the report.</span></span>  
  
 <span data-ttu-id="98db0-140">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="98db0-140">**Description**</span></span>  
 <span data-ttu-id="98db0-141">Mostra uma descrição da assinatura.</span><span class="sxs-lookup"><span data-stu-id="98db0-141">Shows a description of the subscription.</span></span>  
  
 <span data-ttu-id="98db0-142">**Gatilho**</span><span class="sxs-lookup"><span data-stu-id="98db0-142">**Trigger**</span></span>  
 <span data-ttu-id="98db0-143">Identifica critérios que causam a execução da assinatura.</span><span class="sxs-lookup"><span data-stu-id="98db0-143">Identifies criteria that cause the subscription to run.</span></span> <span data-ttu-id="98db0-144">Um gatilho **TimedSubscription** é baseado em uma agenda que define quando a assinatura é executada.</span><span class="sxs-lookup"><span data-stu-id="98db0-144">A **TimedSubscription** trigger is based on a schedule that defines when the subscription runs.</span></span> <span data-ttu-id="98db0-145">Um gatilho **SnapshotUpdated** é baseado em uma atualização de um instantâneo de relatório.</span><span class="sxs-lookup"><span data-stu-id="98db0-145">A **SnapshotUpdated** trigger is based on an update to a report snapshot.</span></span>  
  
 <span data-ttu-id="98db0-146">**Proprietário**</span><span class="sxs-lookup"><span data-stu-id="98db0-146">**Owner**</span></span>  
 <span data-ttu-id="98db0-147">Exibe o nome do usuário que criou a assinatura.</span><span class="sxs-lookup"><span data-stu-id="98db0-147">Shows the name of the user who created the subscription.</span></span>  
  
 <span data-ttu-id="98db0-148">**Última Execução**</span><span class="sxs-lookup"><span data-stu-id="98db0-148">**Last Run**</span></span>  
 <span data-ttu-id="98db0-149">Exibe a última vez em que a assinatura foi processada.</span><span class="sxs-lookup"><span data-stu-id="98db0-149">Shows the last time that the subscription was processed.</span></span>  
  
 <span data-ttu-id="98db0-150">**Status**</span><span class="sxs-lookup"><span data-stu-id="98db0-150">**Status**</span></span>  
 <span data-ttu-id="98db0-151">Exibe o status da assinatura.</span><span class="sxs-lookup"><span data-stu-id="98db0-151">Shows the status of the subscription.</span></span> <span data-ttu-id="98db0-152">Geralmente, o valor do status é Novo ou a data e hora da última execução da assinatura.</span><span class="sxs-lookup"><span data-stu-id="98db0-152">Usually, the status value is either New or the date and time at which the subscription last ran.</span></span>  
  
 <span data-ttu-id="98db0-153">Um valor de status "Dados Incorretos" ocorre quando a assinatura inclui um ponteiro para valores criptografados que não são mais válidos (ou seja, para as credenciais armazenadas usadas para executar o relatório).</span><span class="sxs-lookup"><span data-stu-id="98db0-153">A status value of "Bad Data" occurs when the subscription includes a pointer to encrypted values that are no longer valid (that is, to the stored credentials used to run the report).</span></span> <span data-ttu-id="98db0-154">Valores criptografados existentes se tornam inutilizáveis quando as chaves simétricas usadas para criptografar e descriptografar dados são recriadas no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="98db0-154">Existing encrypted values become unusable when the symmetric keys used to encrypt and decrypt data are recreated on the report server.</span></span>  
  
 <span data-ttu-id="98db0-155">Uma assinatura não poderá ser processada se tiver sido desativada.</span><span class="sxs-lookup"><span data-stu-id="98db0-155">A subscription cannot be processed if it has been deactivated.</span></span> <span data-ttu-id="98db0-156">Para atualizar a assinatura e torná-la operacional, abra e depois salve a assinatura.</span><span class="sxs-lookup"><span data-stu-id="98db0-156">To update the subscription and make it operational, open and then save the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98db0-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98db0-157">See Also</span></span>  
 <span data-ttu-id="98db0-158">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="98db0-158">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="98db0-159">[Criar, modificar e excluir assinaturas padrão &#40;Reporting Services no modo nativo&#41;](subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md) </span><span class="sxs-lookup"><span data-stu-id="98db0-159">[Create, Modify, and Delete Standard Subscriptions &#40;Reporting Services in Native Mode&#41;](subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md) </span></span>  
 <span data-ttu-id="98db0-160">[Criar, modificar e excluir agendas](subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="98db0-160">[Create, Modify, and Delete Schedules](subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="98db0-161">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="98db0-161">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
