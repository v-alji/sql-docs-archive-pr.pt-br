---
title: Criar uma relação entre duas tabelas (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.managereldb.f1
- sql12.asvs.bidtoolset.createrelatdb.f1
ms.assetid: 052d77b7-7922-408a-a200-786016ee4d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33481b8d50be9ca632bcade932d51df86c1910a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572221"
---
# <a name="create-a-relationship-between-two-tables-ssas-tabular"></a><span data-ttu-id="8cdc0-102">Criar uma relação entre duas tabelas (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="8cdc0-102">Create a Relationship Between Two Tables (SSAS Tabular)</span></span>
  <span data-ttu-id="8cdc0-103">Se as tabelas da fonte de dados não tiverem relações existentes ou se você adicionar novas tabelas, será possível usar as ferramentas no designer de modelo para criar novas relações.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-103">If the tables in your data source do not have existing relationships, or if you add new tables, you can use the tools in the model designer to create new relationships.</span></span> <span data-ttu-id="8cdc0-104">Para obter informações sobre como as relações são usadas em modelos tabulares, consulte [Relações &#40;SSAS de Tabela&#41;](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="8cdc0-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="create-a-relationship-between-two-tables"></a><span data-ttu-id="8cdc0-105">Criar uma relação entre duas tabelas</span><span class="sxs-lookup"><span data-stu-id="8cdc0-105">Create a relationship between two tables</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-click-and-drag"></a><span data-ttu-id="8cdc0-106">Para criar uma relação entre duas tabelas na Exibição de Diagrama (clicar e arrastar)</span><span class="sxs-lookup"><span data-stu-id="8cdc0-106">To create a relationship between two tables in Diagram View (Click and drag)</span></span>  
  
1.  <span data-ttu-id="8cdc0-107">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], clique no menu **Modelo** , clique em **Exibição de Modelo**e clique em **Exibição de Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="8cdc0-108">Clique (e mantenha pressionado) em uma coluna dentro de uma tabela e arraste o cursor para uma coluna de pesquisa relacionada em uma tabela de pesquisa relacionada e, em seguida, solte.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-108">Click (and hold) on a column within a table, then drag the cursor to a related lookup column in a related lookup table, and then release.</span></span> <span data-ttu-id="8cdc0-109">A relação será criada na ordem correta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-109">The relationship will be created in the correct order automatically.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-right-click"></a><span data-ttu-id="8cdc0-110">Para criar uma relação entre duas tabelas na Exibição de Diagrama (clicar com o botão direito)</span><span class="sxs-lookup"><span data-stu-id="8cdc0-110">To create a relationship between two tables in Diagram View (Right-click)</span></span>  
  
1.  <span data-ttu-id="8cdc0-111">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], clique no menu **Modelo** , clique em **Exibição de Modelo**e clique em **Exibição de Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="8cdc0-112">Clique com o botão direito do mouse em um cabeçalho ou coluna de tabela e clique em **Criar Relação**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-112">Right-click a table heading or column, and then click **Create Relationship**.</span></span>  
  
3.  <span data-ttu-id="8cdc0-113">Na caixa de diálogo **Criar Relação** , clique na seta para baixo de **Tabela**e selecione uma tabela da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-113">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="8cdc0-114">Em uma relação "muitos-para-um", essa tabela deve estar no lado "muitos".</span><span class="sxs-lookup"><span data-stu-id="8cdc0-114">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
4.  <span data-ttu-id="8cdc0-115">Para **Coluna**, selecione a coluna que contém os dados relacionados a **Coluna de Pesquisa Relacionada**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-115">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span> <span data-ttu-id="8cdc0-116">A coluna é selecionada automaticamente se você clicou com o botão direito em uma coluna para criar a relação.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-116">The column is automatically selected if you right-clicked on a column to create the relationship.</span></span>  
  
5.  <span data-ttu-id="8cdc0-117">Para **Coluna de Pesquisa Relacionada**, selecione uma tabela que tenha pelo menos uma coluna de dados relacionada à tabela que você acabou de selecionar para **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-117">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="8cdc0-118">Em uma relação "um-para-muitos", essa tabela deve estar no lado "um", o que significa que os valores da coluna selecionada não contêm duplicatas.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-118">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="8cdc0-119">Se você tentar criar a relação na ordem errada (um para muitos, em vez de muitos para um), um ícone aparecerá ao lado do campo **Coluna de Pesquisa Relacionada** .</span><span class="sxs-lookup"><span data-stu-id="8cdc0-119">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="8cdc0-120">Inverta a ordem para criar uma relação válida.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-120">Reverse the order to create a valid relationship.</span></span>  
  
6.  <span data-ttu-id="8cdc0-121">Para **Coluna de Pesquisa Relacionada**, selecione uma coluna que tenha valores exclusivos correspondentes aos valores da coluna selecionada para **Coluna**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-121">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
7.  <span data-ttu-id="8cdc0-122">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-122">Click **Create**.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-data-view"></a><span data-ttu-id="8cdc0-123">Para criar uma relação entre duas tabelas na Exibição de Dados</span><span class="sxs-lookup"><span data-stu-id="8cdc0-123">To create a relationship between two tables in Data View</span></span>  
  
1.  <span data-ttu-id="8cdc0-124">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], clique no menu **Tabela** e clique em **Criar Relações**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-124">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Create Relationships**.</span></span>  
  
2.  <span data-ttu-id="8cdc0-125">Na caixa de diálogo **Criar Relação** , clique na seta para baixo de **Tabela**e selecione uma tabela da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-125">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="8cdc0-126">Em uma relação "muitos-para-um", essa tabela deve estar no lado "muitos".</span><span class="sxs-lookup"><span data-stu-id="8cdc0-126">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
3.  <span data-ttu-id="8cdc0-127">Para **Coluna**, selecione a coluna que contém os dados relacionados a **Coluna de Pesquisa Relacionada**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-127">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span>  
  
4.  <span data-ttu-id="8cdc0-128">Para **Coluna de Pesquisa Relacionada**, selecione uma tabela que tenha pelo menos uma coluna de dados relacionada à tabela que você acabou de selecionar para **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-128">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="8cdc0-129">Em uma relação "um-para-muitos", essa tabela deve estar no lado "um", o que significa que os valores da coluna selecionada não contêm duplicatas.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-129">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="8cdc0-130">Se você tentar criar a relação na ordem errada (um para muitos, em vez de muitos para um), um ícone aparecerá ao lado do campo **Coluna de Pesquisa Relacionada** .</span><span class="sxs-lookup"><span data-stu-id="8cdc0-130">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="8cdc0-131">Inverta a ordem para criar uma relação válida.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-131">Reverse the order to create a valid relationship.</span></span>  
  
5.  <span data-ttu-id="8cdc0-132">Para **Coluna de Pesquisa Relacionada**, selecione uma coluna que tenha valores exclusivos correspondentes aos valores da coluna selecionada para **Coluna**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-132">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
6.  <span data-ttu-id="8cdc0-133">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="8cdc0-133">Click **Create**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cdc0-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8cdc0-134">See Also</span></span>  
 <span data-ttu-id="8cdc0-135">[Excluir relações &#40;SSAS de tabela&#41;](delete-relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="8cdc0-135">[Delete Relationships &#40;SSAS Tabular&#41;](delete-relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="8cdc0-136">Relações &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="8cdc0-136">Relationships &#40;SSAS Tabular&#41;</span></span>](relationships-ssas-tabular.md)  
  
  
