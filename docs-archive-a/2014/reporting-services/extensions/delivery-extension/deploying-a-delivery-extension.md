---
title: Implantando uma extensão de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], deploying
- Extension element
- deploying [Reporting Services], extensions
ms.assetid: 4436ce48-397d-42c7-9b5d-2a267e2a1b2c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f4a4e33266c8d3a27ce2a4ab5f568bdee349720f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584037"
---
# <a name="deploying-a-delivery-extension"></a><span data-ttu-id="1d6d6-102">Implantando uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="1d6d6-102">Deploying a Delivery Extension</span></span>
  <span data-ttu-id="1d6d6-103">As extensões de entrega fornecem suas informações de configuração na forma de um arquivo de configuração XML.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-103">Delivery extensions supply their configuration information in the form of an XML configuration file.</span></span> <span data-ttu-id="1d6d6-104">O arquivo XML é compatível com o esquema XML definido para extensões de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-104">The XML file conforms to the XML schema defined for delivery extensions.</span></span> <span data-ttu-id="1d6d6-105">As extensões de entrega oferecem infraestrutura para a definição e para a modificação do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-105">Delivery extensions provide infrastructure for setting and modifying the configuration file.</span></span>  
  
 <span data-ttu-id="1d6d6-106">Se uma extensão de entrega for substituída ou atualizada, todas as assinaturas que a referenciam permanecerão válidas.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-106">If a delivery extension is replaced or upgraded, all subscriptions that reference the delivery extension remain valid.</span></span>  
  
 <span data-ttu-id="1d6d6-107">Depois de escrever e compilar sua extensão de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] em uma biblioteca do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], você deve copiar a extensão para o diretório apropriado e adicionar uma entrada ao arquivo de configuração do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] adequado para que o servidor de relatório possa localizá-lo.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-107">After you have written and compiled your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension into a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] library, you must copy the extension to the appropriate directory and add an entry to the appropriate [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration file so the report server can locate it.</span></span>  
  
## <a name="configuration-file-extension-element"></a><span data-ttu-id="1d6d6-108">Elemento de extensão do arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="1d6d6-108">Configuration-File Extension Element</span></span>  
 <span data-ttu-id="1d6d6-109">As extensões de entrega que você implanta no servidor de relatório precisam ser inseridas como elementos `Extension` no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-109">Delivery extensions that you deploy to the report server need to be entered as `Extension` elements in the configuration file.</span></span> <span data-ttu-id="1d6d6-110">O arquivo de configuração para o servidor de relatório é RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-110">The configuration file for the report server is RSReportServer.config.</span></span>  
  
 <span data-ttu-id="1d6d6-111">A tabela a seguir descreve os atributos para o elemento `Extension` para extensões de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-111">The following table describes the attributes for the `Extension` element for delivery extensions.</span></span>  
  
|<span data-ttu-id="1d6d6-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="1d6d6-112">Attribute</span></span>|<span data-ttu-id="1d6d6-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="1d6d6-113">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="1d6d6-114">Um nome exclusivo para a extensão (por exemplo "Email do Servidor de Relatório" para a extensão de entrega de email ou "FileShare do Servidor de Relatório" para a extensão de entrega do compartilhamento de arquivo).</span><span class="sxs-lookup"><span data-stu-id="1d6d6-114">A unique name for the extension (for example, "Report Server E-Mail" for the e-mail delivery extension or "Report Server FileShare" for the file share delivery extension).</span></span> <span data-ttu-id="1d6d6-115">O comprimento máximo do atributo `Name` é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-115">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="1d6d6-116">O nome deve ser exclusivo entre todas as entradas dento do elemento `Extension` de um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-116">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="1d6d6-117">Se um nome duplicado estiver presente, o servidor de relatório retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-117">If a duplicate name is present, the report server returns an error.</span></span>|  
|`Type`|<span data-ttu-id="1d6d6-118">Uma lista separada por vírgulas que inclui o namespace totalmente qualificado junto com o nome do assembly.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-118">A comma-separated list that includes the fully qualified namespace along with the name of the assembly.</span></span>|  
|`Visible`|<span data-ttu-id="1d6d6-119">Um valor `false` indica que a extensão de entrega não deve ser visível nas interfaces do usuário.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-119">A value of `false` indicates that the delivery extension should not be visible in user interfaces.</span></span> <span data-ttu-id="1d6d6-120">Se o atributo não for incluído, o valor padrão será `true`.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-120">If the attribute is not included, the default value is `true`.</span></span>|  
  
 <span data-ttu-id="1d6d6-121">Para obter mais informações sobre o arquivo RSReportServer.config, consulte [Arquivos de configuração do Reporting Services](../../report-server/reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="1d6d6-121">For more information about the RSReportServer.config file, see [Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md).</span></span>  
  
## <a name="deploying-the-extension-to-the-report-server"></a><span data-ttu-id="1d6d6-122">Implantando a extensão para o Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="1d6d6-122">Deploying the Extension to the Report Server</span></span>  
 <span data-ttu-id="1d6d6-123">O servidor de relatório usa extensões de entrega para processamento e entrega de notificações ou de relatórios.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-123">The report server uses delivery extensions for processing and delivering notifications or reports.</span></span> <span data-ttu-id="1d6d6-124">Implante o seu assembly de extensão de entrega para o servidor de relatório como um assembly privado.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-124">You should deploy your delivery extension assembly to the report server as a private assembly.</span></span> <span data-ttu-id="1d6d6-125">Também será preciso criar uma entrada no arquivo de configuração do servidor de relatório, RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-125">You also need to make an entry in the report server configuration file, RSReportServer.config.</span></span>  
  
#### <a name="to-deploy-a-deliver-extension-assembly-to-a-report-server"></a><span data-ttu-id="1d6d6-126">Para implantar um assembly de extensão de entrega para um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="1d6d6-126">To deploy a deliver extension assembly to a report server</span></span>  
  
1.  <span data-ttu-id="1d6d6-127">Copie o assembly do local de preparação para o diretório bin do servidor de relatório no qual você deseja usar a extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-127">Copy your assembly from your staging location to the bin directory of the report server on which you want to use the delivery extension.</span></span> <span data-ttu-id="1d6d6-128">O local padrão do diretório bin do servidor de relatório é%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-128">The default location of the report server bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer\bin.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1d6d6-129">Se você estiver tentando substituir um assembly de extensão de entrega existente, primeiro deverá parar o serviço Servidor de Relatório antes de copiar o assembly atualizado.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-129">If you are attempting to overwrite an existing delivery extension assembly, you must first stop the Report Server service before copying the updated assembly.</span></span> <span data-ttu-id="1d6d6-130">Reinicie o seu serviço depois de terminar de copiar o assembly.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-130">Restart your service after the assembly is through copying.</span></span>  
  
2.  <span data-ttu-id="1d6d6-131">Depois que o arquivo do assembly for copiado, abra o arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-131">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="1d6d6-132">O arquivo de RSReportServer.config está localizado em%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-132">The RSReportServer.config file is located in the %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer directory.</span></span> <span data-ttu-id="1d6d6-133">É necessário criar uma entrada no arquivo de configuração para o arquivo de assembly de extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-133">You need to make an entry in the configuration file for your delivery extension assembly file.</span></span> <span data-ttu-id="1d6d6-134">Você pode abrir o arquivo de configuração com o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ou um editor de texto simples, como o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-134">You can open the configuration file with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="1d6d6-135">Localize o elemento `Delivery` no arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-135">Locate the `Delivery` element in the RSReportServer.config file.</span></span> <span data-ttu-id="1d6d6-136">Uma entrada para a sua extensão de entrega recém-criada deve ser feita no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-136">An entry for your newly created delivery extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Delivery>  
          <Your extension configuration information goes here>  
       </Delivery>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="1d6d6-137">Adicione uma entrada para a sua extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-137">Add an entry for your delivery extension.</span></span> <span data-ttu-id="1d6d6-138">A sua entrada deve incluir um elemento `Extension` com valores para `Name` e `Type` e poderia ser assim:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-138">Your entry should include an `Extension` element with values for `Name` and `Type`, and might look like the following:</span></span>  
  
    ```  
    <Extension Name="My Delivery Extension Name" Type="CompanyName.ExtensionName.MyDeliveryExtensionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="1d6d6-139">O valor de `Name` é o nome exclusivo da extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-139">The value for `Name` is the unique name of the delivery extension.</span></span> <span data-ttu-id="1d6d6-140">O valor de `Type` é uma lista separada por vírgulas que inclui uma entrada para o namespace totalmente qualificado da sua classe que implementa a interface <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>, seguida pelo nome do seu assembly (não incluindo a extensão de arquivo .dll).</span><span class="sxs-lookup"><span data-stu-id="1d6d6-140">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="1d6d6-141">Por padrão, as extensões de entrega ficam visíveis.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-141">By default, delivery extensions are visible.</span></span> <span data-ttu-id="1d6d6-142">Para ocultar uma extensão de interfaces do usuário, como, por exemplo, o Gerenciador de Relatórios, adicione um atributo `Visible` ao elemento `Extension` e defina-o como `false`.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-142">To hide an extension from user interfaces, such as Report Manager, add a `Visible` attribute to the `Extension` element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="1d6d6-143">Por fim, adicione um grupo de códigos ao seu assembly personalizado que concede permissão `FullTrust` para a sua extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-143">Finally, add a code group for your custom assembly that grants `FullTrust` permission for your delivery extension.</span></span> <span data-ttu-id="1d6d6-144">Para fazer isso, adicione o grupo de códigos ao arquivo de rssrvpolicy.config localizado por padrão em%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-144">You do this by adding the code group to the rssrvpolicy.config file located by default in %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer.</span></span> <span data-ttu-id="1d6d6-145">O grupo de códigos pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-145">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my delivery extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<InstanceName>\Reporting Services\ReportServer\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
     <span data-ttu-id="1d6d6-146">A associação da URL é somente uma das condições de associação que você pode escolher para a sua extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-146">URL membership is only one of many membership conditions you might choose for your delivery extension.</span></span> <span data-ttu-id="1d6d6-147">Para obter mais informações sobre a segurança de acesso do código no [!INCLUDE[ssRS](../../../includes/ssrs.md)], consulte [Desenvolvimento seguro &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-147">For more information about code access security in [!INCLUDE[ssRS](../../../includes/ssrs.md)], see.[Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="deploying-the-extension-to-report-manager"></a><span data-ttu-id="1d6d6-148">Implantando a Extensão no Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="1d6d6-148">Deploying the Extension to Report Manager</span></span>  
 <span data-ttu-id="1d6d6-149">Se a sua extensão de entrega implementar a interface <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl>, a sua extensão de entrega poderá ser usada com a página de Assinatura do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-149">If your delivery extension implements the <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> interface, your delivery extension can be used with the Report Manager Subscription page.</span></span> <span data-ttu-id="1d6d6-150">Para disponibilizar a interface do usuário de assinatura, você precisa implantar a sua extensão no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-150">To make the subscription user interface available, you need to deploy your extension to Report Manager.</span></span>  
  
#### <a name="to-deploy-a-deliver-extension-assembly-to-report-manager"></a><span data-ttu-id="1d6d6-151">Para implantar um assembly de extensão de entrega no Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="1d6d6-151">To deploy a deliver extension assembly to Report Manager</span></span>  
  
1.  <span data-ttu-id="1d6d6-152">Copie o seu assembly do seu local de preparação para o diretório bin do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-152">Copy your assembly from your staging location to the bin directory of Report Manager.</span></span> <span data-ttu-id="1d6d6-153">O local padrão do diretório bin Report Manager é%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportManager\bin.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-153">The default location of the Report Manager bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportManager\bin.</span></span>  
  
2.  <span data-ttu-id="1d6d6-154">Depois que o arquivo do assembly for copiado, abra o arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-154">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="1d6d6-155">O arquivo de RSReportServer.config está localizado em%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-155">The RSReportServer.config file is located in the %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportServer directory.</span></span> <span data-ttu-id="1d6d6-156">É necessário criar uma entrada no arquivo de configuração para o arquivo de assembly de extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-156">You need to make an entry in the configuration file for your delivery extension assembly file.</span></span> <span data-ttu-id="1d6d6-157">Você pode abrir o arquivo de configuração com o Visual Studio .NET ou com um editor de texto simples, como o Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-157">You can open the configuration file with Visual Studio .NET or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="1d6d6-158">Localize o elemento `DeliveryUI` no arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-158">Locate the `DeliveryUI` element in the RSReportServer.config file.</span></span> <span data-ttu-id="1d6d6-159">Uma entrada para a sua extensão de entrega recém-criada deve ser feita no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-159">An entry for your newly created delivery extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <DeliveryUI>  
          <Your extension configuration information goes here>  
       </DeliveryUI>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="1d6d6-160">Adicione uma entrada para a sua extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-160">Add an entry for your delivery extension.</span></span> <span data-ttu-id="1d6d6-161">A sua entrada deve incluir um elemento `Extension` com valores para `Name` e `Type` e deve ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-161">Your entry should include an `Extension` element with values for `Name` and `Type` and might look like the following:</span></span>  
  
    ```  
    <Extension Name="My Delivery Extension Name" Type="CompanyName.ExtensionName.MyDeliveryUIExtensionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="1d6d6-162">O valor de `Name` é o nome exclusivo da extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-162">The value for `Name` is the unique name of the delivery extension.</span></span> <span data-ttu-id="1d6d6-163">O valor de `Type` é uma lista separada por vírgulas que inclui uma entrada para o namespace totalmente qualificado da sua classe que implementa a interface <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl>, seguida pelo nome do seu assembly (não incluindo a extensão de arquivo .dll).</span><span class="sxs-lookup"><span data-stu-id="1d6d6-163">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> interface, followed by the name of your assembly (not including the .dll file extension).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1d6d6-164">O valor do atributo `Name` deve ser idêntico para as entradas de arquivo de configuração do Servidor de Relatório e do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-164">The value of the `Name` attribute must be identical for both the Report Server and Report Manager configuration file entries.</span></span> <span data-ttu-id="1d6d6-165">Se não forem idênticas, a configuração do seu servidor não será válida.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-165">If they are not identical, your server configuration is not valid.</span></span>  
  
     <span data-ttu-id="1d6d6-166">Por fim, adicione um grupo de códigos ao seu assembly personalizado que concede permissão `FullTrust` para a sua extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-166">Finally, add a code group for your custom assembly that grants `FullTrust` permission for your delivery extension.</span></span> <span data-ttu-id="1d6d6-167">Para fazer isso, adicione o grupo de códigos ao arquivo RSmgrpolicy.config localizado por padrão em C:\Program Files\Microsoft SQL Server \ MSRS10_50. \<InstanceName> \Reporting Services\ReportManager.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-167">You do this by adding the code group to the RSmgrpolicy.config file located by default in C:\Program Files\Microsoft SQL Server\MSRS10_50.\<InstanceName>\Reporting Services\ReportManager.</span></span> <span data-ttu-id="1d6d6-168">O grupo de códigos pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="1d6d6-168">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my delivery UI extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<InstanceName>\Reporting Services\ReportManager\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
     <span data-ttu-id="1d6d6-169">A associação da URL é somente uma das condições de associação que você pode escolher para a sua extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-169">URL membership is only one of many membership conditions you might choose for your delivery extension.</span></span> <span data-ttu-id="1d6d6-170">Para obter mais informações sobre a segurança de acesso do código no [!INCLUDE[ssRS](../../../includes/ssrs.md)] , consulte [&#40;de desenvolvimento seguro Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="1d6d6-170">For more information about code access security in [!INCLUDE[ssRS](../../../includes/ssrs.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="1d6d6-171">Verificando a implantação</span><span class="sxs-lookup"><span data-stu-id="1d6d6-171">Verifying the Deployment</span></span>  
 <span data-ttu-id="1d6d6-172">Você pode verificar se sua extensão de entrega foi implantada com êxito no servidor de relatório usando o método <xref:ReportService2010.ReportingService2010.ListExtensions%2A> do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-172">You can verify whether your delivery extension was deployed successfully to the report server by using the Web service <xref:ReportService2010.ReportingService2010.ListExtensions%2A> method.</span></span> <span data-ttu-id="1d6d6-173">Você também pode abrir o Gerenciador de Relatórios e verificar se a sua extensão foi incluída na lista de extensões de entrega disponíveis para uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="1d6d6-173">You can also open Report Manager and verify that your extension is included in the list of available delivery extensions for a subscription.</span></span> <span data-ttu-id="1d6d6-174">Para obter mais informações sobre Report Manager e assinaturas, consulte [assinaturas e entrega &#40;Reporting Services&#41;](../../subscriptions/subscriptions-and-delivery-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="1d6d6-174">For more information about Report Manager and subscriptions, see [Subscriptions and Delivery &#40;Reporting Services&#41;](../../subscriptions/subscriptions-and-delivery-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d6d6-175">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d6d6-175">See Also</span></span>  
 <span data-ttu-id="1d6d6-176">[Implementando uma extensão de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="1d6d6-176">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="1d6d6-177">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1d6d6-177">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
