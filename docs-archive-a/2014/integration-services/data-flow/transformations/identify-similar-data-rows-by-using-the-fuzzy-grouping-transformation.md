---
title: Identificar linhas de dados semelhantes por meio da transformação Agrupamento Difuso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Fuzzy Grouping transformation
- match similar data [Integration Services]
- similar data rows [Integration Services]
- fuzzy matches
ms.assetid: ffcb41a6-e23d-49ea-8c32-ac980e3dc495
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4e6d49548c211b38a35d6f5f7efc3d50fec93588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582052"
---
# <a name="identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation"></a><span data-ttu-id="c7e01-102">Identificar linhas de dados semelhantes por meio da transformação Agrupamento Difuso</span><span class="sxs-lookup"><span data-stu-id="c7e01-102">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>
  <span data-ttu-id="c7e01-103">Para adicionar e configurar uma transformação Agrupamento Difuso, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e uma fonte.</span><span class="sxs-lookup"><span data-stu-id="c7e01-103">To add and configure a Fuzzy Grouping transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-implement-fuzzy-grouping-transformation-in-a-data-flow"></a><span data-ttu-id="c7e01-104">Implementar uma transformação Agrupamento Difuso em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="c7e01-104">To implement Fuzzy Grouping transformation in a data flow</span></span>  
  
1.  <span data-ttu-id="c7e01-105">No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="c7e01-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="c7e01-106">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="c7e01-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="c7e01-107">Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste a transformação Agrupamento Difuso para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="c7e01-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Fuzzy Grouping transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="c7e01-108">Conecte a transformação Agrupamento Difuso ao fluxo de dados arrastando o conector da fonte de dados ou de uma transformação anterior para a transformação Agrupamento Difuso.</span><span class="sxs-lookup"><span data-stu-id="c7e01-108">Connect the Fuzzy Grouping transformation to the data flow by dragging the connector from the data source or a previous transformation to the Fuzzy Grouping transformation.</span></span>  
  
5.  <span data-ttu-id="c7e01-109">Clique duas vezes no transformação Agrupamento Difuso.</span><span class="sxs-lookup"><span data-stu-id="c7e01-109">Double-click the Fuzzy Grouping transformation.</span></span>  
  
6.  <span data-ttu-id="c7e01-110">Na caixa de diálogo **Editor de Transformação Agrupamento Difuso** , na guia **Gerenciador de Conexões** , selecione um gerenciador de conexões OLE DB que se conecte a um banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7e01-110">In the **Fuzzy Grouping Transformation Editor** dialog box, on the **Connection Manager** tab, select an OLE DB connection manager that connects to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c7e01-111">A transformação requer uma conexão a um banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para criar tabelas temporárias e índices.</span><span class="sxs-lookup"><span data-stu-id="c7e01-111">The transformation requires a connection to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database to create temporary tables and indexes.</span></span>  
  
7.  <span data-ttu-id="c7e01-112">Clique na guia **Colunas** e, na lista **Colunas de Entrada Disponíveis** , marque a caixa de seleção das colunas de entrada a serem usadas para identificar linhas similares no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="c7e01-112">Click the **Columns** tab and, in the **Available Input Columns** list, select the check box of the input columns to use to identify similar rows in the dataset.</span></span>  
  
8.  <span data-ttu-id="c7e01-113">Marque a caixa de seleção na coluna **Passagem** para identificar as colunas de entrada para passar para a saída de transformação.</span><span class="sxs-lookup"><span data-stu-id="c7e01-113">Select the check box in the **Pass Through** column to identify the input columns to pass through to the transformation output.</span></span> <span data-ttu-id="c7e01-114">Colunas de passagem não são incluídas no processo de identificação de linhas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="c7e01-114">Pass-through columns are not included in the process of identification of duplicate rows.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c7e01-115">As colunas de entrada que são usadas para agrupamento são selecionadas automaticamente como colunas de passagem e não podem ser desmarcadas enquanto estiverem sendo utilizadas para agrupamento.</span><span class="sxs-lookup"><span data-stu-id="c7e01-115">Input columns that are used for grouping are automatically selected as pass-through columns, and they cannot be unselected while used for grouping.</span></span>  
  
9. <span data-ttu-id="c7e01-116">Se preferir, atualize os nomes de colunas de saída na coluna **Alias de Saída** .</span><span class="sxs-lookup"><span data-stu-id="c7e01-116">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="c7e01-117">Se preferir, atualize os nomes de colunas limpas na coluna **OutputAlias do Grupo** .</span><span class="sxs-lookup"><span data-stu-id="c7e01-117">Optionally, update the names of cleaned columns in the **Group OutputAlias** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c7e01-118">Os nomes padrão de colunas são os nomes das colunas de entrada com um sufixo "_clean".</span><span class="sxs-lookup"><span data-stu-id="c7e01-118">The default names of columns are the names of the input columns with a "_clean" suffix.</span></span>  
  
11. <span data-ttu-id="c7e01-119">Como alternativa, atualize o tipo de correspondência a ser usada na coluna **Tipo de Correspondência** .</span><span class="sxs-lookup"><span data-stu-id="c7e01-119">Optionally, update the type of match to use in the **Match Type** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c7e01-120">Pelo menos uma coluna deve usar correspondência difusa.</span><span class="sxs-lookup"><span data-stu-id="c7e01-120">At least one column must use fuzzy matching.</span></span>  
  
12. <span data-ttu-id="c7e01-121">Especifique o nível mínimo de semelhança das colunas na coluna **Similaridade Mínima** .</span><span class="sxs-lookup"><span data-stu-id="c7e01-121">Specify the minimum similarity level columns in the **Minimum Similarity** column.</span></span> <span data-ttu-id="c7e01-122">O valor deve estar entre 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="c7e01-122">The value must be between 0 and 1.</span></span> <span data-ttu-id="c7e01-123">Quanto mais próximo de 1 for o valor, mais similares devem ser os valores das colunas de entrada para a formação de um grupo.</span><span class="sxs-lookup"><span data-stu-id="c7e01-123">The closer the value is to 1, the more similar the values in the input columns must be to form a group.</span></span> <span data-ttu-id="c7e01-124">Uma similaridade mínima de 1 indica uma correspondência exata.</span><span class="sxs-lookup"><span data-stu-id="c7e01-124">A minimum similarity of 1 indicates an exact match.</span></span>  
  
13. <span data-ttu-id="c7e01-125">Se preferir, atualize os nomes de colunas de similaridade na coluna **Alias de Saída de Similaridade** .</span><span class="sxs-lookup"><span data-stu-id="c7e01-125">Optionally, update the names of similarity columns in the **Similarity Output Alias** column.</span></span>  
  
14. <span data-ttu-id="c7e01-126">Para especificar a manipulação de números em valores de dados, atualize os valores na coluna **Numerais** .</span><span class="sxs-lookup"><span data-stu-id="c7e01-126">To specify the handling of numbers in data values, update the values in the **Numerals** column.</span></span>  
  
15. <span data-ttu-id="c7e01-127">Para especificar de que forma a transformação compara os dados de cadeia de caracteres, modifique a seleção padrão de opções de comparação na coluna **Sinalizadores de Comparação** .</span><span class="sxs-lookup"><span data-stu-id="c7e01-127">To specify how the transformation compares the string data in a column, modify the default selection of comparison options in the **Comparison Flags** column.</span></span>  
  
16. <span data-ttu-id="c7e01-128">Clique na guia **Avançado** para modificar os nomes das colunas que a transformação acrescenta à saída para o identificador exclusivo de linha (_key_in), identificador de linhas duplicadas (_key_out) e o valor de similaridade (_score).</span><span class="sxs-lookup"><span data-stu-id="c7e01-128">Click the **Advanced** tab to modify the names of the columns that the transformation adds to the output for the unique row identifier (_key_in), the duplicate row identifier (_key_out), and the similarity value (_score).</span></span>  
  
17. <span data-ttu-id="c7e01-129">Como alternativa, ajuste o limite de semelhança movendo a barra deslizante.</span><span class="sxs-lookup"><span data-stu-id="c7e01-129">Optionally, adjust the similarity threshold by moving the slider bar.</span></span>  
  
18. <span data-ttu-id="c7e01-130">Se preferir, desmarque as caixas de seleção do delimitadores de token para ignorar delimitadores nos dados.</span><span class="sxs-lookup"><span data-stu-id="c7e01-130">Optionally, clear the token delimiter check boxes to ignore delimiters in the data.</span></span>  
  
19. <span data-ttu-id="c7e01-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7e01-131">Click **OK**.</span></span>  
  
20. <span data-ttu-id="c7e01-132">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="c7e01-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e01-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c7e01-133">See Also</span></span>  
 <span data-ttu-id="c7e01-134">[Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="c7e01-134">[Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) </span></span>  
 <span data-ttu-id="c7e01-135">[Transformações do Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="c7e01-135">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="c7e01-136">[Caminhos do Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="c7e01-136">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="c7e01-137">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="c7e01-137">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
