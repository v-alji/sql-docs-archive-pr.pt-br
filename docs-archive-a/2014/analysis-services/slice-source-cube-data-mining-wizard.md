---
title: Cubo de origem de fatia (Assistente de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.slicesourcecube.f1
ms.assetid: 16485608-d3b9-49ee-8baa-948038cdd7ec
author: minewiskan
ms.author: owend
ms.openlocfilehash: 762248d4c2a268ac36b0dfa3ffeba20123017017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683707"
---
# <a name="slice-source-cube-data-mining-wizard"></a><span data-ttu-id="9b5a5-102">Fatiar cubo de origem (Assistente de Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="9b5a5-102">Slice Source Cube (Data Mining Wizard)</span></span>
  <span data-ttu-id="9b5a5-103">Você pode usar a caixa de diálogo **Fatiar Cubo de Origem** para restringir os dados usados para treinar o modelo.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-103">You can use the **Slice Source Cube** dialog box to restrict the data used to train the model.</span></span> <span data-ttu-id="9b5a5-104">Normalmente, um cubo contém os dados relacionados a muitas dimensões e atributos diferentes, como todos os repositórios, todas as regiões e todos os produtos.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-104">Typically a cube contains data related to many different dimensions and attributes, such as all stores, all regions, and all products.</span></span> <span data-ttu-id="9b5a5-105">Não é prático treinar um modelo em combinações ilimitadas de atributos; portanto, use essa caixa de diálogo para escolher um conjunto específico a ser usado no treinamento de um modelo.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-105">It is not practical to train a model on unlimited combinations of attributes, so you use this dialog box to choose a specific set to use in training a model.</span></span>  
  
 <span data-ttu-id="9b5a5-106">Por exemplo, no cubo AdventureWorks, você pode fatiar por uma linha de produto, região ou ano específico, para obter uma parte dos dados.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-106">For example, in the AdventureWorks cube, you might slice by a particular product line, region, or year, to get a portion of the data.</span></span>  
  
 <span data-ttu-id="9b5a5-107">Se você não estiver familiarizado com fatias e cubos, recomendamos consultar estes artigos:</span><span class="sxs-lookup"><span data-stu-id="9b5a5-107">If you are unfamiliar with slices and cubes, we recommend that you review these articles:</span></span>  
  
-   [<span data-ttu-id="9b5a5-108">Definir a propriedade de fatia da partição &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9b5a5-108">Set the Partition Slice Property &#40;Analysis Services&#41;</span></span>](multidimensional-models/set-the-partition-slice-property-analysis-services.md)  
  
-   [<span data-ttu-id="9b5a5-109">Criar e gerenciar uma partição local &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9b5a5-109">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](multidimensional-models/create-and-manage-a-local-partition-analysis-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="9b5a5-110">Observe que não há suporte para as funções MDX dinâmicas (como [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) ou [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) na propriedade Slice das partições.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-110">Note that dynamic MDX functions (such as [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) or [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) are not supported in the Slice property for partitions.</span></span> <span data-ttu-id="9b5a5-111">Você deve definir a fatia usando tuplas explícitas ou referências de membro.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-111">You must define the slice by using explicit tuples or member references.</span></span>  
>   
>  <span data-ttu-id="9b5a5-112">Por exemplo, em vez de usar [: &#40;intervalo&#41; &#40;MDX&#41;](/sql/mdx/range-mdx) para definir um intervalo, você precisaria enumerar cada membro pelos anos específicos.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-112">For example, rather than using  [: &#40;Range&#41; &#40;MDX&#41;](/sql/mdx/range-mdx) to define a range, you would need to enumerate each member by the specific years.</span></span>  
>   
>  <span data-ttu-id="9b5a5-113">Se você precisa definir uma fatia complexa, recomendamos definir as tuplas na fatia usando um script XMLA Alter.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-113">If you need to define a complex slice, we recommend that you define the tuples in the slice by using an XMLA Alter script.</span></span> <span data-ttu-id="9b5a5-114">Em seguida, você pode usar a ferramenta de linha de comando ascmd ou [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) do SSIS para executar o script e criar o conjunto especificado de membros imediatamente antes de você processar a partição.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-114">Then, you can use either the ascmd command-line tool or the SSIS [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) to run the script and create the specified set of members immediately before you process the partition.</span></span>  
  
 <span data-ttu-id="9b5a5-115">**Para obter mais informações:** [Assistente de Mineração de Dados &#40;Analysis Services – Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Criar uma estrutura de mineração relacional](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="9b5a5-115">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="9b5a5-116">Opções</span><span class="sxs-lookup"><span data-stu-id="9b5a5-116">Options</span></span>  
 <span data-ttu-id="9b5a5-117">**Dimensão**</span><span class="sxs-lookup"><span data-stu-id="9b5a5-117">**Dimension**</span></span>  
 <span data-ttu-id="9b5a5-118">Selecione a dimensão que deseja fatiar.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-118">Select the dimension that you want to slice.</span></span>  
  
 <span data-ttu-id="9b5a5-119">**Hierarquia**</span><span class="sxs-lookup"><span data-stu-id="9b5a5-119">**Hierarchy**</span></span>  
 <span data-ttu-id="9b5a5-120">Selecione a hierarquia que deseja fatiar.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-120">Select the hierarchy that you want to slice.</span></span> <span data-ttu-id="9b5a5-121">Você pode escolher qualquer nível de uma hierarquia, mas os atributos usados no modelo estarão apenas no nível que você escolher.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-121">You can choose any level of a hierarchy, but the attributes used in the model will be only at the level that you choose.</span></span>  
  
 <span data-ttu-id="9b5a5-122">Por exemplo, se você escolher a hierarquia Geography, e selecionar Country como o nível, não poderá criar um modelo que use City como os atributos.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-122">For example, if you choose the Geography hierarchy, and select Country as the level, you cannot build a model that uses City as the attributes.</span></span> <span data-ttu-id="9b5a5-123">Por outro lado, se você escolher City como o nível da hierarquia onde poderá fatiar, não poderá criar um modelo de mineração baseado em Country.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-123">Conversely, if you choose City as the level of the hierarchy on which to slice, you cannot create a mining model based on Country.</span></span>  
  
 <span data-ttu-id="9b5a5-124">**Operador**</span><span class="sxs-lookup"><span data-stu-id="9b5a5-124">**Operator**</span></span>  
 <span data-ttu-id="9b5a5-125">Selecione o operador a ser usado para criar uma expressão da fatia.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-125">Select the operator to use in building a slice expression.</span></span>  
  
 <span data-ttu-id="9b5a5-126">Por exemplo, se você escolher geografia como a hierarquia, poderá selecionar o operador = e, em seguida, digitar "Europa" como filtro, para obter dados de cubo apenas para a Europa.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-126">For example, if you chose Geography as the hierarchy, you could select the operator = and then type "Europe" as the filter, to get cube data for Europe only.</span></span>  
  
 <span data-ttu-id="9b5a5-127">**Expressão de filtro**</span><span class="sxs-lookup"><span data-stu-id="9b5a5-127">**Filter Expression**</span></span>  
 <span data-ttu-id="9b5a5-128">Digite uma expressão a ser usada como um critério para filtrar o cubo na dimensão selecionada.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-128">Type an expression to use as a criterion when filtering the cube on the selected dimension.</span></span>  
  
 <span data-ttu-id="9b5a5-129">**Parâmetros**</span><span class="sxs-lookup"><span data-stu-id="9b5a5-129">**Parameters**</span></span>  
 <span data-ttu-id="9b5a5-130">Esta opção não é usada para modelos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="9b5a5-130">This option is not used for data mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b5a5-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b5a5-131">See Also</span></span>  
 <span data-ttu-id="9b5a5-132">[Concluindo o assistente &#40;assistente de mineração de dados&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="9b5a5-132">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="9b5a5-133">[Ajuda F1 do assistente de mineração de dados &#40;Analysis Services Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="9b5a5-133">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="9b5a5-134">Especificar o uso de coluna do modelo de mineração &#40;assistente de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="9b5a5-134">Specify Mining Model Column Usage &#40;Data Mining Wizard&#41;</span></span>](specify-mining-model-column-usage-data-mining-wizard.md)  
  
  
