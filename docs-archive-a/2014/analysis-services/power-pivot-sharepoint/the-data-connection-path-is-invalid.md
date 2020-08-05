---
title: 'O caminho de conexão de dados na pasta de trabalho aponta para um arquivo na unidade local ou é um URI inválido. As seguintes conexões não foram atualizadas: dados PowerPivot | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bd22e41a-0931-4d32-888a-633a3046fc5e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3349af08290e2ff659db1441d849b2afef51e95b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573313"
---
# <a name="the-data-connection-path-in-the-workbook-points-to-a-file-on-the-local-drive-or-is-an-invalid-uri-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="07931-103">O caminho de conexão de dados na pasta de trabalho aponta para um arquivo na unidade local ou é um URI inválido.</span><span class="sxs-lookup"><span data-stu-id="07931-103">The data connection path in the workbook points to a file on the local drive or is an invalid URI.</span></span> <span data-ttu-id="07931-104">As conexões a seguir não foram atualizadas: Dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="07931-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="07931-105">Para pastas de trabalho do Excel que contenham dados PowerPivot, os Serviços do Excel retornarão este erro se não for possível conectar a fontes de dados inseridas.</span><span class="sxs-lookup"><span data-stu-id="07931-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to embedded data sources.</span></span>  
  
## <a name="details"></a><span data-ttu-id="07931-106">Detalhes</span><span class="sxs-lookup"><span data-stu-id="07931-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07931-107">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="07931-107">Applies to</span></span>|<span data-ttu-id="07931-108">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="07931-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="07931-109">Versão do produto</span><span class="sxs-lookup"><span data-stu-id="07931-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="07931-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07931-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="07931-111">Causa</span><span class="sxs-lookup"><span data-stu-id="07931-111">Cause</span></span>|<span data-ttu-id="07931-112">Os Serviços do Excel são configurados para permitir somente conexões de dados de arquivos .odc arquivos que estejam em uma biblioteca de conexões de dados confiável.</span><span class="sxs-lookup"><span data-stu-id="07931-112">Excel Services is configured to only allow data connections from .odc files that are in a trusted data connection library.</span></span>|  
|<span data-ttu-id="07931-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="07931-113">Message Text</span></span>|<span data-ttu-id="07931-114">O caminho de conexão de dados na pasta de trabalho aponta para um arquivo na unidade local ou é um URI inválido.</span><span class="sxs-lookup"><span data-stu-id="07931-114">The data connection path in the workbook points to a file on the local drive or is an invalid URI.</span></span> <span data-ttu-id="07931-115">As conexões a seguir não foram atualizadas: Dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="07931-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="07931-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="07931-116">Explanation</span></span>  
 <span data-ttu-id="07931-117">As pastas de trabalho PowerPivot contêm conexões de dados inseridas.</span><span class="sxs-lookup"><span data-stu-id="07931-117">PowerPivot workbooks contain embedded data connections.</span></span> <span data-ttu-id="07931-118">Para dar suporte à interação de pastas de trabalho por slicers e filtros, os Serviços do Excel devem ser configurados para permitir acesso a dados externos por informações de conexão inseridas.</span><span class="sxs-lookup"><span data-stu-id="07931-118">To support workbook interaction through slicers and filters, Excel Services must be configured to allow external data access through embedded connection information.</span></span> <span data-ttu-id="07931-119">O acesso a dados externos é necessário para recuperar dados PowerPivot carregados em servidores PowerPivot no farm.</span><span class="sxs-lookup"><span data-stu-id="07931-119">External data access is required for retrieving PowerPivot data that is loaded on PowerPivot servers in the farm.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07931-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="07931-120">User Action</span></span>  
 <span data-ttu-id="07931-121">Altere as definições de configuração para permitir conexões de fontes de dados inseridas.</span><span class="sxs-lookup"><span data-stu-id="07931-121">Change the configuration settings to allow embedded data source connections.</span></span>  
  
1.  <span data-ttu-id="07931-122">Na Administração Central, em Gerenciamento de Aplicativo, clique em **Gerenciar aplicativos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="07931-122">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="07931-123">Clique em **Aplicativo dos Serviços do Excel**.</span><span class="sxs-lookup"><span data-stu-id="07931-123">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="07931-124">Clique em **Local de Arquivo Confiável**.</span><span class="sxs-lookup"><span data-stu-id="07931-124">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="07931-125">Clique em **http://** ou no local que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="07931-125">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="07931-126">Em Dados Externos, em Permitir Dados Externos, clique em **Bibliotecas de conexões de dados confiáveis e incorporadas**.</span><span class="sxs-lookup"><span data-stu-id="07931-126">In External Data, in Allow External Data, click **Trusted data connection libraries and embedded**.</span></span>  
  
6.  <span data-ttu-id="07931-127">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="07931-127">Click **OK**.</span></span>  
  
 <span data-ttu-id="07931-128">Também é possível criar um novo local confiável para sites que contenham pastas de trabalho PowerPivot e, em seguida, modificar os parâmetros de configuração apenas para esse site.</span><span class="sxs-lookup"><span data-stu-id="07931-128">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="07931-129">Para obter mais informações, consulte [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="07931-129">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
