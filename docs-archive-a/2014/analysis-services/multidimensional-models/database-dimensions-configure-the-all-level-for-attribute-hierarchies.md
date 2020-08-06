---
title: Configurar o nível (All) para hierarquias de atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- All members
- IsAggregatable property
- topmost levels [Analysis Services]
- (All) levels
- AttributeAllMemberName property
- levels [Analysis Services]
- members [Analysis Services], All
- AllMemberName property
ms.assetid: 0cb35e6f-b10f-483d-b893-78f6ca3979fd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9874a8c8a6861bc7d9e44271b089e8af3a4c0ae2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680118"
---
# <a name="configure-the-all-level-for-attribute-hierarchies"></a><span data-ttu-id="bf47e-102">Configurar o nível (All) para hierarquias de atributo</span><span class="sxs-lookup"><span data-stu-id="bf47e-102">Configure the (All) Level for Attribute Hierarchies</span></span>
  <span data-ttu-id="bf47e-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , o nível (All) é um nível opcional gerado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="bf47e-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the (All) level is an optional, system-generated level.</span></span> <span data-ttu-id="bf47e-104">Contém apenas um membro, cujo valor é a agregação de valores de todos os membros do nível imediatamente subordinado.</span><span class="sxs-lookup"><span data-stu-id="bf47e-104">It contains only one member whose value is the aggregation of the values of all members in the immediately subordinate level.</span></span> <span data-ttu-id="bf47e-105">Este membro é chamado de membro All.</span><span class="sxs-lookup"><span data-stu-id="bf47e-105">This member is called the All member.</span></span> <span data-ttu-id="bf47e-106">Trata-se de um membro gerado pelo sistema e que não é incluído na tabela de dimensões.</span><span class="sxs-lookup"><span data-stu-id="bf47e-106">It is a system-generated member that is not contained in the dimension table.</span></span> <span data-ttu-id="bf47e-107">Como o membro do nível (All) está no topo da hierarquia, seu valor é a agregação consolidada dos valores de todos os membros da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="bf47e-107">Because the member in the (All) level is at the top of the hierarchy, the member's value is the consolidated aggregation of the values of all members in the hierarchy.</span></span> <span data-ttu-id="bf47e-108">Geralmente, o membro All funciona como membro padrão de uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="bf47e-108">The All member often serves as the default member of a hierarchy.</span></span>  
  
 <span data-ttu-id="bf47e-109">A existência de um nível (All) em uma hierarquia de atributos depende da configuração da propriedade `IsAggregatable` do atributo e a existência de um nível (All) na hierarquia definida pelo usuário depende da propriedade `IsAggregatable` do atributo em seu nível mais alto.</span><span class="sxs-lookup"><span data-stu-id="bf47e-109">The presence of an (All) level in an attribute hierarchy depends on the `IsAggregatable` property setting for the attribute and the presence of an (All) level in a user-defined hierarchy depends on the `IsAggregatable` property of the attribute at the top-most level of user-defined hierarchy.</span></span> <span data-ttu-id="bf47e-110">Se a propriedade `IsAggregatable` for definida como `True`, existirá um nível (All).</span><span class="sxs-lookup"><span data-stu-id="bf47e-110">If the `IsAggregatable` property is set to `True`, an (All) level will exist.</span></span> <span data-ttu-id="bf47e-111">A hierarquia não terá um nível (All) se a propriedade `IsAggregatable` estiver configurada como `False`.</span><span class="sxs-lookup"><span data-stu-id="bf47e-111">A hierarchy has no (All) level if the `IsAggregatable` property is set to `False`.</span></span>  
  
## <a name="establishing-the-topmost-level"></a><span data-ttu-id="bf47e-112">Estabelecendo o nível mais alto</span><span class="sxs-lookup"><span data-stu-id="bf47e-112">Establishing the Topmost Level</span></span>  
 <span data-ttu-id="bf47e-113">Se a propriedade `IsAggregatable` estiver configurada como `False` no atributo de origem de um nível da hierarquia, nenhum nível agregável pode aparecer acima dele na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="bf47e-113">If the `IsAggregatable` property is set to `False` on the source attribute of a level in a hierarchy, then no aggregatable level can appear in the hierarchy above that level.</span></span> <span data-ttu-id="bf47e-114">Um nível não agregável deve ser o nível mais alto de qualquer hierarquia ou a propriedade `IsAggregatable` dos atributos de origem de todos os níveis acima dele também deve ser configurada como `False`.</span><span class="sxs-lookup"><span data-stu-id="bf47e-114">A non-aggregatable level must be the topmost level of any hierarchy or the `IsAggregatable` property of the source attributes for any levels above it must also be set to `False`.</span></span>  
  
## <a name="all-member-and-all-level"></a><span data-ttu-id="bf47e-115">Membro e nível (All)</span><span class="sxs-lookup"><span data-stu-id="bf47e-115">All Member and (All) Level</span></span>  
 <span data-ttu-id="bf47e-116">O único membro do nível (All) é chamado de membro All.</span><span class="sxs-lookup"><span data-stu-id="bf47e-116">The single member of the (All) level is called the All member.</span></span> <span data-ttu-id="bf47e-117">A `AttributeAllMemberName` propriedade em uma dimensão especifica o nome do membro All para atributos em uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="bf47e-117">The `AttributeAllMemberName`property on a dimension specifies the name of the All member for attributes in a dimension.</span></span> <span data-ttu-id="bf47e-118">A propriedade `AllMemberName` em uma hierarquia especifica o nome do membro All para seus atributos.</span><span class="sxs-lookup"><span data-stu-id="bf47e-118">The `AllMemberName` property on a hierarchy specifies the name of the All member for the hierarchy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf47e-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bf47e-119">See Also</span></span>  
 [<span data-ttu-id="bf47e-120">Definir um membro padrão</span><span class="sxs-lookup"><span data-stu-id="bf47e-120">Define a Default Member</span></span>](attribute-properties-define-a-default-member.md)  
  
  
