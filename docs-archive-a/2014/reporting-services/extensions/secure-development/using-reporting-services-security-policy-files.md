---
title: Usando arquivos de política de segurança do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- code groups [Reporting Services]
- CodeGroup elements
- configuration files [Reporting Services]
- code access security [Reporting Services], security policies
- security policies [Reporting Services]
- security configuration files [Reporting Services]
- named permission sets [Reporting Services]
ms.assetid: 2280fff6-3de7-44b1-87da-5db0ec975928
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 15c5422741137505bc29a2de861fca1420e455d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583383"
---
# <a name="using-reporting-services-security-policy-files"></a><span data-ttu-id="f99e4-102">Usando arquivos de política de segurança do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f99e4-102">Using Reporting Services Security Policy Files</span></span>
  <span data-ttu-id="f99e4-103">O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] armazena informações de política de segurança de componentes em três arquivos de configuração que são copiados no sistema de arquivos durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="f99e4-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] stores component security policy information in three configuration files that are copied to the file system during setup.</span></span> <span data-ttu-id="f99e4-104">Estes arquivos de configuração podem conter uma combinação de políticas de segurança de uso interno e definidas pelo usuário assemblies de código no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f99e4-104">These configuration files can contain a combination of internal-use and user-defined security policies for code assemblies in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="f99e4-105">Os três arquivos de configuração correspondem a três componentes de segurança do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]: o servidor de relatório e o serviço do Windows, o aplicativo Web do Gerenciador de Relatórios e a janela de exibição do Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f99e4-105">The three configuration files correspond to three securable components in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]: The report server and Windows service, the Report Manager Web application, and the Report Designer preview window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f99e4-106">Há dois modos de visualização do Designer de Relatórios: a guia Visualizar e a janela pop-up Visualizar, que é iniciada quando o Projeto de Relatório é inicializado no modo **DebugLocal**.</span><span class="sxs-lookup"><span data-stu-id="f99e4-106">There are two preview modes for Report Designer: the preview tab and the pop-up preview window that is launched when your Report Project is started in **DebugLocal** mode.</span></span> <span data-ttu-id="f99e4-107">A guia **Visualizar** não é um componente protegível e não aplica as configurações de política de segurança.</span><span class="sxs-lookup"><span data-stu-id="f99e4-107">The **Preview** tab is not a securable component and does not apply security policy settings.</span></span> <span data-ttu-id="f99e4-108">A janela de exibição foi desenvolvida para simular a funcionalidade do servidor de relatório e, portanto, tem um arquivo de configuração de política que você ou um administrador devem modificar para usar assemblies e extensões personalizadas no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f99e4-108">The preview window is meant to simulate the report server functionality and therefore has a policy configuration file that you or an administrator must modify to use custom assemblies and custom extensions in Report Designer.</span></span>  
  
 <span data-ttu-id="f99e4-109">Os arquivos de configuração de política de segurança contêm informações sobre a classe de segurança, alguns conjuntos nomeados padrão de permissões e os grupos de código para os assemblies do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f99e4-109">The security policy configuration files contain security class information, some default named permission sets, and the code groups for assemblies in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="f99e4-110">Os arquivos de configuração de política do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] são similares ao arquivo Security.config que determina a hierarquia de grupos de código e os conjuntos de permissões associados às políticas do nível corporativo e de máquina do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f99e4-110">The policy configuration files of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] are similar to the Security.config file that determines the code group hierarchy and permission sets associated with machine and enterprise level policies in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="f99e4-111">O local deste arquivo é C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\CONFIG\security.config.</span><span class="sxs-lookup"><span data-stu-id="f99e4-111">The location of this file is C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\CONFIG\security.config.</span></span>  
  
## <a name="policy-files-in-reporting-services"></a><span data-ttu-id="f99e4-112">Arquivos de política do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f99e4-112">Policy Files in Reporting Services</span></span>  
 <span data-ttu-id="f99e4-113">A tabela a seguir lista os arquivos de configuração de política do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], sua localização (supondo uma instalação padrão) e suas respectivas funções.</span><span class="sxs-lookup"><span data-stu-id="f99e4-113">The following table lists the policy configuration files in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], their locations (assuming a default installation), and their respective functions.</span></span>  
  
|<span data-ttu-id="f99e4-114">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="f99e4-114">File name</span></span>|<span data-ttu-id="f99e4-115">Local (instalação padrão)</span><span class="sxs-lookup"><span data-stu-id="f99e4-115">Location (default installation)</span></span>|<span data-ttu-id="f99e4-116">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="f99e4-116">Description</span></span>|  
|---------------|---------------------------------------|-----------------|  
|<span data-ttu-id="f99e4-117">rssrvpolicy.config</span><span class="sxs-lookup"><span data-stu-id="f99e4-117">rssrvpolicy.config</span></span>|<span data-ttu-id="f99e4-118">C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer</span><span class="sxs-lookup"><span data-stu-id="f99e4-118">C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer</span></span>|<span data-ttu-id="f99e4-119">O arquivo de configuração de política de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="f99e4-119">The report server policy configuration file.</span></span> <span data-ttu-id="f99e4-120">Estas políticas de segurança afetam principalmente expressões de relatório e assemblies personalizados após um relatório ser implantado em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="f99e4-120">These security policies primarily affect report expressions and custom assemblies once a report is deployed to a report server.</span></span> <span data-ttu-id="f99e4-121">Este arquivo de política também afeta dados personalizados, extensões de entrega, renderização e segurança implantados no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="f99e4-121">This policy file also affects custom data, delivery, rendering and security extensions deployed to the report server.</span></span>|  
|<span data-ttu-id="f99e4-122">rsmgrpolicy.config</span><span class="sxs-lookup"><span data-stu-id="f99e4-122">rsmgrpolicy.config</span></span>|<span data-ttu-id="f99e4-123">C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportManager</span><span class="sxs-lookup"><span data-stu-id="f99e4-123">C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportManager</span></span>|<span data-ttu-id="f99e4-124">Arquivo de configuração de política do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f99e4-124">Report Manager policy configuration file.</span></span> <span data-ttu-id="f99e4-125">Estas políticas de segurança afetam todos os assemblies que estendem o Gerenciador de Relatórios; por exemplo, extensões de interface de usuário de assinatura para entrega personalizada.</span><span class="sxs-lookup"><span data-stu-id="f99e4-125">These security policies affect all assemblies that extend Report Manager; for example, subscription user interface extensions for custom delivery.</span></span>|  
|<span data-ttu-id="f99e4-126">rspreviewpolicy.config</span><span class="sxs-lookup"><span data-stu-id="f99e4-126">rspreviewpolicy.config</span></span>|<span data-ttu-id="f99e4-127">C:\Arquivos de Programas\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies</span><span class="sxs-lookup"><span data-stu-id="f99e4-127">C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies</span></span>|<span data-ttu-id="f99e4-128">Arquivo de configuração de política de visualização autônoma do Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f99e4-128">The Report Designer stand-alone preview policy configuration file.</span></span> <span data-ttu-id="f99e4-129">Estas políticas de segurança afetam assemblies personalizados e expressões de relatório que são usados em relatórios durante a visualização e o desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="f99e4-129">These security policies affect custom assemblies and report expressions that are used in reports during preview and development.</span></span> <span data-ttu-id="f99e4-130">Estas políticas também afetam extensões personalizadas, como extensões de processamento de dados, que são implantadas no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f99e4-130">These policies also affect custom extensions, such as data processing extensions, that are deployed to Report Designer.</span></span>|  
  
## <a name="modifying-configuration-files"></a><span data-ttu-id="f99e4-131">Modificando arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="f99e4-131">Modifying Configuration Files</span></span>  
 <span data-ttu-id="f99e4-132">As configurações são especificadas como elementos ou atributos XML.</span><span class="sxs-lookup"><span data-stu-id="f99e4-132">Configuration settings are specified as either XML elements or attributes.</span></span> <span data-ttu-id="f99e4-133">Se você entender de XML e arquivos de configuração, use um editor de texto ou de código para modificar configurações definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="f99e4-133">If you understand XML and configuration files, you can use a text or code editor to modify user-definable settings.</span></span> <span data-ttu-id="f99e4-134">Os arquivos de configuração de segurança contêm informações sobre a hierarquia de grupos de código e os conjuntos de permissões associados a um nível de política do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f99e4-134">Security configuration files contain information about the code group hierarchy and permission sets associated with a policy level in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="f99e4-135">É recomendado usar o utilitário de configuração do .NET Framework (Mscorcfg.msc) ou o utilitário de política de segurança de acesso ao código (Caspol.exe) para modificar políticas de segurança no arquivo Security.config primeiro, de modo que as alterações de política correspondam a elementos válidos de configuração XML para arquivos de política.</span><span class="sxs-lookup"><span data-stu-id="f99e4-135">It is recommended that you use the .NET Framework Configuration Utility (Mscorcfg.msc) or Code Access Security Policy Utility (Caspol.exe) to modify security policies in the Security.config file first, so that policy changes correspond to valid XML configuration elements for policy files.</span></span> <span data-ttu-id="f99e4-136">Feito isso, você pode recortar e colar os novos grupos de código e conjuntos de permissões do Security.config para o arquivo de política do componente ao qual estão sendo adicionadas permissões de código.</span><span class="sxs-lookup"><span data-stu-id="f99e4-136">Once you have done that, you can cut and paste the new code groups and permission sets from Security.config to the policy file for the component to which you are adding code permissions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f99e4-137">Você deve fazer backup dos arquivos de configuração de política antes de fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="f99e4-137">You should backup your policy configuration files prior to making any changes.</span></span>  
  
 <span data-ttu-id="f99e4-138">O uso desse método tem duas vantagens.</span><span class="sxs-lookup"><span data-stu-id="f99e4-138">Using this approach accomplishes two things.</span></span> <span data-ttu-id="f99e4-139">Primeiro, permite usar uma ferramenta visual para criar grupos de código e conjuntos de permissões para o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f99e4-139">First, it enables you to use a visual tool to build your code groups and permission sets for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="f99e4-140">Isto é muito mais fácil do que gravar elementos de configuração XML a partir do zero.</span><span class="sxs-lookup"><span data-stu-id="f99e4-140">This is much easier than writing XML configuration elements from scratch.</span></span> <span data-ttu-id="f99e4-141">Em segundo lugar, esse método assegura que os arquivos de configuração de política de segurança não sejam corrompidos com elementos e atributos XML malformados.</span><span class="sxs-lookup"><span data-stu-id="f99e4-141">Secondly, it ensures that you do not corrupt the security policy configuration files with malformed XML elements and attributes.</span></span> <span data-ttu-id="f99e4-142">Para obter mais informações sobre o utilitário de política de Segurança de Acesso do Código, consulte Usando arquivos de política de segurança do Reporting Services no MSDN.</span><span class="sxs-lookup"><span data-stu-id="f99e4-142">For more information about the Code Access Security Policy Utility, see Using Reporting Services Security Policy Files on MSDN.</span></span>  
  
 <span data-ttu-id="f99e4-143">Antes de modificar arquivos de configuração de política, leia todas as informações disponíveis nesta seção e os tópicos relacionados.</span><span class="sxs-lookup"><span data-stu-id="f99e4-143">Before modifying policy configuration files, you should read all the information available in this section and related topics.</span></span> <span data-ttu-id="f99e4-144">A modificação da configuração de política do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] pode afetar significativamente a segurança no que diz respeito a como os componentes do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] executam módulos de código externos.</span><span class="sxs-lookup"><span data-stu-id="f99e4-144">Modifying the policy configuration of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] can have a significant security impact on how [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] components execute external code modules.</span></span>  
  
## <a name="placement-of-codegroup-elements-for-extensions"></a><span data-ttu-id="f99e4-145">Colocação de elementos CodeGroup para extensões</span><span class="sxs-lookup"><span data-stu-id="f99e4-145">Placement of CodeGroup Elements for Extensions</span></span>  
 <span data-ttu-id="f99e4-146">A colocação de elementos CodeGroup em um arquivo de política de segurança é importante.</span><span class="sxs-lookup"><span data-stu-id="f99e4-146">The placement of CodeGroup elements in a security policy file is important.</span></span> <span data-ttu-id="f99e4-147">Para as extensões e os assemblies personalizados que você desenvolver, é recomendado colocar grupos de código personalizados logo abaixo da entrada existente para a associação "$CodeGen$/\*" de URL, conforme indicado a seguir:</span><span class="sxs-lookup"><span data-stu-id="f99e4-147">For extensions and custom assemblies that you develop, it is recommended that you place your custom code groups directly below the existing entry for the URL membership "$CodeGen$/\*", as indicated by the following:</span></span>  
  
```  
<CodeGroup  
    class="UnionCodeGroup"  
    version="1"  
    PermissionSetName="FullTrust">  
    <IMembershipCondition   
        class="UrlMembershipCondition"  
        version="1"  
        Url="$CodeGen$/*"  
    />  
</CodeGroup>  
<CodeGroup   
    class="UnionCodeGroup"  
    version="1"  
    PermissionSetName="FullTrust"  
    Name="MyCustomCodeGroup"  
    Description="Code group for my custom extension">  
        <IMembershipCondition class="UrlMembershipCondition"  
        version="1"  
        Url="C:\Program Files\Microsoft SQL Server\MSSQL\Reporting Services\ReportServer\bin\MyAssembly.dll"  
        />  
</CodeGroup>  
```  
  
 <span data-ttu-id="f99e4-148">Grupos de código adicionais podem ser adicionados um depois do outro.</span><span class="sxs-lookup"><span data-stu-id="f99e4-148">Additional code groups can be added one after another.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f99e4-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f99e4-149">See Also</span></span>  
 [<span data-ttu-id="f99e4-150">Compreender as políticas de segurança</span><span class="sxs-lookup"><span data-stu-id="f99e4-150">Understanding Security Policies</span></span>](understanding-security-policies.md)  
  
  