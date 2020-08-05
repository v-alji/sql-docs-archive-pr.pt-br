---
title: Excluir uma coluna de um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- excluding mining model columns
- mining models [Analysis Services], columns
- columns [data mining], excluding
ms.assetid: 404fe5fe-3ba2-4b9b-8780-0d02343d467f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30affebc143184c6287858f60b5d4f5d089c322a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572277"
---
# <a name="exclude-a-column-from-a-mining-model"></a><span data-ttu-id="354e5-102">Excluir uma coluna de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="354e5-102">Exclude a Column from a Mining Model</span></span>
  <span data-ttu-id="354e5-103">Ao criar um novo modelo de mineração, talvez você não queira usar todas as colunas existentes na estrutura de mineração em que o modelo é baseado.</span><span class="sxs-lookup"><span data-stu-id="354e5-103">When you create a new mining model, you may not want to use all the columns that exist in the mining structure on which the model is based.</span></span> <span data-ttu-id="354e5-104">Por exemplo, você pode ter adicionado uma coluna de nome de cliente para detalhamento, mas não deseja usá-la para modelagem.</span><span class="sxs-lookup"><span data-stu-id="354e5-104">For example, you might have added a customer name column for drillthrough, but don't want to use it for modeling.</span></span> <span data-ttu-id="354e5-105">Ou você pode decidir criar várias cópias de uma coluna com discretizações diferentes e usar apenas uma das cópias em cada modelo, ignorando as demais.</span><span class="sxs-lookup"><span data-stu-id="354e5-105">Or, you might decide to create multiple copies of a column with different discretizations, and use only one of the copies in each model, and ignore the rest.</span></span> <span data-ttu-id="354e5-106">Você também pode adicionar seletivamente colunas de entrada em vários modelos diferentes para ver como a variável adicionada afeta a coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="354e5-106">You could also selectively add input columns in several different models to see how the added variable affects the output column.</span></span>  
  
 <span data-ttu-id="354e5-107">Você não precisa criar uma nova estrutura de mineração para cada combinação de colunas; basta sinalizar uma coluna como não sendo usado em um modelo específico.</span><span class="sxs-lookup"><span data-stu-id="354e5-107">You do not need to create a new mining structure for each combination of columns; instead, you can simply flag a column as not being used in a particular model.</span></span>  
  
### <a name="to-exclude-a-column-from-a-mining-model"></a><span data-ttu-id="354e5-108">Para excluir uma coluna de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="354e5-108">To exclude a column from a mining model</span></span>  
  
1.  <span data-ttu-id="354e5-109">Na guia **Modelos de Mineração** no Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], selecione a célula que corresponde à coluna que deseja excluir no modelo de mineração apropriado.</span><span class="sxs-lookup"><span data-stu-id="354e5-109">In the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the cell that corresponds to the column you want to exclude, under the appropriate mining model.</span></span>  
  
2.  <span data-ttu-id="354e5-110">Selecione **Ignorar** na caixa de listagem suspensa.</span><span class="sxs-lookup"><span data-stu-id="354e5-110">Select **Ignore** from the drop-down list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="354e5-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="354e5-111">See Also</span></span>  
 [<span data-ttu-id="354e5-112">Tarefas e instruções do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="354e5-112">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
