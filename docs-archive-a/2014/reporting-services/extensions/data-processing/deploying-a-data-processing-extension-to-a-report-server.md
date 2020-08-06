---
title: Como implantar uma extensão de processamento de dados para um Servidor de Relatório | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: e00dface-70f8-434b-9763-8ebee18737d2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d606096b9f2060d3cf5b9cea1f95a5345e592383
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685453"
---
# <a name="how-to-deploy-a-data-processing-extension-to-a-report-server"></a><span data-ttu-id="a0257-102">Como fazer: Para implantar uma extensão de processamento de dados para um Servidor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="a0257-102">How to: Deploy a Data Processing Extension to a Report Server</span></span>
  <span data-ttu-id="a0257-103">Servidores de relatórios usam extensões de processamento de dados por recuperar e processar dados em relatórios renderizados.</span><span class="sxs-lookup"><span data-stu-id="a0257-103">Report servers use data processing extensions for retrieving and processing data in rendered reports.</span></span> <span data-ttu-id="a0257-104">Você deve implantar o seu assembly de extensão de processamento de dados para um servidor de relatório como um assembly privado.</span><span class="sxs-lookup"><span data-stu-id="a0257-104">You should deploy your data processing extension assembly to a report server as a private assembly.</span></span> <span data-ttu-id="a0257-105">Também será preciso criar uma entrada no arquivo de configuração do servidor de relatório, RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a0257-105">You also need to make an entry in the report server configuration file, RSReportServer.config.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="a0257-106">Procedimentos</span><span class="sxs-lookup"><span data-stu-id="a0257-106">Procedures</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="a0257-107">Para implantar um assembly de extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="a0257-107">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="a0257-108">Copie o assembly do local de preparo para o diretório bin do servidor de relatório no qual você deseja usar a extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="a0257-108">Copy your assembly from your staging location to the bin directory of the report server on which you want to use the data processing extension.</span></span> <span data-ttu-id="a0257-109">O local padrão do diretório bin do servidor de relatório é%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<*Instance Name*> \Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="a0257-109">The default location of the report server bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer\bin.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0257-110">Esta etapa impedirá uma atualização para uma instância mais nova do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a0257-110">This step will prevent an upgrade to a newer instance of SQL Server.</span></span> <span data-ttu-id="a0257-111">Para obter mais informações, consulte [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a0257-111">For more information, see [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
2.  <span data-ttu-id="a0257-112">Depois que o arquivo do assembly for copiado, abra o arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a0257-112">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="a0257-113">O arquivo RSReportServer.config está localizado no diretório ReportServer.</span><span class="sxs-lookup"><span data-stu-id="a0257-113">The RSReportServer.config file is located in the ReportServer directory.</span></span> <span data-ttu-id="a0257-114">Você precisa criar uma entrada no arquivo de configuração para o seu arquivo de assembly de extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="a0257-114">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="a0257-115">Abra o arquivo de configuração com o Visual Studio ou com um editor de texto simples, como o Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="a0257-115">You can open the configuration file with Visual Studio or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="a0257-116">Localize o elemento `Data` no arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="a0257-116">Locate the `Data` element in the RSReportServer.config file.</span></span> <span data-ttu-id="a0257-117">Uma entrada para a extensão de processamento de dados recém-criada deve ser adicionada no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="a0257-117">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="a0257-118">Adicione uma entrada para sua extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="a0257-118">Add an entry for your data processing extension.</span></span> <span data-ttu-id="a0257-119">A sua entrada deve incluir um elemento `Extension` com valores para `Name` e `Type` e deve ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="a0257-119">Your entry should include an `Extension` element with values for `Name` and `Type` and might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, MyExtensionAssembly" />  
    ```  
  
     <span data-ttu-id="a0257-120">O valor de `Name` é o nome exclusivo da extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="a0257-120">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="a0257-121">O valor de `Type` é uma lista separada por vírgulas que inclui uma entrada para o namespace totalmente qualificado da sua classe que implementa as interfaces <xref:Microsoft.ReportingServices.Interfaces.IExtension> e <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection>, seguida do nome do seu assembly (sem incluir a extensão de arquivo .dll).</span><span class="sxs-lookup"><span data-stu-id="a0257-121">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="a0257-122">Por padrão, as extensões de processamento de dados estão visíveis.</span><span class="sxs-lookup"><span data-stu-id="a0257-122">By default, data processing extensions are visible.</span></span> <span data-ttu-id="a0257-123">Para ocultar uma extensão de interfaces do usuário, como, por exemplo, o Gerenciador de Relatórios, adicione um atributo `Visible` ao elemento `Extension` e defina-o como `false`.</span><span class="sxs-lookup"><span data-stu-id="a0257-123">To hide an extension from user interfaces, such as Report Manager, add a `Visible` attribute to the `Extension` element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="a0257-124">Adicione um grupo de códigos ao seu assembly personalizado que concede permissão `FullTrust` para a sua extensão.</span><span class="sxs-lookup"><span data-stu-id="a0257-124">Add a code group for your custom assembly that grants `FullTrust` permission for your extension.</span></span> <span data-ttu-id="a0257-125">Para fazer isso, adicione o grupo de códigos ao arquivo rssrvpolicy.config localizado por padrão em%ProgramFiles%\Microsoft SQL Server \\<MSRS10_50. \<*Instance Name*> \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="a0257-125">You do this by adding the code group to the rssrvpolicy.config file located by default in %ProgramFiles%\Microsoft SQL Server\\<MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer.</span></span> <span data-ttu-id="a0257-126">O grupo de códigos pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="a0257-126">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<Instance Name>\Reporting Services\ReportServer\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="a0257-127">A associação da URL é somente uma das condições de associação que você pode escolher para a sua extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="a0257-127">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="a0257-128">Para obter mais informações sobre a segurança de acesso do código no [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], confira [Desenvolvimento seguro &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a0257-128">For more information about code access security in [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span></span>  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="a0257-129">Verificando a implantação</span><span class="sxs-lookup"><span data-stu-id="a0257-129">Verifying the Deployment</span></span>  
 <span data-ttu-id="a0257-130">Você pode verificar se sua extensão de processamento de dados foi implantada com êxito no servidor de relatório usando o método <xref:ReportService2010.ReportingService2010.ListExtensions%2A> do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="a0257-130">You can verify whether your data processing extension was deployed successfully to the report server by using the Web service <xref:ReportService2010.ReportingService2010.ListExtensions%2A> method.</span></span> <span data-ttu-id="a0257-131">Você também pode abrir o Gerenciador de Relatórios e verificar se a sua extensão foi incluída na lista de fontes de dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a0257-131">You can also open Report Manager and verify that your extension is included in the list of available data sources.</span></span> <span data-ttu-id="a0257-132">Para obter mais informações sobre o Gerenciador de Relatórios e fontes de dados, consulte [Criar, modificar e excluir fontes de dados compartilhadas &#40;SSRS&#41;](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a0257-132">For more information about Report Manager and data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0257-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a0257-133">See Also</span></span>  
 <span data-ttu-id="a0257-134">[Implantando uma extensão de processamento de dados](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="a0257-134">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="a0257-135">[Extensões do Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="a0257-135">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="a0257-136">[Implementando uma extensão de processamento de dados](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="a0257-136">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="a0257-137">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a0257-137">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
