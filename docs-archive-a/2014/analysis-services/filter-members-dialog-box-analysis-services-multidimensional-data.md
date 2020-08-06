---
title: Caixa de diálogo Filtrar Membros (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.filtermembers.f1
helpviewer_keywords:
- Filter Members dialog box
ms.assetid: 52c6da1d-9fb5-4dbc-bffa-248d11cd337c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66980b1afe9d4eed353ae18c37ed1fdd052e62b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568861"
---
# <a name="filter-members-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="687a3-102">Caixa de diálogo Filtrar Membros (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="687a3-102">Filter Members Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="687a3-103">Use a caixa de diálogo **Filtrar Membros** do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para filtrar membros de dimensão por legenda de membro, nome de membro, nome exclusivo de membro, valor de coluna de chave ou valor de coluna de valor para o nível atual ao procurar uma dimensão na guia **Navegador** do **Designer de Dimensão**.</span><span class="sxs-lookup"><span data-stu-id="687a3-103">Use the **Filter Members** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to filter dimension members by member caption, member name, member unique name, key column value, or value column value for the current level while browsing a dimension in the **Browser** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="687a3-104">Opções</span><span class="sxs-lookup"><span data-stu-id="687a3-104">Options</span></span>  
  
|<span data-ttu-id="687a3-105">Termo</span><span class="sxs-lookup"><span data-stu-id="687a3-105">Term</span></span>|<span data-ttu-id="687a3-106">Definição</span><span class="sxs-lookup"><span data-stu-id="687a3-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="687a3-107">**Expressão de filtro**</span><span class="sxs-lookup"><span data-stu-id="687a3-107">**Filter expression**</span></span>|<span data-ttu-id="687a3-108">Exibe uma grade de propriedades, operadores e valores usados para construir uma expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="687a3-108">Displays a grid of properties, operators, and values used to construct a filter expression.</span></span> <span data-ttu-id="687a3-109">Observe que depois que uma linha é adicionada, ela não pode ser removida.</span><span class="sxs-lookup"><span data-stu-id="687a3-109">Note that after a row is added, it cannot be removed.</span></span> <span data-ttu-id="687a3-110">Você deve fechar e reabrir a caixa de diálogo para especificar uma nova expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="687a3-110">You must close and reopen the dialog box to specify a new filter expression.</span></span> <span data-ttu-id="687a3-111">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="687a3-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="687a3-112">**Propriedade**: selecione a propriedade do membro a ser usada para a expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="687a3-112">**Property**: Select the property of the member to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="687a3-113">**Operador**: selecione o operador a ser usado para a expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="687a3-113">**Operator**: Select the operator to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="687a3-114">**Valor**: digite o valor da propriedade selecionada em **Propriedade** a ser avaliada usando o operador especificado em **operador**.</span><span class="sxs-lookup"><span data-stu-id="687a3-114">**Value**: Type the value of the property selected in **Property** to evaluate using the operator specified in **Operator**.</span></span>|  
|<span data-ttu-id="687a3-115">**Painel de teste**</span><span class="sxs-lookup"><span data-stu-id="687a3-115">**Test pane**</span></span>|<span data-ttu-id="687a3-116">Quando **Teste** é clicado, este painel exibe os membros retornados pela expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="687a3-116">When **Test** is clicked, this pane displays the members returned by the filter expression.</span></span> <span data-ttu-id="687a3-117">Se nenhum membro que usa os critérios especificados em **Expressão de filtro**for retornado, será exibida uma advertência.</span><span class="sxs-lookup"><span data-stu-id="687a3-117">If no members are returned using the criteria specified in **Filter expression**, a warning is displayed.</span></span>|  
|<span data-ttu-id="687a3-118">**Test**</span><span class="sxs-lookup"><span data-stu-id="687a3-118">**Test**</span></span>|<span data-ttu-id="687a3-119">Clique para testar os critérios especificados em **Expressão de filtro**.</span><span class="sxs-lookup"><span data-stu-id="687a3-119">Click to test the criteria specified in **Filter expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="687a3-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="687a3-120">See Also</span></span>  
 <span data-ttu-id="687a3-121">[Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="687a3-121">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="687a3-122">Navegador &#40;designer de dimensão&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="687a3-122">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
