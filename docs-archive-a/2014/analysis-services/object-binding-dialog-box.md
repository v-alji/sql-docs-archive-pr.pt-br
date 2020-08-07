---
title: Caixa de diálogo Associação de objetos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.objectbinding.f1
helpviewer_keywords:
- Object Binding dialog box
ms.assetid: 2bb5ad7c-2962-4559-8c95-cf7148bd2e72
author: minewiskan
ms.author: owend
ms.openlocfilehash: a10c91e0222b826066aeede96aa665cc22540637
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575393"
---
# <a name="object-binding-dialog-box"></a><span data-ttu-id="02185-102">Caixa de diálogo Associação de Objetos</span><span class="sxs-lookup"><span data-stu-id="02185-102">Object Binding Dialog Box</span></span>
  <span data-ttu-id="02185-103">Use a caixa de diálogo **Associação de Objetos** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para definir associações entre a propriedade de um objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e uma tabela ou coluna em uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="02185-103">Use the **Object Binding** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define bindings between the property of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object and a table or column in a data source view.</span></span> <span data-ttu-id="02185-104">É possível exibir a caixa de diálogo **Associação de Objetos** selecionando **(nova)** na lista suspensa para obter o valor das seguintes propriedades de um objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] na janela **Propriedades** do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="02185-104">You can display the **Object Binding** dialog box by selecting **(new)** from the drop-down list for the value of the following properties of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span></span>  
  
-   <span data-ttu-id="02185-105">NameColumn</span><span class="sxs-lookup"><span data-stu-id="02185-105">NameColumn</span></span>  
  
-   <span data-ttu-id="02185-106">ValueColumn</span><span class="sxs-lookup"><span data-stu-id="02185-106">ValueColumn</span></span>  
  
-   <span data-ttu-id="02185-107">CustomRollupColumn</span><span class="sxs-lookup"><span data-stu-id="02185-107">CustomRollupColumn</span></span>  
  
-   <span data-ttu-id="02185-108">CustomRollupPropertiesColumn</span><span class="sxs-lookup"><span data-stu-id="02185-108">CustomRollupPropertiesColumn</span></span>  
  
-   <span data-ttu-id="02185-109">UnaryOperatorColumn</span><span class="sxs-lookup"><span data-stu-id="02185-109">UnaryOperatorColumn</span></span>  
  
## <a name="options"></a><span data-ttu-id="02185-110">Opções</span><span class="sxs-lookup"><span data-stu-id="02185-110">Options</span></span>  
 <span data-ttu-id="02185-111">**Tipo de associação**</span><span class="sxs-lookup"><span data-stu-id="02185-111">**Binding type**</span></span>  
 <span data-ttu-id="02185-112">Selecione a associação a ser usada para o objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02185-112">Select the binding to use for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="02185-113">Os seguintes tipos de associação podem ser usados:</span><span class="sxs-lookup"><span data-stu-id="02185-113">The following types of binding can be used:</span></span>  
  
 <span data-ttu-id="02185-114">Associação de coluna</span><span class="sxs-lookup"><span data-stu-id="02185-114">Column binding</span></span>  
 <span data-ttu-id="02185-115">Associa o objeto a uma tabela e coluna existentes dentro de uma exibição de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="02185-115">Binds the object to an existing table and column within a data source view.</span></span>  
  
 <span data-ttu-id="02185-116">Gerar coluna</span><span class="sxs-lookup"><span data-stu-id="02185-116">Generate column</span></span>  
 <span data-ttu-id="02185-117">Indica que a nova coluna deve ser definida na exibição da fonte de dados e uma associação de coluna deve ser associada a ela.</span><span class="sxs-lookup"><span data-stu-id="02185-117">Indicates that a new column is to be defined in the data source view, and a column binding is then associated with it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02185-118">Se esta opção estiver selecionada, execute o **Assistente de Geração de Esquema** antes de implantar o objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02185-118">If this option is selected, you must run the **Schema Generation Wizard** before deploying the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="02185-119">Associação de linha</span><span class="sxs-lookup"><span data-stu-id="02185-119">Row binding</span></span>  
 <span data-ttu-id="02185-120">Associa o objeto a uma linha em uma tabela de fatos e é usada para facilitar medidas de contagem com base no número de linhas processadas na tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="02185-120">Binds the object to a row in a fact table and is used to facilitate count measures based on the number of rows processed in the fact table.</span></span>  
  
 <span data-ttu-id="02185-121">**Tabela de origem**</span><span class="sxs-lookup"><span data-stu-id="02185-121">**Source table**</span></span>  
 <span data-ttu-id="02185-122">Exibe uma lista de tabelas na exibição da fonte de dados associada ao objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02185-122">Displays a list of tables in the data source view associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="02185-123">**Coluna de origem**</span><span class="sxs-lookup"><span data-stu-id="02185-123">**Source column**</span></span>  
 <span data-ttu-id="02185-124">Exibe uma lista das colunas da tabela selecionada na **Tabela de origem**.</span><span class="sxs-lookup"><span data-stu-id="02185-124">Displays a list of columns in the table selected in **Source table**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02185-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="02185-125">See Also</span></span>  
 [<span data-ttu-id="02185-126">Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="02185-126">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
