---
title: Configurar a autenticação personalizada ou de formulários no servidor de relatório | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Forms authentication, configuring
- custom authentication [Reporting Services]
ms.assetid: e8601a8f-e66d-4649-8e4d-a46ca20ec7d0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1447e1e695f0e59dbc07b7e19f4df335a1220a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571269"
---
# <a name="configure-custom-or-forms-authentication-on-the-report-server"></a><span data-ttu-id="15d70-102">Configurar autenticação personalizada ou de formulários no servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="15d70-102">Configure Custom or Forms Authentication on the Report Server</span></span>
  <span data-ttu-id="15d70-103">O Reporting Services fornece uma arquitetura extensível que lhe permite conectar módulos de autenticação personalizados ou baseados em formulários.</span><span class="sxs-lookup"><span data-stu-id="15d70-103">Reporting Services provides an extensible architecture that allows you to plug in custom or forms-based authentication modules.</span></span> <span data-ttu-id="15d70-104">Você poderá avaliar a possibilidade de implementar uma extensão de autenticação personalizada, caso os requisitos de implantação não incluam a segurança integrada do Windows ou a autenticação Básica.</span><span class="sxs-lookup"><span data-stu-id="15d70-104">You might consider implementing a custom authentication extension if deployment requirements do not include Windows integrated security or Basic authentication.</span></span> <span data-ttu-id="15d70-105">O cenário mais comum para uso da autenticação personalizada é no suporte ao acesso de Internet ou extranet para um aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="15d70-105">The most common scenario for using custom authentication is to support Internet or extranet access to a Web application.</span></span> <span data-ttu-id="15d70-106">Substituir a extensão de Autenticação do Windows padrão por uma extensão de personalizada proporciona a você mais controle sobre a forma como é concedido a usuários externos acesso ao servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="15d70-106">Replacing the default Windows Authentication extension with a custom authentication extension gives you more control over how external users are granted access to the report server.</span></span>  
  
 <span data-ttu-id="15d70-107">Na prática, a implantação de uma extensão de autenticação personalizada requer várias etapas que incluem a cópia de assemblies e arquivos de aplicativo, a modificação de arquivos de configuração e teste.</span><span class="sxs-lookup"><span data-stu-id="15d70-107">In practice, deploying a custom authentication extension requires multiple steps that include copying assemblies and application files, modifying configuration files, and testing.</span></span> <span data-ttu-id="15d70-108">Este tópico se concentra apenas nas configurações de autenticação que você especifica nos arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="15d70-108">This topic focuses on just the authentication settings that you specify in the configuration files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15d70-109">A criação de uma extensão de autenticação personalizada requer código personalizado e experiência em segurança [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15d70-109">Creating a custom authentication extension requires custom code and expertise in [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] security.</span></span> <span data-ttu-id="15d70-110">Se você não quiser criar uma extensão de autenticação personalizada, poderá usar grupos e contas do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory, mas deverá reduzir significativamente o escopo de uma implantação de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="15d70-110">If you do not want to create a custom authentication extension, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory groups and accounts, but you should greatly reduce the scope of a report server deployment.</span></span> <span data-ttu-id="15d70-111">Para obter mais informações sobre a autenticação personalizada, consulte [Implementando uma extensão de segurança](../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="15d70-111">For more information about custom authentication, see [Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
 <span data-ttu-id="15d70-112">Além disso, se você desejar usar a autenticação de formulários ou uma extensão de autenticação personalizada em um ambiente do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] integrado a um produto do SharePoint, deverá configurar o site do SharePoint para usar o método de autenticação que escolher.</span><span class="sxs-lookup"><span data-stu-id="15d70-112">Additionally, if you want to use Forms authentication or a custom authentication extension in a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] environment that is integrated with a SharePoint product, you must configure the SharePoint site to use the authentication method that you choose.</span></span> <span data-ttu-id="15d70-113">Para obter mais informações sobre como configurar a autenticação no SharePoint, consulte [Amostras de autenticação](https://go.microsoft.com/fwlink/?LinkId=115575) no [!INCLUDE[msCoName](../../includes/msconame-md.md)] Developer Network (MSDN).</span><span class="sxs-lookup"><span data-stu-id="15d70-113">For more information about configuring authentication in SharePoint, see [Authentication Samples](https://go.microsoft.com/fwlink/?LinkId=115575) on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Developer Network (MSDN).</span></span>  
  
### <a name="to-configure-a-report-server-to-use-custom-authentication"></a><span data-ttu-id="15d70-114">Para configurar um servidor de relatório para usar a autenticação personalizada</span><span class="sxs-lookup"><span data-stu-id="15d70-114">To configure a report server to use Custom authentication</span></span>  
  
1.  <span data-ttu-id="15d70-115">Abra o RSReportServer.config em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="15d70-115">Open RSReportServer.config in a text editor.</span></span>  
  
2.  <span data-ttu-id="15d70-116">Localizar <`Authentication`>.</span><span class="sxs-lookup"><span data-stu-id="15d70-116">Find <`Authentication`>.</span></span>  
  
3.  <span data-ttu-id="15d70-117">Copie a seguinte estrutura XML:</span><span class="sxs-lookup"><span data-stu-id="15d70-117">Copy the following XML structure:</span></span>  
  
    ```  
    <Authentication>  
          <AuthenticationTypes>  
                 <Custom />  
          </AuthenticationTypes>  
          <EnableAuthPersistence>true</EnableAuthPersistence>  
    </Authentication>  
    ```  
  
4.  <span data-ttu-id="15d70-118">Cole-o nas entradas existentes para <`Authentication`>.</span><span class="sxs-lookup"><span data-stu-id="15d70-118">Paste it over the existing entries for <`Authentication`>.</span></span>  
  
     <span data-ttu-id="15d70-119">Observe que não é possível usar `Custom` com outros tipos de autenticação.</span><span class="sxs-lookup"><span data-stu-id="15d70-119">Note that you cannot use `Custom` with other authentication types.</span></span>  
  
5.  <span data-ttu-id="15d70-120">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="15d70-120">Save the file.</span></span>  
  
6.  <span data-ttu-id="15d70-121">Abra o arquivo Web.config do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="15d70-121">Open the Web.config file for the report server.</span></span> <span data-ttu-id="15d70-122">Por padrão, ele está localizado em \Arquivos de Programas\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="15d70-122">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer.</span></span>  
  
7.  <span data-ttu-id="15d70-123">Localize `authentication mode` e defina-o `Forms` .</span><span class="sxs-lookup"><span data-stu-id="15d70-123">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
8.  <span data-ttu-id="15d70-124">Localize `identity impersonate` e defina-o como `False`.</span><span class="sxs-lookup"><span data-stu-id="15d70-124">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
9. <span data-ttu-id="15d70-125">Abra o arquivo Web.config para o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="15d70-125">Open the Web.config file for Report Manager.</span></span> <span data-ttu-id="15d70-126">Por padrão, ele está localizado em \Arquivos de Programas\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager.</span><span class="sxs-lookup"><span data-stu-id="15d70-126">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager.</span></span>  
  
10. <span data-ttu-id="15d70-127">Localize `authentication mode` e defina-o `Forms` .</span><span class="sxs-lookup"><span data-stu-id="15d70-127">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
11. <span data-ttu-id="15d70-128">Localize `identity impersonate` e defina-o como `False`.</span><span class="sxs-lookup"><span data-stu-id="15d70-128">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
12. <span data-ttu-id="15d70-129">Adicione a estrutura de elementos `PassThroughCookies` ao arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="15d70-129">Add the `PassThroughCookies` element structure to the configuration file.</span></span> <span data-ttu-id="15d70-130">Para obter mais informações, consulte [Configurar o Gerenciador de Relatórios para transmitir cookies de autenticação personalizados](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span><span class="sxs-lookup"><span data-stu-id="15d70-130">For more information, see [Configure Report Manager to Pass Custom Authentication Cookies](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span></span>  
  
13. <span data-ttu-id="15d70-131">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="15d70-131">Save the file.</span></span>  
  
14. <span data-ttu-id="15d70-132">Se você configurou uma implantação em expansão, repita todas as etapas anteriores para outros servidores de relatório na implantação.</span><span class="sxs-lookup"><span data-stu-id="15d70-132">If you configured a scale-out deployment, repeat all of the previous steps for other report servers in the deployment.</span></span>  
  
15. <span data-ttu-id="15d70-133">Reinicie o servidor de relatório para terminar as sessões que estão atualmente abertas.</span><span class="sxs-lookup"><span data-stu-id="15d70-133">Restart the report server to clear any sessions that are currently open.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15d70-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15d70-134">See Also</span></span>  
 <span data-ttu-id="15d70-135">[Implementando uma extensão de segurança](../extensions/security-extension/implementing-a-security-extension.md) </span><span class="sxs-lookup"><span data-stu-id="15d70-135">[Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md) </span></span>  
 <span data-ttu-id="15d70-136">[Autenticação com o servidor de relatório](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="15d70-136">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="15d70-137">[Arquivo de configuração RSReportServer](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="15d70-137">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="15d70-138">[Configurar a autenticação básica no servidor de relatório](configure-basic-authentication-on-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="15d70-138">[Configure Basic Authentication on the Report Server](configure-basic-authentication-on-the-report-server.md) </span></span>  
 [<span data-ttu-id="15d70-139">Configurar a Autenticação do Windows no servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="15d70-139">Configure Windows Authentication on the Report Server</span></span>](configure-windows-authentication-on-the-report-server.md)  
  
  
