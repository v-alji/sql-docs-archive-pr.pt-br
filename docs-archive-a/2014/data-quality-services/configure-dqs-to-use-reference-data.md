---
title: Configurar o DQS para usar dados de referência | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.rds.f1
- sql12.dqs.administration.rdsconfiguration.f1
- sql12.dqs.administration.configuration.createDirectRDS.f1
ms.assetid: fae745e7-57a7-4cbc-8979-56ea8e392e4e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 670e984c2afabb70dece75d94701d7a3a03c95bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678982"
---
# <a name="configure-dqs-to-use-reference-data"></a><span data-ttu-id="a4b52-102">Configurar DQS para usar dados de referência</span><span class="sxs-lookup"><span data-stu-id="a4b52-102">Configure DQS to Use Reference Data</span></span>
  <span data-ttu-id="a4b52-103">Este tópico descreve como configurar o [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) para usar dados de referência para limpar seus dados.</span><span class="sxs-lookup"><span data-stu-id="a4b52-103">This topic describes how to configure [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) to use reference data for cleansing your data.</span></span> <span data-ttu-id="a4b52-104">Você pode usar dados de referência do Azure Marketplace ou de provedores de dados de referência terceirizados online diretos.</span><span class="sxs-lookup"><span data-stu-id="a4b52-104">You could either use reference data from Azure Marketplace or from direct online third-party reference data providers.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="a4b52-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a4b52-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a4b52-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a4b52-106">Prerequisites</span></span>  
 <span data-ttu-id="a4b52-107">Para usar dados de referência do Marketplace, você deve ter uma chave de conta válida no Marketplace.</span><span class="sxs-lookup"><span data-stu-id="a4b52-107">To use reference data from Marketplace, you must have a valid Marketplace account key.</span></span> <span data-ttu-id="a4b52-108">Para obter informações detalhadas sobre como criar uma chave de conta do Marketplace, consulte [criar sua conta](https://go.microsoft.com/fwlink/?LinkId=212936) ( https://go.microsoft.com/fwlink/?LinkId=212936) .</span><span class="sxs-lookup"><span data-stu-id="a4b52-108">For detailed information about creating a Marketplace account key, see [Create Your Account](https://go.microsoft.com/fwlink/?LinkId=212936) (https://go.microsoft.com/fwlink/?LinkId=212936).</span></span> <span data-ttu-id="a4b52-109">Você também pode criar uma chave de conta do Marketplace no [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] clicando em **Configuração** sob **Administração** na tela de início do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] e depois clicando em **Criar uma ID de Conta do DataMarket** na guia **Dados de Referência** .</span><span class="sxs-lookup"><span data-stu-id="a4b52-109">You can also create a Marketplace account key from within [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] by clicking **Configuration** under **Administration** in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, and then clicking **Create a DataMarket Account ID** under the **Reference Data** tab.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a4b52-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="a4b52-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a4b52-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="a4b52-111">Permissions</span></span>  
 <span data-ttu-id="a4b52-112">Você deve ter a função dqs_administrator no banco de dados DQS_MAIN para definir configurações de serviço de dados de referência no DQS.</span><span class="sxs-lookup"><span data-stu-id="a4b52-112">You must have the dqs_administrator role on the DQS_MAIN database to configure reference data service settings in DQS.</span></span>  
  
##  <a name="configure-dqs-to-use-reference-data-from-marketplace"></a><a name="Marketplace"></a> <span data-ttu-id="a4b52-113">Configurar o DQS para usar dados de referência do Marketplace</span><span class="sxs-lookup"><span data-stu-id="a4b52-113">Configure DQS to Use Reference Data from Marketplace</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="a4b52-114">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="a4b52-114">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="a4b52-115">Na tela de início do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , sob **Administração**, clique em **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="a4b52-115">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, under **Administration**, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="a4b52-116">Na guia **Dados de Referência** , sob a área **Configurações de Rede** , digite os valores apropriados nas caixas **Servidor Proxy** e **Porta** se você ou sua organização usar o servidor proxy para conectar à Internet.</span><span class="sxs-lookup"><span data-stu-id="a4b52-116">In the **Reference Data** tab, under the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** boxes if you or your organization uses proxy server to connect to the Internet.</span></span>  
  
4.  <span data-ttu-id="a4b52-117">Especifique a chave de conta do Marketplace na caixa **ID da Contas do DataMarket** e clique no ícone **Validar ID da Conta do DataMarket** para validar a chave de conta.</span><span class="sxs-lookup"><span data-stu-id="a4b52-117">Specify the Marketplace account key in the **DataMarket Account ID** box, and click the **Validate DataMarket Account ID** icon to validate the account key.</span></span> <span data-ttu-id="a4b52-118">Será exibida uma mensagem para mostrar se a chave de conta do Marketplace é válida.</span><span class="sxs-lookup"><span data-stu-id="a4b52-118">A message appears to display whether the specified Marketplace account key is valid.</span></span>  
  
 <span data-ttu-id="a4b52-119">Agora você está pronto para usar os serviços de dados de referência do Marketplace no DQS assinados para a chave de conta do Marketplace especificada.</span><span class="sxs-lookup"><span data-stu-id="a4b52-119">You are now ready to use the reference data services from Marketplace in DQS that are subscribed for the specified Marketplace account key.</span></span>  
  
##  <a name="configure-dqs-to-use-reference-data-from-direct-online-third-party-reference-data-providers"></a><a name="ThirdParty"></a> <span data-ttu-id="a4b52-120">Configurar o DQS para usar dados de referência de provedores de dados de referência terceirizados online diretos</span><span class="sxs-lookup"><span data-stu-id="a4b52-120">Configure DQS to Use Reference Data from Direct Online Third-Party Reference Data Providers</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="a4b52-121">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="a4b52-121">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="a4b52-122">Na tela de início do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , sob **Administração**, clique em **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="a4b52-122">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, under **Administration**, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="a4b52-123">Na guia **Dados de Referência** , sob a área **Configurações de Rede** , digite os valores apropriados nas caixas **Servidor Proxy** e **Porta** se você ou sua organização usar o servidor proxy para conectar à Internet.</span><span class="sxs-lookup"><span data-stu-id="a4b52-123">In the **Reference Data** tab, under the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** boxes if you or your organization uses proxy server to connect to the Internet.</span></span>  
  
4.  <span data-ttu-id="a4b52-124">Na área **Configurações do Serviço de Dados de Referência Terceirizado Online Direto** , clique no ícone **Adicionar novo provedor de serviço de dados de referência** .</span><span class="sxs-lookup"><span data-stu-id="a4b52-124">In the **Direct Online 3rd Party Reference Data Service Settings** area, click the **Add new reference data service provider** icon.</span></span>  
  
5.  <span data-ttu-id="a4b52-125">Na caixa de diálogo **Criar Novo Provedor de Serviço de Dados de Referência Terceirizado Online Direto** , especifique os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="a4b52-125">In the **Create New Direct Online 3rd Party Reference Data Service Provider** dialog box, specify the following details:</span></span>  
  
    1.  <span data-ttu-id="a4b52-126">Na caixa **Nome** , digite um nome para o novo provedor de serviço de dados de referência direto.</span><span class="sxs-lookup"><span data-stu-id="a4b52-126">In the **Name** box, type a name of the new direct reference data service provider.</span></span>  
  
    2.  <span data-ttu-id="a4b52-127">(Opcional) Na caixa **Descrição** , digite uma descrição para o novo provedor de serviço de dados de referência direto.</span><span class="sxs-lookup"><span data-stu-id="a4b52-127">(Optional) In the **Description** box, type a description of the new direct reference data service provider.</span></span>  
  
    3.  <span data-ttu-id="a4b52-128">Na caixa **Categoria** , digite a categoria dos dados fornecidos pelo novo provedor de serviço de dados de referência direto.</span><span class="sxs-lookup"><span data-stu-id="a4b52-128">In the **Category** box, type the category of the data provided by the new direct reference data service provider.</span></span>  
  
    4.  <span data-ttu-id="a4b52-129">Na caixa Esquema, especifique o esquema que define a cadeia de caracteres de campos (nomes de coluna) a ser usada do provedor de serviço de dados de referência direto.</span><span class="sxs-lookup"><span data-stu-id="a4b52-129">In the Schema box, specify the schema that defines the string of fields (column names) to be used from the direct reference data service provider.</span></span> <span data-ttu-id="a4b52-130">Um nome de campo não deve conter um espaço e os campos devem ser separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="a4b52-130">A field name should not contain a space, and the fields should be separated by commas.</span></span> <span data-ttu-id="a4b52-131">Por exemplo: `FirstName, LastName, City, State`.</span><span class="sxs-lookup"><span data-stu-id="a4b52-131">For example: `FirstName, LastName, City, State`.</span></span>  
  
    5.  <span data-ttu-id="a4b52-132">Na caixa **URI** , digite a URI do provedor de serviço de dados de referência direto.</span><span class="sxs-lookup"><span data-stu-id="a4b52-132">In the **URI** box, type the URI of the direct reference data service provider.</span></span> <span data-ttu-id="a4b52-133">Apenas URIs seguros (endereço que inicia com "https://") são permitidos no DQS.</span><span class="sxs-lookup"><span data-stu-id="a4b52-133">Only secure URIs (address starting with "https://") are allowed in DQS.</span></span>  
  
    6.  <span data-ttu-id="a4b52-134">Na caixa **Tamanho Máximo do Lote** , digite o número máximo de registros por lote que serão enviados ao provedor de serviço de dados de referência para limpeza.</span><span class="sxs-lookup"><span data-stu-id="a4b52-134">In the **Max Batch Size** box, type the maximum number of records per batch that will be sent to the reference data service provider for cleansing.</span></span> <span data-ttu-id="a4b52-135">Um máximo de 100 registros por lote pode ser especificado para a atividade de limpeza.</span><span class="sxs-lookup"><span data-stu-id="a4b52-135">A maximum of 100 records per batch can be specified for the cleansing activity.</span></span>  
  
    7.  <span data-ttu-id="a4b52-136">Na caixa **ID da Conta** , digite a identificação da conta do assinante no provedor de serviço de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="a4b52-136">In the **Account ID** box, type the account ID of the subscriber with the reference data service provider.</span></span>  
  
6.  <span data-ttu-id="a4b52-137">Clique em **OK** para salvar os dados e feche a caixa de diálogo **Criar Novo Provedor de Serviço de Dados de Referência Terceirizado Online Direto** .</span><span class="sxs-lookup"><span data-stu-id="a4b52-137">Click **OK** to save the data, and close the **Create New Direct Online 3rd Party Reference Data Service Provider** dialog box.</span></span> <span data-ttu-id="a4b52-138">O provedor de dados de referência terceirizado online direto recém-adicionado ficará disponível na **Grade de Provedores de Serviço de Dados de Referência Diretos** no DQS.</span><span class="sxs-lookup"><span data-stu-id="a4b52-138">The newly added direct online third party reference data provider becomes available in the **Direct Reference Data Service Providers Grid** in DQS.</span></span>  
  
 <span data-ttu-id="a4b52-139">Agora você está pronto para usar os serviços de dados de referência do provedor de serviço de dados de referência terceirizado online direto recém-configurado no DQS.</span><span class="sxs-lookup"><span data-stu-id="a4b52-139">You are now ready to use the reference data services from the newly configured direct online third-party reference data service provider in DQS.</span></span>  
  
##  <a name="follow-up-after-configuring-dqs-to-use-reference-data"></a><a name="FollowUp"></a><span data-ttu-id="a4b52-140">Acompanhamento: depois de configurar o DQS para usar dados de referência</span><span class="sxs-lookup"><span data-stu-id="a4b52-140">Follow Up: After Configuring DQS to use Reference Data</span></span>  
 <span data-ttu-id="a4b52-141">Agora você deve mapear os domínios da base de conhecimento necessários para os dados de referência disponíveis nos provedores de dados que acabou de configurar.</span><span class="sxs-lookup"><span data-stu-id="a4b52-141">You must now map the required knowledge base domains to the reference data available from the data providers you just configured.</span></span> <span data-ttu-id="a4b52-142">Para fazer isso, consulte [anexar um domínio ou domínio de composição aos dados de referência](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span><span class="sxs-lookup"><span data-stu-id="a4b52-142">To do so, see [Attach a Domain or Composite Domain to Reference Data](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span></span>  
  
  
