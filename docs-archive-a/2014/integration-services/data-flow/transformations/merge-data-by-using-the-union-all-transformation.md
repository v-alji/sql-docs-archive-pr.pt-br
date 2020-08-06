---
title: Mesclar dados por meio da transformação Unir Tudo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- merging datasets [Integration Services]
- merging inputs [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 78304403-a81c-4101-b87e-ec80ddfdac98
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e782a5770ab9936e4c5cc84da706a5472ecd4d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582039"
---
# <a name="merge-data-by-using-the-union-all-transformation"></a><span data-ttu-id="1734f-102">Mesclar dados por meio da transformação Unir Tudo</span><span class="sxs-lookup"><span data-stu-id="1734f-102">Merge Data by Using the Union All Transformation</span></span>
  <span data-ttu-id="1734f-103">Para adicionar e configurar uma transformação Union All, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e duas fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="1734f-103">To add and configure a Union All transformation, the package must already include at least one Data Flow task and two data sources.</span></span>  
  
 <span data-ttu-id="1734f-104">A transformação Union All combina várias entradas.</span><span class="sxs-lookup"><span data-stu-id="1734f-104">The Union All transformation combines multiple inputs.</span></span> <span data-ttu-id="1734f-105">A primeira entrada que é conectada à transformação é a entrada de referência e as entradas conectadas em seguida são as entradas secundárias.</span><span class="sxs-lookup"><span data-stu-id="1734f-105">The first input that is connected to the transformation is the reference input, and the inputs connected subsequently are the secondary inputs.</span></span> <span data-ttu-id="1734f-106">A saída inclui as colunas da entrada de referência.</span><span class="sxs-lookup"><span data-stu-id="1734f-106">The output includes the columns in the reference input.</span></span>  
  
### <a name="to-combine-inputs-in-a-data-flow"></a><span data-ttu-id="1734f-107">Para combinar entradas em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="1734f-107">To combine inputs in a data flow</span></span>  
  
1.  <span data-ttu-id="1734f-108">No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], clique duas vezes no pacote no Gerenciador de Soluções para abri-lo no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , e clique na guia **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="1734f-108">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], double-click the package in Solution Explorer to open the package in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and then click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="1734f-109">Da **Caixa de Ferramentas**, arraste a transformação Union All para a superfície de design da guia **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="1734f-109">From the **Toolbox**, drag the Union All transformation to the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="1734f-110">Conecte a transformação Union All para o fluxo de dados arrastando um conector de uma fonte de dados ou uma transformação anterior para a transformação Union All.</span><span class="sxs-lookup"><span data-stu-id="1734f-110">Connect the Union All transformation to the data flow by dragging a connector from the data source or a previous transformation to the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="1734f-111">Clique duas vezes na transformação Union All.</span><span class="sxs-lookup"><span data-stu-id="1734f-111">Double-click the Union All transformation.</span></span>  
  
5.  <span data-ttu-id="1734f-112">No **Editor da Transformação Union All**, mapeie uma coluna de uma entrada para uma coluna na lista **Nome da Coluna de Saída** clicando uma linha e selecionando uma coluna na lista de entrada.</span><span class="sxs-lookup"><span data-stu-id="1734f-112">In the **Union All Transformation Editor**, map a column from an input to a column in the **Output Column Name** list by clicking a row and then selecting a column in the input list.</span></span> <span data-ttu-id="1734f-113">Selecione **\<ignore>** na lista de entrada para ignorar o mapeamento da coluna.</span><span class="sxs-lookup"><span data-stu-id="1734f-113">Select **\<ignore>** in the input list to skip mapping the column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1734f-114">O mapeamento entre duas colunas requer que seus metadados tenham correspondência.</span><span class="sxs-lookup"><span data-stu-id="1734f-114">The mapping between two columns requires that the metadata of the columns match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1734f-115">As colunas em uma entrada secundária que não são mapeadas para colunas de referência, são definidas com valores nulos na saída.</span><span class="sxs-lookup"><span data-stu-id="1734f-115">Columns in a secondary input that are not mapped to reference columns are set to null values in the output.</span></span>  
  
6.  <span data-ttu-id="1734f-116">Opcionalmente, modifique os nomes de colunas na coluna **Nome da Coluna de Saída** .</span><span class="sxs-lookup"><span data-stu-id="1734f-116">Optionally, modify the names of columns in the **Output Column Name** column.</span></span>  
  
7.  <span data-ttu-id="1734f-117">Repetir as etapas 5 e 6 para cada coluna em cada entrada.</span><span class="sxs-lookup"><span data-stu-id="1734f-117">Repeat steps 5 and 6 for each column in each input.</span></span>  
  
8.  <span data-ttu-id="1734f-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1734f-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="1734f-119">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="1734f-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1734f-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1734f-120">See Also</span></span>  
 <span data-ttu-id="1734f-121">[Transformação Unir Tudo](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="1734f-121">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="1734f-122">[Transformações do Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="1734f-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="1734f-123">[Caminhos do Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="1734f-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="1734f-124">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="1734f-124">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
