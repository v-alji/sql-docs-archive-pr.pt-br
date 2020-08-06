---
title: Registrar um provedor de dados .NET Framework padrão (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], data
- .NET Framework data providers for Reporting Services
- data processing extensions [Reporting Services]
- data providers [Reporting Services]
- data retrieval [Reporting Services]
- Reporting Services, data sources
ms.assetid: d92add64-e93c-4598-8508-55d1bc46acf6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5fd26f9c7fa163d9e6005d42e24c7b1483987f3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679162"
---
# <a name="register-a-standard-net-framework-data-provider-ssrs"></a><span data-ttu-id="4cecd-102">Registrar um provedor de dados padrão do .NET Framework (SSRS)</span><span class="sxs-lookup"><span data-stu-id="4cecd-102">Register a Standard .NET Framework Data Provider (SSRS)</span></span>
  <span data-ttu-id="4cecd-103">Para usar um provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] terceirizado com o objetivo de recuperar dados para um conjunto de relatórios do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , é preciso implantar e registrar o assembly do provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] em dois locais: no cliente que está criando o relatório e no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4cecd-103">To use a third-party [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider to retrieve data for a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report dataset, you need to deploy and register the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly in two locations: on the report authoring client and on the report server.</span></span> <span data-ttu-id="4cecd-104">No cliente que está criando o relatório, você deve registrar o provedor de dados como um tipo de fonte de dados e associá-lo a um designer de consulta.</span><span class="sxs-lookup"><span data-stu-id="4cecd-104">On the report authoring client, you must register the data provider as a data source type and associate it with a query designer.</span></span> <span data-ttu-id="4cecd-105">Você pode selecionar esse provedor de dados como um tipo de fonte de dados quando criar um conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="4cecd-105">You can then select this data provider as a type of data source when you create a report dataset.</span></span> <span data-ttu-id="4cecd-106">O designer de consulta associado é aberto para ajudá-lo a criar consultas para esse tipo de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-106">The associated query designer opens to help you create queries for this data source type.</span></span> <span data-ttu-id="4cecd-107">No servidor de relatório, é preciso registrar o provedor de dados como um tipo de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-107">On the report server, you must register the data provider as a data source type.</span></span> <span data-ttu-id="4cecd-108">Você pode processar os relatórios publicados que recuperam dados a partir de uma fonte de dados usando este provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-108">You can then process published reports that retrieve data from a data source using this data provider.</span></span>  
  
 <span data-ttu-id="4cecd-109">Os provedores de dados de terceiros não fornecem necessariamente todas as funções disponíveis nas extensões de processamento de dados do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cecd-109">Third-party data providers do not necessarily provide all the functionality available with the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] data processing extensions.</span></span> <span data-ttu-id="4cecd-110">Para obter mais informações, consulte [Fontes de dados com suporte no Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span><span class="sxs-lookup"><span data-stu-id="4cecd-110">For more information, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span></span> <span data-ttu-id="4cecd-111">Para saber como estender a funcionalidade de um provedor de dados do .[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cecd-111">To learn about extending the functionality of a .[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]</span></span> <span data-ttu-id="4cecd-112">provedor de dados do , confira [Implementando uma extensão de processamento de dados](../extensions/data-processing/implementing-a-data-processing-extension.md).</span><span class="sxs-lookup"><span data-stu-id="4cecd-112">data provider, see [Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md).</span></span>  
  
 <span data-ttu-id="4cecd-113">Você precisa ter credenciais de administrador para instalar e registrar provedores de dados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-113">You need administrator credentials to install and register data providers.</span></span>  
  
## <a name="registering-a-net-framework-data-provider-on-the-report-server"></a><span data-ttu-id="4cecd-114">Registrando um provedor de dados .NET Framework no Servidor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="4cecd-114">Registering a .NET Framework Data Provider on the Report Server</span></span>  
 <span data-ttu-id="4cecd-115">Para processar os relatórios publicados que usam esse provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] no servidor de relatórios, é preciso instalar o assembly no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="4cecd-115">In order to process published reports that use this [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider on the report server, you need to install the assembly on the report server.</span></span> <span data-ttu-id="4cecd-116">Modifique dois arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="4cecd-116">You must modify two configuration files.</span></span> <span data-ttu-id="4cecd-117">Modifique rsreportserver.config para registrar o provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-117">Modify rsreportserver.config to register the data provider.</span></span> <span data-ttu-id="4cecd-118">Modifique rssrvpolicy.config para conceder permissões de segurança de acesso do código para o assembly.</span><span class="sxs-lookup"><span data-stu-id="4cecd-118">Modify rssrvpolicy.config to grant code access security permissions for the assembly.</span></span>  
  
#### <a name="to-install-a-data-provider-assembly-on-the-report-server"></a><span data-ttu-id="4cecd-119">Para instalar um assembly do provedor de dados no servidor de relatórios</span><span class="sxs-lookup"><span data-stu-id="4cecd-119">To install a data provider assembly on the report server</span></span>  
  
1.  <span data-ttu-id="4cecd-120">Navegue até o local padrão do diretório \bin no servidor de relatórios no qual deseja usar o provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cecd-120">Navigate to the default location of the bin directory on the report server on which you want to use the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="4cecd-121">O local padrão do diretório bin do servidor de relatório é *\<drive>* : \Program Files\Microsoft SQL Server \ MSRS10_50. MSSQLSERVER\Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="4cecd-121">The default location of the report server bin directory is *\<drive>*:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin.</span></span>  
  
2.  <span data-ttu-id="4cecd-122">Copie o assembly de seu local de preparação para o diretório \bin do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="4cecd-122">Copy your assembly from your staging location to the bin directory of the report server.</span></span> <span data-ttu-id="4cecd-123">Como alternativa, você pode carregar seu assembly no cache de assembly global (GAC).</span><span class="sxs-lookup"><span data-stu-id="4cecd-123">Alternatively, you can load your assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="4cecd-124">Para obter mais informações, consulte [Trabalhando com assemblies e cache de assembly global](https://go.microsoft.com/fwlink/?linkid=63912) na documentação do SDK do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] no MSDN.</span><span class="sxs-lookup"><span data-stu-id="4cecd-124">For more information, see [Working with Assemblies and the Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation on MSDN.</span></span>  
  
#### <a name="to-register-a-net-data-provider-on-the-report-server"></a><span data-ttu-id="4cecd-125">Para registrar um provedor de dados .NET Framework no servidor de relatórios</span><span class="sxs-lookup"><span data-stu-id="4cecd-125">To register a .NET data provider on the report server</span></span>  
  
1.  <span data-ttu-id="4cecd-126">Crie um backup do arquivo RSReportServer.config no diretório pai ReportServer do \bin.</span><span class="sxs-lookup"><span data-stu-id="4cecd-126">Make a backup of the RSReportServer.config file in the ReportServer parent directory for bin.</span></span>  
  
2.  <span data-ttu-id="4cecd-127">Abra o RSReportServer.config. Você pode abrir o arquivo de configuração com o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ou um editor de texto simples, como o Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="4cecd-127">Open RSReportServer.config. You can open the configuration file with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="4cecd-128">Localize o elemento `Data` no arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="4cecd-128">Locate the `Data` element in the RSReportServer.config file.</span></span> <span data-ttu-id="4cecd-129">Uma entrada para o provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] deve ser criada no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="4cecd-129">An entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Extension Your data provider configuration information goes here />  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="4cecd-130">Adicione uma entrada para o provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cecd-130">Add an entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span>  
  
    |<span data-ttu-id="4cecd-131">Atributo</span><span class="sxs-lookup"><span data-stu-id="4cecd-131">Attribute</span></span>|<span data-ttu-id="4cecd-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="4cecd-132">Description</span></span>|  
    |---------------|-----------------|  
    |`Name`|<span data-ttu-id="4cecd-133">Forneça um nome exclusivo para o provedor de dados, como, por exemplo, **MeuProvedorDadosNET**.</span><span class="sxs-lookup"><span data-stu-id="4cecd-133">Provide a unique name for the data provider, for example, **MyNETDataProvider**.</span></span> <span data-ttu-id="4cecd-134">O comprimento máximo do atributo `Name` é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="4cecd-134">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="4cecd-135">O nome deve ser exclusivo entre todas as entradas dento do elemento `Extension` de um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="4cecd-135">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="4cecd-136">O valor incluído aqui será exibido na lista suspensa dos tipos de fonte de dados quando você criar uma nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-136">The value you include here appears in the drop-down list of data source types when you create a new data source.</span></span>|  
    |`Type`|<span data-ttu-id="4cecd-137">Insira uma lista separada por vírgulas que inclua o namespace totalmente qualificado da classe que implementa a interface <xref:System.Data.IDbConnection> , seguida pelo nome do assembly do provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] (sem incluir a extensão de nome de arquivo .dll).</span><span class="sxs-lookup"><span data-stu-id="4cecd-137">Enter a comma-separated list that includes the fully qualified namespace of the class that implements the <xref:System.Data.IDbConnection> interface, followed by the name of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly (not including the .dll file name extension).</span></span>|  
  
     <span data-ttu-id="4cecd-138">Por exemplo, a entrada deve ser semelhante à seguinte para uma DLL implantada no servidor de relatórios do diretório \bin:</span><span class="sxs-lookup"><span data-stu-id="4cecd-138">For example, the entry might resemble the following for a DLL deployed to the report server bin directory:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly" />   
    ```  
  
     <span data-ttu-id="4cecd-139">Se você carregar seu assembly no cache de assembly global (GAC), poderá fornecer as propriedades de nome forte.</span><span class="sxs-lookup"><span data-stu-id="4cecd-139">If you load your assembly into the global assembly cache (GAC), you must provide the strong name properties.</span></span> <span data-ttu-id="4cecd-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4cecd-140">For example:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly,Version=1.0.0.0, Culture=neutral, PublicKeyToken=MyPublicToken"/>  
    ```  
  
#### <a name="to-set-the-code-group-policy-for-a-net-data-provider"></a><span data-ttu-id="4cecd-141">Para definir a política do grupo de códigos para um provedor de dados .NET</span><span class="sxs-lookup"><span data-stu-id="4cecd-141">To set the code group policy for a .NET data provider</span></span>  
  
1.  <span data-ttu-id="4cecd-142">Faça uma cópia de backup do arquivo rssrvpolicy.config no diretório pai ReportServer do \bin.</span><span class="sxs-lookup"><span data-stu-id="4cecd-142">Make a backup copy of the rssrvpolicy.config file in the ReportServer parent directory for bin.</span></span>  
  
2.  <span data-ttu-id="4cecd-143">Abra rssrvpolicy.config. Você pode abrir o arquivo de configuração com o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ou um editor de texto simples, como o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="4cecd-143">Open rssrvpolicy.config. You can open the configuration file with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor such as Notepad.</span></span>  
  
3.  <span data-ttu-id="4cecd-144">Localize o elemento `CodeGroup` no arquivo rssrvpolicy.config.</span><span class="sxs-lookup"><span data-stu-id="4cecd-144">Locate the `CodeGroup` element in the rssrvpolicy.config file.</span></span>  
  
4.  <span data-ttu-id="4cecd-145">Adicione um grupo de códigos para o assembly do provedor de dados que conceda permissão `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="4cecd-145">Add a code group for the data provider assembly that grants `FullTrust` permission.</span></span> <span data-ttu-id="4cecd-146">O grupo de códigos deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="4cecd-146">Your code group might resemble the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="ThisDataProviderCodeGroup"  
       Description="Code group for the .NET data provider">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url=  
    "C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\DataProviderAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="4cecd-147">A associação da URL é apenas uma das condições de associação que você pode selecionar para o provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-147">URL membership is only one of many membership conditions you might select for the data provider.</span></span>  
  
### <a name="verifying-the-deployment-and-registration"></a><span data-ttu-id="4cecd-148">Verificando a implantação e o registro</span><span class="sxs-lookup"><span data-stu-id="4cecd-148">Verifying the Deployment and Registration</span></span>  
 <span data-ttu-id="4cecd-149">Você pode verificar se o provedor de dados foi implantado com sucesso no servidor de relatórios abrindo o Gerenciador de Relatórios e verificando se o provedor de dados está incluído na lista de fontes de dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4cecd-149">You can verify whether the data provider was deployed successfully to the report server by opening Report Manager and verifying that the data provider is included in the list of available data sources.</span></span> <span data-ttu-id="4cecd-150">Para obter mais informações sobre o Gerenciador de Relatórios e fontes de dados, consulte [Criar, modificar e excluir fontes de dados compartilhadas &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4cecd-150">For more information about Report Manager and data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
## <a name="registering-a-net-framework-data-provider-on-the-report-designer-client"></a><span data-ttu-id="4cecd-151">Registrando um provedor de dados .NET Framework no Cliente do Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="4cecd-151">Registering a .NET Framework Data Provider on the Report Designer Client</span></span>  
 <span data-ttu-id="4cecd-152">Para criar relatórios que usam esse provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] em uma fonte de dados, é preciso instalar o assembly no computador cliente que estiver executando o Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="4cecd-152">In order to author reports that use this [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider for a data source, you must install the assembly on your client computer that runs Report Designer.</span></span> <span data-ttu-id="4cecd-153">Modifique dois arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="4cecd-153">You must modify two configuration files.</span></span> <span data-ttu-id="4cecd-154">Modifique o arquivo RSReportDesigner.config para registrar o provedor de dados como uma fonte de dados e para usar o designer de consulta genérico.</span><span class="sxs-lookup"><span data-stu-id="4cecd-154">Modify RSReportDesigner.config to register the data provider as a data source and to use the generic query designer.</span></span> <span data-ttu-id="4cecd-155">Modifique RSPreviewPolicy.config para conceder permissões de segurança de acesso do código para o assembly do provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-155">Modify RSPreviewPolicy.config to grant code access security permissions for the data provider assembly.</span></span>  
  
#### <a name="to-install-a-data-provider-assembly-on-the-report-designer-client"></a><span data-ttu-id="4cecd-156">Para instalar um assembly do provedor de dados no cliente do Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="4cecd-156">To install a data provider assembly on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="4cecd-157">Navegue até o local padrão do diretório PrivateAssemblies no cliente do Designer de Relatórios no qual deseja usar o provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cecd-157">Navigate to the default location of the PrivateAssemblies directory on the Report Designer client on which you want to use the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="4cecd-158">O local padrão do diretório PrivateAssemblies é *\<drive>* : \Program Files\Microsoft Visual Studio 9.0 \ Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="4cecd-158">The default location of the PrivateAssemblies directory is *\<drive>*:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span>  
  
2.  <span data-ttu-id="4cecd-159">Copie o assembly de seu local de preparação para o diretório PrivateAssemblies do cliente do Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="4cecd-159">Copy your assembly from your staging location to the PrivateAssemblies directory of the Report Designer client.</span></span> <span data-ttu-id="4cecd-160">Como alternativa, você pode carregar seu assembly no cache de assembly global (GAC).</span><span class="sxs-lookup"><span data-stu-id="4cecd-160">Alternatively, you can load your assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="4cecd-161">Para obter mais informações, consulte [Trabalhando com assemblies e cache de assembly global](https://go.microsoft.com/fwlink/?linkid=63912) na documentação do SDK do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] no MSDN.</span><span class="sxs-lookup"><span data-stu-id="4cecd-161">For more information, see [Working with Assemblies and the Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation on MSDN.</span></span>  
  
#### <a name="to-register-a-net-data-provider-on-the-report-designer-client"></a><span data-ttu-id="4cecd-162">Para registrar um provedor de dados .NET no cliente do Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="4cecd-162">To register a .NET data provider on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="4cecd-163">Faça uma cópia de backup do arquivo RSReportDesigner.config no diretório PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="4cecd-163">Make a backup copy of the RSReportDesigner.config file in the PrivateAssemblies directory.</span></span>  
  
2.  <span data-ttu-id="4cecd-164">Abra o arquivo RSReportDesigner.config com o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ou um editor de texto simples, como o Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="4cecd-164">Open RSReportDesigner.config with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor such as Notepad.</span></span>  
  
3.  <span data-ttu-id="4cecd-165">Localize o elemento `Data` no arquivo RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="4cecd-165">Locate the `Data` element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="4cecd-166">Uma entrada para o provedor de dados deve ser criada no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="4cecd-166">An entry for the data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Extension Your data provider configuration information goes here />  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="4cecd-167">Adicione uma entrada para o provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-167">Add an entry for the data provider.</span></span>  
  
    |<span data-ttu-id="4cecd-168">Atributo</span><span class="sxs-lookup"><span data-stu-id="4cecd-168">Attribute</span></span>|<span data-ttu-id="4cecd-169">Descrição</span><span class="sxs-lookup"><span data-stu-id="4cecd-169">Description</span></span>|  
    |---------------|-----------------|  
    |`Name`|<span data-ttu-id="4cecd-170">Forneça um nome exclusivo para o provedor de dados, como, por exemplo, **MeuProvedorDadosNET**.</span><span class="sxs-lookup"><span data-stu-id="4cecd-170">Provide a unique name for the data provider, for example, **MyNETDataProvider**.</span></span> <span data-ttu-id="4cecd-171">O comprimento máximo do atributo `Name` é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="4cecd-171">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="4cecd-172">O nome deve ser exclusivo entre todas as entradas dento do elemento `Extension` de um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="4cecd-172">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="4cecd-173">O valor incluído aqui será exibido na lista suspensa dos tipos de fonte de dados quando você criar uma nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-173">The value that you include here appears in the drop-down list of data source types when you create a new data source.</span></span>|  
    |`Type`|<span data-ttu-id="4cecd-174">Insira uma lista separada por vírgulas que inclua o namespace totalmente qualificado da classe que implementa a interface <xref:System.Data.IDbConnection> , seguida pelo nome do assembly do provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] (sem incluir a extensão de nome de arquivo .dll).</span><span class="sxs-lookup"><span data-stu-id="4cecd-174">Enter a comma-separated list that includes the fully qualified namespace of the class that implements the <xref:System.Data.IDbConnection> interface, followed by the name of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly (not including the .dll file name extension).</span></span>|  
  
     <span data-ttu-id="4cecd-175">Por exemplo, a entrada deve ser semelhante à seguinte para uma DLL implantada no diretório PrivateAssemblies do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4cecd-175">For example, the entry might resemble the following for a DLL deployed to the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] PrivateAssemblies directory:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly" />   
    ```  
  
     <span data-ttu-id="4cecd-176">Se você carregar seu assembly no GAC, poderá fornecer as propriedades de nome forte.</span><span class="sxs-lookup"><span data-stu-id="4cecd-176">If you load your assembly into the GAC, you must provide the strong name properties.</span></span> <span data-ttu-id="4cecd-177">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4cecd-177">For example:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=MyPublicToken"/>  
    ```  
  
5.  <span data-ttu-id="4cecd-178">Localize o elemento `Designer` no arquivo RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="4cecd-178">Locate the `Designer` element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="4cecd-179">Uma entrada para o provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] deve ser criada no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="4cecd-179">An entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Designer>  
          <Your data provider configuration information goes here>  
       </Designer>  
    </Extensions>  
    ```  
  
6.  <span data-ttu-id="4cecd-180">Adicione a seguinte entrada ao arquivo RSReportDesigner.config no elemento `Designer`:</span><span class="sxs-lookup"><span data-stu-id="4cecd-180">Add the following entry to the RSReportDesigner.config file under the `Designer` element.</span></span> <span data-ttu-id="4cecd-181">apenas o atributo `Name` precisará ser substituído pelo nome que você forneceu nas entradas anteriores.</span><span class="sxs-lookup"><span data-stu-id="4cecd-181">You need to replace only the `Name` attribute with the name that you provided in previous entries.</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
#### <a name="to-set-the-code-group-policy-for-a-net-data-provider-on-the-report-designer-client"></a><span data-ttu-id="4cecd-182">Para definir a política do grupo de códigos para um provedor de dados .NET no cliente do Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="4cecd-182">To set the code group policy for a .NET data provider on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="4cecd-183">Faça uma cópia de backup do arquivo RSPreviewPolicy.config no diretório PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="4cecd-183">Make a backup copy of the RSPreviewPolicy.config file in the PrivateAssemblies directory.</span></span>  
  
2.  <span data-ttu-id="4cecd-184">Abra o arquivo RSPreviewPolicy.config com o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ou um editor de texto simples, como o Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="4cecd-184">Open RSPreviewPolicy.config with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="4cecd-185">Localize o elemento `CodeGroup` no arquivo RSPreviewPolicy.config.</span><span class="sxs-lookup"><span data-stu-id="4cecd-185">Locate the `CodeGroup` element in the RSPreviewPolicy.config file.</span></span>  
  
4.  <span data-ttu-id="4cecd-186">Adicione um grupo de códigos para o assembly do provedor de dados do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que conceda permissão `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="4cecd-186">Add a code group for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly that grants `FullTrust` permission.</span></span> <span data-ttu-id="4cecd-187">O grupo de códigos deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="4cecd-187">Your code group might resemble the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="ThisDataProviderCodeGroup"  
       Description="Code group for the .NET data provider">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url=  
    " C:\Program Files\Microsoft Visual Studio 9\Common7\IDE\PrivateAssemblies\DataProviderAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="4cecd-188">A associação da URL é apenas uma das condições de associação que você pode selecionar para o provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-188">URL membership is only one of many membership conditions you might select for the data provider.</span></span>  
  
### <a name="verifying-the-deployment-and-registration-on-the-report-designer-client"></a><span data-ttu-id="4cecd-189">Verificando a implantação e o registro no Cliente do Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="4cecd-189">Verifying the Deployment and Registration on the Report Designer Client</span></span>  
 <span data-ttu-id="4cecd-190">Antes de verificar a implantação, é preciso fechar todas as instâncias do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] no computador local.</span><span class="sxs-lookup"><span data-stu-id="4cecd-190">Before you can verify deployment, you must close all instances of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] on your local computer.</span></span> <span data-ttu-id="4cecd-191">Depois de encerrar todas as sessões atuais, você poderá verificar se o provedor de dados foi implantado com êxito ao Designer de Relatórios criando um novo projeto de relatório no [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cecd-191">After you have ended all current sessions, you can verify whether your data provider was deployed successfully to Report Designer by creating a new report project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="4cecd-192">O provedor de dados deve ser incluído na lista de tipos de fontes de dados disponíveis quando você criar um novo conjunto de dados para o relatório.</span><span class="sxs-lookup"><span data-stu-id="4cecd-192">The data provider should be included in the list of available data source types when you create a new data set for your report.</span></span>  
  
## <a name="platform-considerations"></a><span data-ttu-id="4cecd-193">Considerações sobre plataformas</span><span class="sxs-lookup"><span data-stu-id="4cecd-193">Platform Considerations</span></span>  
 <span data-ttu-id="4cecd-194">Em uma plataforma de 64 bits (x64), o [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] é executado no modo WOW de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="4cecd-194">On a 64-bit (x64) platform, [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] runs in 32-bit WOW mode.</span></span> <span data-ttu-id="4cecd-195">Quando você cria relatórios em uma plataforma x64, é preciso que os provedores de dados de 32 bits estejam instalados no cliente que está criando o relatório para que seja possível visualizá-los.</span><span class="sxs-lookup"><span data-stu-id="4cecd-195">When you author reports on an x64 platform, you need 32-bit data providers installed on the report authoring client in order to preview your reports.</span></span> <span data-ttu-id="4cecd-196">Ao publicar o relatório no mesmo sistema, é preciso que os provedores de dados de x64 estejam instalados para permitir a exibição do relatório com o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="4cecd-196">If you publish the report on the same system, you need x64 data providers to view the report with Report Manager.</span></span>  
  
 [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="4cecd-197">Não há suporte para plataformas com base em [!INCLUDE[vcpritanium](../../includes/vcpritanium-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cecd-197">is not supported for [!INCLUDE[vcpritanium](../../includes/vcpritanium-md.md)]-based platforms.</span></span>  
  
 <span data-ttu-id="4cecd-198">As extensões de processamento de dados que estão instaladas com o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] devem ser compiladas em modo nativo para cada plataforma e instaladas nos locais corretos.</span><span class="sxs-lookup"><span data-stu-id="4cecd-198">The data processing extensions that are installed with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] must be compiled natively for each platform and installed in the correct locations.</span></span> <span data-ttu-id="4cecd-199">Se você registrar um provedor de dados personalizado ou um provedor de dados padrão do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , sua compilação deverá ser executada em modo nativo para a plataforma adequada e a instalação deverá ocorrer em locais apropriados.</span><span class="sxs-lookup"><span data-stu-id="4cecd-199">If you register a custom data provider or a standard [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider, it needs to be compiled natively for the appropriate platform and installed the appropriate locations.</span></span> <span data-ttu-id="4cecd-200">Caso a execução esteja sendo realizada em uma plataforma de 32 bits, o provedor de dados deverá ser compilado para uma plataforma de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="4cecd-200">If you are running on a 32-bit platform, the data provider must be compiled for a 32-bit platform.</span></span> <span data-ttu-id="4cecd-201">Caso a execução esteja sendo realizada em uma plataforma de 64 bits, o provedor de dados deverá ser compilado para uma plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4cecd-201">If you are running on a 64-bit platform, the data provider must be compiled for the 64-bit platform.</span></span> <span data-ttu-id="4cecd-202">Não é permitido usar um provedor de dados de 32 bits com interfaces de 64 bits em uma plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4cecd-202">You cannot use a 32-bit data provider wrapped with 64-bit interfaces on a 64 bit platform.</span></span> <span data-ttu-id="4cecd-203">No software de terceiro, procure por informações que possam indicar se o provedor de dados funcionará na plataforma em que você deseja instalá-lo.</span><span class="sxs-lookup"><span data-stu-id="4cecd-203">Check your third-party software for information about whether the data provider will work on the installed platform.</span></span> <span data-ttu-id="4cecd-204">Para obter mais informações sobre os provedores de dados e o suporte à plataforma, consulte [Fontes de dados com suporte no Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span><span class="sxs-lookup"><span data-stu-id="4cecd-204">For more information about data providers and platform support, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cecd-205">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4cecd-205">See Also</span></span>  
 <span data-ttu-id="4cecd-206">[Configurar e administrar um servidor de relatório &#40;modo nativo do SSRS&#41;](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="4cecd-206">[Configure and Administer a Report Server &#40;SSRS Native Mode&#41;](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="4cecd-207">[Implementando uma extensão de processamento de dados](../extensions/data-processing/implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="4cecd-207">[Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="4cecd-208">[Arquivos de configuração do Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="4cecd-208">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="4cecd-209">Segurança de acesso do código no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="4cecd-209">Code Access Security in Reporting Services</span></span>](../extensions/secure-development/code-access-security-in-reporting-services.md)  
  
  
