---
title: Criando conjuntos nomeados no escopo da sessão (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE SET statement
- session-scoped named sets [MDX]
ms.assetid: b751e1e4-6d4c-4d36-a28d-ffdaaee0f1c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d35bd61dcc59eca8bcb920ed99f2e791631047c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681866"
---
# <a name="creating-session-scoped-named-sets-mdx"></a><span data-ttu-id="48d6d-102">Criando conjuntos nomeados no escopo da sessão (MDX)</span><span class="sxs-lookup"><span data-stu-id="48d6d-102">Creating Session-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="48d6d-103">Para criar um conjunto nomeado que esteja disponível por meio de uma sessão da linguagem MDX, use a instrução [CREATE SET](/sql/mdx/mdx-data-definition-create-set) .</span><span class="sxs-lookup"><span data-stu-id="48d6d-103">To create a named set that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE SET](/sql/mdx/mdx-data-definition-create-set) statement.</span></span> <span data-ttu-id="48d6d-104">Um conjunto nomeado criado com a instrução CREATE SET não será removido até que a sessão MDX seja encerrada.</span><span class="sxs-lookup"><span data-stu-id="48d6d-104">A named set that is created by using the CREATE SET statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="48d6d-105">Como discutido neste tópico, a sintaxe da palavra-chave WITH é direta e fácil usar.</span><span class="sxs-lookup"><span data-stu-id="48d6d-105">As discussed in this topic, the syntax of the WITH keyword is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48d6d-106">Para obter mais informações sobre conjuntos nomeados, consulte [Criando conjuntos nomeados em MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="48d6d-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="create-set-syntax"></a><span data-ttu-id="48d6d-107">Sintaxe de CREATE SET</span><span class="sxs-lookup"><span data-stu-id="48d6d-107">CREATE SET Syntax</span></span>  
 <span data-ttu-id="48d6d-108">Use a sintaxe a seguir para uma instrução CREATE SET:</span><span class="sxs-lookup"><span data-stu-id="48d6d-108">Use the following syntax for the CREATE SET statement:</span></span>  
  
```  
CREATE SESSION SET [CURRENTCUBE. | <cube name>.]<Set Identifier> AS <Set Expression>  
```  
  
 <span data-ttu-id="48d6d-109">Na sintaxe de CREATE SET, o parâmetro `cube name` contém o nome do cubo que contém os membros do conjunto nomeado.</span><span class="sxs-lookup"><span data-stu-id="48d6d-109">In the CREATE SET syntax, the `cube name` parameter contains the name of the cube that contains the members for the named set.</span></span> <span data-ttu-id="48d6d-110">Se o parâmetro `cube name` não for especificado, o cubo atual será usado como o cubo que contém o membro do conjunto nomeado.</span><span class="sxs-lookup"><span data-stu-id="48d6d-110">If the `cube name` parameter is not specified, the current cube will be used as the cube that contains the member for the named set.</span></span> <span data-ttu-id="48d6d-111">Além disso, o parâmetro `Set_Identifier` contém o alias do conjunto nomeado, e o parâmetro `Set_Expression` contém a expressão de conjunto à qual o alias do conjunto nomeado fará referência.</span><span class="sxs-lookup"><span data-stu-id="48d6d-111">Also, the `Set_Identifier` parameter contains the alias for the named set, and the `Set_Expression` parameter contains the set expression to which the named set alias will refer.</span></span>  
  
## <a name="create-set-example"></a><span data-ttu-id="48d6d-112">Exemplo de CREATE SET</span><span class="sxs-lookup"><span data-stu-id="48d6d-112">CREATE SET Example</span></span>  
 <span data-ttu-id="48d6d-113">O exemplo a seguir usa a instrução CREATE SET para criar o conjunto nomeado `SetCities_2_3` com base no cubo Loja.</span><span class="sxs-lookup"><span data-stu-id="48d6d-113">The following example uses the CREATE SET statement to create the `SetCities_2_3` named set based on the Store cube.</span></span> <span data-ttu-id="48d6d-114">Os membros do conjunto nomeado `SetCities_2_3` são as lojas localizadas em Cidade 2 e Cidade 3.</span><span class="sxs-lookup"><span data-stu-id="48d6d-114">The members of the `SetCities_2_3` named set are the stores within City 2 and City 3.</span></span>  
  
```  
create Session set [Store].[SetCities_2_3] as  
{[Data Stores].[ByLocation].[State].&[CA].&[City 02],  
[Data Stores].[ByLocation].[State].&[NH].&[City 03]}  
```  
  
 <span data-ttu-id="48d6d-115">Ao usar a instrução CREATE SET para definir o conjunto nomeado `SetCities_2_3` , esse conjunto nomeado continuará disponível durante a sessão MDX atual.</span><span class="sxs-lookup"><span data-stu-id="48d6d-115">By using the CREATE SET statement to define the `SetCities_2_3` named set, this named set remains available for the length of the current MDX session.</span></span> <span data-ttu-id="48d6d-116">O exemplo a seguir é uma consulta válida que retornaria os membros de Cidade 2 e Cidade 3 e que poderia ser executada a qualquer momento após a criação do conjunto nomeado `SetCities_2_3` e antes do fim da sessão.</span><span class="sxs-lookup"><span data-stu-id="48d6d-116">The following example is a valid query that would return City 2 and City 3 members, and that could be run anytime after you create the `SetCities_2_3` named set and before the session closes.</span></span>  
  
```  
select SetCities_2_3 on 0 from [Store]  
```  
  
## <a name="see-also"></a><span data-ttu-id="48d6d-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48d6d-117">See Also</span></span>  
 [<span data-ttu-id="48d6d-118">Criando conjuntos nomeados no escopo da consulta &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="48d6d-118">Creating Query-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-query-scoped-named-sets.md)  
  
  
