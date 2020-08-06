---
title: Script e PowerShell com o Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services]
- Reporting Services, scripting
- scripting [Reporting Services]
ms.assetid: 1ac2646d-ed5a-4436-b18f-2150c33f3d87
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a7a8dc805351897c11202467ed8bcb0373ef77c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575020"
---
# <a name="scripting-and-powershell-with-reporting-services"></a><span data-ttu-id="63176-102">Script e PowerShell com o Reporting Services</span><span class="sxs-lookup"><span data-stu-id="63176-102">Scripting and PowerShell with Reporting Services</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="63176-103">dá suporte a uma ampla variedade de cenários de desenvolvimento e gerenciamento por meio de script, incluindo o utilitário de linha de comando rs.exe, os cmdlets do PowerShell para servidores de relatório no modo SharePoint e aproveitando o modelo de objeto [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] do PowerShell para os modos nativo e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="63176-103">supports a wide range of development and management scenarios through script, including the rs.exe command line utility, PowerShell cmdlets for SharePoint mode report servers, and leveraging the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] object model from PowerShell for both Native and SharePoint mode.</span></span>

-   <span data-ttu-id="63176-104">Os administradores podem escrever o script no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] para automatizar o modo como eles implantam e gerenciam uma instalação do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="63176-104">Administrators can write script in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] to automate how they deploy and manage a report server installation.</span></span> <span data-ttu-id="63176-105">Os administradores também podem gerar e executar scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] que criam, configuram e atualizam um banco de dados de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="63176-105">Administrators can also generate and run [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that create, configure, and update a report server database.</span></span> <span data-ttu-id="63176-106">Os administradores também podem usar o registro e os recursos de script de reprodução no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para automatizar tarefas de manutenção de rotina.</span><span class="sxs-lookup"><span data-stu-id="63176-106">Administrators can also use the record and playback script features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to automate routine maintenance tasks.</span></span>

-   <span data-ttu-id="63176-107">Os desenvolvedores podem criar aplicativos personalizados que incluem script.</span><span class="sxs-lookup"><span data-stu-id="63176-107">Developers can create custom applications that include script.</span></span> <span data-ttu-id="63176-108">Você pode executar o script que faz chamadas ao serviço Web Servidor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="63176-108">You can run script that makes calls to the Report Server Web service.</span></span> <span data-ttu-id="63176-109">Quase qualquer operação que pode ser escrita em código gerenciado também pode ser escrita em script.</span><span class="sxs-lookup"><span data-stu-id="63176-109">Almost any operation that you can write in managed code can also be written in script.</span></span>

-   [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="63176-110">é compatível com o script .NET do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] como a linguagem de script que pode ser processada pelo utilitário RS.exe, um host de script que é executado no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="63176-110">supports [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET script as the script language that can be processed by the RS.exe utility, a script host that runs on the report server.</span></span>

## <a name="reporting-services-sharepoint-mode-powershell-cmdlets-and-samples"></a><span data-ttu-id="63176-111">Exemplos e cmdlets do PowerShell do modo SharePoint do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="63176-111">Reporting Services SharePoint mode PowerShell cmdlets and samples</span></span>
 <span data-ttu-id="63176-112">![Conteúdo relacionado ao PowerShell](../media/rs-powershellicon.jpg "Conteúdo relacionado ao PowerShell")</span><span class="sxs-lookup"><span data-stu-id="63176-112">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="63176-113">O modo SharePoint inclui cmdlets [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] para administração do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="63176-113">SharePoint mode includes [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] cmdlets for report server administration.</span></span>

-   <span data-ttu-id="63176-114">[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) Inclui os seguintes exemplos:</span><span class="sxs-lookup"><span data-stu-id="63176-114">[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) Includes the following examples:</span></span>

    -   <span data-ttu-id="63176-115">Criar um aplicativo de serviço e proxy</span><span class="sxs-lookup"><span data-stu-id="63176-115">Create a service application and proxy</span></span>

    -   <span data-ttu-id="63176-116">Revisar e atualizar uma extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="63176-116">Review and update a delivery extension</span></span>

    -   <span data-ttu-id="63176-117">Obter e definir propriedades do Banco de dados do aplicativo Reporting Services como, por exemplo, limite de banco de dados</span><span class="sxs-lookup"><span data-stu-id="63176-117">Get and set Properties of the Reporting Service Application Database, for example database timeout</span></span>

    -   <span data-ttu-id="63176-118">Listar extensões de dados</span><span class="sxs-lookup"><span data-stu-id="63176-118">List Data Extensions</span></span>

## <a name="reporting-services-object-model-and-powershell-samples"></a><span data-ttu-id="63176-119">Modelo de objeto do Reporting Services e exemplos do Powershell</span><span class="sxs-lookup"><span data-stu-id="63176-119">Reporting Services Object model and Powershell samples</span></span>
 <span data-ttu-id="63176-120">![Conteúdo relacionado ao PowerShell](../media/rs-powershellicon.jpg "Conteúdo relacionado ao PowerShell")</span><span class="sxs-lookup"><span data-stu-id="63176-120">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 <span data-ttu-id="63176-121">O PowerShell chama o modelo de objeto principal e da maior parte válida do SharePoint e do modo nativo; por exemplo, o trabalho de migração, o trabalho de assinatura e mais exemplos relacionados para o trabalho de assinaturas no SQL15.</span><span class="sxs-lookup"><span data-stu-id="63176-121">PowerShell calling the core object model and for the most part valid for SharePoint and native mode, for example the migration work, subscription work, and more related samples for subscriptions work in SQL15.</span></span>

-   <span data-ttu-id="63176-122">[Usar o PowerShell para alterar e listar proprietários de assinatura do Reporting Services e executar uma assinatura](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="63176-122">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>

-   <span data-ttu-id="63176-123">[Utilize o PowerShell para criar uma VM do Azure com um servidor de relatório no modo nativo](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span><span class="sxs-lookup"><span data-stu-id="63176-123">[Use PowerShell to Create an Azure VM With a Native Mode Report Server](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span></span>

-   <span data-ttu-id="63176-124">Veja a seção "Acessar as classes WMI usando o PowerShell" em [Acessar o Provedor WMI do Reporting Services](access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="63176-124">See the section "Access the WMI classes using PowerShell" in [Access the Reporting Services WMI Provider](access-the-reporting-services-wmi-provider.md).</span></span>

-   <span data-ttu-id="63176-125">[Como administrar SSRS usando o PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/).scriptin</span><span class="sxs-lookup"><span data-stu-id="63176-125">[How to Administer SSRS using PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/).scriptin</span></span>

## <a name="rsexe-scripting-samples"></a><span data-ttu-id="63176-126">Exemplos de script RS.exe</span><span class="sxs-lookup"><span data-stu-id="63176-126">RS.exe scripting samples</span></span>

-   <span data-ttu-id="63176-127">[Reporting Services de exemplo rs.exe script para migrar conteúdo entre servidores de relatório](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="63176-127">[Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>

-   <span data-ttu-id="63176-128">Para obter exemplos adicionais de extensão, aplicativos e scripts, consulte [SQL Server Reporting Services Product Samples (Amostras do produto SQL Server Reporting Services)](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="63176-128">For additional script, application, and extension examples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>

## <a name="see-also"></a><span data-ttu-id="63176-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="63176-129">See Also</span></span>
 <span data-ttu-id="63176-130">[Utilitário deRS.exe &#40;SSRS&#41;](rs-exe-utility-ssrs.md) script de [implantação de script e tarefas administrativas](script-deployment-and-administrative-tasks.md) [com o utilitário rs.exe e o serviço Web](script-with-the-rs-exe-utility-and-the-web-service.md)</span><span class="sxs-lookup"><span data-stu-id="63176-130">[RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md) [Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) [Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md)</span></span>


