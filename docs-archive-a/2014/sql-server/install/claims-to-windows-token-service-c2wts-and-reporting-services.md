---
title: Declarações para serviço de token do Windows (C2WTS) e Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/25/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- c2wts.exe.config
- SharePoint mode
- C2WTS
- WSS_WPG
ms.assetid: 4d380509-deed-4b4b-a9c1-a9134cc40641
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: cf2e245dfae17556bdb906c134ba0d53898a8631
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573513"
---
# <a name="claims-to-windows-token-service-c2wts-and-reporting-services"></a><span data-ttu-id="83466-102">Claims to Windows Token Service (C2WTS) e Reporting Services</span><span class="sxs-lookup"><span data-stu-id="83466-102">Claims to Windows Token Service (C2WTS) and Reporting Services</span></span>
  <span data-ttu-id="83466-103">The SharePoint Claims to Windows Token Service (c2WTS) is required with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] se você desejar usar a autenticação do Windows para Fontes de Dados que estão fora do farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="83466-103">The SharePoint Claims to Windows Token Service (c2WTS) is required with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode if you want to use windows authentication for Data Sources that are outside the SharePoint farm.</span></span> <span data-ttu-id="83466-104">Isso ocorre mesmo quando o usuário acessa as fontes de dados com a Autenticação do Windows porque a comunicação entre o WFE (front-end da Web) e o serviço compartilhado do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sempre será uma autenticação de Reivindicações.</span><span class="sxs-lookup"><span data-stu-id="83466-104">This is true even if the user accesses the data sources with Windows Authentication because the communication between the web front-end (WFE) and the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service will always be Claims authentication.</span></span>  
  
 <span data-ttu-id="83466-105">O c2WTS é necessário até mesmo quando as fontes de dados estão no mesmo computador que o serviço compartilhado.</span><span class="sxs-lookup"><span data-stu-id="83466-105">c2WTS is needed even if your data source(s) are on the same computer as the shared service.</span></span> <span data-ttu-id="83466-106">Entretanto, neste cenário, a delegação restrita não é necessária.</span><span class="sxs-lookup"><span data-stu-id="83466-106">However in this scenario, constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="83466-107">Os tokens criados por c2WTS só funcionarão com a delegação restrita (restrições a serviços específicos) e a opção de configuração "usando qualquer protocolo de autenticação".</span><span class="sxs-lookup"><span data-stu-id="83466-107">The tokens created by c2WTS will only work with constrained delegation (constrains to specific services) and the configuration option "using any authentication protocol".</span></span> <span data-ttu-id="83466-108">Conforme observado anteriormente, se suas fontes de dados estiverem no mesmo computador que o serviço compartilhado, a delegação restrita não será necessária.</span><span class="sxs-lookup"><span data-stu-id="83466-108">As noted earlier, if your data sources are on the same computer as the shared service, then constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="83466-109">Se seu ambiente usar a delegação restrita de Kerberos, o serviço do SharePoint Server e as fontes de dados externas precisarão residir no mesmo domínio do Windows.</span><span class="sxs-lookup"><span data-stu-id="83466-109">If your environment will use Kerberos constrained delegation, then the SharePoint Server service and external data sources need to reside in the same Windows domain.</span></span> <span data-ttu-id="83466-110">Qualquer serviço que dependa do c2WTS (Declarações para Serviço de Token do Windows) deve usar a delegação **restrita** Kerberos para permitir que o c2WTS use a transição do protocolo Kerberos para traduzir declarações em credenciais do Windows.</span><span class="sxs-lookup"><span data-stu-id="83466-110">Any service that relies on the Claims to Windows token service (c2WTS) must use Kerberos **constrained** delegation to allow c2WTS to use Kerberos protocol transition to translate claims into Windows credentials.</span></span> <span data-ttu-id="83466-111">Estes requisitos são verdadeiros para todos os Serviços Compartilhados do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="83466-111">These requirements are true for all SharePoint Shared Services.</span></span> <span data-ttu-id="83466-112">Para obter mais informações, consulte [visão geral da autenticação Kerberos para produtos do Microsoft https://technet.microsoft.com/library/gg502594.aspx) SharePoint 2010 (](https://technet.microsoft.com/library/gg502594.aspx).</span><span class="sxs-lookup"><span data-stu-id="83466-112">For more information, see [Overview of Kerberos authentication for Microsoft SharePoint 2010 Products  (https://technet.microsoft.com/library/gg502594.aspx)](https://technet.microsoft.com/library/gg502594.aspx).</span></span>  
  
 <span data-ttu-id="83466-113">O procedimento é resumido neste tópico.</span><span class="sxs-lookup"><span data-stu-id="83466-113">The procedure is summarized in this topic.</span></span>  
  
||  
|-|  
|<span data-ttu-id="83466-114">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="83466-114">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="83466-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="83466-115">Prerequisites</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83466-116">Nota: Algumas das etapas de configuração podem mudar ou não funcionar em certas topologias de farm.</span><span class="sxs-lookup"><span data-stu-id="83466-116">Note: Some of the configuration steps may change, or may not work in certain farm topologies.</span></span> <span data-ttu-id="83466-117">Por exemplo, uma única instalação de servidor não oferece suporte aos serviços Windows Identity Foundation c2WTS; portanto, cenários de delegação de declarações para token do windows não são possíveis com esta configuração de farm.</span><span class="sxs-lookup"><span data-stu-id="83466-117">For instance, a single server install does not support the Windows Identity Foundation c2WTS services so claims to windows token delegation scenarios are not possible with this farm configuration.</span></span>  
  
### <a name="basic-steps-needed-to-configure-c2wts"></a><span data-ttu-id="83466-118">Etapas básicas necessárias para configurar o c2WTS</span><span class="sxs-lookup"><span data-stu-id="83466-118">Basic steps needed to configure c2WTS</span></span>  
  
1.  <span data-ttu-id="83466-119">Configure a conta de serviço do c2WTS.</span><span class="sxs-lookup"><span data-stu-id="83466-119">Configure the c2WTS service account.</span></span> <span data-ttu-id="83466-120">Adicione a conta de serviço ao grupo de Administradores local em cada servidor de aplicativos executando c2WTS.</span><span class="sxs-lookup"><span data-stu-id="83466-120">Add the service account to the local Administrators group on each application server running c2WTS.</span></span> <span data-ttu-id="83466-121">Além disso, verifique se a conta tem os seguintes direitos de política de segurança local:</span><span class="sxs-lookup"><span data-stu-id="83466-121">In addition, verify that the account has the following local security policy rights:</span></span>  
  
    -   <span data-ttu-id="83466-122">Atuar como parte do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="83466-122">Act as part of the operating system</span></span>  
  
    -   <span data-ttu-id="83466-123">Representar um cliente após a autenticação</span><span class="sxs-lookup"><span data-stu-id="83466-123">Impersonate a client after authentication</span></span>  
  
    -   <span data-ttu-id="83466-124">Fazer logon como um serviço</span><span class="sxs-lookup"><span data-stu-id="83466-124">Log on as a service</span></span>  
  
     <span data-ttu-id="83466-125">A conta que você usa para C2WTS também precisa ser configurada para Delegação Restrita com Protocolo que Faz a transição e precisa de permissões para delegar aos Serviços com os quais ela precisa se comunicar (isto é, mecanismo SQL Server, SQL Server Analysis Services). Para configurar a delegação, você pode usar o snap-in do computador de usuários do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="83466-125">The account you use for c2WTS also needs to be configured for Constrained Delegation with Protocol Transitioning and needs permissions to delegate to the Services it is required to communicate with (i.e. SQL Server Engine, SQL Server Analysis Services).To configure delegation you can use the Active Directory Users and Computer snap-in.</span></span>  
  
    1.  <span data-ttu-id="83466-126">Clique com o botão direito do mouse em cada conta de serviço e abra a caixa de diálogo de propriedades.</span><span class="sxs-lookup"><span data-stu-id="83466-126">Right-click each service account and open the properties dialog.</span></span> <span data-ttu-id="83466-127">Na caixa de diálogo, clique na guia **Delegação** .</span><span class="sxs-lookup"><span data-stu-id="83466-127">In the dialog click the **Delegation** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="83466-128">Nota: a guia delegação só ficará visível se o objeto tiver um SPN atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="83466-128">Note: the delegation tab is only visible if the object has an SPN assigned to it.</span></span> <span data-ttu-id="83466-129">o c2WTS não requer um SPN na conta do c2WTS, no entanto, sem um SPN, a guia **delegação** não estará visível.</span><span class="sxs-lookup"><span data-stu-id="83466-129">c2WTS does not require an SPN on the c2WTS Account, however, without an SPN, the **Delegation** tab will not be visible.</span></span> <span data-ttu-id="83466-130">Um modo alternativo de configurar a delegação restrita é usar um utilitário como **ADSIEdit**.</span><span class="sxs-lookup"><span data-stu-id="83466-130">An alternative way to configure constrained delegation is to use a utility such as **ADSIEdit**.</span></span>  
  
    2.  <span data-ttu-id="83466-131">Principais opções de configuração na guia delegação:</span><span class="sxs-lookup"><span data-stu-id="83466-131">Key configuration options on the delegation tab are the following:</span></span>  
  
        -   <span data-ttu-id="83466-132">Selecione "confiar neste usuário para delegação apenas aos serviços especificados"</span><span class="sxs-lookup"><span data-stu-id="83466-132">Select "Trust this user for delegation to specified services only"</span></span>  
  
        -   <span data-ttu-id="83466-133">Selecione "usar qualquer protocolo de autenticação"</span><span class="sxs-lookup"><span data-stu-id="83466-133">Select "Use any authentication protocol"</span></span>  
  
         <span data-ttu-id="83466-134">Para obter mais informações, consulte a seção "configurar a delegação restrita de Kerberos para computadores e contas de serviço" do seguinte white paper, [Configurando a autenticação Kerberos para produtos SharePoint 2010 e SQL Server 2008 R2](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products)</span><span class="sxs-lookup"><span data-stu-id="83466-134">For more information, see the "configure Kerberos constrained delegation for computers and service accounts" section of the following white paper, [Configuring Kerberos authentication for SharePoint 2010 and SQL Server 2008 R2 products](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products)</span></span>  
  
2.  <span data-ttu-id="83466-135">Configurar o c2WTS ' AllowedCallers '</span><span class="sxs-lookup"><span data-stu-id="83466-135">Configure c2WTS 'AllowedCallers'</span></span>  
  
     <span data-ttu-id="83466-136">c2WTS requer que as identidades dos "chamadores" sejam explicitamente listadas no arquivo de configuração, **c2wtshost.exe.config**. o c2WTS não aceita solicitações de todos os usuários autenticados no sistema, a menos que esteja configurado para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="83466-136">c2WTS requires the 'callers' identities explicitly listed in the configuration file, **c2wtshost.exe.config**. c2WTS does not accept requests from all authenticated users in the system unless it is configured to do so.</span></span> <span data-ttu-id="83466-137">Neste caso, o “chamador” é o grupo WSS_WPG do Windows.</span><span class="sxs-lookup"><span data-stu-id="83466-137">In this case the 'caller' is the WSS_WPG Windows group.</span></span> <span data-ttu-id="83466-138">O arquivo c2wtshost.exe.confi é salvo no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="83466-138">The c2wtshost.exe.confi file is saved in the following location:</span></span>  
  
     <span data-ttu-id="83466-139">**\Arquivos de Programas\windows Identity Foundation\v3.5\c2wtshost.exe.config**</span><span class="sxs-lookup"><span data-stu-id="83466-139">**\Program Files\Windows Identity Foundation\v3.5\c2wtshost.exe.config**</span></span>  
  
     <span data-ttu-id="83466-140">Este é um exemplo do arquivo de configuração:</span><span class="sxs-lookup"><span data-stu-id="83466-140">The following is an example of the configuration file:</span></span>  
  
    ```  
    <configuration>  
      <windowsTokenService>  
        <!--  
            By default no callers are allowed to use the Windows Identity Foundation Claims To NT Token Service.  
            Add the identities you wish to allow below.  
          -->  
        <allowedCallers>  
          <clear/>  
          <add value="WSS_WPG" />  
        </allowedCallers>  
      </windowsTokenService>  
    </configuration>  
    ```  
  
3.  <span data-ttu-id="83466-141">Inicie o serviço C2WTS do sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="83466-141">Start the operating system c2WTS service:</span></span>  
  
    1.  <span data-ttu-id="83466-142">Configure o serviço para usar a conta de serviço configurada na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="83466-142">Configure the service to use the service account you configured in the previous step.</span></span>  
  
    2.  <span data-ttu-id="83466-143">Altere o tipo de inicialização para "**automático**" e inicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="83466-143">Change the Startup type to "**Automatic**" and start the service.</span></span>  
  
4.  <span data-ttu-id="83466-144">Inicie o SharePoint ' claims to Windows token Service ': Inicie o claims to Windows token Service por meio da administração central do SharePoint na página **gerenciar serviços no servidor** .</span><span class="sxs-lookup"><span data-stu-id="83466-144">Start the SharePoint 'Claims to Windows Token Service': Start the Claims to Windows Token Service through SharePoint Central Administration on the **Manage Services on Server** page.</span></span> <span data-ttu-id="83466-145">O serviço deverá ser iniciado no servidor que estará executando a ação.</span><span class="sxs-lookup"><span data-stu-id="83466-145">The service should be started on the server that will be performing the action.</span></span> <span data-ttu-id="83466-146">Por exemplo, se você tiver um servidor que é um WFE e outro servidor que é um Servidor de aplicativos com o serviço compartilhado do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service running, you only need to start c2WTS on the Application Server.</span><span class="sxs-lookup"><span data-stu-id="83466-146">For example if you have a server that is a WFE and another server that is an Application Server that has the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service running, you only need to start c2WTS on the Application Server.</span></span> <span data-ttu-id="83466-147">O c2WTS não é necessário no WFE.</span><span class="sxs-lookup"><span data-stu-id="83466-147">c2WTS is not needed on the WFE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83466-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83466-148">See Also</span></span>  
 <span data-ttu-id="83466-149">[Visão geral do claims to Windows token Service (c2WTS) (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span><span class="sxs-lookup"><span data-stu-id="83466-149">[Claims to Windows Token Service (c2WTS) Overview (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span></span>  
 [<span data-ttu-id="83466-150">Visão geral da autenticação Kerberos para produtos do Microsoft SharePoint 2010 (https://technet.microsoft.com/library/gg502594.aspx)</span><span class="sxs-lookup"><span data-stu-id="83466-150">Overview of Kerberos authentication for Microsoft SharePoint 2010 Products (https://technet.microsoft.com/library/gg502594.aspx)</span></span>](https://technet.microsoft.com/library/gg502594.aspx)  
  
