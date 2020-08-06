---
title: Cmdlets do PowerShell para o modo do Reporting Services SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7835bc97-2827-4215-b0dd-52f692ce5e02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b20ad870fd8a9cd7f220eebb2b954d7a88a10c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686094"
---
# <a name="powershell-cmdlets-for-reporting-services-sharepoint-mode"></a><span data-ttu-id="c9e3f-102">Cmdlets PowerShell para Modo do SharePoint do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c9e3f-102">PowerShell cmdlets for Reporting Services SharePoint Mode</span></span>
  <span data-ttu-id="c9e3f-103">Quando você instala o [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modo do SharePoint, os cmdlets do PowerShell são instalados para dar suporte a servidores de relatório no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-103">When you install [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode, PowerShell cmdlets are installed to support report Servers in SharePoint mode.</span></span> <span data-ttu-id="c9e3f-104">Os cmdlets abrangem três categorias de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-104">The cmdlets cover three categories of functionality.</span></span>  
  
-   <span data-ttu-id="c9e3f-105">Instalação do serviço compartilhado e proxy do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-105">Installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service and proxy.</span></span>  
  
-   <span data-ttu-id="c9e3f-106">Provisionando e gerenciamento de aplicativos de serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e proxy associados.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-106">Provisioning and management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and associated proxies.</span></span>  
  
-   <span data-ttu-id="c9e3f-107">Gerenciamento de recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , por exemplo, extensões e chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-107">Management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features, for example extensions and encryption keys.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../includes/applies-md.md)]<span data-ttu-id="c9e3f-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9e3f-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint Mode</span></span>|  
  
 <span data-ttu-id="c9e3f-109">**Este tópico inclui o seguinte:**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-109">**This topic contains the following:**</span></span>  
  
-   [<span data-ttu-id="c9e3f-110">Resumo do cmdlet</span><span class="sxs-lookup"><span data-stu-id="c9e3f-110">Cmdlet Summary</span></span>](#bkmk_cmdlet_sum)  
  
-   [<span data-ttu-id="c9e3f-111">Cmdlets de serviço compartilhado e proxy</span><span class="sxs-lookup"><span data-stu-id="c9e3f-111">Shared Service and Proxy Cmdlets</span></span>](#bkmk_sharedservice_cmdlets)  
  
-   [<span data-ttu-id="c9e3f-112">Cmdlets de aplicativo de serviço e proxy</span><span class="sxs-lookup"><span data-stu-id="c9e3f-112">Service Application and Proxy Cmdlets</span></span>](#bkmk_serviceapp_cmdlets)  
  
-   [<span data-ttu-id="c9e3f-113">Cmdlets de funcionalidade personalizada do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c9e3f-113">Reporting Services Custom Functionality Cmdlets</span></span>](#bkmk_ssrsfeatures_cmdlets)  
  
-   [<span data-ttu-id="c9e3f-114">Exemplos básicos</span><span class="sxs-lookup"><span data-stu-id="c9e3f-114">Basic Samples</span></span>](#bkmk_basic_samples)  
  
-   [<span data-ttu-id="c9e3f-115">Exemplos detalhados</span><span class="sxs-lookup"><span data-stu-id="c9e3f-115">Detailed Samples</span></span>](#bkmk_detailedsamples)  
  
    -   [<span data-ttu-id="c9e3f-116">Criar um aplicativo de serviço Reporting Services e um proxy</span><span class="sxs-lookup"><span data-stu-id="c9e3f-116">Create a Reporting Services service application and proxy</span></span>](#bkmk_example_create_service_application)  
  
    -   [<span data-ttu-id="c9e3f-117">Revisar e atualizar uma extensão de entrega do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c9e3f-117">Review and update a Reporting Services delivery extension</span></span>](#bkmk_example_delivery_extension)  
  
    -   [<span data-ttu-id="c9e3f-118">Obter e definir propriedades do banco de dados do aplicativo Reporting Services, por exemplo, limite de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c9e3f-118">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>](#bkmk_example_db_properties)  
  
    -   [<span data-ttu-id="c9e3f-119">Listar extensões de dados do Reporting Services – modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9e3f-119">List reporting services data extensions - SharePoint mode</span></span>](#bkmk_example_list_data_extensions)  
  
    -   [<span data-ttu-id="c9e3f-120">Alterar e listar proprietários de assinatura</span><span class="sxs-lookup"><span data-stu-id="c9e3f-120">Change and list subscription owners</span></span>](#bkmk_change_subscription_owner)  
  
##  <a name="cmdlet-summary"></a><a name="bkmk_cmdlet_sum"></a><span data-ttu-id="c9e3f-121">Resumo do cmdlet</span><span class="sxs-lookup"><span data-stu-id="c9e3f-121">Cmdlet Summary</span></span>  

 <span data-ttu-id="c9e3f-122">Para executar os cmdlets, é necessário abrir o Shell de Gerenciamento do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-122">To run the cmdlets you need to open the SharePoint Management Shell.</span></span> <span data-ttu-id="c9e3f-123">Você também pode usar o editor de interface gráfica do usuário incluído no Microsoft Windows, o **Ambiente de Script Integrado do Windows PowerShell (ISE)**.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-123">You can also use the graphical user interface editor that is included with Microsoft Windows, **Windows PowerShell Integrated Scripting Environment (ISE)**.</span></span> <span data-ttu-id="c9e3f-124">Para obter mais informações, consulte [Starting Windows PowerShell on Windows Server (Iniciando o Windows PowerShell no Windows Server)](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9e3f-124">For more information, see [Starting Windows PowerShell on Windows Server](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell).</span></span> <span data-ttu-id="c9e3f-125">Nos resumos de cmdlets a seguir, as referências a ' bancos de dados ' do aplicativo de serviço referem-se a todos os bancos de dados criados e usados por um [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-125">In the following cmdlet summaries, the references to service application 'databases', refer to all of the databases created and used by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="c9e3f-126">Isso inclui a os bancos de dados de configuração, alerta e temp.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-126">This includes the configuration, alerting, and temp databases.</span></span>  

  
 <span data-ttu-id="c9e3f-127">Se uma mensagem de erro semelhante à seguinte for exibida quando você digitar os exemplos do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c9e3f-127">If you see an error message similar to the following when you type the PowerShell examples:</span></span>  
  
-   <span data-ttu-id="c9e3f-128">Install-SPRSService: o termo 'Install-SPRSService' não é reconhecido como</span><span class="sxs-lookup"><span data-stu-id="c9e3f-128">Install-SPRSService : The term 'Install-SPRSService' is not recognized as the</span></span>  
    <span data-ttu-id="c9e3f-129">nome de cmdlet, função, arquivo de script ou programa operável.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-129">name of a cmdlet, function, script file, or operable program.</span></span> <span data-ttu-id="c9e3f-130">Verifique a ortografia do nome ou se um caminho foi incluído, verifique se ele está correto e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-130">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>  
  
 <span data-ttu-id="c9e3f-131">Um destes problemas está ocorrendo:</span><span class="sxs-lookup"><span data-stu-id="c9e3f-131">One of the following issues is occurring:</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="c9e3f-132">não está instalado e, portanto, os cmdlets do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] também não estão instalados.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-132">SharePoint mode is not installed and therefore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets are not installed.</span></span>  
  
-   <span data-ttu-id="c9e3f-133">Você executou o comando do PowerShell no Windows PowerShell ou no ISE do Windows PowerShell, e não no Shell de Gerenciamento do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-133">You ran the PowerShell command in Windows PowerShell or Windows PowerShell ISE instead of the SharePoint Management Shell.</span></span> <span data-ttu-id="c9e3f-134">Use o Shell de Gerenciamento do SharePoint ou adicione o Snap-in do SharePoint à janela do Windows PowerShell com o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c9e3f-134">Use the SharePoint Management shell or add the SharePoint Snap-in to the Windows PowerShell window with the following command:</span></span>  
  
    ```powershell
    Add-PSSnapin Microsoft.SharePoint.PowerShell  
    ```  
  
 <span data-ttu-id="c9e3f-135">Para obter mais informações, consulte [usar o Windows PowerShell para administrar o SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) ( https://technet.microsoft.com/library/ee806878.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-135">For more information see [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) (https://technet.microsoft.com/library/ee806878.aspx).</span></span>  
  
#### <a name="to-open-the-sharepoint-management-shell-and-run-cmdlets"></a><span data-ttu-id="c9e3f-136">Para abrir p Shell de Gerenciamento do SharePoint e executar cmdlets</span><span class="sxs-lookup"><span data-stu-id="c9e3f-136">To Open the SharePoint Management Shell and run cmdlets</span></span>  
  
1.  <span data-ttu-id="c9e3f-137">Clique no botão **Iniciar**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-137">Click the **Start** button</span></span>  
  
2.  <span data-ttu-id="c9e3f-138">Clique no grupo **Produtos do Microsoft SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-138">Click the **Microsoft SharePoint Products** group.</span></span>  
  
3.  <span data-ttu-id="c9e3f-139">Abra o **Shell de Gerenciamento do SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-139">Click the **SharePoint Management Shell**.</span></span>  
  
 <span data-ttu-id="c9e3f-140">Para exibir a ajuda da linha de comando de um cmdlet, use o comando 'Get-Help' do PowerShell no prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-140">To view command line help for a cmdlet use the PowerShell 'Get-Help' command at the PowerShell command prompt.</span></span> <span data-ttu-id="c9e3f-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9e3f-141">For example:</span></span>  
  
 `Get-Help Get-SPRSServiceApplicationServers`  
  
###  <a name="shared-service-and-proxy-cmdlets"></a><a name="bkmk_sharedservice_cmdlets"></a><span data-ttu-id="c9e3f-142">Cmdlets de serviço compartilhado e proxy</span><span class="sxs-lookup"><span data-stu-id="c9e3f-142">Shared Service and Proxy Cmdlets</span></span>  
 <span data-ttu-id="c9e3f-143">A tabela a seguir contém os cmdlets PowerShell do serviço compartilhado [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-143">The following table contains the PowerShell cmdlets for the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service.</span></span>  
  
|<span data-ttu-id="c9e3f-144">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c9e3f-144">Cmdlet</span></span>|<span data-ttu-id="c9e3f-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="c9e3f-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c9e3f-146">Install-SPRSService</span><span class="sxs-lookup"><span data-stu-id="c9e3f-146">Install-SPRSService</span></span>|<span data-ttu-id="c9e3f-147">Instala e registra, ou desinstala, o aplicativo do serviço compartilhado [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-147">Installs and registers, or uninstalls, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="c9e3f-148">Só pode ser feito em um computador que tenha o SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] instalado no modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-148">This can be done only on the machine that has an installation of SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="c9e3f-149">Para instalação, há duas operações:</span><span class="sxs-lookup"><span data-stu-id="c9e3f-149">For installation, two operations occur:</span></span><br /><br /> <span data-ttu-id="c9e3f-150">1) o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] serviço está instalado no farm.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-150">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is installed in the farm.</span></span><br /><br /> <span data-ttu-id="c9e3f-151">2) a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] instância de serviço é instalada no computador atual.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-151">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service instance is installed to the current machine.</span></span><br /><br /> <span data-ttu-id="c9e3f-152">Para desinstalação, há duas operações:</span><span class="sxs-lookup"><span data-stu-id="c9e3f-152">For Uninstallation, two operations occur:</span></span><br /><span data-ttu-id="c9e3f-153">1) o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] serviço é desinstalado do computador atual.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-153">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the current machine.</span></span><br /><span data-ttu-id="c9e3f-154">2) o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] serviço é desinstalado do farm.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-154">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the farm.</span></span><br /><br /> <br /><br /> <span data-ttu-id="c9e3f-155">OBSERVAÇÃO: se houver outros computadores no farm que tenham o serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] instalado, ou se ainda houver aplicativos do serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] em execução no farm, uma mensagem de aviso será exibida.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-155">NOTE: If there are any other machines in the farm that have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service installed, or if there are still [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications running in the farm, a warning message is displayed.</span></span>|  
|<span data-ttu-id="c9e3f-156">Install-SPRSServiceProxy</span><span class="sxs-lookup"><span data-stu-id="c9e3f-156">Install-SPRSServiceProxy</span></span>|<span data-ttu-id="c9e3f-157">Instala e registra, ou desinstala, o proxy do serviço Reporting Services no farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-157">Installs and registers, or uninstalls, the Reporting Services service proxy in the SharePoint farm.</span></span>|  
|<span data-ttu-id="c9e3f-158">Obtém-SPRSProxyUrl</span><span class="sxs-lookup"><span data-stu-id="c9e3f-158">Get-SPRSProxyUrl</span></span>|<span data-ttu-id="c9e3f-159">Obtém as URLs para acessar o serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-159">Gets the URL(s) for accessing the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="c9e3f-160">Get-SPRSServiceApplicationServers</span><span class="sxs-lookup"><span data-stu-id="c9e3f-160">Get-SPRSServiceApplicationServers</span></span>|<span data-ttu-id="c9e3f-161">Acessa todos os servidores no farm local do SharePoint que contém uma instalação do serviço compartilhado [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-161">Gets all servers in the local SharePoint farm that contain an installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="c9e3f-162">Esse cmdlet é útil para as atualizações do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , para determinar quais servidores executam o serviço compartilhado e, portanto, quais precisam ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-162">This cmdlet is useful for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] upgrades, to determine which servers run the shared service and therefore need to be upgraded.</span></span>|  
  
###  <a name="service-application-and-proxy-cmdlets"></a><a name="bkmk_serviceapp_cmdlets"></a> <span data-ttu-id="c9e3f-163">Cmdlets de serviço de aplicativo e proxy</span><span class="sxs-lookup"><span data-stu-id="c9e3f-163">Service Application and Proxy Cmdlets</span></span>  
 <span data-ttu-id="c9e3f-164">A tabela a seguir contém cmdlets PowerShell para aplicativos de serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e seus proxies associados.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-164">The following table contains the PowerShell cmdlets for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and their associated proxies.</span></span>  
  
|<span data-ttu-id="c9e3f-165">cmdlet</span><span class="sxs-lookup"><span data-stu-id="c9e3f-165">cmdlet</span></span>|<span data-ttu-id="c9e3f-166">Descrição</span><span class="sxs-lookup"><span data-stu-id="c9e3f-166">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c9e3f-167">Get-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="c9e3f-167">Get-SPRSServiceApplication</span></span>|<span data-ttu-id="c9e3f-168">Obtém um ou mais objetos do aplicativo do serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-168">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application objects.</span></span>|  
|<span data-ttu-id="c9e3f-169">New-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="c9e3f-169">New-SPRSServiceApplication</span></span>|<span data-ttu-id="c9e3f-170">Cria um novo aplicativo do serviço Reporting Services e os bancos de dados associados.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-170">Create a new Reporting Services service application and associated databases.</span></span><br /><br /> <span data-ttu-id="c9e3f-171">Parâmetro LogonType: especifica se o servidor de relatório usa a conta do Pool de Aplicativos do SSRS ou um logon do SQL Server para acessar o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-171">LogonType Parameter: Specifies if the report server uses the SSRS Application Pool account or a SQL Server login to access the report server database.</span></span> <span data-ttu-id="c9e3f-172">Pode ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="c9e3f-172">It can be one of the following:</span></span><br /><br /> <span data-ttu-id="c9e3f-173">0 Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="c9e3f-173">0 Windows Authentication</span></span><br /><br /> <span data-ttu-id="c9e3f-174">1 SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9e3f-174">1 SQL Server</span></span><br /><br /> <span data-ttu-id="c9e3f-175">2 Conta do pool de aplicativos (padrão)</span><span class="sxs-lookup"><span data-stu-id="c9e3f-175">2 Application Pool Account (default)</span></span>|  
|<span data-ttu-id="c9e3f-176">Remove-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="c9e3f-176">Remove-SPRSServiceApplication</span></span>|<span data-ttu-id="c9e3f-177">Remove o aplicativo do serviço Reporting Services especificado.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-177">Removes the specified Reporting Services service application.</span></span> <span data-ttu-id="c9e3f-178">Isso também removerá os bancos de dados associados.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-178">This will also remove the associated databases.</span></span>|  
|<span data-ttu-id="c9e3f-179">Set-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="c9e3f-179">Set-SPRSServiceApplication</span></span>|<span data-ttu-id="c9e3f-180">Edita as propriedades de um aplicativo do serviço Reporting Services existente.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-180">Edits the properties of an existing Reporting Services service application.</span></span>|  
|<span data-ttu-id="c9e3f-181">New-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="c9e3f-181">New-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="c9e3f-182">Cria um novo proxy do aplicativo do serviço Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-182">Creates a new Reporting Services service application proxy.</span></span>|  
|<span data-ttu-id="c9e3f-183">Get-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="c9e3f-183">Get-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="c9e3f-184">Obtém um ou mais proxies de aplicativo do serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-184">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application proxies.</span></span>|  
|<span data-ttu-id="c9e3f-185">Dismount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="c9e3f-185">Dismount-SPRSDatabase</span></span>|<span data-ttu-id="c9e3f-186">Desmonta os bancos de dados do aplicativo de serviço de um aplicativo do serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-186">Dismounts the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="c9e3f-187">Remove-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="c9e3f-187">Remove-SPRSDatabase</span></span>|<span data-ttu-id="c9e3f-188">Remove os bancos de dados do aplicativo de serviço de um aplicativo do serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-188">Remove the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="c9e3f-189">Set-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="c9e3f-189">Set-SPRSDatabase</span></span>|<span data-ttu-id="c9e3f-190">Define as propriedades dos bancos de dados associados a um aplicativo do serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-190">Sets the properties of the databases associated to a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="c9e3f-191">Mount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="c9e3f-191">Mount-SPRSDatabase</span></span>|<span data-ttu-id="c9e3f-192">Monta bancos de dados para um aplicativo de serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-192">Mounts databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="c9e3f-193">New-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="c9e3f-193">New-SPRSDatabase</span></span>|<span data-ttu-id="c9e3f-194">Cria novos bancos de dados do aplicativo de serviço para o aplicativo do serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] especificado.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-194">Create new service application databases for the specified [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="c9e3f-195">Get-SPRSDatabaseCreationScript</span><span class="sxs-lookup"><span data-stu-id="c9e3f-195">Get-SPRSDatabaseCreationScript</span></span>|<span data-ttu-id="c9e3f-196">Imprime o script de criação do banco de dados na tela do banco de dados de aplicativo do serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-196">Outputs the database creation script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="c9e3f-197">Assim, você pode executar o script no SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-197">You can then run the script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="c9e3f-198">Get-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="c9e3f-198">Get-SPRSDatabase</span></span>|<span data-ttu-id="c9e3f-199">Obtém um ou mais proxies de bancos de dados do aplicativo do serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-199">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases.</span></span> <span data-ttu-id="c9e3f-200">Use o comando para obter a ID do banco de dados do aplicativo de serviço para que você possa usar o comdlet Set-SPRSDatabase para alterar as propriedades, por exemplo `querytimeout`.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-200">Use the command to get the ID of service application database so you can use the Set-SPRSDatabase comdlet to modify properties, for example the `querytimeout`.</span></span> <span data-ttu-id="c9e3f-201">Veja os exemplos neste tópico, [Obter e definir propriedades do banco de dados do aplicativo Reporting Services, por exemplo, limite de banco de dados](#bkmk_example_db_properties).</span><span class="sxs-lookup"><span data-stu-id="c9e3f-201">See the example in this topic, [Get and set properties of the Reporting Servicea application database, for example database timeout](#bkmk_example_db_properties).</span></span>|  
|<span data-ttu-id="c9e3f-202">Get-SPRSDatabaseRightsScript</span><span class="sxs-lookup"><span data-stu-id="c9e3f-202">Get-SPRSDatabaseRightsScript</span></span>|<span data-ttu-id="c9e3f-203">Imprime o script de direitos do banco de dados na tela do banco de dados de aplicativo do serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-203">Outputs the database rights script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="c9e3f-204">O usuário e o banco de dados desejados serão solicitados e o transact SQL que você pode executar para modificar permissões é retornado.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-204">It will prompt for desired user and database then returns transact SQL you can run to modify permissions.</span></span> <span data-ttu-id="c9e3f-205">Assim, você pode executar esse script no SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-205">You can then run this script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="c9e3f-206">Get-SPRSDatabaseUpgradeScript</span><span class="sxs-lookup"><span data-stu-id="c9e3f-206">Get-SPRSDatabaseUpgradeScript</span></span>|<span data-ttu-id="c9e3f-207">Gera um script de atualização de banco de dados na tela.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-207">Outputs a database upgrade script to the screen.</span></span> <span data-ttu-id="c9e3f-208">O script atualizará os bancos de dados do aplicativo de serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para a versão do banco de dados da instalação atual do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-208">The script will upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases to the database version of the current [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] installation.</span></span>|  
  
###  <a name="reporting-services-custom-functionality-cmdlets"></a><a name="bkmk_ssrsfeatures_cmdlets"></a><span data-ttu-id="c9e3f-209">Reporting Services cmdlets de funcionalidade personalizada</span><span class="sxs-lookup"><span data-stu-id="c9e3f-209">Reporting Services Custom Functionality Cmdlets</span></span>  
  
|<span data-ttu-id="c9e3f-210">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c9e3f-210">Cmdlet</span></span>|<span data-ttu-id="c9e3f-211">Descrição</span><span class="sxs-lookup"><span data-stu-id="c9e3f-211">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c9e3f-212">Update-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="c9e3f-212">Update-SPRSEncryptionKey</span></span>|<span data-ttu-id="c9e3f-213">Atualiza a chave de criptografia do aplicativo do serviço Reporting Services especificado e recriptografa seus dados.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-213">Updates the encryption key for the specified Reporting Services service application and re-encrypts its data.</span></span>|  
|<span data-ttu-id="c9e3f-214">Restore-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="c9e3f-214">Restore-SPRSEncryptionKey</span></span>|<span data-ttu-id="c9e3f-215">Restaura a chave de criptografia com backup anterior para um aplicativo do serviço Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-215">Restores a previously backed up encryption key for a Reporting Services service application.</span></span>|  
|<span data-ttu-id="c9e3f-216">Remove-SPRSEncryptedData</span><span class="sxs-lookup"><span data-stu-id="c9e3f-216">Remove-SPRSEncryptedData</span></span>|<span data-ttu-id="c9e3f-217">Exclui os dados criptografados do aplicativo do serviço Reporting Services especificado.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-217">Delete the encrypted data for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="c9e3f-218">Backup-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="c9e3f-218">Backup-SPRSEncryptionKey</span></span>|<span data-ttu-id="c9e3f-219">Atualiza a chave de criptografia do aplicativo de serviço especificado do Reporting Services e recriptografa seus dados.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-219">Backs up the encryption key for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="c9e3f-220">New-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="c9e3f-220">New-SPRSExtension</span></span>|<span data-ttu-id="c9e3f-221">Registra uma nova extensão com um aplicativo do serviço Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-221">Registers a new extension with a Reporting Services service application.</span></span>|  
|<span data-ttu-id="c9e3f-222">Set-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="c9e3f-222">Set-SPRSExtension</span></span>|<span data-ttu-id="c9e3f-223">Define as propriedades de uma extensão existente do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-223">Sets the properties of an existing Reporting Services extension.</span></span>|  
|<span data-ttu-id="c9e3f-224">Remove-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="c9e3f-224">Remove-SPRSExtension</span></span>|<span data-ttu-id="c9e3f-225">Remove uma extensão de um aplicativo do serviço Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-225">Removes an extension from a Reporting Services service application.</span></span>|  
|<span data-ttu-id="c9e3f-226">Get-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="c9e3f-226">Get-SPRSExtension</span></span>|<span data-ttu-id="c9e3f-227">Obtém uma ou mais extensões do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para um aplicativo do serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-227">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] extensions for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span><br /><br /> <span data-ttu-id="c9e3f-228">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="c9e3f-228">Valid values are:</span></span><br /><br /> <span data-ttu-id="c9e3f-229">**Entrega**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-229">**Delivery**</span></span><br /><br /> <span data-ttu-id="c9e3f-230">**DeliveryUI**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-230">**DeliveryUI**</span></span><br /><br /> <span data-ttu-id="c9e3f-231">**Render**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-231">**Render**</span></span><br /><br /> <span data-ttu-id="c9e3f-232">**Dados**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-232">**Data**</span></span><br /><br /> <span data-ttu-id="c9e3f-233">**Segurança**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-233">**Security**</span></span><br /><br /> <span data-ttu-id="c9e3f-234">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-234">**Authentication**</span></span><br /><br /> <span data-ttu-id="c9e3f-235">**EventProcessing**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-235">**EventProcessing**</span></span><br /><br /> <span data-ttu-id="c9e3f-236">**ReportItems**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-236">**ReportItems**</span></span><br /><br /> <span data-ttu-id="c9e3f-237">**Designer**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-237">**Designer**</span></span><br /><br /> <span data-ttu-id="c9e3f-238">**ReportItemDesigner**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-238">**ReportItemDesigner**</span></span><br /><br /> <span data-ttu-id="c9e3f-239">**ReportItemConverter**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-239">**ReportItemConverter**</span></span><br /><br /> <span data-ttu-id="c9e3f-240">**ReportDefinitionCustomization**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-240">**ReportDefinitionCustomization**</span></span>|  
|<span data-ttu-id="c9e3f-241">Get-SPRSSite</span><span class="sxs-lookup"><span data-stu-id="c9e3f-241">Get-SPRSSite</span></span>|<span data-ttu-id="c9e3f-242">Acessa sites do SharePoint com base na habilitação ou não do recurso "ReportingService".</span><span class="sxs-lookup"><span data-stu-id="c9e3f-242">Gets the SharePoint sites based on whether the "ReportingService" feature is enabled.</span></span> <span data-ttu-id="c9e3f-243">Por padrão, os sites que habilitam o recurso "ReportingService" são retornados.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-243">By default, sites that enable the "ReportingService" feature are returned.</span></span>|  
  
##  <a name="basic-samples"></a><a name="bkmk_basic_samples"></a><span data-ttu-id="c9e3f-244">Amostras básicas</span><span class="sxs-lookup"><span data-stu-id="c9e3f-244">Basic Samples</span></span>  
 <span data-ttu-id="c9e3f-245">Retorne uma lista de cmdlets que contém 'SPRS' no nome.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-245">Return a list of cmdlets that contain 'SPRS' in the name.</span></span> <span data-ttu-id="c9e3f-246">Essa será a lista completa de cmdlets [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e3f-246">This will be the full list of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets.</span></span>  
  
```powershell
Get-command -noun *SPRS*  
```  
  
 <span data-ttu-id="c9e3f-247">Ou com um pouco mais de detalhes, conectada a um arquivo de texto denominado commandlist.txt</span><span class="sxs-lookup"><span data-stu-id="c9e3f-247">Or with a little more detail, piped to a text file named commandlist.txt</span></span>  
  
```powershell
Get-Command -Noun *SPRS* | Select name, definition | Format-List | Out-File c:\commandlist.txt  
```  
  
 <span data-ttu-id="c9e3f-248">Instala o serviço e o proxy de serviço do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-248">Install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint service and service proxy.</span></span>  
  
```powershell
Install-SPRSService  
```  
  
```powershell
Install-SPRSServiceProxy  
```  
  
 <span data-ttu-id="c9e3f-249">Inicie o serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9e3f-249">Start the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service</span></span>  
  
```powershell
Get-SPServiceInstance -all | where {$_.TypeName -like "SQL Server Reporting*"} | Start-SPServiceInstance  
```  
  
 <span data-ttu-id="c9e3f-250">Digite o seguinte comando do SharePoint Management Shell para retornar uma lista filtrada de linhas de um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-250">Type the following command from the SharePoint Management Shell to return a filtered list of rows from the a log file.</span></span> <span data-ttu-id="c9e3f-251">O comando filtrará por linhas que contêm "ssrscustomactionerror".</span><span class="sxs-lookup"><span data-stu-id="c9e3f-251">The command will filter for lines that contain "ssrscustomactionerror".</span></span> <span data-ttu-id="c9e3f-252">Este exemplo examina o arquivo de log criado quando o rssharepoint.msi foi instalado.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-252">This example is looking at the log file created when the rssharepoint.msi was installed.</span></span>  
  
```powershell
Get-Content -Path C:\Users\testuser\AppData\Local\Temp\rs_sp_0.log | Select-String "ssrscustomactionerror"  
```  
  
##  <a name="detailed-samples"></a><a name="bkmk_detailedsamples"></a><span data-ttu-id="c9e3f-253">Exemplos detalhados</span><span class="sxs-lookup"><span data-stu-id="c9e3f-253">Detailed Samples</span></span>  
 <span data-ttu-id="c9e3f-254">Além dos exemplos a seguir, consulte a seção "script do Windows PowerShell" no tópico [Windows PowerShell script for steps 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span><span class="sxs-lookup"><span data-stu-id="c9e3f-254">In addition to the following samples, see the section "Windows PowerShell Script" in the topic [Windows PowerShell script for Steps 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span></span>  
  
###  <a name="create-a-reporting-services-service-application-and-proxy"></a><a name="bkmk_example_create_service_application"></a><span data-ttu-id="c9e3f-255">Criar um aplicativo de serviço Reporting Services e um proxy</span><span class="sxs-lookup"><span data-stu-id="c9e3f-255">Create a Reporting Services service application and proxy</span></span>  
 <span data-ttu-id="c9e3f-256">Este script de exemplo conclui as tarefas seguintes:</span><span class="sxs-lookup"><span data-stu-id="c9e3f-256">This sample script completes the following tasks:</span></span>  
  
1.  <span data-ttu-id="c9e3f-257">Cria um aplicativo de serviço e proxy Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-257">Create a Reporting Services service application and proxy.</span></span> <span data-ttu-id="c9e3f-258">O script supõe que o pool de aplicativos "My App Pool" já existe.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-258">The script assumes the application pool "My App Pool" already exists.</span></span>  
  
2.  <span data-ttu-id="c9e3f-259">Adicione o proxy ao grupo proxy padrão.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-259">Add the proxy to the default proxy group</span></span>  
  
3.  <span data-ttu-id="c9e3f-260">Permita para o aplicativo de serviço o acesso ao banco de dados de conteúdo do aplicativo Web na porta 80.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-260">Grant the service app access to the port 80 web app's content database.</span></span> <span data-ttu-id="c9e3f-261">O script presume que o site " http://sitename " já existe.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-261">The script assumes site "http://sitename" already exists.</span></span>  
  
```powershell
# Create service application and service application proxy  
$appPool = Get-SPServiceApplicationPool "My App Pool"  
$serviceApp = New-SPRSServiceApplication "My RS Service App" -ApplicationPool $appPool  
$serviceAppProxy = New-SPRSServiceApplicationProxy -Name "My RS Service App Proxy" -ServiceApplication $serviceApp  
  
# Add service application proxy to default proxy group.  Any web application that uses the default proxy group will now be able to use this service application.  
Get-SPServiceApplicationProxyGroup -default | Add-SPServiceApplicationProxyGroupMember -Member $serviceAppProxy  
  
# Grant application pool account access to the port 80 web application's content database.  
$webApp = Get-SPWebApplication "http://sitename"  
$appPoolAccountName = $appPool.ProcessAccount.LookupName()  
$webApp.GrantAccessToProcessIdentity($appPoolAccountName)
```  
  
###  <a name="review-and-update-a-reporting-services-delivery-extension"></a><a name="bkmk_example_delivery_extension"></a><span data-ttu-id="c9e3f-262">Revisar e atualizar uma extensão de entrega de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c9e3f-262">Review and update a Reporting Services delivery extension</span></span>  
 <span data-ttu-id="c9e3f-263">O exemplo de script PowerShell a seguir atualiza a configuração completa da extensão de entrega de email do servidor de relatório para o aplicativo de serviço denominado `My RS Service App`.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-263">The following PowerShell script example, updates the configuration for the report server e-mail delivery extension for the service application named `My RS Service App`.</span></span> <span data-ttu-id="c9e3f-264">Atualize os valores do servidor SMTP (`<email server name>`) e o alias de email FROM (`<your FROM email address>`).</span><span class="sxs-lookup"><span data-stu-id="c9e3f-264">Update the values for the SMTP server (`<email server name>`) and the FROM email alias (`<your FROM email address>`).</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication -Name "My RS Service App"  
$emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
$emailXml = [xml]$emailCfg
$emailXml.SelectSingleNode("//SMTPServer").InnerText = "<email server name>"  
$emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
$emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
$emailXml.SelectSingleNode("//From").InnerText = '<your FROM email address>'  
Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
```  
  
 <span data-ttu-id="c9e3f-265">No exemplo acima, se você não sabia o nome exato do aplicativo de serviço, poderia reescrever a primeira instrução para obter o aplicativo de serviço com base em uma pesquisa de nome parcial.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-265">In the above example if you did not know the exact name of the service application, you could rewrite the first statement to get the service application based on a search of the partial name.</span></span> <span data-ttu-id="c9e3f-266">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9e3f-266">For example:</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication | Where {$_.name -like " ssrs_testapp *"}  
```  
  
 <span data-ttu-id="c9e3f-267">O script a seguir retornará os valores de configuração atuais da extensão de entrega de email do servidor de relatório para o aplicativo de serviço denominado “Aplicativo Reporting Services”.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-267">The following script will return the current configuration values for the report server e-mail delivery extension for the service application named "Reporting Services Application".</span></span> <span data-ttu-id="c9e3f-268">A primeira etapa define o valor da variável $app para o objeto do aplicativo de serviço denominado "My RS Service App"</span><span class="sxs-lookup"><span data-stu-id="c9e3f-268">The first step sets the value of the variable $app to the object of the service application that has a name of " My RS Service App "</span></span>  
  
 <span data-ttu-id="c9e3f-269">A segunda instrução obterá a extensão de entrega 'Report Server Email' para o objeto de aplicativo de serviço na variável $app e selecionará configurationXML</span><span class="sxs-lookup"><span data-stu-id="c9e3f-269">The second statement will Get the 'Report Server Email' delivery extension for the service application object in variable $app, and select the configurationXML</span></span>  
  
```powershell
$app = Get-SPRSServiceapplication -Name "Reporting Services Application"  
Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
 <span data-ttu-id="c9e3f-270">Você também pode reescrever as duas instruções acima como se fossem uma:</span><span class="sxs-lookup"><span data-stu-id="c9e3f-270">You can also rewrite the above two statements as one:</span></span>  
  
```powershell
Get-SPRSServiceApplication -Name "Reporting Services Application" | Get-SPRSExtension -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
###  <a name="get-and-set-properties-of-the-reporting-servicea-application-database-for-example-database-timeout"></a><a name="bkmk_example_db_properties"></a><span data-ttu-id="c9e3f-271">Obter e definir propriedades do banco de dados de aplicativo do Reporting Services, por exemplo, tempo limite do banco de dados</span><span class="sxs-lookup"><span data-stu-id="c9e3f-271">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>  
 <span data-ttu-id="c9e3f-272">O seguinte exemplo retorna primeiro uma lista de banco de dados e propriedades, de forma que é possível determinar o banco de dados guid (ID) que você fornecerá ao comando do conjunto.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-272">The following example first returns a list of the databases and properties so you can determine the database guid (ID) that you then supply to the set command.</span></span> <span data-ttu-id="c9e3f-273">Para obter uma lista completa das propriedades, consulte `Get-SPRSDatabase | format-list`.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-273">For a full list of the properties, use `Get-SPRSDatabase | format-list`.</span></span>  
  
```powershell
Get-SPRSDatabase | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance
```  
  
 <span data-ttu-id="c9e3f-274">O item a seguir é um exemplo de saída.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-274">The following is an example of the output.</span></span> <span data-ttu-id="c9e3f-275">Determine a ID para o banco de dados que você deseja modificar e use a ID no cmdlet SET.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-275">Determine the ID for the database you want to modify and use the ID in the SET cmdlet.</span></span>  
  
-   `Id                : 56f8d1bc-cb04-44cf-bd41-a873643c5a14`  
  
     `QueryTimeout      : 120`  
  
     `ConnectionTimeout : 15`  
  
     `Status            : Online`  
  
     `Server            : SPServer Name=uetestb01`  
  
     `ServiceInstance   : SPDatabaseServiceInstance`  
  
```powershell
Set-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 -QueryTimeout 300  
```  
  
 <span data-ttu-id="c9e3f-276">Para verificar se o valor está definido, execute o cmdlet GET novamente.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-276">To verify the value is set, run the GET cmdlet again.</span></span>  
  
```powershell
Get-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance  
```  
  
###  <a name="list-reporting-services-data-extensions---sharepoint-mode"></a><a name="bkmk_example_list_data_extensions"></a><span data-ttu-id="c9e3f-277">Listar extensões de dados do Reporting Services – modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9e3f-277">List reporting services data extensions - SharePoint mode</span></span>  
 <span data-ttu-id="c9e3f-278">O exemplo a seguir executa um loop em cada aplicativo de serviço do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e lista as extensões de dados atuais de cada um deles.</span><span class="sxs-lookup"><span data-stu-id="c9e3f-278">The following example loops through each [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application and lists the current data extensions for each.</span></span>  
  
```powershell
$apps = Get-SPRSServiceApplication  
foreach ($app in $apps)
{  
Write-host -ForegroundColor "yellow" Service App Name $app.Name  
Get-SPRSExtension -identity $app -ExtensionType "Data" | select name, extensiontype | Format-Table -AutoSize  
}  
```  
  
 <span data-ttu-id="c9e3f-279">**Saída de exemplo:**</span><span class="sxs-lookup"><span data-stu-id="c9e3f-279">**Example output:**</span></span>  
  
-   `Name           ExtensionType`  
  
     `----           -------------`  
  
     `SQL                     Data`  
  
     `SQLAZURE                Data`  
  
     `SQLPDW                  Data`  
  
     `OLEDB                   Data`  
  
     `OLEDB-MD                Data`  
  
     `ORACLE                  Data`  
  
     `ODBC                    Data`  
  
     `XML                     Data`  
  
     `SHAREPOINTLIST          Data`  
  
###  <a name="change-and-list-subscription-owners"></a><a name="bkmk_change_subscription_owner"></a><span data-ttu-id="c9e3f-280">Alterar e listar proprietários de assinatura</span><span class="sxs-lookup"><span data-stu-id="c9e3f-280">Change and list subscription owners</span></span>  
 <span data-ttu-id="c9e3f-281">Consulte [usar o PowerShell para alterar e listar Reporting Services proprietários de assinatura e executar uma assinatura](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c9e3f-281">See [Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e3f-282">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9e3f-282">See Also</span></span>  
 <span data-ttu-id="c9e3f-283">[Usar o PowerShell para alterar e listar Reporting Services proprietários de assinatura e executar uma assinatura](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="c9e3f-283">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span></span>  
 <span data-ttu-id="c9e3f-284">[Lista de verificação: Use o PowerShell para verificar PowerPivot para SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span><span class="sxs-lookup"><span data-stu-id="c9e3f-284">[CheckList: Use PowerShell to Verify PowerPivot for SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span></span>  
 [<span data-ttu-id="c9e3f-285">Scripts PowerShell scripts de gerenciamento do CodePlex SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9e3f-285">CodePlex SharePoint Management PowerShell scripts</span></span>](https://sharepointpsscripts.codeplex.com/)   
