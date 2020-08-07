---
title: Configurar um servidor de relatório para entrega de email (SSRS Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], distributing
- report servers [Reporting Services], e-mail delivery
- remote SMTP service [Reporting Services]
- distributing reports [Reporting Services], e-mail
- CDO
- Collaboration Data Objects
- SMTP settings [Reporting Services]
- e-mail [Reporting Services]
- sending reports
- mail [Reporting Services]
- local SMTP service [Reporting Services]
ms.assetid: b838f970-d11a-4239-b164-8d11f4581d83
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3122dbbb5debc90afa73ca0f8ab0d8e23d38a0ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575567"
---
# <a name="configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager"></a><span data-ttu-id="2f3de-102">Configurar um servidor de relatório para entrega de email (Gerenciador de Configurações do SSRS)</span><span class="sxs-lookup"><span data-stu-id="2f3de-102">Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)</span></span>


  <span data-ttu-id="2f3de-103">O [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] inclui uma extensão de entrega de email, para que você possa distribuir relatórios por email.</span><span class="sxs-lookup"><span data-stu-id="2f3de-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] includes an e-mail delivery extension so that you can distribute reports through e-mail.</span></span> <span data-ttu-id="2f3de-104">Dependendo de como você definir a assinatura de email, uma entrega pode consistir em uma notificação, um link, um anexo ou um relatório inserido.</span><span class="sxs-lookup"><span data-stu-id="2f3de-104">Depending on how you define the e-mail subscription, a delivery might consist of a notification, link, attachment, or embedded report.</span></span> <span data-ttu-id="2f3de-105">A extensão de entrega de email funciona com sua tecnologia de servidor de email existente.</span><span class="sxs-lookup"><span data-stu-id="2f3de-105">The e-mail delivery extension works with your existing mail server technology.</span></span> <span data-ttu-id="2f3de-106">O servidor de email deve ser um encaminhador ou servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-106">The mail server must be an SMTP server or forwarder.</span></span> <span data-ttu-id="2f3de-107">O servidor de relatório se conecta a um servidor SMTP por meio de bibliotecas (cdosys.dll) de CDO (Collaboration Data Objects) que são fornecidas pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2f3de-107">The report server connects to an SMTP server through Collaboration Data Objects (CDO) libraries (cdosys.dll) that are provided by the operating system.</span></span>  
  
 <span data-ttu-id="2f3de-108">A extensão de entrega de email do servidor de relatório não é configurada por padrão.</span><span class="sxs-lookup"><span data-stu-id="2f3de-108">The report server e-mail delivery extension is not configured by default.</span></span> <span data-ttu-id="2f3de-109">Você deve usar o Gerenciador de Configurações do Reporting Services para configurar a extensão de forma mínima.</span><span class="sxs-lookup"><span data-stu-id="2f3de-109">You must use the Reporting Services Configuration Manager to minimally configure the extension.</span></span> <span data-ttu-id="2f3de-110">Para definir propriedades avançadas, você deve editar o arquivo `RSReportServer.config` .</span><span class="sxs-lookup"><span data-stu-id="2f3de-110">To set advanced properties, you must edit the `RSReportServer.config` file.</span></span> <span data-ttu-id="2f3de-111">Se não for possível configurar o servidor de relatório para usar essa extensão, em vez disso você poderá entregar relatórios para uma pasta compartilhada.</span><span class="sxs-lookup"><span data-stu-id="2f3de-111">If you cannot configure the report server to use this extension, you can deliver reports to a shared folder instead.</span></span> <span data-ttu-id="2f3de-112">Para obter mais informações, consulte [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2f3de-112">For more information, see [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="2f3de-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo</span><span class="sxs-lookup"><span data-stu-id="2f3de-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 
  
##  <a name="configuration-requirements"></a><a name="bkmk_configuration_requirements"></a><span data-ttu-id="2f3de-114">Requisitos de configuração</span><span class="sxs-lookup"><span data-stu-id="2f3de-114">Configuration Requirements</span></span>  
  
-   <span data-ttu-id="2f3de-115">A entrega de email do servidor de relatório é implementada em CDO (Collaboration Data Objects) e requer um servidor SMTP local ou remoto ou um encaminhador SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-115">Report server e-mail delivery is implemented on Collaboration Data Objects (CDO) and requires a local or remote Simple Mail Transfer Protocol (SMTP) server or SMTP forwarder.</span></span> <span data-ttu-id="2f3de-116">Não há suporte ao SMTP em todos os sistemas operacionais Windows.</span><span class="sxs-lookup"><span data-stu-id="2f3de-116">SMTP is not supported on all Windows operating systems.</span></span> <span data-ttu-id="2f3de-117">Se você estiver usando a edição com base em Itanium do Windows Server 2008, não haverá suporte ao SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-117">If you are using the Itanium-based edition of Windows Server 2008, SMTP is not supported.</span></span> <span data-ttu-id="2f3de-118">Para obter mais informações sobre as opções de configuração fornecidas por CDO, consulte [Configuration CoClass](https://go.microsoft.com/fwlink/?LinkId=98237) (em inglês) no MSDN.</span><span class="sxs-lookup"><span data-stu-id="2f3de-118">For more information about configuration options provided through CDO, see [Configuration CoClass](https://go.microsoft.com/fwlink/?LinkId=98237) on MSDN.</span></span>  
  
-   <span data-ttu-id="2f3de-119">Uma conta de serviço do Servidor de Relatório deve ter permissão no servidor SMTP para enviar email.</span><span class="sxs-lookup"><span data-stu-id="2f3de-119">The Report Server service account must have permission on the SMTP server to send mail.</span></span>  
  
-   <span data-ttu-id="2f3de-120">A extensão de entrega de email usa a codificação UTF-8 em anexos de email.</span><span class="sxs-lookup"><span data-stu-id="2f3de-120">The e-mail delivery extension uses UTF-8 encoding in e-mail attachments.</span></span> <span data-ttu-id="2f3de-121">Você não pode modificar a codificação; a extensão de renderização HTML só dá suporte a UTF-8.</span><span class="sxs-lookup"><span data-stu-id="2f3de-121">You cannot modify the encoding; the HTML rendering extension only supports UTF-8.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f3de-122">A extensão de entrega de email padrão não dá suporte para assinar digitalmente ou criptografar mensagens de email de saída.</span><span class="sxs-lookup"><span data-stu-id="2f3de-122">The default e-mail delivery extension does not provide support for digitally signing or encrypting outgoing mail messages.</span></span>  
  
 
  
##  <a name="configuring-a-report-server-for-local-or-remote-smtp-service"></a><a name="bkmk_configure_for_local_or_remote_SMTP"></a><span data-ttu-id="2f3de-123">Configurando um servidor de relatório para o serviço SMTP local ou remoto</span><span class="sxs-lookup"><span data-stu-id="2f3de-123">Configuring a Report Server for Local or Remote SMTP Service</span></span>  
 <span data-ttu-id="2f3de-124">Você pode usar um serviço SMTP local ou um encaminhador ou servidor SMTP remoto para suportar entrega de email.</span><span class="sxs-lookup"><span data-stu-id="2f3de-124">You can use a local SMTP service or a remote SMTP server or forwarder to support e-mail delivery.</span></span> <span data-ttu-id="2f3de-125">Se tiver acesso a um servidor SMTP remoto existente, você deverá considerar seu uso.</span><span class="sxs-lookup"><span data-stu-id="2f3de-125">If you have access to an existing remote SMTP server, you should consider using it.</span></span> <span data-ttu-id="2f3de-126">Se não houver nenhum servidor SMTP disponível ou se subsequentemente você encontrar erros de entrega de relatório que possam ser atribuídos a falhas de conexão do computador, você deverá alternar para o uso de um serviço SMTP local.</span><span class="sxs-lookup"><span data-stu-id="2f3de-126">If there is no SMTP server available or if you subsequently encounter report delivery errors that can be attributed to computer connection failures, you should switch to using a local SMTP service.</span></span> <span data-ttu-id="2f3de-127">Detalhes sobre como configurar um servidor de relatório para serviço local ou remoto são fornecidos mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2f3de-127">Details about how to configure a report server for local or remote service are provided further on in this topic.</span></span>  
  
  
  
##  <a name="setting-configuration-options-for-e-mail-delivery"></a><a name="bkmk_setting_email_delivery"></a><span data-ttu-id="2f3de-128">Definindo opções de configuração para entrega de email</span><span class="sxs-lookup"><span data-stu-id="2f3de-128">Setting Configuration Options for E-Mail Delivery</span></span>  
 <span data-ttu-id="2f3de-129">Antes de usar a entrega de email do Servidor de Relatório, você deve definir valores de configuração que forneçam informações sobre qual servidor SMTP será usado.</span><span class="sxs-lookup"><span data-stu-id="2f3de-129">Before you can use Report Server e-mail delivery, you must set configuration values that provide information about which SMTP server to use.</span></span>  
  
 <span data-ttu-id="2f3de-130">Para configurar um servidor de relatório para entrega de email, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2f3de-130">To configure a report server for e-mail delivery, do the following:</span></span>  
  
-   <span data-ttu-id="2f3de-131">Use o Gerenciador de Configurações do Reporting Services se estiver especificando somente um servidor SMTP e uma conta de usuário que tenha permissão para enviar email.</span><span class="sxs-lookup"><span data-stu-id="2f3de-131">Use the Reporting Services Configuration Manager if you are specifying just an SMTP server and a user account that has permission to send e-mail.</span></span> <span data-ttu-id="2f3de-132">Essas são as configurações mínimas necessárias para a configuração da extensão de entrega de email do Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="2f3de-132">These are the minimum settings that are required for configuring the Report Server e-mail delivery extension.</span></span> <span data-ttu-id="2f3de-133">Para obter mais informações, consulte [configurações de email-Configuration Manager &#40;modo nativo do SSRS&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) e [entrega de email no Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2f3de-133">For more information, see [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) and [E-Mail Delivery in Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="2f3de-134">(Opcionalmente) Use um editor de texto para especificar configurações adicionais no arquivo RSreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="2f3de-134">(Optionally) Use a text editor to specify additional settings in the RSreportserver.config file.</span></span> <span data-ttu-id="2f3de-135">Esse arquivo contém todos os parâmetros de configuração para a entrega de email do Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="2f3de-135">This file contains all of the configuration settings for Report Server e-mail delivery.</span></span> <span data-ttu-id="2f3de-136">Será necessário especificar configurações adicionais nesses arquivos se você estiver usando um servidor SMTP local ou se estiver restringindo a entrega de email para hosts específicos.</span><span class="sxs-lookup"><span data-stu-id="2f3de-136">Specifying additional settings in these files is required if you are using a local SMTP server or if you are restricting e-mail delivery to specific hosts.</span></span> <span data-ttu-id="2f3de-137">Para obter mais informações sobre como localizar e modificar arquivos de configuração, consulte [modificar um arquivo de configuração de Reporting Services &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) em manuais online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2f3de-137">For more information about finding and modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f3de-138">As configurações de email do servidor de relatório têm como base o CDO.</span><span class="sxs-lookup"><span data-stu-id="2f3de-138">Report server e-mail settings are based on CDO.</span></span> <span data-ttu-id="2f3de-139">Para obter mais detalhes sobre configurações específicas, você pode consultar a documentação de produção do CDO.</span><span class="sxs-lookup"><span data-stu-id="2f3de-139">If you want more detail about specific settings, you can refer to the CDO production documentation.</span></span>  
  

  
##  <a name="example-report-server-e-mail-configuration"></a><a name="bkmk_example_config_file"></a><span data-ttu-id="2f3de-140">Exemplo de configuração de email do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="2f3de-140">Example Report Server E-Mail Configuration</span></span>  
 <span data-ttu-id="2f3de-141">O exemplo a seguir ilustra as configurações no arquivo RSreportserver.config para um servidor SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="2f3de-141">The following example illustrates the settings in the RSreportserver.config file for a remote SMTP server.</span></span> <span data-ttu-id="2f3de-142">Par ler sobre as descrições de configuração e valores válidos, consulte [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onlnos Manuais Online doe or the CDO product documentation.</span><span class="sxs-lookup"><span data-stu-id="2f3de-142">To read about the setting descriptions and valid values, see [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or the CDO product documentation.</span></span>  
  
```  
<RSEmailDPConfiguration>  
     <SMTPServer>mySMTPServer.Adventure-Works.com</SMTPServer>  
     <SMTPServerPort></SMTPServerPort>  
     <SMTPAccountName></SMTPAccountName>  
     <SMTPConnectionTimeout></SMTPConnectionTimeout>  
     <SMTPServerPickupDirectory></SMTPServerPickupDirectory>  
     <SMTPUseSSL></SMTPUseSSL>  
     <SendUsing>2</SendUsing>  
     <SMTPAuthenticate></SMTPAuthenticate>  
     <From>my-rs-email-account@Adventure-Works.com</From>  
     <EmbeddedRenderFormats>  
          <RenderingExtension>MHTML</RenderingExtension>  
     </EmbeddedRenderFormats>  
     <PrivilegedUserRenderFormats></PrivilegedUserRenderFormats>  
     <ExcludedRenderFormats>  
          <RenderingExtension>HTMLOWC</RenderingExtension>  
          <RenderingExtension>NULL</RenderingExtension>  
     </ExcludedRenderFormats>  
     <SendEmailToUserAlias>True</SendEmailToUserAlias>  
     <DefaultHostName></DefaultHostName>  
     <PermittedHosts>  
          <HostName>Adventure-Works.com</HostName>  
          <HostName>hotmail.com</HostName>  
     </PermittedHosts>  
</RSEmailDPConfiguration>  
```  
  

  
##  <a name="configuration-options-for-setting-the-to-field-in-a-message"></a><a name="bkmk_setting_TO_field"></a><span data-ttu-id="2f3de-143">Opções de configuração para definir o campo para: em uma mensagem</span><span class="sxs-lookup"><span data-stu-id="2f3de-143">Configuration Options for Setting the To: Field in a Message</span></span>  
 <span data-ttu-id="2f3de-144">As assinaturas definidas pelo usuário que são criadas de acordo com as permissões concedidas pela tarefa **gerenciar assinaturas individuais** contêm um nome de usuário predefinido com base na conta de usuário do domínio.</span><span class="sxs-lookup"><span data-stu-id="2f3de-144">User-defined subscriptions that are created according to the permissions granted by the **Manage individual subscriptions** task contain a pre-set user name that is based on the domain user account.</span></span> <span data-ttu-id="2f3de-145">Quando o usuário cria a assinatura, o nome do destinatário no campo **Para:** é endereçado a si mesmo, usando a conta do usuário do domínio da pessoa que está criando a assinatura.</span><span class="sxs-lookup"><span data-stu-id="2f3de-145">When the user creates the subscription, the recipient name in the **To:** field is self-addressed using the domain user account of the person creating the subscription.</span></span>  
  
 <span data-ttu-id="2f3de-146">Se você estiver usando um servidor ou encaminhador SMTP que use contas de email diferentes da conta de usuário do domínio, a entrega do relatório falhará quando o servidor SMTP tentar entregar o relatório para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="2f3de-146">If you are using an SMTP server or forwarder that uses e-mail accounts that are different from the domain user account, the report delivery will fail when the SMTP server tries to deliver the report to that user.</span></span>  
  
 <span data-ttu-id="2f3de-147">Para solucionar esse erro, você pode modificar os parâmetros de configuração que permitem aos usuários inserir um nome no campo **Para:** :</span><span class="sxs-lookup"><span data-stu-id="2f3de-147">To workaround this issue, you can modify configuration settings that allow users to enter a name in the **To:** field:</span></span>  
  
1.  <span data-ttu-id="2f3de-148">Abra RSReportServer.config com um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="2f3de-148">Open RSReportServer.config with a text editor.</span></span>  
  
2.  <span data-ttu-id="2f3de-149">Defina `SendEmailToUserAlias` como `False`.</span><span class="sxs-lookup"><span data-stu-id="2f3de-149">Set `SendEmailToUserAlias` to `False`.</span></span>  
  
3.  <span data-ttu-id="2f3de-150">Defina `DefaultHostName` como o nome DNS (Sistema de Nome de Domínio) ou o endereço IP do servidor ou encaminhador SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-150">Set `DefaultHostName` to the Domain Name System (DNS) name or IP address of the SMTP server or forwarder.</span></span>  
  
4.  <span data-ttu-id="2f3de-151">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f3de-151">Save the file.</span></span>  
  
  
  
##  <a name="configuration-options-for-remote-smtp-service"></a><a name="bkmk_options_remote_SMTP"></a><span data-ttu-id="2f3de-152">Opções de configuração para o serviço SMTP remoto</span><span class="sxs-lookup"><span data-stu-id="2f3de-152">Configuration Options for Remote SMTP Service</span></span>  
 <span data-ttu-id="2f3de-153">A conexão entre o servidor de relatório e um encaminhador ou servidor SMTP é determinada pelos seguintes parâmetros de configuração:</span><span class="sxs-lookup"><span data-stu-id="2f3de-153">The connection between the report server and an SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="2f3de-154">`SendUsing` especifica um método para o envio de mensagens.</span><span class="sxs-lookup"><span data-stu-id="2f3de-154">`SendUsing` specifies a method for sending messages.</span></span> <span data-ttu-id="2f3de-155">Você pode escolher entre um serviço de rede SMTP ou um diretório local de retirada de serviço SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-155">You can choose between a network SMTP service or a local SMTP service pickup directory.</span></span> <span data-ttu-id="2f3de-156">Para usar um serviço SMTP remoto, este valor deve ser definido como **2** no arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="2f3de-156">To use a remote SMTP service, this value must be set to **2** in the RSReportServer.config file.</span></span>  
  
-   <span data-ttu-id="2f3de-157">`SMTPServer` especifica o encaminhador ou servidor SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="2f3de-157">`SMTPServer` specifies the remote SMTP server or forwarder.</span></span> <span data-ttu-id="2f3de-158">Esse valor será necessário se você estiver usando um encaminhador ou servidor SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="2f3de-158">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
-   <span data-ttu-id="2f3de-159">`From` define o valor que aparece na linha **De:** de uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="2f3de-159">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="2f3de-160">Esse valor será necessário se você estiver usando um encaminhador ou servidor SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="2f3de-160">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
 <span data-ttu-id="2f3de-161">Outros valores usados para o serviço SMTP remoto incluem os seguintes (observe que não é necessário especificar esses valores, a menos que deseje substituir os valores padrão).</span><span class="sxs-lookup"><span data-stu-id="2f3de-161">Other values that are used for remote SMTP service include the following (note that you do not need to specify these values unless you want to override the default values).</span></span>  
  
-   <span data-ttu-id="2f3de-162">**SMTPServerPort** é configurado para a porta 25.</span><span class="sxs-lookup"><span data-stu-id="2f3de-162">**SMTPServerPort** is configured for port 25.</span></span>  
  
-   <span data-ttu-id="2f3de-163">**SMTPAuthenticate** especifica como o servidor de relatório se conecta ao servidor SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="2f3de-163">**SMTPAuthenticate** specifies how the report server connects to the remote SMTP server.</span></span> <span data-ttu-id="2f3de-164">O valor padrão é 0 (sem autenticação).</span><span class="sxs-lookup"><span data-stu-id="2f3de-164">The default value is 0 (or no authentication).</span></span> <span data-ttu-id="2f3de-165">Nesse caso, a conexão é feita por acesso Anônimo.</span><span class="sxs-lookup"><span data-stu-id="2f3de-165">In this case, the connection is made through Anonymous access.</span></span> <span data-ttu-id="2f3de-166">Dependendo da configuração do domínio, o servidor de relatório e o servidor SMTP podem precisar ser membros do mesmo domínio.</span><span class="sxs-lookup"><span data-stu-id="2f3de-166">Depending on your domain configuration, the report server and the SMTP server may need to be members of the same domain.</span></span>  
  
     <span data-ttu-id="2f3de-167">Para enviar e-mail para listas de distribuição restritas (por exemplo, listas de distribuição que aceitem mensagens de entrada apenas de contas autenticadas), defina **SMTPAuthenticate** como **2**.</span><span class="sxs-lookup"><span data-stu-id="2f3de-167">To send e-mail to restricted distribution lists (for example, distribution lists that accept incoming messages only from authenticated accounts), set **SMTPAuthenticate** to **2**.</span></span>  
  

  
##  <a name="configuration-options-for-local-smtp-service"></a><a name="bkmk_options_local_SMTP"></a><span data-ttu-id="2f3de-168">Opções de configuração para o serviço SMTP local</span><span class="sxs-lookup"><span data-stu-id="2f3de-168">Configuration Options for Local SMTP Service</span></span>  
 <span data-ttu-id="2f3de-169">A configuração de um serviço SMTP local será útil se você estiver testando ou solucionando problemas de entrega de email do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2f3de-169">Configuring a local SMTP service is useful if you are testing or troubleshooting report server e-mail delivery.</span></span> <span data-ttu-id="2f3de-170">O serviço SMTP local não está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="2f3de-170">The local SMTP service is not enabled by default.</span></span> <span data-ttu-id="2f3de-171">Para obter instruções sobre como habilitá-lo, consulte [configurar um servidor de relatório para entrega de email (SSRS Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) e [configurações de email-Configuration Manager &#40;o modo nativo do SSRS&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2f3de-171">For instructions on how to enable it, see [Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="2f3de-172">A conexão entre o servidor de relatório e um encaminhador ou servidor SMTP local é determinada pelos seguintes parâmetros de configuração:</span><span class="sxs-lookup"><span data-stu-id="2f3de-172">The connection between the report server and a local SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="2f3de-173">`SendUsing` está definido como **1**.</span><span class="sxs-lookup"><span data-stu-id="2f3de-173">`SendUsing` is set to **1**.</span></span>  
  
-   <span data-ttu-id="2f3de-174">**SMTPServerPickupDirectory** é definido como uma pasta na unidade local.</span><span class="sxs-lookup"><span data-stu-id="2f3de-174">**SMTPServerPickupDirectory** is set to a folder on the local drive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f3de-175">Certifique-se de não definir `SMTPServer` se estiver usando um servidor SMTP local.</span><span class="sxs-lookup"><span data-stu-id="2f3de-175">Be sure that you do not set `SMTPServer` if you are using a local SMTP server.</span></span>  
  
-   <span data-ttu-id="2f3de-176">`From` define o valor que aparece na linha **De:** de uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="2f3de-176">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="2f3de-177">Esse valor é necessário.</span><span class="sxs-lookup"><span data-stu-id="2f3de-177">This value is required.</span></span>  
  
 
  
##  <a name="to-configure-report-server-e-mail-using-the-reporting-services-configuration-manager"></a><a name="bkmk_use_configuration_manager"></a><span data-ttu-id="2f3de-178">Para configurar o email do servidor de relatório usando o Gerenciador de Configurações do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2f3de-178">To configure report server e-mail using the Reporting Services Configuration Manager</span></span>  
  
1.  <span data-ttu-id="2f3de-179">Verifique se o serviço do Windows Servidor de Relatório tem permissões `Send As` no servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-179">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="2f3de-180">Inicie o Gerenciador de Configurações do Reporting Services e conecte-se à instância do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2f3de-180">Start the Reporting Services Configuration Manager and connect to the report server instance.</span></span>  
  
3.  <span data-ttu-id="2f3de-181">Na página Configurações de Email, digite o nome do servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-181">On the Email Settings page, enter the name of the SMTP server.</span></span> <span data-ttu-id="2f3de-182">Esse valor pode ser um endereço IP, um nome UNC de um computador em sua intranet corporativa ou um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="2f3de-182">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
4.  <span data-ttu-id="2f3de-183">Em **Endereço do Remetente**, digite o nome uma conta que tenha permissão para enviar email a partir do servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-183">In **Sender Address**, enter the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
5.  <span data-ttu-id="2f3de-184">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2f3de-184">Click **Apply**.</span></span>  
  

  
##  <a name="to-configure-a-remote-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_remote_SMTP"></a><span data-ttu-id="2f3de-185">Para configurar um serviço SMTP remoto para o servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="2f3de-185">To configure a remote SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="2f3de-186">Verifique se o serviço do Windows Servidor de Relatório tem permissões `Send As` no servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-186">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="2f3de-187">Abra o arquivo RSReportServer.config em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="2f3de-187">Open the RSReportServer.config file in a text editor.</span></span>  
  
3.  <span data-ttu-id="2f3de-188">Verifique se <`UrlRoot`> está definido como o endereço da URL do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2f3de-188">Verify that <`UrlRoot`> is set to the report server URL address.</span></span> <span data-ttu-id="2f3de-189">Esse valor é definido quando você configura o servidor de relatório e já deveria estar preenchido.</span><span class="sxs-lookup"><span data-stu-id="2f3de-189">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="2f3de-190">Se não estiver definido, digite o endereço da URL do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2f3de-190">If it is not set, type the report server URL address.</span></span>  
  
4.  <span data-ttu-id="2f3de-191">Na seção entrega, localize <`ReportServerEmail`>.</span><span class="sxs-lookup"><span data-stu-id="2f3de-191">In the Delivery section, find <`ReportServerEmail`>.</span></span>  
  
5.  <span data-ttu-id="2f3de-192">Em <`SMTPServer`>, digite o nome do servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-192">In <`SMTPServer`>, type the name of the SMTP server.</span></span> <span data-ttu-id="2f3de-193">Esse valor pode ser um endereço IP, um nome UNC de um computador em sua intranet corporativa ou um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="2f3de-193">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
6.  <span data-ttu-id="2f3de-194">Verifique se <`SendUsing`> está definido como 2.</span><span class="sxs-lookup"><span data-stu-id="2f3de-194">Verify that <`SendUsing`> is set to 2.</span></span> <span data-ttu-id="2f3de-195">Se estiver definido como outro valor, o servidor de relatório não está configurado para usar um serviço SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="2f3de-195">If it is set another value, the report server is not configured to use a remote SMTP service.</span></span>  
  
7.  <span data-ttu-id="2f3de-196">Em <`From`>, digite o nome uma conta que tenha permissão para enviar email do servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-196">In <`From`>, type the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
8.  <span data-ttu-id="2f3de-197">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f3de-197">Save the file.</span></span>  
  
     <span data-ttu-id="2f3de-198">O servidor de relatório usará as novas configurações automaticamente; você não precisa reiniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="2f3de-198">The report server will use the new settings automatically; you do not need to restart the service.</span></span> <span data-ttu-id="2f3de-199">Você pode especificar configurações adicionais de SMTP para configurar mais como o servidor SMTP é usado para entrega de email do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2f3de-199">You can specify additional SMTP settings to further configure how the SMTP server is used for report server e-mail delivery.</span></span> <span data-ttu-id="2f3de-200">Para obter mais nos Manuais Online doformações, consulte [Configurnos Manuais Online dog a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) e [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onlnos Manuais Online doe.</span><span class="sxs-lookup"><span data-stu-id="2f3de-200">For more information, see [Configuring a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  

  
##  <a name="to-configure-a-local-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_local_SMTP"></a><span data-ttu-id="2f3de-201">Para configurar um serviço SMTP local para o servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="2f3de-201">To configure a local SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="2f3de-202">No Painel de Controle, clique em **Adicionar ou Remover Programas**.</span><span class="sxs-lookup"><span data-stu-id="2f3de-202">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="2f3de-203">Clique em **Adicionar/Remover Componentes do Windows** para iniciar o Assistente de Componentes do Windows.</span><span class="sxs-lookup"><span data-stu-id="2f3de-203">Click **Add/Remove Windows Components** to start the Windows Component Wizard.</span></span>  
  
3.  <span data-ttu-id="2f3de-204">Selecione **Servidor de Aplicativos** e clique em **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="2f3de-204">Select **Application Server** and click **Details**.</span></span>  
  
4.  <span data-ttu-id="2f3de-205">Selecione **Serviços de Informações da Internet (IIS)** e clique em **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="2f3de-205">Select **Internet Information Services (IIS)** and click **Details**.</span></span>  
  
5.  <span data-ttu-id="2f3de-206">Marque a caixa de seleção **Serviço SMTP** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f3de-206">Select the **SMTP Service** checkbox and click **OK**.</span></span>  
  
6.  <span data-ttu-id="2f3de-207">No Assistente de Componentes do Windows, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2f3de-207">On the Windows Component Wizard, click **Next**.</span></span> <span data-ttu-id="2f3de-208">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2f3de-208">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="2f3de-209">Verifique se o serviço está em execução no console **Serviços** .</span><span class="sxs-lookup"><span data-stu-id="2f3de-209">Verify that the service is running in the **Services** console.</span></span>  
  
8.  <span data-ttu-id="2f3de-210">Abra o arquivo **RSReportServer.config** em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="2f3de-210">Open the **RSReportServer.config** file in a text editor.</span></span>  
  
9. <span data-ttu-id="2f3de-211">Verifique se `<UrlRoot>` está configurado como o endereço da URL do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2f3de-211">Verify that `<UrlRoot>` is set to the report server URL address.</span></span> <span data-ttu-id="2f3de-212">Esse valor é definido quando você configura o servidor de relatório e já deveria estar preenchido.</span><span class="sxs-lookup"><span data-stu-id="2f3de-212">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="2f3de-213">Se não estiver definido, digite o endereço da URL do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2f3de-213">If it is not set, type the report server URL address.</span></span>  
  
10. <span data-ttu-id="2f3de-214">Na seção Entrega, localize `<ReportServerEmail>.`</span><span class="sxs-lookup"><span data-stu-id="2f3de-214">In the Delivery section, find `<ReportServerEmail>.`</span></span>  
  
11. <span data-ttu-id="2f3de-215">Em `<SMTPServer>`, desmarque quaisquer valores para essa configuração, mas não exclua as marcas.</span><span class="sxs-lookup"><span data-stu-id="2f3de-215">In `<SMTPServer>`, clear any values for this setting, but do not delete the tags.</span></span>  
  
12. <span data-ttu-id="2f3de-216">Defina `<SendUsing>` como 1.</span><span class="sxs-lookup"><span data-stu-id="2f3de-216">Set `<SendUsing>` to 1.</span></span> <span data-ttu-id="2f3de-217">Se estiver definido como outro valor, o servidor de relatório não está configurado para usar um serviço SMTP local.</span><span class="sxs-lookup"><span data-stu-id="2f3de-217">If it is set another value, the report server is not configured to use a local SMTP service.</span></span>  
  
13. <span data-ttu-id="2f3de-218">Defina `<SMTPServerPickupDirectory>` para uma pasta na unidade local.</span><span class="sxs-lookup"><span data-stu-id="2f3de-218">Set `<SMTPServerPickupDirectory>` to a folder on the local drive.</span></span>  
  
14. <span data-ttu-id="2f3de-219">Configure `<From>` como uma conta que tenha permissão para enviar email a partir do servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2f3de-219">Set `<From>` to an account that has permission to send e-mail from the SMTP server.</span></span>  
  
15. <span data-ttu-id="2f3de-220">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f3de-220">Save the file.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="2f3de-221">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f3de-221">See Also</span></span>  
 [<span data-ttu-id="2f3de-222">Reporting Services Configuration Manager &#40;Modo Nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="2f3de-222">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
