---
title: Substituir uma tabela ou uma consulta nomeada em uma exibição da fonte de dados (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- replacing tables
- data source views [Analysis Services], tables
- named queries [Analysis Services], replacing tables
- tables [Analysis Services], data source views
- partitions [Analysis Services], named queries
ms.assetid: 60c2a018-1299-4915-b60e-e73316524def
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b5055de60ba757c9dcfa118e4e2c4748c6534e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575407"
---
# <a name="replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services"></a><span data-ttu-id="fc588-102">Substituir uma tabela ou uma consulta nomeada em uma exibição da fonte de dados (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="fc588-102">Replace a Table or a Named Query in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="fc588-103">No Designer de Exibição da Fonte de Dados, é possível substituir uma tabela, exibição ou consulta nomeada de uma DSV (exibição da fonte de dados) por outra tabela ou exibição da mesma fonte de dados ou de outra ou ainda por uma consulta nomeada definida na DSV.</span><span class="sxs-lookup"><span data-stu-id="fc588-103">In Data Source View Designer, you can replace a table, view, or named query in a data source view (DSV) with a different table or view from the same or a different data source, or with a named query defined in the DSV.</span></span> <span data-ttu-id="fc588-104">Quando você substitui uma tabela, as referências existentes para essa tabela em todos os outros objetos do banco de dados ou projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] são preservadas porque a identificação do objeto para a tabela na DSV não é alterada.</span><span class="sxs-lookup"><span data-stu-id="fc588-104">When you replace a table, all other objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project that have references to the table continue to reference the table because the object ID for the table in the DSV does not change.</span></span> <span data-ttu-id="fc588-105">Todas as relações que ainda são relevantes (com base no nome e na correspondência coluna-tipo) são mantidas.</span><span class="sxs-lookup"><span data-stu-id="fc588-105">Any relationships that are still relevant (based on name and column-type matching) are retained.</span></span> <span data-ttu-id="fc588-106">Diferentemente, se você excluir e, em seguida, adicionar uma tabela, as referências e relações serão perdidas e terão de ser recriadas.</span><span class="sxs-lookup"><span data-stu-id="fc588-106">In contrast, if you delete and then add a table, references and relationships are lost and must be recreated.</span></span>  
  
 <span data-ttu-id="fc588-107">Para substituir uma tabela por outra, é necessária uma conexão ativa com a fonte de dados no Designer de Exibição da Fonte de Dados em modo de projeto.</span><span class="sxs-lookup"><span data-stu-id="fc588-107">To replace a table with another table, you must have an active connection to the source data in Data Source View Designer in project mode.</span></span>  
  
 <span data-ttu-id="fc588-108">O que ocorre com mais frequência é a substituição de uma tabela da exibição da fonte de dados por outra tabela da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fc588-108">You most frequently replace a table in the data source view with another table in the data source.</span></span> <span data-ttu-id="fc588-109">No entanto, você também pode substituir uma consulta nomeada por uma tabela.</span><span class="sxs-lookup"><span data-stu-id="fc588-109">However, you can also replace a named query with a table.</span></span> <span data-ttu-id="fc588-110">Por exemplo, anteriormente, você substituiu uma tabela por uma consulta nomeada e agora deseja voltar para a tabela.</span><span class="sxs-lookup"><span data-stu-id="fc588-110">For example, you previously replaced a table with a named query, and now want to revert to a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fc588-111">Se você renomear uma tabela de uma fonte de dados, siga os passos de substituição de tabela e especifique a tabela renomeada como a fonte da tabela correspondente na DSV antes de atualizá-la.</span><span class="sxs-lookup"><span data-stu-id="fc588-111">If you rename a table in a data source, follow the steps for replacing a table and specify the renamed table as the source of the corresponding table in the DSV before you refresh a DSV.</span></span> <span data-ttu-id="fc588-112">A conclusão do processo de substituir e renomear preservará a tabela, suas referências e relações na DSV.</span><span class="sxs-lookup"><span data-stu-id="fc588-112">Completing the replacement and renaming process preserves the table, the table's references, and the table's relationships in the DSV.</span></span> <span data-ttu-id="fc588-113">Caso contrário, quando você atualizar a DSV, uma tabela renomeada na fonte de dados será interpretada como se tivesse sido excluída.</span><span class="sxs-lookup"><span data-stu-id="fc588-113">Otherwise, when you refresh the DSV, a renamed table in data source is interpreted as being deleted.</span></span> <span data-ttu-id="fc588-114">Para obter mais informações, consulte [Atualizar o esquema em uma exibição da fonte de dados &#40;Analysis Services&#41;](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="fc588-114">For more information, see [Refresh the Schema in a Data Source View &#40;Analysis Services&#41;](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span></span>  
  
##  <a name="replace-a-table-with-a-named-query"></a><a name="bkmk_nq"></a> <span data-ttu-id="fc588-115">Substituir uma tabela com uma consulta nomeada</span><span class="sxs-lookup"><span data-stu-id="fc588-115">Replace a table with a named query</span></span>  
  
1.  <span data-ttu-id="fc588-116">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto ou conecte-se ao banco de dados que contém a exibição da fonte de dados na qual existe uma tabela ou consulta nomeada que você deseja substituir.</span><span class="sxs-lookup"><span data-stu-id="fc588-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="fc588-117">No Gerenciador de Soluções, expanda a pasta **Exibições da Fonte de Dados** e clique duas vezes na exibição da fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="fc588-117">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="fc588-118">Abra a caixa de diálogo **Criar Consulta Nomeada** .</span><span class="sxs-lookup"><span data-stu-id="fc588-118">Open the **Create Named Query** dialog box.</span></span> <span data-ttu-id="fc588-119">No painel **Tabelas** ou **Diagrama** , clique com o botão direito do mouse na tabela que você deseja substituir, aponte para **Substituir Tabela** e, em seguida, clique em **Com Nova Consulta Nomeada**.</span><span class="sxs-lookup"><span data-stu-id="fc588-119">In either **Tables** or **Diagram** pane, right-click the table that you wish to replace, point to **Replace Table** and then click **With New Named Query**.</span></span>  
  
4.  <span data-ttu-id="fc588-120">Na caixa de diálogo **Criar Consulta Nomeada** , defina a consulta nomeada e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc588-120">In the **Create Named Query** dialog box, define the named query and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="fc588-121">Salve a exibição de fonte de dados modificada.</span><span class="sxs-lookup"><span data-stu-id="fc588-121">Save the modified data source view.</span></span>  
  
## <a name="replace-a-table-or-named-query-with-a-table"></a><span data-ttu-id="fc588-122">Substituir uma tabela ou consulta nomeada por uma tabela</span><span class="sxs-lookup"><span data-stu-id="fc588-122">Replace a table or named query with a table</span></span>  
  
1.  <span data-ttu-id="fc588-123">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto ou conecte-se ao banco de dados que contém a exibição da fonte de dados na qual existe uma tabela ou consulta nomeada que você deseja substituir.</span><span class="sxs-lookup"><span data-stu-id="fc588-123">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="fc588-124">No Gerenciador de Soluções, expanda a pasta **Exibições da Fonte de Dados** e clique duas vezes na exibição da fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="fc588-124">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="fc588-125">Abra a caixa de diálogo **Substituir Tabela por Outra** .</span><span class="sxs-lookup"><span data-stu-id="fc588-125">Open the **Replace Table with Other Table** dialog box.</span></span> <span data-ttu-id="fc588-126">No painel **Tabelas** ou **Diagrama** , clique com o botão direito do mouse na tabela ou na consulta nomeada que você deseja substituir, aponte para **Substituir Tabela** e, em seguida, clique em **Com Outra Tabela**.</span><span class="sxs-lookup"><span data-stu-id="fc588-126">In either **Tables** or **Diagram** pane, right-click the table or named query that you wish to replace, point to **Replace Table** and then click **With Other Table**.</span></span>  
  
4.  <span data-ttu-id="fc588-127">Na caixa de diálogo **Substituir Tabela por Outra** :</span><span class="sxs-lookup"><span data-stu-id="fc588-127">In the **Replace Table with Other Table** dialog box:</span></span>  
  
    1.  <span data-ttu-id="fc588-128">Na caixa de listagem suspensa **Fonte de dados** , selecione a fonte de dados desejada</span><span class="sxs-lookup"><span data-stu-id="fc588-128">In the **DataSource** drop-down list box, select the desired data source</span></span>  
  
    2.  <span data-ttu-id="fc588-129">Selecione a tabela pela qual você deseja substituir a tabela ou consulta nomeada.</span><span class="sxs-lookup"><span data-stu-id="fc588-129">Select the table with which you wish to replace the table or named query</span></span>  
  
5.  <span data-ttu-id="fc588-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc588-130">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="fc588-131">Salve a exibição de fonte de dados modificada.</span><span class="sxs-lookup"><span data-stu-id="fc588-131">Save the modified data source view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc588-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fc588-132">See Also</span></span>  
 [<span data-ttu-id="fc588-133">Exibições de fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="fc588-133">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
