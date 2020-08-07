---
title: Tipo de conexão do Teradata (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b02779c2-a6b9-453c-815f-adad53353952
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 73e51c82a824bb607d75c2e78cfc9b0f37476e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576222"
---
# <a name="teradata-connection-type-ssrs"></a><span data-ttu-id="707df-102">Tipo de conexão Teradata (SSRS)</span><span class="sxs-lookup"><span data-stu-id="707df-102">Teradata Connection Type (SSRS)</span></span>
  <span data-ttu-id="707df-103">Para incluir dados de um banco de dados relacional Teradata no seu relatório, é necessário ter um conjunto de dados baseado na fonte de dados do relatório do tipo Teradata.</span><span class="sxs-lookup"><span data-stu-id="707df-103">To include data from a Teradata relational database in your report, you must have a dataset that is based on a report data source of type Teradata.</span></span> <span data-ttu-id="707df-104">Esse tipo de fonte de dados interna é baseado na extensão de processamento de dados do Provedor Gerenciados do .NET para Teradata.</span><span class="sxs-lookup"><span data-stu-id="707df-104">This built-in data source type is based on the .NET Managed Provider for Teradata data processing extension.</span></span>  
  
 <span data-ttu-id="707df-105">Use as informações deste tópico para criar uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="707df-105">Use the information in this topic to build a data source.</span></span> <span data-ttu-id="707df-106">Para obter instruções detalhadas, consulte [Adicionar e verificar uma &#40;de conexão de dados ou fonte de dados Construtor de relatórios e SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="707df-106">For step-by-step instructions, see [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="connection-string"></a><a name="Connection"></a> <span data-ttu-id="707df-107">Cadeia de Conexão</span><span class="sxs-lookup"><span data-stu-id="707df-107">Connection String</span></span>  
 <span data-ttu-id="707df-108">Contate o administrador do banco de dados para obter informações sobre a conexão e as credenciais que devem ser usadas para se conectar à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="707df-108">Contact your database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="707df-109">O exemplo de cadeia de conexão seguinte define um banco de dados Teradata no servidor especificado com um endereço IP:</span><span class="sxs-lookup"><span data-stu-id="707df-109">The following connection string example specifies a Teradata database on the server specified with an IP address:</span></span>  
  
```  
data source=<IP Address>  
```  
  
 <span data-ttu-id="707df-110">Para obter mais exemplos de cadeias de conexão, consulte [Conexões de dados, fontes de dados e cadeias de conexão no Construtor de Relatórios](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="707df-110">For more connection string examples, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
##  <a name="credentials"></a><a name="Credentials"></a> <span data-ttu-id="707df-111">Credenciais</span><span class="sxs-lookup"><span data-stu-id="707df-111">Credentials</span></span>  
 <span data-ttu-id="707df-112">As credenciais são necessárias para executar consultas, visualizar o relatório localmente e visualizá-lo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="707df-112">Credentials are required to run queries, to preview the report locally, and to preview the report from the report server.</span></span>  
  
 <span data-ttu-id="707df-113">Após a publicação do relatório, talvez seja necessário alterar as credenciais da fonte de dados para que, quando o relatório for executado no servidor de relatório, as permissões recuperadas sejam válidas.</span><span class="sxs-lookup"><span data-stu-id="707df-113">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
 <span data-ttu-id="707df-114">Para obter mais informações, consulte [conexões de dados, fontes de dados e cadeias de conexão em Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) ou [especificar credenciais no construtor de relatórios](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="707df-114">For more information, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) or [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  

##  <a name="remarks"></a><a name="Remarks"></a> <span data-ttu-id="707df-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="707df-115">Remarks</span></span>  
 <span data-ttu-id="707df-116">Para que você possa se conectar a uma fonte de dados Teradata, o administrador do sistema deve ter instalado a versão do Provedor de Dados .NET para Teradata que dá suporte à recuperação de dados do banco de dados Teradata.</span><span class="sxs-lookup"><span data-stu-id="707df-116">Before you can connect a Teradata data source, the system administrator must have installed the version of the .NET Data Provider for Teradata that supports retrieving data from the Teradata database.</span></span> <span data-ttu-id="707df-117">O provedor de dados deve ser instalado no mesmo computador que o Construtor de Relatórios e também no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="707df-117">This data provider must be installed on the same computer as Report Builder and also on the report server.</span></span>  
  
 <span data-ttu-id="707df-118">Nem todos os modos de entrega de relatório são suportados por esse provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="707df-118">Not all report delivery modes are supported by this data provider.</span></span> <span data-ttu-id="707df-119">Não há suporte para a entrega de relatórios através de assinaturas controladas por dados para essa extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="707df-119">Delivering reports through data-driven subscriptions is not supported for this data processing extension.</span></span> <span data-ttu-id="707df-120">Para obter mais informações, consulte [Usar uma fonte de dados externa para obter dados de assinante &#40;Assinatura controlada por dados&#41;](../subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md) na documentação do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] nos [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Manuais Online](https://go.microsoft.com/fwlink/?linkid=121312) do .</span><span class="sxs-lookup"><span data-stu-id="707df-120">For more information, see [Use an External Data Source for Subscriber Data &#40;Data-Driven Subscription&#41;](../subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  

##  <a name="report-models"></a><a name="Models"></a> <span data-ttu-id="707df-121">Modelos de relatório</span><span class="sxs-lookup"><span data-stu-id="707df-121">Report Models</span></span>  
 <span data-ttu-id="707df-122">Para criar um conjunto de dados de um modelo de relatório baseado em uma fonte de dados Teradata, o modelo deve ser criado no Designer de Modelos em [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e deve ser publicado em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="707df-122">To create a dataset from a report model that is based on a Teradata data source, the model must be designed in Model Designer in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and published on a report server.</span></span>  

##  <a name="related-sections"></a><a name="Related"></a> <span data-ttu-id="707df-123">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="707df-123">Related Sections</span></span>  
 <span data-ttu-id="707df-124">Estas seções da documentação fornecem informações conceituais detalhadas sobre dados de relatório, bem como informações de procedimentos sobre como definir, personalizar e usar partes de um relatório relacionadas aos dados.</span><span class="sxs-lookup"><span data-stu-id="707df-124">These sections of the documentation provide in-depth conceptual information about report data, as well as procedural information about how to define, customize, and use parts of a report that are related to data.</span></span>  
  
 [<span data-ttu-id="707df-125">Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="707df-125">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-datasets-ssrs.md)  
 <span data-ttu-id="707df-126">Fornece uma visão geral de como acessar dados de seu relatório.</span><span class="sxs-lookup"><span data-stu-id="707df-126">Provides an overview of accessing data for your report.</span></span>  
  
 [<span data-ttu-id="707df-127">Conexões de dados, fontes de dados e cadeias de conexão no Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="707df-127">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
 <span data-ttu-id="707df-128">Fornece informações sobre conexões de dados e fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="707df-128">Provides information about data connections and data sources.</span></span>  
  
 [<span data-ttu-id="707df-129">Conjuntos de dados inseridos e compartilhados de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="707df-129">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
 <span data-ttu-id="707df-130">Fornece informações sobre conjuntos de dados inseridos e compartilhados.</span><span class="sxs-lookup"><span data-stu-id="707df-130">Provides information about embedded and shared datasets.</span></span>  
  
 [<span data-ttu-id="707df-131">Coleção de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="707df-131">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](dataset-fields-collection-report-builder-and-ssrs.md)  
 <span data-ttu-id="707df-132">Fornece informações sobre a coleção de campos gerada pela consulta do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="707df-132">Provides information about the field collection that is generated by the dataset query.</span></span>  
  
 <span data-ttu-id="707df-133">[Fontes de dados com suporte no Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) na documentação do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] nos [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Manuais Online](https://go.microsoft.com/fwlink/?linkid=121312) do .</span><span class="sxs-lookup"><span data-stu-id="707df-133">[Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
 <span data-ttu-id="707df-134">Fornece informações detalhadas sobre suporte à plataforma e à versão para cada extensão de dados.</span><span class="sxs-lookup"><span data-stu-id="707df-134">Provides in-depth information about platform and version support for each data extension.</span></span>  
  
 [<span data-ttu-id="707df-135">Usando o SQL Server 2008 Reporting Services com o Provedor de Dados do .NET Framework para Teradata</span><span class="sxs-lookup"><span data-stu-id="707df-135">Using SQL Server 2008 Reporting Services with the .NET Framework Data Provider for Teradata</span></span>](https://go.microsoft.com/fwlink/?LinkID=130848)  
 <span data-ttu-id="707df-136">Fornece informações detalhadas sobre como trabalhar com esta extensão de dados.</span><span class="sxs-lookup"><span data-stu-id="707df-136">Provides detailed information about working with this data extension.</span></span>  

## <a name="see-also"></a><span data-ttu-id="707df-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="707df-137">See Also</span></span>  
 <span data-ttu-id="707df-138">[Parâmetros de relatório &#40;Construtor de Relatórios e Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="707df-138">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="707df-139">[Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="707df-139">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="707df-140">Expressões &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="707df-140">Expressions &#40;Report Builder and SSRS&#41;</span></span>](../report-design/expressions-report-builder-and-ssrs.md)  