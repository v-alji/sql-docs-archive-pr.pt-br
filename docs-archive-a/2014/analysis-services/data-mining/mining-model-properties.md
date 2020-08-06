---
title: Propriedades do modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- data mining [Analysis Services], properties
- columns [data mining], properties
- Data Mining Designer
- properties [data mining]
ms.assetid: c5194619-8b31-42be-a95f-585711462945
author: minewiskan
ms.author: owend
ms.openlocfilehash: fb086f4a978ca96de8e6fc99f889f718247629af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581601"
---
# <a name="mining-model-properties"></a><span data-ttu-id="bbb75-102">Propriedades do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="bbb75-102">Mining Model Properties</span></span>
  <span data-ttu-id="bbb75-103">Os modelos de mineração têm os seguintes tipos de propriedades:</span><span class="sxs-lookup"><span data-stu-id="bbb75-103">Mining models have the following kinds of properties:</span></span>  
  
-   <span data-ttu-id="bbb75-104">As propriedades que são herdadas da estrutura de mineração que definem o tipo de dados e o tipo de conteúdo dos dados usados pelo modelo;</span><span class="sxs-lookup"><span data-stu-id="bbb75-104">Properties that are inherited from the mining structure that define the data type and content type of the data used by the model;</span></span>  
  
-   <span data-ttu-id="bbb75-105">As propriedades que são relacionadas ao algoritmo usadas para criar o modelo de mineração, inclusive os parâmetros de cliente;</span><span class="sxs-lookup"><span data-stu-id="bbb75-105">Properties that are related to the algorithm used to create the mining model, including any customer parameters;</span></span>  
  
-   <span data-ttu-id="bbb75-106">As propriedades que definem um filtro no modelo usado para treinar o modelo.</span><span class="sxs-lookup"><span data-stu-id="bbb75-106">Properties that define a filter on the model used to train the model.</span></span>  
  
 <span data-ttu-id="bbb75-107">As propriedades de um modelo de mineração são inicialmente definidas quando você cria o modelo; porém, você pode alterar a maioria das propriedades posteriormente, inclusive os parâmetros de algoritmo, filtros e uso de coluna.</span><span class="sxs-lookup"><span data-stu-id="bbb75-107">The properties of a mining model are initially defined when you create the model; however, you can alter most properties later, including the algorithm parameters, filters, and column usage properties.</span></span> <span data-ttu-id="bbb75-108">Você pode alterar as propriedades usando a guia **Modelos de Mineração** do Designer de Data Mining ou usando AMO ou XMLA.</span><span class="sxs-lookup"><span data-stu-id="bbb75-108">You change properties by using the **Mining Models** tab of Data Mining Designer, or by using AMO or XMLA.</span></span>  
  
 <span data-ttu-id="bbb75-109">Sempre que você alterar uma propriedade de um modelo, deve processar novamente o modelo para que as alterações sejam refletidas no modelo.</span><span class="sxs-lookup"><span data-stu-id="bbb75-109">Whenever you change any property of a model, you must reprocess the model for the changes to be reflected in the model.</span></span> <span data-ttu-id="bbb75-110">O reprocessamento é necessário mesmo se a alteração envolver apenas metadados, como a adição de um alias ou descrição de coluna.</span><span class="sxs-lookup"><span data-stu-id="bbb75-110">Reprocessing is required even if the change only involves metadata, such as adding a column alias or description.</span></span>  
  
## <a name="properties-of-models"></a><span data-ttu-id="bbb75-111">Propriedades de modelos</span><span class="sxs-lookup"><span data-stu-id="bbb75-111">Properties of Models</span></span>  
 <span data-ttu-id="bbb75-112">A tabela a seguir descreve as propriedades que são específicas para modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="bbb75-112">The following table describes the properties that are specific to mining models.</span></span> <span data-ttu-id="bbb75-113">Adicionalmente, há propriedades que você pode definir em colunas individuais na mineração</span><span class="sxs-lookup"><span data-stu-id="bbb75-113">Additionally, there are properties that you can set on individual columns in the mining</span></span>  
  
|<span data-ttu-id="bbb75-114">Propriedade</span><span class="sxs-lookup"><span data-stu-id="bbb75-114">Property</span></span>|<span data-ttu-id="bbb75-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="bbb75-115">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="bbb75-116">**Algoritmo**</span><span class="sxs-lookup"><span data-stu-id="bbb75-116">**Algorithm**</span></span>|<span data-ttu-id="bbb75-117">Define o tipo de algoritmo do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="bbb75-117">Sets the algorithm type for the mining model.</span></span>|  
|<span data-ttu-id="bbb75-118">**AlgorithmParameters**</span><span class="sxs-lookup"><span data-stu-id="bbb75-118">**AlgorithmParameters**</span></span>|<span data-ttu-id="bbb75-119">Define valores para os parâmetros dos algoritmos disponíveis para cada tipo de algoritmo.</span><span class="sxs-lookup"><span data-stu-id="bbb75-119">Sets values for algorithm parameters that are available for each algorithm type.</span></span>|  
|<span data-ttu-id="bbb75-120">**Filter**</span><span class="sxs-lookup"><span data-stu-id="bbb75-120">**Filter**</span></span>|<span data-ttu-id="bbb75-121">Define um filtro que é aplicado aos dados que são usados para treinar e testar o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="bbb75-121">Sets a filter that is applied to the data that is used for training and testing the mining model.</span></span> <span data-ttu-id="bbb75-122">A definição do filtro é armazenada com o modelo e pode ser usada opcionalmente quando consultas de previsão são criadas ou quando você testar a exatidão do modelo.</span><span class="sxs-lookup"><span data-stu-id="bbb75-122">The filter definition is stored with the model and can be used optionally when you create prediction queries, or when you test the accuracy of the model.</span></span><br /><br /> <span data-ttu-id="bbb75-123">O filtro de modelo não é opcional para o treinamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="bbb75-123">The model filter is not optional when training the model.</span></span>|  
|<span data-ttu-id="bbb75-124">**Nome**</span><span class="sxs-lookup"><span data-stu-id="bbb75-124">**Name**</span></span>|<span data-ttu-id="bbb75-125">Define o nome do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="bbb75-125">Sets the name of the mining model.</span></span>|  
|<span data-ttu-id="bbb75-126">**AllowDrillThrough**</span><span class="sxs-lookup"><span data-stu-id="bbb75-126">**AllowDrillThrough**</span></span>|<span data-ttu-id="bbb75-127">Especifica se a análise está habilitada no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="bbb75-127">Specifies whether drill through is enabled on the mining model.</span></span>|  
  
## <a name="properties-of-model-columns"></a><span data-ttu-id="bbb75-128">Propriedades das colunas de modelo</span><span class="sxs-lookup"><span data-stu-id="bbb75-128">Properties of Model Columns</span></span>  
 <span data-ttu-id="bbb75-129">Você pode definir as seguintes propriedades específicas da mineração de dados para cada coluna em um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="bbb75-129">You can set the following data mining-specific properties for each column in a mining model.</span></span> <span data-ttu-id="bbb75-130">Você pode definir essas propriedades com um valor diferente em cada modelo de mineração em uma estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="bbb75-130">You can set these properties to a different value for each mining model in a mining structure.</span></span>  
  
|<span data-ttu-id="bbb75-131">Propriedade</span><span class="sxs-lookup"><span data-stu-id="bbb75-131">Property</span></span>|<span data-ttu-id="bbb75-132">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="bbb75-132">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="bbb75-133">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="bbb75-133">**Description**</span></span>|<span data-ttu-id="bbb75-134">Descreve a finalidade da coluna de mineração.</span><span class="sxs-lookup"><span data-stu-id="bbb75-134">Describes the purpose of the mining column.</span></span>|  
|<span data-ttu-id="bbb75-135">**Nome**</span><span class="sxs-lookup"><span data-stu-id="bbb75-135">**Name**</span></span>|<span data-ttu-id="bbb75-136">Define o nome da coluna do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="bbb75-136">Sets the name of the mining model column.</span></span> <span data-ttu-id="bbb75-137">Você pode digitar um novo nome, para fornecer um alias à coluna do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="bbb75-137">You can type a new name, to provide an alias for the mining model column.</span></span>|  
|<span data-ttu-id="bbb75-138">**ModelingFlags**</span><span class="sxs-lookup"><span data-stu-id="bbb75-138">**ModelingFlags**</span></span>|<span data-ttu-id="bbb75-139">Define qualquer sinalizador específico de um algoritmo para a coluna.</span><span class="sxs-lookup"><span data-stu-id="bbb75-139">Sets any algorithm-specific flags for the column.</span></span>|  
|<span data-ttu-id="bbb75-140">**SourceColumnID**</span><span class="sxs-lookup"><span data-stu-id="bbb75-140">**SourceColumnID**</span></span>|<span data-ttu-id="bbb75-141">Indica o nome da coluna de estrutura de mineração na qual a coluna de modelo é baseada.</span><span class="sxs-lookup"><span data-stu-id="bbb75-141">Indicates the name of the mining structure column on which the model column is based.</span></span><br /><br /> <span data-ttu-id="bbb75-142">Esta propriedade é somente para leitura.</span><span class="sxs-lookup"><span data-stu-id="bbb75-142">This property is read-only.</span></span>|  
|<span data-ttu-id="bbb75-143">**Usage**</span><span class="sxs-lookup"><span data-stu-id="bbb75-143">**Usage**</span></span>|<span data-ttu-id="bbb75-144">Define como a coluna será usada pelo modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="bbb75-144">Sets how the column will be used by the mining model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bbb75-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bbb75-145">See Also</span></span>  
 <span data-ttu-id="bbb75-146">[Colunas do modelo de mineração](mining-model-columns.md) </span><span class="sxs-lookup"><span data-stu-id="bbb75-146">[Mining Model Columns](mining-model-columns.md) </span></span>  
 <span data-ttu-id="bbb75-147">[Estruturas de mineração &#40;Analysis Services de mineração de dados&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="bbb75-147">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="bbb75-148">[Tarefas e instruções do modelo de mineração](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="bbb75-148">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="bbb75-149">[Alterar as propriedades de um modelo de mineração](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="bbb75-149">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="bbb75-150">[Ferramentas de mineração de dados](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="bbb75-150">[Data Mining Tools](data-mining-tools.md) </span></span>  
 <span data-ttu-id="bbb75-151">[Criar uma estrutura de mineração relacional](create-a-relational-mining-structure.md) </span><span class="sxs-lookup"><span data-stu-id="bbb75-151">[Create a Relational Mining Structure](create-a-relational-mining-structure.md) </span></span>  
 [<span data-ttu-id="bbb75-152">Criar um alias para uma coluna de modelo</span><span class="sxs-lookup"><span data-stu-id="bbb75-152">Create an Alias for a Model Column</span></span>](create-an-alias-for-a-model-column.md)  
  
  
