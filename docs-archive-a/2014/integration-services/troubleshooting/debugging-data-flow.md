---
title: Depurando o fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- progress reporting [Integration Services]
- data viewers [Integration Services]
- data flow [Integration Services], debugging
- debugging [Integration Services], data flow
- counting rows
ms.assetid: 1c574f1b-54f7-4c05-8e42-8620e2c1df0f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed1d1b7ebb119d452ca3de92fdad47552d1cc36c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681751"
---
# <a name="debugging-data-flow"></a><span data-ttu-id="0112e-102">Depurando fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="0112e-102">Debugging Data Flow</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="0112e-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] e o Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] incluem recursos e ferramentas que você pode usar para solucionar problemas de fluxos de dados em um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0112e-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] and the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer include features and tools that you can use to troubleshoot the data flows in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
-   [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="0112e-104">O Designer fornece visualizadores de dados.</span><span class="sxs-lookup"><span data-stu-id="0112e-104">Designer provides data viewers.</span></span>  
  
-   [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="0112e-105">O Designer e as transformações do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fornecem contagens de linha.</span><span class="sxs-lookup"><span data-stu-id="0112e-105">Designer and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] transformations provide row counts.</span></span>  
  
-   [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="0112e-106">fornece relatórios de progresso em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="0112e-106">Designer provides progress reporting at run time.</span></span>  
  
## <a name="data-viewers"></a><span data-ttu-id="0112e-107">Visualizadores de dados</span><span class="sxs-lookup"><span data-stu-id="0112e-107">Data Viewers</span></span>  
 <span data-ttu-id="0112e-108">Os visualizadores de dados exibem dados entre dois componentes em um fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="0112e-108">Data viewers display data between two components in a data flow.</span></span> <span data-ttu-id="0112e-109">Os visualizadores de dados podem exibir dados quando os dados são extraídos de uma fonte de dados e entram primeiro um fluxo de dados, antes e depois de uma transformação atualizar os dados, e antes dos dados serem carregados em seu destino.</span><span class="sxs-lookup"><span data-stu-id="0112e-109">Data viewers can display data when the data is extracted from a data source and first enters a data flow, before and after a transformation updates the data, and before the data is loaded into its destination.</span></span>  
  
 <span data-ttu-id="0112e-110">Para visualizar os dados, você anexa os visualizadores de dados ao caminho que conecta dois componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="0112e-110">To view the data, you attach data viewers to the path that connects two data flow components.</span></span> <span data-ttu-id="0112e-111">A habilidade de visualizar os dados entre componentes de fluxo de dados, facilita a identificação de valores de dados inesperados, a visualização de como uma transformação altera os valores das colunas, e a descoberta da razão pela qual uma transformação falha.</span><span class="sxs-lookup"><span data-stu-id="0112e-111">The ability to view data between data flow components makes it easier to identify unexpected data values, view the way a transformation changes column values, and discover the reason that a transformation fails.</span></span> <span data-ttu-id="0112e-112">Por exemplo, você pode descobrir uma falha na pesquisa em uma tabela de referência e, para corrigir isso, você pode desejar adicionar uma transformação que forneça dados padrão para colunas em branco.</span><span class="sxs-lookup"><span data-stu-id="0112e-112">For example, you may find that a lookup in a reference table fails, and to correct this you may want to add a transformation that provides default data for blank columns.</span></span>  
  
 <span data-ttu-id="0112e-113">Um visualizador de dados pode exibir dados em uma grade.</span><span class="sxs-lookup"><span data-stu-id="0112e-113">A data viewer can display data in a grid.</span></span> <span data-ttu-id="0112e-114">Ao usar uma grade, você seleciona as colunas a serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="0112e-114">Using a grid, you select the columns to display.</span></span> <span data-ttu-id="0112e-115">Os valores das colunas selecionadas são exibidos em um formato tabular.</span><span class="sxs-lookup"><span data-stu-id="0112e-115">The values for the selected columns display in a tabular format.</span></span>  
  
 <span data-ttu-id="0112e-116">Você também pode incluir vários visualizadores de dados em um caminho.</span><span class="sxs-lookup"><span data-stu-id="0112e-116">You can also include multiple data viewers on a path.</span></span> <span data-ttu-id="0112e-117">Você pode exibir os mesmos dados em diferentes formatos, por exemplo, criar uma exibição de gráfico e uma exibição de grade dos dados, ou criar visualizadores de dados para diferentes colunas de dados.</span><span class="sxs-lookup"><span data-stu-id="0112e-117">You can display the same data in different formats-for example, create a chart view and a grid view of the data-or create different data viewers for different columns of data.</span></span>  
  
 <span data-ttu-id="0112e-118">Quando você adiciona um visualizador de dados a um caminho, o Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] adiciona um ícone de visualização de dados à superfície de design da guia **Fluxo de Dados** , ao lado do caminho.</span><span class="sxs-lookup"><span data-stu-id="0112e-118">When you add a data viewer to a path, [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer adds a data viewer icon to the design surface of the **Data Flow** tab, next to the path.</span></span> <span data-ttu-id="0112e-119">As transformações que podem tem múltiplas saídas, tais como as transformações Divisão Condicional, podem incluir um visualizador em cada caminho.</span><span class="sxs-lookup"><span data-stu-id="0112e-119">Transformations that can have multiple outputs, such as the Conditional Split transformation, can include a data viewer on each path.</span></span>  
  
 <span data-ttu-id="0112e-120">Em tempo de execução, uma janela **Visualizador de Dados** é aberta e exibe as informações especificadas pelo formato do visualizador de dados.</span><span class="sxs-lookup"><span data-stu-id="0112e-120">At run time, a **Data Viewer** window opens and displays the information specified by the data viewer format.</span></span> <span data-ttu-id="0112e-121">Por exemplo, um visualizador de dados que utiliza o formato de grade exibe os dados das colunas selecionadas, o número de linhas de saída transmitidas ao componente de fluxo de dados e o número de linhas exibidas.</span><span class="sxs-lookup"><span data-stu-id="0112e-121">For example, a data viewer that uses the grid format shows data for the selected columns, the number of output rows passed to the data flow component, and the number of rows displayed.</span></span> <span data-ttu-id="0112e-122">As informações exibem buffer por buffer e, dependendo da largura das linhas no fluxo de dados, um buffer pode conter mais ou menos linhas.</span><span class="sxs-lookup"><span data-stu-id="0112e-122">The information displays buffer by buffer and, depending on the width of the rows in the data flow, a buffer may contain more or fewer rows.</span></span>  
  
 <span data-ttu-id="0112e-123">Na caixa de diálogo **Visualizador de Dados** , você pode copiar os dados para a Área de Transferência, limpar todos os dados da tabela, configurar novamente o visualizador de dados, retomar o fluxo de dados e desanexar ou anexar o visualizador de dados.</span><span class="sxs-lookup"><span data-stu-id="0112e-123">In the **Data Viewer** dialog box, you can copy the data to the Clipboard, clear all data from the table, reconfigure the data viewer, resume the flow of data, and detach or attach the data viewer.</span></span>  
  
#### <a name="to-add-a-data-viewer"></a><span data-ttu-id="0112e-124">Para adicionar um visualizador de dados</span><span class="sxs-lookup"><span data-stu-id="0112e-124">To add a data viewer</span></span>  
  
-   [<span data-ttu-id="0112e-125">Adicionar um visualizador de dados a um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="0112e-125">Add a Data Viewer to a Data Flow</span></span>](../add-a-data-viewer-to-a-data-flow.md)  
  
## <a name="row-counts"></a><span data-ttu-id="0112e-126">Contagens de linhas</span><span class="sxs-lookup"><span data-stu-id="0112e-126">Row Counts</span></span>  
 <span data-ttu-id="0112e-127">O número de linhas que passaram por um caminho é exibido na superfície de design da guia **Fluxo de Dados** no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , ao lado do caminho.</span><span class="sxs-lookup"><span data-stu-id="0112e-127">The number of rows that have passed through a path is displayed on the design surface of the **Data Flow** tab in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer next to the path.</span></span> <span data-ttu-id="0112e-128">O número é atualizado periodicamente enquanto os dados se movimentam pelo caminho.</span><span class="sxs-lookup"><span data-stu-id="0112e-128">The number is updated periodically while the data moves through the path.</span></span>  
  
 <span data-ttu-id="0112e-129">Você também pode adicionar uma transformação Contagem de Linhas ao fluxo de dados para capturar a contagem final de linhas em uma variável.</span><span class="sxs-lookup"><span data-stu-id="0112e-129">You can also add a Row Count transformation to the data flow to capture the final row count in a variable.</span></span> <span data-ttu-id="0112e-130">Para obter mais informações, consulte [Row Count Transformation](../data-flow/transformations/row-count-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="0112e-130">For more information, see [Row Count Transformation](../data-flow/transformations/row-count-transformation.md).</span></span>  
  
## <a name="progress-reporting"></a><span data-ttu-id="0112e-131">Relatório de progresso</span><span class="sxs-lookup"><span data-stu-id="0112e-131">Progress Reporting</span></span>  
 <span data-ttu-id="0112e-132">Quando você executa um pacote, o Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] descreve o progresso na superfície de design da guia **Fluxo de Dados** , exibindo cada componente de fluxo de dados em uma cor que indica seu status.</span><span class="sxs-lookup"><span data-stu-id="0112e-132">When you run a package, [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer depicts progress on the design surface of the **Data Flow** tab by displaying each data flow component in a color that indicates status.</span></span> <span data-ttu-id="0112e-133">Quando cada componente começa a executar sua função, ele muda para a cor amarelo, e quando ele termina com sucesso, sua cor muda para verde.</span><span class="sxs-lookup"><span data-stu-id="0112e-133">When each component starts to perform its work, it changes from no color to yellow, and when it finishes successfully, it changes to green.</span></span> <span data-ttu-id="0112e-134">A cor vermelha indica que o componente falhou.</span><span class="sxs-lookup"><span data-stu-id="0112e-134">A red color indicates that the component failed.</span></span>  
  
 <span data-ttu-id="0112e-135">A tabela a seguir descreve a codificação de cores.</span><span class="sxs-lookup"><span data-stu-id="0112e-135">The following table describes the color-coding.</span></span>  
  
|<span data-ttu-id="0112e-136">Color</span><span class="sxs-lookup"><span data-stu-id="0112e-136">Color</span></span>|<span data-ttu-id="0112e-137">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0112e-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0112e-138">Nenhuma cor</span><span class="sxs-lookup"><span data-stu-id="0112e-138">No color</span></span>|<span data-ttu-id="0112e-139">Esperando ser chamado pelo mecanismo de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="0112e-139">Waiting to be called by the data flow engine.</span></span>|  
|<span data-ttu-id="0112e-140">Amarelo</span><span class="sxs-lookup"><span data-stu-id="0112e-140">Yellow</span></span>|<span data-ttu-id="0112e-141">Executando uma transformação, extraindo dados ou carregando dados.</span><span class="sxs-lookup"><span data-stu-id="0112e-141">Performing a transformation, extracting data, or loading data.</span></span>|  
|<span data-ttu-id="0112e-142">Verde</span><span class="sxs-lookup"><span data-stu-id="0112e-142">Green</span></span>|<span data-ttu-id="0112e-143">Executado com êxito.</span><span class="sxs-lookup"><span data-stu-id="0112e-143">Ran successfully.</span></span>|  
|<span data-ttu-id="0112e-144">vermelha</span><span class="sxs-lookup"><span data-stu-id="0112e-144">red</span></span>|<span data-ttu-id="0112e-145">Executado com erros.</span><span class="sxs-lookup"><span data-stu-id="0112e-145">Ran with errors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0112e-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0112e-146">See Also</span></span>  
 [<span data-ttu-id="0112e-147">Ferramentas de solução de problemas para desenvolvimento de pacotes</span><span class="sxs-lookup"><span data-stu-id="0112e-147">Troubleshooting Tools for Package Development</span></span>](troubleshooting-tools-for-package-development.md)  
  
  
