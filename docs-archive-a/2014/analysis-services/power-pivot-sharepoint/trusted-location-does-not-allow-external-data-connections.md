---
title: 'O local confiável em que a pasta de trabalho é armazenada não permite conexões de dados externas. As seguintes conexões não foram atualizadas: dados PowerPivot | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: dc0cedfd-a7d0-40ef-bdd6-ea508130640a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b7f6d335eac0bec0f67012cc413f3917c50348b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568810"
---
# <a name="the-trusted-location-where-the-workbook-is-stored-does-not-allow-external-data-connections-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="ae541-103">O local confiável em que a pasta de trabalho é armazenada não permite conexões de dados externas.</span><span class="sxs-lookup"><span data-stu-id="ae541-103">The trusted location where the workbook is stored does not allow external data connections.</span></span> <span data-ttu-id="ae541-104">As conexões a seguir não foram atualizadas: Dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="ae541-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="ae541-105">Para pastas de trabalho do Excel que contenham dados PowerPivot, os Serviços do Excel retornarão este erro se não for possível conectar a fontes de dados inseridas.</span><span class="sxs-lookup"><span data-stu-id="ae541-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to embedded data sources.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ae541-106">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ae541-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae541-107">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="ae541-107">Applies to</span></span>|<span data-ttu-id="ae541-108">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="ae541-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="ae541-109">Versão do produto</span><span class="sxs-lookup"><span data-stu-id="ae541-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="ae541-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae541-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="ae541-111">Causa</span><span class="sxs-lookup"><span data-stu-id="ae541-111">Cause</span></span>|<span data-ttu-id="ae541-112">Os Serviços do Excel são configurados para negar acesso a dados externos.</span><span class="sxs-lookup"><span data-stu-id="ae541-112">Excel Services is configured to deny external data access.</span></span>|  
|<span data-ttu-id="ae541-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ae541-113">Message Text</span></span>|<span data-ttu-id="ae541-114">O local confiável em que a pasta de trabalho é armazenada não permite conexões de dados externas.</span><span class="sxs-lookup"><span data-stu-id="ae541-114">The trusted location where the workbook is stored does not allow external data connections.</span></span> <span data-ttu-id="ae541-115">As conexões a seguir não foram atualizadas: Dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="ae541-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ae541-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="ae541-116">Explanation</span></span>  
 <span data-ttu-id="ae541-117">As pastas de trabalho PowerPivot contêm conexões de dados inseridas.</span><span class="sxs-lookup"><span data-stu-id="ae541-117">PowerPivot workbooks contain embedded data connections.</span></span> <span data-ttu-id="ae541-118">Para dar suporte à interação de pastas de trabalho por slicers e filtros, os Serviços do Excel devem ser configurados para permitir acesso a dados externos por informações de conexão inseridas.</span><span class="sxs-lookup"><span data-stu-id="ae541-118">To support workbook interaction through slicers and filters, Excel Services must be configured to allow external data access through embedded connection information.</span></span> <span data-ttu-id="ae541-119">O acesso a dados externos é necessário para recuperar dados PowerPivot carregados em servidores PowerPivot no farm.</span><span class="sxs-lookup"><span data-stu-id="ae541-119">External data access is required for retrieving PowerPivot data that is loaded on PowerPivot servers in the farm.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ae541-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ae541-120">User Action</span></span>  
 <span data-ttu-id="ae541-121">Altere as definições de configuração para permitir fontes de dados inseridas.</span><span class="sxs-lookup"><span data-stu-id="ae541-121">Change the configuration settings to allow embedded data sources.</span></span>  
  
1.  <span data-ttu-id="ae541-122">Na Administração Central, em Gerenciamento de Aplicativo, clique em **Gerenciar aplicativos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="ae541-122">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="ae541-123">Clique em **Aplicativo dos Serviços do Excel**.</span><span class="sxs-lookup"><span data-stu-id="ae541-123">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="ae541-124">Clique em **Local de Arquivo Confiável**.</span><span class="sxs-lookup"><span data-stu-id="ae541-124">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="ae541-125">Clique em **http://** ou no local que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="ae541-125">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="ae541-126">Em Dados Externos, em Permitir Dados Externos, clique em **Bibliotecas de conexões de dados confiáveis e incorporadas**.</span><span class="sxs-lookup"><span data-stu-id="ae541-126">In External Data, in Allow External Data, click **Trusted data connection libraries and embedded**.</span></span>  
  
6.  <span data-ttu-id="ae541-127">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae541-127">Click **OK**.</span></span>  
  
 <span data-ttu-id="ae541-128">Também é possível criar um novo local confiável para sites que contenham pastas de trabalho PowerPivot e, em seguida, modificar os parâmetros de configuração apenas para esse site.</span><span class="sxs-lookup"><span data-stu-id="ae541-128">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="ae541-129">Para obter mais informações, consulte [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="ae541-129">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  