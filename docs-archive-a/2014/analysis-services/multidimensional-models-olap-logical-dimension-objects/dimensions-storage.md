---
title: Armazenamento de dimensão | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- dimensions [Analysis Services], storage
- storing data [Analysis Services]
- storage [Analysis Services], dimensions
- relational OLAP
- multidimensional OLAP
- MOLAP
- storing data [Analysis Services], dimensions
- ROLAP
ms.assetid: 8d74b932-2174-4e1f-8414-636455880b6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: afa68ebcfa8f4136bcd4a131842c852665ee9851
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679072"
---
# <a name="dimension-storage"></a><span data-ttu-id="f6ca2-102">Armazenamento de dimensões</span><span class="sxs-lookup"><span data-stu-id="f6ca2-102">Dimension Storage</span></span>
  <span data-ttu-id="f6ca2-103">As dimensões no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dão suporte a dois modos de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="f6ca2-103">Dimensions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support two storage modes:</span></span>  
  
-   <span data-ttu-id="f6ca2-104">OLAP relacional (ROLAP)</span><span class="sxs-lookup"><span data-stu-id="f6ca2-104">Relational OLAP (ROLAP)</span></span>  
  
-   <span data-ttu-id="f6ca2-105">OLAP multidimensional (MOLAP)</span><span class="sxs-lookup"><span data-stu-id="f6ca2-105">Multidimensional OLAP (MOLAP)</span></span>  
  
 <span data-ttu-id="f6ca2-106">O modo de armazenamento determina o local e a forma dos dados de uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-106">The storage mode determines the location and form of a dimension's data.</span></span> <span data-ttu-id="f6ca2-107">O MOLAP é o modo de armazenamento padrão para dimensões.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-107">MOLAP is the default storage mode for dimensions.</span></span> <span data-ttu-id="f6ca2-108">**Tópicos relacionados:**[modos de armazenamento de partição e processamento](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span><span class="sxs-lookup"><span data-stu-id="f6ca2-108">**Related topics:**[Partition Storage Modes and Processing](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span></span>  
  
## <a name="molap"></a><span data-ttu-id="f6ca2-109">MOLAP</span><span class="sxs-lookup"><span data-stu-id="f6ca2-109">MOLAP</span></span>  
 <span data-ttu-id="f6ca2-110">Dados de uma dimensão que usam MOLAP são armazenados em uma estrutura multidimensional na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6ca2-110">Data for a dimension that uses MOLAP is stored in a multidimensional structure in the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="f6ca2-111">Essa estrutura multidimensional é criada e populada quando a dimensão é processada.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-111">This multidimensional structure is created and populated when the dimension is processed.</span></span> <span data-ttu-id="f6ca2-112">As dimensões MOLAP fornecem melhores desempenho de consulta do que de dimensões ROLAP.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-112">MOLAP dimensions provide better query performance than ROLAP dimensions.</span></span>  
  
## <a name="rolap"></a><span data-ttu-id="f6ca2-113">ROLAP</span><span class="sxs-lookup"><span data-stu-id="f6ca2-113">ROLAP</span></span>  
 <span data-ttu-id="f6ca2-114">Dados de uma dimensão que usa ROLAP são armazenados nas tabelas usadas para definir a dimensão.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-114">Data for a dimension that uses ROLAP is actually stored in the tables used to define the dimension.</span></span> <span data-ttu-id="f6ca2-115">O modo de armazenamento ROLAP pode ser usado para oferecer suporte para grandes dimensões sem duplicar grandes quantidades de dados, mas diminuindo o desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-115">The ROLAP storage mode can be used to support large dimensions without duplicating large amounts of data, but at the expense of query performance.</span></span> <span data-ttu-id="f6ca2-116">Como a dimensão depende diretamente das tabelas na exibição de fonte de dados, usados para definir a dimensão, o modo de armazenamento ROLAP também oferece suporte ao OLAP em tempo real.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-116">Because the dimension relies directly on the tables in the data source view used to define the dimension, the ROLAP storage mode also supports real-time OLAP.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f6ca2-117">Se a dimensão usa o modo de armazenamento ROLAP e a dimensão está incluída em um cubo que usa o armazenamento MOLAP, qualquer alteração de esquema na tabela de origem deve ser seguida por processamento imediato do cubo.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-117">If a dimension uses the ROLAP storage mode and the dimension is included in a cube that uses MOLAP storage, any schema changes to its source table must be followed by immediate processing of the cube.</span></span> <span data-ttu-id="f6ca2-118">Se não fizer isso, poderá gerar resultados inconsistentes quando consultar o cubo.</span><span class="sxs-lookup"><span data-stu-id="f6ca2-118">Failure to do this may result in inconsistent results when querying the cube.</span></span> <span data-ttu-id="f6ca2-119">**Tópico relacionado:**[automatizar Analysis Services tarefas administrativas com o SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="f6ca2-119">**Related topic:**[Automate Analysis Services Administrative Tasks with SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ca2-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6ca2-120">See Also</span></span>  
 [<span data-ttu-id="f6ca2-121">Modos e processamento de armazenamento de partição</span><span class="sxs-lookup"><span data-stu-id="f6ca2-121">Partition Storage Modes and Processing</span></span>](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)  
  
  
