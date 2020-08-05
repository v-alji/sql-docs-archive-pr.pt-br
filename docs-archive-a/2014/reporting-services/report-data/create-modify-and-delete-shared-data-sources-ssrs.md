---
title: Criar, modificar e excluir fontes de dados compartilhadas (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- modifying data source properties
- shared data sources [Reporting Services]
- removing shared data sources
- roles [Reporting Services], shared data sources
- data sources [Reporting Services], shared
- data sources [Reporting Services], modifying properties
- deleting shared data sources
ms.assetid: 1e58c1c2-5ecf-4ce6-9d04-0a8acfba17be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7e0c0eccb605a99077570fee73687e156372bcbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573776"
---
# <a name="create-modify-and-delete-shared-data-sources-ssrs"></a><span data-ttu-id="97220-102">Criar, modificar e excluir fontes de dados compartilhadas (SSRS)</span><span class="sxs-lookup"><span data-stu-id="97220-102">Create, Modify, and Delete Shared Data Sources (SSRS)</span></span>
  <span data-ttu-id="97220-103">Uma fonte de dados compartilhada é um conjunto de propriedades de conexão de fonte de dados que pode ser referenciada por vários relatórios, modelos e assinaturas controladas por dados que são executados em um servidor de relatório do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97220-103">A shared data source is a set of data source connection properties that can be referenced by multiple reports, models, and data-driven subscriptions that run on a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server.</span></span> <span data-ttu-id="97220-104">As fontes de dados compartilhadas fornecem um modo fácil de gerenciar as propriedades da fonte de dados que geralmente são alteradas com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="97220-104">Shared data sources provide an easy way to manage data source properties that often change over time.</span></span> <span data-ttu-id="97220-105">Se a conta de usuário ou senha for alterada ou se você mover o banco de dados para outro servidor, as informações de conexão poderão ser atualizadas em um único lugar.</span><span class="sxs-lookup"><span data-stu-id="97220-105">If a user account or password changes, or if you move the database to a different server, you can update the connection information in one place.</span></span>  
  
 <span data-ttu-id="97220-106">As fontes de dados compartilhadas são opcionais para relatórios e assinaturas controladas por dados, mas são obrigatórias para modelos de relatórios.</span><span class="sxs-lookup"><span data-stu-id="97220-106">Shared data sources are optional for reports and data-driven subscriptions, but required for report models.</span></span> <span data-ttu-id="97220-107">Se você planeja usar os modelos de relatório para relatórios ad hoc, deve criar e manter um item fonte de dados compartilhada para fornecer informações de conexão ao modelo.</span><span class="sxs-lookup"><span data-stu-id="97220-107">If you plan to use report models for ad hoc reporting, you must create and maintain a shared data source item to provide connection information to the model.</span></span>  
  
 <span data-ttu-id="97220-108">Uma fonte de dados compartilhada é composta pelas seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="97220-108">A shared data source consists of the following parts:</span></span>  
  
|<span data-ttu-id="97220-109">Parte</span><span class="sxs-lookup"><span data-stu-id="97220-109">Part</span></span>|<span data-ttu-id="97220-110">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="97220-110">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="97220-111">Nome</span><span class="sxs-lookup"><span data-stu-id="97220-111">Name</span></span>|<span data-ttu-id="97220-112">Um nome que identifica o item dentro da hierarquia de pastas do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="97220-112">A name that identifies the item within the report server folder hierarchy.</span></span>|  
|<span data-ttu-id="97220-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="97220-113">Description</span></span>|<span data-ttu-id="97220-114">Uma descrição que aparece com o item no Gerenciador de Relatórios quando você exibe os conteúdos da pasta.</span><span class="sxs-lookup"><span data-stu-id="97220-114">A description that appears with the item in Report Manager when you view the contents of the folder.</span></span>|  
|<span data-ttu-id="97220-115">Tipo de conexão</span><span class="sxs-lookup"><span data-stu-id="97220-115">Connection type</span></span>|<span data-ttu-id="97220-116">A extensão de processamento de dados usada com a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="97220-116">The data processing extension used with the data source.</span></span> <span data-ttu-id="97220-117">Você só poderá usar extensões de processamento de dados que estiverem implantadas no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="97220-117">You can only use data processing extensions that are deployed on the report server.</span></span> <span data-ttu-id="97220-118">Para obter mais informações sobre as extensões de processamento de dados incluídas no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], consulte [Fontes de dados com suporte no Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span><span class="sxs-lookup"><span data-stu-id="97220-118">For more information about data processing extensions included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span></span>|  
|<span data-ttu-id="97220-119">Cadeia de conexão</span><span class="sxs-lookup"><span data-stu-id="97220-119">Connection string</span></span>|<span data-ttu-id="97220-120">A cadeia de conexão para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="97220-120">The connection string for the database.</span></span> <span data-ttu-id="97220-121">Para obter mais informações e exibir exemplos de cadeias de conexão para fontes de dados usadas com frequência, consulte [conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="97220-121">For more information and to view examples of connection strings to frequently used data sources, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span></span>|  
|<span data-ttu-id="97220-122">Tipo de credencial</span><span class="sxs-lookup"><span data-stu-id="97220-122">Credential type</span></span>|<span data-ttu-id="97220-123">Especifica como as credenciais são obtidas para a conexão e se elas serão usadas depois que a conexão for estabelecida.</span><span class="sxs-lookup"><span data-stu-id="97220-123">Specifies how credentials are obtained for the connection and whether they are to be used after the connection is made.</span></span> <span data-ttu-id="97220-124">Para obter mais informações, consulte [Especificar informações de credenciais e de conexão para fontes de dados de relatório](../../integration-services/connection-manager/data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="97220-124">For more information, see [Specify Credential and Connection Information for Report Data Sources](../../integration-services/connection-manager/data-sources.md).</span></span>|  
  
 <span data-ttu-id="97220-125">Uma fonte de dados compartilhada não contém informações de consulta usadas para a recuperação de dados.</span><span class="sxs-lookup"><span data-stu-id="97220-125">A shared data source does not contain query information used to retrieve data.</span></span> <span data-ttu-id="97220-126">A consulta sempre é mantida dentro de uma definição do relatório.</span><span class="sxs-lookup"><span data-stu-id="97220-126">The query is always kept within a report definition.</span></span>  
  
## <a name="creating-and-modifying-a-shared-data-source"></a><span data-ttu-id="97220-127">Criando e modificando uma fonte de dados compartilhada</span><span class="sxs-lookup"><span data-stu-id="97220-127">Creating and Modifying a Shared Data Source</span></span>  
 <span data-ttu-id="97220-128">Para criar uma fonte de dados compartilhada ou modificar suas propriedades, é preciso ter permissões para **Gerenciar fontes de dados** no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="97220-128">To create a shared data source or modify its properties, you must have **Manage data sources** permissions on the report server.</span></span> <span data-ttu-id="97220-129">Se o servidor de relatórios for executado em modo nativo, você poderá usar o Gerenciador de Relatórios para criar e configurar a fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="97220-129">If the report server runs in native mode, you can use Report Manager to create and configure the shared data source.</span></span> <span data-ttu-id="97220-130">Se o servidor de relatórios for executado no modo integrado do SharePoint, use as páginas de aplicativo em um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="97220-130">If the report server runs in SharePoint integrated mode, you can use the application pages on a SharePoint site.</span></span> <span data-ttu-id="97220-131">Para qualquer servidor de relatórios independentemente de seu modo, você pode criar uma fonte de dados compartilhada no Designer de Relatórios e publicá-la em um servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="97220-131">For any report server regardless of its mode, you can create a shared data source in Report Designer and then publish it to a target server.</span></span>  
  
 <span data-ttu-id="97220-132">Para obter mais informações sobre como criar uma fonte de dados compartilhada, consulte:</span><span class="sxs-lookup"><span data-stu-id="97220-132">For more information about creating a shared data source, see:</span></span>  
  
-   [<span data-ttu-id="97220-133">Criar uma fonte de dados inserida ou compartilhada &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="97220-133">Create an Embedded or Shared Data Source &#40;SSRS&#41;</span></span>](../create-an-embedded-or-shared-data-source-ssrs.md)  
  
-   [<span data-ttu-id="97220-134">Criar e gerenciar fontes de dados compartilhadas &#40;Reporting Services no modo integrado do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="97220-134">Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md)  
  
 <span data-ttu-id="97220-135">Depois de criar uma fonte de dados compartilhada no servidor de relatórios, você poderá criar atribuições de função para controlar o acesso a ela, movê-la para outro local, renomeá-la ou torná-la offline para evitar o processamento de relatórios durante as operações de manutenção na fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="97220-135">After you create a shared data source on the report server, you can create role assignments to control access to it, move it to a different location, rename it, or take it offline to prevent report processing while maintenance operations are performed on the external data source.</span></span> <span data-ttu-id="97220-136">Se renomear ou mover um item fonte de dados compartilhada para outro local na hierarquia de pastas do servidor de relatórios, as informações de caminho em todos os relatórios ou assinaturas que fazem referência à fonte de dados compartilhada serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="97220-136">If you rename or move a shared data source item to another location in the report server folder hierarchy, the path information in all reports or subscriptions that reference the shared data source are updated accordingly.</span></span> <span data-ttu-id="97220-137">Ao colocar a fonte de dados no estado offline, todos os relatórios, modelos e assinaturas não serão executados enquanto a fonte de dados não for reativada.</span><span class="sxs-lookup"><span data-stu-id="97220-137">If you take the shared data source offline, all reports, models, and subscriptions will not run until you re-enable the data source.</span></span>  
  
 <span data-ttu-id="97220-138">Para obter mais informações sobre como controlar o acesso às fontes de dados compartilhadas na hierarquia de pastas do servidor de relatório, consulte [Proteger itens de fontes de dados compartilhadas](../security/secure-shared-data-source-items.md).</span><span class="sxs-lookup"><span data-stu-id="97220-138">For more information about controlling access to shared data sources in the report server folder hierarchy, see [Secure Shared Data Source Items](../security/secure-shared-data-source-items.md).</span></span>  
  
## <a name="deleting-a-shared-data-source"></a><span data-ttu-id="97220-139">Excluindo uma fonte de dados compartilhada</span><span class="sxs-lookup"><span data-stu-id="97220-139">Deleting a Shared Data Source</span></span>  
 <span data-ttu-id="97220-140">Você pode excluir uma fonte de dados compartilhada da mesma forma que exclui qualquer item do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="97220-140">You can delete a shared data source the same way that you delete any item from the report server.</span></span> <span data-ttu-id="97220-141">No Report Manager, abra a pasta no modo de exibição detalhes, selecione o item e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="97220-141">In Report Manager, you open the folder in Details View, select the item, and click **Delete**.</span></span> <span data-ttu-id="97220-142">Em uma página de aplicativo em um site do SharePoint, abra a biblioteca do SharePoint, selecione o item e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="97220-142">In an application page on a SharePoint site, you open the SharePoint library, select the item, and click **Delete**.</span></span>  
  
 <span data-ttu-id="97220-143">A exclusão de uma fonte de dados compartilhada desabilitará todos os relatórios, modelos ou assinaturas controladas por dados que a usam.</span><span class="sxs-lookup"><span data-stu-id="97220-143">Deleting a shared data source will deactivate any report, model, or data-driven subscription that uses it.</span></span> <span data-ttu-id="97220-144">Sem as informações de conexão da fonte de dados, os itens não poderão ser executados.</span><span class="sxs-lookup"><span data-stu-id="97220-144">Without the data source connection information, the items will no longer run.</span></span> <span data-ttu-id="97220-145">Para habilitar esses itens, abra cada um deles e siga as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="97220-145">To activate these items, you must open each one and do the following:</span></span>  
  
-   <span data-ttu-id="97220-146">Para os relatórios e as assinaturas controlados por dados que fazem referência à fonte de dados compartilhada, você pode especificar as informações de conexão da fonte de dados nas propriedades do relatório ou da assinatura, ou também pode selecionar uma nova fonte de dados compartilhada que contenha os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="97220-146">For reports and data-driven subscriptions that reference the shared data source, you can specify data source connection information in report properties or subscription, or you can select a new shared data source that has the values you want to use.</span></span>  
  
-   <span data-ttu-id="97220-147">Para modelos e relatórios do Construtor de Relatórios que usam esse modelo, é preciso especificar uma nova fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="97220-147">For models and Report Builder reports that use that model, you must specify a new shared data source.</span></span> <span data-ttu-id="97220-148">Os modelos podem obter as informações de conexão da fonte de dados somente pelas fontes de dados compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="97220-148">Models get data source connection information only through shared data sources.</span></span>  
  
 <span data-ttu-id="97220-149">Para exibir a lista de relatórios e modelos que usam a fonte de dados, abra a página Itens Dependentes da fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="97220-149">To view a list of reports and models that use the data source, open the Dependent Items page for the shared data source.</span></span> <span data-ttu-id="97220-150">Você pode acessar essa página quando abrir a fonte de dados no Gerenciador de Relatórios ou uma página de aplicativo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="97220-150">You can access this page when you open the data source in Report Manager or a SharePoint application page.</span></span> <span data-ttu-id="97220-151">Observe que a página Itens Dependente não mostra as assinaturas controladas por dados.</span><span class="sxs-lookup"><span data-stu-id="97220-151">Note that the Dependent Items page does not show data-driven subscriptions.</span></span> <span data-ttu-id="97220-152">Se uma fonte de dados compartilhada for usada por uma assinatura, a assinatura não será exibida na lista de itens dependentes.</span><span class="sxs-lookup"><span data-stu-id="97220-152">If a shared data source is used by a subscription, the subscription will not appear in the dependent items list.</span></span>  
  
 <span data-ttu-id="97220-153">Não existe a operação Desfazer para a exclusão de uma fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="97220-153">There is no Undo operation for deleting a shared data source.</span></span> <span data-ttu-id="97220-154">Entretanto, em caso de exclusão acidental, você poderá criar uma nova fonte de dados compartilhada usando os mesmos valores de propriedades daquela que foi excluída.</span><span class="sxs-lookup"><span data-stu-id="97220-154">However, if you accidentally delete a shared data source, you can create a new one using the same property values as the one you deleted.</span></span> <span data-ttu-id="97220-155">Também será preciso abrir cada relatório, modelo e assinatura controlada por dados para reassociar a fonte de dados compartilhada ao item que a usa, mas como as propriedades serão as mesmas, os relatórios, os modelos e as assinaturas continuarão funcionando normalmente.</span><span class="sxs-lookup"><span data-stu-id="97220-155">You will have to open each report, model, and data-driven subscription to rebind the shared data source to the item that uses it, but as long as the data source properties are the same as before, the reports, models, and subscriptions will continue to function as before.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97220-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="97220-156">See Also</span></span>  
 <span data-ttu-id="97220-157">[Criar e gerenciar fontes de dados compartilhadas &#40;Reporting Services no modo integrado do SharePoint&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span><span class="sxs-lookup"><span data-stu-id="97220-157">[Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span></span>  
 <span data-ttu-id="97220-158">[Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="97220-158">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="97220-159">[Gerenciar fontes de dados de relatório](manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="97220-159">[Manage Report Data Sources](manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="97220-160">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="97220-160">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="97220-161">[Conexões de dados ou fontes de dados inseridas e compartilhadas &#40;Construtor de Relatórios e SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="97220-161">[Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="97220-162">[Página Propriedades das fontes de dados &#40;Report Manager&#41;](../data-sources-properties-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="97220-162">[Data Sources Properties Page &#40;Report Manager&#41;](../data-sources-properties-page-report-manager.md) </span></span>  
 <span data-ttu-id="97220-163">[Criar, excluir ou modificar uma fonte de dados compartilhada &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="97220-163">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 [<span data-ttu-id="97220-164">Configurar as propriedades de fonte de dados de um relatório &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="97220-164">Configure Data Source Properties for a Report  &#40;Report Manager&#41;</span></span>](configure-data-source-properties-for-a-report-report-manager.md)  
  
  