---
title: Como implantar uma extensão de processamento de dados no Designer de Relatórios | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: 3614e601-004e-4a16-8388-836ffd67e9dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56bd56e9d8eeeeff1781f22b42cf0eb1ce706fa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685445"
---
# <a name="how-to-deploy-a-data-processing-extension-to-report-designer"></a><span data-ttu-id="5a35c-102">Como fazer: Para implantar uma extensão de processamento de dados para o Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="5a35c-102">How to: Deploy a Data Processing Extension to Report Designer</span></span>
  <span data-ttu-id="5a35c-103">O Designer de Relatórios usa extensões de processamento de dados para recuperar e processar dados enquanto você estiver criando relatórios.</span><span class="sxs-lookup"><span data-stu-id="5a35c-103">Report Designer uses data processing extensions for retrieving and processing data while you are designing reports.</span></span> <span data-ttu-id="5a35c-104">Você deve implantar o seu assembly de extensão de processamento de dados para o Designer de Relatórios como um assembly privado.</span><span class="sxs-lookup"><span data-stu-id="5a35c-104">You should deploy your data processing extension assembly to Report Designer as a private assembly.</span></span> <span data-ttu-id="5a35c-105">Precisa também criar uma uma entrada no arquivo de configuração do Designer de Relatórios, RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="5a35c-105">You also need to make an entry in the Report Designer configuration file, RSReportDesigner.config.</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="5a35c-106">Para implantar um assembly de extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="5a35c-106">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="5a35c-107">Copie o assembly de seu local de preparação para o diretório do Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="5a35c-107">Copy your assembly from your staging location to the Report Designer directory.</span></span> <span data-ttu-id="5a35c-108">O local padrão do diretório do Designer de Relatórios é C:\Arquivos de Programas\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="5a35c-108">The default location of the Report Designer directory is C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span>  
  
2.  <span data-ttu-id="5a35c-109">Depois de copiar o arquivo de assembly, abra o arquivo RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="5a35c-109">After the assembly file is copied, open the RSReportDesigner.config file.</span></span> <span data-ttu-id="5a35c-110">O arquivo RSReportDesigner.config também está localizado no diretório do Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="5a35c-110">The RSReportDesigner.config file is also located in the Report Designer directory.</span></span> <span data-ttu-id="5a35c-111">Você precisa criar uma entrada no arquivo de configuração para o seu arquivo de assembly de extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="5a35c-111">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="5a35c-112">Você pode abrir o arquivo de configuração com [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ou com um simples editor de texto, como o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="5a35c-112">You can open the configuration file with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or with a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="5a35c-113">Localize o elemento **Data** no arquivo RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="5a35c-113">Locate the **Data** element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="5a35c-114">Uma entrada para a extensão de processamento de dados recém-criada deve ser adicionada no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="5a35c-114">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="5a35c-115">Adicione uma entrada para sua extensão de processamento de dados, que inclui um elemento de **extensão** com valores para os `Name` `Type` atributos, e `Visible` .</span><span class="sxs-lookup"><span data-stu-id="5a35c-115">Add an entry for your data processing extension which includes an **Extension** element with values for the `Name`, `Type`, and `Visible` attributes.</span></span> <span data-ttu-id="5a35c-116">A sua entrada poderia ser assim:</span><span class="sxs-lookup"><span data-stu-id="5a35c-116">Your entry might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="5a35c-117">O valor de `Name` é o nome exclusivo da extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="5a35c-117">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="5a35c-118">O valor de `Type` é uma lista separada por vírgulas que inclui uma entrada para o namespace totalmente qualificado da sua classe que implementa as interfaces <xref:Microsoft.ReportingServices.Interfaces.IExtension> e <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection>, seguida do nome do seu assembly (sem incluir a extensão de arquivo .dll).</span><span class="sxs-lookup"><span data-stu-id="5a35c-118">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="5a35c-119">Por padrão, as extensões de processamento de dados estão visíveis.</span><span class="sxs-lookup"><span data-stu-id="5a35c-119">By default, data processing extensions are visible.</span></span> <span data-ttu-id="5a35c-120">Para ocultar uma extensão das interfaces do usuário, como Report Designer, adicione um `Visible` atributo ao elemento de **extensão** e defina-o como `false` .</span><span class="sxs-lookup"><span data-stu-id="5a35c-120">To hide an extension from user interfaces, such as Report Designer, add a `Visible` attribute to the **Extension** element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="5a35c-121">Por fim, adicione um grupo de códigos ao assembly personalizado que concede a permissão **FullTrust** para a extensão.</span><span class="sxs-lookup"><span data-stu-id="5a35c-121">Finally, add a code group for your custom assembly that grants **FullTrust** permission for your extension.</span></span> <span data-ttu-id="5a35c-122">Faça isso adicionando o grupo de códigos ao arquivo rspreviewpolicy.config localizado por padrão em C:\Arquivos de Programas\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="5a35c-122">You do this by adding the code group to the rspreviewpolicy.config file located by default in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span> <span data-ttu-id="5a35c-123">O grupo de códigos pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="5a35c-123">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="5a35c-124">A associação da URL é somente uma das condições de associação que você pode escolher para a sua extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="5a35c-124">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="5a35c-125">Para obter mais informações sobre a segurança de acesso do código no [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)], consulte [Desenvolvimento seguro &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="5a35c-125">For more information about code access security in [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="generic-query-designer"></a><span data-ttu-id="5a35c-126">Designer de consulta genérico</span><span class="sxs-lookup"><span data-stu-id="5a35c-126">Generic Query Designer</span></span>  
 <span data-ttu-id="5a35c-127">O Designer de Relatórios oferece um designer de consulta genérico que você pode usar com extensões de processamento de dados personalizadas.</span><span class="sxs-lookup"><span data-stu-id="5a35c-127">Report Designer provides a generic query designer that you can use with custom data processing extensions.</span></span> <span data-ttu-id="5a35c-128">Esse designer consiste em dois painéis: um painel de consulta e um painel de resultados.</span><span class="sxs-lookup"><span data-stu-id="5a35c-128">This designer consists of two panes: a query pane and a results pane.</span></span> <span data-ttu-id="5a35c-129">Você pode usar o designer genérico para escrever consultas que não são suportadas pela interface gráfica.</span><span class="sxs-lookup"><span data-stu-id="5a35c-129">You can use the generic designer to write queries that are not supported by the graphical interface.</span></span> <span data-ttu-id="5a35c-130">Ao contrário do designer de consultas gráficas, o designer de consulta genérico não verifica a sintaxe da consulta ou a reestrutura.</span><span class="sxs-lookup"><span data-stu-id="5a35c-130">Unlike the graphical query designer, the generic query designer does not check query syntax or restructure the query.</span></span>  
  
#### <a name="to-enable-the-generic-query-designer-for-a-custom-extension"></a><span data-ttu-id="5a35c-131">Para habilitar o designer de consulta genérico para uma extensão personalizada.</span><span class="sxs-lookup"><span data-stu-id="5a35c-131">To enable the generic query designer for a custom extension</span></span>  
  
-   <span data-ttu-id="5a35c-132">Adicione a seguinte entrada ao arquivo de RSReportDesigner.config sob o elemento **Designer** , substituindo o `Name` atributo pelo nome que você forneceu nas entradas anteriores.</span><span class="sxs-lookup"><span data-stu-id="5a35c-132">Add the following entry to the RSReportDesigner.config file under the **Designer** element, replacing the `Name` attribute with the name that you provided in previous entries.</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="5a35c-133">Verificando a implantação</span><span class="sxs-lookup"><span data-stu-id="5a35c-133">Verifying the Deployment</span></span>  
 <span data-ttu-id="5a35c-134">Antes de verificar a implantação, é preciso fechar todas as instâncias do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] no computador local.</span><span class="sxs-lookup"><span data-stu-id="5a35c-134">Before you can verify deployment, you must close all instances of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] on your local computer.</span></span> <span data-ttu-id="5a35c-135">Depois de encerrar todas as sessões atuais, você poderá verificar se a extensão de processamento de dados foi implantada com êxito para o Designer de Relatórios criando um novo projeto de relatório no [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a35c-135">After you have ended all current sessions, you can verify whether your data processing extension was deployed successfully to Report Designer by creating a new report project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="5a35c-136">A sua extensão deve ser incluída na lista de tipos de fontes de dados disponíveis quando você criar um novo conjunto de dados para o relatório.</span><span class="sxs-lookup"><span data-stu-id="5a35c-136">Your extension should be included in the list of available data source types when you create a new data set for your report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a35c-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5a35c-137">See Also</span></span>  
 <span data-ttu-id="5a35c-138">[Implantando uma extensão de processamento de dados](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="5a35c-138">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="5a35c-139">[Extensões do Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="5a35c-139">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="5a35c-140">[Implementando uma extensão de processamento de dados](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="5a35c-140">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="5a35c-141">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5a35c-141">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
