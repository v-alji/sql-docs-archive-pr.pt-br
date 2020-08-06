---
title: Ocultar ou congelar colunas (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.hideunhidecolumnsdb.f1
ms.assetid: 5407aee5-6a07-4559-a2ba-2ca00a242f02
author: minewiskan
ms.author: owend
ms.openlocfilehash: 71398eecbc342b4e3f9c2445fef3023132266dac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679033"
---
# <a name="hide-or-freeze-columns-ssas-tabular"></a><span data-ttu-id="f24f0-102">Ocultar ou congelar colunas (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="f24f0-102">Hide or Freeze Columns (SSAS Tabular)</span></span>
  <span data-ttu-id="f24f0-103">No designer de modelo, se houver colunas que você não deseja exibir na tabela, será possível ocultá-las temporariamente.</span><span class="sxs-lookup"><span data-stu-id="f24f0-103">In the model designer, if there are columns that you don't want to display in a table, you can temporarily hide them.</span></span> <span data-ttu-id="f24f0-104">Ocultar uma coluna libera mais espaço na tela para adicionar novas colunas ou trabalhar somente com as colunas de dados relevantes.</span><span class="sxs-lookup"><span data-stu-id="f24f0-104">Hiding a column gives you more room on the screen to add new columns or to work with only relevant columns of data.</span></span> <span data-ttu-id="f24f0-105">Você pode ocultar e reexibir colunas do menu **Coluna** no designer de modelo, e do menu de atalho disponível de cada cabeçalho de coluna.</span><span class="sxs-lookup"><span data-stu-id="f24f0-105">You can hide and unhide columns from the **Column** menu in the model designer, and from the right-click menu available from each column header.</span></span> <span data-ttu-id="f24f0-106">Para manter a área de um modelo visível enquanto você rola para outra área do modelo, bloqueie colunas específicas em uma área congelando-as.</span><span class="sxs-lookup"><span data-stu-id="f24f0-106">To keep an area of a model visible while you scroll to another area of the model, you can lock specific columns in one area by freezing them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f24f0-107">A capacidade de ocultar colunas não visa a segurança dos dados, mas apenas a simplificação e a diminuição da lista de colunas visíveis no designer de modelo ou relatórios.</span><span class="sxs-lookup"><span data-stu-id="f24f0-107">The ability to hide columns is not intended to be used for data security, only to simplify and shorten the list of columns visible in the model designer or reports.</span></span> <span data-ttu-id="f24f0-108">Para proteger dados, você pode definir funções de segurança.</span><span class="sxs-lookup"><span data-stu-id="f24f0-108">To secure data, you can define security roles.</span></span> <span data-ttu-id="f24f0-109">As funções podem limitar metadados visíveis e dados a somente esses objetos definidos na função.</span><span class="sxs-lookup"><span data-stu-id="f24f0-109">Roles can limit viewable metadata and data to only those objects defined in the role.</span></span> <span data-ttu-id="f24f0-110">Para obter mais informações, consulte [Funções &#40;SSAS de Tabela&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="f24f0-110">For more information, see [Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="f24f0-111">Ao ocultar uma coluna, você tem a opção de ocultá-la apenas enquanto trabalha no designer de modelo ou em relatórios.</span><span class="sxs-lookup"><span data-stu-id="f24f0-111">When you hide a column, you have the option to hide the column while you are working in the model designer or in reports.</span></span> <span data-ttu-id="f24f0-112">Se você ocultar todas as colunas, a tabela inteira aparecerá em branco no designer de modelo.</span><span class="sxs-lookup"><span data-stu-id="f24f0-112">If you hide all columns, the entire table appears blank in the model designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f24f0-113">Se você tiver muitas colunas a serem ocultas, poderá criar uma perspectiva em vez de ocultar e reexibir colunas.</span><span class="sxs-lookup"><span data-stu-id="f24f0-113">If you have many columns to hide, you can create a perspective instead of hiding and unhiding columns.</span></span> <span data-ttu-id="f24f0-114">Uma perspectiva é uma exibição personalizada dos dados que facilitam o trabalho com um subconjunto de dados relacionados.</span><span class="sxs-lookup"><span data-stu-id="f24f0-114">A perspective is a custom view of the data that makes it easier to work with subset of related data.</span></span> <span data-ttu-id="f24f0-115">Para obter mais informações, consulte [Criar e gerenciar perspectivas &#40;SSAS de Tabela&#41;](perspectives-ssas-tabular.md)</span><span class="sxs-lookup"><span data-stu-id="f24f0-115">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md)</span></span>  
  
### <a name="to-hide-an-individual-column"></a><span data-ttu-id="f24f0-116">Para ocultar uma coluna individual</span><span class="sxs-lookup"><span data-stu-id="f24f0-116">To hide an individual column</span></span>  
  
1.  <span data-ttu-id="f24f0-117">No designer de modelo, selecione a tabela que contém a coluna que você deseja ocultar.</span><span class="sxs-lookup"><span data-stu-id="f24f0-117">In the model designer, select the table that contains the column that you want to hide.</span></span>  
  
2.  <span data-ttu-id="f24f0-118">Clique com o botão direito do mouse na coluna, clique em **Ocultar Colunas**e, em seguida, clique em **De Designer e Relatórios**, **De Relatórios**ou **Do Designer**.</span><span class="sxs-lookup"><span data-stu-id="f24f0-118">Right-click the column, then click **Hide Columns**, and then click **From Designer and Reports**, **From Reports**, or **From Designer**.</span></span>  
  
### <a name="to-hide-multiple-columns"></a><span data-ttu-id="f24f0-119">Para ocultar várias colunas</span><span class="sxs-lookup"><span data-stu-id="f24f0-119">To hide multiple columns</span></span>  
  
1.  <span data-ttu-id="f24f0-120">No designer de modelo, selecione a tabela que contém as colunas que você deseja ocultar.</span><span class="sxs-lookup"><span data-stu-id="f24f0-120">In the model designer, select the table that contains the columns that you want to hide.</span></span>  
  
2.  <span data-ttu-id="f24f0-121">Clique no menu **Colunas** e depois em **Ocultar e Reexibir**.</span><span class="sxs-lookup"><span data-stu-id="f24f0-121">Click on the **Columns** menu, and then click **Hide and Unhide**.</span></span>  
  
3.  <span data-ttu-id="f24f0-122">Na caixa de diálogo **Ocultar e Reexibir Colunas** , localize cada coluna que você deseja oculta e desmarque a seleção de **No Designer** e **Nos Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="f24f0-122">In the **Hide and Unhide Columns** dialog box, locate each column that you want to hide, and then deselect one or both of **In Designer** and **In Reports**.</span></span>  
  
4.  <span data-ttu-id="f24f0-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f24f0-123">Click **OK**.</span></span>  
  
### <a name="to-freeze-columns"></a><span data-ttu-id="f24f0-124">Para congelar colunas</span><span class="sxs-lookup"><span data-stu-id="f24f0-124">To freeze columns</span></span>  
  
1.  <span data-ttu-id="f24f0-125">No designer de modelo, selecione a tabela que contém as colunas que você deseja congelar.</span><span class="sxs-lookup"><span data-stu-id="f24f0-125">In the model designer, select the table that contains the columns that you want to freeze.</span></span>  
  
2.  <span data-ttu-id="f24f0-126">Selecione um ou mais colunas a serem congeladas.</span><span class="sxs-lookup"><span data-stu-id="f24f0-126">Select one or more columns to freeze.</span></span>  
  
3.  <span data-ttu-id="f24f0-127">Clique no menu **Colunas** e depois em **Congelar**.</span><span class="sxs-lookup"><span data-stu-id="f24f0-127">Click on the **Columns** menu, and then click **Freeze**..</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f24f0-128">Quando uma coluna é congelada, ela é movida para a esquerda (ou frente) da tabela no designer.</span><span class="sxs-lookup"><span data-stu-id="f24f0-128">When a column(s) is frozen, it is moved to left (or front) of the table in the designer.</span></span> <span data-ttu-id="f24f0-129">Descongelar a coluna não a move para seu local original.</span><span class="sxs-lookup"><span data-stu-id="f24f0-129">Unfreezing the column does not move it back to its original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f24f0-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f24f0-130">See Also</span></span>  
 <span data-ttu-id="f24f0-131">[Tabelas e colunas &#40;SSAS de tabela&#41;](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="f24f0-131">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="f24f0-132">[Perspectivas &#40;SSAS de tabela&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="f24f0-132">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="f24f0-133">Funções &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="f24f0-133">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
