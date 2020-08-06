---
title: Adicionar MSOLAP. 5 como um Provedor de Dados confiável nos serviços do Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1f40fa4-de6d-41ee-8124-14b4d65988f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 876ec613f18b2d91b5e06ab5fed4a7b258c30a36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582163"
---
# <a name="add-msolap5-as-a-trusted-data-provider-in-excel-services"></a><span data-ttu-id="66657-102">Adicionar MSOLAP.5 como um provedor de dados confiável em Serviços do Excel</span><span class="sxs-lookup"><span data-stu-id="66657-102">Add MSOLAP.5 as a Trusted Data Provider in Excel Services</span></span>
  <span data-ttu-id="66657-103">MSOLAP.5 se refere ao provedor OLE DB do Analysis Services para SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="66657-103">MSOLAP.5 refers to the Analysis Services OLE DB provider for SQL Server 2012.</span></span> <span data-ttu-id="66657-104">Os Serviços do Excel devem confiar neste provedor antes de fazer a solicitação de conexão que resulta na disponibilidade de dados PowerPivot em um servidor.</span><span class="sxs-lookup"><span data-stu-id="66657-104">Excel Services must trust this provider before it will make the connection request that results in the availability of PowerPivot data on a server.</span></span>  
  
 <span data-ttu-id="66657-105">Se você configurou o PowerPivot para SharePoint usando a Ferramenta de Configuração do PowerPivot, o MSOLAP.5 já poderá ser um provedor de confiança porque a ferramenta inclui uma ação que atende a este requisito.</span><span class="sxs-lookup"><span data-stu-id="66657-105">If you configured PowerPivot for SharePoint using the PowerPivot Configuration Tool, MSOLAP.5 might already be a trusted provider because the tool includes an action that satisfies this requirement.</span></span> <span data-ttu-id="66657-106">No entanto, se você estiver usando o PowerShell, a Administração Central ou caso tenha excluído a ação do provedor confiável na ferramenta de configuração, o provedor deverá estar faltando e, nesse caso, você deverá adicioná-lo agora como parte da configuração do farm para o acesso a dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="66657-106">However, if you are using PowerShell, Central Administration, or if you excluded the trusted provider action in the configuration tool, the provider might be missing, which case you should add it now as part of configuring the farm for PowerPivot data access.</span></span>  
  
 <span data-ttu-id="66657-107">somente é necessário executar essa etapa uma vez para cada aplicativo de serviço de Serviços do Excel.</span><span class="sxs-lookup"><span data-stu-id="66657-107">You only need to perform this step once for each Excel Services service application.</span></span>  
  
 <span data-ttu-id="66657-108">Todo servidor físico que manipula uma solicitação de dados PowerPivot, como um servidor PowerPivot para SharePoint ou um servidor de Serviços do Excel, deve ter o provedor OLE DB instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="66657-108">Each physical server that handles a PowerPivot data request, such as a PowerPivot for SharePoint server or an Excel Services server, must have the OLE DB provider installed on the computer.</span></span> <span data-ttu-id="66657-109">Uma instalação do PowerPivot para SharePoint sempre inclui o provedor OLE DB, mas se os Serviços do Excel estiverem sendo executados em um computador que não tenha o PowerPivot para SharePoint, deverá instalar o provedor manualmente.</span><span class="sxs-lookup"><span data-stu-id="66657-109">A PowerPivot for SharePoint installation always includes the OLE DB provider, but if Excel Services is running on a computer that does not have PowerPivot for SharePoint, you must install the provider manually.</span></span> <span data-ttu-id="66657-110">Para obter mais informações, consulte [Instalar o Provedor OLE DB do Analysis Services nos Servidores SharePoint](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="66657-110">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="add-a-trusted-provider-to-excel-services"></a><span data-ttu-id="66657-111">Adicionar um provedor confiável aos Serviços do Excel</span><span class="sxs-lookup"><span data-stu-id="66657-111">Add a trusted provider to Excel Services</span></span>  
  
1.  <span data-ttu-id="66657-112">Na Administração Central, clique em **Gerenciar aplicativos de serviço**e clique no aplicativo de serviço de Serviços do Excel.</span><span class="sxs-lookup"><span data-stu-id="66657-112">In Central Administration, click **Manage service applications**, and then click the Excel Services service application.</span></span>  
  
2.  <span data-ttu-id="66657-113">Clique em **Provedores de Dados Confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="66657-113">Click **Trusted Data Providers**.</span></span>  
  
3.  <span data-ttu-id="66657-114">Verifique se MSOLAP.5 aparece na lista.</span><span class="sxs-lookup"><span data-stu-id="66657-114">Verify that MSOLAP.5 appears in the list.</span></span> <span data-ttu-id="66657-115">Dependendo do modo como você configurou o PowerPivot para SharePoint, o MSOLAP.5 talvez já seja confiável.</span><span class="sxs-lookup"><span data-stu-id="66657-115">Depending on how you configured PowerPivot for SharePoint, MSOLAP.5 might already be trusted.</span></span>  
  
4.  <span data-ttu-id="66657-116">Se esse item não estiver na lista, clique em **Adicionar Provedor de Dados Confiável**.</span><span class="sxs-lookup"><span data-stu-id="66657-116">If it is not listed, click **Add Trusted Data Provider**.</span></span>  
  
5.  <span data-ttu-id="66657-117">Na ID do Provedor, digite `MSOLAP.5`.</span><span class="sxs-lookup"><span data-stu-id="66657-117">In Provider ID, type `MSOLAP.5`.</span></span>  
  
6.  <span data-ttu-id="66657-118">Em Tipo de Provedor, verifique se a opção OLE DB está selecionada.</span><span class="sxs-lookup"><span data-stu-id="66657-118">For Provider Type, ensure that OLE DB is selected.</span></span>  
  
7.  <span data-ttu-id="66657-119">Na Descrição do Provedor, digite **Microsoft OLE DB Provider for OLAP Services 11.0**.</span><span class="sxs-lookup"><span data-stu-id="66657-119">In Provider Description, type **Microsoft OLE DB Provider for OLAP Services 11.0**.</span></span>  
  
  
