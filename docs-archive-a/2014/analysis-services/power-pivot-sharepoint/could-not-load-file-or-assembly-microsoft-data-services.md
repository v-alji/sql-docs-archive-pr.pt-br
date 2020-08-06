---
title: Não foi possível carregar o arquivo ou assembly &#39;Microsoft. AnalysisServices. SharePoint. Integration&#39; | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6e350b67-5e18-4b90-8fb7-a0109cbb27b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: b7ba75bdbd8e25f98d11d822c22fa7881352ad88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581532"
---
# <a name="could-not-load-file-or-assembly-39microsoftanalysisservicessharepointintegration39"></a><span data-ttu-id="7eefe-102">Não foi possível carregar o arquivo ou assembly &#39;Microsoft. AnalysisServices. SharePoint. Integration&#39;</span><span class="sxs-lookup"><span data-stu-id="7eefe-102">Could not load file or assembly &#39;Microsoft.AnalysisServices.SharePoint.Integration&#39;</span></span>
  <span data-ttu-id="7eefe-103">Em ambientes do SharePoint 2010 com o PowerPivot para SharePoint, este erro ocorrerá se a solução no nível de aplicativo para o PowerPivot não tiver sido implantada corretamente.</span><span class="sxs-lookup"><span data-stu-id="7eefe-103">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if the application-level solution for PowerPivot did not deploy correctly.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7eefe-104">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7eefe-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7eefe-105">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="7eefe-105">Applies to</span></span>|<span data-ttu-id="7eefe-106">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="7eefe-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="7eefe-107">Versão do produto</span><span class="sxs-lookup"><span data-stu-id="7eefe-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="7eefe-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eefe-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="7eefe-109">Causa</span><span class="sxs-lookup"><span data-stu-id="7eefe-109">Cause</span></span>|<span data-ttu-id="7eefe-110">A solução Powerpivotwebapp não está implantada ou não foi implantada corretamente.</span><span class="sxs-lookup"><span data-stu-id="7eefe-110">Powerpivotwebapp solution is not deployed or did not deploy correctly.</span></span>|  
|<span data-ttu-id="7eefe-111">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="7eefe-111">Message Text</span></span>|<span data-ttu-id="7eefe-112">Não foi possível carregar arquivo ou assembly 'Microsoft.AnalysisServices.SharePoint.Integration'</span><span class="sxs-lookup"><span data-stu-id="7eefe-112">Could not load file or assembly 'Microsoft.AnalysisServices.SharePoint.Integration'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7eefe-113">Explicação</span><span class="sxs-lookup"><span data-stu-id="7eefe-113">Explanation</span></span>  
 <span data-ttu-id="7eefe-114">O PowerPivot para SharePoint usa pacotes de solução para implantar seus recursos em um servidor do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7eefe-114">PowerPivot for SharePoint uses solution packages to deploy its features on a SharePoint server.</span></span> <span data-ttu-id="7eefe-115">Uma das soluções não está implantada corretamente.</span><span class="sxs-lookup"><span data-stu-id="7eefe-115">One of the solutions is not deployed correctly.</span></span> <span data-ttu-id="7eefe-116">Como resultado, este erro aparece sempre que você tenta abrir a Galeria PowerPivot ou outras páginas de aplicativo do PowerPivot em um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7eefe-116">As a result, this error appears whenever you try to open PowerPivot Gallery or other PowerPivot application pages on a SharePoint site.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7eefe-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="7eefe-117">User Action</span></span>  
 <span data-ttu-id="7eefe-118">Implantar o pacote de solução.</span><span class="sxs-lookup"><span data-stu-id="7eefe-118">Deploy the solution package.</span></span>  
  
1.  <span data-ttu-id="7eefe-119">Na Administração Central, em Configurações do Sistema, clique em **Gerenciar soluções de farm**.</span><span class="sxs-lookup"><span data-stu-id="7eefe-119">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="7eefe-120">Clique em **Powerpivotwebapp**.</span><span class="sxs-lookup"><span data-stu-id="7eefe-120">Click **Powerpivotwebapp**.</span></span>  
  
3.  <span data-ttu-id="7eefe-121">Clique em **Implantar Solução**.</span><span class="sxs-lookup"><span data-stu-id="7eefe-121">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="7eefe-122">Escolha o aplicativo Web para o qual este erro está ocorrendo.</span><span class="sxs-lookup"><span data-stu-id="7eefe-122">Choose the web application for which this error is occurring.</span></span> <span data-ttu-id="7eefe-123">Se houver mais de um aplicativo Web, reimplante a solução para todos eles.</span><span class="sxs-lookup"><span data-stu-id="7eefe-123">If there is more than one web application, redeploy the solution for all of hem.</span></span>  
  
5.  <span data-ttu-id="7eefe-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7eefe-124">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eefe-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7eefe-125">See Also</span></span>  
 [<span data-ttu-id="7eefe-126">Implantar soluções PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="7eefe-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
