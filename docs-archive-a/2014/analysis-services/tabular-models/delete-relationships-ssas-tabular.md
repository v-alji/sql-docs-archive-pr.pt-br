---
title: Excluir relações (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d40e3f05-54e8-4c4b-807a-0b06f446079b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c63324918eb6919ce0abd65b5ee0765f9d7243b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679038"
---
# <a name="delete-relationships-ssas-tabular"></a><span data-ttu-id="84ef8-102">Excluir relações (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="84ef8-102">Delete Relationships (SSAS Tabular)</span></span>
  <span data-ttu-id="84ef8-103">É possível excluir relações existentes usando o designer de modelos na Exibição de Diagrama ou usando a caixa de diálogos Gerenciar Relações.</span><span class="sxs-lookup"><span data-stu-id="84ef8-103">You can delete existing relationships by using the model designer in Diagram View or by using the Manage Relationships dialog box.</span></span> <span data-ttu-id="84ef8-104">Para obter informações sobre como as relações são usadas em modelos tabulares, consulte [Relações &#40;SSAS de Tabela&#41;](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="84ef8-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="considerations-for-deleting-relationships"></a><span data-ttu-id="84ef8-105">Considerações para excluir relações</span><span class="sxs-lookup"><span data-stu-id="84ef8-105">Considerations for Deleting Relationships</span></span>  
 <span data-ttu-id="84ef8-106">Lembre-se destes problemas quando decidir excluir uma relação:</span><span class="sxs-lookup"><span data-stu-id="84ef8-106">Keep the following issues in mind when deciding whether to delete a relationship:</span></span>  
  
-   <span data-ttu-id="84ef8-107">Não há como desfazer a exclusão de uma relação.</span><span class="sxs-lookup"><span data-stu-id="84ef8-107">There is no way to undo the deletion of a relationship.</span></span> <span data-ttu-id="84ef8-108">Você pode recriar a relação, mas essa ação requer um recálculo completo das fórmulas no modelo.</span><span class="sxs-lookup"><span data-stu-id="84ef8-108">You can re-create the relationship, but this action requires a complete recalculation of formulas in the model.</span></span> <span data-ttu-id="84ef8-109">Portanto, sempre verifique primeiro antes de excluir uma relação que é usada em fórmulas.</span><span class="sxs-lookup"><span data-stu-id="84ef8-109">Therefore, always check first before deleting a relationship that is used in formulas.</span></span>  
  
-   <span data-ttu-id="84ef8-110">A exclusão de uma relação entre duas tabelas pode causar erros em fórmulas que referenciam essas tabelas.</span><span class="sxs-lookup"><span data-stu-id="84ef8-110">Deleting a relationship between two tables can cause errors in formulas that reference these tables.</span></span>  
  
-   <span data-ttu-id="84ef8-111">A função DAX (Data Analysis Expression) RELATED usa as relações entre tabelas para procurar valores relacionados em outra tabela.</span><span class="sxs-lookup"><span data-stu-id="84ef8-111">The Data Analysis Expression (DAX) RELATED function uses the relationships between tables to look up related values in another table.</span></span> <span data-ttu-id="84ef8-112">Ela retornará resultados diferentes depois que a relação for excluída.</span><span class="sxs-lookup"><span data-stu-id="84ef8-112">It will return different results after the relationship is deleted.</span></span> <span data-ttu-id="84ef8-113">Para obter mais informações, consulte a função RELATED (DAX).</span><span class="sxs-lookup"><span data-stu-id="84ef8-113">For more information, see the RELATED Function (DAX).</span></span>  
  
-   <span data-ttu-id="84ef8-114">Além de alterar os resultados de Tabelas Dinâmicas e de fórmulas, a criação e a exclusão de relações causará o recálculo da pasta de trabalho, o que pode demorar um pouco.</span><span class="sxs-lookup"><span data-stu-id="84ef8-114">In addition to changing PivotTable and formula results, both the creation and deletion of relationships will cause the workbook to be recalculated, which can take some time.</span></span>  
  
## <a name="delete-relationships"></a><span data-ttu-id="84ef8-115">Excluir relações</span><span class="sxs-lookup"><span data-stu-id="84ef8-115">Delete Relationships</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-diagram-view"></a><span data-ttu-id="84ef8-116">Para excluir uma relação usando a Exibição de Diagrama</span><span class="sxs-lookup"><span data-stu-id="84ef8-116">To delete a relationship by using Diagram View</span></span>  
  
1.  <span data-ttu-id="84ef8-117">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique no menu **Modelo** , aponte para **Exibição de Modelo**e clique em **Exibição de Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="84ef8-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="84ef8-118">Clique com o botão direito do mouse na linha da relação entre as duas tabelas e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="84ef8-118">Right-click a relationship line between two tables, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-the-manage-relationships-dialog-box"></a><span data-ttu-id="84ef8-119">Para excluir uma relação usando a caixa de diálogo Gerenciar Relações</span><span class="sxs-lookup"><span data-stu-id="84ef8-119">To delete a relationship by using the Manage Relationships dialog box</span></span>  
  
1.  <span data-ttu-id="84ef8-120">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], clique no menu **Tabela** e clique em **Gerenciar Relações**.</span><span class="sxs-lookup"><span data-stu-id="84ef8-120">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Manage Relationships**.</span></span>  
  
2.  <span data-ttu-id="84ef8-121">Na caixa de diálogo **Gerenciar Relações** , selecione uma ou mais relações na lista.</span><span class="sxs-lookup"><span data-stu-id="84ef8-121">In the **Manage Relationships** dialog box, select one or more relationships from the list.</span></span>  
  
     <span data-ttu-id="84ef8-122">Para selecionar várias relações, mantenha a tecla CTRL pressionada enquanto você clica em cada relação.</span><span class="sxs-lookup"><span data-stu-id="84ef8-122">To select multiple relationships, hold down CTRL while you click each relationship.</span></span>  
  
3.  <span data-ttu-id="84ef8-123">Clique em **Excluir Relação**.</span><span class="sxs-lookup"><span data-stu-id="84ef8-123">Click **Delete Relationship**.</span></span>  
  
4.  <span data-ttu-id="84ef8-124">Na caixa de diálogo **Gerenciar Relações** , clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="84ef8-124">In the **Manage Relationships** dialog box, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84ef8-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84ef8-125">See Also</span></span>  
 <span data-ttu-id="84ef8-126">[Relações &#40;SSAS de tabela&#41;](relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="84ef8-126">[Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="84ef8-127">Criar uma relação entre duas tabelas &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="84ef8-127">Create a Relationship Between Two Tables &#40;SSAS Tabular&#41;</span></span>](create-a-relationship-between-two-tables-ssas-tabular.md)  
  
  
