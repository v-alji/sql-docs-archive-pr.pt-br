---
title: Criar uma conta de finanças da dimensão de tipo pai-filho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], account
- account dimensions [Analysis Services]
- adding account intelligence
- account intelligence [Analysis Services]
ms.assetid: 2ba74e81-5b4b-407e-acdf-deb2f6accf0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: ba10e642425628426d9183be2b8d2c4ff751c3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680116"
---
# <a name="create-a-finance-account-of-parent-child-type-dimension"></a><span data-ttu-id="a6f53-102">Criar uma Conta de Finanças de Dimensão de tipo pai-filho</span><span class="sxs-lookup"><span data-stu-id="a6f53-102">Create a Finance Account of parent-child type Dimension</span></span>
  <span data-ttu-id="a6f53-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , uma dimensão de tipo de conta é uma dimensão cujos atributos representam um plano de contas para fins de relatório financeiro.</span><span class="sxs-lookup"><span data-stu-id="a6f53-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], an account type dimension is a dimension whose attributes represent a chart of accounts for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="a6f53-104">Uma dimensão de conta permite o gerenciamento seletivo do comportamento de agregação entre contas no decorrer do tempo.</span><span class="sxs-lookup"><span data-stu-id="a6f53-104">An account dimension lets you selectively manage aggregation behavior across accounts over time.</span></span> <span data-ttu-id="a6f53-105">Uma dimensão de conta também possibilita o uso de mecanismos padrão para resolver a maioria das questões de agregação não padrão geralmente encontradas em soluções de business intelligence que lidam com dados financeiros.</span><span class="sxs-lookup"><span data-stu-id="a6f53-105">An account dimension also lets use a standard mechanism to resolve most of the nonstandard aggregation issues typically encountered in business intelligence solutions that handle financial data.</span></span> <span data-ttu-id="a6f53-106">Sem esse tipo de mecanismo padrão, a resolução dessas questões de agregação não padrão requer fórmulas de acúmulo personalizado, membros calculados ou scripts de expressões multidimensionais (MDX).</span><span class="sxs-lookup"><span data-stu-id="a6f53-106">If you did not have such a standard mechanism, resolving these nonstandard aggregation issues would require custom rollup formulas, calculated members, or Multidimensional Expressions (MDX) scripts.</span></span>  
  
 <span data-ttu-id="a6f53-107">Para identificar uma dimensão como dimensão de conta, defina sua propriedade `Type` como `Accounts`.</span><span class="sxs-lookup"><span data-stu-id="a6f53-107">To identify a dimension as an account dimension, set the `Type` property of the dimension to `Accounts`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="a6f53-108">Estrutura da Dimensão</span><span class="sxs-lookup"><span data-stu-id="a6f53-108">Dimension Structure</span></span>  
 <span data-ttu-id="a6f53-109">Uma dimensão de conta contém, no mínimo, dois atributos:</span><span class="sxs-lookup"><span data-stu-id="a6f53-109">An account dimension contains, at least, two attributes:</span></span>  
  
-   <span data-ttu-id="a6f53-110">Um atributo de chave-um atributo que identifica contas individuais na tabela de dimensões para a dimensão de conta.</span><span class="sxs-lookup"><span data-stu-id="a6f53-110">A key attribute-an attribute that identifies individual accounts in the dimension table for the account dimension.</span></span>  
  
-   <span data-ttu-id="a6f53-111">Um atributo de conta – um atributo pai que descreve como as contas são organizadas hierarquicamente na dimensão de conta.</span><span class="sxs-lookup"><span data-stu-id="a6f53-111">An account attribute-a parent attribute that describes how accounts are hierarchically arranged in the account dimension.</span></span>  
  
     <span data-ttu-id="a6f53-112">Para identificar um atributo como atributo de conta, defina sua propriedade `Type` como `Account` e a propriedade `Usage` como `Parent`.</span><span class="sxs-lookup"><span data-stu-id="a6f53-112">To identify an attribute as an account attribute, set the `Type` property of the attribute to `Account` and the `Usage` property to `Parent`.</span></span>  
  
 <span data-ttu-id="a6f53-113">Opcionalmente, as dimensões de conta podem conter os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="a6f53-113">Account dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="a6f53-114">Um atributo de tipo de conta – um atributo que define o tipo de conta para cada conta na dimensão.</span><span class="sxs-lookup"><span data-stu-id="a6f53-114">An account type attribute-an attribute that defines the account type for each account in the dimension.</span></span> <span data-ttu-id="a6f53-115">Os nomes de membros do atributo de tipo de conta são mapeados para os tipos de conta definidos para o banco de dados ou projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e indicam a função de agregação usada pelo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para essas contas.</span><span class="sxs-lookup"><span data-stu-id="a6f53-115">The member names of the account type attribute map to the account types defined for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project, and indicate the aggregation function used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for those accounts.</span></span> <span data-ttu-id="a6f53-116">Também é possível usar operadores unários ou fórmulas de acúmulo personalizado para determinar o comportamento de agregação dos atributos de conta, mas, com os tipos de conta, é possível aplicar facilmente ao plano de contas um comportamento consistente sem precisar fazer alterações no banco de dados relacional subjacente.</span><span class="sxs-lookup"><span data-stu-id="a6f53-116">You can also use unary operators or custom rollup formulas to determine aggregation behavior for account attributes, but account types let you to easily apply consistent behavior to a chart of accounts without requiring changes to the underlying relational database.</span></span>  
  
     <span data-ttu-id="a6f53-117">Para identificar um atributo de tipo de conta, defina sua propriedade `Type` como `AccountType`.</span><span class="sxs-lookup"><span data-stu-id="a6f53-117">To identify an account type attribute, set the `Type` property of the attribute to `AccountType`.</span></span>  
  
-   <span data-ttu-id="a6f53-118">Um atributo de nome de conta – um atributo que é usado para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="a6f53-118">An account name attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="a6f53-119">Para identificar um atributo de nome de conta, configure sua propriedade `Type` como `AccountName`.</span><span class="sxs-lookup"><span data-stu-id="a6f53-119">You identify an account name attribute by setting the `Type` property of the attribute to `AccountName`.</span></span>  
  
-   <span data-ttu-id="a6f53-120">Um atributo de número de conta – um atributo que é usado para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="a6f53-120">An account number attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="a6f53-121">Para identificar um atributo de número de conta, configure sua propriedade `Type` como `AccountNumber`.</span><span class="sxs-lookup"><span data-stu-id="a6f53-121">You identify an account number attribute by setting the `Type` property of the attribute to `AccountNumber`.</span></span>  
  
 <span data-ttu-id="a6f53-122">Para obter mais informações sobre tipos de atributos, consulte [Configurar tipos de atributo](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="a6f53-122">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="adding-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="a6f53-123">Adicionando inteligência de conta com o Assistente de Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="a6f53-123">Adding Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="a6f53-124">Depois de configurar a dimensão de conta e adicioná-la a um cubo, você pode usar o Assistente de Business Intelligence para adicionar à dimensão funcionalidades de inteligência de conta, como identificação e mapeamento de tipos de conta.</span><span class="sxs-lookup"><span data-stu-id="a6f53-124">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to adding account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="a6f53-125">Para obter mais informações, consulte [Adicionar inteligência de conta a uma dimensão](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="a6f53-125">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f53-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a6f53-126">See Also</span></span>  
 <span data-ttu-id="a6f53-127">[Atributos e hierarquias de atributo](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="a6f53-127">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="a6f53-128">[Ajuda F1 do assistente de Business Intelligence](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="a6f53-128">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="a6f53-129">Tipos de dimensão</span><span class="sxs-lookup"><span data-stu-id="a6f53-129">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
