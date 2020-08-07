---
title: Configurar o email para um aplicativo de serviço de Reporting Services (SharePoint 2010 e SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 38fc34a6-aae7-4dde-9ad2-f1eee0c42a9f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 628122289f8a9d83a307d70a369ab51f8f571c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575635"
---
# <a name="configure-e-mail-for-a-reporting-services-service-application-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="2220f-102">Configurar o email para um serviço de aplicativo do Reporting Services (SharePoint 2010 e SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="2220f-102">Configure E-mail for a Reporting Services Service Application (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="2220f-103">O alerta de dados envia alertas de dados em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="2220f-103">data alerting sends alerts in e-mail messages.</span></span> <span data-ttu-id="2220f-104">Para enviar um email, talvez seja necessário configurar o aplicativo de serviço do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e modificar a extensão de entrega de email do aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="2220f-104">To send e-mail you may need to configure your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and you may need to modify the e-mail delivery extension for the service application.</span></span> <span data-ttu-id="2220f-105">As configurações de email também serão necessárias se você estiver planejando usar a extensão de entrega de email do recurso de assinatura do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2220f-105">The e-mail settings are also required if you plan to use the e-mail delivery extension for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscription feature.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="2220f-106">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo do sharepoint &#124; sharepoint 2010 e sharepoint 2013.</span><span class="sxs-lookup"><span data-stu-id="2220f-106">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode &#124; SharePoint 2010 and SharePoint 2013.</span></span>|  
  
### <a name="to-configure-e-mail-for-the-shared-service"></a><span data-ttu-id="2220f-107">Para configurar o email para o serviço compartilhado</span><span class="sxs-lookup"><span data-stu-id="2220f-107">To configure e-mail for the shared service</span></span>  
  
1.  <span data-ttu-id="2220f-108">Na Administração Central do SharePoint, clique em **Gerenciamento de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="2220f-108">In SharePoint Central Administration, click the **Application Management**.</span></span>  
  
2.  <span data-ttu-id="2220f-109">No grupo **Aplicativos de Serviço** , clique em **Gerenciar aplicativos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="2220f-109">In the **Service Applications** group, click **Manage service applications**.</span></span>  
  
3.  <span data-ttu-id="2220f-110">Na lista **Nome** , clique no nome do seu aplicativo de serviço do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2220f-110">In the **Name** list, click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
4.  <span data-ttu-id="2220f-111">Clique em **Configurações de Email** na página **Gerenciar Aplicativo Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="2220f-111">Click **E-mail Settings** on the **Manage Reporting Services Application** page.</span></span>  
  
5.  <span data-ttu-id="2220f-112">Selecione **Usar servidor SMTP**.</span><span class="sxs-lookup"><span data-stu-id="2220f-112">Select **Use SMTP server**.</span></span>  
  
6.  <span data-ttu-id="2220f-113">Na caixa **Servidor SMTP de saída** , digite o nome de um servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="2220f-113">In the **Outbound SMTP server** box, type the name of an SMTP server.</span></span>  
  
7.  <span data-ttu-id="2220f-114">Na caixa **Endereço de origem** , digite um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="2220f-114">In the **From address** box, type an e-mail address.</span></span>  
  
     <span data-ttu-id="2220f-115">Esse endereço corresponde ao remetente de mensagens de email de alerta.</span><span class="sxs-lookup"><span data-stu-id="2220f-115">This address is the sender of all alert e-mail messages.</span></span>  
  
     <span data-ttu-id="2220f-116">A conta de usuário especificada no **Endereço de origem** deve ser uma conta gerenciada que você especificou quando configurou o pool de aplicativos para o aplicativo de serviço do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2220f-116">The account of the user specified in **From address** must be a managed account that you specified when you configured the application pool for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="2220f-117">Se tiver permissão, você poderá exibir uma lista das contas gerenciadas existentes na página Contas de Serviço na Administração Central do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2220f-117">If you have permission, you can view a list of existing managed accounts on the Service Accounts page in SharePoint Central Administration.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="ntlm-authentication"></a><span data-ttu-id="2220f-118">Autenticação NTLM</span><span class="sxs-lookup"><span data-stu-id="2220f-118">NTLM Authentication</span></span>  
  
1.  <span data-ttu-id="2220f-119">Se o seu ambiente de email exigir a autenticação NTLM e não permitir acesso anônimo, será necessário modificar a configuração de extensão de entrega de email para aplicativos de serviço do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2220f-119">If your email environment requires NTLM authentication and does not allow anonymous access, you need to modify the e-mail delivery extension configuration for your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service applications.</span></span> <span data-ttu-id="2220f-120">Altere o **SMTPAuthenticate** para usar um valor de "2".</span><span class="sxs-lookup"><span data-stu-id="2220f-120">Change the **SMTPAuthenticate** to use a value of "2".</span></span> <span data-ttu-id="2220f-121">Esse valor não pode ser alterado na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="2220f-121">This value cannot be changed from the user interface.</span></span> <span data-ttu-id="2220f-122">O exemplo de script PowerShell a seguir atualiza a configuração completa da extensão de entrega de email do servidor de relatório para o aplicativo de serviço denominado "SSRS_TESTAPPLICATION".</span><span class="sxs-lookup"><span data-stu-id="2220f-122">The following PowerShell script example, updates the full configuration for the report server e-mail delivery extension for the service application named "SSRS_TESTAPPLICATION".</span></span> <span data-ttu-id="2220f-123">Observe que alguns dos nós listados no script também podem ser definidos na interface do usuário, por exemplo, o endereço "De".</span><span class="sxs-lookup"><span data-stu-id="2220f-123">Note some of the nodes listed in the script can also be set from the user interface, for example the "From" address.</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION *"}  
    $emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
    $emailXml = [xml]$emailCfg
    $emailXml.SelectSingleNode("//SMTPServer").InnerText = "your email server name"  
    $emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
    $emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
    $emailXml.SelectSingleNode("//From").InnerText = "your FROM email address"  
    Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
    ```  
  
2.  <span data-ttu-id="2220f-124">Se você precisar verificar o nome do seu aplicativo de serviço, execute o cmdlet **Get-SPRSServiceApplication** .</span><span class="sxs-lookup"><span data-stu-id="2220f-124">If you need to verify the name of your service application, run the **Get-SPRSServiceApplication** cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication  
    ```  
  
3.  <span data-ttu-id="2220f-125">O exemplo a seguir retornará os valores atuais da extensão de email para o aplicativo de serviço denominado "SSRS_TESTAPPLICATION".</span><span class="sxs-lookup"><span data-stu-id="2220f-125">The following example will return the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION".</span></span>  
  
    ```powershell
    $app = get-sprsserviceapplication | Where {$_.name -like "SSRSTEST_APPLICATION*"}  
    Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
    ```  
  
4.  <span data-ttu-id="2220f-126">O exemplo a seguir criará um novo arquivo denominado "emailconfig.txt" com os valores atuais da extensão de email para o aplicativo de serviço chamado "SSRS_TESTAPPLICATION"</span><span class="sxs-lookup"><span data-stu-id="2220f-126">The following example will create a new file named "emailconfig.txt" with the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION"</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION*"}  
    Get-SPRSExtension -identity $app -ExtensionType "Delivery" -name "Report Server Email" | Select -ExpandProperty ConfigurationXml | Out-File c:\emailconfig.txt  
    ```
