---
title: Derivar valores de coluna por meio da transformação Coluna Derivada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- columns [Integration Services]
- derived columns
- columns [Integration Services], values
- Derived Column transformation
ms.assetid: 28b07746-fc6f-42b2-b741-9de6fac3f29c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 837ec552144697b40cf649bc0403edfe4dc57a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569571"
---
# <a name="derive-column-values-by-using-the-derived-column-transformation"></a><span data-ttu-id="6824d-102">Derivar valores de coluna por meio da transformação Coluna Derivada</span><span class="sxs-lookup"><span data-stu-id="6824d-102">Derive Column Values by Using the Derived Column Transformation</span></span>
  <span data-ttu-id="6824d-103">Para adicionar e configurar uma transformação Coluna Derivada, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e uma origem.</span><span class="sxs-lookup"><span data-stu-id="6824d-103">To add and configure a Derived Column transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
 <span data-ttu-id="6824d-104">A transformação de Coluna Derivada usa expressões para atualizar os valores de colunas existentes ou adicionar valores a novas colunas.</span><span class="sxs-lookup"><span data-stu-id="6824d-104">The Derived Column transformation uses expressions to update the values of existing or to add values to new columns.</span></span> <span data-ttu-id="6824d-105">Ao optar por adicionar valores a novas colunas, a caixa de diálogo **Editor de Transformação Coluna Derivada** avalia a expressão e define apropriadamente os metadados das colunas.</span><span class="sxs-lookup"><span data-stu-id="6824d-105">When you choose to add values to new columns, the **Derived Column Transformation Editor** dialog box evaluates the expression and defines the metadata of the columns accordingly.</span></span> <span data-ttu-id="6824d-106">Por exemplo, se uma expressão concatena duas colunas – cada uma com o tipo de dados DT_WSTR e um comprimento de 50 – com um espaço entre os dois valores de coluna, a nova coluna terá o tipo de dados DT_WSTR e um comprimento de 101.</span><span class="sxs-lookup"><span data-stu-id="6824d-106">For example, if an expression concatenates two columns-each with the DT_WSTR data type and a length of 50-with a space between the two column values, the new column has the DT_WSTR data type and a length of 101.</span></span> <span data-ttu-id="6824d-107">É possível atualizar o tipo de dados de colunas novas.</span><span class="sxs-lookup"><span data-stu-id="6824d-107">You can update the data type of new columns.</span></span> <span data-ttu-id="6824d-108">O único requisito é que o tipo de dados seja compatível com os dados inseridos.</span><span class="sxs-lookup"><span data-stu-id="6824d-108">The only requirement is that data type be compatible with the inserted data.</span></span> <span data-ttu-id="6824d-109">Por exemplo, a caixa de diálogo **Editor de Transformação Coluna Derivada** gera um erro de validação ao atribuir um valor de dados a uma coluna com um tipo de dados Integer.</span><span class="sxs-lookup"><span data-stu-id="6824d-109">For example, the **Derived Column Transformation Editor** dialog box generates a validation error when you assign a date value to a column with an integer data type.</span></span> <span data-ttu-id="6824d-110">Dependendo do tipo de dados selecionado, é possível especificar o comprimento, a precisão, a escala e a página de código da coluna.</span><span class="sxs-lookup"><span data-stu-id="6824d-110">Depending on the data type that you selected, you can specify the length, precision, scale, and code page of the column.</span></span>  
  
### <a name="to-derive-column-values"></a><span data-ttu-id="6824d-111">Para derivar valores de coluna</span><span class="sxs-lookup"><span data-stu-id="6824d-111">To derive column values</span></span>  
  
1.  <span data-ttu-id="6824d-112">No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="6824d-112">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="6824d-113">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="6824d-113">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="6824d-114">Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste a transformação Coluna Derivada para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="6824d-114">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Derived Column transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="6824d-115">Conecte a transformação de Coluna Derivada ao fluxo de dados arrastando um conector da fonte ou da transformação anterior para a transformação de Coluna Derivada.</span><span class="sxs-lookup"><span data-stu-id="6824d-115">Connect the Derived Column transformation to the data flow by dragging the connector from the source or the previous transformation to the Derived Column transformation.</span></span>  
  
5.  <span data-ttu-id="6824d-116">Clique duas vezes na transformação de Coluna Derivada.</span><span class="sxs-lookup"><span data-stu-id="6824d-116">Double-click the Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="6824d-117">Na caixa de diálogo **Editor de Transformação Coluna Derivada** , crie as expressões para usar como condições arrastando variáveis, colunas, funções e operadores para a coluna **Expressão** na grade.</span><span class="sxs-lookup"><span data-stu-id="6824d-117">In the **Derived Column Transformation Editor** dialog box, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Expression** column in the grid.</span></span> <span data-ttu-id="6824d-118">Como alternativa, é possível digitar a expressão na coluna **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="6824d-118">Alternatively, you can type the expression in the **Expression** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6824d-119">Se a expressão não for válida, o texto da expressão será realçado e uma Dica de Ferramenta na coluna descreverá os erros.</span><span class="sxs-lookup"><span data-stu-id="6824d-119">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="6824d-120">Na lista **Coluna Derivada**, selecione **\<add as new column>** para escrever o resultado de avaliação da expressão em uma nova coluna ou selecionar uma coluna existente para atualizar com o resultado da avaliação.</span><span class="sxs-lookup"><span data-stu-id="6824d-120">In the **Derived Column** list, select **\<add as new column>** to write the evaluation result of the expression to a new column, or select an existing column to update with the evaluation result.</span></span>  
  
     <span data-ttu-id="6824d-121">Se você optar por usar uma nova coluna, a caixa de diálogo **Editor de Transformação Coluna Derivada** avaliará a expressão e atribuirá um tipo de dados à coluna, dependendo do tipo de dados, tamanho, precisões, escala e página de código.</span><span class="sxs-lookup"><span data-stu-id="6824d-121">If you chose to use a new column, the **Derived Column Transformation Editor** dialog box evaluates the expression and assigns a data type to the column, depending on the data type, length, precisions, scale, and code page.</span></span>  
  
8.  <span data-ttu-id="6824d-122">Se estiver usando uma nova coluna, selecione um tipo de dados na lista **Tipo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="6824d-122">If using a new column, select a data type in the **Data Type** list.</span></span> <span data-ttu-id="6824d-123">Dependendo do tipo de dados selecionado, atualize, opcionalmente, os valores nas colunas **Tamanho**, **Precisão**, **Escala**e **Página de Código** .</span><span class="sxs-lookup"><span data-stu-id="6824d-123">Depending on the selected data type, optionally update the values in the **Length**, **Precision**, **Scale**, and **Code Page** columns.</span></span> <span data-ttu-id="6824d-124">Metadados de colunas existentes não podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="6824d-124">Metadata of existing columns cannot be changed.</span></span>  
  
9. <span data-ttu-id="6824d-125">Opcionalmente, modifique os valores na coluna **Nome da Coluna Derivada** .</span><span class="sxs-lookup"><span data-stu-id="6824d-125">Optionally, modify the values in the **Derived Column Name** column.</span></span>  
  
10. <span data-ttu-id="6824d-126">Para configurar a saída de erro, clique em **Configurar Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="6824d-126">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="6824d-127">Para obter mais informações, consulte [Configurar uma saída de erro em um componente de fluxo de dados](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="6824d-127">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="6824d-128">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6824d-128">Click **OK**.</span></span>  
  
12. <span data-ttu-id="6824d-129">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="6824d-129">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6824d-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6824d-130">See Also</span></span>  
 <span data-ttu-id="6824d-131">[Derived Column Transformation](derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="6824d-131">[Derived Column Transformation](derived-column-transformation.md) </span></span>  
 <span data-ttu-id="6824d-132">[Tipos de dados do Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="6824d-132">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="6824d-133">[Transformações do Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="6824d-133">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="6824d-134">[Caminhos do Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="6824d-134">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="6824d-135">[Tarefa de Fluxo de Dados](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="6824d-135">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="6824d-136">Expressões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6824d-136">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
