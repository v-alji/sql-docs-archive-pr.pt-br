---
title: Compartilhar feeds de dados usando uma biblioteca de feeds de dados (PowerPivot para SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data feeds [Analysis Services with SharePoint]
ms.assetid: 4ec98dec-0cd2-4727-bb79-5bf6f8a865d6
author: minewiskan
ms.author: owend
ms.openlocfilehash: cb24a0ae66cdb0b0623aaa217be778280bdb14ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574316"
---
# <a name="share-data-feeds-using-a-data-feed-library-powerpivot-for-sharepoint"></a><span data-ttu-id="80b34-102">Compartilhar feeds de dados usando uma biblioteca de feed de dados (PowerPivot para SharePoint)</span><span class="sxs-lookup"><span data-stu-id="80b34-102">Share Data Feeds Using a Data Feed Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="80b34-103">Um feed de dados é um fluxo de dados XML que é gerado em um serviço ou aplicativo que expõe dados no formato de conexão Atom.</span><span class="sxs-lookup"><span data-stu-id="80b34-103">A data feed is an XML data stream that is generated from a service or application that exposes data in the Atom wire format.</span></span> <span data-ttu-id="80b34-104">Ele é usado cada vez mais para transportar dados entre aplicativos e para visualizadores do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="80b34-104">Increasingly, it is used to transport data between applications and to client-side viewers.</span></span> <span data-ttu-id="80b34-105">Em uma implantação PowerPivot para SharePoint, os feeds de dados são usados para popular uma [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] fonte de dados com dados de um aplicativo ou serviço com reconhecimento de Atom.</span><span class="sxs-lookup"><span data-stu-id="80b34-105">In a PowerPivot for SharePoint deployment, data feeds are used to populate a [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data source with data from an Atom-aware application or service.</span></span>  
  
 <span data-ttu-id="80b34-106">Se já usar uma combinação de aplicativos com reconhecimento do Atom, você talvez nunca precise saber como os feeds são gerados e consumidos porque a transferência de dados é transparente entre os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="80b34-106">If you already use a combination of Atom-aware applications, you might never need to know how feeds are generated and consumed because the data transfer is seamless between the applications.</span></span> <span data-ttu-id="80b34-107">No entanto, frequentemente as organizações que usam soluções personalizadas para publicar feeds Atom precisam de uma maneira de disponibilizar os feeds para os operadores de informações.</span><span class="sxs-lookup"><span data-stu-id="80b34-107">However, organizations that use custom solutions to publish Atom feeds often need a way to make feeds available to information workers.</span></span> <span data-ttu-id="80b34-108">Uma maneira de fazer isso é criar e compartilhar arquivos de documento de serviço de dados (.atomsvc) que fornecem conexões às origens online que geram os feeds.</span><span class="sxs-lookup"><span data-stu-id="80b34-108">One way to do that is to create and share data service document (.atomsvc) files that provide connections to the online sources that produce the feeds.</span></span> <span data-ttu-id="80b34-109">Uma biblioteca com finalidade especial, chamada de biblioteca de feed de dados, dá suporte à criação e ao compartilhamento de documentos de serviço de dados em um aplicativo Web do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="80b34-109">A special-purpose library, called a data feed library, supports creating and sharing data service documents in a SharePoint web application.</span></span>  
  
 <span data-ttu-id="80b34-110">Este tópico contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="80b34-110">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="80b34-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="80b34-111">Prerequisites</span></span>](#prereq)  
  
 [<span data-ttu-id="80b34-112">Criar um documento de serviço de dados</span><span class="sxs-lookup"><span data-stu-id="80b34-112">Create a Data Service Document</span></span>](#createdsdoc)  
  
 [<span data-ttu-id="80b34-113">Proteger um documento de serviço de dados</span><span class="sxs-lookup"><span data-stu-id="80b34-113">Secure a Data Service Document</span></span>](#securedsdoc)  
  
 [<span data-ttu-id="80b34-114">Modificar um documento de serviço de dados</span><span class="sxs-lookup"><span data-stu-id="80b34-114">Modify a Data Service Document</span></span>](#modifydsdoc)  
  
 [<span data-ttu-id="80b34-115">Próxima etapa: usar um documento de serviço de dados</span><span class="sxs-lookup"><span data-stu-id="80b34-115">Next Step: Use a Data Service Document</span></span>](#usedsdoc)  
  
> [!NOTE]  
>  <span data-ttu-id="80b34-116">Embora os feeds de dados sejam usados para adicionar dados da Web a uma fonte de dados do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] criada em um [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], qualquer aplicativo cliente que possa ler um feed Atom pode processar um documento de serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-116">Although data feeds are used to add Web data to a [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data source that you create in a [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], any client application that can read an Atom feed can process a data service document.</span></span>  
  
##  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="80b34-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="80b34-117">Prerequisites</span></span>  
 <span data-ttu-id="80b34-118">Você deve ter uma implantação de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] PowerPivot para SharePoint que adiciona [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] o processamento de consulta a um farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="80b34-118">You must have a deployment of [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] PowerPivot for SharePoint that adds [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] query processing to a SharePoint farm.</span></span> <span data-ttu-id="80b34-119">O suporte ao feed de dados é implantado por meio do pacote de solução [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80b34-119">Data Feed support is deployed through the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] solution package.</span></span>  
  
 <span data-ttu-id="80b34-120">Você deve ter uma biblioteca do SharePoint que dê suporte ao tipo de conteúdo de documento de serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-120">You must have a SharePoint library that supports the data service document content type.</span></span> <span data-ttu-id="80b34-121">Uma biblioteca de Feed de Dados padrão é recomendada para essa finalidade, mas você pode adicionar manualmente o tipo de conteúdo a qualquer biblioteca.</span><span class="sxs-lookup"><span data-stu-id="80b34-121">A default Data Feed library is recommended for this purpose, but you can manually add the content type to any library.</span></span> <span data-ttu-id="80b34-122">Para obter mais informações, consulte [criar ou personalizar uma biblioteca de feeds de dados &#40;PowerPivot para SharePoint&#41;](create-or-customize-a-data-feed-library-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="80b34-122">For more information, see [Create or Customize a Data Feed Library &#40;PowerPivot for SharePoint&#41;](create-or-customize-a-data-feed-library-power-pivot-for-sharepoint.md).</span></span>  
  
 <span data-ttu-id="80b34-123">Você deve ter um serviço de dados ou uma fonte de dados online que forneça os dados tabulares XML no formato Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="80b34-123">You must have a data service or online data source that provides XML tabular data in the Atom 1.0 format.</span></span>  
  
 <span data-ttu-id="80b34-124">Você deve ter permissões de colaboração em um site do SharePoint para criar ou gerenciar um documento de serviço de dados em uma biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="80b34-124">You must have Contribute permissions on a SharePoint site to create or manage a data service document in a SharePoint library.</span></span>  
  
##  <a name="create-a-data-service-document"></a><a name="createdsdoc"></a> <span data-ttu-id="80b34-125">Criar um documento de serviço de dados</span><span class="sxs-lookup"><span data-stu-id="80b34-125">Create a Data Service Document</span></span>  
 <span data-ttu-id="80b34-126">Um documento de serviço de dados é uma solicitação permanente para transmissão de dados sob solicitação de uma fonte de dados ou aplicativo online que fornece dados em um formato de feed.</span><span class="sxs-lookup"><span data-stu-id="80b34-126">A data service document is a standing request to stream data upon request from an online data source or application that provides data in a feed format.</span></span> <span data-ttu-id="80b34-127">Ao criar um documento de serviço de dados, você especifica um ponteiro para um ou mais serviços de dados endereçáveis por URL que fornecem o XML tabular no formato Atom distribuído.</span><span class="sxs-lookup"><span data-stu-id="80b34-127">When you create a data service document, you specify a pointer to one or more URL addressable data services that provide XML tabular in Atom syndicated format.</span></span>  
  
 <span data-ttu-id="80b34-128">Um único documento pode especificar vários feeds de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-128">A single document can specify multiple data feeds.</span></span> <span data-ttu-id="80b34-129">Isso será útil se você desejar recuperar um conjunto de cargas de dados do mesmo serviço ou até mesmo de serviços diferentes em uma única operação de importação.</span><span class="sxs-lookup"><span data-stu-id="80b34-129">This is useful if you want to retrieve a set of data payloads from the same service, or even from different services, in a single import operation.</span></span>  
  
1.  <span data-ttu-id="80b34-130">Em um site do SharePoint, abra a biblioteca de Feed de Dados ou outra biblioteca de documentos à qual você adicionou e configurou o tipo de conteúdo de serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-130">On a SharePoint site, open the Data Feed library or another document library to which you have added and configured the data service content type.</span></span> <span data-ttu-id="80b34-131">Para localizar uma biblioteca de Feed de Dados criada anteriormente, clique em **Exibir Tudo** no Início Rápido.</span><span class="sxs-lookup"><span data-stu-id="80b34-131">To find a Data Feed library that was previously created, click **View All** on the Quick Launch.</span></span>  
  
2.  <span data-ttu-id="80b34-132">Na faixa de opções na parte superior da página, em Ferramentas de Documento, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="80b34-132">On the ribbon at the top of the page, in Document Tools, click **Documents**.</span></span>  
  
3.  <span data-ttu-id="80b34-133">Clique em **Novo Documento** e selecione **Documento de Serviço de Dados**.</span><span class="sxs-lookup"><span data-stu-id="80b34-133">Click **New Document,** and then select **Data Service Document**.</span></span>  
  
4.  <span data-ttu-id="80b34-134">Na página Novo Documento de Serviço de Dados, digite as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="80b34-134">In the New Data Service Document page, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="80b34-135">Um nome e uma descrição para o documento de serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-135">A name and description for the data service document.</span></span> <span data-ttu-id="80b34-136">Forneça detalhes suficientes para que os usuários possam determinar se devem usar o feed.</span><span class="sxs-lookup"><span data-stu-id="80b34-136">Be sure to provide sufficient detail so that users can determine whether to use the feed.</span></span>  
  
    2.  <span data-ttu-id="80b34-137">Em Feed de Dados, digite uma URL para um serviço de dados ou aplicativo Web que forneça dados no formato Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="80b34-137">In Data Feed, enter a URL to a data service or Web application that provides data in the Atom 1.0 format.</span></span>  
  
         <span data-ttu-id="80b34-138">A URL deve ser resolvida para um serviço que retorna dados estruturados ou semiestruturados em linhas e colunas.</span><span class="sxs-lookup"><span data-stu-id="80b34-138">The URL must resolve to a service that returns structured or semi-structured data in rows and columns.</span></span> <span data-ttu-id="80b34-139">O serviço deve retornar dados anonimamente ou por meio das credenciais de segurança do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="80b34-139">The service should return data anonymously or via the security credentials of the current user.</span></span>  
  
         <span data-ttu-id="80b34-140">A URL deve ser resolvida para um serviço que dê suporte à Autenticação do Windows, à autenticação básica ou ao acesso anônimo.</span><span class="sxs-lookup"><span data-stu-id="80b34-140">The URL must resolve to a service that supports Windows Authentication, Basic authentication, or anonymous access.</span></span> <span data-ttu-id="80b34-141">O usuário que importa o feed especifica qual esquema usar.</span><span class="sxs-lookup"><span data-stu-id="80b34-141">The user who imports the feed specifies which scheme to use.</span></span> <span data-ttu-id="80b34-142">Por padrão, a segurança integrada é selecionada.</span><span class="sxs-lookup"><span data-stu-id="80b34-142">Integrated security is selected by default.</span></span>  
  
         <span data-ttu-id="80b34-143">A URL de um feed de dados pode incluir parâmetros.</span><span class="sxs-lookup"><span data-stu-id="80b34-143">A data feed URL can include parameters.</span></span> <span data-ttu-id="80b34-144">Tipos diferentes de tecnologias de serviço de dados dão suporte a esquemas avançados de endereçamento por URL que permitem selecionar precisamente os dados que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="80b34-144">Different types of data service technologies support advanced URL addressing schemes that allow you to precisely select the data you want to use.</span></span> <span data-ttu-id="80b34-145">Por exemplo, um serviço de dados do ADO.NET fornece parâmetros de URL para especificar entidades, associações e caminhos de navegação nos dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="80b34-145">For example, an ADO.NET data service provides URL parameters for specifying entities, associations, and navigation paths in the underlying data.</span></span> <span data-ttu-id="80b34-146">Ao especificar uma URL complexa como uma origem de um feed de dados, você pode especificar precisamente o conjunto de dados que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="80b34-146">By specifying a complex URL as a source of a data feed, you can precisely specify the dataset you want to use.</span></span>  
  
    3.  <span data-ttu-id="80b34-147">Para o mesmo feed de dados, digite um nome de tabela que identifique subsequentemente o conjunto de dados em um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="80b34-147">For the same data feed, enter a table name that subsequently identifies the dataset in a client application.</span></span> <span data-ttu-id="80b34-148">No [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], cada feed de dados importado é colocado em seu próprio controle de tabela em uma fonte de dados do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80b34-148">In the [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], each data feed that you import is placed in its own table control in an [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data source.</span></span> <span data-ttu-id="80b34-149">Você deve especificar o nome da tabela que recebe os dados importados ao configurar o feed de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-149">You must specify the name of the table that receives the imported data when you set up the data feed.</span></span>  
  
5.  <span data-ttu-id="80b34-150">Clique em "Adicionar outro feed de dados" para repetir as etapas anteriores para especificar feeds adicionais do mesmo serviço ou de um serviço diferente.</span><span class="sxs-lookup"><span data-stu-id="80b34-150">Click "Add another data feed" to repeat the previous steps for specifying additional feeds from the same service or a different service.</span></span>  
  
     <span data-ttu-id="80b34-151">Cada documento de serviço de dados é processado como uma única operação.</span><span class="sxs-lookup"><span data-stu-id="80b34-151">Each data service document is processed as a single operation.</span></span> <span data-ttu-id="80b34-152">Todos os feeds de dados no documento serão gerados de forma assíncrona e retornados a um aplicativo cliente na mesma operação.</span><span class="sxs-lookup"><span data-stu-id="80b34-152">All of the data feeds in the document will be generated asynchronously and returned to a client application in the same operation.</span></span> <span data-ttu-id="80b34-153">Por isso, especifique os pares de tabela-URL apenas para feeds de dados que você deseja usar em conjunto.</span><span class="sxs-lookup"><span data-stu-id="80b34-153">For this reason, only specify the URL-table pairs for data feeds that you want to use together.</span></span>  
  
     <span data-ttu-id="80b34-154">Como os esquemas de autenticação são definidos no nível do documento de serviço de dados, cada feed de dados adicional deve originar-se do serviço ou aplicativo que dê suporte ao mesmo esquema de autenticação do primeiro feed.</span><span class="sxs-lookup"><span data-stu-id="80b34-154">Because authentication schemes are set at the data service document level, each additional data feed must originate from service or application that supports the same authentication scheme as the first feed.</span></span> <span data-ttu-id="80b34-155">Todos os feeds dentro do mesmo documento de serviço de dados serão autenticados pelo mesmo método em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="80b34-155">All feeds within the same data service document will be authenticated under the same method at run time.</span></span>  
  
6.  <span data-ttu-id="80b34-156">Salve o documento.</span><span class="sxs-lookup"><span data-stu-id="80b34-156">Save the document.</span></span> <span data-ttu-id="80b34-157">O documento de serviço de dados é armazenado como um arquivo físico (.atomsvc) em uma biblioteca de conteúdo configurada para esse tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="80b34-157">The data service document is stored as a physical file (.atomsvc) in a content library that is configured for this content type.</span></span>  
  
 <span data-ttu-id="80b34-158">Para usar o documento de serviço de dados, você pode abrir uma pasta de trabalho do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] no [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)] e escolher a opção **Do Feed de Dados** no Assistente de Importação de Dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-158">To use the data service document, you can open an [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbook in the [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)] and choose the **From Data Feed** option in the Import Data wizard.</span></span> <span data-ttu-id="80b34-159">Quando solicitado, um usuário especificará a URL do SharePoint do documento de serviço de dados para iniciar uma operação de importação de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-159">When prompted, a user will specify the SharePoint URL of the data service document to start a data import operation.</span></span> <span data-ttu-id="80b34-160">Para obter mais informações, consulte [usar feeds de dados &#40;PowerPivot para SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="80b34-160">For more information, see [Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span></span>  
  
##  <a name="secure-a-data-service-document"></a><a name="securedsdoc"></a><span data-ttu-id="80b34-161">Proteger um documento de serviço de dados</span><span class="sxs-lookup"><span data-stu-id="80b34-161">Secure a Data Service Document</span></span>  
 <span data-ttu-id="80b34-162">Um documento de serviço de dados herda as permissões da biblioteca que o contém.</span><span class="sxs-lookup"><span data-stu-id="80b34-162">A data service document inherits the permissions of the library that contains it.</span></span> <span data-ttu-id="80b34-163">As permissões definidas no item determinarão se um usuário pode abrir, modificar ou excluir o documento de serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-163">Permissions that you set on the item will determine whether a user can open, modify or delete the data service document.</span></span>  
  
 <span data-ttu-id="80b34-164">Para usar um documento de serviço de dados como uma importação de feed de dados no aplicativo cliente PowerPivot, um usuário precisa apenas de permissões de exibição no documento.</span><span class="sxs-lookup"><span data-stu-id="80b34-164">To use a data service document as a data feed import in the PowerPivot client application, a user only needs view permissions on the document.</span></span> <span data-ttu-id="80b34-165">As permissões de exibição são suficientes para resolver a URL no Assistente de Importação.</span><span class="sxs-lookup"><span data-stu-id="80b34-165">View permissions are sufficient to resolve the URL in the Import Wizard.</span></span>  
  
 <span data-ttu-id="80b34-166">As permissões de exibição em um documento de serviço de dados são verificadas apenas quando uma operação de importação de feed de dados é iniciada.</span><span class="sxs-lookup"><span data-stu-id="80b34-166">View permissions on a data service document are checked only when a data feed import operation begins.</span></span> <span data-ttu-id="80b34-167">Depois da importação, as permissões no documento não são verificadas em uma base contínua. Os feeds que foram adicionados a uma fonte de dados PowerPivot existem como dados estáticos, desconectados do documento de serviço de dados que forneceu as informações de conexão originais.</span><span class="sxs-lookup"><span data-stu-id="80b34-167">Post-import, permissions on the document are not checked on an ongoing basis; feeds that were added to a PowerPivot data source exist as static data, disconnected from the data service document that provided the original connection information.</span></span>  
  
 <span data-ttu-id="80b34-168">De modo semelhante, qualquer operação de atualização de dados agendada subsequentemente também exclui o documento de serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-168">Similarly, any data refresh operations that you subsequently schedule also exclude the data service document.</span></span> <span data-ttu-id="80b34-169">No momento da importação, as informações de conexão de cada feed são copiadas na fonte de dados PowerPivot para fins de atualização.</span><span class="sxs-lookup"><span data-stu-id="80b34-169">At the time of import, connection information for each feed is copied into the PowerPivot data source for refresh purposes.</span></span> <span data-ttu-id="80b34-170">Dessa forma, as permissões em um documento de serviço de dados não são verificadas para atualização de dados, porque o próprio documento nunca é referenciado em uma operação de atualização.</span><span class="sxs-lookup"><span data-stu-id="80b34-170">As such, permissions on a data service document are not checked for data refresh, because the document itself is never referenced in a refresh operation.</span></span>  
  
|<span data-ttu-id="80b34-171">Tarefa</span><span class="sxs-lookup"><span data-stu-id="80b34-171">Task</span></span>|<span data-ttu-id="80b34-172">Requisitos de permissão do SharePoint</span><span class="sxs-lookup"><span data-stu-id="80b34-172">SharePoint permission requirements</span></span>|  
|----------|----------------------------------------|  
|<span data-ttu-id="80b34-173">Importe os feeds de dados para uma pasta de trabalho habilitada para PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="80b34-173">Import data feeds to a PowerPivot-enabled workbook.</span></span>|<span data-ttu-id="80b34-174">Exiba as permissões para o documento de serviço de dados em uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="80b34-174">View permissions to the data service document in a library.</span></span>|  
|<span data-ttu-id="80b34-175">No aplicativo cliente PowerPivot, atualize os dados que foram recuperados anteriormente por meio de um feed.</span><span class="sxs-lookup"><span data-stu-id="80b34-175">In the PowerPivot client application, refresh data that was previously retrieved via a feed.</span></span>|<span data-ttu-id="80b34-176">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="80b34-176">Not applicable.</span></span> <span data-ttu-id="80b34-177">O aplicativo cliente PowerPivot usa informações de conexão HTTP inseridas para conectar-se diretamente aos serviços de dados e aplicativos que fornecem o feed.</span><span class="sxs-lookup"><span data-stu-id="80b34-177">The PowerPivot client application uses embedded HTTP connection information to connect directly to the data services and applications that provide the feed.</span></span> <span data-ttu-id="80b34-178">O aplicativo cliente PowerPivot não usa o documento de serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-178">The PowerPivot client application does not use the data service document.</span></span>|  
|<span data-ttu-id="80b34-179">Em um farm do SharePoint, atualize dados como uma tarefa agendada, sem necessidade de nenhuma entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="80b34-179">In a SharePoint farm, refresh data as a scheduled task, with no user input required.</span></span>|<span data-ttu-id="80b34-180">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="80b34-180">Not applicable.</span></span> <span data-ttu-id="80b34-181">O serviço PowerPivot usa informações de conexão HTTP inseridas para conectar-se diretamente aos serviços de dados e aplicativos que fornecem o feed.</span><span class="sxs-lookup"><span data-stu-id="80b34-181">The PowerPivot service uses embedded HTTP connection information to connect directly to the data services and applications that provide the feed.</span></span> <span data-ttu-id="80b34-182">O serviço PowerPivot não usa o documento de serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-182">The PowerPivot service does not use the data service document.</span></span>|  
|<span data-ttu-id="80b34-183">Excluir um documento de serviço de dados em uma biblioteca</span><span class="sxs-lookup"><span data-stu-id="80b34-183">Delete a data service document in a library</span></span>|<span data-ttu-id="80b34-184">Permissões de colaboração na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="80b34-184">Contribute permissions on the library.</span></span>|  
  
##  <a name="modify-a-data-service-document"></a><a name="modifydsdoc"></a> <span data-ttu-id="80b34-185">Modificar um documento de serviço de dados</span><span class="sxs-lookup"><span data-stu-id="80b34-185">Modify a Data Service Document</span></span>  
 <span data-ttu-id="80b34-186">Você pode adicionar, editar ou remover entradas individuais da tabela de URL em um documento de serviço de dados.</span><span class="sxs-lookup"><span data-stu-id="80b34-186">You can add, edit, or remove individual URL-table entries in a data service document.</span></span> <span data-ttu-id="80b34-187">Depois de salvar suas alterações, os usuários que selecionarem o documento de serviço em uma nova operação de importação obterão os feeds de dados que você especificou.</span><span class="sxs-lookup"><span data-stu-id="80b34-187">After you save your changes, users who select the service document in a new import operation will get the data feeds you specified.</span></span>  
  
 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] <span data-ttu-id="80b34-188">que usavam uma versão anterior do documento não são afetadas por nenhuma alteração que você faça.</span><span class="sxs-lookup"><span data-stu-id="80b34-188">workbooks that used a previous version of the document are unaffected by any changes you make.</span></span> <span data-ttu-id="80b34-189">Isso ocorre porque um documento de serviço de dados é lido apenas uma vez durante a operação de importação inicial.</span><span class="sxs-lookup"><span data-stu-id="80b34-189">This is because a data service document is read only once during the initial import operation.</span></span> <span data-ttu-id="80b34-190">Durante a importação, a URL do serviço e os nomes das tabelas são copiados e armazenados internamente na pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="80b34-190">During the import, service URL and table names are copied and stored internally in the workbook.</span></span> <span data-ttu-id="80b34-191">Esses valores internos são usados em operações de atualização subsequentes para obter dados atualizados.</span><span class="sxs-lookup"><span data-stu-id="80b34-191">These internal values are then used in subsequent refresh operations to get updated data.</span></span>  
  
 <span data-ttu-id="80b34-192">Como não há nenhum link persistente entre um documento de serviço de dados em um site do SharePoint e a pasta de trabalho do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] que contém o feed importado, a modificação de qualquer parte de um documento de serviço de dados não tem nenhum efeito em pastas de trabalho do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] existentes.</span><span class="sxs-lookup"><span data-stu-id="80b34-192">Because there is no persistent link between a data service document on a SharePoint site and the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbook that contains the imported feed, modifying any part of a data service document has no effect on existing [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="80b34-193">Embora o documento de serviço de dados seja lido apenas uma vez, os serviços de dados que fornecem os dados reais podem ser acessados em intervalos regulares para obter feeds mais recentes.</span><span class="sxs-lookup"><span data-stu-id="80b34-193">Although the data service document is read only once, data services that provide the actual data can be accessed at regular intervals to get newer feeds.</span></span> <span data-ttu-id="80b34-194">Para obter mais informações sobre como atualizar dados, consulte [PowerPivot data Refresh](power-pivot-data-refresh.md).</span><span class="sxs-lookup"><span data-stu-id="80b34-194">For more information about how to refresh data, see [PowerPivot Data Refresh](power-pivot-data-refresh.md).</span></span>  
  
##  <a name="next-step-use-a-data-service-document"></a><a name="usedsdoc"></a> <span data-ttu-id="80b34-195">Próxima etapa: Usar um documento de serviço de dados</span><span class="sxs-lookup"><span data-stu-id="80b34-195">Next Step: Use a Data Service Document</span></span>  
 <span data-ttu-id="80b34-196">Para usar um documento de serviço de dados que você criou em uma biblioteca do SharePoint, use a opção **de importação de feeds de dados** em uma fonte de dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="80b34-196">To use a data service document that you created in a SharePoint library, you use the **From Data Feeds** import option in a PowerPivot data source.</span></span> <span data-ttu-id="80b34-197">Para obter instruções, consulte [usar feeds de dados &#40;PowerPivot para SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="80b34-197">For instructions, see [Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b34-198">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="80b34-198">See Also</span></span>  
 [<span data-ttu-id="80b34-199">Feeds de dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="80b34-199">PowerPivot Data Feeds</span></span>](power-pivot-data-feeds.md)  
  
  