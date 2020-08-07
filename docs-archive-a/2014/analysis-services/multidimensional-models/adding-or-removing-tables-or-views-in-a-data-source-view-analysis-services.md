---
title: Adicionando ou removendo tabelas ou exibições em uma exibição da fonte de dados (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.tablespane.f1
helpviewer_keywords:
- deleting tables
- tables [Analysis Services]
- removing tables
- adding tables
- data source views [Analysis Services], tables
- tables [Analysis Services], data source views
ms.assetid: 98307d04-6548-4d7d-9244-2371dd165249
author: minewiskan
ms.author: owend
ms.openlocfilehash: da1bc2b1ac0af7576cfe3c3593b451f78d6a9fae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583203"
---
# <a name="adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services"></a><span data-ttu-id="47b4e-102">Adicionando ou removendo tabelas ou exibições em uma exibição da fonte de dados (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="47b4e-102">Adding or Removing Tables or Views in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="47b4e-103">Depois de criar uma DSV (exibição da fonte de dados) no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], você pode modificá-lo no Designer da Exibição da Fonte de Dados adicionando ou removendo tabelas e colunas, inclusive tabelas e colunas de outra fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="47b4e-103">After you have created a data source view (DSV) in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can modify it in Data Source View Designer by adding or removing tables and columns, including tables and columns from another data source.</span></span>  
  
 <span data-ttu-id="47b4e-104">Para abrir a DSV no Designer da Exibição da Fonte de Dados, clique duas vezes na DSV no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="47b4e-104">To open the DSV in Data Source View Designer, you double-click the DSV in Solution Explorer.</span></span> <span data-ttu-id="47b4e-105">Após abrir a DSV, você pode usar o comando **Adicionar/Remover Tabelas** na barra de botões ou no menu para modificar ou estender a DSV.</span><span class="sxs-lookup"><span data-stu-id="47b4e-105">Once you open the DSV, you can use the **Add/Remove Tables** command on the button bar or menu to modify or extend the DSV.</span></span> <span data-ttu-id="47b4e-106">Você também pode trabalhar com os objetos no diagrama.</span><span class="sxs-lookup"><span data-stu-id="47b4e-106">You can also work with the objects in the diagram.</span></span> <span data-ttu-id="47b4e-107">Por exemplo, você pode selecionar um objeto e usar a tecla Delete em seu teclado para remover um objeto.</span><span class="sxs-lookup"><span data-stu-id="47b4e-107">For example, you can select an object and then use the Delete key on your keyboard to remove an object.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="47b4e-108">Tenha cuidado ao remover uma tabela.</span><span class="sxs-lookup"><span data-stu-id="47b4e-108">Use caution when removing a table.</span></span> <span data-ttu-id="47b4e-109">Remover uma tabela exclui todas as colunas e as relações associadas do DSV e invalida todos os objetos associados àquela tabela.</span><span class="sxs-lookup"><span data-stu-id="47b4e-109">Removing a table deletes all the associated columns and relationships from the DSV and invalidates all objects bound to that table.</span></span>  
  
## <a name="selecting-tables-or-views-to-add-or-remove"></a><span data-ttu-id="47b4e-110">Selecionando tabelas ou exibições para adicionar ou remover</span><span class="sxs-lookup"><span data-stu-id="47b4e-110">Selecting Tables or Views to Add or Remove</span></span>  
 <span data-ttu-id="47b4e-111">Usando a caixa de diálogo **Adicionar/Remover Tabelas** , é possível mover tabelas ou exibições entre as listas **Objetos disponíveis** e **Objetos incluídos** .</span><span class="sxs-lookup"><span data-stu-id="47b4e-111">Using the **Add/Remove Tables** dialog box, you can move tables or views between the **Available objects** and **Included objects** lists.</span></span> <span data-ttu-id="47b4e-112">A lista **Objetos disponíveis** inicialmente inclui todas as tabelas ou exibições da fonte de dados primária que ainda não estão na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="47b4e-112">The **Available objects** list initially includes any tables or views in the primary data source that are not already in the data source view.</span></span> <span data-ttu-id="47b4e-113">Se a fonte de dados primária oferecer suporte à função `OPENROWSET`, também será possível adicionar tabelas e exibições de outras fontes de dados do projeto ou banco de dados.</span><span class="sxs-lookup"><span data-stu-id="47b4e-113">If the primary data source supports the `OPENROWSET` function, you can also add tables or views from other data sources in the project or database.</span></span>  
  
 <span data-ttu-id="47b4e-114">Quando você adiciona ou remove uma tabela da DSV, também adiciona ou remove essa tabela do diagrama selecionado na DSV.</span><span class="sxs-lookup"><span data-stu-id="47b4e-114">Adding or removing a table to the DSV also adds or removes the table to the currently selected diagram in the DSV.</span></span> <span data-ttu-id="47b4e-115">Para obter mais informações sobre diagramas, consulte [Trabalhar com diagramas em um Designer de exibição da fonte de dados &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="47b4e-115">For more information on diagrams, see [Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span></span>  
  
 <span data-ttu-id="47b4e-116">Depois de mover uma tabela para a lista **Objetos incluídos** na caixa de diálogo **Adicionar/Remover Tabelas** , você pode adicionar todas as tabelas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="47b4e-116">After you move a table to the **Included objects** list in the **Add/Remove Tables** dialog box, you can add all related tables.</span></span> <span data-ttu-id="47b4e-117">Essa operação adiciona as tabelas de acordo com as restrições de chave estrangeira da fonte de dados, se existir alguma.</span><span class="sxs-lookup"><span data-stu-id="47b4e-117">This operation adds tables according to foreign key constraints in the data source, if such constraints exist.</span></span> <span data-ttu-id="47b4e-118">Se não existirem restrições de chave estrangeira, use a propriedade `NameMatchingCriteria` da exibição da fonte de dados para determinar as relações especificando um critério para a correspondência dos nomes de colunas das tabelas para gerar relações similares.</span><span class="sxs-lookup"><span data-stu-id="47b4e-118">If foreign key constraints do not exist, you can use the `NameMatchingCriteria` property of the data source view to determine relationships by specifying a criterion for matching column names in tables to generate likely relationships.</span></span> <span data-ttu-id="47b4e-119">Se a `NameMatchingCriteria` propriedade for especificada para a exibição da fonte de dados, clique em **adicionar tabelas relacionadas** para adicionar tabelas da fonte de dados que têm nomes de coluna correspondentes.</span><span class="sxs-lookup"><span data-stu-id="47b4e-119">If the `NameMatchingCriteria`property is specified for the data source view, click **Add Related Tables** to add tables from the data source that have matching column names.</span></span> <span data-ttu-id="47b4e-120">Para obter mais informações sobre como definir a `NameMatchingCriteria` propriedade, consulte [exibições da fonte de dados em modelos multidimensionais](data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="47b4e-120">For more information about setting the `NameMatchingCriteria` property, see [Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47b4e-121">Adicionar objetos a uma exibição da fonte de dados ou removê-los dela não afeta a fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="47b4e-121">Adding or removing objects in a data source view does not affect the underlying data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b4e-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="47b4e-122">See Also</span></span>  
 <span data-ttu-id="47b4e-123">[Exibições da fonte de dados em modelos multidimensionais](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="47b4e-123">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="47b4e-124">Trabalhar com diagramas em um Designer de exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="47b4e-124">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
  
