---
title: Propriedades de membro definidas pelo usuário (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- custom member properties [MDX]
ms.assetid: b64cc581-e784-42c4-bec8-932abd687423
author: minewiskan
ms.author: owend
ms.openlocfilehash: 75e5df5a0677ee205b5517f4c7ca89a390426971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680094"
---
# <a name="user-defined-member-properties-mdx"></a><span data-ttu-id="f5085-102">Propriedades do membro definidas pelo usuário (MDX)</span><span class="sxs-lookup"><span data-stu-id="f5085-102">User-Defined Member Properties (MDX)</span></span>
  <span data-ttu-id="f5085-103">É possível adicionar propriedades do membro definidas pelo usuário a um nível nomeado específico de uma dimensão como relações de atributo.</span><span class="sxs-lookup"><span data-stu-id="f5085-103">User-defined member properties can be added to a specific named level in a dimension as attribute relationships.</span></span> <span data-ttu-id="f5085-104">Não é possível adicionar propriedades do membro definidas pelo usuário ao nível `(All)` de uma hierarquia ou à própria hierarquia.</span><span class="sxs-lookup"><span data-stu-id="f5085-104">User-defined member properties cannot be added to the `(All)` level of a hierarchy, or to the hierarchy itself.</span></span>  
  
## <a name="creating-user-defined-member-properties"></a><span data-ttu-id="f5085-105">Criando propriedades do membro definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f5085-105">Creating User-Defined Member Properties</span></span>  
 <span data-ttu-id="f5085-106">Propriedades do membro definidas pelo usuário podem ser adicionadas a dimensões ou cubos com base em servidor pela interface de usuário ou programaticamente:</span><span class="sxs-lookup"><span data-stu-id="f5085-106">User-defined member properties can be added to server-based dimensions or cubes either through the user interface or programmatically:</span></span>  
  
-   <span data-ttu-id="f5085-107">Para adicionar propriedades do membro definidas pelo usuário através da interface do usuário, use o Designer de Dimensão no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5085-107">To add user-defined member properties through the user interface, you use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="f5085-108">Para obter mais informações, consulte [Definir Relações de Atributos](../attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="f5085-108">For more information, see [Define Attribute Relationships](../attribute-relationships-define.md).</span></span>  
  
-   <span data-ttu-id="f5085-109">Para adicionar propriedades do membro definidas pelo usuário de forma programática, o aplicativo pode usar o Objetos de Gerenciamento de Análise (AMO) ou uma combinação de XML for Analysis (XMLA) e Analysis Services Scripting Language (ASSL).</span><span class="sxs-lookup"><span data-stu-id="f5085-109">To add user-defined member properties programmatically, your application can use either Analysis Manager Objects (AMO) or a combination of XML for Analysis (XMLA) and Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="f5085-110">Para obter mais informações, consulte [Relações de atributos](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="f5085-110">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
## <a name="retrieving-user-defined-member-properties"></a><span data-ttu-id="f5085-111">Recuperando propriedades do membro definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f5085-111">Retrieving User-Defined Member Properties</span></span>  
 <span data-ttu-id="f5085-112">Você pode recuperar propriedades do membro definidas pelo usuário usando a `PROPERTIES` palavra-chave ou a função [Properties](/sql/mdx/properties-mdx) .</span><span class="sxs-lookup"><span data-stu-id="f5085-112">You can retrieve user-defined member properties using either the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
### <a name="using-the-properties-keyword-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="f5085-113">Usando a palavra-chave PROPERTIES para recuperar propriedades do membro definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f5085-113">Using the PROPERTIES Keyword to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="f5085-114">A sintaxe que recupera as propriedades do membro definidas pelo usuário é similar àquela usada para recuperar propriedades do membro do nível intrínsecas, como mostrada na sintaxe a seguir:</span><span class="sxs-lookup"><span data-stu-id="f5085-114">The syntax that retrieves user-defined member properties is similar to that used to retrieve intrinsic level member properties, as shown in the following syntax:</span></span>  
  
 `DIMENSION PROPERTIES [Dimension.]Level.<Custom_Member_Property>`  
  
 <span data-ttu-id="f5085-115">A palavra-chave `PROPERTIES` aparece depois da expressão de conjunto da especificação de eixo.</span><span class="sxs-lookup"><span data-stu-id="f5085-115">The `PROPERTIES` keyword appears after the set expression of the axis specification.</span></span> <span data-ttu-id="f5085-116">Por exemplo, na consulta MDX a seguir, a palavra-chave `PROPERTIES` recupera as propriedades do membro definidas pelo usuário `List Price` e `Dealer Price` e aparece depois da expressão de conjunto que identifica os produtos vendidos em janeiro:</span><span class="sxs-lookup"><span data-stu-id="f5085-116">For example, the following MDX query the `PROPERTIES` keyword retrieves the `List Price` and `Dealer Price` user-defined member properties and appears after the set expression that identifies the products sold in January:</span></span>  
  
```  
SELECT   
   CROSSJOIN([Ship Date].[Calendar].[Calendar Year].Members,   
             [Measures].[Sales Amount]) ON COLUMNS,  
   NON EMPTY Product.Product.MEMBERS  
   DIMENSION PROPERTIES   
              Product.Product.[List Price],  
              Product.Product.[Dealer Price]  ON ROWS  
FROM [Adventure Works]  
WHERE ([Date].[Month of Year].[January])   
```  
  
### <a name="using-the-properties-function-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="f5085-117">Usando a função Properties para recuperar propriedades do membro definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f5085-117">Using the Properties Function to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="f5085-118">Como alternativa, você pode acessar as propriedades do membro personalizadas com a função `Properties`.</span><span class="sxs-lookup"><span data-stu-id="f5085-118">Alternatively, you can access custom member properties with the `Properties` function.</span></span> <span data-ttu-id="f5085-119">Por exemplo, a consulta MDX a seguir usa a palavra-chave `WITH` para criar um membro calculado formado pela propriedade do membro `List Price`:</span><span class="sxs-lookup"><span data-stu-id="f5085-119">For example, the following MDX query uses the `WITH` keyword to create a calculated member consisting of the `List Price` member property:</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Product List Price] AS  
   [Product].[Product].CurrentMember.Properties("List Price")  
SELECT   
   [Measures].[Product List Price] on COLUMNS,  
   [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="f5085-120">Para obter mais informações sobre como criar membros calculados, consulte [Criando membros calculados em MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="f5085-120">For more information about building calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5085-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f5085-121">See Also</span></span>  
 <span data-ttu-id="f5085-122">[Usando propriedades do membro &#40;MDX&#41;](mdx-member-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f5085-122">[Using Member Properties &#40;MDX&#41;](mdx-member-properties.md) </span></span>  
 [<span data-ttu-id="f5085-123">Properties &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f5085-123">Properties &#40;MDX&#41;</span></span>](/sql/mdx/properties-mdx)  
  
  
