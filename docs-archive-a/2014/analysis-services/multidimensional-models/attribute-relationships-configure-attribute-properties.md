---
title: Configurar propriedades de relação de atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- flexible relationships (Analysis Services)
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
- properties [Analysis Services], attribute relationships
- rigid relationships (Analysis Services)
ms.assetid: fce511af-66d7-42fc-bb3a-6c516f16b10e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 241fa2af16377fd2cacf657ec6f99c5ca4bd0c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569716"
---
# <a name="configure-attribute-relationship-properties"></a><span data-ttu-id="1b818-102">Configurar propriedades de relação de atributo</span><span class="sxs-lookup"><span data-stu-id="1b818-102">Configure Attribute Relationship Properties</span></span>
  <span data-ttu-id="1b818-103">A tabela a seguir lista e descreve as propriedades de uma relação de atributo.</span><span class="sxs-lookup"><span data-stu-id="1b818-103">The following table lists and describes the properties of an attribute relationship.</span></span>  
  
|<span data-ttu-id="1b818-104">Propriedade</span><span class="sxs-lookup"><span data-stu-id="1b818-104">Property</span></span>|<span data-ttu-id="1b818-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b818-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="1b818-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="1b818-106">Attribute</span></span>|<span data-ttu-id="1b818-107">Contém o nome do atributo.</span><span class="sxs-lookup"><span data-stu-id="1b818-107">Contains the name of the attribute.</span></span>|  
|<span data-ttu-id="1b818-108">Cardinalidade</span><span class="sxs-lookup"><span data-stu-id="1b818-108">Cardinality</span></span>|<span data-ttu-id="1b818-109">Indica a cardinalidade da relação.</span><span class="sxs-lookup"><span data-stu-id="1b818-109">Indicates the cardinality of the relationship.</span></span> <span data-ttu-id="1b818-110">Os valores são Many, para uma relação muitos para um, ou One, para uma relação um para um.</span><span class="sxs-lookup"><span data-stu-id="1b818-110">Values are Many, for a many to one relationship, or One, for a one to one relationship.</span></span> <span data-ttu-id="1b818-111">O valor padrão é Many.</span><span class="sxs-lookup"><span data-stu-id="1b818-111">Default value is Many.</span></span> <span data-ttu-id="1b818-112">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , a propriedade cardinalidade não tem nenhum efeito – seu uso é reservado para uma implementação futura.</span><span class="sxs-lookup"><span data-stu-id="1b818-112">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the cardinality property has no effect - its use is reserved for a future implementation.</span></span>|  
|<span data-ttu-id="1b818-113">Nome</span><span class="sxs-lookup"><span data-stu-id="1b818-113">Name</span></span>|<span data-ttu-id="1b818-114">Contém o nome amigável do atributo.</span><span class="sxs-lookup"><span data-stu-id="1b818-114">Contains the friendly name of the attribute.</span></span>|  
|<span data-ttu-id="1b818-115">RelationshipType</span><span class="sxs-lookup"><span data-stu-id="1b818-115">RelationshipType</span></span>|<span data-ttu-id="1b818-116">Indica se relações de membro alteram com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="1b818-116">Indicates whether member relationships change over time.</span></span> <span data-ttu-id="1b818-117">Os valores são Rigid, o que significa que as relações entre membros não muda com o passar do tempo, ou Flexible, o que significa que as relações entre os membros mudam.</span><span class="sxs-lookup"><span data-stu-id="1b818-117">Values are Rigid, which means that relationships between members do not change over time, or Flexible, which means that relationships between members change over time.</span></span> <span data-ttu-id="1b818-118">O padrão é Flexible.</span><span class="sxs-lookup"><span data-stu-id="1b818-118">Default is Flexible.</span></span> <span data-ttu-id="1b818-119">Se você definir uma relação como flexível, as agregações serão descartadas e recomputadas como parte de uma atualização incremental (elas não serão descartadas se apenas novos membros forem adicionados).</span><span class="sxs-lookup"><span data-stu-id="1b818-119">If you define a relationship as flexible, aggregations are dropped and recomputed as part of an incremental update (they will not be dropped if only new members are added).</span></span> <span data-ttu-id="1b818-120">Se você definir uma relação como rígida, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] manterá as agregações quando a dimensão for atualizada incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="1b818-120">If you define a relationship as rigid, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retains aggregations when the dimension is incrementally updated.</span></span> <span data-ttu-id="1b818-121">Se uma relação que é definida como rígida mudar, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gerará um erro durante o processamento incremental.</span><span class="sxs-lookup"><span data-stu-id="1b818-121">If a relationship that is defined as rigid actually changes, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] generates an error during incremental processing.</span></span> <span data-ttu-id="1b818-122">Ao especificar as relações apropriadas e as propriedades da relação, são produzidos aumento de consulta e desempenho de processamento.</span><span class="sxs-lookup"><span data-stu-id="1b818-122">Specifying the appropriate relationships and relationship properties increases query and processing performance.</span></span>|  
|<span data-ttu-id="1b818-123">Visible</span><span class="sxs-lookup"><span data-stu-id="1b818-123">Visible</span></span>|<span data-ttu-id="1b818-124">Determina a visibilidade da relação do atributo.</span><span class="sxs-lookup"><span data-stu-id="1b818-124">Determines the visibility of the attribute relationship.</span></span> <span data-ttu-id="1b818-125">Os valores são True ou False.</span><span class="sxs-lookup"><span data-stu-id="1b818-125">Values are True or False.</span></span> <span data-ttu-id="1b818-126">O padrão é True.</span><span class="sxs-lookup"><span data-stu-id="1b818-126">Default is True.</span></span>|  
  
  
