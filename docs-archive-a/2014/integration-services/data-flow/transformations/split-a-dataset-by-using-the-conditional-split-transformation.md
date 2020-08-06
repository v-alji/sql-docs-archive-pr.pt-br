---
title: Dividir um conjunto de dados por meio da transformação Divisão Condicional | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Conditional Split transformation
- splitting dataset
- datasets [Integration Services], splitting
ms.assetid: 23b3e84f-9296-4dc9-81c0-c7f06ae3f1ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2efbc3973db1ab1b6b61f6de879e451319b50e49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582036"
---
# <a name="split-a-dataset-by-using-the-conditional-split-transformation"></a><span data-ttu-id="c3d7a-102">Dividir um conjunto de dados por meio da transformação Divisão Condicional</span><span class="sxs-lookup"><span data-stu-id="c3d7a-102">Split a Dataset by Using the Conditional Split Transformation</span></span>
  <span data-ttu-id="c3d7a-103">Para adicionar e configurar uma transformação Divisão Condicional, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e uma origem.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-103">To add and configure a Conditional Split transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-conditionally-split-a-dataset"></a><span data-ttu-id="c3d7a-104">Para dividir um conjunto de dados condicionalmente</span><span class="sxs-lookup"><span data-stu-id="c3d7a-104">To conditionally split a dataset</span></span>  
  
1.  <span data-ttu-id="c3d7a-105">No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="c3d7a-106">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="c3d7a-107">Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste a transformação de Divisão Condicional para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-107">Click the **Data Flow** tab, and, from the **Toolbox**, drag the Conditional Split transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="c3d7a-108">Conecte a transformação de Divisão Condicional ao fluxo de dados arrastando o m conector da fonte de dados ou da transformação anterior para a transformação de Divisão Condicional.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-108">Connect the Conditional Split transformation to the data flow by dragging the connector from the data source or the previous transformation to the Conditional Split transformation.</span></span>  
  
5.  <span data-ttu-id="c3d7a-109">Clique duas vezes na transformação de Divisão Condicional.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-109">Double-click the Conditional Split transformation.</span></span>  
  
6.  <span data-ttu-id="c3d7a-110">No **Editor da Transformação de Divisão Condicional**, construa as expressões para usar como condições arrastando variáveis, colunas, funções e operadores para a coluna **Condição** na grade.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-110">In the **Conditional Split Transformation Editor**, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Condition** column in the grid.</span></span> <span data-ttu-id="c3d7a-111">Ou, é possível digitar a expressão na coluna **Condição** .</span><span class="sxs-lookup"><span data-stu-id="c3d7a-111">Or, you can type the expression in the **Condition** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c3d7a-112">Uma variável ou coluna pode ser usada em diversas expressões.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-112">A variable or column can be used in multiple expressions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c3d7a-113">Se a expressão não for válida, o texto da expressão será realçado e uma Dica de Ferramenta na coluna descreverá os erros.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-113">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="c3d7a-114">Como opção, modifique os valores na coluna **Nome da Saída** .</span><span class="sxs-lookup"><span data-stu-id="c3d7a-114">Optionally, modify the values in the **Output Name** column.</span></span> <span data-ttu-id="c3d7a-115">Os nomes padrão são Maiúscula 1, Maiúscula 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-115">The default names are Case 1, Case 2, and so forth.</span></span>  
  
8.  <span data-ttu-id="c3d7a-116">Para modificar a sequência na qual as condições são avaliadas, clique na seta para cima ou na seta para abaixo.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-116">To modify the sequence in which the conditions are evaluated, click the up arrow or down arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c3d7a-117">Coloque as condições que são mais prováveis de serem encontradas no topo da lista.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-117">Place the conditions that are most likely to be encountered at the top of the list.</span></span>  
  
9. <span data-ttu-id="c3d7a-118">Como opção, modifique o nome da saída padrão para obter linhas de dados que não correspondem com nenhuma condição.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-118">Optionally, modify the name of the default output for data rows that do not match any condition.</span></span>  
  
10. <span data-ttu-id="c3d7a-119">Para configurar uma saída de erro, clique em **Configurar Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-119">To configure an error output, click **Configure Error Output**.</span></span> <span data-ttu-id="c3d7a-120">Para obter mais informações, consulte [Configurar uma saída de erro em um componente de fluxo de dados](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="c3d7a-120">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="c3d7a-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3d7a-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="c3d7a-122">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="c3d7a-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d7a-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3d7a-123">See Also</span></span>  
 <span data-ttu-id="c3d7a-124">[Conditional Split Transformation](conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="c3d7a-124">[Conditional Split Transformation](conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="c3d7a-125">[Transformações do Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="c3d7a-125">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="c3d7a-126">[Caminhos do Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="c3d7a-126">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="c3d7a-127">[Tipos de dados do Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="c3d7a-127">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="c3d7a-128">[Tarefa de Fluxo de Dados](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="c3d7a-128">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="c3d7a-129">Expressões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c3d7a-129">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
