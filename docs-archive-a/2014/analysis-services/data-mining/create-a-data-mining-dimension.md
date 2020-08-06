---
title: Criar uma dimensão de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], dimensions
ms.assetid: 9f0c39e5-3516-43ab-b203-f3f6dbcff89a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 265cf671bbc825258f0b2bd6627690e8c52f252b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678353"
---
# <a name="create-a-data-mining-dimension"></a><span data-ttu-id="0b498-102">Criar uma dimensão de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="0b498-102">Create a Data Mining Dimension</span></span>
  <span data-ttu-id="0b498-103">Se a sua estrutura de mineração é baseada em um cubo OLAP, você pode criar uma dimensão que possua o conteúdo do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="0b498-103">If your mining structure is based on an OLAP cube, you can create a dimension that contains the content of the mining model.</span></span> <span data-ttu-id="0b498-104">É possível incorporar a dimensão de volta no cubo de origem.</span><span class="sxs-lookup"><span data-stu-id="0b498-104">You can then incorporate the dimension back into the source cube.</span></span>  
  
 <span data-ttu-id="0b498-105">Você também pode procurar a dimensão, usá-la para explorar os resultados do modelo, ou consultar a dimensão usando MDX.</span><span class="sxs-lookup"><span data-stu-id="0b498-105">You can also browse the dimension, use it to explore the model results, or query the dimension using MDX.</span></span>  
  
### <a name="to-create-a-data-mining-dimension"></a><span data-ttu-id="0b498-106">Para criar uma dimensão de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="0b498-106">To create a data mining dimension</span></span>  
  
1.  <span data-ttu-id="0b498-107">No Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], selecione a guia **Estrutura de Mineração** ou a guia **Modelos de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="0b498-107">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], select either the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="0b498-108">No menu **Modelo de Mineração** , selecione **Criar uma Dimensão de Mineração de Dados**.</span><span class="sxs-lookup"><span data-stu-id="0b498-108">From the **Mining Model** menu, select **Create a Data Mining Dimension**.</span></span>  
  
     <span data-ttu-id="0b498-109">A caixa de diálogo **Criar Dimensão de Mineração de Dados** é exibida.</span><span class="sxs-lookup"><span data-stu-id="0b498-109">The **Create Data Mining Dimension** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="0b498-110">Na lista **Nome do modelo** da caixa de diálogo **Criar Dimensão de Mineração de Dados** , selecione um modelo de mineração OLAP.</span><span class="sxs-lookup"><span data-stu-id="0b498-110">In the **Model name** list of the **Create Data Mining Dimension** dialog box, select an OLAP mining model.</span></span>  
  
4.  <span data-ttu-id="0b498-111">Na caixa **Nome da dimensão** , digite um nome para a nova dimensão de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="0b498-111">In the **Dimension name** box, enter a name for the new data mining dimension.</span></span>  
  
5.  <span data-ttu-id="0b498-112">Se você quiser criar um cubo que inclua a nova dimensão de mineração de dados, selecione **Criar cubo**.</span><span class="sxs-lookup"><span data-stu-id="0b498-112">If you want to create a cube that includes the new data mining dimension, select **Create cube**.</span></span> <span data-ttu-id="0b498-113">Após selecionar **Criar cubo**, você pode digitar um nome novo para o cubo.</span><span class="sxs-lookup"><span data-stu-id="0b498-113">After you select **Create cube**, you can enter a new name for the cube.</span></span>  
  
6.  <span data-ttu-id="0b498-114">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b498-114">Click **OK**.</span></span>  
  
     <span data-ttu-id="0b498-115">A dimensão de mineração de dados é criada e adicionada à pasta **Dimensões** no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="0b498-115">The data mining dimension is created and is added to the **Dimensions** folder in Solution Explorer.</span></span> <span data-ttu-id="0b498-116">Se você selecionou **Criar cubo**, um cubo novo também será criado e adicionado à pasta **Cubos** .</span><span class="sxs-lookup"><span data-stu-id="0b498-116">If you selected **Create cube**, a new cube is also created and is added to the **Cubes** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b498-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0b498-117">See Also</span></span>  
 [<span data-ttu-id="0b498-118">Tarefas e instruções da estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="0b498-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
