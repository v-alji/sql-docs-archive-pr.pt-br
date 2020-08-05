---
title: Alterar os mapeamentos de tabela, coluna ou filtro de linha (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2124c526-5772-4f84-a019-9dd3e906e8dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: d8a597fb51804ea12caace63f3308b07bffc5899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572709"
---
# <a name="change-table-column-or-row-filter-mappings-ssas-tabular"></a><span data-ttu-id="edca3-102">Alterar os mapeamentos de tabela, coluna ou filtro de linha (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="edca3-102">Change table, column, or row filter mappings (SSAS Tabular)</span></span>
  <span data-ttu-id="edca3-103">Esse tópico descreve como alterar tabela, coluna ou mapeamentos de filtro de linha usando a visualização de tabela ou editor de consulta SQL na caixa de diálogo **Editar Propriedades de Tabela** no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edca3-103">This topic describes how to change table, column, or row filter mappings by using the **Edit Table Properties** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
 <span data-ttu-id="edca3-104">As opções desta caixa de diálogo **Editar Propriedades da Tabela** são diferentes, dependendo de você ter importado os dados originalmente selecionando tabelas em uma lista ou usando uma consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="edca3-104">Options in the **Edit Table Properties** dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span> <span data-ttu-id="edca3-105">Se você importou os dados originalmente selecionando de uma lista, a caixa de diálogo **Editar Propriedades da Tabela** exibirá o modo de visualização de Tabela.</span><span class="sxs-lookup"><span data-stu-id="edca3-105">If you originally imported the data by selecting from a list, the **Edit Table Properties** dialog box displays the Table Preview mode.</span></span> <span data-ttu-id="edca3-106">Este modo exibe somente um subconjunto limitado às primeiras cinquenta linhas da tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="edca3-106">This mode displays only a subset limited to the first fifty rows of the source table.</span></span> <span data-ttu-id="edca3-107">Se você importou os dados originalmente usando uma instrução SQL, a caixa de diálogo **Editar Propriedades da Tabela** somente exibirá uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="edca3-107">If you originally imported the data by using a SQL statement, the **Edit Table Properties** dialog box only displays a SQL statement.</span></span> <span data-ttu-id="edca3-108">Usando uma instrução de consulta SQL, é possível recuperar um subconjunto de linhas, criando um filtro ou editando manualmente a instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="edca3-108">Using a SQL query statement, you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="edca3-109">Se você alterar a origem para uma tabela que tenha colunas diferentes das da tabela atual, uma mensagem será exibida, avisando que as colunas são diferentes.</span><span class="sxs-lookup"><span data-stu-id="edca3-109">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="edca3-110">Em seguida, você deve selecionar as colunas que deseja colocar na tabela atual e clicar em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="edca3-110">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="edca3-111">Você pode substituir toda a tabela marcando a caixa de seleção no lado esquerdo da tabela.</span><span class="sxs-lookup"><span data-stu-id="edca3-111">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="edca3-112">Se sua tabela tiver mais de uma partição, você não poderá usar a caixa de diálogo Propriedades da Tabela de Edição para alterar os mapeamentos de filtro de linha.</span><span class="sxs-lookup"><span data-stu-id="edca3-112">If your table has more than one partition, you cannot use the Edit Table Properties dialog box to change row filter mappings.</span></span> <span data-ttu-id="edca3-113">Para alterar os mapeamentos de filtro de linha para tabelas com várias partições, use o Gerenciador de Partições.</span><span class="sxs-lookup"><span data-stu-id="edca3-113">To change row filter mappings for tables with multiple partitions, use Partition Manager.</span></span> <span data-ttu-id="edca3-114">Para obter mais informações, consulte [Partições &#40;SSAS de Tabela&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="edca3-114">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-change-table-column-or-row-filter-mappings"></a><span data-ttu-id="edca3-115">Para alterar os mapeamentos de tabela, coluna ou filtro de linha</span><span class="sxs-lookup"><span data-stu-id="edca3-115">To change table, column, or row filter mappings</span></span>  
  
1.  <span data-ttu-id="edca3-116">No designer de modelo, clique na tabela, clique no menu **Tabela** e, clique em **Propriedades da Tabela**.</span><span class="sxs-lookup"><span data-stu-id="edca3-116">In the model designer, click the table, then click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="edca3-117">Na caixa de diálogo **Editar Propriedades da Tabela** , localize a coluna que contém os critérios pelos quais você deseja filtrar e clique na seta para baixo à direita do cabeçalho da coluna.</span><span class="sxs-lookup"><span data-stu-id="edca3-117">In the **Edit Table Properties** dialog box, locate the column that contains the criteria you want to filter on, and then click the down arrow at the right of the column heading.</span></span>  
  
3.  <span data-ttu-id="edca3-118">No menu **AutoFiltro** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="edca3-118">In the **AutoFilter** menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="edca3-119">Na lista de valores de coluna, selecione ou limpe um ou mais valores pelos quais filtrar e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="edca3-119">In the list of column values, select or clear one or more values to filter by, and then click OK.</span></span>  
  
         <span data-ttu-id="edca3-120">Se o número de valores for extremamente grande, os itens individuais poderão não ser mostrados na lista.</span><span class="sxs-lookup"><span data-stu-id="edca3-120">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="edca3-121">Em vez disso, você verá a mensagem "Itens demais para mostrar".</span><span class="sxs-lookup"><span data-stu-id="edca3-121">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="edca3-122">Clique em **Filtros de Número** ou em **Filtros de Texto** (dependendo do tipo de coluna) e clique nos comandos de operador de comparação (como Igual a) ou clique em Filtro Personalizado.</span><span class="sxs-lookup"><span data-stu-id="edca3-122">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as Equals), or click Custom Filter.</span></span> <span data-ttu-id="edca3-123">Na caixa de diálogo **Filtro Personalizado** , crie o filtro e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="edca3-123">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
         <span data-ttu-id="edca3-124">Se você cometer um erro e precisa recomeçar, clique em **Limpar Filtros de Linha**.</span><span class="sxs-lookup"><span data-stu-id="edca3-124">If you make a mistake and need to start over, click **Clear Row Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edca3-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="edca3-125">See Also</span></span>  
 [<span data-ttu-id="edca3-126">Caixa de diálogo Editar Propriedades da Tabela &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="edca3-126">Edit Table Properties Dialog Box &#40;SSAS&#41;</span></span>](../edit-table-properties-dialog-box-ssas.md)  
  
  
