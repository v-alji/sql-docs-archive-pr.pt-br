---
title: Tipo de conexão do Oracle (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9db86dd2-beda-42d8-8af7-2629d58a8e3d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e9bf19953c5d2dc2f818eddcacf445e641972d4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573777"
---
# <a name="oracle-connection-type-ssrs"></a><span data-ttu-id="e31ba-102">Tipo de conexão Oracle (SSRS)</span><span class="sxs-lookup"><span data-stu-id="e31ba-102">Oracle Connection Type (SSRS)</span></span>
  <span data-ttu-id="e31ba-103">Para usar dados de um banco de dados Oracle em seu relatório, é necessário ter um conjunto de dados baseado na fonte de dados do relatório do tipo Oracle.</span><span class="sxs-lookup"><span data-stu-id="e31ba-103">To use data from an Oracle database in your report, you must you must have a dataset that is based on a report data source of type Oracle.</span></span> <span data-ttu-id="e31ba-104">Esse tipo interno de fonte de dados é baseado no Provedor Gerenciado do .NET Framework para Oracle e requer um componente de software cliente Oracle.</span><span class="sxs-lookup"><span data-stu-id="e31ba-104">This built-in data source type is based on the .NET Framework Managed Provider for Oracle and requires an Oracle client software component.</span></span>  
  
 <span data-ttu-id="e31ba-105">Use as informações deste tópico para criar uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e31ba-105">Use the information in this topic to build a data source.</span></span> <span data-ttu-id="e31ba-106">Para obter instruções detalhadas, consulte [Adicionar e verificar uma &#40;de conexão de dados ou fonte de dados Construtor de relatórios e SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e31ba-106">For step-by-step instructions, see [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="connection-string"></a><a name="Connection"></a><span data-ttu-id="e31ba-107">Cadeia de conexão</span><span class="sxs-lookup"><span data-stu-id="e31ba-107">Connection String</span></span>  
 <span data-ttu-id="e31ba-108">Contate o administrador do banco de dados para obter informações sobre a conexão e as credenciais que devem ser usadas para se conectar à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e31ba-108">Contact your database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="e31ba-109">O exemplo de cadeia de conexão a seguir especifica um banco de dados Oracle no servidor chamado “Oracle9” com Unicode.</span><span class="sxs-lookup"><span data-stu-id="e31ba-109">The following connection string example specifies an Oracle database on the server named "Oracle9" using Unicode.</span></span> <span data-ttu-id="e31ba-110">O nome do servidor deve coincidir com o que está definido no arquivo de configuração Tnsnames.ora como o nome da instância do servidor Oracle.</span><span class="sxs-lookup"><span data-stu-id="e31ba-110">The server name must match what is defined in the Tnsnames.ora configuration file as the Oracle server instance name.</span></span>  
  
```  
Data Source="Oracle9"; Unicode="True"  
```  
  
 <span data-ttu-id="e31ba-111">Para obter mais informações sobre exemplos de cadeias de conexão, consulte [Conexões de dados, fontes de dados e cadeias de conexão no Construtor de Relatórios](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e31ba-111">For more information about connection string examples, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
##  <a name="credentials"></a><a name="Credentials"></a><span data-ttu-id="e31ba-112">Fornecidas</span><span class="sxs-lookup"><span data-stu-id="e31ba-112">Credentials</span></span>  
 <span data-ttu-id="e31ba-113">As credenciais são necessárias para executar consultas, visualizar o relatório localmente e visualizá-lo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e31ba-113">Credentials are required to run queries, to preview the report locally, and to preview the report from the report server.</span></span>  
  
 <span data-ttu-id="e31ba-114">Após a publicação do relatório, talvez seja necessário alterar as credenciais da fonte de dados para que, quando o relatório for executado no servidor de relatório, as permissões recuperadas sejam válidas.</span><span class="sxs-lookup"><span data-stu-id="e31ba-114">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
 <span data-ttu-id="e31ba-115">Para obter mais informações, consulte [conexões de dados, fontes de dados e cadeias de conexão em Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) ou [especificar credenciais no construtor de relatórios](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e31ba-115">For more information, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) or [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  

  
##  <a name="queries"></a><a name="Query"></a><span data-ttu-id="e31ba-116">Procura</span><span class="sxs-lookup"><span data-stu-id="e31ba-116">Queries</span></span>  
 <span data-ttu-id="e31ba-117">Para criar um conjunto de dados, você pode selecionar um procedimento armazenado na lista suspensa ou criar uma consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="e31ba-117">To create a dataset, you can either select a stored procedure from a drop-down list or create an SQL query.</span></span> <span data-ttu-id="e31ba-118">Para criar uma consulta, use o designer de consulta baseado em texto.</span><span class="sxs-lookup"><span data-stu-id="e31ba-118">To build a query, you must use the text-based query designer.</span></span> <span data-ttu-id="e31ba-119">Para obter mais informações, consulte [Interface do usuário do Designer de Consultas Baseadas em Texto &#40;Construtor de Relatórios&#41;](text-based-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e31ba-119">For more information, see [Text-based Query Designer User Interface &#40;Report Builder&#41;](text-based-query-designer-user-interface-report-builder.md).</span></span>  
  
 <span data-ttu-id="e31ba-120">É possível especificar procedimentos armazenados que retornem apenas um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e31ba-120">You can specify stored procedures that return only one result set.</span></span> <span data-ttu-id="e31ba-121">Não há suporte para o uso de consultas com base no cursor.</span><span class="sxs-lookup"><span data-stu-id="e31ba-121">Using cursor-based queries are not supported.</span></span>  
  
##  <a name="parameters"></a><a name="Parameters"></a> <span data-ttu-id="e31ba-122">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e31ba-122">Parameters</span></span>  
 <span data-ttu-id="e31ba-123">Se a consulta incluir variáveis de consulta, os parâmetros de relatório correspondentes serão gerados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e31ba-123">If the query includes query variables, corresponding report parameters are automatically generated.</span></span> <span data-ttu-id="e31ba-124">Essa extensão dá suporte a parâmetros nomeados.</span><span class="sxs-lookup"><span data-stu-id="e31ba-124">Named parameters are supported by this extension.</span></span> <span data-ttu-id="e31ba-125">Para o Oracle versão 9 ou posterior, há suporte para parâmetros de vários valores.</span><span class="sxs-lookup"><span data-stu-id="e31ba-125">For Oracle version 9 or later, multivalue parameters are supported.</span></span>  
  
 <span data-ttu-id="e31ba-126">Os parâmetros de relatório são criados com valores de propriedade padrão que talvez precisem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="e31ba-126">Report parameters are created with default property values that you might need to modify.</span></span> <span data-ttu-id="e31ba-127">Por exemplo, cada parâmetro de relatório é do tipo de dados **Texto**.</span><span class="sxs-lookup"><span data-stu-id="e31ba-127">For example, each report parameter is data type **Text**.</span></span> <span data-ttu-id="e31ba-128">Depois que os parâmetros de relatório forem criados, talvez seja necessário alterar os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="e31ba-128">After the report parameters are created, you might have to change default values.</span></span> <span data-ttu-id="e31ba-129">Para obter mais informações, consulte [Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="e31ba-129">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  

  
##  <a name="remarks"></a><a name="Remarks"></a> <span data-ttu-id="e31ba-130">Comentários</span><span class="sxs-lookup"><span data-stu-id="e31ba-130">Remarks</span></span>  
 <span data-ttu-id="e31ba-131">Para que você possa se conectar a uma fonte de dados Oracle, o administrador do sistema deve ter instalado a versão do .NET Data Provider for Oracle que dê suporte à recuperação de dados do banco de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="e31ba-131">Before you can connect an Oracle data source, the system administrator must have installed the version of the .NET Data Provider for Oracle that supports retrieving data from the Oracle database.</span></span> <span data-ttu-id="e31ba-132">O provedor de dados deve ser instalado no mesmo computador que o Construtor de Relatórios e também no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e31ba-132">This data provider must be installed on the same computer as Report Builder and also on the report server.</span></span>  
  
 <span data-ttu-id="e31ba-133">Para saber mais, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e31ba-133">For more information, see the following:</span></span>  
  
-   <span data-ttu-id="e31ba-134">[Usando o Provedor de Dados .NET Framework para Oracle](https://go.microsoft.com/fwlink/?LinkId=112314) no msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e31ba-134">[Using the .NET Framework Data Provider for Oracle](https://go.microsoft.com/fwlink/?LinkId=112314) on msdn.microsoft.com</span></span>  
  
-   [<span data-ttu-id="e31ba-135">Como usar o Reporting Services para configurar e acessar uma fonte de dados Oracle</span><span class="sxs-lookup"><span data-stu-id="e31ba-135">How to use Reporting Services to configure and to access an Oracle data source</span></span>](https://support.microsoft.com/kb/834305)  
  
-   [<span data-ttu-id="e31ba-136">Como adicionar permissões à entidade de segurança de NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="e31ba-136">How to add permissions for the NETWORK SERVICE security principal</span></span>](https://support.microsoft.com/kb/870668)  
  
###### <a name="alternate-data-extensions"></a><span data-ttu-id="e31ba-137">Extensões de dados alternativas</span><span class="sxs-lookup"><span data-stu-id="e31ba-137">Alternate Data Extensions</span></span>  
 <span data-ttu-id="e31ba-138">Você também pode recuperar dados de um banco de dados Oracle com o uso de um tipo de fonte de dados OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e31ba-138">You can also retrieve data from an Oracle database by using an OLE DB data source type.</span></span> <span data-ttu-id="e31ba-139">Para obter mais informações, consulte [Tipo de conexão OLE DB &#40;SSRS&#41;](ole-db-connection-type-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e31ba-139">For more information, see [OLE DB Connection Type &#40;SSRS&#41;](ole-db-connection-type-ssrs.md).</span></span>  
  
###### <a name="report-models"></a><span data-ttu-id="e31ba-140">Modelos de relatório</span><span class="sxs-lookup"><span data-stu-id="e31ba-140">Report Models</span></span>  
 <span data-ttu-id="e31ba-141">Também é possível criar modelos com base em um banco de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="e31ba-141">You can also create models based on an Oracle database.</span></span>  
  
###### <a name="platform-and-version-information"></a><span data-ttu-id="e31ba-142">Informações sobre plataforma e versão</span><span class="sxs-lookup"><span data-stu-id="e31ba-142">Platform and Version Information</span></span>  
 <span data-ttu-id="e31ba-143">Para obter mais informações sobre o suporte de plataforma e à versão, consulte [Fontes de dados com suporte no Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) na documentação do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] nos [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Manuais Online](https://go.microsoft.com/fwlink/?linkid=121312) do .</span><span class="sxs-lookup"><span data-stu-id="e31ba-143">For more information about platform and version support, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="e31ba-144">Tópicos de instruções</span><span class="sxs-lookup"><span data-stu-id="e31ba-144">How-To Topics</span></span>  
 <span data-ttu-id="e31ba-145">Esta seção contém instruções passo a passo para trabalhar com conexões de dados, fontes de dados e conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="e31ba-145">This section contains step-by-step instructions for working with data connections, data sources, and datasets.</span></span>  
  
 [<span data-ttu-id="e31ba-146">Adicionar e verificar uma conexão de dados ou uma fonte de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e31ba-146">Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;</span></span>](add-and-verify-a-data-connection-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e31ba-147">Criar um conjunto de dados compartilhado ou um conjunto de dados inserido &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e31ba-147">Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;</span></span>](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e31ba-148">Adicionar um filtro a um conjunto de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e31ba-148">Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;</span></span>](add-a-filter-to-a-dataset-report-builder-and-ssrs.md)  
  
 
  
##  <a name="related-sections"></a><a name="Related"></a><span data-ttu-id="e31ba-149">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="e31ba-149">Related Sections</span></span>  
 <span data-ttu-id="e31ba-150">Estas seções da documentação fornecem informações conceituais detalhadas sobre dados de relatório, bem como informações de procedimentos sobre como definir, personalizar e usar partes de um relatório relacionadas aos dados.</span><span class="sxs-lookup"><span data-stu-id="e31ba-150">These sections of the documentation provide in-depth conceptual information about report data, as well as procedural information about how to define, customize, and use parts of a report that are related to data.</span></span>  
  
 [<span data-ttu-id="e31ba-151">Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e31ba-151">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-datasets-ssrs.md)  
 <span data-ttu-id="e31ba-152">Fornece uma visão geral de como acessar dados de seu relatório.</span><span class="sxs-lookup"><span data-stu-id="e31ba-152">Provides an overview of accessing data for your report.</span></span>  
  
 [<span data-ttu-id="e31ba-153">Conexões de dados, fontes de dados e cadeias de conexão no Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="e31ba-153">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
 <span data-ttu-id="e31ba-154">Fornece informações sobre conexões de dados e fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="e31ba-154">Provides information about data connections and data sources.</span></span>  
  
 [<span data-ttu-id="e31ba-155">Conjuntos de itens de relatório inseridos e conjuntos de &#40;compartilhados Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e31ba-155">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
 <span data-ttu-id="e31ba-156">Fornece informações sobre conjuntos de dados inseridos e compartilhados.</span><span class="sxs-lookup"><span data-stu-id="e31ba-156">Provides information about embedded and shared datasets.</span></span>  
  
 [<span data-ttu-id="e31ba-157">Coleção de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e31ba-157">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](dataset-fields-collection-report-builder-and-ssrs.md)  
 <span data-ttu-id="e31ba-158">Fornece informações sobre a coleção de campos de conjuntos de dados gerada pela consulta.</span><span class="sxs-lookup"><span data-stu-id="e31ba-158">Provides information about the dataset field collection generated by the query.</span></span>  
  
 <span data-ttu-id="e31ba-159">[Fontes de dados com suporte no Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) na documentação do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] nos [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Manuais Online](https://go.microsoft.com/fwlink/?linkid=121312) do .</span><span class="sxs-lookup"><span data-stu-id="e31ba-159">[Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
 <span data-ttu-id="e31ba-160">Fornece informações detalhadas sobre suporte à plataforma e à versão para cada extensão de dados.</span><span class="sxs-lookup"><span data-stu-id="e31ba-160">Provides in-depth information about platform and version support for each data extension.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="e31ba-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e31ba-161">See Also</span></span>  
 <span data-ttu-id="e31ba-162">[Parâmetros de relatório &#40;Construtor de Relatórios e Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="e31ba-162">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="e31ba-163">[Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e31ba-163">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e31ba-164">Expressões &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e31ba-164">Expressions &#40;Report Builder and SSRS&#41;</span></span>](../report-design/expressions-report-builder-and-ssrs.md)  
  
  