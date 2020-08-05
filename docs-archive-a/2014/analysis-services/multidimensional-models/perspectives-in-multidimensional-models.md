---
title: Perspectivas em modelos multidimensionais | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default members
- hiding objects from perspective
- renaming perspectives
- attributes [Analysis Services], default members
- removing perspectives
- perspectives [Analysis Services]
- names [Analysis Services], perspectives
- cubes [Analysis Services], perspectives
- deleting perspectives
ms.assetid: 5a3d6577-6833-4c24-820c-b65bb856157b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2d4be87ddbd691710b361d8b07d225bce37659fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571654"
---
# <a name="perspectives-in-multidimensional-models"></a><span data-ttu-id="824ae-102">Perspectivas em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="824ae-102">Perspectives in Multidimensional Models</span></span>
  <span data-ttu-id="824ae-103">Uma perspectiva é um subconjunto de um cubo criado para um determinado aplicativo ou grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="824ae-103">A perspective is a subset of a cube created for a particular application or group of users.</span></span> <span data-ttu-id="824ae-104">O próprio cubo é a perspectiva padrão.</span><span class="sxs-lookup"><span data-stu-id="824ae-104">The cube itself is the default perspective.</span></span> <span data-ttu-id="824ae-105">Uma perspectiva é exposta a um cliente como um cubo.</span><span class="sxs-lookup"><span data-stu-id="824ae-105">A perspective is exposed to a client as a cube.</span></span> <span data-ttu-id="824ae-106">Quando um usuário exibe uma perspectiva, ela aparece como outro cubo.</span><span class="sxs-lookup"><span data-stu-id="824ae-106">When a user views a perspective, it appears like another cube.</span></span> <span data-ttu-id="824ae-107">Toda alteração feita nos dados do cubo por meio de write-back da perspectiva é aplicada ao cubo original.</span><span class="sxs-lookup"><span data-stu-id="824ae-107">Any changes made to cube data through writeback in the perspective are to the original cube.</span></span> <span data-ttu-id="824ae-108">Para obter mais informações sobre exibições no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consulte [Perspectivas](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="824ae-108">For more information about the views in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], see [Perspectives](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span></span>  
  
 <span data-ttu-id="824ae-109">Use a guia **Perspectivas** do Designer de Cubo para criar ou modificar perspectivas em um cubo.</span><span class="sxs-lookup"><span data-stu-id="824ae-109">Use the **Perspectives** tab in Cube Designer to create or modify perspectives in a cube.</span></span> <span data-ttu-id="824ae-110">A primeira coluna da guia **Perspectivas** é **Objetos Cubo** , que lista todos os objetos do cubo.</span><span class="sxs-lookup"><span data-stu-id="824ae-110">The first column of the **Perspectives** tab is the **Cube Objects** column, which lists all the objects in the cube.</span></span> <span data-ttu-id="824ae-111">Corresponde à perspectiva padrão do cubo, que é o próprio cubo.</span><span class="sxs-lookup"><span data-stu-id="824ae-111">This corresponds to the default perspective for the cube, which is the cube itself.</span></span>  
  
## <a name="creating-or-deleting-perspectives"></a><span data-ttu-id="824ae-112">Criando ou excluindo perspectivas</span><span class="sxs-lookup"><span data-stu-id="824ae-112">Creating or Deleting Perspectives</span></span>  
 <span data-ttu-id="824ae-113">Você pode adicionar uma perspectiva à guia **Perspectivas** clicando em **Nova Perspectiva** no menu **Cubo** .</span><span class="sxs-lookup"><span data-stu-id="824ae-113">You can add a perspective to the **Perspectives** tab by clicking **New Perspective** on the **Cube** menu.</span></span> <span data-ttu-id="824ae-114">Pode também clicar no botão **Nova Perspectiva** na barra de ferramentas ou clicar com o botão direito do mouse no painel e clicar em **Nova Perspectiva** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="824ae-114">You can also click the **New Perspective** button on the toolbar, or right-click anywhere in the pane and click **New Perspective** on the shortcut menu.</span></span> <span data-ttu-id="824ae-115">É possível adicionar qualquer número de perspectivas a um cubo.</span><span class="sxs-lookup"><span data-stu-id="824ae-115">You can add any number of perspectives to a cube.</span></span>  
  
 <span data-ttu-id="824ae-116">Para remover uma perspectiva, primeiro clique em qualquer célula da coluna da perspectiva que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="824ae-116">To remove a perspective, first click any cell in the column for the perspective that you want to delete.</span></span> <span data-ttu-id="824ae-117">Em seguida, no menu **Cubo** , clique em **Excluir Perspectiva**.</span><span class="sxs-lookup"><span data-stu-id="824ae-117">Then, on the **Cube** menu, click **Delete Perspective**.</span></span> <span data-ttu-id="824ae-118">Você também pode clicar no botão **Excluir Perspectiva** na barra de ferramentas ou clicar com o botão direito do mouse em uma célula da perspectiva que deseja excluir e, em seguida, clicar em **Excluir Perspectiva** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="824ae-118">You can also click the **Delete Perspective** button on the toolbar, or right-click any cell in the perspective you want to delete, and then click **Delete Perspective** on the shortcut menu.</span></span>  
  
## <a name="renaming-perspectives"></a><span data-ttu-id="824ae-119">renomeando perspectivas</span><span class="sxs-lookup"><span data-stu-id="824ae-119">Renaming Perspectives</span></span>  
 <span data-ttu-id="824ae-120">A primeira linha de cada perspectiva mostra seu nome.</span><span class="sxs-lookup"><span data-stu-id="824ae-120">The first row of each perspective shows its name.</span></span> <span data-ttu-id="824ae-121">Quando você cria uma perspectiva, inicialmente, o nome é Perspectiva (seguido por um número ordinal, começando em 1, se já existir uma perspectiva chamada Perspectiva).</span><span class="sxs-lookup"><span data-stu-id="824ae-121">When you create a perspective, the name is initially Perspective (followed by an ordinal number, starting with 1, if there is already a perspective called Perspective).</span></span> <span data-ttu-id="824ae-122">Clique no nome se quiser editá-lo.</span><span class="sxs-lookup"><span data-stu-id="824ae-122">You can click the name to edit it.</span></span>  
  
## <a name="hiding-objects-from-a-perspective"></a><span data-ttu-id="824ae-123">Ocultando objetos de uma perspectiva</span><span class="sxs-lookup"><span data-stu-id="824ae-123">Hiding Objects from a Perspective</span></span>  
 <span data-ttu-id="824ae-124">Para ocultar um objeto de uma perspectiva, desmarque a caixa de seleção da linha correspondente ao objeto na coluna da perspectiva.</span><span class="sxs-lookup"><span data-stu-id="824ae-124">To hide an object from a perspective, clear the check box in the row that corresponds to the object in the column for the perspective.</span></span> <span data-ttu-id="824ae-125">Os objetos de cubo que podem ser ocultados de uma perspectiva são:</span><span class="sxs-lookup"><span data-stu-id="824ae-125">The cube objects that can be hidden from a perspective are:</span></span>  
  
-   <span data-ttu-id="824ae-126">Grupos de medidas</span><span class="sxs-lookup"><span data-stu-id="824ae-126">Measure groups</span></span>  
  
-   <span data-ttu-id="824ae-127">Medidas</span><span class="sxs-lookup"><span data-stu-id="824ae-127">Measures</span></span>  
  
-   <span data-ttu-id="824ae-128">Dimensões</span><span class="sxs-lookup"><span data-stu-id="824ae-128">Dimensions</span></span>  
  
-   <span data-ttu-id="824ae-129">Hierarquias</span><span class="sxs-lookup"><span data-stu-id="824ae-129">Hierarchies</span></span>  
  
-   <span data-ttu-id="824ae-130">Conjuntos nomeados</span><span class="sxs-lookup"><span data-stu-id="824ae-130">Named sets</span></span>  
  
-   <span data-ttu-id="824ae-131">KPIs</span><span class="sxs-lookup"><span data-stu-id="824ae-131">KPIs</span></span>  
  
-   <span data-ttu-id="824ae-132">Ações</span><span class="sxs-lookup"><span data-stu-id="824ae-132">Actions</span></span>  
  
-   <span data-ttu-id="824ae-133">Membros calculados</span><span class="sxs-lookup"><span data-stu-id="824ae-133">Calculated members</span></span>  
  
 <span data-ttu-id="824ae-134">Para exibir algum dos objetos, expanda a categoria (**Grupos de Medidas**, **Dimensões**, **KPIs**, **Cálculos**ou **Ações**) de qualquer tipo de objeto de **Objetos Cubo**.</span><span class="sxs-lookup"><span data-stu-id="824ae-134">To view any object, expand the category (**Measure Groups**, **Dimensions**, **KPIs**, **Calculations**, or **Actions**) for any object type under **Cube Objects**.</span></span> <span data-ttu-id="824ae-135">Para exibir hierarquias ou atributos de uma dimensão, primeiro expanda a dimensão e, em seguida, expanda a linha **Hierarquias** ou **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="824ae-135">To view hierarchies or attributes in a dimension, first expand a dimension, and then expand the **Hierarchies** or **Attributes** row.</span></span> <span data-ttu-id="824ae-136">Para exibir medidas de um grupo de medidas, expanda o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="824ae-136">To view measures in a measure group, expand the measure group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="824ae-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="824ae-137">See Also</span></span>  
 [<span data-ttu-id="824ae-138">Cubos em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="824ae-138">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
