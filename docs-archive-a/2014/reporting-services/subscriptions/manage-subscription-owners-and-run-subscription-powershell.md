---
title: Usar o PowerShell para alterar e listar Reporting Services proprietários de assinatura e executar uma assinatura | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0fa6cb36-68fc-4fb8-b1dc-ae4f12bf6ff0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b274dc190d8830a2cf7b55110f15267a00c581e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574470"
---
# <a name="use-powershell-to-change-and-list-reporting-services-subscription-owners-and-run-a-subscription"></a><span data-ttu-id="a2a7d-102">Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription</span><span class="sxs-lookup"><span data-stu-id="a2a7d-102">Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription</span></span>
  <span data-ttu-id="a2a7d-103">A partir do [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] , você pode transferir de forma programática a propriedade de uma assinatura do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] de um usuário para outro.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-103">Starting with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] you can programmatically transfer the ownership of a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] subscription from one user to another.</span></span> <span data-ttu-id="a2a7d-104">Este tópico fornece vários scripts do Windows PowerShell que você pode usar para mudar ou simplesmente listar a propriedade das assinaturas.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-104">This topic provides several Windows PowerShell scripts you can use to change or simply list subscription ownership.</span></span> <span data-ttu-id="a2a7d-105">Cada amostra inclui a sintaxe de amostra do modo Nativo e do modo SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-105">Each sample includes sample syntax for both Native mode and SharePoint mode.</span></span> <span data-ttu-id="a2a7d-106">Após mudar o proprietário da assinatura, está será executada no contexto de segurança do novo proprietário, e o campo User!UserID no relatório exibirá o valor do novo proprietário.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-106">After you change the subscription owner, the subscription will then execute in the security context of the new owner, and the User!UserID field in the report will display the value of new owner.</span></span> <span data-ttu-id="a2a7d-107">Para obter mais informações sobre o modelo de objeto que as amostras do PowerShell chamam, consulte <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="a2a7d-107">For more information on the object model the PowerShell samples call, see <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span>

 <span data-ttu-id="a2a7d-108">![Conteúdo relacionado ao PowerShell](../media/rs-powershellicon.jpg "Conteúdo relacionado ao PowerShell")</span><span class="sxs-lookup"><span data-stu-id="a2a7d-108">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

||
|-|
|<span data-ttu-id="a2a7d-109">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] &#124; modo do SharePoint para [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2a7d-109">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|

 <span data-ttu-id="a2a7d-110">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="a2a7d-110">**In this topic:**</span></span>

-   [<span data-ttu-id="a2a7d-111">Como usar os scripts</span><span class="sxs-lookup"><span data-stu-id="a2a7d-111">How to use the scripts</span></span>](#bkmk_how_to)

-   [<span data-ttu-id="a2a7d-112">Script: listar a propriedade de todas as assinaturas</span><span class="sxs-lookup"><span data-stu-id="a2a7d-112">Script: List the ownership of all subscriptions</span></span>](#bkmk_list_ownership_all)

-   [<span data-ttu-id="a2a7d-113">Script: listar todas as assinaturas pertencentes a um usuário específico</span><span class="sxs-lookup"><span data-stu-id="a2a7d-113">Script: List all subscriptions owned by a specific user</span></span>](#bkmk_list_all_one_user)

-   [<span data-ttu-id="a2a7d-114">Script: alterar a propriedade de todas as assinaturas pertencentes a um usuário específico</span><span class="sxs-lookup"><span data-stu-id="a2a7d-114">Script: Change ownership for all subscriptions owned by a specific user</span></span>](#bkmk_change_all)

-   [<span data-ttu-id="a2a7d-115">Script: listar todas as assinaturas associadas a um relatório específico</span><span class="sxs-lookup"><span data-stu-id="a2a7d-115">Script: List all subscriptions associated with a specific report</span></span>](#bkmk_list_for_1_report)

-   [<span data-ttu-id="a2a7d-116">Script: alterar a propriedade de uma assinatura específica</span><span class="sxs-lookup"><span data-stu-id="a2a7d-116">Script: Change ownership of a specific subscription</span></span>](#bkmk_change_all_1_subscription)

-   [<span data-ttu-id="a2a7d-117">Script: executar (acionar) assinatura única</span><span class="sxs-lookup"><span data-stu-id="a2a7d-117">Script: Run (fire) a single subscription</span></span>](#bkmk_run_1_subscription)

##  <a name="how-to-use-the-scripts"></a><a name="bkmk_how_to"></a> <span data-ttu-id="a2a7d-118">Como usar os scripts</span><span class="sxs-lookup"><span data-stu-id="a2a7d-118">How to use the scripts</span></span>

### <a name="permissions"></a><span data-ttu-id="a2a7d-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="a2a7d-119">Permissions</span></span>
 <span data-ttu-id="a2a7d-120">Esta seção resume os níveis de permissão necessários para usar cada um dos métodos para o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]em modo Nativo e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-120">This section summarizes the permission levels required to use each of the methods for both Native and SharePoint mode [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="a2a7d-121">Os scripts neste tópico usam os seguintes métodos [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="a2a7d-121">The scripts in this topic use the following [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] methods:</span></span>

-   [<span data-ttu-id="a2a7d-122">Método ReportingService2010.ListSubscriptions</span><span class="sxs-lookup"><span data-stu-id="a2a7d-122">ReportingService2010.ListSubscriptions Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listsubscriptions.aspx)

-   [<span data-ttu-id="a2a7d-123">Método ReportingService2010.ChangeSubscriptionOwner</span><span class="sxs-lookup"><span data-stu-id="a2a7d-123">ReportingService2010.ChangeSubscriptionOwner Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.changesubscriptionowner.aspx)

-   [<span data-ttu-id="a2a7d-124">ReportingService2010.ListChildren</span><span class="sxs-lookup"><span data-stu-id="a2a7d-124">ReportingService2010.ListChildren</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listchildren.aspx)

-   <span data-ttu-id="a2a7d-125">O método [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) é usado apenas no último script para disparar uma assinatura específica a ser executada.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-125">The method [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) is only used in the last script to trigger a specific subscription to run.</span></span> <span data-ttu-id="a2a7d-126">Se você não planeja usar esse script, é possível ignorar os requisitos de permissão para o método FireEvent.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-126">If you do not plan to use that script you can ignore the permission requirements for the FireEvent method.</span></span>

 <span data-ttu-id="a2a7d-127">**Modo Nativo:**</span><span class="sxs-lookup"><span data-stu-id="a2a7d-127">**Native mode:**</span></span>

-   <span data-ttu-id="a2a7d-128">Listar assinaturas: (HYPERLINK " https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx " ReadSubscription no relatório e o usuário é o proprietário da assinatura) ou ReadAnySubscription</span><span class="sxs-lookup"><span data-stu-id="a2a7d-128">List Subscriptions: ( HYPERLINK "https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx" ReadSubscription on the report AND the user is the subscription owner) OR ReadAnySubscription</span></span>

-   <span data-ttu-id="a2a7d-129">Alterar assinaturas: O usuário deve ser membro do grupo BUILTIN\Administrators</span><span class="sxs-lookup"><span data-stu-id="a2a7d-129">Change Subscriptions: The user must be a member of the BUILTIN\Administrators group</span></span>

-   <span data-ttu-id="a2a7d-130">Listar filhos: ReadProperties no item</span><span class="sxs-lookup"><span data-stu-id="a2a7d-130">List Children: ReadProperties on Item</span></span>

-   <span data-ttu-id="a2a7d-131">Acionar evento: GenerateEvents (sistema)</span><span class="sxs-lookup"><span data-stu-id="a2a7d-131">Fire Event: GenerateEvents (System)</span></span>

 <span data-ttu-id="a2a7d-132">**Modo SharePoint:**</span><span class="sxs-lookup"><span data-stu-id="a2a7d-132">**SharePoint mode:**</span></span>

-   <span data-ttu-id="a2a7d-133">Listar assinaturas: ManageAlerts ou (HYPERLINK " https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx " createalerta no relatório e o usuário é o proprietário da assinatura e a assinatura é uma assinatura cronometrada).</span><span class="sxs-lookup"><span data-stu-id="a2a7d-133">List Subscriptions: ManageAlerts OR ( HYPERLINK "https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx" CreateAlerts on the report AND the user is the subscription owner and the subscription is a timed subscription).</span></span>

-   <span data-ttu-id="a2a7d-134">Alterar assinaturas: ManageWeb</span><span class="sxs-lookup"><span data-stu-id="a2a7d-134">Change Subscriptions: ManageWeb</span></span>

-   <span data-ttu-id="a2a7d-135">Listar filhos: ViewListItems</span><span class="sxs-lookup"><span data-stu-id="a2a7d-135">List Children: ViewListItems</span></span>

-   <span data-ttu-id="a2a7d-136">Acionar evento: ManageWeb</span><span class="sxs-lookup"><span data-stu-id="a2a7d-136">Fire Event: ManageWeb</span></span>

 <span data-ttu-id="a2a7d-137">Para obter mais informações, consulte [Comparar funções e tarefas no Reporting Services com grupos e permissões do SharePoint](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a2a7d-137">For more information, see [Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span></span>

### <a name="script-usage"></a><span data-ttu-id="a2a7d-138">Uso de script</span><span class="sxs-lookup"><span data-stu-id="a2a7d-138">Script usage</span></span>
 <span data-ttu-id="a2a7d-139">**Criar arquivos de script (.ps1)**</span><span class="sxs-lookup"><span data-stu-id="a2a7d-139">**Create Script files (.ps1)**</span></span>

1.  <span data-ttu-id="a2a7d-140">Crie uma pasta chamada **c:\scripts**.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-140">Create a folder named **c:\scripts**.</span></span> <span data-ttu-id="a2a7d-141">Se você escolher uma pasta diferente, mude o nome da pasta usado nas instruções de sintaxe da linha de comando do exemplo.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-141">If you choose a different folder then modify the folder name used in the example command line syntax statements.</span></span>

2.  <span data-ttu-id="a2a7d-142">Crie um arquivo de texto para cada script e salve os arquivos na pasta c:\scripts.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-142">Create a text file for each script and save the files to the c:\scripts folder.</span></span> <span data-ttu-id="a2a7d-143">Quando criar os arquivos .ps1, use o nome de cada sintaxe de linha de comando do exemplo.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-143">When you create the .ps1 files, use the name from each example command line syntax.</span></span>

3.  <span data-ttu-id="a2a7d-144">Abra uma prompt de comando com privilégios de administrativos.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-144">Open a command prompt with administrative privileges.</span></span>

4.  <span data-ttu-id="a2a7d-145">Execute cada arquivo de script, usando a respectiva sintaxe de linha de comando de exemplo fornecida.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-145">Run each script file, using the sample command line syntax provided with each example.</span></span>

 <span data-ttu-id="a2a7d-146">**Ambientes testados**</span><span class="sxs-lookup"><span data-stu-id="a2a7d-146">**Tested environments**</span></span>

 <span data-ttu-id="a2a7d-147">Os scripts neste tópico foram testados no PowerShell versão 3 e com as seguintes versões do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a2a7d-147">The scripts in this topic were tested on PowerShell version 3 and with the following versions of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span></span>

-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]

-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]

-   [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)]

##  <a name="script-list-the-ownership-of-all-subscriptions"></a><a name="bkmk_list_ownership_all"></a> <span data-ttu-id="a2a7d-148">Script: listar a propriedade de todas as assinaturas</span><span class="sxs-lookup"><span data-stu-id="a2a7d-148">Script: List the ownership of all subscriptions</span></span>
 <span data-ttu-id="a2a7d-149">Esse script lista todas as assinaturas em um site.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-149">This script lists all of the subscriptions on a site.</span></span> <span data-ttu-id="a2a7d-150">Você pode usar esse script para testar sua conexão ou para verificar o caminho do relatório e a identificação de assinatura para uso em outros scripts.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-150">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="a2a7d-151">Ele também é um script útil para simplesmente auditar as assinaturas existentes e seus proprietários.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-151">This is also a useful script to simply audit what subscriptions exist and who owns them.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="a2a7d-152">Sintaxe do modo nativo</span><span class="sxs-lookup"><span data-stu-id="a2a7d-152">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="a2a7d-153">Sintaxe do modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="a2a7d-153">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="a2a7d-154">Script</span><span class="sxs-lookup"><span data-stu-id="a2a7d-154">Script</span></span>

```powershell
# Parameters
#    server   - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)

Param(
    [string]$server,
    [string]$site
   )

$rs2010 += New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site); # use "/" for default native mode site

Write-Host " "
Write-Host "----- $server's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted, Status
```

> [!TIP]
>  <span data-ttu-id="a2a7d-155">Para verificar URLs de sites no modo do SharePoint, use o cmdlet **Get-SPSite**do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-155">To verify site URLS in SharePoint mode, use the SharePoint cmdlet **Get-SPSite**.</span></span> <span data-ttu-id="a2a7d-156">Para obter mais informações, consulte [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="a2a7d-156">For more information, see [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span></span>

##  <a name="script-list-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_list_all_one_user"></a> <span data-ttu-id="a2a7d-157">Script: listar todas as assinaturas pertencentes a um usuário específico</span><span class="sxs-lookup"><span data-stu-id="a2a7d-157">Script: List all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="a2a7d-158">Esse script lista todas as assinaturas de propriedade de um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-158">This script lists all of the subscriptions owned by a specific user.</span></span> <span data-ttu-id="a2a7d-159">Você pode usar esse script para testar sua conexão ou para verificar o caminho do relatório e a identificação de assinatura para uso em outros scripts.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-159">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="a2a7d-160">Esse script é útil quando alguém sai da organização e você deseja verificar quais assinaturas essa pessoa possuía para alterar o proprietário ou excluir a assinatura.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-160">This script is useful when someone in your organization leaves and you want to verify what subscriptions they owned so you can change the owner or delete the subscription.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="a2a7d-161">Sintaxe do modo nativo</span><span class="sxs-lookup"><span data-stu-id="a2a7d-161">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]" "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="a2a7d-162">Sintaxe do modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="a2a7d-162">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]"  "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="a2a7d-163">Script</span><span class="sxs-lookup"><span data-stu-id="a2a7d-163">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
Param(
    [string]$currentOwner,
    [string]$server,
    [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $currentOwner's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.owner -eq $currentOwner}
```

##  <a name="script-change-ownership-for-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_change_all"></a> <span data-ttu-id="a2a7d-164">Script: alterar a propriedade de todas as assinaturas pertencentes a um usuário específico</span><span class="sxs-lookup"><span data-stu-id="a2a7d-164">Script: Change ownership for all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="a2a7d-165">Esse script muda a propriedade de todas as assinaturas de um usuário específico para o parâmetro do novo proprietário.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-165">This script changes the ownership for all subscriptions owned by a specific user to the new owner parameter.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="a2a7d-166">Sintaxe do modo nativo</span><span class="sxs-lookup"><span data-stu-id="a2a7d-166">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\current owner]" "[Domain]\[new owner]" "[server]/reportserver"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="a2a7d-167">Sintaxe do modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="a2a7d-167">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\{current owner]" "[Domain]\[new owner]" "[server]/_vti_bin/reportserver"
```

### <a name="script"></a><span data-ttu-id="a2a7d-168">Script</span><span class="sxs-lookup"><span data-stu-id="a2a7d-168">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    newOwner      - DOMAIN\USER that will own the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver, myserver/reportserver_db2, myserver/_vti_bin/reportserver)

Param(
    [string]$currentOwner,
    [string]$newOwner,
    [string]$server
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$items = $rs2010.ListChildren("/", $true);

$subscriptions = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $curRepSubs = $rs2010.ListSubscriptions($item.Path);
        ForEach ($curRepSub in $curRepSubs)
        {
            if ($curRepSub.Owner -eq $currentOwner)
            {
                $subscriptions += $curRepSub;
            }
        }
    }
}

Write-Host " "
Write-Host " "
Write-Host -foregroundcolor "green" "-----  $currentOwner's Subscriptions changing ownership to $newOwner : "
$subscriptions | select SubscriptionID, Owner, Path, Description,  Status  | format-table -AutoSize

ForEach ($sub in $subscriptions)
{
    $rs2010.ChangeSubscriptionOwner($sub.SubscriptionID, $newOwner);
}

$subs2 = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $subs2 += $rs2010.ListSubscriptions($item.Path);
    }
}
```

##  <a name="script-list-all-subscriptions-associated-with-a-specific-report"></a><a name="bkmk_list_for_1_report"></a> <span data-ttu-id="a2a7d-169">Script: listar todas as assinaturas associadas a um relatório específico</span><span class="sxs-lookup"><span data-stu-id="a2a7d-169">Script: List all subscriptions associated with a specific report</span></span>
 <span data-ttu-id="a2a7d-170">Esse script lista todas as assinaturas associadas a um relatório específico.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-170">This script lists all of the subscriptions associated with a specific report.</span></span> <span data-ttu-id="a2a7d-171">A sintaxe do caminho do relatório é um modo SharePoint diferente que exige uma URL completa.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-171">The report path syntax is different SharePoint mode which requires a full URL.</span></span> <span data-ttu-id="a2a7d-172">Nos exemplos de sintaxe, o nome do relatório usado é "somente título", que contém um espaço e, portanto, requer aspas simples em torno do nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-172">In the syntax examples, the report name used is "title only", which contains a space and therefore requires the single quotes around the report name.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="a2a7d-173">Sintaxe do modo nativo</span><span class="sxs-lookup"><span data-stu-id="a2a7d-173">Native mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/reportserver" "'/reports/title only'" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="a2a7d-174">Sintaxe do modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="a2a7d-174">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/_vti_bin/reportserver"  "'http://[server]/shared documents/title only.rdl'" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="a2a7d-175">Script</span><span class="sxs-lookup"><span data-stu-id="a2a7d-175">Script</span></span>

```powershell
# Parameters:
#    server      - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    reportpath  - path to report in the report server, including report name e.g. /reports/test report >> pass in  "'/reports/title only'"
#    site        - use "/" for default native mode site
Param
(
      [string]$server,
      [string]$reportpath,
      [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $reportpath 's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.path -eq $reportpath}
```

##  <a name="script-change-ownership-of-a-specific-subscription"></a><a name="bkmk_change_all_1_subscription"></a> <span data-ttu-id="a2a7d-176">Script: alterar a propriedade de uma assinatura específica</span><span class="sxs-lookup"><span data-stu-id="a2a7d-176">Script: Change ownership of a specific subscription</span></span>
 <span data-ttu-id="a2a7d-177">Esse script altera a propriedade de uma assinatura específica.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-177">This script changes the ownership for a specific subscription.</span></span> <span data-ttu-id="a2a7d-178">A assinatura é identificada pela SubscriptionID que você passa no script.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-178">The subscription is identified by the SubscriptionID that you pass into the script.</span></span> <span data-ttu-id="a2a7d-179">Você pode usar um dos scripts de assinatura da lista para determinar a SubscriptionID correta.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-179">You can use one of the list subscription scripts to determine the correct SubscriptionID.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="a2a7d-180">Sintaxe do modo nativo</span><span class="sxs-lookup"><span data-stu-id="a2a7d-180">Native mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/reportserver" "/" "ac5637a1-9982-4d89-9d69-a72a9c3b3150"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="a2a7d-181">Sintaxe do modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="a2a7d-181">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/_vti_bin/reportserver" "http://[server]" "9660674b-f020-453f-b1e3-d9ba37624519"
```

### <a name="script"></a><span data-ttu-id="a2a7d-182">Script</span><span class="sxs-lookup"><span data-stu-id="a2a7d-182">Script</span></span>

```powershell
# Parameters:
#    newOwner       - DOMAIN\USER that will own the subscriptions you wish to change
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
#    subscriptionID - guid for the single subscription to change

Param(
    [string]$newOwner,
    [string]$server,
    [string]$site,
    [string]$subscriptionid
   )
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential;

$subscription += $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid};

Write-Host " "
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status

$rs2010.ChangeSubscriptionOwner($subscription.SubscriptionID, $newOwner)

#refresh the list
$subscription = $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid}; # use "/" for default native mode site
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status
```

##  <a name="script-run-fire-a-single-subscription"></a><a name="bkmk_run_1_subscription"></a> <span data-ttu-id="a2a7d-183">Script: executar (acionar) uma assinatura única</span><span class="sxs-lookup"><span data-stu-id="a2a7d-183">Script: Run (fire) a single subscription</span></span>
 <span data-ttu-id="a2a7d-184">Esse script executa uma assinatura específica usando o método FireEvent.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-184">This script will run a specific subscription using the FireEvent method.</span></span> <span data-ttu-id="a2a7d-185">O script executa a assinatura de maneira imediata, independentemente da agenda configurada para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-185">The script will immediately run the subscription regardless of the schedule configured for the subscription.</span></span> <span data-ttu-id="a2a7d-186">O EventType é comparado com o conjunto conhecido de eventos que estão definidos no arquivo de configuração do servidor do relatório **rsreportserver.config** O script usa o tipo de evento a seguir para assinaturas padrão:</span><span class="sxs-lookup"><span data-stu-id="a2a7d-186">The EventType is matched against the known set of events that are defined in the report server configuration file **rsreportserver.config** The script uses the following event type for standard subscriptions:</span></span>

 `<Event>`

 `<Type>TimedSubscription</Type>`

 `</Event>`

 <span data-ttu-id="a2a7d-187">Para obter mais informações sobre o arquivo de configuração, confira [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="a2a7d-187">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span>

 <span data-ttu-id="a2a7d-188">O script inclui a lógica de atraso "`Start-Sleep -s 6`" para que haja tempo após o evento ser acionado e para que o status atualizado fique disponível com o método ListSubscription.</span><span class="sxs-lookup"><span data-stu-id="a2a7d-188">The script includes delay logic "`Start-Sleep -s 6`" so there is time after the event fires, for the updated status to be available with the ListSubscription method.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="a2a7d-189">Sintaxe do modo nativo</span><span class="sxs-lookup"><span data-stu-id="a2a7d-189">Native mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/reportserver" $null "70366e82-2d3c-4edd-a216-b97e51e26de9"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="a2a7d-190">Sintaxe do modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="a2a7d-190">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/_vti_bin/reportserver" "http://[server]" "c3425c72-580d-423e-805a-41cf9799fd25"
```

### <a name="script"></a><span data-ttu-id="a2a7d-191">Script</span><span class="sxs-lookup"><span data-stu-id="a2a7d-191">Script</span></span>

```powershell
# Parameters
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site           - use $null for a native mode server
#    subscriptionid - subscription guid

Param(
  [string]$server,
  [string]$site,
  [string]$subscriptionid
  )

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
#event type is case sensative to what is in the rsreportserver.config
$rs2010.FireEvent("TimedSubscription",$subscriptionid,$site)

Write-Host " "
Write-Host "----- Subscription ($subscriptionid) status: "
#get list of subscriptions and filter to the specific ID to see the Status and LastExecuted
Start-Sleep -s 6 # slight delay in processing so ListSubscription returns the updated Status and LastExecuted
$subscriptions = $rs2010.ListSubscriptions($site); 
$subscriptions | select Status, Path, report, Description, Owner, SubscriptionID, EventType, lastexecuted | where {$_.SubscriptionID -eq $subscriptionid}
```

## <a name="see-also"></a><span data-ttu-id="a2a7d-192">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2a7d-192">See Also</span></span>
 <span data-ttu-id="a2a7d-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="a2a7d-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span> 
 <xref:ReportService2010.ReportingService2010.ListChildren%2A> 
 <xref:ReportService2010.ReportingService2010.FireEvent%2A>
