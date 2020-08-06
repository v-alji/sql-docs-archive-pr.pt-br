---
title: Instalar o ADOMD.NET em servidores front-end da Web executando a administração central | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2372180-e847-4cdb-b267-4befac3faf7e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 0d9f52bf612c4878a8dacd4f5acfdcc135ae115e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569836"
---
# <a name="install-adomdnet-on-web-front-end-servers-running-central-administration"></a><span data-ttu-id="eac13-102">Instalar o ADOMD.NET em servidores Web front-end executando a Administração Central</span><span class="sxs-lookup"><span data-stu-id="eac13-102">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>
  <span data-ttu-id="eac13-103">Se você instalar o PowerPivot para SharePoint em um farm que tenha a topologia de Administração Central, sem Serviços do Excel ou PowerPivot para SharePoint, baixe e instale a biblioteca cliente do Microsoft ADOMD.NET se quiser acesso completo aos relatórios internos no painel de gerenciamento PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="eac13-103">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="eac13-104">Alguns relatórios no painel usam ADOMD.NET para acessar dados internos que fornecem dados de relação sobre o processamento de consultas do PowerPivot e a integridade de servidor no farm.</span><span class="sxs-lookup"><span data-stu-id="eac13-104">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span>  
  
 <span data-ttu-id="eac13-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="eac13-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010</span></span>  
  
 <span data-ttu-id="eac13-106">Para o SharePoint 2013, o provedor é incluído no SQL Server feature pack.</span><span class="sxs-lookup"><span data-stu-id="eac13-106">For SharePoint 2013, the provider is included in the SQL Server feature pack.</span></span> <span data-ttu-id="eac13-107">Para obter informações sobre como baixar spPowerPivot.msi, consulte [Microsoft SQL Server Feature Pack 2014](https://www.microsoft.com/download/details.aspx?id=35577)</span><span class="sxs-lookup"><span data-stu-id="eac13-107">For information on how to download spPowerPivot.msi, see [Microsoft SQL Server 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=35577)</span></span>  
  
### <a name="download-and-install-the-client-library"></a><span data-ttu-id="eac13-108">Baixar e instalar a biblioteca de cliente</span><span class="sxs-lookup"><span data-stu-id="eac13-108">Download and install the client library</span></span>  
  
1.  <span data-ttu-id="eac13-109">Na [página SQL Server 2014 Feature Pack](https://go.microsoft.com/fwlink/?LinkID=296473), encontre Microsoft ADOMD.net.</span><span class="sxs-lookup"><span data-stu-id="eac13-109">On the [SQL Server 2014 Feature Pack page](https://go.microsoft.com/fwlink/?LinkID=296473), find Microsoft ADOMD.NET.</span></span>  
  
2.  <span data-ttu-id="eac13-110">Baixe o Pacote x64 do programa de instalação `SQL_AS_ADOMD.msi`.</span><span class="sxs-lookup"><span data-stu-id="eac13-110">Download the x64 Package of the `SQL_AS_ADOMD.msi` installation program.</span></span>  
  
3.  <span data-ttu-id="eac13-111">Execute o .msi para instalar a biblioteca.</span><span class="sxs-lookup"><span data-stu-id="eac13-111">Run the .msi to install the library.</span></span>  
  
4.  <span data-ttu-id="eac13-112">Reinicie o IIS após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="eac13-112">Reset IIS after installation is finished.</span></span> <span data-ttu-id="eac13-113">Abra um prompt de comando administrativo e digite **iisreset**.</span><span class="sxs-lookup"><span data-stu-id="eac13-113">Open an administrative command prompt and type **IISRESET**.</span></span>  
  
### <a name="verify-installation"></a><span data-ttu-id="eac13-114">Verifique a instalação</span><span class="sxs-lookup"><span data-stu-id="eac13-114">Verify installation</span></span>  
  
1.  <span data-ttu-id="eac13-115">Vá para Windows\Assembly.</span><span class="sxs-lookup"><span data-stu-id="eac13-115">Go to Windows\Assembly.</span></span>  
  
2.  <span data-ttu-id="eac13-116">Clique com o botão direito do mouse em Microsoft. AnalysisServices. AdomdClient e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="eac13-116">Right-click Microsoft.AnalysisServices.AdomdClient and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="eac13-117">Clique em **Versão**.</span><span class="sxs-lookup"><span data-stu-id="eac13-117">Click **Version**.</span></span>  
  
4.  <span data-ttu-id="eac13-118">Verifique se a versão inclui 12, 0.\<build number></span><span class="sxs-lookup"><span data-stu-id="eac13-118">Verify that the version includes 12.00.\<build number></span></span> <span data-ttu-id="eac13-119">e que a descrição é Microsoft. AnalysisService. AdomdClient.</span><span class="sxs-lookup"><span data-stu-id="eac13-119">and that the description is Microsoft.AnalysisService.AdomdClient.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac13-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eac13-120">See Also</span></span>  
 [<span data-ttu-id="eac13-121">Painel de Gerenciamento PowerPivot e dados de uso</span><span class="sxs-lookup"><span data-stu-id="eac13-121">PowerPivot Management Dashboard and Usage Data</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data)  
  
  
