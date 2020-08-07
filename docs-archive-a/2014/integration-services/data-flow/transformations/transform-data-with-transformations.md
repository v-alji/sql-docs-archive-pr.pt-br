---
title: Transformar Dados com Transformações | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], transformations
- transformations [Integration Services], about transformations
- transforming data [Integration Services]
ms.assetid: e1340b6f-ef75-4b14-af6f-823586eff0ed
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952d8ea4eeea2dd8010a17a2b3deba41447b6231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583178"
---
# <a name="transform-data-with-transformations"></a><span data-ttu-id="d8da2-102">Transformar dados com transformações</span><span class="sxs-lookup"><span data-stu-id="d8da2-102">Transform Data with Transformations</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="d8da2-103">inclui três tipos de componentes de fluxo de dados: fontes, transformações e destinos.</span><span class="sxs-lookup"><span data-stu-id="d8da2-103">includes three types of data flow components: sources, transformations, and destinations.</span></span>  
  
 <span data-ttu-id="d8da2-104">O diagrama a seguir mostra um fluxo de dados simples que tem uma fonte, duas transformações e um destino.</span><span class="sxs-lookup"><span data-stu-id="d8da2-104">The following diagram shows a simple data flow that has a source, two transformations, and a destination.</span></span>  
  
 <span data-ttu-id="d8da2-105">![Fluxo de dados](../../media/mw-dts-08.gif "Fluxo de dados")</span><span class="sxs-lookup"><span data-stu-id="d8da2-105">![Data flow](../../media/mw-dts-08.gif "Data flow")</span></span>  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="d8da2-106">As transformações fornecem a seguinte funcionalidade:</span><span class="sxs-lookup"><span data-stu-id="d8da2-106">transformations provide the following functionality:</span></span>  
  
-   <span data-ttu-id="d8da2-107">Dividir, copiar e mesclar conjuntos de linhas e executar operações de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d8da2-107">Splitting, copying, and merging rowsets and performing lookup operations.</span></span>  
  
-   <span data-ttu-id="d8da2-108">Atualizar valores de coluna e criar novas colunas aplicando transformações tais como alterar minúsculas para maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="d8da2-108">Updating column values and creating new columns by applying transformations such as changing lowercase to uppercase.</span></span>  
  
-   <span data-ttu-id="d8da2-109">Executar operações de inteligência empresarial, tais como limpeza de dados, mineração de texto ou execução de consultas de previsão de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="d8da2-109">Performing business intelligence operations such as cleaning data, mining text, or running data mining prediction queries.</span></span>  
  
-   <span data-ttu-id="d8da2-110">Criar novos conjuntos de linhas que consistem em valores agregados classificados, dados de exemplo ou dados dinâmicos ou não dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="d8da2-110">Creating new rowsets that consist of aggregate or sorted values, sample data, or pivoted and unpivoted data.</span></span>  
  
-   <span data-ttu-id="d8da2-111">Executar tarefas como exportar e importar dados, fornecer informações de auditoria e trabalhar com dimensões de alteração lenta.</span><span class="sxs-lookup"><span data-stu-id="d8da2-111">Performing tasks such as exporting and importing data, providing audit information, and working with slowly changing dimensions.</span></span>  
  
 <span data-ttu-id="d8da2-112">Para obter mais informações, consulte [Integration Services Transformations](integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="d8da2-112">For more information, see [Integration Services Transformations](integration-services-transformations.md).</span></span>  
  
 <span data-ttu-id="d8da2-113">Você também pode gravar transformações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d8da2-113">You can also write custom transformations.</span></span> <span data-ttu-id="d8da2-114">Para obter mais informações, consulte [Desenvolvendo um componente de fluxo de dados personalizado](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) e [Desenvolvendo tipos específicos de componentes de fluxo de dados](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span><span class="sxs-lookup"><span data-stu-id="d8da2-114">For more information, see [Developing a Custom Data Flow Component](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) and [Developing Specific Types of Data Flow Components](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span></span>  
  
 <span data-ttu-id="d8da2-115">Depois de adicionar a transformação ao designer de fluxo de dados, mas antes de configurar a transformação, você conecta a transformação ao fluxo de dados conectando a saída de outra transformação ou fonte no fluxo de dados à entrada desta transformação.</span><span class="sxs-lookup"><span data-stu-id="d8da2-115">After you add the transformation to the data flow designer, but before you configure the transformation, you connect the transformation to the data flow by connecting the output of another transformation or source in the data flow to the input of this transformation.</span></span> <span data-ttu-id="d8da2-116">O conector entre dois componentes de fluxo de dados é chamado de caminho.</span><span class="sxs-lookup"><span data-stu-id="d8da2-116">The connector between two data flow components is called a path.</span></span> <span data-ttu-id="d8da2-117">Para obter mais informações sobre como conectar componentes e trabalhar com caminhos, consulte [Conectar componentes com caminhos](../../connect-components-with-paths.md).</span><span class="sxs-lookup"><span data-stu-id="d8da2-117">For more information about connecting components and working with paths, see [Connect Components with Paths](../../connect-components-with-paths.md).</span></span>  
  
### <a name="to-add-a-transformation-to-a-data-flow"></a><span data-ttu-id="d8da2-118">Para adicionar uma transformação a um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="d8da2-118">To add a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="d8da2-119">Adicionar ou excluir um componente em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="d8da2-119">Add or Delete a Component in a Data Flow</span></span>](../add-or-delete-a-component-in-a-data-flow.md)  
  
### <a name="to-connect-a-transformation-to-a-data-flow"></a><span data-ttu-id="d8da2-120">Para conectar uma transformação a um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="d8da2-120">To connect a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="d8da2-121">Conectar componentes em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="d8da2-121">Connect Components in a Data Flow</span></span>](../connect-components-in-a-data-flow.md)  
  
### <a name="to-set-the-properties-of-a-transformation"></a><span data-ttu-id="d8da2-122">Para definir as propriedades de uma transformação</span><span class="sxs-lookup"><span data-stu-id="d8da2-122">To set the properties of a transformation</span></span>  
  
-   [<span data-ttu-id="d8da2-123">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="d8da2-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8da2-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d8da2-124">See Also</span></span>  
 <span data-ttu-id="d8da2-125">[Tarefa de Fluxo de Dados](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="d8da2-125">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 <span data-ttu-id="d8da2-126">[Fluxo de Dados](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="d8da2-126">[Data Flow](../data-flow.md) </span></span>  
 <span data-ttu-id="d8da2-127">[Conectar componentes com caminhos](../../connect-components-with-paths.md) </span><span class="sxs-lookup"><span data-stu-id="d8da2-127">[Connect Components with Paths](../../connect-components-with-paths.md) </span></span>  
 <span data-ttu-id="d8da2-128">[Tratamento de erro em dados](../error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="d8da2-128">[Error Handling in Data](../error-handling-in-data.md) </span></span>  
 [<span data-ttu-id="d8da2-129">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="d8da2-129">Data Flow</span></span>](../data-flow.md)  
  
  
