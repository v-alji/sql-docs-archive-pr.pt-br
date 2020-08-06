---
title: Publicar relatórios | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], publishing
- publishing reports [Reporting Services]
ms.assetid: ef5a514e-e818-4041-a8b0-15835f9a046b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb54308a6b15260d4c336950f231d0ee40836430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569169"
---
# <a name="publish-reports"></a><span data-ttu-id="6069d-102">Publicar Relatórios</span><span class="sxs-lookup"><span data-stu-id="6069d-102">Publish Reports</span></span>
  <span data-ttu-id="6069d-103">No[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], é possível publicar todos os relatórios e fontes de dados compartilhadas em um projeto do Servidor de Relatório implantando um projeto ou publicar um único relatório.</span><span class="sxs-lookup"><span data-stu-id="6069d-103">From[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can publish either all the reports and shared data sources in a Report Server project to a report server by deploying the project, or you can publish a single report.</span></span> <span data-ttu-id="6069d-104">Antes de publicar um relatório, você deve especificar a URL do servidor de relatório de destino.</span><span class="sxs-lookup"><span data-stu-id="6069d-104">Before you can publish a report you must specify the URL of the target report server.</span></span> <span data-ttu-id="6069d-105">Para obter mais informações, consulte [Definir propriedades de implantação &#40;Reporting Services&#41;](tools/set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="6069d-105">For more information, see [Set Deployment Properties &#40;Reporting Services&#41;](tools/set-deployment-properties-reporting-services.md).</span></span>  
  
 <span data-ttu-id="6069d-106">Você pode usar a versão do [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para abrir, modificar, visualizar, salvar e publicar relatórios do [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] e do [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6069d-106">You can use the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] version of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to open, modify, preview, save, and publish both [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] and [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] reports.</span></span> <span data-ttu-id="6069d-107">Para obter mais informações, veja [Implantação e suporte de versão no SQL Server Data Tools &#40;SSRS&#41;](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6069d-107">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
### <a name="to-publish-all-reports-in-a-project"></a><span data-ttu-id="6069d-108">Para publicar todos os relatórios em um projeto</span><span class="sxs-lookup"><span data-stu-id="6069d-108">To publish all reports in a project</span></span>  
  
-   <span data-ttu-id="6069d-109">No menu **Compilar** , clique em \*\*implantar \<report project name> \*\*.</span><span class="sxs-lookup"><span data-stu-id="6069d-109">On the **Build** menu, click **Deploy \<report project name>**.</span></span> <span data-ttu-id="6069d-110">Como alternativa, no Gerenciador de Soluções, clique com o botão direito do mouse no projeto de relatório e clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="6069d-110">Alternatively, in Solution Explorer, right-click the report project and then click **Deploy**.</span></span> <span data-ttu-id="6069d-111">Você pode visualizar o status do processo de publicação na janela Saída.</span><span class="sxs-lookup"><span data-stu-id="6069d-111">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6069d-112">Quando você implantar um projeto do Servidor de Relatório, também são implantadas as fontes de dados compartilhadas no projeto de relatório.</span><span class="sxs-lookup"><span data-stu-id="6069d-112">When you deploy a Report Server project, the shared data sources in the report project are also deployed.</span></span>  
  
### <a name="to-publish-a-single-report"></a><span data-ttu-id="6069d-113">Para publicar um relatório simples</span><span class="sxs-lookup"><span data-stu-id="6069d-113">To publish a single report</span></span>  
  
-   <span data-ttu-id="6069d-114">No Gerenciador de Soluções, clique com o botão direito do mouse no relatório e clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="6069d-114">In Solution Explorer, right-click the report and then click **Deploy**.</span></span> <span data-ttu-id="6069d-115">Você pode visualizar o status do processo de publicação na janela Saída.</span><span class="sxs-lookup"><span data-stu-id="6069d-115">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6069d-116">Quando você publica um relatório, também precisa implantar as fontes de dados compartilhadas que o relatório usa.</span><span class="sxs-lookup"><span data-stu-id="6069d-116">When you publish a report, you must also deploy the shared data sources that the report uses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6069d-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6069d-117">See Also</span></span>  
 <span data-ttu-id="6069d-118">[Publicando fontes de dados e relatórios](reports/publishing-data-sources-and-reports.md) </span><span class="sxs-lookup"><span data-stu-id="6069d-118">[Publishing Data Sources and Reports](reports/publishing-data-sources-and-reports.md) </span></span>  
 <span data-ttu-id="6069d-119">[Visualizando relatórios](reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="6069d-119">[Previewing Reports](reports/previewing-reports.md) </span></span>  
 <span data-ttu-id="6069d-120">[Publicando relatórios em um servidor de relatório](reports/publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="6069d-120">[Publishing Reports to a Report Server](reports/publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="6069d-121">[Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6069d-121">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6069d-122">Exportando relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6069d-122">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](report-builder/export-reports-report-builder-and-ssrs.md)  
  
  
