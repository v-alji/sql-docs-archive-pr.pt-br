---
title: Personalizar parâmetros de extensão de renderização em RSReportServer.Config | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- configuration options [Reporting Services]
- DeviceInfo settings
- rendering extensions [Reporting Services], overriding behaviors
- parameters [Reporting Services], report rendering
- overriding report rendering behavior
- extensions [Reporting Services], rendering
ms.assetid: 3bf7ab2b-70bb-41c8-acda-227994d15aed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35a01e12fa4016d03717b008e4241c3be5e55236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685464"
---
# <a name="customize-rendering-extension-parameters-in-rsreportserverconfig"></a><span data-ttu-id="8f993-102">Personalizar parâmetros de extensão de renderização em RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="8f993-102">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>
  <span data-ttu-id="8f993-103">Você pode especificar parâmetros de extensão de renderização no arquivo de configuração RSReportServer para substituir o comportamento de renderização de relatório padrão para os relatórios executados em um servidor de relatórios do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f993-103">You can specify rendering extension parameters in the RSReportServer configuration file to override default report rendering behavior for reports that run on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server.</span></span> <span data-ttu-id="8f993-104">Os parâmetros de extensão de renderização podem ser modificados com os seguintes objetivos:</span><span class="sxs-lookup"><span data-stu-id="8f993-104">You can modify rendering extension parameters to achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="8f993-105">Alterar o modo de exibição do nome da extensão de renderização na lista Exportar da barra de ferramentas de relatórios (por exemplo, alterar “arquivo da Web” para “MHTML”) ou localizar o nome em um idioma diferente.</span><span class="sxs-lookup"><span data-stu-id="8f993-105">Change how the rendering extension name appears in the Export list of the report toolbar (for example, to change "Web archive" to "MHTML"), or localize the name to a different language.</span></span>  
  
-   <span data-ttu-id="8f993-106">Criar várias instâncias da mesma extensão de renderização para oferecer suporte a diferentes opções de apresentação de relatório (por exemplo, uma versão do modo retrato e paisagem da extensão de renderização Imagem).</span><span class="sxs-lookup"><span data-stu-id="8f993-106">Create multiple instances of the same rendering extension to support different report presentation options (for example, a portrait and landscape mode version of the Image rendering extension).</span></span>  
  
-   <span data-ttu-id="8f993-107">Alterar os parâmetros padrão da extensão de renderização para usar valores diferentes (por exemplo, a extensão de renderização Imagem usa TIFF como o formato de saída padrão; se desejar, você pode modificar os parâmetros de extensão para usar EMF).</span><span class="sxs-lookup"><span data-stu-id="8f993-107">Change the default rendering extension parameters to use different values (for example, the Image rendering extension uses TIFF as the default output format; you can modify the extension parameters to use EMF instead).</span></span>  
  
 <span data-ttu-id="8f993-108">A alteração dos parâmetros de extensão de renderização afeta somente as operações de renderização no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="8f993-108">Changing the rendering extension parameters only affects rendering operations on the report server.</span></span> <span data-ttu-id="8f993-109">Não é possível substituir as configurações de extensão de renderização ao visualizar relatórios no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="8f993-109">You cannot override rendering extension settings in report preview in Report Designer.</span></span>  
  
 <span data-ttu-id="8f993-110">A especificação de parâmetros de extensão de renderização nos arquivos de configuração afeta as extensões de renderização globalmente.</span><span class="sxs-lookup"><span data-stu-id="8f993-110">Specifying rendering extension parameters in the configuration files affects rendering extensions globally.</span></span> <span data-ttu-id="8f993-111">As definições dos arquivos de configuração são usadas no lugar de valores padrão sempre que uma extensão de renderização específica é usada.</span><span class="sxs-lookup"><span data-stu-id="8f993-111">The settings in the configuration files are used in place of default values whenever a particular rendering extension is used.</span></span> <span data-ttu-id="8f993-112">Se desejar definir parâmetros de extensão de renderização para um relatório ou operação de renderização específico, especifique as informações do dispositivo programaticamente usando o método <xref:ReportExecution2005.ReportExecutionService.Render%2A> ou especificando configurações de informações de dispositivo em uma URL de relatório.</span><span class="sxs-lookup"><span data-stu-id="8f993-112">If you want to set rendering extension parameters for a specific report or render operation, you must specify device information programmatically using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method or by specifying device information settings on a report URL.</span></span> <span data-ttu-id="8f993-113">Para obter mais informações sobre como especificar configurações de informações de dispositivo para uma operação de renderização e como exibir a lista completa de configurações de informações de dispositivo, consulte [Como passar configurações de informações de dispositivos para extensões de renderização](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="8f993-113">For more information about specifying device information settings for a render operation, and to view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="finding-and-modifying-rsreportserverconfig"></a><span data-ttu-id="8f993-114">Localizando e modificando RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="8f993-114">Finding and Modifying RSReportServer.config</span></span>  
 <span data-ttu-id="8f993-115">As configurações de formatos de saída de relatório são especificadas como parâmetros de extensão de renderização no arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="8f993-115">Configuration settings for report output formats are specified as rendering extension parameters in the RSReportServer.config file.</span></span> <span data-ttu-id="8f993-116">Para especificar parâmetros de extensão de renderização nos arquivos de configuração, você deve saber como definir estruturas XML que definem parâmetros de renderização.</span><span class="sxs-lookup"><span data-stu-id="8f993-116">To specify rendering extension parameters in the configuration files, you must know how to define the XML structures that set rendering parameters.</span></span> <span data-ttu-id="8f993-117">Há duas estruturas XML que podem ser modificadas:</span><span class="sxs-lookup"><span data-stu-id="8f993-117">There are two XML structures that you can modify:</span></span>  
  
-   <span data-ttu-id="8f993-118">O elemento `OverrideNames` define o nome para exibição e a linguagem da extensão de renderização.</span><span class="sxs-lookup"><span data-stu-id="8f993-118">The `OverrideNames` element defines the display name and language of the rendering extension.</span></span>  
  
-   <span data-ttu-id="8f993-119">A estrutura XML `DeviceInfo` define as configurações de informações de dispositivo que são usadas por uma extensão de renderização.</span><span class="sxs-lookup"><span data-stu-id="8f993-119">The `DeviceInfo` XML structure defines the device information settings that are used by a rendering extension.</span></span> <span data-ttu-id="8f993-120">A maioria dos parâmetros de extensão de renderização é especificada como configurações de informações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8f993-120">Most rendering extension parameters are specified as device information settings.</span></span>  
  
 <span data-ttu-id="8f993-121">Você pode usar um editor de texto para modificar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="8f993-121">You can use a text editor to modify the file.</span></span> <span data-ttu-id="8f993-122">O arquivo RSReportServer.config pode ser localizado na pasta \Reporting Services\Report Server\Bin.</span><span class="sxs-lookup"><span data-stu-id="8f993-122">The RSReportServer.config file can be found in the \Reporting Services\Report Server\Bin folder.</span></span> <span data-ttu-id="8f993-123">Para obter mais informações sobre como modificar arquivos de configuração, consulte [Modificar um arquivo de configuração do Reporting Services &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="8f993-123">For more information about modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span>  
  
## <a name="changing-the-display-name"></a><span data-ttu-id="8f993-124">Alterando o nome para exibição</span><span class="sxs-lookup"><span data-stu-id="8f993-124">Changing the Display Name</span></span>  
 <span data-ttu-id="8f993-125">O nome para exibição de uma extensão de renderização aparece na lista Exportar da barra de ferramentas de relatório.</span><span class="sxs-lookup"><span data-stu-id="8f993-125">The display name for a rendering extension appears in the Export list of the report toolbar.</span></span> <span data-ttu-id="8f993-126">Exemplos de nomes para exibição padrão incluem arquivos da Web, TIFF e Acrobat (PDF).</span><span class="sxs-lookup"><span data-stu-id="8f993-126">Examples of default display names include Web archive, TIFF file, and Acrobat (PDF) file.</span></span> <span data-ttu-id="8f993-127">Você pode substituir o nome para exibição padrão por um valor personalizado especificando o elemento `OverrideNames` nos arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="8f993-127">You can replace the default display name with a custom value by specifying the `OverrideNames` element in the configuration files.</span></span> <span data-ttu-id="8f993-128">Além disso, se duas instâncias de uma única extensão de renderização forem definidas, use o elemento `OverrideNames` para diferenciar cada instância na lista Exportar.</span><span class="sxs-lookup"><span data-stu-id="8f993-128">In addition, if you are defining two instances of a single rendering extension, you can use the `OverrideNames` element to distinguish each instance in the Export list.</span></span>  
  
 <span data-ttu-id="8f993-129">Como os nomes para exibição são localizados, defina o atributo `Language` se estiver substituindo o nome padrão por um valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="8f993-129">Because display names are localized, you must set the `Language` attribute if you are replacing the default display name with a custom value.</span></span> <span data-ttu-id="8f993-130">Caso contrário, qualquer nome especificado será ignorado.</span><span class="sxs-lookup"><span data-stu-id="8f993-130">Otherwise, any name that you specify will be ignored.</span></span> <span data-ttu-id="8f993-131">O valor de idioma definido deve ser válido para o computador do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="8f993-131">The language value that you set must be valid for the report server computer.</span></span> <span data-ttu-id="8f993-132">Por exemplo, se o servidor de relatórios for executado em um sistema operacional francês, especifique "fr-FR" como o valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="8f993-132">For example, if the report server is running on a French operating system, you should specify "fr-FR" as the attribute value.</span></span>  
  
 <span data-ttu-id="8f993-133">O exemplo a seguir ilustra como fornecer um nome personalizado em um servidor de relatórios em inglês:</span><span class="sxs-lookup"><span data-stu-id="8f993-133">The following example illustrates how to provide a custom name on an English report server:</span></span>  
  
```  
<Extension Name="XML" Type="Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport,Microsoft.ReportingServices.DataRendering">  
   <OverrideNames>  
     <Name Language="en-US">My Custom Display Name for XML Rendering</Name>  
   </OverrideNames>  
</Extension>  
```  
  
## <a name="changing-device-information-settings"></a><span data-ttu-id="8f993-134">Alterando as configurações de informações de dispositivo</span><span class="sxs-lookup"><span data-stu-id="8f993-134">Changing Device Information Settings</span></span>  
 <span data-ttu-id="8f993-135">Para modificar as configurações padrão de informações de dispositivo que são usadas por uma extensão de renderização que já está implantada no servidor de relatórios, digite a estrutura XML `DeviceInfo` nos arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="8f993-135">To modify default device information settings that are used by a rendering extension that is already deployed on your report server, you must type the `DeviceInfo` XML structure into the configuration files.</span></span> <span data-ttu-id="8f993-136">Todas as extensões de renderização oferecem suporte para configurações de informações de dispositivo que são exclusivas na extensão em questão.</span><span class="sxs-lookup"><span data-stu-id="8f993-136">Every rendering extension supports device information settings that are unique to that extension.</span></span> <span data-ttu-id="8f993-137">Para exibir a lista completa de informações do dispositivo, consulte [Como passar configurações de informações de dispositivos para extensões de renderização](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="8f993-137">To view the complete list of device information settings, see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="8f993-138">O exemplo a seguir ilustra a estrutura XML e a sintaxe que modificam as configurações padrão da extensão de renderização Imagem:</span><span class="sxs-lookup"><span data-stu-id="8f993-138">The following example provides an illustration of the XML structure and syntax that modifies the default settings of the Image rendering extension:</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">Image (EMF)</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <ColorDepth>32</ColorDepth>  
                <DpiX>300</DpiX>  
                <DpiY>300</DpiY>  
                <OutputFormat>EMF</OutputFormat>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="configuring-multiple-entries-for-a-rendering-extension"></a><span data-ttu-id="8f993-139">Configurando várias entradas para uma extensão de renderização</span><span class="sxs-lookup"><span data-stu-id="8f993-139">Configuring Multiple Entries for a Rendering Extension</span></span>  
 <span data-ttu-id="8f993-140">Você pode criar várias instâncias da mesma extensão de renderização para oferecer suporte para opções de apresentação de relatório diferentes.</span><span class="sxs-lookup"><span data-stu-id="8f993-140">You can create multiple instances of the same rendering extension to support different report presentation options.</span></span> <span data-ttu-id="8f993-141">Cada instância definida pode ter uma combinação diferente de valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8f993-141">Each instance that you define can have a different combination of parameter values.</span></span> <span data-ttu-id="8f993-142">Ao definir novas instâncias de uma extensão de renderização existente, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8f993-142">When defining new instances of an existing rendering extension, be sure to do the following:</span></span>  
  
-   <span data-ttu-id="8f993-143">Especifique um nome exclusivo para a extensão.</span><span class="sxs-lookup"><span data-stu-id="8f993-143">Specify a unique name for the extension.</span></span>  
  
     <span data-ttu-id="8f993-144">Cada instância deve ter um valor exclusivo para o atributo `Name`.</span><span class="sxs-lookup"><span data-stu-id="8f993-144">Each instance must have a unique value for the `Name` attribute.</span></span> <span data-ttu-id="8f993-145">O exemplo a seguir usa os nomes "IMAGE (EMF Landscape)" e "IMAGE (EMF Portrait)" para diferenciar as duas instâncias.</span><span class="sxs-lookup"><span data-stu-id="8f993-145">The following example uses the names "IMAGE (EMF Landscape)" and "IMAGE (EMF Portrait)" to distinguish between the two instances.</span></span>  
  
     <span data-ttu-id="8f993-146">Tenha cuidado ao alterar o nome de uma extensão de renderização que já está implantada.</span><span class="sxs-lookup"><span data-stu-id="8f993-146">Use caution when changing the name of a rendering extension that is already deployed.</span></span> <span data-ttu-id="8f993-147">Os desenvolvedores que especificam extensões de renderização programaticamente usam o nome da extensão para identificar a instância que deve ser usada em uma operação de renderização específica.</span><span class="sxs-lookup"><span data-stu-id="8f993-147">Developers who specify rendering extensions programmatically use the extension name to identify which instance to use for a particular render operation.</span></span> <span data-ttu-id="8f993-148">Se estiver executando aplicativos personalizados do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] no servidor de relatórios, verifique se o desenvolvedor sabe se está modificando o nome de uma extensão existente ou adicionando uma nova extensão.</span><span class="sxs-lookup"><span data-stu-id="8f993-148">If you are running custom [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] applications on your report server, make sure that the developer knows if you modify an existing extension name or add a new one.</span></span>  
  
-   <span data-ttu-id="8f993-149">Especifique um nome para exibição exclusivo de forma que usuários possam entender as diferenças de cada formato de saída.</span><span class="sxs-lookup"><span data-stu-id="8f993-149">Specify a unique display name so that users can understand the differences for each output format.</span></span>  
  
     <span data-ttu-id="8f993-150">Se estiver configurando várias versões da mesma extensão, dê a cada versão um nome exclusivo fornecendo um valor para `OverrideNames`.</span><span class="sxs-lookup"><span data-stu-id="8f993-150">If you are configuring multiple versions of the same extension, you can give each version a unique name by providing a value for `OverrideNames`.</span></span> <span data-ttu-id="8f993-151">Caso contrário, todas as versões da extensão parecerão ter o mesmo nome na lista opções Exportar na barra de ferramentas de relatório.</span><span class="sxs-lookup"><span data-stu-id="8f993-151">Otherwise, all versions of the extension will appear to have the same name in the Export options list on the report toolbar.</span></span>  
  
 <span data-ttu-id="8f993-152">O exemplo a seguir ilustra como usar a extensão de renderização Imagem padrão (que produz a saída TIFF) para gerar EMF no modo Retrato, junto com uma segunda instância que gera relatórios em EMF no modo Paisagem.</span><span class="sxs-lookup"><span data-stu-id="8f993-152">The following example illustrates how to use the default Image rendering extension (which produces TIFF output) to output EMF in Portrait mode alongside a second instance that outputs reports in EMF in Landscape mode.</span></span> <span data-ttu-id="8f993-153">Observe que cada nome de extensão é exclusivo.</span><span class="sxs-lookup"><span data-stu-id="8f993-153">Notice that each extension name is unique.</span></span> <span data-ttu-id="8f993-154">Ao testar esse exemplo, escolha relatórios que não contenham recursos interativos como opções de mostrar/ocultar, matrizes ou links de detalhamentos (os recursos interativos não funcionam na extensão de renderização Imagem):</span><span class="sxs-lookup"><span data-stu-id="8f993-154">When testing this example, remember to choose reports that do not contain interactive features such as show/hide options, matrices, or drillthrough links (interactive features do not work in the Image rendering extension):</span></span>  
  
```  
<Render>  
    <Extension Name="IMAGE (EMF Landscape)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Landscape Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>8.5in</PageHeight>  
                <PageWidth>11in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
    <Extension Name="IMAGE (EMF Portrait)" Type="Microsoft.ReportingServices.Rendering.ImageRenderer.ImageRenderer,Microsoft.ReportingServices.ImageRendering">  
        <OverrideNames>  
            <Name Language="en-US">EMF in Portait Mode</Name>  
        </OverrideNames>  
        <Configuration>  
            <DeviceInfo>  
                <OutputFormat>EMF</OutputFormat>  
                <PageHeight>11in</PageHeight>  
                <PageWidth>8.5in</PageWidth>  
            </DeviceInfo>  
        </Configuration>  
    </Extension>  
</Render>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f993-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f993-155">See Also</span></span>  
 <span data-ttu-id="8f993-156">[Arquivo de configuração RSReportServer](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="8f993-156">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="8f993-157">[Arquivo de configuração RSReportDesigner](report-server/rsreportdesigner-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="8f993-157">[RSReportDesigner Configuration File](report-server/rsreportdesigner-configuration-file.md) </span></span>  
 <span data-ttu-id="8f993-158">[Configurações de informações de dispositivo CSV](csv-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="8f993-158">[CSV Device Information Settings](csv-device-information-settings.md) </span></span>  
 <span data-ttu-id="8f993-159">[Configurações de informações de dispositivo Excel](excel-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="8f993-159">[Excel Device Information Settings](excel-device-information-settings.md) </span></span>  
 <span data-ttu-id="8f993-160">[Configurações de informações de dispositivo HTML](html-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="8f993-160">[HTML Device Information Settings](html-device-information-settings.md) </span></span>  
 <span data-ttu-id="8f993-161">[Configurações de informações de dispositivo de imagem](image-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="8f993-161">[Image Device Information Settings](image-device-information-settings.md) </span></span>  
 <span data-ttu-id="8f993-162">[Configurações de informações de dispositivo MHTML](mhtml-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="8f993-162">[MHTML Device Information Settings](mhtml-device-information-settings.md) </span></span>  
 <span data-ttu-id="8f993-163">[Configurações de informações de dispositivo PDF](pdf-device-information-settings.md) </span><span class="sxs-lookup"><span data-stu-id="8f993-163">[PDF Device Information Settings](pdf-device-information-settings.md) </span></span>  
 [<span data-ttu-id="8f993-164">Configurações de informações do dispositivo XML</span><span class="sxs-lookup"><span data-stu-id="8f993-164">XML Device Information Settings</span></span>](xml-device-information-settings.md)  
  
  
