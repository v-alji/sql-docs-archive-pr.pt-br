---
title: Habilitar erros remotos (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- remote data source [Reporting Services]
- EnableRemoteError server property
ms.assetid: 5f05022b-d557-43e0-b50a-f5e2a1846b83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d2a7e7e0b38b38bf563dfc2a8cff65c897c5293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575580"
---
# <a name="enable-remote-errors-reporting-services"></a><span data-ttu-id="6648b-102">Habilitar erros remotos (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="6648b-102">Enable Remote Errors (Reporting Services)</span></span>
  <span data-ttu-id="6648b-103">É possível configurar propriedades do servidor de relatório em um [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para retornar informações adicionais sobre as condições de erro que ocorrem em servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="6648b-103">You can set server properties on a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server to return additional information about error conditions that occur on remote servers.</span></span> <span data-ttu-id="6648b-104">Se uma mensagem de erro contiver o texto "Para obter mais informações sobre este erro, navegue até o servidor de relatório na máquina de servidor local ou habilite erros remotos", você poderá configurar a propriedade `EnableRemoteErrors` para acessar informações adicionais que podem ajudá-lo a resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="6648b-104">If an error message contains the text "For more information about this error, navigate to the report server on the local server machine, or enable remote errors", you can set the `EnableRemoteErrors` property to access additional information that can help you troubleshoot the problem.</span></span> <span data-ttu-id="6648b-105">Para obter mais informações, consulte [Propriedades de sistema do servidor de relatório](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6648b-105">For more information, see [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="6648b-106">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="6648b-106">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="6648b-107">Habilitar erros remotos para o modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="6648b-107">Enable Remote Errors for SharePoint Mode</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="6648b-108">Habilitar erros remotos com o SQL Server Management Studio (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="6648b-108">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>](#bkmk_mgtStudio)  
  
-   [<span data-ttu-id="6648b-109">Habilitar erros remotos por meio de script (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="6648b-109">Enable remote errors through script (Native Mode)</span></span>](#bkmk_script)  
  
-   [<span data-ttu-id="6648b-110">Modificando a tabela ConfigurationInfo (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="6648b-110">Modifying the ConfigurationInfo table (Native Mode)</span></span>](#bkmk_ConfigurationInfo)  
  
##  <a name="enable-remote-errors-for-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="6648b-111">Habilitar erros remotos para o modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="6648b-111">Enable Remote Errors for SharePoint Mode</span></span>  
 <span data-ttu-id="6648b-112">Há dois procedimentos diferentes para habilitar erros remotos para o modo do SharePoint do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6648b-112">There are two different procedures for enabling remote errors for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="6648b-113">O procedimento é diferente para as duas arquiteturas de servidor de relatório distintas.</span><span class="sxs-lookup"><span data-stu-id="6648b-113">The procedure is different for the two different report server architectures.</span></span> <span data-ttu-id="6648b-114">A mais nova arquitetura baseada no serviço do SharePoint, que foi apresentada na versão [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , utiliza uma configuração que pode ser definida para cada aplicativo de serviço do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6648b-114">The newer SharePoint service based architecture that was introduced in the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, utilizes a setting that can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="6648b-115">A arquitetura mais antiga utiliza uma única configuração em nível de site.</span><span class="sxs-lookup"><span data-stu-id="6648b-115">The older architecture utilizes a single site level setting.</span></span>  
  
#### <a name="enable-remote-errors-for-a-reporting-services-service-application"></a><span data-ttu-id="6648b-116">Habilitar erros remotos para um aplicativo de serviço do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="6648b-116">Enable Remote errors for a Reporting Services Service Application</span></span>  
  
1.  <span data-ttu-id="6648b-117">Para um servidor de relatório de modo do SharePoint instalado com o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ou uma versão mais nova do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], habilite a configuração de aplicativo de serviço **Habilitar erros remotos**.</span><span class="sxs-lookup"><span data-stu-id="6648b-117">For a SharePoint mode report server installed with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] or a newer version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], enable the service application setting **Enable remote errors**.</span></span> <span data-ttu-id="6648b-118">A configuração pode ser definida para cada aplicativo de serviço do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6648b-118">The setting can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="6648b-119">Na Administração Central do SharePoint, clique em **Gerenciar aplicativos de serviço** no grupo **Gerenciamento de Aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="6648b-119">In SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
3.  <span data-ttu-id="6648b-120">Localize seu aplicativo de serviço do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e clique no nome do aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="6648b-120">Find your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and click the name of your service application.</span></span>  
  
4.  <span data-ttu-id="6648b-121">Clique em **Configurações do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="6648b-121">Click **System Settings**.</span></span>  
  
5.  <span data-ttu-id="6648b-122">Clique em **Habilitar Erros Remotos** , na seção **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="6648b-122">Click **Enable Remote Errors** in the **Security** section.</span></span>  
  
6.  <span data-ttu-id="6648b-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6648b-123">Click **OK**.</span></span>  
  
#### <a name="enable-remote-errors-for-a-sharepoint-site"></a><span data-ttu-id="6648b-124">Habilitar erros remotos para um site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="6648b-124">Enable Remote Errors for a SharePoint Site</span></span>  
  
1.  <span data-ttu-id="6648b-125">Para um servidor de relatório de modo do SharePoint instalado com uma versão do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] anterior ao [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], habilite a configuração de site **Habilitar erros remotos no modo local**.</span><span class="sxs-lookup"><span data-stu-id="6648b-125">For a SharePoint mode report server installed with a version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] prior to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], enable the site setting **Enable remote errors in local mode**.</span></span>  
  
2.  <span data-ttu-id="6648b-126">Em **Site Ações** , clique em **Configurações de Site** para o site a ser modificado.</span><span class="sxs-lookup"><span data-stu-id="6648b-126">In **Site Actions** click **Site Settings** for the site you want to modify.</span></span>  
  
3.  <span data-ttu-id="6648b-127">Clique em **Configurações do Reporting Services** , no grupo **Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="6648b-127">Click **Reporting Services Site Settings** in the **Reporting Services** group.</span></span>  
  
4.  <span data-ttu-id="6648b-128">Clique em **Habilitar erros remotos em modo local**.</span><span class="sxs-lookup"><span data-stu-id="6648b-128">Click **Enable remote errors in local mode**.</span></span>  
  
5.  <span data-ttu-id="6648b-129">Clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="6648b-129">Click **OK**</span></span>  
  
##  <a name="enable-remote-errors-through-sql-server-management-studio-native-mode"></a><a name="bkmk_mgtStudio"></a> <span data-ttu-id="6648b-130">Habilitar erros remotos com o SQL Server Management Studio (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="6648b-130">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>  
  
1.  <span data-ttu-id="6648b-131">Inicie o Management Studio e conecte-se a uma instância de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="6648b-131">Start Management Studio and connect to a report server instance.</span></span> <span data-ttu-id="6648b-132">Para obter mais informações, consulte [Conectar-se a um servidor de relatório no Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6648b-132">For more information, see [Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="6648b-133">Clique com o botão direito do mouse no nó do servidor de relatório e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6648b-133">Right-click the report server node, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="6648b-134">Clique em **Avançado** para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="6648b-134">Click **Advanced** to open the properties page.</span></span> <span data-ttu-id="6648b-135">Para obter mais informações, consulte [Propriedades do Servidor &#40;página Avançado&#41; – Reporting Services](../tools/server-properties-advanced-page-reporting-services.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6648b-135">For more information, see [Server Properties &#40;Advanced Page&#41; - Reporting Services](../tools/server-properties-advanced-page-reporting-services.md)in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="6648b-136">Em `EnableRemoteErrors` , selecione `True` .</span><span class="sxs-lookup"><span data-stu-id="6648b-136">In `EnableRemoteErrors`, select `True`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="enable-remote-errors-through-script-native-mode"></a><a name="bkmk_script"></a> <span data-ttu-id="6648b-137">Habilitar erros remotos por meio de script (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="6648b-137">Enable remote errors through script (Native Mode)</span></span>  
  
1.  <span data-ttu-id="6648b-138">Crie um arquivo de texto e copie o seguinte script no arquivo.</span><span class="sxs-lookup"><span data-stu-id="6648b-138">Create a text file and copy the following script into the file.</span></span>  
  
    ```  
    Public Sub Main()  
      Dim P As New [Property]()  
      P.Name = "EnableRemoteErrors"  
      P.Value = True  
      Dim Properties(0) As [Property]  
      Properties(0) = P  
      Try  
        rs.SetSystemProperties(Properties)  
        Console.WriteLine("Remote errors enabled.")  
      Catch SE As SoapException  
        Console.WriteLine(SE.Detail.OuterXml)  
      End Try  
    End Sub  
    ```  
  
2.  <span data-ttu-id="6648b-139">Salve o arquivo como EnableRemoteErrors.rss.</span><span class="sxs-lookup"><span data-stu-id="6648b-139">Save the file as EnableRemoteErrors.rss.</span></span>  
  
3.  <span data-ttu-id="6648b-140">Clique em **Iniciar**, aponte para **Executar**, digite **cmd**e clique em **OK** para abrir uma janela do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="6648b-140">Click **Start**, point to **Run**, type **cmd**, and click **OK** to open a command prompt window.</span></span>  
  
4.  <span data-ttu-id="6648b-141">Navegue até o diretório que contém o arquivo .rss recém-criado.</span><span class="sxs-lookup"><span data-stu-id="6648b-141">Navigate to the directory that contains the .rss file you just created.</span></span>  
  
5.  <span data-ttu-id="6648b-142">Digite a seguinte linha de comando, substituindo *servername* pelo nome atual de seu servidor:</span><span class="sxs-lookup"><span data-stu-id="6648b-142">Type the following command line, replacing *servername* with the actual name of your server:</span></span>  
  
    ```  
    rs -i EnableRemoteErrors.rss -s http://servername/ReportServer  
    ```  
  
6.  <span data-ttu-id="6648b-143">Para obter mais informações, consulte [Utilitário RS.exe &#40;SSRS&#41;](../tools/rs-exe-utility-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="6648b-143">For more information, see [RS.exe Utility &#40;SSRS&#41;](../tools/rs-exe-utility-ssrs.md)</span></span>  
  
##  <a name="modifying-the-configurationinfo-table-native-mode"></a><a name="bkmk_ConfigurationInfo"></a> <span data-ttu-id="6648b-144">Modificando a tabela ConfigurationInfo (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="6648b-144">Modifying the ConfigurationInfo table (Native Mode)</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="6648b-145">Você pode editar a tabela **ConfigurationInfo** no banco de dados do servidor de relatório para definir `EnableRemoteErrors` como `True` , mas se o servidor de relatório for usado ativamente, você deverá usar SQL Server Management Studio ou script para modificar as configurações.</span><span class="sxs-lookup"><span data-stu-id="6648b-145">You can edit the **ConfigurationInfo** table in the report server database to set `EnableRemoteErrors` to `True`, but if the report server is actively used, you should use SQL Server Management Studio or script to modify the settings.</span></span> <span data-ttu-id="6648b-146">Se você modificar a configuração no banco de dados, precisará reiniciar o serviço do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] antes de as alterações entrarem em vigor.</span><span class="sxs-lookup"><span data-stu-id="6648b-146">If you modify the setting in the database, you need to restart the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service before the changes take effect.</span></span>  
  
  
