---
title: Exemplos de expressões (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/08/2017
ms.openlocfilehash: c7ef06143dafdb5034d0f6202fdc16bc51f74ca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572411"
---
# <a name="expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="05c90-102">Exemplos de expressões (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="05c90-102">Expression Examples (Report Builder and SSRS)</span></span>

<span data-ttu-id="05c90-103">Expressões costumam ser usadas em relatórios para controlar o conteúdo e a aparência do relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-103">Expressions are used frequently in reports to control content and report appearance.</span></span> <span data-ttu-id="05c90-104">As expressões são escritas em [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] e podem usar funções internas de código personalizado, de relatório e de grupo e variáveis definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="05c90-104">Expressions are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], and can use built-in functions custom code, report and group variables, and user-defined variables.</span></span> <span data-ttu-id="05c90-105">As expressões começam com um sinal de igual (=).</span><span class="sxs-lookup"><span data-stu-id="05c90-105">Expressions begin with an equal sign (=).</span></span> <span data-ttu-id="05c90-106">Para obter mais informações sobre o editor de expressões e os tipos de referências que podem ser incluídos, consulte [Uso de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) e [Adicionar uma expressão &#40;Construtor de Relatórios e SSRS&#41;](add-an-expression-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-106">For more information about the expression editor and the types of references that you can include, see [Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md), and [Add an Expression &#40;Report Builder and SSRS&#41;](add-an-expression-report-builder-and-ssrs.md).</span></span>  

> [!IMPORTANT]  
>  <span data-ttu-id="05c90-107">Quando o RDL Sandboxing é habilitado, somente certos tipos e membros podem ser usados no texto da expressão durante o tempo de publicação do relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-107">When RDL Sandboxing is enabled, only certain types and members can be used in expression text at report publish time.</span></span> <span data-ttu-id="05c90-108">Para obter mais informações, consulte [Habilitar e desabilitar o RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-108">For more information, see [Enable and Disable RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span></span>  

<span data-ttu-id="05c90-109">Este tópico fornece exemplos de expressões que podem ser usadas para tarefas comuns em um relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-109">This topic provides examples of expressions that can be used for common tasks in a report.</span></span>  

-   <span data-ttu-id="05c90-110">[Funções do Visual Basic](#VisualBasicFunctions) Exemplos de funções de data, de cadeia de caracteres, de conversão e condicionais do [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05c90-110">[Visual Basic Functions](#VisualBasicFunctions) Examples for date, string, conversion and conditional [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions.</span></span>  

-   <span data-ttu-id="05c90-111">[Funções de relatórios](#ReportFunctions) Exemplos de funções de agregação e de outras funções internas de relatórios.</span><span class="sxs-lookup"><span data-stu-id="05c90-111">[Report Functions](#ReportFunctions) Examples for aggregates and other built-in report functions.</span></span>  

-   <span data-ttu-id="05c90-112">[Aparência dos dados do relatório](#AppearanceofReportData) Exemplos de alteração da aparência de um relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-112">[Appearance of Report Data](#AppearanceofReportData) Examples for changing the appearance of a report.</span></span>  

-   <span data-ttu-id="05c90-113">Exemplos de[propriedades](#Properties) para definir propriedades de item de relatório para controlar formato ou visibilidade.</span><span class="sxs-lookup"><span data-stu-id="05c90-113">[Properties](#Properties) Examples for setting report item properties to control format or visibility.</span></span>  

-   <span data-ttu-id="05c90-114">[Parâmetros](#Parameters) Exemplos de uso de parâmetros em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="05c90-114">[Parameters](#Parameters) Examples for using parameters in an expression.</span></span>  

-   <span data-ttu-id="05c90-115">[Código Personalizado](#CustomCode) Exemplos de código personalizado inserido.</span><span class="sxs-lookup"><span data-stu-id="05c90-115">[Custom Code](#CustomCode) Examples of embedded custom code.</span></span>  

<span data-ttu-id="05c90-116">Para obter exemplos de expressões para usos específicos, consulte os tópicos seguintes:</span><span class="sxs-lookup"><span data-stu-id="05c90-116">For expression examples for specific uses, see the following topics:</span></span>  

-   [<span data-ttu-id="05c90-117">Exemplos de expressões de grupo &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="05c90-117">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="05c90-118">Exemplos de equações de filtro &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="05c90-118">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="05c90-119">Filtros geralmente usados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="05c90-119">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="05c90-120">Referências de coleções de variáveis de grupo e de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="05c90-120">Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-report-and-group-variables-references-report-builder.md)  

<span data-ttu-id="05c90-121">Para obter mais informações sobre expressões simples e complexas, em que você pode usar expressões e os tipos de referências que pode incluir em uma expressão, consulte tópicos em [Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-121">For more information about simple and complex expressions, where you can use expressions, and the types of references that you can include in an expression, see topics under [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="05c90-122">Para obter mais informações sobre o contexto em que as expressões são avaliadas para calcular agregações, consulte [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-122">For more information about the context in which expressions are evaluated for calculating aggregates, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  

<span data-ttu-id="05c90-123">Para aprender como gravar expressões que usam muitas das funções e dos operadores também empregados por exemplos de expressões neste tópico, mas no contexto da gravação de um relatório, consulte [Tutorial: introdução às expressões](../tutorial-introducing-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-123">To learn how to write expressions that use many of the functions and operators also used by expression examples in this topic, but in the context of writing a report, see [Tutorial: Introducing Expressions](../tutorial-introducing-expressions.md).</span></span>  

<span data-ttu-id="05c90-124">O editor de expressão inclui uma exibição hierárquica de funções internas.</span><span class="sxs-lookup"><span data-stu-id="05c90-124">The expression editor includes a hierarchical view of built-in functions.</span></span> <span data-ttu-id="05c90-125">Quando você seleciona a função, um exemplo de código aparece no painel Valores.</span><span class="sxs-lookup"><span data-stu-id="05c90-125">When you select the function, a code example appears in the Values pane.</span></span> <span data-ttu-id="05c90-126">Para obter mais informações, consulte a caixa de diálogo [expressão](../expression-dialog-box.md) ou a [caixa de diálogo expressão &#40;Construtor de relatórios&#41;](../expression-dialog-box-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-126">For more information, see the [Expression Dialog Box](../expression-dialog-box.md) or [Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md).</span></span>  

## <a name="functions"></a><span data-ttu-id="05c90-127">Funções</span><span class="sxs-lookup"><span data-stu-id="05c90-127">Functions</span></span>  

<span data-ttu-id="05c90-128">Muitas expressões em um relatório contêm funções.</span><span class="sxs-lookup"><span data-stu-id="05c90-128">Many expressions in a report contain functions.</span></span> <span data-ttu-id="05c90-129">É possível formatar dados, aplicar lógica e acessar metadados do relatório usando estas funções.</span><span class="sxs-lookup"><span data-stu-id="05c90-129">You can format data, apply logic, and access report metadata using these functions.</span></span> <span data-ttu-id="05c90-130">Você pode escrever expressões que usam funções da [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] biblioteca de tempo de execução e dos <xref:System.Convert> <xref:System.Math> namespaces e.</span><span class="sxs-lookup"><span data-stu-id="05c90-130">You can write expressions that use functions from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library, and from the <xref:System.Convert> and <xref:System.Math> namespaces.</span></span> <span data-ttu-id="05c90-131">É possível adicionar referências a funções a partir de outros assemblies ou de código personalizado.</span><span class="sxs-lookup"><span data-stu-id="05c90-131">You can add references to functions from other assemblies or custom code.</span></span> <span data-ttu-id="05c90-132">Você também pode usar classes do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , incluindo <xref:System.Text.RegularExpressions> .</span><span class="sxs-lookup"><span data-stu-id="05c90-132">You can also use classes from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], including <xref:System.Text.RegularExpressions>.</span></span>  

###  <a name="visual-basic-functions"></a><a name="VisualBasicFunctions"></a> <span data-ttu-id="05c90-133">Funções do Visual Basic</span><span class="sxs-lookup"><span data-stu-id="05c90-133">Visual Basic Functions</span></span>  
<span data-ttu-id="05c90-134">Você pode usar as funções do [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] para manipular os dados exibidos nas caixas de texto ou usados para parâmetros, propriedades ou outras áreas do relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-134">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to manipulate the data that is displayed in text boxes or that is used for parameters, properties, or other areas of the report.</span></span> <span data-ttu-id="05c90-135">Esta seção fornece exemplos que demonstram algumas dessas funções.</span><span class="sxs-lookup"><span data-stu-id="05c90-135">This section provides examples demonstrating some of these functions.</span></span> <span data-ttu-id="05c90-136">Para obter mais informações, confira [Membros da Biblioteca de Runtime do Visual Basic](https://go.microsoft.com/fwlink/?LinkId=198941) no MSDN.</span><span class="sxs-lookup"><span data-stu-id="05c90-136">For more information, see [Visual Basic Runtime Library Members](https://go.microsoft.com/fwlink/?LinkId=198941) on MSDN.</span></span>  

<span data-ttu-id="05c90-137">O [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fornece muitas opções de formatos personalizados como, por exemplo, para formatos de data específicos.</span><span class="sxs-lookup"><span data-stu-id="05c90-137">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides many custom format options, for example, for specific date formats.</span></span> <span data-ttu-id="05c90-138">Para obter mais informações, consulte [Tipos de Formatação](https://go.microsoft.com/fwlink/?LinkId=112024) no MSDN.</span><span class="sxs-lookup"><span data-stu-id="05c90-138">For more information, see [Formatting Types](https://go.microsoft.com/fwlink/?LinkId=112024) on MSDN.</span></span>  

#### <a name="math-functions"></a><span data-ttu-id="05c90-139">Funções Matemáticas</span><span class="sxs-lookup"><span data-stu-id="05c90-139">Math Functions</span></span>  

-   <span data-ttu-id="05c90-140">A função `Round` é útil para números arredondados para o inteiro mais próximo.</span><span class="sxs-lookup"><span data-stu-id="05c90-140">The `Round` function is useful to round numbers to the nearest integer.</span></span> <span data-ttu-id="05c90-141">A expressão a seguir arredonda 1,3 para 1:</span><span class="sxs-lookup"><span data-stu-id="05c90-141">The following expression rounds a 1.3 to 1:</span></span>  

```  
= Round(1.3)  
```  

<span data-ttu-id="05c90-142">Também é possível escrever uma expressão para arredondar um valor para um múltiplo especificado, semelhante à função `MRound` no Excel.</span><span class="sxs-lookup"><span data-stu-id="05c90-142">You can also write an expression to round a value to a multiple that you specify, similar to the `MRound` function in Excel.</span></span> <span data-ttu-id="05c90-143">Multiplique o valor por um fator que cria um inteiro, arredonde o número e divida pelo mesmo fator.</span><span class="sxs-lookup"><span data-stu-id="05c90-143">Multiply the value by a factor that creates an integer, round the number, and then divide by the same factor.</span></span> <span data-ttu-id="05c90-144">Por exemplo, para arredondar 1,3 para o múltiplo mais próximo de 0,2 (1,4), use a seguinte expressão.</span><span class="sxs-lookup"><span data-stu-id="05c90-144">For example, to round 1.3 to the nearest multiple of .2 (1.4), use the following expression:</span></span>  

```  
= Round(1.3*5)/5  
```  

####  <a name="date-functions"></a><a name="DateFunctions"></a><span data-ttu-id="05c90-145">Funções de data</span><span class="sxs-lookup"><span data-stu-id="05c90-145">Date Functions</span></span>  

-   <span data-ttu-id="05c90-146">A função `Today` fornece a data atual.</span><span class="sxs-lookup"><span data-stu-id="05c90-146">The `Today` function provides the current date.</span></span> <span data-ttu-id="05c90-147">Essa expressão pode ser usada em uma caixa de texto para exibir a data no relatório ou em um parâmetro para filtrar dados baseados na data atual.</span><span class="sxs-lookup"><span data-stu-id="05c90-147">This expression can be used in a text box to display the date on the report, or in a parameter to filter data based on the current date.</span></span>  

```  
=Today()  
```  

-   <span data-ttu-id="05c90-148">A função `DateAdd` é útil para fornecer um intervalo de datas baseado em um único parâmetro.</span><span class="sxs-lookup"><span data-stu-id="05c90-148">The `DateAdd` function is useful for supplying a range of dates based on a single parameter.</span></span> <span data-ttu-id="05c90-149">A expressão a seguir fornece uma data seis meses posterior à data de um parâmetro denominado *StartDate*.</span><span class="sxs-lookup"><span data-stu-id="05c90-149">The following expression provides a date that is six months after the date from a parameter named *StartDate*.</span></span>  

```  
=DateAdd(DateInterval.Month, 6, Parameters!StartDate.Value)  
```  

-   <span data-ttu-id="05c90-150">A função `Year` exibe o ano de uma data específica.</span><span class="sxs-lookup"><span data-stu-id="05c90-150">The `Year` function displays the year for a particular date.</span></span> <span data-ttu-id="05c90-151">Você pode usar essa função para agrupar datas em conjunto ou para exibir o ano como um rótulo para um conjunto de datas.</span><span class="sxs-lookup"><span data-stu-id="05c90-151">You can use this to group dates together or to display the year as a label for a set of dates.</span></span> <span data-ttu-id="05c90-152">Essa expressão fornece o ano para um grupo determinado de datas de pedidos de vendas.</span><span class="sxs-lookup"><span data-stu-id="05c90-152">This expression provides the year for a given group of sales order dates.</span></span> <span data-ttu-id="05c90-153">A função `Month` e outras funções também podem ser usadas para manipular datas.</span><span class="sxs-lookup"><span data-stu-id="05c90-153">The `Month` function and other functions can also be used to manipulate dates.</span></span> <span data-ttu-id="05c90-154">Para obter mais informações, consulte a documentação do [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c90-154">For more information, see the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] documentation.</span></span>  

```  
=Year(Fields!OrderDate.Value)  
```  

-   <span data-ttu-id="05c90-155">É possível combinar funções em uma expressão para personalizar o formato.</span><span class="sxs-lookup"><span data-stu-id="05c90-155">You can combine functions in an expression to customize the format.</span></span> <span data-ttu-id="05c90-156">A expressão a seguir altera o formato de uma data na forma mês-dia-ano para mês-semana-número da semana.</span><span class="sxs-lookup"><span data-stu-id="05c90-156">The following expression changes the format of a date in the form month-day-year to month-week-week number.</span></span> <span data-ttu-id="05c90-157">Por exemplo, 23/12/2009 para a terceira semana de dezembro:</span><span class="sxs-lookup"><span data-stu-id="05c90-157">For example, 12/23/2009 to December Week 3:</span></span>  

```  
=Format(Fields!MyDate.Value, "MMMM") & " Week " &   
(Int(DateDiff("d", DateSerial(Year(Fields!MyDate.Value),   
Month(Fields!MyDate.Value),1), Fields!FullDateAlternateKey.Value)/7)+1).ToString  
```  

<span data-ttu-id="05c90-158">Quando usado como um campo calculado em um conjunto de dados, é possível usar essa expressão em um gráfico para agregar valores por semana dentro de cada mês.</span><span class="sxs-lookup"><span data-stu-id="05c90-158">When used as a calculated field in a dataset, you can use this expression on a chart to aggregate values by week within each month.</span></span>  

-   <span data-ttu-id="05c90-159">A expressão a seguir formata o valor SellStartDate como MMM-AA.</span><span class="sxs-lookup"><span data-stu-id="05c90-159">The following expression formats the SellStartDate value as MMM-YY.</span></span> <span data-ttu-id="05c90-160">O campo SellStartDate é um tipo de dados de data/hora.</span><span class="sxs-lookup"><span data-stu-id="05c90-160">SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "MMM-yy")  
```  

-   <span data-ttu-id="05c90-161">A expressão a seguir formata o valor SellStartDate como dd/MM/aaaa.</span><span class="sxs-lookup"><span data-stu-id="05c90-161">The following expression formats the SellStartDate value as dd/MM/yyyy.</span></span> <span data-ttu-id="05c90-162">O campo SellStartDate é um tipo de dados datetime.</span><span class="sxs-lookup"><span data-stu-id="05c90-162">The SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "dd/MM/yyyy")  
```  

-   <span data-ttu-id="05c90-163">A função `CDate` converte o valor em uma data.</span><span class="sxs-lookup"><span data-stu-id="05c90-163">The `CDate` function converts the value to a date.</span></span> <span data-ttu-id="05c90-164">A função `Now` retorna um valor de data que contém a data e hora atuais de acordo com seu sistema.</span><span class="sxs-lookup"><span data-stu-id="05c90-164">The `Now` function returns a date value containing the current date and time according to your system.</span></span> <span data-ttu-id="05c90-165">`DateDiff` retorna um valor Longo especificando o número de intervalos de hora entre dois valores de Data.</span><span class="sxs-lookup"><span data-stu-id="05c90-165">`DateDiff` returns a Long value specifying the number of time intervals between two Date values.</span></span>  

<span data-ttu-id="05c90-166">O exemplo a seguir exibe a data de início do ano atual</span><span class="sxs-lookup"><span data-stu-id="05c90-166">The following example displays the start date of the current year</span></span>  

```  
=DateAdd(DateInterval.Year,DateDiff(DateInterval.Year,CDate("01/01/1900"),Now()),CDate("01/01/1900"))  
```  

-   <span data-ttu-id="05c90-167">O exemplo a seguir exibe a data de início do mês anterior com base no mês atual.</span><span class="sxs-lookup"><span data-stu-id="05c90-167">The following example displays the start date for the previous month based on the current month.</span></span>  

```  
=DateAdd(DateInterval.Month,DateDiff(DateInterval.Month,CDate("01/01/1900"),Now())-1,CDate("01/01/1900"))  
```  

-   <span data-ttu-id="05c90-168">A expressão a seguir gera os anos de intervalo entre SellStartDate e LastReceiptDate.</span><span class="sxs-lookup"><span data-stu-id="05c90-168">The following expression generates the interval years between SellStartDate and LastReceiptDate.</span></span> <span data-ttu-id="05c90-169">Esses campos estão em dois conjuntos de dados diferentes, DataSet1 e DataSet2.</span><span class="sxs-lookup"><span data-stu-id="05c90-169">These fields are in two different datasets, DataSet1 and DataSet2.</span></span> <span data-ttu-id="05c90-170">A [Função First &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-first-function.md), que é uma função de agregação, retorna o primeiro valor de SellStartDate em DataSet1 e o primeiro valor de LastReceiptDate em DataSet2.</span><span class="sxs-lookup"><span data-stu-id="05c90-170">The [First Function &#40;Report Builder and SSRS&#41;](report-builder-functions-first-function.md), which is an aggregate function, returns the first value of SellStartDate in DataSet1 and the first value of LastReceiptDate in DataSet2.</span></span>  

```  
=DATEDIFF("yyyy", First(Fields!SellStartDate.Value, "DataSet1"), First(Fields!LastReceiptDate.Value, "DataSet2"))  
```  

-   <span data-ttu-id="05c90-171">A função `DatePart` retorn um valor de Inteiro que contém o componente especificado de um valor de Data fornecido. A expressão a seguir retorna o ano para o primeiro valor do SellStartDate em DataSet1.</span><span class="sxs-lookup"><span data-stu-id="05c90-171">The `DatePart` function returns an Integer value containing the specified component of a given Date value.The following expression returns the year for the first value of the SellStartDate in DataSet1.</span></span> <span data-ttu-id="05c90-172">O escopo do conjunto de dados é especificado, pois há vários conjuntos de dados no relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-172">The dataset scope is specified because there are multiple datasets in the report.</span></span>  

```  
=Datepart("yyyy", First(Fields!SellStartDate.Value, "DataSet1"))  

```  

-   <span data-ttu-id="05c90-173">A função `DateSerial` retorna um valor de Data que representa um ano, um mês e um dia especificados, com as informações de tempo definidas como meia-noite.</span><span class="sxs-lookup"><span data-stu-id="05c90-173">The `DateSerial` function returns a Date value representing a specified year, month, and day, with the time information set to midnight.</span></span> <span data-ttu-id="05c90-174">O exemplo a seguir exibe a data de término do mês anterior com base no mês atual.</span><span class="sxs-lookup"><span data-stu-id="05c90-174">The following example displays the ending date for the prior month, based on the current month.</span></span>  

```  
=DateSerial(Year(Now()), Month(Now()), "1").AddDays(-1)  
```  

-   <span data-ttu-id="05c90-175">As expressões a seguir exibem várias datas com base em um valor de parâmetro de data selecionado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="05c90-175">The following expressions display various dates based on a date parameter value selected by the user.</span></span>  

|<span data-ttu-id="05c90-176">Descrição de exemplo</span><span class="sxs-lookup"><span data-stu-id="05c90-176">Example Description</span></span>|<span data-ttu-id="05c90-177">Exemplo</span><span class="sxs-lookup"><span data-stu-id="05c90-177">Example</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="05c90-178">Ontem</span><span class="sxs-lookup"><span data-stu-id="05c90-178">Yesterday</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-1)`|  
|<span data-ttu-id="05c90-179">Dois Dias Atrás</span><span class="sxs-lookup"><span data-stu-id="05c90-179">Two Days Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-2)`|  
|<span data-ttu-id="05c90-180">Um Mês Atrás</span><span class="sxs-lookup"><span data-stu-id="05c90-180">One Month Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-1,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="05c90-181">Dois Meses Atrás</span><span class="sxs-lookup"><span data-stu-id="05c90-181">Two Months Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-2,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="05c90-182">Um Ano Atrás</span><span class="sxs-lookup"><span data-stu-id="05c90-182">One Year Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-1,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="05c90-183">Dois Anos Atrás</span><span class="sxs-lookup"><span data-stu-id="05c90-183">Two Years Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-2,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  

####  <a name="string-functions"></a><a name="StringFunctions"></a><span data-ttu-id="05c90-184">Funções de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="05c90-184">String Functions</span></span>  

-   <span data-ttu-id="05c90-185">Combine mais de um campo usando operadores de concatenação e constantes do [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05c90-185">Combine more than one field by using concatenation operators and [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] constants.</span></span> <span data-ttu-id="05c90-186">A expressão a seguir retorna dois campos, cada um em uma linha separada na mesma caixa de texto:</span><span class="sxs-lookup"><span data-stu-id="05c90-186">The following expression returns two fields, each on a separate line in the same text box:</span></span>  

```  
=Fields!FirstName.Value & vbCrLf & Fields!LastName.Value   
```  

-   <span data-ttu-id="05c90-187">Formate datas e números em uma cadeia de caracteres com a função `Format`.</span><span class="sxs-lookup"><span data-stu-id="05c90-187">Format dates and numbers in a string with the `Format` function.</span></span> <span data-ttu-id="05c90-188">A expressão a seguir exibe valores dos parâmetros *StartDate* e *EndDate* em formato de data por extenso:</span><span class="sxs-lookup"><span data-stu-id="05c90-188">The following expression displays values of the *StartDate* and *EndDate* parameters in long date format:</span></span>  

```  
=Format(Parameters!StartDate.Value, "D") & " through " &  Format(Parameters!EndDate.Value, "D")    
```  

<span data-ttu-id="05c90-189">Se a caixa de texto contiver apenas uma data ou um número, você deverá usar a propriedade Format da caixa de texto para aplicar a formatação em vez da `Format` função dentro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="05c90-189">If the text box contains only a date or number, you should use the Format property of the text box to apply formatting instead of the `Format` function within the text box.</span></span>  

-   <span data-ttu-id="05c90-190">As `Right` `Len` funções,, e `InStr` são úteis para retornar uma subcadeia de caracteres, por exemplo *DOMAIN*, aparando o nome de \\ *username* usuário do domínio apenas para o nome.</span><span class="sxs-lookup"><span data-stu-id="05c90-190">The `Right`, `Len`, and `InStr` functions are useful for returning a substring, for example, trimming *DOMAIN*\\*username* to just the user name.</span></span> <span data-ttu-id="05c90-191">A expressão a seguir retorna a parte da cadeia de caracteres à direita de um caractere de barra invertida (\\) de um parâmetro denominado *User*:</span><span class="sxs-lookup"><span data-stu-id="05c90-191">The following expression returns the part of the string to the right of a backslash (\\) character from a parameter named *User*:</span></span>  

```  
=Right(Parameters!User.Value, Len(Parameters!User.Value) - InStr(Parameters!User.Value, "\"))  
```  

<span data-ttu-id="05c90-192">A expressão a seguir resulta no mesmo valor que o anterior, usando membros da [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> classe em vez de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] funções:</span><span class="sxs-lookup"><span data-stu-id="05c90-192">The following expression results in the same value as the previous one, using members of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> class instead of [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions:</span></span>  

```  
=Parameters!User.Value.Substring(Parameters!User.Value.IndexOf("\")+1, Parameters!User.Value.Length-Parameters!User.Value.IndexOf("\")-1)  
```  

-   <span data-ttu-id="05c90-193">Exiba os valores selecionados de um parâmetro de vários valores.</span><span class="sxs-lookup"><span data-stu-id="05c90-193">Display the selected values from a multivalue parameter.</span></span> <span data-ttu-id="05c90-194">O exemplo a seguir usa a `Join` função para concatenar os valores selecionados do parâmetro *myseleções* em uma única cadeia de caracteres que pode ser definida como uma expressão para o valor de uma caixa de texto em um item de relatório:</span><span class="sxs-lookup"><span data-stu-id="05c90-194">The following example uses the `Join` function to concatenate the selected values of the parameter *MySelection* into a single string that can be set as an expression for the value of a text box in a report item:</span></span>  

```  
= Join(Parameters!MySelection.Value)  
```  

<span data-ttu-id="05c90-195">O exemplo a seguir faz o mesmo que exemplo acima, além de exibir uma cadeia de texto antes da lista de valores selecionados.</span><span class="sxs-lookup"><span data-stu-id="05c90-195">The following example does the same as the above example, as well as displays a text string prior to the list of selected values.</span></span>  

```  
="Report for " & JOIN(Parameters!MySelection.Value, " & ")  

```  

-   <span data-ttu-id="05c90-196">As `Regex` funções do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> são úteis para alterar o formato das cadeias de caracteres existentes, por exemplo, formatar um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="05c90-196">The `Regex` functions from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> are useful for changing the format of existing strings, for example, formatting a telephone number.</span></span> <span data-ttu-id="05c90-197">A expressão a seguir usa a `Replace` função para alterar o formato de um número de telefone de dez dígitos em um campo de "*nnn* - *nnn* - *nnnn*" para "(*nnn*) *nnn* - *nnnn*":</span><span class="sxs-lookup"><span data-stu-id="05c90-197">The following expression uses the `Replace` function to change the format of a ten-digit telephone number in a field from "*nnn*-*nnn*-*nnnn*" to "(*nnn*) *nnn*-*nnnn*":</span></span>  

```  
=System.Text.RegularExpressions.Regex.Replace(Fields!Phone.Value, "(\d{3})[ -.]*(\d{3})[ -.]*(\d{4})", "($1) $2-$3")  
```  

> [!NOTE]  
>  <span data-ttu-id="05c90-198">Verifique se o valor para Fields!Phone.Value não tem espaços adicionais e se é do tipo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="05c90-198">Verify that the value for Fields!Phone.Value has no extra spaces and is of type <xref:System.String>.</span></span>  

#### <a name="lookup"></a><span data-ttu-id="05c90-199">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="05c90-199">Lookup</span></span>  

-   <span data-ttu-id="05c90-200">Ao especificar um campo chave, você pode usar a função `Lookup` para recuperar um valor de um conjunto de dados para uma relação um-para-um como, por exemplo, um par de valor-chave.</span><span class="sxs-lookup"><span data-stu-id="05c90-200">By specifying a key field, you can use the `Lookup` function to retrieve a value from a dataset for a one-to-one relationship, for example, a key-value pair.</span></span> <span data-ttu-id="05c90-201">A expressão seguinte exibe o nome de produto de um conjunto de dados ("Produto"), considerando o identificador de produto para correspondência:</span><span class="sxs-lookup"><span data-stu-id="05c90-201">The following expression displays the product name from a dataset ("Product"), given the product identifier to match on:</span></span>  

```  
=Lookup(Fields!PID.Value, Fields!ProductID.Value, Fields!ProductName.Value, "Product")  
```  

#### <a name="lookupset"></a><span data-ttu-id="05c90-202">LookupSet</span><span class="sxs-lookup"><span data-stu-id="05c90-202">LookupSet</span></span>  

-   <span data-ttu-id="05c90-203">Ao especificar um campo chave, você pode usar a função `LookupSet` para recuperar um conjunto de valores de um conjunto de dados para uma relação de 1 para muitos.</span><span class="sxs-lookup"><span data-stu-id="05c90-203">By specifying a key field, you can use the `LookupSet` function to retrieve a set of values from a dataset for a one-to-many relationship.</span></span> <span data-ttu-id="05c90-204">Por exemplo, uma pessoa pode ter vários números de telefone.</span><span class="sxs-lookup"><span data-stu-id="05c90-204">For example, a person can have multiple telephone numbers.</span></span> <span data-ttu-id="05c90-205">No exemplo seguinte, suponha que o conjunto de dados PhoneList contenha um identificador de pessoa e um número de telefone em cada linha.</span><span class="sxs-lookup"><span data-stu-id="05c90-205">In the following example, assume the dataset PhoneList contains a person identifier and a telephone number in each row.</span></span> <span data-ttu-id="05c90-206">`LookupSet` retorna uma matriz de valores.</span><span class="sxs-lookup"><span data-stu-id="05c90-206">`LookupSet` returns an array of values.</span></span> <span data-ttu-id="05c90-207">A seguinte expressão combina os valores de retorno em uma única cadeia de caracteres e exibe a lista de números de telefone para a pessoa especificada por ContactID:</span><span class="sxs-lookup"><span data-stu-id="05c90-207">The following expression combines the return values into a single string and displays the list of telephone numbers for the person specified by ContactID:</span></span>  

```  
=Join(LookupSet(Fields!ContactID.Value, Fields!PersonID.Value, Fields!PhoneNumber.Value, "PhoneList"),",")  
```  

####  <a name="conversion-functions"></a><a name="ConversionFunctions"></a><span data-ttu-id="05c90-208">Funções de conversão</span><span class="sxs-lookup"><span data-stu-id="05c90-208">Conversion Functions</span></span>  
<span data-ttu-id="05c90-209">É possível usar as funções do [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] para converter um campo de um tipo de dados em outro tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="05c90-209">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to convert a field from the one data type to a different data type.</span></span> <span data-ttu-id="05c90-210">As funções de conversão podem ser usadas para converter um tipo de dados padrão de um campo no tipo de dados necessário para cálculos ou para combinar texto.</span><span class="sxs-lookup"><span data-stu-id="05c90-210">Conversion functions can be used to convert the default data type for a field to the data type needed for calculations or to combine text.</span></span>  

-   <span data-ttu-id="05c90-211">A expressão a seguir converte a constante 500 para o tipo Decimal a fim de compará-la a um tipo de dados de dinheiro [!INCLUDE[tsql](../../includes/tsql-md.md)] no campo Valor de uma expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="05c90-211">The following expression converts the constant 500 to type Decimal in order to compare it to a [!INCLUDE[tsql](../../includes/tsql-md.md)] money data type in the Value field for a filter expression.</span></span>  

```  
=CDec(500)  
```  

-   <span data-ttu-id="05c90-212">A expressão a seguir exibe o número de valores selecionados para o parâmetro de diversos valores *MySelection*.</span><span class="sxs-lookup"><span data-stu-id="05c90-212">The following expression displays the number of values selected for the multivalue parameter *MySelection*.</span></span>  

```  
=CStr(Parameters!MySelection.Count)  
```  

####  <a name="decision-functions"></a><a name="DecisionFunctions"></a> <span data-ttu-id="05c90-213">Funções de decisão</span><span class="sxs-lookup"><span data-stu-id="05c90-213">Decision Functions</span></span>  

-   <span data-ttu-id="05c90-214">A função `Iif` retorna um de dois valores, dependendo da expressão ser verdadeira ou não.</span><span class="sxs-lookup"><span data-stu-id="05c90-214">The `Iif` function returns one of two values depending on whether the expression is true or not.</span></span> <span data-ttu-id="05c90-215">A expressão a seguir usa a função `Iif` para retornar um valor booliano de `True` se o valor de `LineTotal` exceder 100.</span><span class="sxs-lookup"><span data-stu-id="05c90-215">The following expression uses the `Iif` function to return a Boolean value of `True` if the value of `LineTotal` exceeds 100.</span></span> <span data-ttu-id="05c90-216">Caso contrário, ele retornará `False`:</span><span class="sxs-lookup"><span data-stu-id="05c90-216">Otherwise it returns `False`:</span></span>  

```  
=IIF(Fields!LineTotal.Value > 100, True, False)  
```  

-   <span data-ttu-id="05c90-217">Use várias funções `IIF` (também conhecidas como "IIFs aninhadas") para retornar um de três valores, dependendo do valor de `PctComplete`.</span><span class="sxs-lookup"><span data-stu-id="05c90-217">Use multiple `IIF` functions (also known as "nested IIFs") to return one of three values depending on the value of `PctComplete`.</span></span> <span data-ttu-id="05c90-218">A expressão a seguir pode ser colocada na cor de preenchimento de uma caixa de texto para alterar a cor de plano de fundo, dependendo do valor na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="05c90-218">The following expression can be placed in the fill color of a text box to change the background color depending on the value in the text box.</span></span>  

```  
=IIF(Fields!PctComplete.Value >= 10, "Green", IIF(Fields!PctComplete.Value >= 1, "Blue", "Red"))  
```  

<span data-ttu-id="05c90-219">Valores maiores ou iguais a 10 são exibidos com um plano de fundo verde, entre 1 e 9 são exibidos com um plano de fundo azul e menores do que 1 são exibidos com um plano de fundo vermelho.</span><span class="sxs-lookup"><span data-stu-id="05c90-219">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, and less than 1 display with a red background.</span></span>  

-   <span data-ttu-id="05c90-220">Uma maneira diferente de obter a mesma funcionalidade é usar a função `Switch`.</span><span class="sxs-lookup"><span data-stu-id="05c90-220">A different way to get the same functionality uses the `Switch` function.</span></span> <span data-ttu-id="05c90-221">A função `Switch` é útil quando você tem três ou mais condições a serem testadas.</span><span class="sxs-lookup"><span data-stu-id="05c90-221">The `Switch` function is useful when you have three or more conditions to test.</span></span> <span data-ttu-id="05c90-222">A função `Switch` retorna o valor associado à primeira expressão em uma série avaliada como verdadeira:</span><span class="sxs-lookup"><span data-stu-id="05c90-222">The `Switch` function returns the value associated with the first expression in a series that evaluates to true:</span></span>  

```  
=Switch(Fields!PctComplete.Value >= 10, "Green", Fields!PctComplete.Value >= 1, "Blue", Fields!PctComplete.Value = 1, "Yellow", Fields!PctComplete.Value <= 0, "Red",)  
```  

<span data-ttu-id="05c90-223">Valores maiores ou iguais a 10 são exibidos com um plano de fundo verde, entre 1 e 9 são exibidos com um plano de fundo azul, iguais a 1 são exibidos com um plano de fundo amarelo e 0 ou menos são exibidos com um plano de fundo vermelho.</span><span class="sxs-lookup"><span data-stu-id="05c90-223">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, equal to 1 display with a yellow background, and 0 or less display with a red background.</span></span>  

-   <span data-ttu-id="05c90-224">Teste o valor do campo `ImportantDate` e retorne "Vermelho", se ele tiver mais de uma semana, caso contrário, "Azul".</span><span class="sxs-lookup"><span data-stu-id="05c90-224">Test the value of the `ImportantDate` field and return "Red" if it is more than a week old, and "Blue" otherwise.</span></span> <span data-ttu-id="05c90-225">Esta expressão pode ser usada para controlar a propriedade Cor de uma caixa de texto em um item de relatório:</span><span class="sxs-lookup"><span data-stu-id="05c90-225">This expression can be used to control the Color property of a text box in a report item:</span></span>  

```  
=IIF(DateDiff("d",Fields!ImportantDate.Value, Now())>7,"Red","Blue")  
```  

-   <span data-ttu-id="05c90-226">Teste o valor do campo `PhoneNumber` e retorne "Sem valor", se ele for `null` (`Nothing` no [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]); caso contrário retorne o valor do número do telefone.</span><span class="sxs-lookup"><span data-stu-id="05c90-226">Test the value of the `PhoneNumber` field and return "No Value" if it is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]); otherwise return the phone number value.</span></span> <span data-ttu-id="05c90-227">Esta expressão pode ser usada para controlar o valor de uma caixa de texto em um item de relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-227">This expression can be used to control the value of a text box in a report item.</span></span>  

```  
=IIF(Fields!PhoneNumber.Value Is Nothing,"No Value",Fields!PhoneNumber.Value)  
```  

-   <span data-ttu-id="05c90-228">Teste o valor do campo `Department` e retorne o nome de um sub-relatório ou um `null` (`Nothing` no [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="05c90-228">Test the value of the `Department` field and return either a subreport name or a `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="05c90-229">Esta expressão pode ser usada para sub-relatórios detalhados condicional.</span><span class="sxs-lookup"><span data-stu-id="05c90-229">This expression can be used for conditional drillthrough subreports.</span></span>  

```  
=IIF(Fields!Department.Value = "Development", "EmployeeReport", Nothing)  
```  

-   <span data-ttu-id="05c90-230">Teste se o valor de um campo é nulo.</span><span class="sxs-lookup"><span data-stu-id="05c90-230">Test if a field value is null.</span></span> <span data-ttu-id="05c90-231">Esta expressão pode ser usada para controlar a propriedade `Hidden` de um item de relatório de imagem.</span><span class="sxs-lookup"><span data-stu-id="05c90-231">This expression can be used to control the `Hidden` property of an image report item.</span></span> <span data-ttu-id="05c90-232">No exemplo a seguir, a imagem especificada pelo campo [LargePhoto] será exibida apenas se o valor do campo não for nulo.</span><span class="sxs-lookup"><span data-stu-id="05c90-232">In the following example, the image specified by the field [LargePhoto] is displayed only if the value of the field is not null.</span></span>  

```  
=IIF(IsNothing(Fields!LargePhoto.Value),True,False)  
```  

-   <span data-ttu-id="05c90-233">A função `MonthName` retorna um valor de cadeia de caracteres que contém o nome do mês especificado.</span><span class="sxs-lookup"><span data-stu-id="05c90-233">The `MonthName` function returns a string value containing the name of the specified month.</span></span> <span data-ttu-id="05c90-234">O exemplo a seguir exibe NA no campo Mês quando o campo contiver o valor de 0.</span><span class="sxs-lookup"><span data-stu-id="05c90-234">The following example displays NA in the Month field when the field contains the value of 0.</span></span>  

```  
IIF(Fields!Month.Value=0,"NA",MonthName(IIF(Fields!Month.Value=0,1,Fields!Month.Value)))  

```  

###  <a name="report-functions"></a><a name="ReportFunctions"></a> <span data-ttu-id="05c90-235">Funções de relatórios</span><span class="sxs-lookup"><span data-stu-id="05c90-235">Report Functions</span></span>  
<span data-ttu-id="05c90-236">Em uma expressão, você pode adicionar uma referência a funções de relatório adicionais que manipulam dados em um relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-236">In an expression, you can add a reference to additional report functions that manipulate data in a report.</span></span> <span data-ttu-id="05c90-237">Esta seção fornece exemplos de duas dessas funções.</span><span class="sxs-lookup"><span data-stu-id="05c90-237">This section provides examples for two of these functions.</span></span> <span data-ttu-id="05c90-238">Para obter mais informações sobre as funções e exemplos de relatório, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-238">For more information about report functions and examples, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  

#####  <a name="sum"></a><a name="Sum"></a><span data-ttu-id="05c90-239">Quantia</span><span class="sxs-lookup"><span data-stu-id="05c90-239">Sum</span></span>  

-   <span data-ttu-id="05c90-240">A função `Sum` pode somar os valores em um grupo ou região de dados.</span><span class="sxs-lookup"><span data-stu-id="05c90-240">The `Sum` function can total the values in a group or data region.</span></span> <span data-ttu-id="05c90-241">Essa função pode ser útil no cabeçalho ou no rodapé de um grupo.</span><span class="sxs-lookup"><span data-stu-id="05c90-241">This function can be useful in the header or footer of a group.</span></span> <span data-ttu-id="05c90-242">A expressão a seguir exibe a soma de dados no grupo Ordem ou na região de dados:</span><span class="sxs-lookup"><span data-stu-id="05c90-242">The following expression displays the sum of data in the Order group or data region:</span></span>  

```  
=Sum(Fields!LineTotal.Value, "Order")  
```  

-   <span data-ttu-id="05c90-243">Você também pode usar a função `Sum` para cálculos de agregação condicionais.</span><span class="sxs-lookup"><span data-stu-id="05c90-243">You can also use the `Sum` function for conditional aggregate calculations.</span></span> <span data-ttu-id="05c90-244">Por exemplo, se um conjunto de dados tiver um campo denominado Estado com valores possíveis Não Iniciado, Iniciado, Concluído, a seguinte expressão, quando colocada em um cabeçalho do grupo, calculará a soma de agregação apenas para o valor Concluído:</span><span class="sxs-lookup"><span data-stu-id="05c90-244">For example, if a dataset has a field that is named State with possible values Not Started, Started, Finished, the following expression, when placed in a group header, calculates the aggregate sum for only the value Finished:</span></span>  

```  
=Sum(IIF(Fields!State.Value = "Finished", 1, 0))  
```  

#####  <a name="rownumber"></a><a name="RowNumber"></a><span data-ttu-id="05c90-245">RowNumber</span><span class="sxs-lookup"><span data-stu-id="05c90-245">RowNumber</span></span>  

-   <span data-ttu-id="05c90-246">A função `RowNumber`, quando usada em uma caixa de texto dentro de uma região de dados, exibe o número da linha de cada instância da caixa de texto na qual a expressão é exibida.</span><span class="sxs-lookup"><span data-stu-id="05c90-246">The `RowNumber` function, when used in a text box within a data region, displays the row number for each instance of the text box in which the expression appears.</span></span> <span data-ttu-id="05c90-247">Essa função pode ser útil para numerar linhas em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="05c90-247">This function can be useful to number rows in a table.</span></span> <span data-ttu-id="05c90-248">Ela também pode ser útil para tarefas mais complexas, como fornecer quebras de página baseadas no número de linhas.</span><span class="sxs-lookup"><span data-stu-id="05c90-248">It can also be useful for more complex tasks, such as providing page breaks based on number of rows.</span></span> <span data-ttu-id="05c90-249">Para obter mais informações, consulte [Quebras de página](#PageBreaks) neste tópico.</span><span class="sxs-lookup"><span data-stu-id="05c90-249">For more information, see [Page Breaks](#PageBreaks) in this topic.</span></span>  

<span data-ttu-id="05c90-250">O escopo especificado para `RowNumber` controla quando a renumeração é iniciada.</span><span class="sxs-lookup"><span data-stu-id="05c90-250">The scope you specify for `RowNumber` controls when renumbering begins.</span></span> <span data-ttu-id="05c90-251">A palavra-chave `Nothing` indica que a função iniciará a contagem na primeira linha da região de dados mais externa.</span><span class="sxs-lookup"><span data-stu-id="05c90-251">The `Nothing` keyword indicates that the function will start counting at the first row in the outermost data region.</span></span> <span data-ttu-id="05c90-252">Para iniciar a contagem dentro de regiões de dados aninhadas, use o nome da região de dados.</span><span class="sxs-lookup"><span data-stu-id="05c90-252">To start counting within nested data regions, use the name of the data region.</span></span> <span data-ttu-id="05c90-253">Para iniciar a contagem dentro de um grupo, use o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="05c90-253">To start counting within a group, use the name of the group.</span></span>  

```  
=RowNumber(Nothing)  
```  

##  <a name="appearance-of-report-data"></a><a name="AppearanceofReportData"></a> <span data-ttu-id="05c90-254">Aparência dos dados do relatório</span><span class="sxs-lookup"><span data-stu-id="05c90-254">Appearance of Report Data</span></span>  
<span data-ttu-id="05c90-255">É possível usar expressões para manipular como os dados são exibidos em um relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-255">You can use expressions to manipulate how data appears on a report.</span></span> <span data-ttu-id="05c90-256">Por exemplo, é possível exibir os valores de dois campos em uma única caixa de texto, exibir informações sobre o relatório ou afetar o modo como as quebras de página são inseridas no relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-256">For example, you can display the values of two fields in a single text box, display information about the report, or affect how page breaks are inserted in the report.</span></span>  

###  <a name="page-headers-and-footers"></a><a name="PageHeadersandFooters"></a><span data-ttu-id="05c90-257">Cabeçalhos e rodapés de página</span><span class="sxs-lookup"><span data-stu-id="05c90-257">Page Headers and Footers</span></span>  
<span data-ttu-id="05c90-258">Ao criar um relatório, você pode exibir o nome do relatório e o número da página no rodapé.</span><span class="sxs-lookup"><span data-stu-id="05c90-258">When designing a report, you may want to display the name of the report and page number in the report footer.</span></span> <span data-ttu-id="05c90-259">Para fazer isso, você pode usar as expressões a seguir:</span><span class="sxs-lookup"><span data-stu-id="05c90-259">To do this, you can use the following expressions:</span></span>  

-   <span data-ttu-id="05c90-260">A seguinte expressão fornece o nome do relatório e a hora em que foi executado.</span><span class="sxs-lookup"><span data-stu-id="05c90-260">The following expression provides the name of the report and the time it was run.</span></span> <span data-ttu-id="05c90-261">Ela pode ser colocada em uma caixa de texto no rodapé ou no corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-261">It can be placed in a text box in the report footer or in the body of the report.</span></span> <span data-ttu-id="05c90-262">A hora é formatada com a cadeia de caracteres de formatação do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para data abreviada:</span><span class="sxs-lookup"><span data-stu-id="05c90-262">The time is formatted with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] formatting string for short date:</span></span>  

```  
=Globals.ReportName & ", dated " & Format(Globals.ExecutionTime, "d")  
```  

-   <span data-ttu-id="05c90-263">A seguinte expressão, colocada em uma caixa de texto no rodapé de um relatório, fornece o número da página e o total de páginas no relatório:</span><span class="sxs-lookup"><span data-stu-id="05c90-263">The following expression, placed in a text box in the footer of a report, provides page number and total pages in the report:</span></span>  

```  
=Globals.PageNumber & " of " & Globals.TotalPages  
```  

<span data-ttu-id="05c90-264">Os exemplos a seguir descrevem como exibir os primeiros e os últimos valores de uma página no cabeçalho da página, semelhante ao que você pode encontrar em uma listagem de diretório.</span><span class="sxs-lookup"><span data-stu-id="05c90-264">The following examples describe how to display the first and last values from a page in the page header, similar to what you might find in a directory listing.</span></span> <span data-ttu-id="05c90-265">O exemplo pressupõe uma região de dados que contém uma caixa de texto denominada `LastName`.</span><span class="sxs-lookup"><span data-stu-id="05c90-265">The example assumes a data region that contains a text box named `LastName`.</span></span>  

-   <span data-ttu-id="05c90-266">A expressão a seguir, colocada em uma caixa de texto no lado esquerdo do cabeçalho da página, fornece o primeiro valor da caixa de texto `LastName` na página:</span><span class="sxs-lookup"><span data-stu-id="05c90-266">The following expression, placed in a text box on the left side of the page header, provides the first value of the `LastName` text box on the page:</span></span>  

```  
=First(ReportItems("LastName").Value)  
```  

-   <span data-ttu-id="05c90-267">A expressão a seguir, colocada em uma caixa de texto no lado direito do cabeçalho da página, fornece o último valor da caixa de texto `LastName` na página:</span><span class="sxs-lookup"><span data-stu-id="05c90-267">The following expression, placed in a text box on the right side of the page header, provides the last value of the `LastName` text box on the page:</span></span>  

```  
=Last(ReportItems("LastName").Value)  
```  

<span data-ttu-id="05c90-268">O exemplo a seguir descreve como exibir um total de páginas.</span><span class="sxs-lookup"><span data-stu-id="05c90-268">The following example describes how to display a page total.</span></span> <span data-ttu-id="05c90-269">O exemplo pressupõe uma região de dados que contém uma caixa de texto denominada `Cost`.</span><span class="sxs-lookup"><span data-stu-id="05c90-269">The example assumes a data region that contains a text box named `Cost`.</span></span>  

-   <span data-ttu-id="05c90-270">A expressão a seguir, colocada no cabeçalho ou no rodapé de página, fornece a soma dos valores na caixa de texto `Cost` da página:</span><span class="sxs-lookup"><span data-stu-id="05c90-270">The following expression, placed in the page header or footer, provides the sum of the values in the `Cost` text box for the page:</span></span>  

```  
=Sum(ReportItems("Cost").Value)  
```  

> [!NOTE]  
>  <span data-ttu-id="05c90-271">Você pode fazer referência a apenas um item de relatório por expressão em um cabeçalho ou rodapé de página.</span><span class="sxs-lookup"><span data-stu-id="05c90-271">You can refer to only one report item per expression in a page header or footer.</span></span> <span data-ttu-id="05c90-272">Além disso, é possível fazer referência ao nome da caixa de texto, mas não à expressão de dados reais dentro da caixa de texto, nas expressões de cabeçalho e rodapé de página.</span><span class="sxs-lookup"><span data-stu-id="05c90-272">Also, you can refer to the text box name, but not the actual data expression within the text box, in page header and footer expressions.</span></span>  

###  <a name="page-breaks"></a><a name="PageBreaks"></a> <span data-ttu-id="05c90-273">Quebras de página</span><span class="sxs-lookup"><span data-stu-id="05c90-273">Page Breaks</span></span>  
<span data-ttu-id="05c90-274">Em alguns relatórios, você pode desejar colocar uma quebra de página no final de um número de linhas especificado ou, além disso, em grupos ou itens de relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-274">In some reports, you may want to place a page break at the end of a specified number of rows instead of, or in addition to, on groups or report items.</span></span> <span data-ttu-id="05c90-275">Para fazer isso, crie um grupo que contenha os grupos ou registros de detalhes desejados, adicione uma quebra de página ao grupo e adicione uma expressão de grupo ao grupo por um número de linhas especificado.</span><span class="sxs-lookup"><span data-stu-id="05c90-275">To do this, create a group that contains the groups or detail records you want, add a page break to the group, and then add a group expression to group by a specified number of rows.</span></span>  

-   <span data-ttu-id="05c90-276">A expressão a seguir, quando colocada na expressão de grupo, atribui um número para cada conjunto de 25 linhas.</span><span class="sxs-lookup"><span data-stu-id="05c90-276">The following expression, when placed in the group expression, assigns a number to each set of 25 rows.</span></span> <span data-ttu-id="05c90-277">Quando uma quebra de página é definida para o grupo, essa expressão resulta em uma quebra de página a cada 25 linhas.</span><span class="sxs-lookup"><span data-stu-id="05c90-277">When a page break is defined for the group, this expression results in a page break every 25 rows.</span></span>  

```  
=Ceiling(RowNumber(Nothing)/25)  
```  

<span data-ttu-id="05c90-278">Para permitir que o usuário defina um valor para o número de linhas por página, crie um parâmetro denominado `RowsPerPage` e baseie a expressão de grupo no parâmetro, conforme mostrado na expressão a seguir:</span><span class="sxs-lookup"><span data-stu-id="05c90-278">To allow the user to set a value for the number of rows per page, create a parameter named `RowsPerPage` and base the group expression on the parameter, as shown in the following expression:</span></span>  

```  
=Ceiling(RowNumber(Nothing)/Parameters!RowsPerPage.Value)  
```  

<span data-ttu-id="05c90-279">Para obter mais informações sobre como configurar quebras de página para um grupo, consulte [Adicionar uma quebra de página &#40;Construtor de Relatórios e SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-279">For more information about setting page breaks for a group, see [Add a Page Break &#40;Report Builder and SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span></span>  

##  <a name="properties"></a><a name="Properties"></a> <span data-ttu-id="05c90-280">Propriedades</span><span class="sxs-lookup"><span data-stu-id="05c90-280">Properties</span></span>  
<span data-ttu-id="05c90-281">As expressões não são usadas apenas para exibir dados nas caixas de texto.</span><span class="sxs-lookup"><span data-stu-id="05c90-281">Expressions are not only used to display data in text boxes.</span></span> <span data-ttu-id="05c90-282">Elas também podem ser usadas para alterar o modo como as propriedades são aplicadas aos itens do relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-282">They can also be used to change how properties are applied to report items.</span></span> <span data-ttu-id="05c90-283">É possível alterar informações de estilo para um item de relatório ou alterar sua visibilidade.</span><span class="sxs-lookup"><span data-stu-id="05c90-283">You can change style information for a report item, or change its visibility.</span></span>  

###  <a name="formatting"></a><a name="Formatting"></a><span data-ttu-id="05c90-284">Formatação</span><span class="sxs-lookup"><span data-stu-id="05c90-284">Formatting</span></span>  

-   <span data-ttu-id="05c90-285">A expressão a seguir, quando usada na propriedade Color de uma caixa de texto, altera a cor do texto dependendo do valor do campo `Profit` :</span><span class="sxs-lookup"><span data-stu-id="05c90-285">The following expression, when used in the Color property of a text box, changes the color of the text depending on the value of the `Profit` field:</span></span>  

```  
=Iif(Fields!Profit.Value < 0, "Red", "Black")  
```  

<span data-ttu-id="05c90-286">Você também pode usar a variável de objeto [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] do `Me`.</span><span class="sxs-lookup"><span data-stu-id="05c90-286">You can also use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] object variable `Me`.</span></span> <span data-ttu-id="05c90-287">Essa variável é outra maneira de fazer referência ao valor de uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="05c90-287">This variable is another way of referring to the value of a text box.</span></span>  

`=Iif(Me.Value < 0, "Red", "Black")`  

-   <span data-ttu-id="05c90-288">A expressão a seguir, quando usada na propriedade BackgroundColor de um item de relatório em uma região de dados, alterna a cor da tela de fundo de cada linha entre verde claro e branco:</span><span class="sxs-lookup"><span data-stu-id="05c90-288">The following expression, when used in the BackgroundColor property of a report item in a data region, alternates the background color of each row between pale green and white:</span></span>  

```  
=Iif(RowNumber(Nothing) Mod 2, "PaleGreen", "White")  
```  

<span data-ttu-id="05c90-289">Se você estiver usando uma expressão para um escopo especificado, poderá precisar indicar o conjunto de dados para a função de agregação:</span><span class="sxs-lookup"><span data-stu-id="05c90-289">If you are using an expression for a specified scope, you may have to indicate the dataset for the aggregate function:</span></span>  

```  
=Iif(RowNumber("Employees") Mod 2, "PaleGreen", "White")  
```  

> [!NOTE]  
>  <span data-ttu-id="05c90-290">As cores disponíveis são provenientes da enumeração de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] KnownColor.</span><span class="sxs-lookup"><span data-stu-id="05c90-290">Available colors come from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] KnownColor enumeration.</span></span>  

### <a name="chart-colors"></a><span data-ttu-id="05c90-291">Cores dos gráficos</span><span class="sxs-lookup"><span data-stu-id="05c90-291">Chart Colors</span></span>  
<span data-ttu-id="05c90-292">Para especificar cores para um gráfico de Forma, você pode usar código personalizado para controlar a ordem em que as cores são mapeadas para valores de pontos de dados.</span><span class="sxs-lookup"><span data-stu-id="05c90-292">To specify colors for a Shape chart, you can use custom code to control the order that colors are mapped to data point values.</span></span> <span data-ttu-id="05c90-293">Isso ajuda a usar cores consistentes para vários gráficos que têm os mesmos grupos de categorias.</span><span class="sxs-lookup"><span data-stu-id="05c90-293">This helps you use consistent colors for multiple charts that have the same category groups.</span></span> <span data-ttu-id="05c90-294">Para obter mais informações, consulte [Especificar cores consistentes em gráficos com várias formas &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-294">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  

###  <a name="visibility"></a><a name="Visibility"></a><span data-ttu-id="05c90-295">Visualizar</span><span class="sxs-lookup"><span data-stu-id="05c90-295">Visibility</span></span>  
<span data-ttu-id="05c90-296">Você pode mostrar e ocultar itens em um relatório usando as propriedades de visibilidade para o item de relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-296">You can show and hide items in a report using the visibility properties for the report item.</span></span> <span data-ttu-id="05c90-297">Em uma região de dados, como uma tabela, é possível ocultar inicialmente as linhas de detalhes com base no valor de uma expressão.</span><span class="sxs-lookup"><span data-stu-id="05c90-297">In a data region such as a table, you can initially hide detail rows based on the value in an expression.</span></span>  

-   <span data-ttu-id="05c90-298">A expressão a seguir, quando usada para visibilidade inicial de linhas de detalhes em um grupo, mostra as linhas de detalhes de todas as vendas que excedem 90 por cento no campo `PctQuota` :</span><span class="sxs-lookup"><span data-stu-id="05c90-298">The following expression, when used for initial visibility of detail rows in a group, shows the detail rows for all sales exceeding 90 percent in the `PctQuota` field:</span></span>  

```  
=Iif(Fields!PctQuota.Value>.9, False, True)  
```  

-   <span data-ttu-id="05c90-299">A expressão a seguir, quando definida na propriedade Hidden de uma tabela, mostrará a tabela apenas se ela tiver mais de 12 linhas:</span><span class="sxs-lookup"><span data-stu-id="05c90-299">The following expression, when set in the Hidden property of a table, shows the table only if it has more than 12 rows:</span></span>  

```  
=IIF(CountRows()>12,false,true)  
```  

-   <span data-ttu-id="05c90-300">A expressão a seguir, quando definida na `Hidden` propriedade de uma coluna, mostrará a coluna somente se o campo existir no conjunto de dados do relatório depois que eles forem recuperados da fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="05c90-300">The following expression, when set in the `Hidden` property of a column, shows the column only if the field exists in the report dataset after the data is retrieved from the data source:</span></span>  

```  
=IIF(Fields!Column_1.IsMissing, true, false)  
```  

###  <a name="urls"></a><a name="Hyperlinks"></a><span data-ttu-id="05c90-301">URLs</span><span class="sxs-lookup"><span data-stu-id="05c90-301">URLs</span></span>  
<span data-ttu-id="05c90-302">É possível personalizar URLs usando dados do relatório e também controlar condicionalmente se as URLs são adicionadas como uma ação para uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="05c90-302">You can customize URLs by using report data and also conditionally control whether URLs are added as an action for a text box.</span></span>  

-   <span data-ttu-id="05c90-303">A expressão a seguir, quando usada como uma ação em uma caixa de texto, gera uma URL personalizada que especifica o campo do conjunto de dados `EmployeeID` como um parâmetro da URL.</span><span class="sxs-lookup"><span data-stu-id="05c90-303">The following expression, when used as an action on a text box, generates a customized URL that specifies the dataset field `EmployeeID` as a URL parameter.</span></span>  

```  
="http://adventure-works/MyInfo?ID=" & Fields!EmployeeID.Value  
```  

<span data-ttu-id="05c90-304">Para obter mais informações, consulte [Adicionar um hiperlink a uma URL &#40;Construtor de Relatórios e SSRS&#41;](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-304">For more information, see [Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span></span>  

-   <span data-ttu-id="05c90-305">A expressão a seguir controla condicionalmente se uma URL deve ser adicionada em uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="05c90-305">The following expression conditionally controls whether to add a URL in a text box.</span></span> <span data-ttu-id="05c90-306">Essa expressão depende de um parâmetro denominado `IncludeURLs` que permite que um usuário decida se deve incluir URLs ativas em um relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-306">This expression depends on a parameter named `IncludeURLs` that allows a user to decide whether to include active URLs in a report.</span></span> <span data-ttu-id="05c90-307">Essa expressão é definida como uma ação em uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="05c90-307">This expression is set as an action on a text box.</span></span> <span data-ttu-id="05c90-308">Configurando o parâmetro como Falso e exibindo o relatório, você pode exportar o relatório Microsoft Excel sem hiperlinks.</span><span class="sxs-lookup"><span data-stu-id="05c90-308">By setting the parameter to False and then viewing the report, you can export the report Microsoft Excel without hyperlinks.</span></span>  

```  
=IIF(Parameters!IncludeURLs.Value,"http://adventure-works.com/productcatalog",Nothing)  
```  

##  <a name="report-data"></a><a name="ReportData"></a><span data-ttu-id="05c90-309">Dados do relatório</span><span class="sxs-lookup"><span data-stu-id="05c90-309">Report Data</span></span>  
<span data-ttu-id="05c90-310">As expressões podem ser usadas para manipular os dados usados no relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-310">Expressions can be used to manipulate the data that is used in the report.</span></span> <span data-ttu-id="05c90-311">Você pode fazer referência a parâmetros e a outras informações do relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-311">You can refer to parameters and other report information.</span></span> <span data-ttu-id="05c90-312">É possível até mesmo alterar a consulta usada para recuperar dados para o relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-312">You can even change the query that is used to retrieve data for the report.</span></span>  

###  <a name="parameters"></a><a name="Parameters"></a> <span data-ttu-id="05c90-313">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="05c90-313">Parameters</span></span>  
<span data-ttu-id="05c90-314">É possível usar expressões em um parâmetro para variar o valor padrão do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="05c90-314">You can use expressions in a parameter to vary the default value for the parameter.</span></span> <span data-ttu-id="05c90-315">Por exemplo, você pode usar um parâmetro para filtrar dados para um usuário específico baseado na ID do usuário usada para executar o relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-315">For example, you can use a parameter to filter data to a particular user based on the user ID that is used to run the report.</span></span>  

-   <span data-ttu-id="05c90-316">A expressão a seguir, quando usada com o valor padrão para um parâmetro, coleta a ID do usuário da pessoa que executa o relatório:</span><span class="sxs-lookup"><span data-stu-id="05c90-316">The following expression, when used as the default value for a parameter, collects the user ID of the person running the report:</span></span>  

```  
=User!UserID  
```  

-   <span data-ttu-id="05c90-317">Para consultar um parâmetro em um parâmetro de consulta, expressão de filtro, caixa de texto ou outra área do relatório, use a coleção global de `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="05c90-317">To refer to a parameter in a query parameter, filter expression, text box, or other area of the report, use the `Parameters` global collection.</span></span> <span data-ttu-id="05c90-318">Este exemplo supõe que o parâmetro é denominado *Department*:</span><span class="sxs-lookup"><span data-stu-id="05c90-318">This example assumes that the parameter is named *Department*:</span></span>  

```  
=Parameters!Department.Value  
```  

-   <span data-ttu-id="05c90-319">Parâmetros podem ser criados em um relatório, mas definidos como ocultos.</span><span class="sxs-lookup"><span data-stu-id="05c90-319">Parameters can be created in a report but set to hidden.</span></span> <span data-ttu-id="05c90-320">Quando o relatório é executado no servidor de relatório, o parâmetro não é exibido na barra de ferramentas e o leitor de relatório não pode alterar o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="05c90-320">When the report runs on the report server, the parameter does not appear in the toolbar and the report reader cannot change the default value.</span></span> <span data-ttu-id="05c90-321">É possível usar um parâmetro oculto, definido como um valor padrão, como uma constante personalizada.</span><span class="sxs-lookup"><span data-stu-id="05c90-321">You can use a hidden parameter set to a default value as custom constant.</span></span> <span data-ttu-id="05c90-322">É possível usar esse valor em qualquer expressão, incluindo uma expressão de campo.</span><span class="sxs-lookup"><span data-stu-id="05c90-322">You can use this value in any expression, including a field expression.</span></span> <span data-ttu-id="05c90-323">A expressão a seguir identifica o campo especificado pelo valor do parâmetro padrão para o parâmetro denominado *ParameterField*:</span><span class="sxs-lookup"><span data-stu-id="05c90-323">The following expression identifies the field specified by the default parameter value for the parameter named *ParameterField*:</span></span>  

```  
=Fields(Parameters!ParameterField.Value).Value  
```  

## <a name="custom-code"></a><a name="CustomCode"></a><span data-ttu-id="05c90-324">Código personalizado</span><span class="sxs-lookup"><span data-stu-id="05c90-324">Custom Code</span></span>

<span data-ttu-id="05c90-325">É possível usar código personalizado em um relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-325">You can use custom code in a report.</span></span> <span data-ttu-id="05c90-326">O código personalizado é inserido em um relatório ou armazenado em um assembly personalizado que é usado no relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-326">Custom code is either embedded in a report or stored in a custom assembly which is used in the report.</span></span> <span data-ttu-id="05c90-327">Para obter mais informações sobre o código personalizado, consulte [Referências a código personalizado e assemblies em expressões no Designer de Relatórios &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-327">For more information about custom code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  

### <a name="using-group-variables-for-custom-aggregation"></a><span data-ttu-id="05c90-328">Usando variáveis de grupo para agregação personalizada</span><span class="sxs-lookup"><span data-stu-id="05c90-328">Using Group Variables for Custom Aggregation</span></span>

<span data-ttu-id="05c90-329">Você pode inicializar o valor para uma variável de grupo que é local para um escopo de grupo específico e depois incluir uma referência a essa variável nas expressões.</span><span class="sxs-lookup"><span data-stu-id="05c90-329">You can initialize the value for a group variable that is local to a particular group scope and then include a reference to that variable in expressions.</span></span> <span data-ttu-id="05c90-330">Um dos modos pelos quais é possível usar uma variável de grupo com código personalizado é implementar uma agregação personalizada.</span><span class="sxs-lookup"><span data-stu-id="05c90-330">One of the ways that you can use a group variable with custom code is to implement a custom aggregate.</span></span> <span data-ttu-id="05c90-331">Para obter mais informações, consulte [Usando variáveis de grupo no Reporting Services 2008 para agregação personalizada](https://go.microsoft.com/fwlink/?LinkId=128714).</span><span class="sxs-lookup"><span data-stu-id="05c90-331">For more information, see [Using Group Variables in Reporting Services 2008 for Custom Aggregation](https://go.microsoft.com/fwlink/?LinkId=128714).</span></span>  

<span data-ttu-id="05c90-332">Para obter mais informações sobre as variáveis, consulte [Referências de coleções de variáveis de grupo e de relatório &#40;Construtor de Relatórios e SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="05c90-332">For more information about variables, see [Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md).</span></span>  

## <a name="suppressing-null-or-zero-values-at-run-time"></a><span data-ttu-id="05c90-333">Suprimindo valores nulos ou zero em tempo de execução</span><span class="sxs-lookup"><span data-stu-id="05c90-333">Suppressing Null or Zero Values at Run Time</span></span>

<span data-ttu-id="05c90-334">Alguns valores em uma expressão podem ser avaliados como nulos ou indefinidos na hora do processamento do relatório.</span><span class="sxs-lookup"><span data-stu-id="05c90-334">Some values in an expression can evaluate to null or undefined at report processing time.</span></span> <span data-ttu-id="05c90-335">Isso pode criar erros de tempo de execução que resultam em **#Erro** exibidos na caixa de texto em vez da expressão avaliada.</span><span class="sxs-lookup"><span data-stu-id="05c90-335">This can create run-time errors that result in **#Error** displaying in the text box instead of the evaluated expression.</span></span> <span data-ttu-id="05c90-336">A função `IIF` é particularmente sensível a esse comportamento porque, ao contrário de uma instrução If-Then-Else, cada parte da instrução `IIF` é avaliada (incluindo chamadas de função) antes de ser passada para a rotina que é testada como `true` ou `false`.</span><span class="sxs-lookup"><span data-stu-id="05c90-336">The `IIF` function is particularly sensitive to this behavior because, unlike an If-Then-Else statement, each part of the `IIF` statement is evaluated (including function calls) before being passed to the routine that tests for `true` or `false`.</span></span> <span data-ttu-id="05c90-337">A instrução `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` gerará **#Erro** no relatório renderizado se `Fields!Sales.Value` for NOTHING.</span><span class="sxs-lookup"><span data-stu-id="05c90-337">The statement `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` generates **#Error** in the rendered report if `Fields!Sales.Value` is NOTHING.</span></span>  

<span data-ttu-id="05c90-338">Para evitar essa condição, use uma das seguintes estratégias:</span><span class="sxs-lookup"><span data-stu-id="05c90-338">To avoid this condition, use one of the following strategies:</span></span>  

-   <span data-ttu-id="05c90-339">Defina o numerador como 0 e o denominador como 1, se o valor do campo B for 0 ou indefinido. Caso contrário defina o numerador como o valor do campo A e o denominador como o valor do campo B.</span><span class="sxs-lookup"><span data-stu-id="05c90-339">Set the numerator to 0 and the denominator to 1 if the value for field B is 0 or undefined; otherwise, set the numerator to the value for field A and the denominator to the value for field B.</span></span>  

```  
=IIF(Field!B.Value=0, 0, Field!A.Value / IIF(Field!B.Value =0, 1, Field!B.Value))  
```  

-   <span data-ttu-id="05c90-340">Use uma função de código personalizado para retornar o valor da expressão.</span><span class="sxs-lookup"><span data-stu-id="05c90-340">Use a custom code function to return the value for the expression.</span></span> <span data-ttu-id="05c90-341">O exemplo a seguir retorna a diferença da porcentagem entre um valor atual e um valor anterior.</span><span class="sxs-lookup"><span data-stu-id="05c90-341">The following example returns the percentage difference between a current value and a previous value.</span></span> <span data-ttu-id="05c90-342">Isso pode ser usado para calcular a diferença entre quaisquer dois valores sucessivos e trata o caso de borda da primeira comparação (quando não há valor anterior) e casos em que o valor anterior ou o valor atual é `null` (`Nothing` no [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="05c90-342">This can be used to calculate the difference between any two successive values and it handles the edge case of the first comparison (when there is no previous value) and cases whether either the previous value or the current value is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  

```  
Public Function GetDeltaPercentage(ByVal PreviousValue, ByVal CurrentValue) As Object  
     If IsNothing(PreviousValue) OR IsNothing(CurrentValue) Then  
          Return Nothing  
     Else if PreviousValue = 0 OR CurrentValue = 0 Then  
          Return Nothing  
     Else
          Return (CurrentValue - PreviousValue) / CurrentValue  
     End If  
End Function  
```  

<span data-ttu-id="05c90-343">A expressão a seguir mostra como chamar esse código personalizado de uma caixa de texto, para o contêiner "ColumnGroupByYear" (grupo ou região de dados).</span><span class="sxs-lookup"><span data-stu-id="05c90-343">The following expression shows how to call this custom code from a text box, for the "ColumnGroupByYear" container (group or data region).</span></span>  

```  
=Code.GetDeltaPercentage(Previous(Sum(Fields!Sales.Value),"ColumnGroupByYear"), Sum(Fields!Sales.Value))  
```  

<span data-ttu-id="05c90-344">Isso ajuda a evitar exceções em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="05c90-344">This helps to avoid run-time exceptions.</span></span> <span data-ttu-id="05c90-345">Agora você pode usar uma expressão como `=IIF(Me.Value < 0, "red", "black")` na propriedade `Color` da caixa de texto para exibição condicional do texto, dependendo se os valores são maiores que ou menores que 0.</span><span class="sxs-lookup"><span data-stu-id="05c90-345">You can now use an expression like `=IIF(Me.Value < 0, "red", "black")` in the `Color` property of the text box to conditionally the display text based on whether the values are greater than or less than 0.</span></span>  

## <a name="see-also"></a><span data-ttu-id="05c90-346">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05c90-346">See Also</span></span>

- [<span data-ttu-id="05c90-347">Exemplos de equações de filtro &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="05c90-347">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="05c90-348">Exemplos de expressões de grupo &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="05c90-348">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="05c90-349">Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="05c90-349">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)
- [<span data-ttu-id="05c90-350">Expressões &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="05c90-350">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)
- [<span data-ttu-id="05c90-351">Filtros geralmente usados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="05c90-351">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)