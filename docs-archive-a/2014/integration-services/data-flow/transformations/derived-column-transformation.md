---
title: Transformação de Coluna Derivada | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntrans.f1
helpviewer_keywords:
- multiple derived columns
- expressions [Integration Services], derived columns
- derived columns
- columns [Integration Services], derivations
- Derived Column transformation
ms.assetid: 8eba755e-8e48-4233-bd1e-09a46bf2692f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bbdc46f2e67b1b859fcfa446c584373cfbeca0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569570"
---
# <a name="derived-column-transformation"></a><span data-ttu-id="5e246-102">Transformação Coluna Derivada</span><span class="sxs-lookup"><span data-stu-id="5e246-102">Derived Column Transformation</span></span>
  <span data-ttu-id="5e246-103">A transformação Coluna Derivada cria novos valores de coluna aplicando expressões às colunas de entrada de transformação.</span><span class="sxs-lookup"><span data-stu-id="5e246-103">The Derived Column transformation creates new column values by applying expressions to transformation input columns.</span></span> <span data-ttu-id="5e246-104">Uma expressão pode conter qualquer combinação de variáveis, funções, operadores e colunas da entrada de transformação.</span><span class="sxs-lookup"><span data-stu-id="5e246-104">An expression can contain any combination of variables, functions, operators, and columns from the transformation input.</span></span> <span data-ttu-id="5e246-105">O resultado pode ser adicionado como uma coluna nova ou adicionado a uma coluna existente como um valor de substituição.</span><span class="sxs-lookup"><span data-stu-id="5e246-105">The result can be added as a new column or inserted into an existing column as a replacement value.</span></span> <span data-ttu-id="5e246-106">A transformação Coluna Derivada pode definir várias colunas derivadas, e qualquer variável ou coluna de entrada pode aparecer em várias expressões.</span><span class="sxs-lookup"><span data-stu-id="5e246-106">The Derived Column transformation can define multiple derived columns, and any variable or input columns can appear in multiple expressions.</span></span>  
  
 <span data-ttu-id="5e246-107">É possível usar essa transformação para executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="5e246-107">You can use this transformation to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="5e246-108">Concatenar dados de colunas diferentes em uma coluna derivada.</span><span class="sxs-lookup"><span data-stu-id="5e246-108">Concatenate data from different columns into a derived column.</span></span> <span data-ttu-id="5e246-109">Por exemplo, você pode combinar valores das colunas **FirstName** e **LastName** em uma única coluna derivada chamada **FullName**usando a expressão `FirstName + " " + LastName`.</span><span class="sxs-lookup"><span data-stu-id="5e246-109">For example, you can combine values from the **FirstName** and **LastName** columns into a single derived column named **FullName**, by using the expression `FirstName + " " + LastName`.</span></span>  
  
-   <span data-ttu-id="5e246-110">Extrair caracteres de dados de cadeia de caracteres utilizando funções, como SUBSTRING, e armazenar o resultado em uma coluna derivada.</span><span class="sxs-lookup"><span data-stu-id="5e246-110">Extract characters from string data by using functions such as SUBSTRING, and then store the result in a derived column.</span></span> <span data-ttu-id="5e246-111">Por exemplo, é possível extrair a inicial de uma pessoa da coluna **FirstName** utilizando a expressão `SUBSTRING(FirstName,1,1)`.</span><span class="sxs-lookup"><span data-stu-id="5e246-111">For example, you can extract a person's initial from the **FirstName** column, by using the expression `SUBSTRING(FirstName,1,1)`.</span></span>  
  
-   <span data-ttu-id="5e246-112">Aplicar funções matemáticas a dados numéricos e armazenar o resultado em uma coluna derivada.</span><span class="sxs-lookup"><span data-stu-id="5e246-112">Apply mathematical functions to numeric data and store the result in a derived column.</span></span> <span data-ttu-id="5e246-113">Por exemplo, você pode alterar o comprimento e a precisão de uma coluna numérica, **SalesTax**, para um número com duas casas decimais utilizando a expressão `ROUND(SalesTax, 2)`.</span><span class="sxs-lookup"><span data-stu-id="5e246-113">For example, you can change the length and precision of a numeric column, **SalesTax**, to a number with two decimal places, by using the expression `ROUND(SalesTax, 2)`.</span></span>  
  
-   <span data-ttu-id="5e246-114">Criar expressões que comparam colunas de entrada e variáveis.</span><span class="sxs-lookup"><span data-stu-id="5e246-114">Create expressions that compare input columns and variables.</span></span> <span data-ttu-id="5e246-115">Por exemplo, você pode comparar a variável **Version** com os dados na coluna **ProductVersion**e, dependendo do resultado da comparação, utilizar o valor de **Version** ou de **ProductVersion**utilizando a expressão `ProductVersion == @Version? ProductVersion : @Version`.</span><span class="sxs-lookup"><span data-stu-id="5e246-115">For example, you can compare the variable **Version** against the data in the column **ProductVersion**, and depending on the comparison result, use the value of either **Version** or **ProductVersion**, by using the expression `ProductVersion == @Version? ProductVersion : @Version`.</span></span>  
  
-   <span data-ttu-id="5e246-116">Extrair partes de um valor de data e hora.</span><span class="sxs-lookup"><span data-stu-id="5e246-116">Extract parts of a datetime value.</span></span> <span data-ttu-id="5e246-117">Por exemplo, você pode usar as funções GETDATE e DATEPART para extrair o ano atual por meio da expressão `DATEPART("year",GETDATE())`.</span><span class="sxs-lookup"><span data-stu-id="5e246-117">For example, you can use the GETDATE and DATEPART functions to extract the current year, by using the expression `DATEPART("year",GETDATE())`.</span></span>  
  
-   <span data-ttu-id="5e246-118">Converta cadeias de caracteres de dados em um formato específico usando uma expressão.</span><span class="sxs-lookup"><span data-stu-id="5e246-118">Convert date strings to a specific format using an expression.</span></span>  
  
## <a name="configuration-of-the-derived-column-transformation"></a><span data-ttu-id="5e246-119">Configuração da transformação Coluna Derivada</span><span class="sxs-lookup"><span data-stu-id="5e246-119">Configuration of the Derived Column Transformation</span></span>  
 <span data-ttu-id="5e246-120">Você pode configurar a transformação Coluna Derivada das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="5e246-120">You can configure the Derived column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="5e246-121">Forneça uma expressão para cada coluna de entrada ou coluna nova a ser alterada.</span><span class="sxs-lookup"><span data-stu-id="5e246-121">Provide an expression for each input column or new column that will be changed.</span></span> <span data-ttu-id="5e246-122">Para obter mais informações, consulte [Expressões do Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5e246-122">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5e246-123">Se uma expressão fizer referência a uma coluna de entrada substituída pela transformação Coluna Derivada, a expressão utilizará o valor original da coluna e não o valor derivado.</span><span class="sxs-lookup"><span data-stu-id="5e246-123">If an expression references an input column that is overwritten by the Derived Column transformation, the expression uses the original value of the column, not the derived value.</span></span>  
  
-   <span data-ttu-id="5e246-124">Se estiver adicionando resultados às novas colunas e o tipo de dados for `string`, especifique uma página de código.</span><span class="sxs-lookup"><span data-stu-id="5e246-124">If adding results to new columns and the data type is `string`, specify a code page.</span></span> <span data-ttu-id="5e246-125">Para obter mais informações, consulte [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="5e246-125">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="5e246-126">A transformação Coluna Derivada inclui a propriedade personalizada FriendlyExpression.</span><span class="sxs-lookup"><span data-stu-id="5e246-126">The Derived Column transformation includes the FriendlyExpression custom property.</span></span> <span data-ttu-id="5e246-127">Essa propriedade pode ser atualizada por uma expressão de propriedade quando o pacote é carregado.</span><span class="sxs-lookup"><span data-stu-id="5e246-127">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="5e246-128">Para obter mais informações, consulte [Usar expressões de propriedade em pacotes](../../expressions/use-property-expressions-in-packages.md)e [Propriedades personalizadas da transformação](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5e246-128">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="5e246-129">Essa transformação tem uma entrada, uma saída comum e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="5e246-129">This transformation has one input, one regular output, and one error output.</span></span>  
  
 <span data-ttu-id="5e246-130">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="5e246-130">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="5e246-131">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação Coluna Derivada** , consulte [Editor de Transformação Colunas Derivadas](../../derived-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="5e246-131">For more information about the properties that you can set in the **Derived Column Transformation Editor** dialog box, see [Derived Column Transformation Editor](../../derived-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="5e246-132">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="5e246-132">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="5e246-133">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="5e246-133">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="5e246-134">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="5e246-134">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="5e246-135">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="5e246-135">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="5e246-136">Para obter mais informações sobre como definir propriedades, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="5e246-136">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="5e246-137">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="5e246-137">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="5e246-138">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="5e246-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="5e246-139">Derivar valores de coluna por meio da transformação Coluna Derivada</span><span class="sxs-lookup"><span data-stu-id="5e246-139">Derive Column Values by Using the Derived Column Transformation</span></span>](derived-column-transformation.md)  
  
## <a name="related-content"></a><span data-ttu-id="5e246-140">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="5e246-140">Related Content</span></span>  
 <span data-ttu-id="5e246-141">Artigo técnico, [Exemplos de expressões SSIS](https://go.microsoft.com/fwlink/?LinkId=220761), em social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5e246-141">Technical article, [SSIS Expression Examples](https://go.microsoft.com/fwlink/?LinkId=220761), on social.technet.microsoft.com</span></span>  
  
 <span data-ttu-id="5e246-142">Blog, [como dividir os dados da coluna usando o SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span><span class="sxs-lookup"><span data-stu-id="5e246-142">Blog, [How to Split Column Data using SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span></span>  
  
  
