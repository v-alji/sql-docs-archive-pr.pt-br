---
title: Serviços do Reporting Services SharePoint e aplicativos de serviço | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 501aa9ee-8c13-458c-bf6f-24e00c82681b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5654764f7913002cdae58d3264848250a292c585
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584006"
---
# <a name="reporting-services-sharepoint-service-and-service-applications"></a><span data-ttu-id="a8dbd-102">Serviço SharePoint do Reporting Services e aplicativos de serviço</span><span class="sxs-lookup"><span data-stu-id="a8dbd-102">Reporting Services SharePoint Service and Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="a8dbd-103">SharePoint foi arquitetado com base na arquitetura do serviço do SharePoint e utiliza um serviço do SharePoint e aplicativos de serviço um para muitos.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-103">SharePoint mode is architected on the SharePoint service architecture and utilizes a SharePoint service and one to many service applications.</span></span> <span data-ttu-id="a8dbd-104">Criar um aplicativo de serviço torna o serviço disponível e gera o banco de dados de aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-104">Creating a service application makes the service available and generates the service application database.</span></span> <span data-ttu-id="a8dbd-105">Você pode criar vários aplicativos de serviço Reporting Services, mas um aplicativo de serviço é suficiente para a maioria dos cenários de implantação.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-105">You can create multiple Reporting Services service applications but one service application is sufficient for most deployment scenarios.</span></span>  
  
 <span data-ttu-id="a8dbd-106">Este tópico aborda as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="a8dbd-106">This topic covers the following information:</span></span>  
  
-   [<span data-ttu-id="a8dbd-107">Criando um aplicativo de serviço Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a8dbd-107">Creating a Reporting Services Service Application</span></span>](#bkmk_createapp)  
  
-   [<span data-ttu-id="a8dbd-108">Modificar as associações do aplicativo de serviço com um grupo proxy</span><span class="sxs-lookup"><span data-stu-id="a8dbd-108">Modify the Associations of the Service Application with a proxy group</span></span>](#bkmk_associations)  
  
-   [<span data-ttu-id="a8dbd-109">Editar propriedades do aplicativo de serviço</span><span class="sxs-lookup"><span data-stu-id="a8dbd-109">Edit Service Application Properties</span></span>](#bkmk_editserviceapplication)  
  
-   [<span data-ttu-id="a8dbd-110">Para criar um Aplicativo de Serviço Reporting Services usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8dbd-110">To create a Reporting Services Service Application using PowerShell</span></span>](#bkmk_powershell_create_ssrs_serviceapp)  
  
-   [<span data-ttu-id="a8dbd-111">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a8dbd-111">Related Tasks</span></span>](#bkmk_related)  
  
##  <a name="creating-a-reporting-services-service-application"></a><a name="bkmk_createapp"></a><span data-ttu-id="a8dbd-112">Criando um aplicativo de serviço de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a8dbd-112">Creating a Reporting Services Service Application</span></span>  
 <span data-ttu-id="a8dbd-113">Você pode usar a Administração Central do SharePoint ou scripts PowerShell para criar aplicativos de serviço do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8dbd-113">You can use SharePoint Central Administration or PowerShell scripts to create the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services applications.</span></span> <span data-ttu-id="a8dbd-114">Para obter mais informações sobre como usar a Administração Central do SharePoint, confira a seção "Criar um aplicativo de serviço do Reporting Services" em [Instalar o Reporting Services no modo do SharePoint para SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="a8dbd-114">For more information on using SharePoint Central Administration, see the "Create a Reporting Services Service Application" section in [Install Reporting Services SharePoint Mode for SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span></span> <span data-ttu-id="a8dbd-115">Consulte a seção PowerShell posteriormente neste tópico para obter um exemplo de script PowerShell para criar aplicativos de serviço.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-115">See the PowerShell section later in this topic for a sample PowerShell script for creating service applications.</span></span>  
  
##  <a name="modify-the-associations-of-the-service-application-with-a-proxy-group"></a><a name="bkmk_associations"></a><span data-ttu-id="a8dbd-116">Modificar as associações do aplicativo de serviço com um grupo de proxy</span><span class="sxs-lookup"><span data-stu-id="a8dbd-116">Modify the Associations of the Service Application with a proxy group</span></span>  
 <span data-ttu-id="a8dbd-117">A página Nova para criar um aplicativo de serviço contém a seção **Associação de Aplicativo Web**.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-117">The New page for creating a services application contains the section **Web Application Association**.</span></span> <span data-ttu-id="a8dbd-118">Esta seção permite a você associar seu aplicativo de serviço conforme criá-lo.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-118">The section allows you to associate your service application as you create it.</span></span> <span data-ttu-id="a8dbd-119">Use as etapas a seguir para alterar a associação e atribuir uma configuração de cliente ao aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-119">Use the following steps to change the association and assign a customer configuration to the service application.</span></span> <span data-ttu-id="a8dbd-120">O mesmo processo geral também pode ser usado para adicionar o proxy ao grupo padrão em vez de alterar a associação do aplicativo de serviço com um grupo personalizado.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-120">The same general process can also be used to add the proxy to the default group rather than changing the association of the service application to a custom group.</span></span>  
  
1.  <span data-ttu-id="a8dbd-121">Na Administração Central do SharePoint, em Gerenciamento de Aplicativo, clique em **Configurar Associações de Aplicativo de Serviço**.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-121">In SharePoint Central Administration, in the Application Management, click **Configure Service Application Associations**.</span></span>  
  
2.  <span data-ttu-id="a8dbd-122">Na página Associações de Aplicativos de Serviço, altere a exibição para **Aplicativos de Serviço**.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-122">On the Service application Associations page, change the view to **Service Applications**.</span></span>  
  
3.  <span data-ttu-id="a8dbd-123">Localize e clique no nome do novo aplicativo de serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8dbd-123">Find and click the name of your new [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Service application.</span></span> <span data-ttu-id="a8dbd-124">Você também pode clicar no nome do grupos de proxies de aplicativos **padrão** para adicionar o proxy ao grupo padrão em vez de concluir as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-124">You could also click the application proxy group name **default** to add the proxy to default group rather than completing the following steps.</span></span>  
  
4.  <span data-ttu-id="a8dbd-125">Selecione **Personalizado** na caixa de seleção **Editar o seguinte grupo de conexões**.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-125">Select **Custom** in the selection box **Edit the following group of connections**.</span></span>  
  
5.  <span data-ttu-id="a8dbd-126">Marque a caixa do proxy e clique em **Ok**.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-126">Check the box for your proxy and click **Ok**.</span></span>  
  
##  <a name="edit-service-application-properties"></a><a name="bkmk_editserviceapplication"></a> <span data-ttu-id="a8dbd-127">Editar propriedades de aplicativo de serviço</span><span class="sxs-lookup"><span data-stu-id="a8dbd-127">Edit Service Application Properties</span></span>  
 <span data-ttu-id="a8dbd-128">Você pode reabrir a página de propriedades do aplicativo de serviço para modificar as propriedades.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-128">You can reopen the property page of the service application to modify the properties.</span></span>  
  
1.  <span data-ttu-id="a8dbd-129">Na Administração Central do SharePoint, no grupo Gerenciamento de Aplicativo, clique em **Gerenciar aplicativos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-129">In SharePoint Central Administration, in the Application Management group, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="a8dbd-130">Selecione o aplicativo de serviço clicando na coluna de tipo para selecionar a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-130">Select the service application by clicking the type column to select the entire row.</span></span> <span data-ttu-id="a8dbd-131">Se você clicar no nome do aplicativo, a página de opções de Gerenciamento do serviço será aberta em vez das propriedades do aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-131">If you click the name of the application it, the Management options page for the service opens instead of opening the properties of the service application.</span></span>  
  
3.  <span data-ttu-id="a8dbd-132">Na faixa de opções Aplicativos de Serviço, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-132">In the Service Applications ribbon, click **Properties**.</span></span>  
  
##  <a name="to-create-a-reporting-services-service-application-using-powershell"></a><a name="bkmk_powershell_create_ssrs_serviceapp"></a><span data-ttu-id="a8dbd-133">Para criar um aplicativo de serviço de Reporting Services usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8dbd-133">To create a Reporting Services Service Application using PowerShell</span></span>  
 <span data-ttu-id="a8dbd-134">Você pode usar o PowerShell para criar o aplicativo de serviço e o proxy.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-134">You can use PowerShell to create the Service application and proxy.</span></span> <span data-ttu-id="a8dbd-135">O exemplo a seguir presume que você saiba qual pool de aplicativos deseja para configurar o aplicativo de serviço a ser usado.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-135">The sample below assumes that you know what application pool you want to configure the service application to use.</span></span>  
  
1.  <span data-ttu-id="a8dbd-136">Adicione o objeto do pool de aplicativos do nome do pool de aplicativos a uma variável que será passada para a ação Novo.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-136">Add the application pool object of your application pool name to a variable that is passed into the New action.</span></span>  
  
    ```powershell
    $appPoolName = Get-SPServiceApplicationPool "<application pool name>"  
    ```  
  
2.  <span data-ttu-id="a8dbd-137">Crie o aplicativo de serviço com um nome e um nome de pool de aplicativos fornecidos.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-137">Create the service application with a name and application pool name you provide.</span></span>  
  
    ```powershell
    New-SPRSServiceApplication -Name 'MyServiceApplication' -ApplicationPool $appPoolName -DatabaseName 'MyServiceApplicationDatabase' -DatabaseServer '<Server Name>'  
    ```  
  
3.  <span data-ttu-id="a8dbd-138">Obtenha o novo objeto do aplicativo de serviço e redirecione o objeto para o Pipe do novo cmdlet de proxy.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-138">Get the new service application object, and pipe the object into the Pipe the new proxy cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication -name MyServiceApplication | New-SPRSServiceApplicationProxy "MyServiceApplicationProxy"  
    ```  
  
##  <a name="related-tasks"></a><a name="bkmk_related"></a> <span data-ttu-id="a8dbd-139">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a8dbd-139">Related Tasks</span></span>  
  
|<span data-ttu-id="a8dbd-140">Tarefa</span><span class="sxs-lookup"><span data-stu-id="a8dbd-140">Task</span></span>|<span data-ttu-id="a8dbd-141">Link</span><span class="sxs-lookup"><span data-stu-id="a8dbd-141">Link</span></span>|  
|----------|----------|  
|<span data-ttu-id="a8dbd-142">Gerenciar as configurações de seu aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-142">Manage the settings of your Service Application.</span></span>|[<span data-ttu-id="a8dbd-143">Gerenciar um aplicativo de serviço do SharePoint Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a8dbd-143">Manage a Reporting Services SharePoint Service Application</span></span>](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md)|  
|<span data-ttu-id="a8dbd-144">Faça backup e restaure o aplicativo de serviço e os componentes relacionados, como chaves de criptografia e proxy.</span><span class="sxs-lookup"><span data-stu-id="a8dbd-144">Backup and restore the service application and related components such as encryption keys and proxy.</span></span>|[<span data-ttu-id="a8dbd-145">Aplicativos de serviço SharePoint de backup e restauração do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a8dbd-145">Backup and Restore Reporting Services SharePoint Service Applications</span></span>](../../2014/reporting-services/backup-and-restore-reporting-services-sharepoint-service-applications.md)|  
