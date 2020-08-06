---
title: Programação de modelo de tabela | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 0ceb461e-12c1-44ea-97ac-b99bf308676b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2565ed28a882750ab9b37beadbce698d3a0abb19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686385"
---
# <a name="tabular-model-programming"></a><span data-ttu-id="81d7e-102">Programação de modelo tabular</span><span class="sxs-lookup"><span data-stu-id="81d7e-102">Tabular Model Programming</span></span>
  <span data-ttu-id="81d7e-103">Os modelos tabulares usam construções relacionais para modelar os dados do Analysis Services usados aplicativos analíticos e de relatório.</span><span class="sxs-lookup"><span data-stu-id="81d7e-103">Tabular models use relational constructs to model the Analysis Services data used by analytical and reporting applications.</span></span> <span data-ttu-id="81d7e-104">Esses modelos são executados em uma instância do Analysis Services que é configurada para o modo tabular, usando um mecanismo analítico na memória para armazenamento e análises rápidas de tabelas que agregam e calculam dados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="81d7e-104">These models run on an Analysis Service instance that is configured for tabular mode, using an in-memory analytics engine for storage and fast table scans that aggregate and calculate data as it is requested.</span></span>  
  
 <span data-ttu-id="81d7e-105">Em termos de programação, os objetos com os quais você trabalha no AMO, ADOMD.NET, XMLA ou OLE DB são basicamente os mesmos para soluções tabulares e multidimensionais.</span><span class="sxs-lookup"><span data-stu-id="81d7e-105">Programmatically, the objects you work with in AMO, ADOMD.NET, XMLA, or OLE DB are fundamentally the same for both tabular and multidimensional solutions.</span></span> <span data-ttu-id="81d7e-106">Se os requisitos de sua solução de BI personalizada forem atendidos da melhor forma por um banco de dados modelo, poderá usar qualquer uma das bibliotecas de cliente e interfaces de programação do Analysis Services para integrar seu aplicativo com modelos tabulares em uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="81d7e-106">If the requirements of your custom BI solution are best met by a tabular model database, you can use any of the Analysis Services client libraries and programming interfaces to integrate your application with tabular models on an Analysis Services instance.</span></span> <span data-ttu-id="81d7e-107">Para consultar e calcular dados de modelos tabulares, é possível usar MDX ou DAX inserido no código.</span><span class="sxs-lookup"><span data-stu-id="81d7e-107">To query and calculate tabular model data, you can use either embedded MDX or DAX in your code.</span></span>  
  
 <span data-ttu-id="81d7e-108">Esta seção fornece mais informações sobre como trabalhar programaticamente com entidades de modelos tabulares e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="81d7e-108">This section provides more information about how you can programmatically work with tabular model entities and their properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="81d7e-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="81d7e-109">In This Section</span></span>  
 [<span data-ttu-id="81d7e-110">Anotações CSDLBI &#40;CSDL para Business Intelligence&#41;</span><span class="sxs-lookup"><span data-stu-id="81d7e-110">CSDL Annotations for Business Intelligence &#40;CSDLBI&#41;</span></span>](/analysis-services/csdlbi/csdl-annotations-for-business-intelligence-csdlbi)  
  
 [<span data-ttu-id="81d7e-111">Compreendendo o modelo de objeto de tabela</span><span class="sxs-lookup"><span data-stu-id="81d7e-111">Understanding the Tabular Object Model</span></span>](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
 [<span data-ttu-id="81d7e-112">Referência técnica para Anotações de BI para CSDL</span><span class="sxs-lookup"><span data-stu-id="81d7e-112">Technical Reference for BI Annotations to CSDL</span></span>](/analysis-services/csdlbi/technical-reference-for-bi-annotations-to-csdl)  
  
 [<span data-ttu-id="81d7e-113">Interface IMDEmbedded</span><span class="sxs-lookup"><span data-stu-id="81d7e-113">IMDEmbedded Interface</span></span>](imdembeddeddata-interface.md)  
  
## <a name="see-also"></a><span data-ttu-id="81d7e-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81d7e-114">See Also</span></span>  
 <span data-ttu-id="81d7e-115">[Modelagem de tabela &#40;SSAS de tabela&#41;](../tabular-models/tabular-models-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="81d7e-115">[Tabular Modeling &#40;SSAS Tabular&#41;](../tabular-models/tabular-models-ssas.md) </span></span>  
 [<span data-ttu-id="81d7e-116">Designer de modelo de tabela &#40;SSAS de tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="81d7e-116">Tabular Model Designer &#40;SSAS Tabular&#41;</span></span>](../tabular-model-designer-ssas-tabular.md)  
  
  
