---
title: Caixa de diálogo Criar-editar cálculo nomeado (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsveditor.createnamedcalculation.f1
helpviewer_keywords:
- Named Calculation dialog box
ms.assetid: 66fb30ae-f5c5-4bfc-80ca-8c8a3a9bb30d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b6777feb47a1ce6b601d0190e413b4baae35f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568909"
---
# <a name="create-edit-named-calculation-dialog-box-analysis-services"></a><span data-ttu-id="ae6e0-102">Create-Edit Named Calculation Dialog Box (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="ae6e0-102">Create-Edit Named Calculation Dialog Box (Analysis Services)</span></span>
  <span data-ttu-id="ae6e0-103">Use a caixa de diálogo **Criar/Editar Cálculo Nomeado** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para definir ou modificar um cálculo nomeado para uma tabela em uma exibição de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ae6e0-103">Use the **Create/Edit Named Calculation** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a named calculation for a table in a data source view.</span></span> <span data-ttu-id="ae6e0-104">É possível exibir a caixa de diálogo **Criar/Editar Cálculo Nomeado** da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ae6e0-104">You can display the **Create/Edit Named Calculation** dialog box by:</span></span>  
  
-   <span data-ttu-id="ae6e0-105">Clicando em **Novo Cálculo Nomeado** no painel **Barra de Ferramentas** do **Designer de Exibição da Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="ae6e0-105">Clicking **New Named Calculation** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="ae6e0-106">Clicando com o botão direito do mouse em uma tabela no painel **Tabelas** ou **Diagrama** do **Designer de Exibição da Fonte de Dados** e selecionando **Novo Cálculo Nomeado**.</span><span class="sxs-lookup"><span data-stu-id="ae6e0-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Named Calculation**.</span></span>  
  
-   <span data-ttu-id="ae6e0-107">Clicando com o botão direito do mouse no nome de um cálculo nomeado no painel **Diagrama** do **Designer de Exibição da Fonte de Dados** e selecionando **Editar Cálculo Nomeado**.</span><span class="sxs-lookup"><span data-stu-id="ae6e0-107">Right-clicking the name of a named calculation in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Named Calculation**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae6e0-108">Opções</span><span class="sxs-lookup"><span data-stu-id="ae6e0-108">Options</span></span>  
 <span data-ttu-id="ae6e0-109">**Nome da coluna**</span><span class="sxs-lookup"><span data-stu-id="ae6e0-109">**Column Name**</span></span>  
 <span data-ttu-id="ae6e0-110">Digite o nome do cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="ae6e0-110">Type the name of the named calculation.</span></span>  
  
 <span data-ttu-id="ae6e0-111">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ae6e0-111">**Description**</span></span>  
 <span data-ttu-id="ae6e0-112">Digite a descrição opcional do cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="ae6e0-112">Type the optional description of the named calculation.</span></span>  
  
 <span data-ttu-id="ae6e0-113">**Expression**</span><span class="sxs-lookup"><span data-stu-id="ae6e0-113">**Expression**</span></span>  
 <span data-ttu-id="ae6e0-114">Digite uma expressão SQL válida que retorne um valor escalar.</span><span class="sxs-lookup"><span data-stu-id="ae6e0-114">Type a valid SQL expression that returns a scalar value.</span></span> <span data-ttu-id="ae6e0-115">A expressão é enviada ao provedor e validada na expressão seguinte:</span><span class="sxs-lookup"><span data-stu-id="ae6e0-115">The expression is sent to the provider, and validated in the following expression:</span></span>  
  
```  
SELECT <Table Name in Data Source>.* , <Expression> AS <Column Name> FROM <Table Name in Data Source>AS <Table Name in Data Source View>  
```  
  
 <span data-ttu-id="ae6e0-116">A expressão pode conter referências a outras tabelas, por meio de uma instrução de subseleção.</span><span class="sxs-lookup"><span data-stu-id="ae6e0-116">The expression can contain references to other tables, by means of a sub-select statement.</span></span> <span data-ttu-id="ae6e0-117">If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.</span><span class="sxs-lookup"><span data-stu-id="ae6e0-117">If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae6e0-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ae6e0-118">See Also</span></span>  
 <span data-ttu-id="ae6e0-119">[Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ae6e0-119">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="ae6e0-120">Designer de Exibição da Fonte de Dados &#40;Analysis Services – Dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="ae6e0-120">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
