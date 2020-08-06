---
title: Excluir uma tabela (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: be4ed45f-fde3-466c-9869-49bd3ddb505e
author: minewiskan
ms.author: owend
ms.openlocfilehash: c72fa90426440c1be84318a15cf0d761ef16aca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581463"
---
# <a name="delete-a-table-ssas-tabular"></a><span data-ttu-id="a6414-102">Excluir uma tabela (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="a6414-102">Delete a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="a6414-103">No designer de modelo, você pode excluir tabelas em seu banco de dados de workspace modelo que você não precisa mais.</span><span class="sxs-lookup"><span data-stu-id="a6414-103">In the model designer, you can delete tables in your model workspace database that you no longer need.</span></span> <span data-ttu-id="a6414-104">A exclusão de uma tabela não afeta os dados de origem originais, somente os dados que você importou e com os quais estava trabalhando.</span><span class="sxs-lookup"><span data-stu-id="a6414-104">Deleting a table does not affect the original source data, only the data that you imported and were working with.</span></span> <span data-ttu-id="a6414-105">Não é possível desfazer a exclusão de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="a6414-105">You cannot undo the deletion of a table.</span></span>  
  
### <a name="to-delete-a-table"></a><span data-ttu-id="a6414-106">Para excluir uma tabela</span><span class="sxs-lookup"><span data-stu-id="a6414-106">To delete a table</span></span>  
  
-   <span data-ttu-id="a6414-107">Clique com o botão direito do mouse na guia, na parte inferior do designer de modelo para a tabela que você deseja excluir, e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="a6414-107">Right-click the tab at the bottom of the model designer for the table that you want to delete, and then click **Delete**.</span></span>  
  
## <a name="considerations-when-deleting-tables"></a><span data-ttu-id="a6414-108">Considerações ao excluir tabelas</span><span class="sxs-lookup"><span data-stu-id="a6414-108">Considerations when Deleting Tables</span></span>  
  
-   <span data-ttu-id="a6414-109">Quando você excluir uma tabela, a guia inteira na qual a tabela se encontra será excluída.</span><span class="sxs-lookup"><span data-stu-id="a6414-109">When you delete a table, the entire tab that the table was on is deleted.</span></span>  
  
-   <span data-ttu-id="a6414-110">Se houver uma medida associada a essa tabela, a definição da medida também será excluída.</span><span class="sxs-lookup"><span data-stu-id="a6414-110">If any measures were associated with that table, the definition of the measure will also be deleted.</span></span>  
  
-   <span data-ttu-id="a6414-111">Se você criou qualquer coluna calculada usando essa tabela, as colunas dessa tabela também serão excluídas; as colunas calculadas de outras tabelas que usam colunas da tabela excluída exibirão um erro.</span><span class="sxs-lookup"><span data-stu-id="a6414-111">If you created any calculated columns using that table, columns in that table are also deleted; any calculated columns in other tables that use columns from the deleted table will display an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6414-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a6414-112">See Also</span></span>  
 [<span data-ttu-id="a6414-113">Tabelas e colunas &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="a6414-113">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tables-and-columns-ssas-tabular.md)  
  
  
