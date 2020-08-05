---
title: Estender um conjunto de dados por meio da transformação Junção de Mesclagem | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Merge Join transformation
- datasets [Integration Services], joining
- datasets [Integration Services], extending
- joining datasets [Integration Services]
ms.assetid: 9e512c3c-f89b-45f3-8281-cdb8f35a2b1f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a387c4ad840eb739d36023be9323c063dcb9a68e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570783"
---
# <a name="extend-a-dataset-by-using-the-merge-join-transformation"></a><span data-ttu-id="428bb-102">Estender um conjunto de dados por meio da transformação Junção de Mesclagem</span><span class="sxs-lookup"><span data-stu-id="428bb-102">Extend a Dataset by Using the Merge Join Transformation</span></span>
  <span data-ttu-id="428bb-103">Para adicionar e configurar uma ttransformação Junção de Mesclagem, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e dois componentes de fluxo de dados que forneçam entradas para a ttransformação Junção de Mesclagem.</span><span class="sxs-lookup"><span data-stu-id="428bb-103">To add and configure a Merge Join transformation, the package must already include at least one Data Flow task and two data flow components that provide inputs to the Merge Join transformation.</span></span>  
  
 <span data-ttu-id="428bb-104">A ttransformação Junção de Mesclagem requer duas entradas classificadas.</span><span class="sxs-lookup"><span data-stu-id="428bb-104">The Merge Join transformation requires two sorted inputs.</span></span> <span data-ttu-id="428bb-105">Para obter mais informações, consulte [Classificar dados para as transformações Mesclagem e Junção de Mesclagem](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="428bb-105">For more information, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
### <a name="to-extend-a-dataset"></a><span data-ttu-id="428bb-106">Estender um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="428bb-106">To extend a dataset</span></span>  
  
1.  <span data-ttu-id="428bb-107">No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="428bb-107">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="428bb-108">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="428bb-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="428bb-109">Clique na guia **Fluxo de Dados** e na **Caixa de Ferramentas**, arraste a transformação Junção de Mesclagem para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="428bb-109">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Merge Join transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="428bb-110">Conecte a transformação Junção de Mesclagem ao fluxo de dados arrastando um conector de uma fonte de dados ou transformação anterior para a transformação Junção de Mesclagem.</span><span class="sxs-lookup"><span data-stu-id="428bb-110">Connect the Merge Join transformation to the data flow by dragging the connector from a data source or a previous transformation to the Merge Join transformation.</span></span>  
  
5.  <span data-ttu-id="428bb-111">Clique duas vezes na ttransformação Junção de Mesclagem.</span><span class="sxs-lookup"><span data-stu-id="428bb-111">Double-click the Merge Join transformation.</span></span>  
  
6.  <span data-ttu-id="428bb-112">Na caixa de diálogo **Editor da transformação Junção de Mesclagem** , selecione o tipo de junção que deseja usar na lista **Tipo de junção** .</span><span class="sxs-lookup"><span data-stu-id="428bb-112">In the **Merge Join Transformation Editor** dialog box, select the type of join to use in the **Join type** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="428bb-113">Se você selecionar o tipo **Junção externa esquerda** , poderá clicar em **Trocar Entradas** para mudar as entradas e converter a junção externa esquerda para uma junção externa direita.</span><span class="sxs-lookup"><span data-stu-id="428bb-113">If you select the **Left outer join** type, you can click **Swap Inputs** to switch the inputs and convert the left outer join to a right outer join.</span></span>  
  
7.  <span data-ttu-id="428bb-114">Arraste as colunas na entrada esquerda para colunas na entrada direita para especificar as colunas de junção.</span><span class="sxs-lookup"><span data-stu-id="428bb-114">Drag columns in the left input to columns in the right input to specify the join columns.</span></span> <span data-ttu-id="428bb-115">Se as colunas tiverem o mesmo nome, marque a caixa de seleção **Chave de Junção** e a transformação Junção de Mesclagem criará a junção automaticamente.</span><span class="sxs-lookup"><span data-stu-id="428bb-115">If the columns have the same name, you can select the **Join Key** check box and the Merge Join transformation automatically creates the join.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="428bb-116">Você pode criar junções somente entre colunas que tem a mesma posição de classificação e as junções devem ser criadas na ordem especificada pela posição de classificação.</span><span class="sxs-lookup"><span data-stu-id="428bb-116">You can create joins only between columns that have the same sort position, and the joins must be created in the order specified by the sort position.</span></span> <span data-ttu-id="428bb-117">Se você tentar criar as junções fora da ordem, o **Editor da Transformação Junção de Mesclagem** solicitará que você crie junções adicionais para as posições da ordem de classificação que foram ignoradas.</span><span class="sxs-lookup"><span data-stu-id="428bb-117">If you attempt to create the joins out of order, the **Merge Join Transformation Editor** prompts you to create additional joins for the skipped sort order positions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="428bb-118">Por padrão, a saída é classificada nas colunas de junção.</span><span class="sxs-lookup"><span data-stu-id="428bb-118">By default, the output is sorted on the join columns.</span></span>  
  
8.  <span data-ttu-id="428bb-119">Nas entradas esquerda e direita, marque as caixas de seleção de colunas adicionais a serem incluídas na saída.</span><span class="sxs-lookup"><span data-stu-id="428bb-119">In the left and right inputs, select the check boxes of additional columns to include in the output.</span></span> <span data-ttu-id="428bb-120">Por padrão, as colunas de junção já estão incluídas.</span><span class="sxs-lookup"><span data-stu-id="428bb-120">Join columns are included by default.</span></span>  
  
9. <span data-ttu-id="428bb-121">Se preferir, atualize os nomes de colunas de saída na coluna **Alias de Saída** .</span><span class="sxs-lookup"><span data-stu-id="428bb-121">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="428bb-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="428bb-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="428bb-123">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="428bb-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="428bb-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="428bb-124">See Also</span></span>  
 <span data-ttu-id="428bb-125">[Transformação Junção de Mesclagem](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="428bb-125">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="428bb-126">[Transformações do Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="428bb-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="428bb-127">[Caminhos do Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="428bb-127">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="428bb-128">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="428bb-128">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
