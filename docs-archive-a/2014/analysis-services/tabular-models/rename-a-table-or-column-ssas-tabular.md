---
title: Renomear uma tabela ou coluna (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.renametableorcolumn.f1
ms.assetid: 88061a39-c5aa-403d-a52b-7fdb365fc235
author: minewiskan
ms.author: owend
ms.openlocfilehash: d3a2e9a9f41434e64f9ec5ea2180861b459e8f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684366"
---
# <a name="rename-a-table-or-column-ssas-tabular"></a><span data-ttu-id="6414d-102">Renomear uma tabela ou coluna (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="6414d-102">Rename a Table or Column (SSAS Tabular)</span></span>
  <span data-ttu-id="6414d-103">É possível alterar o nome de uma tabela durante o processo de importação por meio da digitação de um **Nome Amigável** na página **Selecionar Tabelas e Exibições** do **Assistente de Importação de Tabela**.</span><span class="sxs-lookup"><span data-stu-id="6414d-103">You can change the name of a table during the import process by typing a **Friendly Name** in the **Select Tables and Views** page of the **Table Import Wizard**.</span></span> <span data-ttu-id="6414d-104">Você também poderá alterar tabela e nomes de coluna se importar dados especificando uma consulta na página **Especificar uma Consulta SQL** do **Assistente de Importação de Tabela**.</span><span class="sxs-lookup"><span data-stu-id="6414d-104">You can also change table and column names if you import data by specifying a query on the **Specify a SQL Query** page of the **Table Import Wizard**.</span></span>  
  
 <span data-ttu-id="6414d-105">Depois de adicionar os dados ao modelo, o nome (ou título) da tabela aparece na guia da tabela, na parte inferior da janela do designer de modelo.</span><span class="sxs-lookup"><span data-stu-id="6414d-105">After you have added the data to the model, the name (or title) of a table appears on the table tab, at the bottom of the model designer.</span></span> <span data-ttu-id="6414d-106">É possível alterar o nome da tabela para um nome mais apropriado.</span><span class="sxs-lookup"><span data-stu-id="6414d-106">You can change the name of your table to give it a more appropriate name.</span></span> <span data-ttu-id="6414d-107">Você também poderá renomear uma coluna depois que os dados forem adicionados ao modelo.</span><span class="sxs-lookup"><span data-stu-id="6414d-107">You can also rename a column after the data has been added to the model.</span></span> <span data-ttu-id="6414d-108">Essa opção é especialmente importante quando você importa dados de várias fontes e deseja assegurar que as colunas nas diferentes tabelas tenham nomes fáceis de distinguir.</span><span class="sxs-lookup"><span data-stu-id="6414d-108">This option is especially important when you have imported data from multiple sources, and want to ensure that columns in different tables have names that are easy to distinguish.</span></span>  
  
### <a name="to-rename-a-table"></a><span data-ttu-id="6414d-109">Para renomear uma tabela</span><span class="sxs-lookup"><span data-stu-id="6414d-109">To rename a table</span></span>  
  
1.  <span data-ttu-id="6414d-110">No designer de modelo, clique com o botão direito do mouse na guia que contém a tabela que você deseja renomear e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="6414d-110">In the model designer, right-click the tab that contains the table that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="6414d-111">Digite o novo nome.</span><span class="sxs-lookup"><span data-stu-id="6414d-111">Type the new name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6414d-112">Você pode alterar outras propriedades de uma tabela, inclusive as informações de conexão e mapeamento de colunas, usando a caixa de diálogo **Editar Propriedades da Tabela** .</span><span class="sxs-lookup"><span data-stu-id="6414d-112">You can edit other properties of a table, including the connection information and column mappings, by using the **Edit Table Properties** dialog box.</span></span> <span data-ttu-id="6414d-113">No entanto, você não pode alterar o nome nessa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6414d-113">However, you cannot change the name in this dialog box.</span></span>  
  
### <a name="to-rename-a-column"></a><span data-ttu-id="6414d-114">Para renomear uma coluna</span><span class="sxs-lookup"><span data-stu-id="6414d-114">To rename a column</span></span>  
  
1.  <span data-ttu-id="6414d-115">No designer do modelo, clique duas vezes no cabeçalho da coluna que você deseja renomear, ou clique com o botão direito do mouse no cabeçalho e selecione **Renomear Coluna** no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="6414d-115">In the model designer, double-click the header of the column that you want to rename, or right-click the header and select **Rename Column** from the context menu.</span></span>  
  
2.  <span data-ttu-id="6414d-116">Digite o novo nome.</span><span class="sxs-lookup"><span data-stu-id="6414d-116">Type the new name.</span></span>  
  
## <a name="naming-requirements-for-columns-and-tables"></a><span data-ttu-id="6414d-117">Requisitos de nomenclatura para colunas e tabelas</span><span class="sxs-lookup"><span data-stu-id="6414d-117">Naming Requirements for Columns and Tables</span></span>  
 <span data-ttu-id="6414d-118">As seguintes palavras e caracteres não podem ser usadas no nome de uma tabela ou coluna:</span><span class="sxs-lookup"><span data-stu-id="6414d-118">The following words and characters cannot be used in the name of a table or column:</span></span>  
  
-   <span data-ttu-id="6414d-119">Espaços à esquerda ou à direita</span><span class="sxs-lookup"><span data-stu-id="6414d-119">Leading or trailing spaces</span></span>  
  
-   <span data-ttu-id="6414d-120">Caracteres de controle</span><span class="sxs-lookup"><span data-stu-id="6414d-120">Control characters</span></span>  
  
-   <span data-ttu-id="6414d-121">Os seguintes caracteres (que não são válidos nos nomes dos objetos Analysis Services):.,; ':/ \\ \*|? &% $! + = () [] {}<></span><span class="sxs-lookup"><span data-stu-id="6414d-121">The following characters (which are not valid in the names of Analysis Services objects): .,;':/\\*|?&%$!+=()[]{}<></span></span>  
  
-   <span data-ttu-id="6414d-122">As palavras-chave reservadas do Analysis Services, incluindo nomes de função e operadores de Linguagens MDX (MDX) e DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="6414d-122">Analysis Services reserved keywords, including Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) function names and operators.</span></span>  
  
## <a name="effect-of-renaming-on-existing-tables-columns-and-calculations"></a><span data-ttu-id="6414d-123">Efeito de renomear tabelas, colunas e cálculos existentes</span><span class="sxs-lookup"><span data-stu-id="6414d-123">Effect of Renaming on Existing Tables, Columns, and Calculations</span></span>  
 <span data-ttu-id="6414d-124">Sempre que altera o nome de uma tabela, você altera o nome do objeto de tabela subjacente que pode conter várias colunas ou medidas.</span><span class="sxs-lookup"><span data-stu-id="6414d-124">Whenever you change the name of a table, you change the name of the underlying table object, which may contain multiple columns or measures.</span></span> <span data-ttu-id="6414d-125">Portanto, as colunas que estiverem na tabela e as relações que usam a tabela deverão ser atualizadas para usar o novo nome em suas definições.</span><span class="sxs-lookup"><span data-stu-id="6414d-125">Therefore, any columns that are in the table, and any relationships that use the table, must be updated to use the new name in their definitions.</span></span> <span data-ttu-id="6414d-126">Essa atualização ocorre automaticamente em alguns casos.</span><span class="sxs-lookup"><span data-stu-id="6414d-126">This update happens automatically in some cases.</span></span> <span data-ttu-id="6414d-127">Medidas não são atualizadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6414d-127">Measures are not updated automatically.</span></span>  
  
 <span data-ttu-id="6414d-128">Além disso, qualquer cálculo que use a tabela renomeada ou as colunas da tabela renomeada também deverá ser atualizado, e os dados derivados desses cálculos deverão ser atualizados e recalculados.</span><span class="sxs-lookup"><span data-stu-id="6414d-128">Moreover, any calculations that use the renamed table, or that use columns from the renamed table, must also be updated, and the data derived from those calculations must be refreshed and recalculated.</span></span> <span data-ttu-id="6414d-129">Dependendo da quantidade de tabelas e cálculos afetados, a conclusão dessa operação poderá demorar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="6414d-129">Depending on how many tables and calculations are affected, this can take some time to complete.</span></span> <span data-ttu-id="6414d-130">Portanto, o melhor momento para renomear tabelas é durante o processo de importação ou antes de você começar a criar relacionamentos e cálculos complexos.</span><span class="sxs-lookup"><span data-stu-id="6414d-130">Therefore, the best time to rename tables is either during the import process, or before you start to build complex relationships and calculations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6414d-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6414d-131">See Also</span></span>  
 <span data-ttu-id="6414d-132">[Tabelas e colunas &#40;SSAS de tabela&#41;](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="6414d-132">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="6414d-133">[Importar do PowerPivot &#40;SSAS de tabela&#41;](import-from-power-pivot-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="6414d-133">[Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="6414d-134">Importar do Analysis Services &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="6414d-134">Import from Analysis Services &#40;SSAS Tabular&#41;</span></span>](import-from-analysis-services-ssas-tabular.md)  
  
  
