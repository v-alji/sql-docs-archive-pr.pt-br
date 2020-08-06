---
title: Criar um alias para uma coluna de modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- mining models [Analysis Services], columns
- column names [Analysis Services]
ms.assetid: c80ebe66-a8f8-4f24-9fe8-8288de9d13bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 908c0a8d8caa810badf4b82dc3dd3f411d09f323
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570332"
---
# <a name="create-an-alias-for-a-model-column"></a><span data-ttu-id="74098-102">Criar um alias para uma coluna de modelo</span><span class="sxs-lookup"><span data-stu-id="74098-102">Create an Alias for a Model Column</span></span>
  <span data-ttu-id="74098-103">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], você pode criar um alias para uma coluna de modelo.</span><span class="sxs-lookup"><span data-stu-id="74098-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can create an alias for a model column.</span></span> <span data-ttu-id="74098-104">Isso é útil quando o nome da estrutura de mineração é muito comprido, dificultando o trabalho, ou quando é necessário renomear a coluna para uma descrição mais detalhada de seu conteúdo ou uso no modelo.</span><span class="sxs-lookup"><span data-stu-id="74098-104">This might be useful when the mining structure name is too long to easily work with, or when you want to rename the column to be more descriptive of its contents or usage in the model.</span></span> <span data-ttu-id="74098-105">Por exemplo, se fizer uma cópia da coluna de estrutura e em seguida diferenciar a coluna para um modelo específico, você poderá renomear a coluna de modo a refletir o conteúdo com maior exatidão.</span><span class="sxs-lookup"><span data-stu-id="74098-105">For example, if you make a copy of a structure column and then discretize the column differently for a particular model, you can rename the column to reflect the content more accurately.</span></span>  
  
 <span data-ttu-id="74098-106">Para criar um alias para uma coluna de modelo, use o painel **Propriedades** e defina a propriedade [Nome](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) da coluna.</span><span class="sxs-lookup"><span data-stu-id="74098-106">To create an alias for a model column, you use the **Properties** pane and set the [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) property of the column.</span></span>  
  
 <span data-ttu-id="74098-107">Na guia **Modelos de Mineração** do Designer de Data Mining, o alias aparece entre parênteses próximo ao rótulo de uso da coluna.</span><span class="sxs-lookup"><span data-stu-id="74098-107">On the **Mining Models** tab of Data Mining Designer, the alias appears enclosed in parentheses next to the column usage label.</span></span>  
  
 <span data-ttu-id="74098-108">Para obter informações sobre como definir as propriedades em um modelo de mineração, consulte [Colunas do modelo de mineração](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="74098-108">For information about how to set the properties of a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-add-an-alias-to-a-mining-model-column"></a><span data-ttu-id="74098-109">Para adicionar um alias a uma coluna de modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="74098-109">To add an alias to a mining model column</span></span>  
  
1.  <span data-ttu-id="74098-110">Na guia **Modelos de Mineração** no Designer de Data Mining, clique com o botão direito do mouse na célula no modelo da coluna de mineração que desejar alterar e, em seguida, selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="74098-110">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the mining model for the mining column that you want to change, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="74098-111">Na janela **Propriedades** , no lado direito da tela, clique na célula ao lado da propriedade Nome e exclua o valor atual.</span><span class="sxs-lookup"><span data-stu-id="74098-111">In the **Properties** window on the right side of the screen, click the cell next to the Name property and delete the current value.</span></span> <span data-ttu-id="74098-112">Digite um novo nome para a coluna.</span><span class="sxs-lookup"><span data-stu-id="74098-112">Type a new name for the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74098-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="74098-113">See Also</span></span>  
 <span data-ttu-id="74098-114">[Tarefas e instruções do modelo de mineração](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="74098-114">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="74098-115">Propriedades do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="74098-115">Mining Model Properties</span></span>](mining-model-properties.md)  
  
  
