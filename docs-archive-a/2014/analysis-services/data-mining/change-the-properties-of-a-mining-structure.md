---
title: Alterar as propriedades de uma estrutura de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], properties
ms.assetid: 03b16897-2e36-42b8-9f7d-db1b9b898401
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c1e63ad5fada770394e2fc283e0e592319281b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678357"
---
# <a name="change-the-properties-of-a-mining-structure"></a><span data-ttu-id="1c6cb-102">Alterar as propriedades de uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="1c6cb-102">Change the Properties of a Mining Structure</span></span>
  <span data-ttu-id="1c6cb-103">Há dois tipos de propriedades em uma estrutura de mineração e ambos podem ser modificados:</span><span class="sxs-lookup"><span data-stu-id="1c6cb-103">There are two kinds of properties on a mining structure, both of which can be modified:</span></span>  
  
-   <span data-ttu-id="1c6cb-104">Propriedades da estrutura de mineração que afetam a estrutura inteira</span><span class="sxs-lookup"><span data-stu-id="1c6cb-104">Properties of the mining structure that affect the entire structure</span></span>  
  
-   <span data-ttu-id="1c6cb-105">Propriedades em colunas individuais na estrutura</span><span class="sxs-lookup"><span data-stu-id="1c6cb-105">Properties on individual columns in the structure</span></span>  
  
 <span data-ttu-id="1c6cb-106">Note que algumas propriedades dependem de outras configurações de propriedade.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-106">Note that some properties are dependent on other property settings.</span></span> <span data-ttu-id="1c6cb-107">Por exemplo, não é possível definir propriedades que controlam o comportamento de compartimentalização (como <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> ou <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A>) até definir o tipo de dados da coluna como `Discretized`.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-107">For example, you cannot set properties that control binning behavior (such as <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> or <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A>) until you have set the data type of the column to `Discretized`.</span></span>  
  
 <span data-ttu-id="1c6cb-108">Para obter mais informações sobre as propriedades da estrutura de mineração, consulte [Colunas da estrutura de mineração](mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="1c6cb-108">For more information about mining structure properties, see [Mining Structure Columns](mining-structure-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-structure"></a><span data-ttu-id="1c6cb-109">Para alterar as propriedades de uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="1c6cb-109">To change the properties of a mining structure</span></span>  
  
1.  <span data-ttu-id="1c6cb-110">Na guia **Estrutura de Mineração** do Designer de Mineração de Dados, clique com o botão direito do mouse na estrutura de mineração ou em uma coluna na estrutura de mineração e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-110">On the **Mining Structure** tab in Data Mining Designer, right-click either the mining structure or a column in the mining structure, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="1c6cb-111">A janela **Propriedades** será aberta no lado direito da tela se ela ainda não estiver visível.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-111">The **Properties** window opens on the right side of the screen, if it was not already visible.</span></span>  
  
2.  <span data-ttu-id="1c6cb-112">Na janela **Propriedades** , selecione o valor que corresponde à propriedade que você quer alterar e insira o novo valor.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-112">In the **Properties** window, select the value that corresponds to the property that you want to change, and then enter the new value.</span></span>  
  
     <span data-ttu-id="1c6cb-113">O novo valor entrará em vigor quando você selecionar um elemento diferente no designer.</span><span class="sxs-lookup"><span data-stu-id="1c6cb-113">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c6cb-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1c6cb-114">See Also</span></span>  
 [<span data-ttu-id="1c6cb-115">Tarefas e instruções da estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="1c6cb-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
