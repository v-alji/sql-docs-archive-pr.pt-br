---
title: Consulta (SQL Server suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [data mining]
- Data Mining Query Advanced Editor
- query builder [data mining]
- DMX
ms.assetid: 16af4a6f-18d4-496a-a304-7a13aa32ee76
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90794aae8a3d664d47ab251ffdd954f22d48f992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684394"
---
# <a name="query-sql-server-data-mining-add-ins"></a><span data-ttu-id="f7a1c-102">Consulta (Suplementos de Mineração de Dados do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f7a1c-102">Query (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="f7a1c-103">![Botão Modelo da Consulta, faixa de opções Mineração de Dados](media/dmc-query.gif "Botão Modelo da Consulta, faixa de opções Mineração de Dados")</span><span class="sxs-lookup"><span data-stu-id="f7a1c-103">![Query Model button, Data Mining ribbon](media/dmc-query.gif "Query Model button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="f7a1c-104">O assistente de **Consulta** o ajuda a interagir com os modelos de mineração de dados existentes para fazer previsões com base nos dados em uma tabela ou intervalo do Excel, ou outra fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-104">The **Query** wizard helps you interact with existing mining models to make predictions based on data in an Excel table, an Excel range, or another data source.</span></span> <span data-ttu-id="f7a1c-105">O processo de aplicar novos dados a um modelo existente para prever tendências é denominado *consulta de previsão*.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-105">The process of applying new data to an existing model to predict trends is called a *prediction query*.</span></span>  
  
 <span data-ttu-id="f7a1c-106">O assistente de **Consulta** também fornece um editor avançado para criar ou modificar modelos de mineração de dados, para gerar consultas personalizadas ou trabalhar com estruturas que não têm suporte nas outras ferramentas, como conjuntos de dados aninhados.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-106">The **Query** wizard also provides an advanced editor for creating or modifying data mining models, for generating custom queries, or for working with structures not supported in the other tools, such as nested datasets.</span></span>  
  
-   <span data-ttu-id="f7a1c-107">Use o editor de texto para digitar ou colar as instruções DMX (Data Mining Extensions) que você criou em outro lugar.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-107">Use the text editor to type or paste in the Data Mining Extensions (DMX) statements you've created elsewhere.</span></span>  
  
-   <span data-ttu-id="f7a1c-108">Use o Construtor de Consultas interativo para compor uma instrução DMX personalizada com a ajuda de modelos e caixas de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-108">Use the interactive Query Builder to compose a custom DMX statement with the help of templates and dialog boxes.</span></span>  
  
-   <span data-ttu-id="f7a1c-109">Criar instruções DMX para gerenciar ou fazer backup de modelos e estruturas de mineração.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-109">Create DMX statements to manage or back up mining models and structures.</span></span>  
  
## <a name="using-the-query-wizard"></a><span data-ttu-id="f7a1c-110">Usando o Assistente de Consulta</span><span class="sxs-lookup"><span data-stu-id="f7a1c-110">Using the Query Wizard</span></span>  
  
1.  <span data-ttu-id="f7a1c-111">Primeiro, você deve especificar uma fonte para os dados a ser usada como entrada.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-111">First, you must specify a source for the data to use as input.</span></span> <span data-ttu-id="f7a1c-112">Use os dados em uma tabela ou intervalo existente do Excel ou especifique uma instrução SQL para recuperar os dados.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-112">You can use data in an existing Excel table or range, or you can specify a SQL statement to retrieve the data.</span></span>  
  
2.  <span data-ttu-id="f7a1c-113">Em seguida, o assistente apresenta uma lista dos modelos de mineração de dados no servidor ao qual você está conectado.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-113">Next, the wizard presents a list of data mining models on the server to which you are connected.</span></span> <span data-ttu-id="f7a1c-114">Se você souber qual modelo deseja e estiver familiarizado com mineração de dados, também poderá clicar em **Avançado** para abrir o **Editor de Consulta Avançada de Mineração de Dados**.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-114">If you know the model you want and are familiar with data mining, you can also click **Advanced** to open the **Data Mining Advanced Query Editor**.</span></span>  
  
3.  <span data-ttu-id="f7a1c-115">Dependendo do tipo de modelo escolhido, você deverá especificar a coluna que contém os dados a serem avaliados e definir mapeamentos entre as colunas dos dados de entrada e as colunas do modelo.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-115">Depending on the type of model that you choose, you must specify the column that contains the data to be evaluated, and define mappings between the input data columns and the model columns.</span></span> <span data-ttu-id="f7a1c-116">De acordo com o algoritmo escolhido, você poderá definir outras propriedades no modelo.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-116">Depending on the algorithm you choose, you can set other properties on the model.</span></span>  
  
4.  <span data-ttu-id="f7a1c-117">Por fim, o assistente também lhe oferecerá a capacidade de escolher uma ou mais previsões e especificar um destino no qual armazenar os resultados.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-117">Finally, the wizard also gives you the ability to choose one or more predictions, and specify a destination in which to store the results.</span></span>  
  
 <span data-ttu-id="f7a1c-118">A qualquer momento, você poderá clicar em **Avançado** para alternar para o **Editor de Consulta Avançada de Mineração de Dados**, que lhe proporcionará mais controle sobre cada parte da instrução DMX.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-118">At any time, you can click **Advanced** to switch to the **Data Mining Advanced Query Editor**, which gives you more control over each part of the DMX statement.</span></span> <span data-ttu-id="f7a1c-119">Para obter mais informações sobre como usar as ferramentas avançadas de edição de consulta, consulte [Editor de consulta de mineração de dados avançado](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="f7a1c-119">For more information about how to use the advanced query editing tools, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="f7a1c-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7a1c-120">Requirements</span></span>  
 <span data-ttu-id="f7a1c-121">Para usar o assistente de **Consulta** , você deve estar conectado a uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7a1c-121">To use the **Query** wizard, you must be connected to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="f7a1c-122">Além disso, o servidor deve conter pelo menos um modelo de mineração de dados de um tipo apropriado.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-122">Moreover, the server must contain at least one data mining model of an appropriate type.</span></span> <span data-ttu-id="f7a1c-123">Se não houver nenhum modelo de mineração disponível, você poderá criar um desses modelos usando os assistentes fornecidos no Cliente de Mineração de Dados para Excel.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-123">If no mining models are available, you can create one by using the wizards provided in the Data Mining Client for Excel.</span></span> <span data-ttu-id="f7a1c-124">Para obter informações sobre como criar um novo modo de mineração usando um assistente, consulte [criando um modelo de mineração de dados](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="f7a1c-124">For information about how to create a new mining mode by using a wizard, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a1c-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f7a1c-125">See Also</span></span>  
 <span data-ttu-id="f7a1c-126">[Implantando e dimensionando modelos de mineração &#40;suplementos de mineração de dados para Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="f7a1c-126">[Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="f7a1c-127">O cliente de mineração de dados para Excel &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="f7a1c-127">Data Mining Client for Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](data-mining-client-for-excel-sql-server-data-mining-add-ins.md)  
  
  
