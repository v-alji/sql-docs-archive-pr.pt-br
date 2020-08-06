---
title: Modelagem avançada (suplementos de mineração de dados para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures, creating
ms.assetid: 042270a3-6ec7-4b52-b2ba-2adb6c4740d5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 771eb6111765b558995ee3b0eb98196c63951567
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571241"
---
# <a name="advanced-modeling-data-mining-add-ins-for-excel"></a><span data-ttu-id="e4e06-102">Modelagem avançada (Suplementos de Mineração de Dados para Excel)</span><span class="sxs-lookup"><span data-stu-id="e4e06-102">Advanced Modeling (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="e4e06-103">Você pode usar as opções de modelagem de dados **avançadas** para criar estruturas e modelos de Data Mining personalizados com parâmetros diferentes daqueles criados pelos assistentes.</span><span class="sxs-lookup"><span data-stu-id="e4e06-103">You can use the **Advanced** data modeling options to create custom data mining structures and models with parameters different from those created by the wizards.</span></span> <span data-ttu-id="e4e06-104">Os dois assistentes descritos nesta seção o ajudam a criar uma estrutura de mineração de dados completamente nova e um novo modelo de mineração para aplicar a uma estrutura de mineração de dados existente.</span><span class="sxs-lookup"><span data-stu-id="e4e06-104">The two wizards described in this section help you create a completely new data mining structure, and a new mining model to apply to an existing data mining structure.</span></span>  
  
## <a name="create-mining-structure"></a><span data-ttu-id="e4e06-105">Criar a Estrutura de Mineração</span><span class="sxs-lookup"><span data-stu-id="e4e06-105">Create Mining Structure</span></span>  
 <span data-ttu-id="e4e06-106">![Botão Criar Estrutura de Mineração, faixa de opções Mineração de Dados](media/dmc-createstruct.gif "Botão Criar Estrutura de Mineração, faixa de opções Mineração de Dados")</span><span class="sxs-lookup"><span data-stu-id="e4e06-106">![Create Mining Structure button, Data Mining ribbon](media/dmc-createstruct.gif "Create Mining Structure button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="e4e06-107">O **Assistente para criar estrutura de mineração** ajuda a criar uma nova estrutura de data mining.</span><span class="sxs-lookup"><span data-stu-id="e4e06-107">The **Create Mining Structure Wizard** helps you build a new data mining structure.</span></span> <span data-ttu-id="e4e06-108">Uma estrutura é uma coleção dos dados extraídos de uma fonte de dados especificada.</span><span class="sxs-lookup"><span data-stu-id="e4e06-108">A structure is a collection of data extracted from a specified data source.</span></span>  <span data-ttu-id="e4e06-109">Uma estrutura de mineração pode ser atualizada com novos dados na origem, mas quando você cria a estrutura de mineração, define tipos de dados e nomes que definem como os dados são usados para análise.</span><span class="sxs-lookup"><span data-stu-id="e4e06-109">A mining structure can be updated with new data at the source, but when you create the mining structure, you define data types and names that define how the data is used for analysis.</span></span>  
  
 <span data-ttu-id="e4e06-110">Você pode usar as seguintes fontes de dados para criar sua estrutura: uma tabela do Excel, um intervalo do Excel ou qualquer dado em uma fonte de dados externa que já foi definida como uma exibição da fonte de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4e06-110">You can use the following data sources to build your structure: an Excel table, an Excel range, or any data in an external data source that has already been defined as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source view.</span></span>  
  
 <span data-ttu-id="e4e06-111">Para cada estrutura, você tem a opção de separar alguns dos dados para utilizar para teste e validação.</span><span class="sxs-lookup"><span data-stu-id="e4e06-111">For each structure, you have the option of setting aside some of the data to use for testing and validation.</span></span> <span data-ttu-id="e4e06-112">Ao criar esse *conjunto de dados* de controle ao configurar suas fontes de dados, você pode garantir que todos os modelos baseados na estrutura sejam capazes de usar um conjunto de dados consistente para teste.</span><span class="sxs-lookup"><span data-stu-id="e4e06-112">By creating this *holdout data set* when you set up your data sources, you can ensure that all models that are based on the structure are able to use a consistent data set for testing.</span></span>  
  
 <span data-ttu-id="e4e06-113">Após ter criado uma estrutura de mineração, é possível adicionar vários modelos para aplicar a diferentes métodos de análise.</span><span class="sxs-lookup"><span data-stu-id="e4e06-113">After you have created a mining structure, you can add multiple models to apply different methods of analysis.</span></span>  
  
 <span data-ttu-id="e4e06-114">Para obter mais informações sobre como usar o **Assistente para criar estrutura de mineração**, consulte [criar estrutura de mineração &#40;SQL Server suplementos de mineração de dados&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="e4e06-114">For more information about how to use the **Create Mining Structure Wizard**, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="add-model-to-structure"></a><span data-ttu-id="e4e06-115">Adicionar modelo à estrutura</span><span class="sxs-lookup"><span data-stu-id="e4e06-115">Add Model to Structure</span></span>  
 <span data-ttu-id="e4e06-116">![Botão Adicionar Modelo à Estrutura](media/dmc-addmodel.gif "Botão Adicionar Modelo à Estrutura")</span><span class="sxs-lookup"><span data-stu-id="e4e06-116">![Add Model to Structure button](media/dmc-addmodel.gif "Add Model to Structure button")</span></span>  
  
 <span data-ttu-id="e4e06-117">Quando você adiciona um novo modelo a uma estrutura, analisa os dados usando um algoritmo diferente ou com parâmetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="e4e06-117">When you add a new model to a structure, you analyze the data by using a different algorithm, or with different parameters.</span></span> <span data-ttu-id="e4e06-118">Essa opção é particularmente útil se você quiser criar um modelo usando um dos algoritmos não expostos nas ferramentas de cliente de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="e4e06-118">This option is particularly useful if you want to create a model using one of the algorithms not exposed in the Data Mining Client tools.</span></span>  
  
 <span data-ttu-id="e4e06-119">Por exemplo, você pode usar qualquer um dos algoritmos suportados pelo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e4e06-119">For example, you can use any of the algorithms supported by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], such as:</span></span>  
  
-   <span data-ttu-id="e4e06-120">Regressão linear</span><span class="sxs-lookup"><span data-stu-id="e4e06-120">Linear regression</span></span>  
  
-   <span data-ttu-id="e4e06-121">Clustering de sequências</span><span class="sxs-lookup"><span data-stu-id="e4e06-121">Sequence clustering</span></span>  
  
-   <span data-ttu-id="e4e06-122">Análise de associação em conjuntos de dados aninhados</span><span class="sxs-lookup"><span data-stu-id="e4e06-122">Association analysis on nested data sets</span></span>  
  
 <span data-ttu-id="e4e06-123">Para ver quais tipos de estruturas de mineração estão disponíveis, você pode procurar os modelos e estruturas armazenados no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] clicando em **gerenciar modelos** ou **procurar**.</span><span class="sxs-lookup"><span data-stu-id="e4e06-123">To see what kind of mining structures are available, you can browse the models and structures stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] by clicking either **Manage Models** or **Browse**.</span></span>  
  
 <span data-ttu-id="e4e06-124">Você está limitado às estruturas de mineração de dados criados durante a sessão atual ou as estruturas de mineração que foram salvas em uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4e06-124">You are limited to data mining structures that were created during the current session, or mining structures that were saved to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e4e06-125">Para obter mais informações, consulte [Adicionar modelo à estrutura &#40;suplementos de mineração de dados para Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="e4e06-125">For more information, see [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e06-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e4e06-126">See Also</span></span>  
 <span data-ttu-id="e4e06-127">[Gerenciar modelos &#40;SQL Server suplementos de mineração de dados&#41;](manage-models-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="e4e06-127">[Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="e4e06-128">Pesquisando modelos no Excel &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="e4e06-128">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
