---
title: Excluir uma coluna (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 703db83b-e554-450e-813e-23ad08c1cdad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 06af0b7fd9879661db95bb2073cced545bb4eef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574924"
---
# <a name="delete-a-column-ssas-tabular"></a><span data-ttu-id="f529f-102">Excluir uma coluna (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="f529f-102">Delete a Column (SSAS Tabular)</span></span>
  <span data-ttu-id="f529f-103">Este tópico descreve como excluir uma coluna de uma tabela de modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="f529f-103">This topic describes how to delete a column from a tabular model table.</span></span>  
  
## <a name="delete-a-model-table-column"></a><span data-ttu-id="f529f-104">Excluir uma coluna de tabela modelo</span><span class="sxs-lookup"><span data-stu-id="f529f-104">Delete a Model Table Column</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f529f-105">A exclusão de uma coluna de uma tabela modelo não exclui a coluna de uma definição de consulta de partição.</span><span class="sxs-lookup"><span data-stu-id="f529f-105">Deleting a column from a model table does not delete the column from a partition query definition.</span></span> <span data-ttu-id="f529f-106">Se a coluna que você está excluindo fizer parte de uma partição, exclua a coluna manualmente da definição de consulta de partição.</span><span class="sxs-lookup"><span data-stu-id="f529f-106">If the column you are deleting is part of a partition, you must manually delete the column from the partition query definition.</span></span> <span data-ttu-id="f529f-107">A falha ao excluir a coluna da definição de consulta de partição causará a consulta da coluna e o retorno dos dados, mas não a população da tabela modelo, durante operações de processamento.</span><span class="sxs-lookup"><span data-stu-id="f529f-107">Failure to delete the column from the partition query definition will cause the column to be queried and data returned, but not populated to the model table, during processing operations.</span></span> <span data-ttu-id="f529f-108">Para obter mais informações, consulte [Partições &#40;SSAS de Tabela&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="f529f-108">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-delete-a-model-table-column"></a><span data-ttu-id="f529f-109">Para excluir uma coluna de tabela modelo</span><span class="sxs-lookup"><span data-stu-id="f529f-109">To delete a model table column</span></span>  
  
-   <span data-ttu-id="f529f-110">No designer de modelo, na tabela que contém a coluna a ser excluída, clique com o botão direito do mouse na coluna e, depois, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="f529f-110">In the model designer, in the table that contains the column you want to delete, right-click on the column, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-model-table-column-by-using-the-table-properties-dialog-box"></a><span data-ttu-id="f529f-111">Para excluir uma coluna de tabela modelo usando a caixa de diálogo Propriedades da Tabela</span><span class="sxs-lookup"><span data-stu-id="f529f-111">To delete a model table column by using the Table Properties dialog box</span></span>  
  
1.  <span data-ttu-id="f529f-112">No designer de modelo, clique na tabela que contém a coluna a ser excluída, clique no menu **Tabela** e em  **Propriedades da Tabela**.</span><span class="sxs-lookup"><span data-stu-id="f529f-112">In the model designer, click on the table which contains the column you want to delete, then click the **Table** menu, and then click  **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="f529f-113">Em **Nomes das coluna de**, selecione **Modelo** (*para usar nomes de coluna de tabela modelo, se for diferente da origem*).</span><span class="sxs-lookup"><span data-stu-id="f529f-113">In **Column names from**, select **Model** (*to use model table column names, if different from source*).</span></span>  
  
3.  <span data-ttu-id="f529f-114">Na caixa de diálogo **Editar Propriedades da Tabela** , na janela de visualização de tabela, desmarque a coluna a ser excluída e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f529f-114">In the **Edit Table Properties** dialog box, in the table preview window, uncheck the column you want to delete, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f529f-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f529f-115">See Also</span></span>  
 <span data-ttu-id="f529f-116">[Adicionar colunas a uma tabela &#40;SSAS tabular&#41;](add-columns-to-a-table-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="f529f-116">[Add Columns to a Table &#40;SSAS Tabular&#41;](add-columns-to-a-table-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="f529f-117">Partições &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="f529f-117">Partitions &#40;SSAS Tabular&#41;</span></span>](partitions-ssas-tabular.md)  
  
  
