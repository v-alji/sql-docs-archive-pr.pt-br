---
title: Implementar uma transformação pesquisa em modo de cache cheio usando o Gerenciador de conexões OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Lookup transformation [Integration Services]
ms.assetid: c4150e1b-bdff-4f7a-af4c-3401c34def83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f77a753dd71bc487d57492371906fc48bc114357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582090"
---
# <a name="implement-a-lookup-transformation-in-full-cache-mode-using-the-ole-db-connection-manager"></a><span data-ttu-id="1aece-102">Implementar uma transformação Pesquisa em modo de cache cheio por meio da transformação Gerenciador de Conexões OLE DB</span><span class="sxs-lookup"><span data-stu-id="1aece-102">Implement a Lookup Transformation in Full Cache Mode Using the OLE DB Connection Manager</span></span>
  <span data-ttu-id="1aece-103">Você pode configurar a transformação Pesquisa para usar o modo cache cheio e um gerenciador de conexões OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1aece-103">You can configure the Lookup transformation to use full cache mode and an OLE DB connection manager.</span></span> <span data-ttu-id="1aece-104">No modo cache cheio, o conjunto de dados de referência é carregado no cache antes que a transformação Pesquisa seja executada.</span><span class="sxs-lookup"><span data-stu-id="1aece-104">In the full cache mode, the reference dataset is loaded into cache before the Lookup transformation runs.</span></span>  
  
 <span data-ttu-id="1aece-105">A transformação Pesquisa executa pesquisas ao unir dados em colunas de entradas através de uma fonte de dados conectada com colunas em um conjunto de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="1aece-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in a reference dataset.</span></span> <span data-ttu-id="1aece-106">Para obter mais informações, consulte [Lookup Transformation](../data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="1aece-106">For more information, see [Lookup Transformation](../data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="1aece-107">Ao configurar a transformação Pesquisa para usar o gerenciador de conexões OLE DB, selecione uma tabela, exibição ou consulta SQL para gerar o conjunto de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="1aece-107">When you configure the Lookup transformation to use an OLE DB connection manager, you select a table, view, or SQL query to generate the reference dataset.</span></span>  
  
### <a name="to-implement-a-lookup-transformation-in-full-cache-mode-by-using-ole-db-connection-manager"></a><span data-ttu-id="1aece-108">Para implementar uma transformação Pesquisa em modo cache cheio usando o gerenciador de conexões OLE DB</span><span class="sxs-lookup"><span data-stu-id="1aece-108">To implement a Lookup transformation in full cache mode by using OLE DB connection manager</span></span>  
  
1.  <span data-ttu-id="1aece-109">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote que você deseja e, então, clique duas vezes no pacote no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="1aece-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want, and then double-click the package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="1aece-110">Na guia **Fluxo de Dado** , na **Caixa de Ferramentas**, arraste a transformação Pesquisa até a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="1aece-110">On the **Data Flow** tab, from the **Toolbox**, drag the Lookup transformation to the design surface.</span></span>  
  
3.  <span data-ttu-id="1aece-111">Conecte a transformação Pesquisa ao fluxo de dados arrastando um conector de uma fonte ou transformação anterior para a transformação Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1aece-111">Connect the Lookup transformation to the data flow by dragging a connector from a source or a previous transformation to the Lookup transformation.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1aece-112">Uma transformação Pesquisa talvez não seja validada se essa transformação se conectar a um arquivo simples que contém um campo de data vazio.</span><span class="sxs-lookup"><span data-stu-id="1aece-112">A Lookup transformation might not validate if that transformation connects to a flat file that contains an empty date field.</span></span> <span data-ttu-id="1aece-113">A transformação será validada se o gerenciador de conexões para o arquivo simples tiver sido configurado para reter valores nulos.</span><span class="sxs-lookup"><span data-stu-id="1aece-113">Whether the transformation validates depends on whether the connection manager for the flat file has been configured to retain null values.</span></span> <span data-ttu-id="1aece-114">Para garantir a validação da transformação Pesquisa, no **Editor de Fonte de Arquivo Simples**, na página **Gerenciador de Conexões**, selecione a opção **Reter valores nulos da origem como valores nulos no fluxo de dados** .</span><span class="sxs-lookup"><span data-stu-id="1aece-114">To ensure that the Lookup transformation validates, in the **Flat File Source Editor**, on the **Connection Manager Page**, select the **Retain null values from the source as null values in the data flow** option.</span></span>  
  
4.  <span data-ttu-id="1aece-115">Clique duas vezes na fonte ou transformação anterior para configurar o componente.</span><span class="sxs-lookup"><span data-stu-id="1aece-115">Double-click the source or previous transformation to configure the component.</span></span>  
  
5.  <span data-ttu-id="1aece-116">Clique duas vezes na transformação Pesquisa e, então, em **Editor de Transformação Pesquisa**, na página **Geral** , selecione **Cache cheio**.</span><span class="sxs-lookup"><span data-stu-id="1aece-116">Double-click the Lookup transformation, and then in the **Lookup Transformation Editor**, on the **General** page, select **Full cache**.</span></span>  
  
6.  <span data-ttu-id="1aece-117">Na área **Tipo de conexão** , selecione **Gerenciador de conexões OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="1aece-117">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
7.  <span data-ttu-id="1aece-118">Na lista **Especificar como lidar com linhas sem entradas correspondentes** , selecione uma opção de tratamento de erro para as linhas sem entradas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="1aece-118">In the **Specify how to handle rows with no matching entries** list, select an error handling option for rows without matching entries.</span></span>  
  
8.  <span data-ttu-id="1aece-119">Na página Conexão, selecione um gerenciador de conexões da lista **Gerenciador de conexões OLE DB** ou clique em **Novo** para criar um novo gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="1aece-119">On the Connection page, select a connection manager from the **OLE DB connection manager** list or click **New** to create a new connection manager.</span></span> <span data-ttu-id="1aece-120">Para obter mais informações, consulte [OLE DB Connection Manager](ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1aece-120">For more information, see [OLE DB Connection Manager](ole-db-connection-manager.md).</span></span>  
  
9. <span data-ttu-id="1aece-121">Execute uma dessas tarefas:</span><span class="sxs-lookup"><span data-stu-id="1aece-121">Do one of the following tasks:</span></span>  
  
    -   <span data-ttu-id="1aece-122">Clique em **Usar uma tabela ou uma exibição**e selecione uma tabela ou exibição ou clique em **Nova** para criar uma tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="1aece-122">Click **Use a table or a view**, and then either select a table or view, or click **New** to create a table or view.</span></span>  
  
         <span data-ttu-id="1aece-123">-ou-</span><span class="sxs-lookup"><span data-stu-id="1aece-123">-or-</span></span>  
  
    -   <span data-ttu-id="1aece-124">Clique em **Use os resultados de uma consulta SQL**e crie uma consulta na janela **Comando SQL** ou clique em **Criar Consulta** para criar uma consulta usando as ferramentas gráficas que o **Construtor de Consultas** fornece.</span><span class="sxs-lookup"><span data-stu-id="1aece-124">Click **Use results of an SQL query**, and then build a query in the **SQL Command** window, or click **Build Query** to build a query by using the graphical tools that the **Query Builder** provides.</span></span>  
  
         <span data-ttu-id="1aece-125">-ou-</span><span class="sxs-lookup"><span data-stu-id="1aece-125">-or-</span></span>  
  
    -   <span data-ttu-id="1aece-126">Se preferir, clique em **Procurar** para importar uma instrução SQL de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="1aece-126">Alternatively, click **Browse** to import an SQL statement from a file.</span></span>  
  
     <span data-ttu-id="1aece-127">Para validar a consulta SQL, clique em **Analisar Consulta**.</span><span class="sxs-lookup"><span data-stu-id="1aece-127">To validate the SQL query, click **Parse Query**.</span></span>  
  
     <span data-ttu-id="1aece-128">Para exibir um exemplo dos dados, clique em **Visualização**.</span><span class="sxs-lookup"><span data-stu-id="1aece-128">To view a sample of the data, click **Preview**.</span></span>  
  
10. <span data-ttu-id="1aece-129">Clique na página **Colunas** e, então, na lista **Colunas de Entrada Disponíveis** , arraste pelo menos uma coluna para a coluna na lista **Coluna de Pesquisa Disponível** .</span><span class="sxs-lookup"><span data-stu-id="1aece-129">Click the **Columns** page, and then from the **Available Input Columns** list, drag at least one column to a column in the **Available Lookup Column** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1aece-130">A transformação Pesquisa mapeia automaticamente colunas que têm o mesmo nome e o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="1aece-130">The Lookup transformation automatically maps columns that have the same name and the same data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1aece-131">Estas colunas devem ter tipos de dados correspondentes a serem mapeados.</span><span class="sxs-lookup"><span data-stu-id="1aece-131">Columns must have matching data types to be mapped.</span></span> <span data-ttu-id="1aece-132">Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1aece-132">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
11. <span data-ttu-id="1aece-133">Inclua colunas de pesquisa na saída realizando as etapas tarefas:</span><span class="sxs-lookup"><span data-stu-id="1aece-133">Include lookup columns in the output by doing the following tasks:</span></span>  
  
    1.  <span data-ttu-id="1aece-134">Na lista **Colunas de Consulta Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="1aece-134">In the **Available Lookup Columns** list.</span></span> <span data-ttu-id="1aece-135">selecione colunas</span><span class="sxs-lookup"><span data-stu-id="1aece-135">select columns.</span></span>  
  
    2.  <span data-ttu-id="1aece-136">Na lista **Operação de Pesquisa** , especifique se os valores das colunas de pesquisa devem substituir os valores na coluna de entrada ou ser gravados em uma nova coluna.</span><span class="sxs-lookup"><span data-stu-id="1aece-136">In **Lookup Operation** list, specify whether the values from the lookup columns replace values in the input column or are written to a new column.</span></span>  
  
12. <span data-ttu-id="1aece-137">Para configurar a saída de erro, clique na página **Saída de Erro** e defina as opções de tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="1aece-137">To configure the error output, click the **Error Output** page and set the error handling options.</span></span> <span data-ttu-id="1aece-138">Para obter mais informações, consulte [Editor de Transformação Pesquisa &#40;página Saída de Erro&#41;](../lookup-transformation-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="1aece-138">For more information, see [Lookup Transformation Editor &#40;Error Output Page&#41;](../lookup-transformation-editor-error-output-page.md).</span></span>  
  
13. <span data-ttu-id="1aece-139">Clique em **OK** para salvar suas alterações na transformação Pesquisa e, então, execute o pacote.</span><span class="sxs-lookup"><span data-stu-id="1aece-139">Click **OK** to save your changes to the Lookup transformation, and then run the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aece-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1aece-140">See Also</span></span>  
 <span data-ttu-id="1aece-141">[Implementar uma Transformação Pesquisa em modo de Cache cheio usando o Gerenciador de Conexões do Cache](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="1aece-141">[Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span></span>  
 <span data-ttu-id="1aece-142">[Implementar uma pesquisa no modo Sem cache ou Cache parcial](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span><span class="sxs-lookup"><span data-stu-id="1aece-142">[Implement a Lookup in No Cache or Partial Cache Mode](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span></span>  
 [<span data-ttu-id="1aece-143">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="1aece-143">Integration Services Transformations</span></span>](../data-flow/transformations/integration-services-transformations.md)  
  
  
