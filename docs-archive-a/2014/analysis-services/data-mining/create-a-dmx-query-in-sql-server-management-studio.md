---
title: Criar uma consulta DMX no SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- templates [Analysis Services], queries
- SQL Server Management Studio [Analysis Services], DMX queries
- predictions [Analysis Services], DMX prediction queries
- predictions [DMX]
- prediction queries [DMX]
- queries [DMX], prediction queries
- mining models [Analysis Services], DMX
ms.assetid: 568ce40a-1f53-47eb-8c79-14347cdfde83
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20fc7a618f4977058203d8f35d235b543609dd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575461"
---
# <a name="create-a-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="dae3f-102">Criar uma consulta DMX no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dae3f-102">Create a DMX Query in SQL Server Management Studio</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dae3f-103">fornece um conjunto de recursos para ajudar a criar consultas de previsão, consultas de conteúdo e consultas de definição de dados em modelos de mineração e estruturas de mineração.</span><span class="sxs-lookup"><span data-stu-id="dae3f-103">provides a set of features to help you create prediction queries, content queries, and data definition queries against mining models and mining structures.</span></span>  
  
-   <span data-ttu-id="dae3f-104">O Construtor de consulta de previsão gráfico está disponível no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], para simplificar o processo de escrever consultas de previsão e conjuntos de dados de mapeamento em um modelo.</span><span class="sxs-lookup"><span data-stu-id="dae3f-104">The graphical Prediction Query Builder is available in both [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], to simplify the process of writing prediction queries and mapping data sets to a model.</span></span>  
  
-   <span data-ttu-id="dae3f-105">Os modelos de consulta fornecidos no Gerenciador de Modelos iniciam a criação de muitos tipos de consultas DMX, incluindo muitos tipos de consultas de previsão.</span><span class="sxs-lookup"><span data-stu-id="dae3f-105">The query templates provided in the Template Explorer jump-start the creation of many kinds of DMX queries, including many types of prediction queries.</span></span> <span data-ttu-id="dae3f-106">Os modelos são fornecidos para consultas de conteúdo, consultas que usaram conjuntos de dados aninhados, consulta que retornaram casos da estrutura de mineração e até mesmo consultas de definição de dados.</span><span class="sxs-lookup"><span data-stu-id="dae3f-106">Templates are provided for content queries, queries used nested data sets, queries that return cases from the mining structure, and even data definition queries.</span></span>  
  
-   <span data-ttu-id="dae3f-107">O Gerenciador de Metadados nos painéis de consulta MDX e DMX fornece uma lista de modelos e estruturas disponíveis que você pode arrastar e soltar no construtor de consultas, assim como uma lista de funções DMX.</span><span class="sxs-lookup"><span data-stu-id="dae3f-107">The Metadata Explorer in the MDX and DMX query panes provides a list of available models and structures that you can drag and drop into the query builder, as well as a list of DMX functions.</span></span> <span data-ttu-id="dae3f-108">Este recurso facilita a obtenção correta de nomes de objetos, sem digitar.</span><span class="sxs-lookup"><span data-stu-id="dae3f-108">This feature makes it easy to get object names right, without typing.</span></span>  
  
 <span data-ttu-id="dae3f-109">Este tópico descreve como criar uma consulta DMX usando o Gerenciador de Metadados e o editor de consultas DMX.</span><span class="sxs-lookup"><span data-stu-id="dae3f-109">This topic describes how to build a DMX query by using the Metadata Explorer and the DMX query editor.</span></span>  
  
##  <a name="dmx-query-templates"></a><a name="BKMK_Templates"></a><span data-ttu-id="dae3f-110">Modelos de consulta DMX</span><span class="sxs-lookup"><span data-stu-id="dae3f-110">DMX Query Templates</span></span>  
 <span data-ttu-id="dae3f-111">Modelos para criar consultas DMX básicas estão disponíveis no Explorador de Modelos.</span><span class="sxs-lookup"><span data-stu-id="dae3f-111">Templates for creating basic DMX queries are available in Template Explorer.</span></span> <span data-ttu-id="dae3f-112">A pasta **DMX** contém modelos de mineração de dados que estão divididos nestas categorias:</span><span class="sxs-lookup"><span data-stu-id="dae3f-112">The **DMX** folder contains data mining templates, which are divided into these categories:</span></span>  
  
-   <span data-ttu-id="dae3f-113">**Conteúdo do modelo**</span><span class="sxs-lookup"><span data-stu-id="dae3f-113">**Model Content**</span></span>  
  
-   <span data-ttu-id="dae3f-114">**Gerenciamento de Modelos**</span><span class="sxs-lookup"><span data-stu-id="dae3f-114">**Model Management**</span></span>  
  
-   <span data-ttu-id="dae3f-115">**Consultas de previsão**</span><span class="sxs-lookup"><span data-stu-id="dae3f-115">**Prediction Queries**</span></span>  
  
-   <span data-ttu-id="dae3f-116">**Conteúdo da estrutura**</span><span class="sxs-lookup"><span data-stu-id="dae3f-116">**Structure Content**</span></span>  
  
 <span data-ttu-id="dae3f-117">Você também pode criar modelos personalizados, para consultas ou comandos que você executa com frequência.</span><span class="sxs-lookup"><span data-stu-id="dae3f-117">You can also create custom templates, for queries or commands that you run frequently.</span></span>  
  
## <a name="xmla-query-templates"></a><span data-ttu-id="dae3f-118">Modelos de consulta XMLA</span><span class="sxs-lookup"><span data-stu-id="dae3f-118">XMLA Query Templates</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="dae3f-119">também fornece modelos para consultas XMLA.</span><span class="sxs-lookup"><span data-stu-id="dae3f-119">also provides templates for XMLA queries.</span></span>  
  
 <span data-ttu-id="dae3f-120">Há alguma sobreposição entre os tipos de consultas que você pode executar usando XMLA e DMX.</span><span class="sxs-lookup"><span data-stu-id="dae3f-120">There is some overlap between the types of queries that you can perform by using XMLA and DMX.</span></span> <span data-ttu-id="dae3f-121">Por exemplo, você pode criar algumas consultas de conteúdo de modelo usando DMX ou os conjuntos de linhas de esquema de mineração de dados, mas os conjuntos de linhas de esquema às vezes contêm informações que não são expostas em consultas de conteúdo DMX.</span><span class="sxs-lookup"><span data-stu-id="dae3f-121">For example, you can create some model content queries by using either DMX or the data mining schema rowsets, but the schema rowsets sometimes contain information that is not exposed in DMX content queries.</span></span>  
  
 <span data-ttu-id="dae3f-122">Também há algumas diferenças principais no modo como as operações são tratadas no DMX e no XMLA.</span><span class="sxs-lookup"><span data-stu-id="dae3f-122">There are also some key differences in the way that operations are handled in DMX and in XMLA.</span></span> <span data-ttu-id="dae3f-123">Por exemplo, você pode usar XMLA para executar operações administrativas como backup de um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] inteiro, mas, se você deseja fazer backup de um único modelo de mineração, o DMX fornece um comando simples, [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx) que é mais adequado a esse propósito.</span><span class="sxs-lookup"><span data-stu-id="dae3f-123">For example, you can use XMLA to perform administrative operations such as backup of an entire [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, but if you want to back up a single mining model, DMX provides a simple command, [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx), that is better suited to that purpose.</span></span>  
  
##  <a name="build-and-run-a-dmx-query"></a><a name="BKMK_Building_Queries"></a><span data-ttu-id="dae3f-124">Compilar e executar uma consulta DMX</span><span class="sxs-lookup"><span data-stu-id="dae3f-124">Build and Run a DMX Query</span></span>  
  
#### <a name="open-a-new-dmx-query-window"></a><span data-ttu-id="dae3f-125">Abrir nova janela de consulta DMX</span><span class="sxs-lookup"><span data-stu-id="dae3f-125">Open a new DMX Query window</span></span>  
  
1.  <span data-ttu-id="dae3f-126">Clique em **Nova Consulta** no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e selecione **Nova Consulta DMX do Analysis Server**.</span><span class="sxs-lookup"><span data-stu-id="dae3f-126">Click **New Query** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then select **New Analysis Server DMX Query**.</span></span>  
  
2.  <span data-ttu-id="dae3f-127">Quando a caixa de diálogo **Conectar ao Servidor** é exibida, selecione a instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém os modelos de mineração com os quais deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="dae3f-127">When the **Connect to Server** dialog box appears, select the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining models you want to work with.</span></span>  
  
#### <a name="open-template-explorer"></a><span data-ttu-id="dae3f-128">Abrir o Explorador de Modelos</span><span class="sxs-lookup"><span data-stu-id="dae3f-128">Open Template Explorer</span></span>  
  
1.  <span data-ttu-id="dae3f-129">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Exibir** , selecione o **Explorador de Modelos**.</span><span class="sxs-lookup"><span data-stu-id="dae3f-129">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, select **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="dae3f-130">Clique em **Analysis Server** para ver uma exibição de árvore do modelo aplicável ao [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dae3f-130">Click **Analysis Server** to see a tree view of the templates that apply to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
#### <a name="apply-a-template-to-build-a-query"></a><span data-ttu-id="dae3f-131">Aplicar um modelo para criar uma consulta</span><span class="sxs-lookup"><span data-stu-id="dae3f-131">Apply a template to build a query</span></span>  
  
-   <span data-ttu-id="dae3f-132">Clique com o botão direito do mouse no tipo de consulta apropriado e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="dae3f-132">Right-click the appropriate query type and select **Open**.</span></span>  
  
-   <span data-ttu-id="dae3f-133">Ou arraste o modelo para o editor de consulta.</span><span class="sxs-lookup"><span data-stu-id="dae3f-133">Or, drag the template into the query editor.</span></span>  
  
-   <span data-ttu-id="dae3f-134">Você também pode preencher os parâmetros para a consulta usando a opção **Especificar Valores para Parâmetros**no menu **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="dae3f-134">You can also fill in the parameters for the query by using the option, **Specify Values for Parameters**, from the **Query** menu.</span></span>  
  
 <span data-ttu-id="dae3f-135">Para obter exemplos de como criar tipos específicos de consultas de modelos, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="dae3f-135">For examples of how to create specific types of queries from templates, see the following topics:</span></span>  
  
 [<span data-ttu-id="dae3f-136">Criar uma consulta de previsão singleton a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="dae3f-136">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
  
 [<span data-ttu-id="dae3f-137">Criar uma consulta de conteúdo em um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="dae3f-137">Create a Content Query on a Mining Model</span></span>](create-a-content-query-on-a-mining-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="dae3f-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dae3f-138">See Also</span></span>  
 <span data-ttu-id="dae3f-139">[Interfaces de consulta de mineração de dados](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dae3f-139">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="dae3f-140">Referência de DMX &#40;extensões DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="dae3f-140">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
