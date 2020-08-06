---
title: Definir relações de atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
ms.assetid: 9184d344-e96d-4025-ad6f-3f75129746df
author: minewiskan
ms.author: owend
ms.openlocfilehash: a694c68a55de2533c4ce7791d3be865008b6321f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569708"
---
# <a name="define-attribute-relationships"></a><span data-ttu-id="85720-102">Definir relações de atributo</span><span class="sxs-lookup"><span data-stu-id="85720-102">Define Attribute Relationships</span></span>
  <span data-ttu-id="85720-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , os atributos são o bloco de construção fundamental de uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="85720-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes are the fundamental building block of a dimension.</span></span> <span data-ttu-id="85720-104">Uma dimensão contém um conjunto de atributos organizados com base em relações de atributo.</span><span class="sxs-lookup"><span data-stu-id="85720-104">A dimension contains a set of attributes that are organized based on attribute relationships.</span></span>  
  
 <span data-ttu-id="85720-105">Para cada tabela incluída em uma dimensão, existe uma relação de atributo que relaciona o atributo de chave da tabela a outros atributos da tabela em questão.</span><span class="sxs-lookup"><span data-stu-id="85720-105">For each table included in a dimension, there is an attribute relationship that relates the table's key attribute to other attributes from that table.</span></span> <span data-ttu-id="85720-106">Essa relação é gerada na criação da dimensão.</span><span class="sxs-lookup"><span data-stu-id="85720-106">You create this relationship when you create the dimension.</span></span>  
  
 <span data-ttu-id="85720-107">Uma relação de atributo fornece as seguintes vantagens:</span><span class="sxs-lookup"><span data-stu-id="85720-107">An attribute relationship provides the following advantages:</span></span>  
  
-   <span data-ttu-id="85720-108">Reduz a quantidade de memória necessária para o processamento da dimensão.</span><span class="sxs-lookup"><span data-stu-id="85720-108">Reduces the amount of memory needed for dimension processing.</span></span> <span data-ttu-id="85720-109">Isso acelera o processamento de dimensão, partição e de consulta.</span><span class="sxs-lookup"><span data-stu-id="85720-109">This speeds up dimension, partition, and query processing.</span></span>  
  
-   <span data-ttu-id="85720-110">Aumenta o desempenho de consulta, pois o acesso ao armazenamento é mais rápido e existe melhor otimização dos planos de execução.</span><span class="sxs-lookup"><span data-stu-id="85720-110">Increases query performance because storage access is faster and execution plans are better optimized.</span></span>  
  
-   <span data-ttu-id="85720-111">Resulta na seleção de agregações mais efetivas pelos algoritmos de design de agregação, contanto que as hierarquias definidas pelo usuário tenham sido definidas ao longo dos caminhos de relação.</span><span class="sxs-lookup"><span data-stu-id="85720-111">Results in the selection of more effective aggregates by the aggregation design algorithms, provided that user-defined hierarchies have been defined along the relationship paths.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="85720-112">Para obter mais informações sobre a importância e as implicações de definir e configurar relações de atributo, consulte a seção "aprimorando o desempenho da consulta" no [Guia de desempenho do SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="85720-112">For more information about the importance and implications of defining and configuring attribute relationships, see the section, "Enhancing query performance," in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="attribute-relationship-considerations"></a><span data-ttu-id="85720-113">Considerações de relação de atributo</span><span class="sxs-lookup"><span data-stu-id="85720-113">Attribute Relationship Considerations</span></span>  
 <span data-ttu-id="85720-114">Quando os dados subjacentes permitirem, também é necessário definir relações de atributo exclusivas entre atributos.</span><span class="sxs-lookup"><span data-stu-id="85720-114">When the underlying data supports it, you should also define unique attribute relationships between attributes.</span></span> <span data-ttu-id="85720-115">Para definir relações de atributo exclusivas, use a guia **Relações de Atributo** do Designer de Dimensão.</span><span class="sxs-lookup"><span data-stu-id="85720-115">To define unique attribute relationships, use the **Attribute Relationships** tab of Dimension Designer.</span></span>  
  
 <span data-ttu-id="85720-116">Qualquer atributo que tenha uma relação de saída deve ter uma chave exclusiva relacionada ao respectivo atributo.</span><span class="sxs-lookup"><span data-stu-id="85720-116">Any attribute that has an outgoing relationship must have a unique key relative to its related attribute.</span></span> <span data-ttu-id="85720-117">Em outras palavras, um membro em um atributo de origem deve identificar um e somente um membro em um atributo relacionado.</span><span class="sxs-lookup"><span data-stu-id="85720-117">In other words, a member in a source attribute must identify one and only one member in a related attribute.</span></span> <span data-ttu-id="85720-118">Por exemplo, considere a relação Cidade -> Estado.</span><span class="sxs-lookup"><span data-stu-id="85720-118">For example, consider the relationship, City -> State.</span></span> <span data-ttu-id="85720-119">Nesta relação, o atributo de origem é Cidade e o atributo relacionado é Estado.</span><span class="sxs-lookup"><span data-stu-id="85720-119">In this relationship, the source attribute is City and the related attribute is State.</span></span> <span data-ttu-id="85720-120">O atributo de origem é o lado "muitos" e o lado relacionado é o lado "um" da relação muitos para um.</span><span class="sxs-lookup"><span data-stu-id="85720-120">The source attribute is the "many" side and the related side is the "one" side of the many-to-one relationship.</span></span> <span data-ttu-id="85720-121">A chave para o atributo de origem seria Cidade + Estado.</span><span class="sxs-lookup"><span data-stu-id="85720-121">The key for the source attribute would be City + State.</span></span> <span data-ttu-id="85720-122">Para obter mais informações, consulte [Criar, modificar ou excluir uma relação de atributo](attribute-relationships-create-modify-or-delete-relationship.md).</span><span class="sxs-lookup"><span data-stu-id="85720-122">For more information, see [Create, Modify, or Delete an Attribute Relationship](attribute-relationships-create-modify-or-delete-relationship.md).</span></span>  
  
 <span data-ttu-id="85720-123">Para obter mais informações sobre as propriedades de uma relação de atributo, consulte [Configurar propriedades de relação de atributo](attribute-relationships-configure-attribute-properties.md).</span><span class="sxs-lookup"><span data-stu-id="85720-123">For more information about properties of an attribute relationship, see [Configure Attribute Relationship Properties](attribute-relationships-configure-attribute-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85720-124">Definir incorretamente relações de atributo pode causar resultados de consulta inválidos.</span><span class="sxs-lookup"><span data-stu-id="85720-124">Defining attribute relationships incorrectly can cause invalid query results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85720-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="85720-125">See Also</span></span>  
 [<span data-ttu-id="85720-126">Relações de Atributo</span><span class="sxs-lookup"><span data-stu-id="85720-126">Attribute Relationships</span></span>](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md)  
  
  
