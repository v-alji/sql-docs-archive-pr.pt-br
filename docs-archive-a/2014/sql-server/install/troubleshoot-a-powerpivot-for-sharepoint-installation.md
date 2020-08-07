---
title: Solucionar problemas de instalação de PowerPivot para SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97bc2ce7-af04-4372-ad79-c96b8c3417ab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3adc27132d976288c14ac702baae0b842e8aef0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573453"
---
# <a name="troubleshoot-a-powerpivot-for-sharepoint-installation"></a><span data-ttu-id="fea36-102">Solução de problemas da instalação do PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="fea36-102">Troubleshoot a PowerPivot for SharePoint Installation</span></span>
  <span data-ttu-id="fea36-103">Se você obtiver erros em vez das páginas e recursos que você esperava, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="fea36-103">If you get errors instead of the pages and features you expect, do the following.</span></span>  
  
-   <span data-ttu-id="fea36-104">Revise as notas de versão do SharePoint e do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para obter soluções alternativas para problemas de instalação conhecidos.</span><span class="sxs-lookup"><span data-stu-id="fea36-104">Review release notes for both SharePoint and [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to get workarounds for known installation problems.</span></span> <span data-ttu-id="fea36-105">As notas de versão são fornecidas com a mídia de instalação ou no site da Microsoft do qual você baixou o software.</span><span class="sxs-lookup"><span data-stu-id="fea36-105">Release notes are provided with the installation media or on the Microsoft site from which you downloaded the software.</span></span>  
  
    -   <span data-ttu-id="fea36-106">[Notas de versão do SQL Server 2014](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="fea36-106">[SQL Server 2014 Release Notes](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).</span></span>  
  
-   <span data-ttu-id="fea36-107">Consulte o tópico de wiki do Technet, [Solução de problemas de instalações do PowerPivot (e outros suplementos)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).</span><span class="sxs-lookup"><span data-stu-id="fea36-107">See the Technet wiki topic, [Troubleshooting Installations of PowerPivot (and other add-ins)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).</span></span>  
  
## <a name="issues"></a><span data-ttu-id="fea36-108">Problemas</span><span class="sxs-lookup"><span data-stu-id="fea36-108">Issues</span></span>  
  
### <a name="powerpivot-gallery-thumbnail-images-show-as-a-red-x"></a><span data-ttu-id="fea36-109">As imagens em miniatura para Galeria PowerPivot são exibidas como um X vermelho</span><span class="sxs-lookup"><span data-stu-id="fea36-109">PowerPivot Gallery Thumbnail images show as a red X</span></span>  
 <span data-ttu-id="fea36-110">Uma causa possível é que a **Integração de recursos do PowerPivot para coleções de sites** não está ativa.</span><span class="sxs-lookup"><span data-stu-id="fea36-110">One Possible cause is the **PowerPivot features Integration for Site Collections** is not active.</span></span> <span data-ttu-id="fea36-111">Preencha o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fea36-111">Complete the following:</span></span>  
  
1.  <span data-ttu-id="fea36-112">Na biblioteca da Galeria PowerPivot, clique em **configurações do site** no ícone de engrenagem configurações do ![SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Configurações do SharePoint") ou na lista **inicial** .</span><span class="sxs-lookup"><span data-stu-id="fea36-112">In the PowerPivot Gallery library, click **Site Settings** from either the gear icon ![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings") or the **Home** list.</span></span>  
  
2.  <span data-ttu-id="fea36-113">Na seção **Administração do Conjunto de Sites** , clique em **Recursos do Conjunto de Sites**.</span><span class="sxs-lookup"><span data-stu-id="fea36-113">In the **Site Collection Administration** section, click **Site Collection Features**.</span></span>  
  
3.  <span data-ttu-id="fea36-114">Clique em **Recursos do Conjunto de Sites**.</span><span class="sxs-lookup"><span data-stu-id="fea36-114">Click **Site Collection Features**.</span></span>  
  
4.  <span data-ttu-id="fea36-115">Verifique se a **Integração de recursos do PowerPivot para coleções de sites** está **Ativa**.</span><span class="sxs-lookup"><span data-stu-id="fea36-115">Verify **PowerPivot features Integration for Site Collections** is **Active**.</span></span>  
  
 <span data-ttu-id="fea36-116">Para obter as causas adicionais desse problema, consulte a [Galeria PowerPivot mostra os ícones de X vermelho](https://support.microsoft.com/kb/2361559) ( https://support.microsoft.com/kb/2361559) .</span><span class="sxs-lookup"><span data-stu-id="fea36-116">For additional causes of this issue, see [PowerPivot Gallery shows Red X's for Icons](https://support.microsoft.com/kb/2361559) (https://support.microsoft.com/kb/2361559).</span></span>  
  
  
