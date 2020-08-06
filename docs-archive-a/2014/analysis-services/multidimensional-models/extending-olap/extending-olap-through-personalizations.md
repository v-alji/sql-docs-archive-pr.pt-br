---
title: Estendendo o OLAP por meio de personalizações | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, extensibility
ms.assetid: 348e49fc-4390-43c1-9b6c-61b386ff4373
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93669980e989b1cb11673f45c111de3609bbe920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685343"
---
# <a name="extending-olap-through-personalizations"></a><span data-ttu-id="b6033-102">Estendendo OLAP por meio de personalizações</span><span class="sxs-lookup"><span data-stu-id="b6033-102">Extending OLAP through personalizations</span></span>
  <span data-ttu-id="b6033-103">O Microsoft [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] fornece muitas funções intrínsecas para uso com as linguagens MDX e DMX.</span><span class="sxs-lookup"><span data-stu-id="b6033-103">Microsoft  [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] supplies many intrinsic functions for use with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span> <span data-ttu-id="b6033-104">Essas funções são designadas para executar todas as operações, desde cálculos estatísticos padrão ao desvio de membros em uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="b6033-104">These functions are designed to accomplish everything from standard statistical calculations to traversing members in a hierarchy.</span></span> <span data-ttu-id="b6033-105">No entanto, como em qualquer outro produto complexo, há sempre a necessidade de estender a funcionalidade para o produto.</span><span class="sxs-lookup"><span data-stu-id="b6033-105">However, as with any other complex and robust product, there is always the need to extend the functionality of such a product further.</span></span>  
  
 <span data-ttu-id="b6033-106">Assim, o Analysis Services oferece a capacidade de adicionar assemblies e extensões personalizadas a uma instância do serviço, para atender suas necessidades comerciais sempre que a funcionalidade padrão não for suficiente.</span><span class="sxs-lookup"><span data-stu-id="b6033-106">Therefore, Analysis Services provides you with the ability to add assemblies and personalized extensions to an instance of the service, in order to complete your business needs whenever the standard functionality is not enough.</span></span>  
  
## <a name="assemblies"></a><span data-ttu-id="b6033-107">Assemblies</span><span class="sxs-lookup"><span data-stu-id="b6033-107">Assemblies</span></span>  
 <span data-ttu-id="b6033-108">Os assemblies permitem que você estenda a funcionalidade comercial do MDX e do DMX.</span><span class="sxs-lookup"><span data-stu-id="b6033-108">Assemblies enable you to extend the business functionality of MDX and DMX.</span></span> <span data-ttu-id="b6033-109">É possível criar a funcionalidade desejada em uma biblioteca, como uma DLL (biblioteca de vínculo dinâmico) e adicionar a biblioteca como um assembly a uma instância ou a um banco de dados do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="b6033-109">You build the functionality that you want into a library, such as a dynamic link library (DLL), then add the library as an assembly to an instance of Analysis Services or to an Analysis Services database.</span></span> <span data-ttu-id="b6033-110">Em seguida, os métodos públicos na biblioteca são expostos como funções definidas pelo usuário para expressões MDX e DMX, procedimentos, cálculos, ações e aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="b6033-110">The public methods in the library are then exposed as user-defined functions to MDX and DMX expressions, procedures, calculations, actions, and client applications.</span></span>  
  
## <a name="personalized-extensions"></a><span data-ttu-id="b6033-111">Extensões personalizadas</span><span class="sxs-lookup"><span data-stu-id="b6033-111">Personalized Extensions</span></span>  
 <span data-ttu-id="b6033-112">As extensões de personalização do SQL Server Analysis Services são a base do conceito de implementação de uma arquitetura de plug-in.</span><span class="sxs-lookup"><span data-stu-id="b6033-112">SQL Server Analysis Services personalization extensions are the foundation of the idea of implementing a plug-in architecture.</span></span> <span data-ttu-id="b6033-113">Analysis Services extensões de personalização são uma modificação simples e elegante da arquitetura de assembly gerenciada existente e são expostas em todo o modelo de objeto Analysis Services [Microsoft. AnalysisServices. AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) , sintaxe MDX e conjuntos de linhas de esquema.</span><span class="sxs-lookup"><span data-stu-id="b6033-113">Analysis Services personalization extensions are a simple and elegant modification to the existing managed assembly architecture and are exposed throughout the Analysis Services [Microsoft.AnalysisServices.AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) object model, Multidimensional Expressions (MDX) syntax, and schema rowsets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6033-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b6033-114">See Also</span></span>  
 <span data-ttu-id="b6033-115">[Gerenciamento de assemblies de modelo multidimensional](../multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="b6033-115">[Multidimensional Model Assemblies Management](../multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="b6033-116">Extensões de personalização do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b6033-116">Analysis Services Personalization Extensions</span></span>](analysis-services-personalization-extensions.md)  
  
  
