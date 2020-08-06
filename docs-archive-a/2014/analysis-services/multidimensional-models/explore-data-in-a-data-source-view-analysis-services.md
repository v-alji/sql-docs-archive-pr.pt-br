---
title: Explorar dados em uma exibição da fonte de dados (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exploring data [Analysis Services]
- data source views [Analysis Services], exploring data
- viewing source data
ms.assetid: 2c922c35-fbcb-45b2-96b1-c7a846d8b419
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adf9edecd807158ba1d0de3287cccd6fa8dd787
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583854"
---
# <a name="explore-data-in-a-data-source-view-analysis-services"></a><span data-ttu-id="d66bb-102">Explorar dados em uma exibição da fonte de dados (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="d66bb-102">Explore Data in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="d66bb-103">Você pode usar a caixa de diálogo **Explorar Dados** do Designer de Exibição da Fonte de Dados do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para procurar dados para uma tabela, exibição ou consulta nomeada de uma DSV (exibição da fonte de dados).</span><span class="sxs-lookup"><span data-stu-id="d66bb-103">You can use the **Explore Data** dialog box in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to browse data for a table, view, or named query in a data source view (DSV).</span></span> <span data-ttu-id="d66bb-104">Ao explorar os dados no Designer de Exibição da Fonte de Dados, você pode exibir o conteúdo de cada coluna de dados da tabela, exibição ou consulta nomeada selecionada.</span><span class="sxs-lookup"><span data-stu-id="d66bb-104">When you explore the data in Data Source View Designer, you can view the contents of each column of data in a selected table, view, or named query.</span></span> <span data-ttu-id="d66bb-105">Exibir o conteúdo real é útil para determinar se todas as colunas são necessárias, se os cálculos nomeados são requeridos para torná-los mais amigável para o usuário e melhorar a usabilidade e se os cálculos nomeados ou as consultas nomeadas existentes retornam os valores previstos.</span><span class="sxs-lookup"><span data-stu-id="d66bb-105">Viewing the actual contents assists you in determining whether all columns are needed, if named calculations are required to increase user friendliness and usability, and whether existing named calculations or named queries return the anticipated values.</span></span>  
  
 <span data-ttu-id="d66bb-106">Para exibir os dados, é necessária uma conexão ativa com a(s) fonte(s) de dados do objeto selecionado na DSV (exibição da fonte de dados).</span><span class="sxs-lookup"><span data-stu-id="d66bb-106">To view data, you must have an active connection to the data source or sources for the selected object in the DSV.</span></span> <span data-ttu-id="d66bb-107">Todos os cálculos nomeados de uma tabela também são enviados na consulta.</span><span class="sxs-lookup"><span data-stu-id="d66bb-107">Any named calculations in a table are also sent in the query.</span></span>  
  
 <span data-ttu-id="d66bb-108">Os dados retornados em um formato de tabela que você pode classificar e copiar.</span><span class="sxs-lookup"><span data-stu-id="d66bb-108">The data returned in a tabular format that you can sort and copy.</span></span> <span data-ttu-id="d66bb-109">Clique nos cabeçalhos das colunas para reclassificar as linhas das respectivas colunas.</span><span class="sxs-lookup"><span data-stu-id="d66bb-109">Click on the column headers to re-sort the rows by that column.</span></span> <span data-ttu-id="d66bb-110">Você também pode realçar dados na grade e pressionar Ctrl-C para copiar a seleção para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="d66bb-110">You can also highlight data in the grid and press Ctrl-C to copy the selection to the clipboard.</span></span>  
  
 <span data-ttu-id="d66bb-111">Você também pode controlar o método de exemplo e a contagem de exemplo.</span><span class="sxs-lookup"><span data-stu-id="d66bb-111">You can also control the sample method and the sample count.</span></span> <span data-ttu-id="d66bb-112">Por padrão, as 5.000 primeiras linhas são retornadas.</span><span class="sxs-lookup"><span data-stu-id="d66bb-112">By default, the top 5000 rows are returned.</span></span>  
  
## <a name="to-browse-data-or-change-sampling-options"></a><span data-ttu-id="d66bb-113">Para procurar dados ou alterar opções de amostragem</span><span class="sxs-lookup"><span data-stu-id="d66bb-113">To browse data or change sampling options</span></span>  
  
1.  <span data-ttu-id="d66bb-114">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto ou conecte-se ao banco de dados que contém a exibição da fonte de dados na qual você deseja procurar dados.</span><span class="sxs-lookup"><span data-stu-id="d66bb-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to browse data.</span></span>  
  
2.  <span data-ttu-id="d66bb-115">No Gerenciador de Soluções, expanda a pasta **Exibições da Fonte de Dados** e clique duas vezes na exibição da fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="d66bb-115">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="d66bb-116">Clique com o botão direito do mouse na tabela, exibição ou consulta nomeada que contém os dados que você deseja exibir e, em seguida, clique em **Explorar Dados**.</span><span class="sxs-lookup"><span data-stu-id="d66bb-116">Right-click the table, view, or named query that contains the data you want to view, and then click **Explore Data**.</span></span>  
  
     <span data-ttu-id="d66bb-117">A fonte de dados subjacente à tabela, exibição ou consulta nomeada na exibição da fonte de dados são consultas e os resultados são exibidos na guia **explorar \<object name> tabela** .</span><span class="sxs-lookup"><span data-stu-id="d66bb-117">The data source underlying the table, view, or named query in the data source view are queries, and the results appear in the **Explore \<object name> Table** tab.</span></span>  
  
4.  <span data-ttu-id="d66bb-118">Na barra de ferramentas **explorar \<object name> tabela** , clique no ícone **Opções de amostragem** .</span><span class="sxs-lookup"><span data-stu-id="d66bb-118">On the **Explore \<object name> Table** toolbar, click the **Sampling options** icon.</span></span>  
  
     <span data-ttu-id="d66bb-119">A caixa de diálogo **Opções de Exploração de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="d66bb-119">The **Data Exploration Options** dialog box opens.</span></span> <span data-ttu-id="d66bb-120">Nela você pode especificar o método de amostragem (menos ou mais registros que o tamanho de amostragem padrão de 5000 linhas) ou a contagem de exemplo.</span><span class="sxs-lookup"><span data-stu-id="d66bb-120">In this dialog box you can specify the sampling method (fewer or more records than the default sampling size of 5000 rows), or sample count.</span></span>  
  
5.  <span data-ttu-id="d66bb-121">Clique em **OK** ou em **Cancelar** , conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="d66bb-121">Click **OK** or **Cancel** as appropriate.</span></span>  
  
6.  <span data-ttu-id="d66bb-122">Para obter uma nova amostra dos dados, clique em **reamostrar dados** na barra de ferramentas da \*\* \<object name> tabela de exploração\*\* .</span><span class="sxs-lookup"><span data-stu-id="d66bb-122">To resample the data, click **Resample Data** on the **Explore \<object name> Table** toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d66bb-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d66bb-123">See Also</span></span>  
 [<span data-ttu-id="d66bb-124">Exibições de fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="d66bb-124">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
