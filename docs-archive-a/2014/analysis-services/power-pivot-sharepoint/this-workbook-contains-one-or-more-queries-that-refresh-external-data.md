---
title: Esta pasta de trabalho contém uma ou mais consultas que atualizam dados externos. | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aa65c992-eb41-4032-9e11-a9ba871b6a3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b2095e13d6151c68eb4a3507400dfdb1739564
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573314"
---
# <a name="this-workbook-contains-one-or-more-queries-that-refresh-external-data"></a><span data-ttu-id="65b67-103">Esta pasta de trabalho contém uma ou mais consultas que atualizam dados externos.</span><span class="sxs-lookup"><span data-stu-id="65b67-103">This workbook contains one or more queries that refresh external data.</span></span>
  <span data-ttu-id="65b67-104">Para pastas de trabalho do Excel que contêm dados PowerPivot, os Serviços do Excel mostram este aviso quando detectam informações de conexão e solicitam que você habilite ou desabilite consultas para essa pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="65b67-104">For Excel workbooks that contain PowerPivot data, Excel Services shows this warning when it detects connection information and prompts you to enable or disable queries for this workbook.</span></span>  
  
## <a name="details"></a><span data-ttu-id="65b67-105">Detalhes</span><span class="sxs-lookup"><span data-stu-id="65b67-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="65b67-106">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="65b67-106">Product Name</span></span>|<span data-ttu-id="65b67-107">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="65b67-107">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="65b67-108">Versão do produto</span><span class="sxs-lookup"><span data-stu-id="65b67-108">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="65b67-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65b67-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="65b67-110">Causa</span><span class="sxs-lookup"><span data-stu-id="65b67-110">Cause</span></span>|<span data-ttu-id="65b67-111">Os Serviços do Excel são configurados para avisar na atualização de dados.</span><span class="sxs-lookup"><span data-stu-id="65b67-111">Excel Services is configured to warn on data refresh.</span></span>|  
|<span data-ttu-id="65b67-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="65b67-112">Message Text</span></span>|<span data-ttu-id="65b67-113">Esta pasta de trabalho contém uma ou mais consultas que atualizam dados externos.</span><span class="sxs-lookup"><span data-stu-id="65b67-113">This workbook contains one or more queries that refresh external data.</span></span> <span data-ttu-id="65b67-114">Um usuário mal-intencionado pode criar uma consulta para acessar informações confidenciais e distribuí-las a outros usuários ou pode executar outras ações prejudiciais.</span><span class="sxs-lookup"><span data-stu-id="65b67-114">A malicious user can design a query to access confidential information and distribute it to other users or perform other harmful actions.</span></span><br /><br /> <span data-ttu-id="65b67-115">Se você confiar na origem dessa pasta de trabalho, clique em Sim para habilitar consultas a dados externos nessa pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="65b67-115">If you trust the source of this workbook, click Yes to enable queries to external data in this workbook.</span></span> <span data-ttu-id="65b67-116">Se você não tiver certeza, clique em Não para que as alterações não sejam aplicados em sua pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="65b67-116">If you are not sure, click No so that changes are not applied to your workbook.</span></span><br /><br /> <span data-ttu-id="65b67-117">Você deseja habilitar consultas a dados externos nesta pasta de trabalho?</span><span class="sxs-lookup"><span data-stu-id="65b67-117">Do you want to enable queries to external data in this workbook?</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="65b67-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="65b67-118">Explanation</span></span>  
 <span data-ttu-id="65b67-119">As pastas de trabalho PowerPivot contêm cadeias de conexão de dados incorporadas usadas pelo Excel para se comunicar com um servidor PowerPivot externo que carrega e calcula os dados.</span><span class="sxs-lookup"><span data-stu-id="65b67-119">PowerPivot workbooks contain embedded data connection strings that are used by Excel to communicate with an external PowerPivot server that loads and calculates the data.</span></span> <span data-ttu-id="65b67-120">Quando o aviso na atualização de dados estiver habilitado, o Serviços do Excel detectará essa cadeia de conexão e avisará o usuário.</span><span class="sxs-lookup"><span data-stu-id="65b67-120">When warn on data refresh is enabled, Excel Services detects this connection string and warns the user accordingly.</span></span>  
  
 <span data-ttu-id="65b67-121">Para filtrar e dividir dados PowerPivot na pasta de trabalho, as consultas devem ser habilitadas.</span><span class="sxs-lookup"><span data-stu-id="65b67-121">To filter and slice PowerPivot data in the workbook, queries must be enabled.</span></span> <span data-ttu-id="65b67-122">Certifique-se de habilitar consultas apenas para as pastas de trabalho PowerPivot nas que você confia.</span><span class="sxs-lookup"><span data-stu-id="65b67-122">Be sure that you enable queries for only those PowerPivot workbooks that you trust.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="65b67-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="65b67-123">User Action</span></span>  
 <span data-ttu-id="65b67-124">Clique em **Sim** para habilitar consultas.</span><span class="sxs-lookup"><span data-stu-id="65b67-124">Click **Yes** to enable queries.</span></span>  
  
 <span data-ttu-id="65b67-125">Você também pode alterar os parâmetros de configuração para que o aviso na atualização não ocorra mais:</span><span class="sxs-lookup"><span data-stu-id="65b67-125">You can also change the configuration settings so that warn on refresh no longer occurs:</span></span>  
  
1.  <span data-ttu-id="65b67-126">Na Administração Central, em Gerenciamento de Aplicativo, clique em **Gerenciar aplicativos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="65b67-126">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="65b67-127">Clique em **Aplicativo dos Serviços do Excel**.</span><span class="sxs-lookup"><span data-stu-id="65b67-127">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="65b67-128">Clique em **Local de Arquivo Confiável**.</span><span class="sxs-lookup"><span data-stu-id="65b67-128">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="65b67-129">Clique em **http://** ou no local que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="65b67-129">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="65b67-130">Em Dados Externos, desmarque a caixa de seleção para **Avisar na atualização de dados**.</span><span class="sxs-lookup"><span data-stu-id="65b67-130">In External Data, clear the checkbox for **Warn on data refresh**.</span></span>  
  
6.  <span data-ttu-id="65b67-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b67-131">Click **OK**.</span></span>  
  
 <span data-ttu-id="65b67-132">Também é possível criar um novo local confiável para sites que contenham pastas de trabalho PowerPivot e, em seguida, modificar os parâmetros de configuração apenas para esse site.</span><span class="sxs-lookup"><span data-stu-id="65b67-132">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="65b67-133">Para obter mais informações, consulte [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="65b67-133">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
