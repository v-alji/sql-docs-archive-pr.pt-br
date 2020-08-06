---
title: 'Erro ao tentar estabelecer uma conexão com a fonte de dados externa. As seguintes conexões não foram atualizadas: dados PowerPivot | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1b951da1-f62d-43d2-b40b-270a4a9ab92c
author: minewiskan
ms.author: owend
ms.openlocfilehash: eb4329440b69d1bdfdbb96fbcc3926fa000d8877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680660"
---
# <a name="an-error-occurred-during-an-attempt-to-establish-a-connection-to-the-external-data-source-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="a240f-103">Erro ao tentar estabelecer uma conexão com a fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="a240f-103">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="a240f-104">As conexões a seguir não foram atualizadas: Dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="a240f-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="a240f-105">Esse erro ocorrerá se você consultar dados PowerPivot em um servidor que não tenha o PowerPivot para SharePoint instalado.</span><span class="sxs-lookup"><span data-stu-id="a240f-105">This error occurs if you query PowerPivot data on a server that does not have PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="a240f-106">Isso também ocorrerá se o serviço do SQL Server Analysis Services (PowerPivot) for parado, ou se você estiver tentando exibir dados PowerPivot de uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="a240f-106">It also occurs if the SQL Server Analysis Services (PowerPivot) service is stopped, or if you are attempting to view PowerPivot data from an earlier version.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a240f-107">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a240f-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a240f-108">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="a240f-108">Applies to</span></span>|<span data-ttu-id="a240f-109">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="a240f-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="a240f-110">Versão do produto</span><span class="sxs-lookup"><span data-stu-id="a240f-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="a240f-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a240f-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="a240f-112">Causa</span><span class="sxs-lookup"><span data-stu-id="a240f-112">Cause</span></span>|<span data-ttu-id="a240f-113">Falha na conexão de dados.</span><span class="sxs-lookup"><span data-stu-id="a240f-113">The data connection failed.</span></span>|  
|<span data-ttu-id="a240f-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a240f-114">Message Text</span></span>|<span data-ttu-id="a240f-115">Erro ao tentar estabelecer uma conexão com a fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="a240f-115">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="a240f-116">As conexões a seguir não foram atualizadas: Dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="a240f-116">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a240f-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="a240f-117">Explanation</span></span>  
 <span data-ttu-id="a240f-118">Os Serviços do Excel retornam esse erro quando você consulta dados PowerPivot em uma pasta de trabalho do Excel que é publicada no SharePoint, e o ambiente do SharePoint não tem um servidor PowerPivot para SharePoint, ou se o serviço do SQL Server Analysis Services (PowerPivot) é interrompido.</span><span class="sxs-lookup"><span data-stu-id="a240f-118">Excel Services returns this error when you query PowerPivot data in an Excel workbook that is published to SharePoint, and the SharePoint environment does not have a PowerPivot for SharePoint server, or the SQL Server Analysis Services (PowerPivot) service is stopped.</span></span>  
  
 <span data-ttu-id="a240f-119">O erro ocorre quando você segmenta ou filtra dados PowerPivot quando o mecanismo de consulta não está disponível.</span><span class="sxs-lookup"><span data-stu-id="a240f-119">The error occurs when you slice or filter PowerPivot data when the query engine is not available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a240f-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a240f-120">User Action</span></span>  
 <span data-ttu-id="a240f-121">Instale o PowerPivot para SharePoint ou mova a pasta de trabalho PowerPivot para um ambiente do SharePoint que tenha o PowerPivot para SharePoint instalado.</span><span class="sxs-lookup"><span data-stu-id="a240f-121">Install PowerPivot for SharePoint or move the PowerPivot workbook to a SharePoint environment that has PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="a240f-122">Para obter mais informações, consulte [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span><span class="sxs-lookup"><span data-stu-id="a240f-122">For more information, see [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span></span>  
  
 <span data-ttu-id="a240f-123">Se o software estiver instalado, verifique se a instância do SQL Server Analysis Services (PowerPivot) está em execução.</span><span class="sxs-lookup"><span data-stu-id="a240f-123">If the software is installed, verify that the SQL Server Analysis Services (PowerPivot) instance is running.</span></span> <span data-ttu-id="a240f-124">Selecione **Gerenciar serviços no servidor** na Administração Central.</span><span class="sxs-lookup"><span data-stu-id="a240f-124">Check **Manage services on server** in Central Administration.</span></span> <span data-ttu-id="a240f-125">Além disso, verifique o aplicativo de console Serviços em Ferramentas Administrativas.</span><span class="sxs-lookup"><span data-stu-id="a240f-125">Also check the Services console application in Administrative Tools.</span></span>  
  
 <span data-ttu-id="a240f-126">Para pastas de trabalho PowerPivot que foram criadas em uma versão do SQL Server 2008 R2 do PowerPivot para Excel, você deve instalar a versão do SQL Server 2008 R2 do provedor OLE DB do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a240f-126">For PowerPivot workbooks that were created in a SQL Server 2008 R2 version of PowerPivot for Excel, you must install the SQL Server 2008 R2 version of the Analysis Services OLE DB provider.</span></span> <span data-ttu-id="a240f-127">Esse erro ocorrerá se você instalar o provedor, mas não registrar o arquivo Microsoft.AnalysisServices.ChannelTransport.dll.</span><span class="sxs-lookup"><span data-stu-id="a240f-127">This error will occur if you installed the provider, but did not register the Microsoft.AnalysisServices.ChannelTransport.dll file.</span></span> <span data-ttu-id="a240f-128">Para saber mais, veja [Instalar o provedor OLE DB do Analysis Services nos servidores do SharePoint](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="a240f-128">For more information about file registration, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a240f-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a240f-129">See Also</span></span>  
 [<span data-ttu-id="a240f-130">A conexão de dados usa a autenticação do Windows e as credenciais do usuário não puderam ser delegadas. Falha ao atualizar as seguintes conexões: dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="a240f-130">The data connection uses Windows Authentication and user credentials could not be delegated. The following connections failed to refresh: PowerPivot Data</span></span>](the-data-connection-user-could-not-be-delegated.md)  
  
  
