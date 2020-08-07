---
title: Caixa de diálogo Criar Nova Condição ou Abrir Condição, Página Geral | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.condition.f1
ms.assetid: 106954bf-e4ba-412b-9c1a-907d06153dcd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 72e4a77df553ac8e97609e82bd51c8fd93b64b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583549"
---
# <a name="create-new-condition-or-open-condition-dialog-box-general-page"></a><span data-ttu-id="3495a-102">Caixa de diálogo Criar Nova Condição ou Abrir Condição, Página Geral</span><span class="sxs-lookup"><span data-stu-id="3495a-102">Create New Condition or Open Condition Dialog Box, General Page</span></span>
  <span data-ttu-id="3495a-103">Use esta caixa de diálogo para criar ou alterar uma condição de Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="3495a-103">Use this dialog box to create or change a Policy-Based Management condition.</span></span> <span data-ttu-id="3495a-104">A condição é uma expressão Booleana que especifica um conjunto de estados permitidos de um destino gerenciado pelo Gerenciamento Baseado em Políticas em relação às facetas.</span><span class="sxs-lookup"><span data-stu-id="3495a-104">A condition is a Boolean expression that specifies a set of allowed states of a Policy-Based Management managed target with regard to facets.</span></span> <span data-ttu-id="3495a-105">As propriedades que podem ser selecionadas na caixa **Expressão/Campo** dependem da faceta usada.</span><span class="sxs-lookup"><span data-stu-id="3495a-105">The properties that can be selected in the **Expression/Field** box depend upon the facet that is used.</span></span> <span data-ttu-id="3495a-106">Para obter mais informações sobre como condições se relacionam às facetas e às políticas, veja [Administrar servidores usando o Gerenciamento Baseado em Políticas](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="3495a-106">For more information about how conditions relate to facets and policies, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3495a-107">Opções</span><span class="sxs-lookup"><span data-stu-id="3495a-107">Options</span></span>  
 <span data-ttu-id="3495a-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3495a-108">**Name**</span></span>  
 <span data-ttu-id="3495a-109">Para uma condição nova, digite o nome da nova condição.</span><span class="sxs-lookup"><span data-stu-id="3495a-109">For a new condition, type the new condition name.</span></span> <span data-ttu-id="3495a-110">Para uma condição existente, o nome será exibido.</span><span class="sxs-lookup"><span data-stu-id="3495a-110">For an existing condition, the name is displayed.</span></span>  
  
 <span data-ttu-id="3495a-111">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="3495a-111">**Facet**</span></span>  
 <span data-ttu-id="3495a-112">A faceta usada por essa condição.</span><span class="sxs-lookup"><span data-stu-id="3495a-112">The facet used by this condition.</span></span>  
  
 <span data-ttu-id="3495a-113">**AndOr**</span><span class="sxs-lookup"><span data-stu-id="3495a-113">**AndOr**</span></span>  
 <span data-ttu-id="3495a-114">Quando você adiciona várias expressões, indica se elas devem ser unidas com **E** ou **Ou**.</span><span class="sxs-lookup"><span data-stu-id="3495a-114">When you add multiple expressions, indicates whether the expressions should be joined by using **And** or **Or**.</span></span> <span data-ttu-id="3495a-115">Permanece em branco quando há somente uma expressão.</span><span class="sxs-lookup"><span data-stu-id="3495a-115">Remains blank when there is only one expression.</span></span>  
  
 <span data-ttu-id="3495a-116">**Campo**</span><span class="sxs-lookup"><span data-stu-id="3495a-116">**Field**</span></span>  
 <span data-ttu-id="3495a-117">Cada faceta expõe uma ou mais propriedades que podem ser definidas.</span><span class="sxs-lookup"><span data-stu-id="3495a-117">Each facet exposes one or more properties that can be set.</span></span> <span data-ttu-id="3495a-118">Na caixa campo, selecione uma propriedade na lista de propriedades disponíveis, para criar uma expressão para essa condição.</span><span class="sxs-lookup"><span data-stu-id="3495a-118">In the field box, select a property from the list of available properties to create an expression for this condition.</span></span>  
  
 <span data-ttu-id="3495a-119">**Operador**</span><span class="sxs-lookup"><span data-stu-id="3495a-119">**Operator**</span></span>  
 <span data-ttu-id="3495a-120">Selecione um operador de comparação para esta expressão.</span><span class="sxs-lookup"><span data-stu-id="3495a-120">Select a comparison operator for this expression.</span></span> <span data-ttu-id="3495a-121">Os operadores são os seguintes: =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN.</span><span class="sxs-lookup"><span data-stu-id="3495a-121">Operators are as follows: =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN.</span></span> <span data-ttu-id="3495a-122">Nem todos os operadores estão disponíveis para algumas propriedades.</span><span class="sxs-lookup"><span data-stu-id="3495a-122">Not all operators are available for some properties.</span></span>  
  
 <span data-ttu-id="3495a-123">**Valor**</span><span class="sxs-lookup"><span data-stu-id="3495a-123">**Value**</span></span>  
 <span data-ttu-id="3495a-124">A configuração de valor dessa expressão.</span><span class="sxs-lookup"><span data-stu-id="3495a-124">The value setting for this expression.</span></span> <span data-ttu-id="3495a-125">Os valores permitidos dependem da faceta.</span><span class="sxs-lookup"><span data-stu-id="3495a-125">The allowed values depend on the facet.</span></span> <span data-ttu-id="3495a-126">Os valores podem ser TRUE/FALSE, cadeia de caracteres ou numéricos.</span><span class="sxs-lookup"><span data-stu-id="3495a-126">Values can be TRUE/FALSE, string, or numeric.</span></span> <span data-ttu-id="3495a-127">Os valores da cadeia de caracteres devem ser colocados entre aspas simples, por exemplo: **'AdventureWorks'**.</span><span class="sxs-lookup"><span data-stu-id="3495a-127">String values must be enclosed in single quotation marks, for example: **'AdventureWorks'**.</span></span> <span data-ttu-id="3495a-128">Nem todos os operadores estão disponíveis para algumas propriedades.</span><span class="sxs-lookup"><span data-stu-id="3495a-128">Not all operators are available for some properties.</span></span>  
  
## <a name="group-clauses"></a><span data-ttu-id="3495a-129">Agrupar Cláusulas</span><span class="sxs-lookup"><span data-stu-id="3495a-129">Group Clauses</span></span>  
 <span data-ttu-id="3495a-130">As cláusulas podem ser agrupadas para operar como uma única unidade separada do restante da consulta, assim como se coloca uma expressão entre parênteses em uma equação matemática ou uma instrução lógica.</span><span class="sxs-lookup"><span data-stu-id="3495a-130">Clauses can be grouped to operate as a single unit separate from the rest of the query, just like putting parentheses around an expression in a mathematical equation or logic statement.</span></span> <span data-ttu-id="3495a-131">O agrupamento de cláusulas é útil quando você está criando consultas complexas.</span><span class="sxs-lookup"><span data-stu-id="3495a-131">Grouping clauses is useful when you are building complex queries.</span></span>  
  
 <span data-ttu-id="3495a-132">**Para agrupar cláusulas**</span><span class="sxs-lookup"><span data-stu-id="3495a-132">**To group clauses**</span></span>  
  
-   <span data-ttu-id="3495a-133">Pressione a tecla SHIFT ou CTRL e clique em duas ou mais cláusulas para selecionar um intervalo.</span><span class="sxs-lookup"><span data-stu-id="3495a-133">Press the SHIFT or CTRL keys, and then click two or more clauses to select a range.</span></span> <span data-ttu-id="3495a-134">Clique com o botão direito do mouse na área selecionada e clique em **Agrupar Cláusulas**.</span><span class="sxs-lookup"><span data-stu-id="3495a-134">Right-click the selected area, and then click **Group Clauses**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3495a-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3495a-135">See Also</span></span>  
 [<span data-ttu-id="3495a-136">Administrar servidores com Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="3495a-136">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
