---
title: Caixa de diálogo colunas de chave (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.dataitemCollection.f1
helpviewer_keywords:
- DataItem Collection dialog box
ms.assetid: 585f27f2-d5eb-4516-b29a-2084010b7d51
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a72a9e137700ddee822e68901bfde971637d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570958"
---
# <a name="key-columns-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="6f1dd-102">Caixa de diálogo Colunas de Chave (Analysis Services - Dados multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="6f1dd-102">Key Columns Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="6f1dd-103">Use a caixa de diálogo **Colunas de Chave** para alterar a propriedade **KeyColumns** de um atributo.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-103">Use the **Key Columns** dialog box to change the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="6f1dd-104">Para obter mais informações, consulte [Modificar a propriedade KeyColumn de um atributo](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="6f1dd-104">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
 <span data-ttu-id="6f1dd-105">**Para exibir a caixa de diálogo Colunas de Chave**</span><span class="sxs-lookup"><span data-stu-id="6f1dd-105">**To display the Key Columns dialog box**</span></span>  
  
-   <span data-ttu-id="6f1dd-106">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], selecione um atributo e, na janela **Propriedades** , clique no botão de reticências (**...**) associado à propriedade **KeyColumns** desse atributo.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-106">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select an attribute, and in the **Properties** window, click the ellipsis button (**...**) associated with the **KeyColumns** property of that attribute.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6f1dd-107">Opções</span><span class="sxs-lookup"><span data-stu-id="6f1dd-107">Options</span></span>  
 <span data-ttu-id="6f1dd-108">**Tabela de origem**</span><span class="sxs-lookup"><span data-stu-id="6f1dd-108">**Source table**</span></span>  
 <span data-ttu-id="6f1dd-109">Selecione a tabela de origem para a qual você quer selecionar as colunas de chave.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-109">Select the source table for which you want to select its key columns.</span></span> <span data-ttu-id="6f1dd-110">Você pode selecionar a tabela de origem em uma lista que contém todas as tabelas na Exibição da Fonte de Dados.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-110">You can select the source table from a list of all tables in the Data Source View.</span></span>  
  
 <span data-ttu-id="6f1dd-111">**Colunas disponíveis**</span><span class="sxs-lookup"><span data-stu-id="6f1dd-111">**Available Columns**</span></span>  
 <span data-ttu-id="6f1dd-112">Selecione as colunas que deseja usar como colunas de chave.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-112">Select the columns that you want to use as key columns.</span></span> <span data-ttu-id="6f1dd-113">Você pode selecionar colunas de uma lista de colunas na **Tabela de origem** especificada que não tenham ainda sido selecionadas como colunas de chave.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-113">You can select the columns from a list of columns in the specified **Source table** that have not yet been selected as key columns.</span></span>  
  
 <span data-ttu-id="6f1dd-114">Para adicionar as colunas selecionadas à lista **Colunas de Chave** , clique no botão **>** .</span><span class="sxs-lookup"><span data-stu-id="6f1dd-114">To add the selected columns to the **Key Columns** list, click the **>** button.</span></span>  
  
 <span data-ttu-id="6f1dd-115">**Colunas de Chave**</span><span class="sxs-lookup"><span data-stu-id="6f1dd-115">**Key Columns**</span></span>  
 <span data-ttu-id="6f1dd-116">Defina a ordem das colunas de chave selecionadas.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-116">Define the order of the selected key columns.</span></span> <span data-ttu-id="6f1dd-117">A ordem das colunas de chave é importante ao se definir a chave composta correta.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-117">The order of the key columns is important in defining the correct composite key.</span></span> <span data-ttu-id="6f1dd-118">Para ordenar ou reordenar a lista de colunas de chave, selecione uma coluna e clique nos botões **Acima** ou **Abaixo** .</span><span class="sxs-lookup"><span data-stu-id="6f1dd-118">To order or reorder the list of key columns, select a column, and then click the **Up** or **Down** buttons.</span></span>  
  
 <span data-ttu-id="6f1dd-119">Para remover uma coluna de chave da lista **Colunas de Chave** , selecione a coluna e clique no botão **\<** .</span><span class="sxs-lookup"><span data-stu-id="6f1dd-119">To remove a column from the **Key Columns** list, select the column and click the **\<** button.</span></span>  
  
 <span data-ttu-id="6f1dd-120">**Limpeza**</span><span class="sxs-lookup"><span data-stu-id="6f1dd-120">**Up**</span></span>  
 <span data-ttu-id="6f1dd-121">Clique para mover a coluna selecionada em **Colunas de Chave** uma posição acima.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-121">Click to move the column selected in **Key Columns** up one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f1dd-122">Esta opção só será habilitada se a lista contiver mais de uma coluna e uma coluna estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-122">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 <span data-ttu-id="6f1dd-123">**Down**</span><span class="sxs-lookup"><span data-stu-id="6f1dd-123">**Down**</span></span>  
 <span data-ttu-id="6f1dd-124">Clique para mover a coluna selecionada em **Colunas de Chave** uma posição abaixo.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-124">Click to move the column selected in **Key Columns** down one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f1dd-125">Esta opção só será habilitada se a lista contiver mais de uma coluna e uma coluna estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-125">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 **>**  
 <span data-ttu-id="6f1dd-126"> Clique para adicionar uma nova coluna ao final das colunas listadas em **Colunas de Chave**.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-126">Click to add a new column to the end of the columns listed in **Key Columns**.</span></span>  
  
 **<**  
 <span data-ttu-id="6f1dd-127"> Clique para remover a coluna selecionada das colunas listadas em **Colunas de Chave**.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-127">Click to remove the selected column from the columns listed in **Key Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1dd-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f1dd-128">See Also</span></span>  
 [<span data-ttu-id="6f1dd-129">Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="6f1dd-129">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
