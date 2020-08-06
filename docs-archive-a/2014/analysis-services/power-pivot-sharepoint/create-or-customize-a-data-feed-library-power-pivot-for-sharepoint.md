---
title: Criar ou personalizar uma biblioteca de feeds de dados (PowerPivot para SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data feed library
- data feeds [Analysis Services with SharePoint]
ms.assetid: 699fbeb9-42ab-436b-beba-214db51ea3dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: b86f63c1af094ea9e8a2a1149debeac387bccbf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680080"
---
# <a name="create-or-customize-a-data-feed-library-powerpivot-for-sharepoint"></a><span data-ttu-id="85cd0-102">Criar ou personalizar uma biblioteca de feed de dados (PowerPivot para SharePoint)</span><span class="sxs-lookup"><span data-stu-id="85cd0-102">Create or Customize a Data Feed Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="85cd0-103">Uma *biblioteca de feed de dados* é uma biblioteca do SharePoint com finalidade especial que permite registrar e compartilhar documentos do serviço de dados Atom (.atomsvc).</span><span class="sxs-lookup"><span data-stu-id="85cd0-103">A *data feed library* is a special-purpose SharePoint library that enables you to register and share Atom data service documents (.atomsvc).</span></span> <span data-ttu-id="85cd0-104">Esses documentos fornecem feeds de dados XML a pastas de trabalho do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] ou outros aplicativos cliente que oferecem suporte ao formato de feed de dados Atom.</span><span class="sxs-lookup"><span data-stu-id="85cd0-104">These documents provide XML data feeds to [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks or other client applications that support the Atom data feed format.</span></span> <span data-ttu-id="85cd0-105">Uma biblioteca de feeds de dados é diferente de outras bibliotecas do SharePoint porque oferece a capacidade de:</span><span class="sxs-lookup"><span data-stu-id="85cd0-105">A data feed library is different from other SharePoint libraries because it gives you the ability to:</span></span>

-   <span data-ttu-id="85cd0-106">Criar ou editar um *documento do serviço de dados*usado para especificar uma conexão HTTP com um feed específico.</span><span class="sxs-lookup"><span data-stu-id="85cd0-106">Create or edit a *data service document*, used to specify an HTTP connection to a specific feed.</span></span>

-   <span data-ttu-id="85cd0-107">Compartilhar e gerenciar documentos do serviço de dados em um local central.</span><span class="sxs-lookup"><span data-stu-id="85cd0-107">Share and manage data service documents in a central location.</span></span>

-   <span data-ttu-id="85cd0-108">Identifique visualmente os documentos do serviço de dados por um ícone, para que você possa distinguir facilmente documentos de serviço de outros documentos armazenados na mesma biblioteca: ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span><span class="sxs-lookup"><span data-stu-id="85cd0-108">Visually identify data service documents by an icon, so that you can easily distinguish service documents from other documents stored in the same library: ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span></span>

 <span data-ttu-id="85cd0-109">Uma biblioteca de feeds de dados sempre contém arquivos de documento do serviço de dados (.atomsvc) e nunca o próprio feed de dados.</span><span class="sxs-lookup"><span data-stu-id="85cd0-109">A data feed library always contains data service document (.atomsvc) files, and never the data feed itself.</span></span> <span data-ttu-id="85cd0-110">Ao contrário de um feed de dados, que consiste em dados XML estáticos, o documento do serviço de dados especifica uma URL para um serviço ou aplicativo que gera um feed sob solicitação, fornecendo informações de conexão reutilizáveis para operações de importação repetíveis.</span><span class="sxs-lookup"><span data-stu-id="85cd0-110">Unlike a data feed, which consists of static XML data, the data service document specifies a URL to a service or application that generates a feed upon request, providing reusable connection information for repeatable import operations.</span></span>

 <span data-ttu-id="85cd0-111">Este tópico contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="85cd0-111">This topic contains the following sections:</span></span>

 [<span data-ttu-id="85cd0-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="85cd0-112">Prerequisites</span></span>](#prereq)

 [<span data-ttu-id="85cd0-113">Criar uma nova biblioteca de feeds de dados</span><span class="sxs-lookup"><span data-stu-id="85cd0-113">Create a New Data Feed Library</span></span>](#createlib)

 [<span data-ttu-id="85cd0-114">Adicionar o tipo de conteúdo do feed de dados a uma biblioteca</span><span class="sxs-lookup"><span data-stu-id="85cd0-114">Add the Data Feed Content Type to Any Library</span></span>](#addtolib)

##  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="85cd0-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="85cd0-115">Prerequisites</span></span>
 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] <span data-ttu-id="85cd0-116">deve ser ativada para sites para os quais você está criando a biblioteca de feeds de dados.</span><span class="sxs-lookup"><span data-stu-id="85cd0-116">feature integration must be activated for the sites for which you are creating the data feed library.</span></span> <span data-ttu-id="85cd0-117">Se o tipo de modelo da biblioteca de feeds de dados não estiver disponível, a causa mais provável será que esse pré-requisito não foi atendido.</span><span class="sxs-lookup"><span data-stu-id="85cd0-117">If the data feed library template type is not available, the most likely cause is that this prerequisite has not been met.</span></span> <span data-ttu-id="85cd0-118">Para obter mais informações, consulte [ativar a integração de recursos do PowerPivot para coleções de sites na administração central](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="85cd0-118">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>

 <span data-ttu-id="85cd0-119">Você deve ser um proprietário do site criar a biblioteca.</span><span class="sxs-lookup"><span data-stu-id="85cd0-119">You must be a site owner to create the library.</span></span>

##  <a name="create-a-new-data-feed-library"></a><a name="createlib"></a><span data-ttu-id="85cd0-120">Criar uma nova biblioteca de feeds de dados</span><span class="sxs-lookup"><span data-stu-id="85cd0-120">Create a New Data Feed Library</span></span>
 <span data-ttu-id="85cd0-121">A criação de uma biblioteca de feeds de dados é a primeira etapa para habilitar feeds de dados para pastas de trabalho do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="85cd0-121">Creating a data feed library is the first step to enabling data feeds for [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks.</span></span> <span data-ttu-id="85cd0-122">Como uma biblioteca de feeds de dados fornece páginas de aplicativo e gerenciamento para os documentos do serviço de dados, você deve ter essa biblioteca pronta para criar um novo documento.</span><span class="sxs-lookup"><span data-stu-id="85cd0-122">Because a data feed library provides application and management pages for data service documents, you must have this library in place before you can create a new document.</span></span>

 <span data-ttu-id="85cd0-123">Uma biblioteca de feeds de dados é baseada em um modelo interno e em um *tipo de conteúdo de documento do serviço de dados* pré-configurado que define propriedades e comportamentos para um documento do serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="85cd0-123">A data feed library is based on a built-in template and a preconfigured *data service document content type* that defines properties and behaviors for a data service document.</span></span>

1.  <span data-ttu-id="85cd0-124">Clique em **Ações do Site** no canto superior esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="85cd0-124">Click **Site Actions** at the top left corner of the page.</span></span>

2.  <span data-ttu-id="85cd0-125">Clique em **mais opções**...</span><span class="sxs-lookup"><span data-stu-id="85cd0-125">Click **More Options**...</span></span>

3.  <span data-ttu-id="85cd0-126">Em Bibliotecas, clique em **Biblioteca de Feeds de Dados**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-126">Under Libraries, click **Data Feed Library**.</span></span>

4.  <span data-ttu-id="85cd0-127">Digite o nome, a descrição e as preferências de inicialização e versão.</span><span class="sxs-lookup"><span data-stu-id="85cd0-127">Type the name, description, launch, and version preferences.</span></span> <span data-ttu-id="85cd0-128">Inclua informações descritivas para ajudar os usuários a identificarem essa biblioteca como armazenamento para documentos do serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="85cd0-128">Include descriptive information to help users identify this library as storage for data service documents.</span></span>

5.  <span data-ttu-id="85cd0-129">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-129">Click **Create**.</span></span>

 <span data-ttu-id="85cd0-130">Um link para a biblioteca de feeds de dados é exibido no painel Início Rápido da navegação do site atual.</span><span class="sxs-lookup"><span data-stu-id="85cd0-130">A link to the data feed library will appear in the navigation Quick Launch pane for the current site.</span></span>

 <span data-ttu-id="85cd0-131">Depois de criar uma biblioteca, você pode usá-la para criar documentos de serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="85cd0-131">After you create a library, you can use it to create data service documents.</span></span> <span data-ttu-id="85cd0-132">Para obter mais informações, consulte [usar feeds de dados &#40;PowerPivot para SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="85cd0-132">For more information, see [Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span></span>

##  <a name="add-the-data-feed-content-type-to-any-library"></a><a name="addtolib"></a><span data-ttu-id="85cd0-133">Adicionar o tipo de conteúdo do feed de dados a qualquer biblioteca</span><span class="sxs-lookup"><span data-stu-id="85cd0-133">Add the Data Feed Content Type to Any Library</span></span>
 <span data-ttu-id="85cd0-134">Se você não desejar criar uma biblioteca de feeds de dados dedicada, mas ainda quiser criar e gerenciar documentos do serviço de dados de um site do SharePoint, poderá adicionar e configurar manualmente o tipo de conteúdo de documento do serviço de dados para qualquer biblioteca que será usada para compartilhar arquivos de documento do serviço de dados (.atomsvc).</span><span class="sxs-lookup"><span data-stu-id="85cd0-134">If you do not want to create a dedicated data feed library, but you still want to create and manage data service documents from a SharePoint site, you can manually add and configure the data service document content type for any library that you will use to share data service document (.atomsvc) files.</span></span>

 <span data-ttu-id="85cd0-135">Você deve ter pelo menos a permissão Gerenciar Listas para adicionar e configurar um tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="85cd0-135">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="85cd0-136">Esta permissão é compilada no nível de permissão Design e superior.</span><span class="sxs-lookup"><span data-stu-id="85cd0-136">This permission is built into the Design permission level and above.</span></span>

 <span data-ttu-id="85cd0-137">As etapas a seguir devem ser repetidas para cada biblioteca na qual você deseja criar ou editar documentos de registro de feed de dados.</span><span class="sxs-lookup"><span data-stu-id="85cd0-137">The following steps must be repeated for each library in which you want to create or edit data feed registration documents.</span></span>

#### <a name="step-1-enable-content-type-management"></a><span data-ttu-id="85cd0-138">Etapa 1: Habilitar o gerenciamento do tipo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="85cd0-138">Step 1: Enable Content Type Management</span></span>

1.  <span data-ttu-id="85cd0-139">Abra a biblioteca de documentos para a qual você deseja habilitar vários tipos de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="85cd0-139">Open the document library for which you want to enable multiple content types.</span></span>

2.  <span data-ttu-id="85cd0-140">Na faixa de opções do SharePoint, em Ferramentas de Biblioteca, clique em **Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-140">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>

3.  <span data-ttu-id="85cd0-141">Clique em **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-141">Click **Settings**.</span></span>

4.  <span data-ttu-id="85cd0-142">Clique em **Configurações da Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-142">Click **Library Settings**.</span></span>

5.  <span data-ttu-id="85cd0-143">Em Configurações Gerais, clique em **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-143">In General Settings, click **Advanced settings**.</span></span>

6.  <span data-ttu-id="85cd0-144">Em Tipos de Conteúdo, na seção "Permitir o gerenciamento de tipos de conteúdo?",</span><span class="sxs-lookup"><span data-stu-id="85cd0-144">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="85cd0-145">clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-145">section, click **Yes**.</span></span>

7.  <span data-ttu-id="85cd0-146">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-146">Click **OK**.</span></span>

#### <a name="step-2-add-the-data-service-document-content-type"></a><span data-ttu-id="85cd0-147">Etapa 2: Adicionar o tipo de conteúdo de documento de serviço de dados</span><span class="sxs-lookup"><span data-stu-id="85cd0-147">Step 2: Add the Data Service Document Content Type</span></span>

1.  <span data-ttu-id="85cd0-148">Na seção Tipos de Conteúdo, clique em **Adicionar a partir de tipos de conteúdo de site existentes**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-148">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="85cd0-149">Se você não vir essa página, volte para o site, clique em **Biblioteca** em Ferramentas de Biblioteca e clique em **Definições da Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-149">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>

2.  <span data-ttu-id="85cd0-150">Em Tipos de Conteúdo, clique em **Adicionar a partir de tipos de conteúdo de site existentes**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-150">In Content Types, click **Add from existing site content types**.</span></span>

3.  <span data-ttu-id="85cd0-151">Em Selecionar tipos de conteúdo de site de:, selecione **Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-151">In Select site content types from:, select **Business Intelligence**.</span></span>

4.  <span data-ttu-id="85cd0-152">Em Tipos Disponíveis de Conteúdo do Site, clique em **Documento de Serviço de Dados**e clique em **Adicionar** para mover o tipo de conteúdo selecionado para a lista Tipos de conteúdo a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="85cd0-152">In Available Site Content Types, click **Data Service Document**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>

5.  <span data-ttu-id="85cd0-153">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-153">Click **OK**.</span></span>

#### <a name="step-3-verify-data-service-document-configuration"></a><span data-ttu-id="85cd0-154">Etapa 3: Verificar a configuração do documento de serviço de dados</span><span class="sxs-lookup"><span data-stu-id="85cd0-154">Step 3: Verify Data Service Document Configuration</span></span>

1.  <span data-ttu-id="85cd0-155">Abra a página inicial do site.</span><span class="sxs-lookup"><span data-stu-id="85cd0-155">Open the site home page.</span></span>

2.  <span data-ttu-id="85cd0-156">Abra a biblioteca.</span><span class="sxs-lookup"><span data-stu-id="85cd0-156">Open the library.</span></span>

3.  <span data-ttu-id="85cd0-157">Na faixa de opções do SharePoint, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-157">On the SharePoint ribbon, click **Documents**.</span></span>

4.  <span data-ttu-id="85cd0-158">Clique na seta para baixo em Novo Documento e selecione **Documento de Serviço de Dados**.</span><span class="sxs-lookup"><span data-stu-id="85cd0-158">Click the down arrow on New Document, and select **Data Service Document**.</span></span> <span data-ttu-id="85cd0-159">A página Novo Documento de Serviço de Dados deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="85cd0-159">The New Data Service Document page should appear.</span></span>

## <a name="see-also"></a><span data-ttu-id="85cd0-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="85cd0-160">See Also</span></span>
 <span data-ttu-id="85cd0-161">[Usar feeds de dados &#40;PowerPivot para SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [excluir uma biblioteca de feed de dados PowerPivot](delete-a-power-pivot-data-feed-library.md) [Administração do servidor PowerPivot e configuração na administração central](power-pivot-server-administration-and-configuration-in-central-administration.md) [feeds de dados PowerPivot](power-pivot-data-feeds.md)</span><span class="sxs-lookup"><span data-stu-id="85cd0-161">[Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [Delete a PowerPivot Data Feed Library](delete-a-power-pivot-data-feed-library.md) [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) [PowerPivot Data Feeds](power-pivot-data-feeds.md)</span></span>


