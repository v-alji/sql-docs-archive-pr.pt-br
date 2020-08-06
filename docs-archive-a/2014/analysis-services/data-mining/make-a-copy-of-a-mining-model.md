---
title: Fazer uma cópia de um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], copying
- mining models [Analysis Services], creating
- mining models [Analysis Services], how-to topics
- copying mining models
ms.assetid: 7975bb02-f188-49a0-b7de-5b9b216254ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: a05eb75210ce9f601aeca515cd299f4204908705
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568906"
---
# <a name="make-a-copy-of-a-mining-model"></a><span data-ttu-id="29961-102">Criar uma cópia de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="29961-102">Make a Copy of a Mining Model</span></span>
  <span data-ttu-id="29961-103">A criação de uma cópia de um modelo de mineração é útil quando você deseja criar rapidamente vários modelos de mineração com base nos mesmos dados.</span><span class="sxs-lookup"><span data-stu-id="29961-103">Creating a copy of a mining model is useful when you want to quickly create several mining models that are based on the same data.</span></span> <span data-ttu-id="29961-104">Após copiar o modelo, você pode editar a nova cópia alterando parâmetros ou adicionando um filtro.</span><span class="sxs-lookup"><span data-stu-id="29961-104">After you copy the model, you can then edit the new copy by changing parameters or adding a filter.</span></span>  
  
 <span data-ttu-id="29961-105">Por exemplo, se você tem uma tabela Clientes vinculada a uma tabela de compras, pode criar cópias para gerar modelos de mineração separados para cada demografia de cliente, filtrando atributos como idade ou região.</span><span class="sxs-lookup"><span data-stu-id="29961-105">For example, if you have a Customers table that is linked to a table of purchases, you could create copies to generate separate mining models for each customer demographic, filtering on attributes such as age or region.</span></span>  
  
 <span data-ttu-id="29961-106">Para obter informações sobre como copiar o conteúdo do modelo (como a representação gráfica ou os padrões de modelo) na Área de Transferência para uso em outros programas, consulte [Copiar a exibição de um modelo de mineração](copy-a-view-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="29961-106">For information about how to copy the content of the model (such as the graphical representation or the model patterns) to the Clipboard for use in other programs, see [Copy a View of a Mining Model](copy-a-view-of-a-mining-model.md).</span></span>  
  
### <a name="to-create-a-related-mining-model"></a><span data-ttu-id="29961-107">Para criar um modelo de mineração relacionado</span><span class="sxs-lookup"><span data-stu-id="29961-107">To create a related mining model</span></span>  
  
1.  <span data-ttu-id="29961-108">Em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], no Gerenciador de Soluções, clique na estrutura de mineração que contém o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="29961-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model.</span></span>  
  
2.  <span data-ttu-id="29961-109">Clique na guia **Modelos de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="29961-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="29961-110">Selecione o modelo, e clique com o botão direito do mouse para abrir o menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="29961-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="29961-111">- ou -</span><span class="sxs-lookup"><span data-stu-id="29961-111">-or-</span></span>  
  
     <span data-ttu-id="29961-112">Selecione o modelo.</span><span class="sxs-lookup"><span data-stu-id="29961-112">Select the model.</span></span> <span data-ttu-id="29961-113">No menu **Modelo de Mineração** , selecione **Novo Modelo de Mineração**.</span><span class="sxs-lookup"><span data-stu-id="29961-113">On the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="29961-114">Digite um nome para o novo modelo de mineração e selecione um algoritmo.</span><span class="sxs-lookup"><span data-stu-id="29961-114">Type a name for the new mining model, and select an algorithm.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-the-filter-on-the-copied-mining-model"></a><span data-ttu-id="29961-115">Para editar o filtro no modelo de mineração copiado</span><span class="sxs-lookup"><span data-stu-id="29961-115">To edit the filter on the copied mining model</span></span>  
  
1.  <span data-ttu-id="29961-116">Selecione o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="29961-116">Select the mining model.</span></span>  
  
2.  <span data-ttu-id="29961-117">Na janela **Propriedades** , clique na caixa de texto da propriedade **filtro** e clique no botão compilar **(...)** .</span><span class="sxs-lookup"><span data-stu-id="29961-117">In the **Properties** window, click the text box for the **Filter** property, and the click the build **(...)** button.</span></span>  
  
3.  <span data-ttu-id="29961-118">Altere as condições do filtro.</span><span class="sxs-lookup"><span data-stu-id="29961-118">Change the filter conditions.</span></span>  
  
     <span data-ttu-id="29961-119">Para obter mais informações sobre como utilizar as caixas de diálogo do editor de filtro, consulte [Aplicar um filtro a um modelo de mineração](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="29961-119">For more information about how to use the filter editor dialog boxes, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
4.  <span data-ttu-id="29961-120">Na janela **Propriedades** , na caixa de `AlgorithmParameters` texto, clique em **parâmetros setalgorithm**e altere os parâmetros do algoritmo, se desejado.</span><span class="sxs-lookup"><span data-stu-id="29961-120">In the **Properties** window, in the `AlgorithmParameters` text box, click **Setalgorithm parameters**, and change algorithm parameters, if desired.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="29961-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29961-121">See Also</span></span>  
 <span data-ttu-id="29961-122">[Filtros para modelos de mineração &#40;mineração de dados Analysis Services&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="29961-122">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="29961-123">[Tarefas e instruções do modelo de mineração](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="29961-123">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="29961-124">Excluir um filtro de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="29961-124">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
