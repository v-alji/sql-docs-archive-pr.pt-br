---
title: Especificar o tipo de conteúdo e de dados de coluna&#39;s (Assistente de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifycontentdatatype.f1
ms.assetid: 7061f674-e806-46f2-8c15-e260a3c69a17
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66af7280e444036468b9cc33a131993524d3586d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581491"
---
# <a name="specify-the-column39s-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="cc23d-102">Especificar o tipo de conteúdo e de dados da coluna&#39;s (Assistente de mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="cc23d-102">Specify the Column&#39;s Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="cc23d-103">Use a página **Especificar o Tipo de Conteúdo e de Dados da Coluna** para modificar a coluna e os tipos de conteúdo que já foram definidos pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="cc23d-103">Use the **Specify the Column's Content and Data Type** page to modify the column and content types that have already been set by the wizard.</span></span> <span data-ttu-id="cc23d-104">O assistente usa os tipos de dados das colunas de origem e os recursos do algoritmo selecionado para determinar os tipos de dados e de conteúdo padrão de cada coluna.</span><span class="sxs-lookup"><span data-stu-id="cc23d-104">The wizard uses the data types of the source columns and the capabilities of the selected algorithm to determine the default data and content types for each column.</span></span>  
  
 <span data-ttu-id="cc23d-105">**Para obter mais informações:** [Assistente de Mineração de Dados &#40;Analysis Services – Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Criar uma estrutura de mineração relacional](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="cc23d-105">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="cc23d-106">Opções</span><span class="sxs-lookup"><span data-stu-id="cc23d-106">Options</span></span>  
 <span data-ttu-id="cc23d-107">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="cc23d-107">**Columns**</span></span>  
 <span data-ttu-id="cc23d-108">Uma lista das colunas definidas na página **Especificar os Dados de Treinamento** do assistente.</span><span class="sxs-lookup"><span data-stu-id="cc23d-108">A list of the columns that are defined in the **Specify the Training Data** page of the wizard.</span></span>  
  
 <span data-ttu-id="cc23d-109">**Tipo de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="cc23d-109">**Content Type**</span></span>  
 <span data-ttu-id="cc23d-110">O tipo de conteúdo que é atribuído a cada coluna.</span><span class="sxs-lookup"><span data-stu-id="cc23d-110">The content type that is assigned to each column.</span></span> <span data-ttu-id="cc23d-111">Clique dentro de uma célula para alterar o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cc23d-111">Click inside a cell to change the content type.</span></span> <span data-ttu-id="cc23d-112">Para obter mais informações sobre tipos de conteúdo, consulte [Tipos de conteúdo &#40;Mineração de dados&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="cc23d-112">For more information about content types, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="cc23d-113">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="cc23d-113">**Data Type**</span></span>  
 <span data-ttu-id="cc23d-114">Os tipos de dados que são atribuídos a cada coluna.</span><span class="sxs-lookup"><span data-stu-id="cc23d-114">The data types that are assigned to each column.</span></span> <span data-ttu-id="cc23d-115">Clique dentro de uma célula para alterar o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="cc23d-115">Click inside a cell to change the data type.</span></span> <span data-ttu-id="cc23d-116">Para obter mais informações sobre tipos de conteúdo, consulte [Tipos de dados &#40;Mineração de dados&#41;](data-mining/data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="cc23d-116">For more information about data types, see [Data Types &#40;Data Mining&#41;](data-mining/data-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="cc23d-117">**Detect**</span><span class="sxs-lookup"><span data-stu-id="cc23d-117">**Detect**</span></span>  
 <span data-ttu-id="cc23d-118">Clique para detectar automaticamente os tipos de conteúdo contínuo e distinto para a coluna numérica.</span><span class="sxs-lookup"><span data-stu-id="cc23d-118">Click to automatically detect the continuous and discrete content types for numeric column.</span></span> <span data-ttu-id="cc23d-119">Isso não se aplica a estruturas de mineração baseadas em fontes de dados OLAP.</span><span class="sxs-lookup"><span data-stu-id="cc23d-119">This does not apply to mining structures that are based on OLAP data sources.</span></span> <span data-ttu-id="cc23d-120">Para estruturas de mineração OLAP, o assistente detecta tipos de conteúdo automaticamente e escolhe um tipo compatível com o algoritmo selecionado.</span><span class="sxs-lookup"><span data-stu-id="cc23d-120">For OLAP mining structures, the wizard automatically detects content types and chooses a type that is compatible with the selected algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc23d-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc23d-121">See Also</span></span>  
 <span data-ttu-id="cc23d-122">[Concluindo o assistente &#40;assistente de mineração de dados&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="cc23d-122">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="cc23d-123">[Ajuda F1 do assistente de mineração de dados &#40;Analysis Services Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="cc23d-123">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="cc23d-124">Especifique os dados de treinamento &#40;assistente de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="cc23d-124">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](specify-the-training-data-data-mining-wizard.md)  
  
  
