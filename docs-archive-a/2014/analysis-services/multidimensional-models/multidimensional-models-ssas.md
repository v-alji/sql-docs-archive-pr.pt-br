---
title: Modelagem multidimensional (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 509df042-fdb3-4e2c-a6b8-86943ce1b0fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7348a932eccb62f2e00c0b154ca9efc8086fcd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686431"
---
# <a name="multidimensional-modeling-ssas"></a><span data-ttu-id="4f0fd-102">Modelagem multidimensional (SSAS)</span><span class="sxs-lookup"><span data-stu-id="4f0fd-102">Multidimensional Modeling (SSAS)</span></span>
  <span data-ttu-id="4f0fd-103">Uma solução multidimensional do Analysis Services usa estruturas de cubo para analisar dados comerciais em várias dimensões.</span><span class="sxs-lookup"><span data-stu-id="4f0fd-103">An Analysis Services multidimensional solution uses cube structures for analyzing business data across multiple dimensions.</span></span> <span data-ttu-id="4f0fd-104">O modo multidimensional é o modo de servidor padrão do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="4f0fd-104">Multidimensional mode is the default server mode of Analysis Services.</span></span> <span data-ttu-id="4f0fd-105">Ele inclui um mecanismo de consulta e de cálculo para dados OLAP, com modos de armazenamento MOLAP, ROLAP e HOLAP para equilibrar o desempenho com requisitos de dados escalonáveis.</span><span class="sxs-lookup"><span data-stu-id="4f0fd-105">It includes a query and calculation engine for OLAP data, with MOLAP, ROLAP, and HOLAP storage modes to balance performance with scalable data requirements.</span></span> <span data-ttu-id="4f0fd-106">O mecanismo OLAP do Analysis Services é um servidor OLAP líder da indústria que funciona bem com um intervalo amplo de ferramentas de BI.</span><span class="sxs-lookup"><span data-stu-id="4f0fd-106">The Analysis Services OLAP engine is an industry leading OLAP server that works well with a broad range of BI tools.</span></span> <span data-ttu-id="4f0fd-107">A maioria das implantações do Analysis Services são instaladas como servidores OLAP clássicos.</span><span class="sxs-lookup"><span data-stu-id="4f0fd-107">Most Analysis Services deployments are installed as classic OLAP servers.</span></span>  
  
## <a name="benefits-of-using-multidimensional-solutions"></a><span data-ttu-id="4f0fd-108">Benefícios do uso de soluções multidimensionais</span><span class="sxs-lookup"><span data-stu-id="4f0fd-108">Benefits of Using Multidimensional Solutions</span></span>  
 <span data-ttu-id="4f0fd-109">O principal motivo para criar um modelo multidimensional do Analysis Services é atingir um desempenho rápido de consultas ad hoc em dados comerciais.</span><span class="sxs-lookup"><span data-stu-id="4f0fd-109">The primary reason for building an Analysis Services multidimensional model is to achieve fast performance of ad hoc queries against business data.</span></span> <span data-ttu-id="4f0fd-110">Um modelo multidimensional é composto de cubos e dimensões que podem ser anotados e estendidos para oferecer suporte a construções de consultas complexas.</span><span class="sxs-lookup"><span data-stu-id="4f0fd-110">A multidimensional model is composed of cubes and dimensions that can be annotated and extended to support complex query constructions.</span></span> <span data-ttu-id="4f0fd-111">Desenvolvedores de BI criam cubos para oferecer suporte a tempos de resposta rápidos e fornecer uma única fonte de dados para relatórios de negócios.</span><span class="sxs-lookup"><span data-stu-id="4f0fd-111">BI developers create cubes to support fast response times, and to provide a single data source for business reporting.</span></span> <span data-ttu-id="4f0fd-112">Em função da crescente importância do business intelligence em todos os níveis de uma organização, a existência de uma única fonte de dados analíticos garante uma discrepância mínima, ou mesmo sua total eliminação.</span><span class="sxs-lookup"><span data-stu-id="4f0fd-112">Given the growing importance of business intelligence across all levels of an organization, having a single source of analytical data ensures that discrepancies are kept to a minimum, if not eliminated entirely.</span></span>  
  
 <span data-ttu-id="4f0fd-113">Outro benefício importante do uso de bancos de dados multidimensionais do Analysis Services é a integração com ferramentas de relatórios de BI usadas com frequência, como o Excel, o Reporting Services e o PerformancePoint, bem como aplicativos personalizados e soluções de terceiros.</span><span class="sxs-lookup"><span data-stu-id="4f0fd-113">Another important benefit to using Analysis Services multidimensional databases is integration with commonly used BI reporting tools such as Excel, Reporting Services, and PerformancePoint, as well as custom applications and third-party solutions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f0fd-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4f0fd-114">In This Section</span></span>  
 [<span data-ttu-id="4f0fd-115">Soluções de modelo multidimensional &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="4f0fd-115">Multidimensional Model Solutions &#40;SSAS&#41;</span></span>](multidimensional-model-solutions-ssas.md)  
  
 [<span data-ttu-id="4f0fd-116">Bancos de dados de modelo multidimensional &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="4f0fd-116">Multidimensional Model Databases &#40;SSAS&#41;</span></span>](multidimensional-model-databases-ssas.md)  
  
 [<span data-ttu-id="4f0fd-117">Processamento de objetos de modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="4f0fd-117">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="4f0fd-118">Funções e permissões &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4f0fd-118">Roles and Permissions &#40;Analysis Services&#41;</span></span>](roles-and-permissions-analysis-services.md)  
  
 [<span data-ttu-id="4f0fd-119">Power View para Modelos Multidimensionais</span><span class="sxs-lookup"><span data-stu-id="4f0fd-119">Power View for Multidimensional Models</span></span>](power-view-for-multidimensional-models.md)  
  
 [<span data-ttu-id="4f0fd-120">Gerenciamento de assemblies de modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="4f0fd-120">Multidimensional Model Assemblies Management</span></span>](multidimensional-model-assemblies-management.md)  
  
  
