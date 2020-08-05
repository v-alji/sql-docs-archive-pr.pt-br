---
title: Compatibilidade de fórmula DAX no modo DirectQuery (SSAS 2014) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: de83cfa9-9ffe-4e24-9c74-96a3876cb4bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: acaac82d6930787a45281c0e942def8df764f4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572822"
---
# <a name="dax-formula-compatibility-in-directquery-mode-ssas-2014"></a><span data-ttu-id="06390-102">Compatibilidade de fórmula do DAX no modo DirectQuery (SSAS 2014)</span><span class="sxs-lookup"><span data-stu-id="06390-102">DAX Formula Compatibility in DirectQuery Mode (SSAS 2014)</span></span>
<span data-ttu-id="06390-103">A DAX (linguagem de expressão de análise de dados) pode ser usada para criar medidas e outras fórmulas personalizadas para uso em Analysis Services modelos de tabela, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] modelos de dados em pastas de trabalho do Excel e Power bi desktop modelos de dados.</span><span class="sxs-lookup"><span data-stu-id="06390-103">The Data Analysis Expression language (DAX) can be used to create measures and other custom formulas for use in Analysis Services Tabular models, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] data models in Excel workbooks, and Power BI Desktop data models.</span></span> <span data-ttu-id="06390-104">Na maioria dos aspectos, os modelos criados nesses ambientes são idênticos e você pode usar as mesmas medidas, relações e KPIs, etc. No entanto, se você criar um modelo de tabela Analysis Services e implantá-lo no modo DirectQuery, haverá algumas restrições nas fórmulas que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="06390-104">In most respects, the models you create in these environments are identical, and you can use the same measures, relationships, and KPIs, etc. However, if you author an Analysis Services Tabular model and deploy it in DirectQuery mode, there are some restrictions on the formulas that you can use.</span></span> <span data-ttu-id="06390-105">Este tópico fornece uma visão geral dessas diferenças, lista as funções que não têm suporte no SQL Server 2014 Analysis Services modelo de tabelas no nível de compatibilidade 1100 ou 1103 e no modo DirectQuery, e lista as funções com suporte, mas que podem retornar resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="06390-105">This topic provides an overview of those differences, lists the functions that are not supported in SQL Server 2014 Analysis Services tabulars model at compatibility level 1100 or 1103 and in DirectQuery mode, and lists the functions that are supported but might return different results.</span></span>  
  
<span data-ttu-id="06390-106">Neste tópico, usamos o termo *modelo na memória* para fazer referência a modelos de tabela, que são totalmente hospedados em dados em cache na memória em um servidor Analysis Services executado no modo de tabela.</span><span class="sxs-lookup"><span data-stu-id="06390-106">Within this topic, we use the term *in-memory model* to refer to  Tabular models, which are fully hosted in-memory cached data on an Analysis Services server running in Tabular mode.</span></span> <span data-ttu-id="06390-107">Usamos *modelos DirectQuery* para fazer referência a modelos de tabela que foram criados e/ou implantados no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="06390-107">We use *DirectQuery models* to refer to Tabular models that have been authored and/or deployed in DirectQuery mode.</span></span> <span data-ttu-id="06390-108">Para obter informações sobre o modo DirectQuery, consulte [modo DirectQuery (SSAS tabular)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span><span class="sxs-lookup"><span data-stu-id="06390-108">For information about DirectQuery mode, see [DirectQuery Mode (SSAS Tabular)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span></span>  
  
  
## <a name="differences-between-in-memory-and-directquery-mode"></a><a name="bkmk_SemanticDifferences"></a><span data-ttu-id="06390-109">Diferenças entre os modos na memória e DirectQuery</span><span class="sxs-lookup"><span data-stu-id="06390-109">Differences between in-memory and DirectQuery mode</span></span>  
<span data-ttu-id="06390-110">Consultas em um modelo implantado no modo DirectQuery podem retornar resultados diferentes do mesmo modelo implantado no modo na memória.</span><span class="sxs-lookup"><span data-stu-id="06390-110">Queries on a model deployed in DirectQuery mode can return different results than the same model deployed in in-memory mode.</span></span> <span data-ttu-id="06390-111">Isso ocorre porque, com o DirectQuery, os dados são consultados diretamente de um armazenamento de dados relacional e as agregações exigidas por fórmulas são executadas usando o mecanismo relacional relevante, em vez de usar o mecanismo analítico na memória xVelocity (VertiPaq) para armazenamento e cálculo.</span><span class="sxs-lookup"><span data-stu-id="06390-111">This is because with DirectQuery, data is queried directly from a relational data store and aggregations required by formulas are performed using the relevant relational engine, rather than using the xVelocity in-memory analytics engine (VertiPaq) for storage and calculation.</span></span>  
  
<span data-ttu-id="06390-112">Por exemplo, há diferenças no modo como certos repositórios de dados relacionais tratam valores numéricos, datas, nulos etc.</span><span class="sxs-lookup"><span data-stu-id="06390-112">For example, there are differences in the way that certain relational data stores handle numeric values, dates, nulls, and so forth.</span></span>  
  
<span data-ttu-id="06390-113">Em contrapartida, a linguagem DAX destina-se a emular, do modo mais semelhante possível, o comportamento das funções no Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="06390-113">In contrast, the DAX language is intended to emulate as closely as possible the behavior of functions in Microsoft Excel.</span></span> <span data-ttu-id="06390-114">Por exemplo, ao tratar nulos, cadeias de caracteres vazias e valores de zero, o Excel tenta fornecer a melhor resposta, independentemente do tipo de dados preciso e, portanto, o mecanismo xVelocity faz o mesmo.</span><span class="sxs-lookup"><span data-stu-id="06390-114">For example, when handling nulls, empty strings and zero values, Excel attempts to provide the best answer regardless of the precise data type, and therefore the xVelocity engine does the same.</span></span> <span data-ttu-id="06390-115">No entanto, quando um modelo de tabela é implantado no modo DirectQuery e passa fórmulas a uma fonte de dados relacional para avaliação, os dados devem ser tratados de acordo com a semântica da fonte de dados relacional, o que geralmente requer o tratamento distinto de cadeias de caracteres e nulos.</span><span class="sxs-lookup"><span data-stu-id="06390-115">However, when a tabular model is deployed in DirectQuery mode and passes formulas to a relational data source for evaluation, the data must be handled according to the semantics of the relational data source, which typically require distinct handling of empty strings vs. nulls.</span></span> <span data-ttu-id="06390-116">Por isso, a mesma fórmula pode retornar um resultado diferente quando avaliada em relação aos dados armazenados em cache e em relação aos dados retornados exclusivamente do repositório relacional.</span><span class="sxs-lookup"><span data-stu-id="06390-116">For this reason, the same formula might return a different result when evaluated against cached data and against data returned solely from the relational store.</span></span>  
  
<span data-ttu-id="06390-117">Além disso, algumas funções não podem ser usadas no modo DirectQuery porque o cálculo exigiria que os dados no contexto atual fossem enviados para a fonte de dados relacional como um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="06390-117">Additionally, some functions cannot be used at all in DirectQuery mode because the calculation would require the data in the current context be sent to the relational data source as a parameter.</span></span> <span data-ttu-id="06390-118">Por exemplo, as medidas em uma [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] pasta de trabalho geralmente usam funções de inteligência de tempo que fazem referência a intervalos de datas disponíveis na pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="06390-118">For example, measures in a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] workbook often use time-intelligence functions that reference date ranges available within the workbook.</span></span> <span data-ttu-id="06390-119">Em geral, essas fórmulas não podem ser usadas no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="06390-119">Such formulas generally cannot be used in DirectQuery mode.</span></span>  
  
## <a name="semantic-differences"></a><span data-ttu-id="06390-120">Diferenças semânticas</span><span class="sxs-lookup"><span data-stu-id="06390-120">Semantic differences</span></span>  
<span data-ttu-id="06390-121">Esta seção lista os tipos de diferenças semânticas que você pode esperar e descreve as limitações que podem se aplicar ao uso de funções ou aos resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="06390-121">This section lists the types of semantic differences that you can expect, and describes any limitations that might apply to the usage of functions or to query results.</span></span>  
  
### <a name="comparisons"></a><a name="bkmk_Comparisons"></a><span data-ttu-id="06390-122">Comparações</span><span class="sxs-lookup"><span data-stu-id="06390-122">Comparisons</span></span>  
<span data-ttu-id="06390-123">A DAX nos modelos na memória dá suporte a comparações de duas expressões que são resolvidas para valores escalares de tipos de dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="06390-123">DAX in in-memory models support comparisons of two expressions that resolve to scalar values of different data types.</span></span> <span data-ttu-id="06390-124">No entanto, modelos implantados no modo DirectQuery usam os tipos de dados e os operadores de comparação do mecanismo relacional e, portanto, podem retornar resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="06390-124">However, models that are deployed in DirectQuery mode use the data types and comparison operators of the relational engine, and therefore might return different results.</span></span>  
  
<span data-ttu-id="06390-125">As seguintes comparações sempre retornarão um erro quando usadas em um cálculo em uma fonte de dados DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="06390-125">The following comparisons will always return an error when used in a calculation on a DirectQuery data source:</span></span>  
  
-   <span data-ttu-id="06390-126">Tipo de dados numeric comparado a qualquer tipo de dados string</span><span class="sxs-lookup"><span data-stu-id="06390-126">Numeric data type compared to any string data type</span></span>  
  
-   <span data-ttu-id="06390-127">Tipo de dados numeric comparado a um valor booliano</span><span class="sxs-lookup"><span data-stu-id="06390-127">Numeric data type compared to a Boolean value</span></span>  
  
-   <span data-ttu-id="06390-128">Qualquer tipo de dados string comparado a um valor booliano</span><span class="sxs-lookup"><span data-stu-id="06390-128">Any string data type compared to a Boolean value</span></span>  
  
<span data-ttu-id="06390-129">Em geral, a DAX é mais tolerante com incompatibilidades de tipo de dados em modelos na memória e tentará uma conversão implícita de valores até duas vezes, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="06390-129">In general, DAX is more forgiving of data type mismatches in in-memory models and will attempt an implicit cast of values up to two times, as described in this section.</span></span> <span data-ttu-id="06390-130">No entanto, as fórmulas enviadas a um repositório de dados relacional no modo DirectQuery são avaliadas com mais rigor, de acordo com as regras do mecanismo relacional e apresentam maior probabilidade de falha.</span><span class="sxs-lookup"><span data-stu-id="06390-130">However, formulas sent to a relational data store in DirectQuery mode are evaluated more strictly, following the rules of the relational engine, and are more likely to fail.</span></span>  
  
<span data-ttu-id="06390-131">**Comparações de cadeias de caracteres e números**</span><span class="sxs-lookup"><span data-stu-id="06390-131">**Comparisons of strings and numbers**</span></span>  
<span data-ttu-id="06390-132">EXEMPLO: `"2" < 3`</span><span class="sxs-lookup"><span data-stu-id="06390-132">EXAMPLE: `"2" < 3`</span></span>  
  
<span data-ttu-id="06390-133">A fórmula compara uma cadeia de caracteres de texto a um número.</span><span class="sxs-lookup"><span data-stu-id="06390-133">The formula compares a text string to a number.</span></span> <span data-ttu-id="06390-134">A expressão é **true** no modo DirectQuery e em modelos na memória.</span><span class="sxs-lookup"><span data-stu-id="06390-134">The expression is **true** in both DirectQuery mode and in-memory models.</span></span>  
  
<span data-ttu-id="06390-135">Em um modelo na memória, o resultado é **true** porque números como cadeias de caracteres são convertidos implicitamente em um tipo de dados numérico para comparações com outros números.</span><span class="sxs-lookup"><span data-stu-id="06390-135">In an in-memory model, the result is **true** because numbers as strings are implicitly cast to a numerical data type for comparisons with other numbers.</span></span> <span data-ttu-id="06390-136">O SQL também converte implicitamente números de texto como números para comparação com tipos de dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="06390-136">SQL also implicitly casts text numbers as numbers for comparison to numerical data types.</span></span>  
  
<span data-ttu-id="06390-137">Observe que isso representa uma alteração no comportamento da primeira versão do [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] , que retornaria **false**, porque o texto "2" sempre seria considerado maior do que qualquer número.</span><span class="sxs-lookup"><span data-stu-id="06390-137">Note that this represents a change in behavior from the first version of [!INCLUDE[ssGemini](../includes/ssgemini-md.md)], which would return **false**, because the text "2" would always be considered larger than any number.</span></span>  
  
<span data-ttu-id="06390-138">**Comparação de texto com booliano**</span><span class="sxs-lookup"><span data-stu-id="06390-138">**Comparison of text with Boolean**</span></span>  
<span data-ttu-id="06390-139">EXEMPLO: `"VERDADERO" = TRUE`</span><span class="sxs-lookup"><span data-stu-id="06390-139">EXAMPLE: `"VERDADERO" = TRUE`</span></span>  
  
<span data-ttu-id="06390-140">Esta expressão compara uma cadeia de caracteres de texto com um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="06390-140">This expression compares a text string with a Boolean value.</span></span> <span data-ttu-id="06390-141">Em geral, para modelos DirectQuery ou Na Memória, a comparação de um valor de cadeia de caracteres com um valor booliano resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="06390-141">In general, for DirectQuery or In-Memory models, comparing a string value to a Boolean value results in an error.</span></span> <span data-ttu-id="06390-142">As únicas exceções à regra ocorrem quando a cadeia de caracteres contém as palavras **true** ou **false**; se a cadeia de caracteres contiver um dos valores true ou false, uma conversão em booliano será feita e a comparação ocorrerá, apresentando o resultado lógico.</span><span class="sxs-lookup"><span data-stu-id="06390-142">The only exceptions to the rule are when the string contains the word **true** or the word **false**; if the string contains any of true or false values, a conversion to Boolean is made and the comparison takes place giving the logical result.</span></span>  
  
<span data-ttu-id="06390-143">**Comparação de nulos**</span><span class="sxs-lookup"><span data-stu-id="06390-143">**Comparison of nulls**</span></span>  
<span data-ttu-id="06390-144">EXEMPLO: `EVALUATE ROW("X", BLANK() = BLANK())`</span><span class="sxs-lookup"><span data-stu-id="06390-144">EXAMPLE: `EVALUATE ROW("X", BLANK() = BLANK())`</span></span>  
  
<span data-ttu-id="06390-145">Esta fórmula compara o SQL equivalente de um nulo a um nulo.</span><span class="sxs-lookup"><span data-stu-id="06390-145">This formula compares the SQL equivalent of a null to a null.</span></span> <span data-ttu-id="06390-146">Retorna **true** em modelos na memória e DirectQuery; um provisionamento é feito no modelo DirectQuery para garantir comportamento semelhante a um modelo na memória.</span><span class="sxs-lookup"><span data-stu-id="06390-146">It returns **true** in in-memory and DirectQuery models; a provision is made in DirectQuery model to guarantee similar behavior to in-memory model.</span></span>  
  
<span data-ttu-id="06390-147">Observe que, no Transact-SQL, um nulo nunca é igual a um nulo.</span><span class="sxs-lookup"><span data-stu-id="06390-147">Note that in Transact-SQL, a null is never equal to a null.</span></span> <span data-ttu-id="06390-148">No entanto, na DAX, um espaço em branco é igual a outro espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="06390-148">However, in DAX, a blank is equal to another blank.</span></span> <span data-ttu-id="06390-149">Esse comportamento é o mesmo para todos os modelos na memória.</span><span class="sxs-lookup"><span data-stu-id="06390-149">This behavior is the same for all in-memory models.</span></span> <span data-ttu-id="06390-150">É importante observar que o modo DirectQuery usa grande parte da semântica do SQL Server; mas, nesse caso, se separa dela, proporcionando um novo comportamento a comparações NULL.</span><span class="sxs-lookup"><span data-stu-id="06390-150">It is important to note that DirectQuery mode uses, most of, the semantics of SQL Server; but, in this case it separates from it giving a new behavior to NULL comparisons.</span></span>  
  
### <a name="casts"></a><a name="bkmk_Casts"></a><span data-ttu-id="06390-151">Conversões</span><span class="sxs-lookup"><span data-stu-id="06390-151">Casts</span></span>  
  
<span data-ttu-id="06390-152">Não há nenhuma função de conversão como na DAX, mas conversões implícitas são executadas em muitas operações de comparação e aritméticas.</span><span class="sxs-lookup"><span data-stu-id="06390-152">There is no cast function as such in DAX, but implicit casts are performed in many comparison and arithmetic operations.</span></span> <span data-ttu-id="06390-153">É a operação de comparação ou aritmética que determina o tipo de dados do resultado.</span><span class="sxs-lookup"><span data-stu-id="06390-153">It is the comparison or arithmetic operation that determines the data type of the result.</span></span> <span data-ttu-id="06390-154">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="06390-154">For example,</span></span>  
  
-   <span data-ttu-id="06390-155">Valores boolianos são tratados como numéricos em operações aritméticas, como TRUE + 1, ou a função MIN aplicada a uma coluna de valores boolianos.</span><span class="sxs-lookup"><span data-stu-id="06390-155">Boolean values are treated as numeric in arithmetic operations, such as TRUE + 1, or the function MIN applied to a column of Boolean values.</span></span> <span data-ttu-id="06390-156">Uma operação NOT também retorna um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="06390-156">A NOT operation also returns a numeric value.</span></span>  
  
-   <span data-ttu-id="06390-157">Valores boolianos sempre são tratados como valores lógicos em comparações e quando usados com EXACT, AND, OR, &amp;&amp;ou ||.</span><span class="sxs-lookup"><span data-stu-id="06390-157">Boolean values are always treated as logical values in comparisons and when used with EXACT, AND, OR, &amp;&amp;, or ||.</span></span>  
  
<span data-ttu-id="06390-158">**Conversão de cadeia de caracteres em booliano**</span><span class="sxs-lookup"><span data-stu-id="06390-158">**Cast from string to Boolean**</span></span>  
<span data-ttu-id="06390-159">Em modelos na memória e DirectQuery, as conversões são permitidas apenas para valores Boolianos dessas cadeias de caracteres: **""** (cadeia de caracteres vazia), **"true"**, **"false"**; em que uma cadeia de caracteres vazia é convertida em valor falso.</span><span class="sxs-lookup"><span data-stu-id="06390-159">In in-memory and DirectQuery models, casts are permitted to Boolean values from these strings only: **""** (empty string), **"true"**, **"false"**; where an empty string casts to false value.</span></span>  
  
<span data-ttu-id="06390-160">As conversões no tipo de dados Boolean de qualquer outra cadeia de caracteres resultam em um erro.</span><span class="sxs-lookup"><span data-stu-id="06390-160">Casts to the Boolean data type of any other string results in an error.</span></span>  
  
<span data-ttu-id="06390-161">**Conversão de cadeia de caracteres em data/hora**</span><span class="sxs-lookup"><span data-stu-id="06390-161">**Cast from string to date/time**</span></span>  
<span data-ttu-id="06390-162">No modo DirectQuery, conversões de representações de cadeias de caracteres de datas e horas em valores **datetime** reais apresentam o mesmo comportamento que teriam no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06390-162">In DirectQuery mode, casts from string representations of dates and times to actual **datetime** values behave the same way as they do in SQL Server.</span></span>  
  
<span data-ttu-id="06390-163">Para obter informações sobre as regras que regem as conversões de tipos de dados String para **DateTime** em [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] modelos, consulte a [referência de sintaxe do Dax](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="06390-163">For information about the rules governing casts from string to **datetime** data types in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, see the [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="06390-164">Os modelos que usam o repositório de dados na memória oferecem suporte a um intervalo mais limitado de formatos de texto para datas que os formatos de cadeias de caracteres para datas que têm suporte no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06390-164">Models that use the in-memory data store support a more limited range of text formats for dates than the string formats for dates that are supported by SQL Server.</span></span> <span data-ttu-id="06390-165">No entanto, a DAX oferece suporte a formatos de data e hora personalizados.</span><span class="sxs-lookup"><span data-stu-id="06390-165">However, DAX supports custom date and time formats.</span></span>  
  
<span data-ttu-id="06390-166">**Conversão de cadeia de caracteres em outros valores não boolianos**</span><span class="sxs-lookup"><span data-stu-id="06390-166">**Cast from string to other non Boolean values**</span></span>  
<span data-ttu-id="06390-167">Ao converter de cadeias de caracteres em valores não boolianos, o modo DirectQuery se comporta da mesma forma que no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06390-167">When casting from strings to non-Boolean values, DirectQuery mode behaves the same as SQL Server.</span></span> <span data-ttu-id="06390-168">Para obter mais informações, veja [CAST e CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span><span class="sxs-lookup"><span data-stu-id="06390-168">For more information, see [CAST and CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span></span>  
  
<span data-ttu-id="06390-169">**Não é permitido converter de números em cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="06390-169">**Cast from numbers to string not allowed**</span></span>  
<span data-ttu-id="06390-170">EXEMPLO: `CONCATENATE(102,",345")`</span><span class="sxs-lookup"><span data-stu-id="06390-170">EXAMPLE: `CONCATENATE(102,",345")`</span></span>  
  
<span data-ttu-id="06390-171">A conversão de números em cadeias de caracteres não é permitida no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06390-171">Casting from numbers to strings is not allowed in SQL Server.</span></span>  
  
<span data-ttu-id="06390-172">Esta fórmula retorna um erro em modelos tabulares e no modo DirectQuery; no entanto, a fórmula produz um resultado no [!INCLUDE[ssGemini](../includes/ssgemini-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06390-172">This formula returns an error in tabular models and in DirectQuery mode; however, the formula produces a result in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)].</span></span>  
  
<span data-ttu-id="06390-173">**Não há suporte para conversões em duas tentativas no DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="06390-173">**No support for two-try casts in DirectQuery**</span></span>  
<span data-ttu-id="06390-174">Com frequência, os modelos na memória tentam uma segunda conversão quando a primeira falha.</span><span class="sxs-lookup"><span data-stu-id="06390-174">In-memory models often attempt a second cast when the first one fails.</span></span> <span data-ttu-id="06390-175">Isso nunca acontece no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="06390-175">This never happens in DirectQuery mode.</span></span>  
  
<span data-ttu-id="06390-176">EXEMPLO: `TODAY() + "13:14:15"`</span><span class="sxs-lookup"><span data-stu-id="06390-176">EXAMPLE: `TODAY() + "13:14:15"`</span></span>  
  
<span data-ttu-id="06390-177">Nessa expressão, o primeiro parâmetro tem o tipo **datetime** e o segundo tem o tipo **string**.</span><span class="sxs-lookup"><span data-stu-id="06390-177">In this expression, the first parameter has type **datetime** and second parameter has type **string**.</span></span> <span data-ttu-id="06390-178">No entanto, as conversões durante a combinação dos operandos são tratadas de modo diferente.</span><span class="sxs-lookup"><span data-stu-id="06390-178">However, the casts when combining the operands are handled differently.</span></span> <span data-ttu-id="06390-179">A DAX executará uma conversão implícita de **string** em **double**.</span><span class="sxs-lookup"><span data-stu-id="06390-179">DAX will perform an implicit cast from **string** to **double**.</span></span> <span data-ttu-id="06390-180">Nos modelos na memória, o mecanismo da fórmula tentará converter diretamente em **double**e, se falhar, tentará converter a cadeia de caracteres em **datetime**.</span><span class="sxs-lookup"><span data-stu-id="06390-180">In in-memory models, the formula engine attempts to cast directly to **double**, and if that fails, it will try to cast the string to **datetime**.</span></span>  
  
<span data-ttu-id="06390-181">No modo DirectQuery, somente a conversão direta de **string** em **double** será aplicada.</span><span class="sxs-lookup"><span data-stu-id="06390-181">In DirectQuery mode, only the direct cast from **string** to **double** will be applied.</span></span> <span data-ttu-id="06390-182">Se essa conversão falhar, a fórmula retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="06390-182">If this cast fails, the formula will return an error.</span></span>  
  
### <a name="math-functions-and-arithmetic-operations"></a><a name="bkmk_Math"></a><span data-ttu-id="06390-183">Funções matemáticas e operações aritméticas</span><span class="sxs-lookup"><span data-stu-id="06390-183">Math functions and arithmetic operations</span></span>  
<span data-ttu-id="06390-184">Algumas funções matemáticas retornarão resultados diferentes no modo DirectQuery, devido às diferenças no tipo de dados subjacente ou as conversões que podem ser aplicadas em operações.</span><span class="sxs-lookup"><span data-stu-id="06390-184">Some mathematical functions will return different results in DirectQuery mode because of differences in the underlying data type or the casts that can be applied in operations.</span></span> <span data-ttu-id="06390-185">Além disso, as restrições descritas acima no intervalo de valores permitido poderão afetar o resultado das operações aritméticas.</span><span class="sxs-lookup"><span data-stu-id="06390-185">Also, the restrictions described above on the allowed range of values might affect the outcome of arithmetic operations.</span></span>  
  
<span data-ttu-id="06390-186">**Ordem de adição**</span><span class="sxs-lookup"><span data-stu-id="06390-186">**Order of addition**</span></span>  
<span data-ttu-id="06390-187">Quando você cria uma fórmula que adiciona uma série de números, um modelo na memória pode processar os números em uma ordem diferente da de um modelo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="06390-187">When you create a formula that adds a series of numbers, an in-memory model might process the numbers in a different order than a DirectQuery model.</span></span>  <span data-ttu-id="06390-188">Portanto, quando há muitos números positivos muito grandes e números negativos muito grandes, você pode receber um erro em uma operação e resultados em outra.</span><span class="sxs-lookup"><span data-stu-id="06390-188">Therefore, when you have many very large positive numbers and very large negative numbers, you may get an error in one operation and results in another operation.</span></span>  
  
<span data-ttu-id="06390-189">**Uso da função POWER**</span><span class="sxs-lookup"><span data-stu-id="06390-189">**Use of the POWER function**</span></span>  
<span data-ttu-id="06390-190">EXEMPLO: `POWER(-64, 1/3)`</span><span class="sxs-lookup"><span data-stu-id="06390-190">EXAMPLE: `POWER(-64, 1/3)`</span></span>  
  
<span data-ttu-id="06390-191">No modo DirectQuery, a função POWER não pode usar valores negativos como a base, quando elevada a um expoente fracionário.</span><span class="sxs-lookup"><span data-stu-id="06390-191">In DirectQuery mode, the POWER function cannot use negative values as the base when raised to a fractional exponent.</span></span> <span data-ttu-id="06390-192">Esse é o comportamento esperado no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06390-192">This is the expected behavior in SQL Server.</span></span>  
  
<span data-ttu-id="06390-193">Em um modelo na memória, a fórmula retorna -4.</span><span class="sxs-lookup"><span data-stu-id="06390-193">In an in-memory model, the formula returns -4.</span></span>  
  
<span data-ttu-id="06390-194">**Operações de estouro numéricas**</span><span class="sxs-lookup"><span data-stu-id="06390-194">**Numerical overflow operations**</span></span>  
<span data-ttu-id="06390-195">No Transact-SQL, as operações que resultam em um estouro numérico retornam um erro de estouro; portanto, fórmulas que resultam em um estouro também geram um erro no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="06390-195">In Transact-SQL, operations that result in a numerical overflow return an overflow error; therefore, formulas that result in an overflow also raise an error in DirectQuery mode.</span></span>  
  
<span data-ttu-id="06390-196">No entanto, quando usada em um modelo na memória, a mesma fórmula retorna um número inteiro de oito bytes.</span><span class="sxs-lookup"><span data-stu-id="06390-196">However, the same formula when used in an in-memory model returns an eight-byte integer.</span></span> <span data-ttu-id="06390-197">Isso ocorre porque o mecanismo da fórmula não executa verificações de estouros numéricos.</span><span class="sxs-lookup"><span data-stu-id="06390-197">That is because the formula engine does not perform checks for numerical overflows.</span></span>  
  
<span data-ttu-id="06390-198">**Funções LOG com espaços em branco retornam resultados diferentes**</span><span class="sxs-lookup"><span data-stu-id="06390-198">**LOG functions with blanks return different results**</span></span>  
<span data-ttu-id="06390-199">O SQL Server trata nulos e espaços em branco de modo diferente do mecanismo xVelocity.</span><span class="sxs-lookup"><span data-stu-id="06390-199">SQL Server handles nulls and blanks differently than the xVelocity engine.</span></span> <span data-ttu-id="06390-200">Como resultado, a fórmula a seguir retorna um erro no modo DirectQuery, mas retorna infinito (-inf) no modo na memória.</span><span class="sxs-lookup"><span data-stu-id="06390-200">As a result, the following formula returns an error in DirectQuery mode, but return infinity (-inf) in in-memory mode.</span></span>  
  
`EXAMPLE: LOG(blank())`  
  
<span data-ttu-id="06390-201">As mesmas limitações se aplicam a outras funções logarítmicas: LOG10 e LN.</span><span class="sxs-lookup"><span data-stu-id="06390-201">The same limitations apply to the other logarithmic functions: LOG10 and LN.</span></span>  
  
<span data-ttu-id="06390-202">Para obter mais informações sobre o tipo de dados **blank** na DAX, consulte [Referência de sintaxe DAX](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="06390-202">For more information about the **blank** data type in DAX, see [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="06390-203">**Divisão por 0 e divisão por espaço em branco**</span><span class="sxs-lookup"><span data-stu-id="06390-203">**Division by 0 and division by Blank**</span></span>  
<span data-ttu-id="06390-204">No modo DirectQuery, a divisão por zero (0) ou a divisão por BLANK sempre resultará em um erro.</span><span class="sxs-lookup"><span data-stu-id="06390-204">In DirectQuery mode, division by zero (0) or division by BLANK will always result in an error.</span></span> <span data-ttu-id="06390-205">O SQL Server não oferece suporte à noção de infinito e, como o resultado natural de qualquer divisão por 0 é infinito, o resultado é um erro.</span><span class="sxs-lookup"><span data-stu-id="06390-205">SQL Server does not support the notion of infinity, and because the natural result of any division by 0 is infinity, the result is an error.</span></span> <span data-ttu-id="06390-206">No entanto, o SQL Server oferece suporte à divisão por nulos e o resultado sempre deve ser igual a nulo.</span><span class="sxs-lookup"><span data-stu-id="06390-206">However, SQL Server supports division by nulls, and the result must always equal null.</span></span>  
  
<span data-ttu-id="06390-207">Em vez de retornar resultados diferentes para essas operações, no modo DirectQuery, ambos os tipos de operações (divisão por zero e divisão por nulo) retornam um erro.</span><span class="sxs-lookup"><span data-stu-id="06390-207">Rather than return different results for these operations, in DirectQuery mode, both types of operations (division by zero and division by null) return an error.</span></span>  
  
<span data-ttu-id="06390-208">Observe que, em modelos do Excel e do [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] , a divisão por zero também retorna um erro.</span><span class="sxs-lookup"><span data-stu-id="06390-208">Note that, in Excel and in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, division by zero also returns an error.</span></span> <span data-ttu-id="06390-209">A divisão por um espaço em branco retorna um espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="06390-209">Division by a blank returns a blank.</span></span>  
  
<span data-ttu-id="06390-210">As seguintes expressões são válidas em modelos na memória, mas falharão no modo DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="06390-210">The following expressions are all valid in in-memory models, but will fail in DirectQuery mode:</span></span>  
  
`1/BLANK`  
  
`1/0`  
  
`0.0/BLANK`  
  
`0/0`  
  
<span data-ttu-id="06390-211">A expressão `BLANK/BLANK` é um caso especial que retorna `BLANK` em modelos na memória e no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="06390-211">The expression `BLANK/BLANK` is a special case that returns `BLANK` in both for in-memory models, and in DirectQuery mode.</span></span>  
  
### <a name="supported-numeric-and-date-time-ranges"></a><a name="bkmk_Ranges"></a><span data-ttu-id="06390-212">Intervalos numéricos e de data-hora com suporte</span><span class="sxs-lookup"><span data-stu-id="06390-212">Supported numeric and date-time ranges</span></span>  
<span data-ttu-id="06390-213">As fórmulas no [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] e nos modelos tabulares na memória estão sujeitas às mesmas limitações que o Excel em relação aos valores máximos permitidos para números e datas reais.</span><span class="sxs-lookup"><span data-stu-id="06390-213">Formulas in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and tabular models in-memory are subject to the same limitations as Excel with regard to maximum allowed values for real numbers and dates.</span></span> <span data-ttu-id="06390-214">No entanto, podem surgir diferenças quando o valor máximo é retornado de um cálculo ou consulta ou quando valores são convertidos, arredondados ou truncados.</span><span class="sxs-lookup"><span data-stu-id="06390-214">However, differences can arise when the maximum value is returned from a calculation or query, or when values are converted, cast, rounded, or truncated.</span></span>  
  
-   <span data-ttu-id="06390-215">Se valores de tipos **Currency** e **Real** forem multiplicados e o resultado for maior do que o máximo possível, no modo DirectQuery, nenhum erro será gerado e um nulo será retornado.</span><span class="sxs-lookup"><span data-stu-id="06390-215">If values of types **Currency** and **Real** are multiplied, and the result is larger than the maximum possible value, in DirectQuery mode, no error is raised, and a null is returned.</span></span>  
  
-   <span data-ttu-id="06390-216">Em modelos na memória, nenhum erro é gerado, mas o valor máximo é retornado.</span><span class="sxs-lookup"><span data-stu-id="06390-216">In in-memory models, no error is raised, but the maximum value is returned.</span></span>  
  
<span data-ttu-id="06390-217">Em geral, como os intervalos de datas aceitos são diferentes para o Excel e o SQL Server, é possível garantir que os resultados coincidam apenas quando as datas estiverem dentro do intervalo de datas comum, o que inclui as seguintes datas:</span><span class="sxs-lookup"><span data-stu-id="06390-217">In general, because the accepted date ranges are different for Excel and SQL Server, results can be guaranteed to match only when dates are within the common date range, which is inclusive of the following dates:</span></span>  
  
-   <span data-ttu-id="06390-218">Data mais antiga: 1º de março de 1990</span><span class="sxs-lookup"><span data-stu-id="06390-218">Earliest date: March 1, 1990</span></span>  
  
-   <span data-ttu-id="06390-219">Data mais recente: 31 de dezembro de 9999</span><span class="sxs-lookup"><span data-stu-id="06390-219">Latest date: December 31, 9999</span></span>  
  
<span data-ttu-id="06390-220">Se qualquer data usada em fórmulas ficar fora desse intervalo, a fórmula resultará em um erro ou os resultados não coincidirão.</span><span class="sxs-lookup"><span data-stu-id="06390-220">If any dates used in formulas fall outside this range, either the formula will result in an error, or the results will not match.</span></span>  
  
<span data-ttu-id="06390-221">**Valores de ponto flutuante com suporte de CEILING**</span><span class="sxs-lookup"><span data-stu-id="06390-221">**Floating point values supported by CEILING**</span></span>  
<span data-ttu-id="06390-222">EXEMPLO: `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span><span class="sxs-lookup"><span data-stu-id="06390-222">EXAMPLE: `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span></span>  
  
<span data-ttu-id="06390-223">O equivalente Transact-SQL da função DAX CEILING somente oferece suporte a valores com magnitude de 10^19 ou menos.</span><span class="sxs-lookup"><span data-stu-id="06390-223">The Transact-SQL equivalent of the DAX CEILING function only supports values with magnitude of 10^19 or less.</span></span> <span data-ttu-id="06390-224">Uma regra prática é que os valores de ponto flutuante devem se ajustar em **bigint**.</span><span class="sxs-lookup"><span data-stu-id="06390-224">A rule of thumb is that floating point values should be able to fit into **bigint**.</span></span>  
  
<span data-ttu-id="06390-225">**Funções Datepart com datas fora do intervalo**</span><span class="sxs-lookup"><span data-stu-id="06390-225">**Datepart functions with dates that are out of range**</span></span>  
<span data-ttu-id="06390-226">É garantido que os resultados no modo DirectQuery correspondam àqueles nos modelos na memória somente quando a data usada como argumento está no intervalo de datas válido.</span><span class="sxs-lookup"><span data-stu-id="06390-226">Results in DirectQuery mode are guaranteed to match those in in-memory models only when the date used as the argument is in the valid date range.</span></span> <span data-ttu-id="06390-227">Se essas condições não forem atendidas, um erro será gerado ou a fórmula retornará resultados diferentes nos modos DirectQuery e na memória.</span><span class="sxs-lookup"><span data-stu-id="06390-227">If these conditions are not satisfied, either an error will be raised, or the formula will return different results in DirectQuery than in in-memory mode.</span></span>  
  
<span data-ttu-id="06390-228">EXEMPLO: `MONTH(0)` ou `YEAR(0)`</span><span class="sxs-lookup"><span data-stu-id="06390-228">EXAMPLE: `MONTH(0)` or `YEAR(0)`</span></span>  
  
<span data-ttu-id="06390-229">No modo DirectQuery, as expressões retornam 12 e 1899, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="06390-229">In DirectQuery mode, the expressions return 12 and 1899, respectively.</span></span>  
  
<span data-ttu-id="06390-230">Nos modelos na memória, as expressões retornam 1 e 1900, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="06390-230">In in-memory models, the expressions return 1 and 1900, respectively.</span></span>  
  
<span data-ttu-id="06390-231">EXEMPLO:  `EOMONTH(0.0001, 1)`</span><span class="sxs-lookup"><span data-stu-id="06390-231">EXAMPLE:  `EOMONTH(0.0001, 1)`</span></span>  
  
<span data-ttu-id="06390-232">Os resultados dessa expressão somente coincidirão quando os dados fornecidos como um parâmetro estiverem dentro do intervalo de datas válido.</span><span class="sxs-lookup"><span data-stu-id="06390-232">The results of this expression will match only when the data supplied as a parameter is within the valid date range.</span></span>  
  
<span data-ttu-id="06390-233">EXEMPLO: `EOMONTH(blank(), blank())` ou `EDATE(blank(), blank())`</span><span class="sxs-lookup"><span data-stu-id="06390-233">EXAMPLE: `EOMONTH(blank(), blank())` or `EDATE(blank(), blank())`</span></span>  
  
<span data-ttu-id="06390-234">Os resultados dessa expressão devem ser iguais no modo DirectQuery e no modo na memória.</span><span class="sxs-lookup"><span data-stu-id="06390-234">The results of this expression should be the same in DirectQuery mode and in-memory mode.</span></span>  
  
<span data-ttu-id="06390-235">**Truncamento de valores temporais**</span><span class="sxs-lookup"><span data-stu-id="06390-235">**Truncation of time values**</span></span>  
<span data-ttu-id="06390-236">EXEMPLO: `SECOND(1231.04097222222)`</span><span class="sxs-lookup"><span data-stu-id="06390-236">EXAMPLE: `SECOND(1231.04097222222)`</span></span>  
  
<span data-ttu-id="06390-237">No modo DirectQuery, o resultado é truncado, de acordo com as regras do SQL Server, e a expressão é avaliada como 59.</span><span class="sxs-lookup"><span data-stu-id="06390-237">In DirectQuery mode, the result is truncated, following the rules of SQL Server, and the expression evaluates to 59.</span></span>  
  
<span data-ttu-id="06390-238">Em modelos na memória, os resultados de cada operação provisória são arredondados; portanto, a expressão é avaliada como 0.</span><span class="sxs-lookup"><span data-stu-id="06390-238">In in-memory models, the results of each interim operation are rounded; therefore, the expression evaluates to 0.</span></span>  
  
<span data-ttu-id="06390-239">O seguinte exemplo demonstra como esse valor é calculado:</span><span class="sxs-lookup"><span data-stu-id="06390-239">The following example demonstrates how this value is calculated:</span></span>  
  
1.  <span data-ttu-id="06390-240">A fração da entrada (0,04097222222) é multiplicada por 24.</span><span class="sxs-lookup"><span data-stu-id="06390-240">The fraction of the input (0.04097222222) is multiplied by 24.</span></span>  
  
2.  <span data-ttu-id="06390-241">O valor de hora resultante (0,98333333328) é multiplicado por 60.</span><span class="sxs-lookup"><span data-stu-id="06390-241">The resulting hour value (0.98333333328) is multiplied by 60.</span></span>  
  
3.  <span data-ttu-id="06390-242">O valor de minuto resultante é 58,9999999968.</span><span class="sxs-lookup"><span data-stu-id="06390-242">The resulting minute value is 58.9999999968.</span></span>  
  
4.  <span data-ttu-id="06390-243">A fração do valor de minuto (0,9999999968) é multiplicada por 60.</span><span class="sxs-lookup"><span data-stu-id="06390-243">The fraction of the minute value (0.9999999968) is multiplied by 60.</span></span>  
  
5.  <span data-ttu-id="06390-244">O segundo valor resultante (59,999999808) é arredondado para 60.</span><span class="sxs-lookup"><span data-stu-id="06390-244">The resulting second value (59.999999808) rounds up to 60.</span></span>  
  
6.  <span data-ttu-id="06390-245">60 é equivalente a 0.</span><span class="sxs-lookup"><span data-stu-id="06390-245">60 is equivalent to 0.</span></span>  
  
<span data-ttu-id="06390-246">**Não há suporte para o tipo de dados SQL Time**</span><span class="sxs-lookup"><span data-stu-id="06390-246">**SQL Time data type not supported**</span></span>  
<span data-ttu-id="06390-247">Modelos na memória não dão suporte ao uso do novo tipo de dados SQL **Time** .</span><span class="sxs-lookup"><span data-stu-id="06390-247">In-memory models do not support use of the new SQL **Time** data type.</span></span> <span data-ttu-id="06390-248">No modo DirectQuery, fórmulas que referenciam colunas com esse tipo de dados retornarão um erro.</span><span class="sxs-lookup"><span data-stu-id="06390-248">In DirectQuery mode, formulas that reference columns with this data type will return an error.</span></span> <span data-ttu-id="06390-249">Colunas de dados temporais não podem ser importadas para um modelo na memória.</span><span class="sxs-lookup"><span data-stu-id="06390-249">Time data columns cannot be imported into an in-memory model.</span></span>  
  
<span data-ttu-id="06390-250">No entanto, no [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] e em modelos em cache, às vezes o mecanismo converte o valor de tempo em um tipo de dados aceitável e a fórmula retorna um resultado.</span><span class="sxs-lookup"><span data-stu-id="06390-250">However, in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and in cached models, sometimes the engine casts the time value to an acceptable data type, and the formula returns a result.</span></span>  
  
<span data-ttu-id="06390-251">Esse comportamento afeta todas as funções que usam uma coluna de data como um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="06390-251">This behavior affects all functions that use a date column as a parameter.</span></span>  
  
### <a name="currency"></a><a name="bkmk_Currency"></a><span data-ttu-id="06390-252">Moeda</span><span class="sxs-lookup"><span data-stu-id="06390-252">Currency</span></span>  
<span data-ttu-id="06390-253">No modo DirectQuery, se o resultado de uma operação aritmética tiver o tipo **Currency**, o valor deverá estar dentro do seguinte intervalo:</span><span class="sxs-lookup"><span data-stu-id="06390-253">In DirectQuery mode, if the result of an arithmetic operation has the type **Currency**, the value must be within the following range:</span></span>  
  
-   <span data-ttu-id="06390-254">Mínimo: -922337203685477,5808</span><span class="sxs-lookup"><span data-stu-id="06390-254">Minimum: -922337203685477.5808</span></span>  
  
-   <span data-ttu-id="06390-255">Máximo: 922337203685477,5807</span><span class="sxs-lookup"><span data-stu-id="06390-255">Maximum: 922337203685477.5807</span></span>  
  
<span data-ttu-id="06390-256">**Combinação dos tipos de dados currency e REAL**</span><span class="sxs-lookup"><span data-stu-id="06390-256">**Combining currency and REAL data types**</span></span>  
<span data-ttu-id="06390-257">EXEMPLO: `Currency sample 1`</span><span class="sxs-lookup"><span data-stu-id="06390-257">EXAMPLE: `Currency sample 1`</span></span>  
  
<span data-ttu-id="06390-258">Se os tipos **Currency** e **Real** forem multiplicados e o resultado for maior que 9223372036854774784 (0x7ffffffffffffc00), o modo DirectQuery não gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="06390-258">If **Currency** and **Real** types are multiplied, and the result is larger than 9223372036854774784 (0x7ffffffffffffc00), DirectQuery mode will not raise an error.</span></span>  
  
<span data-ttu-id="06390-259">Em um modelo na memória, um erro será gerado se o valor absoluto do resultado for maior que 922337203685477,4784.</span><span class="sxs-lookup"><span data-stu-id="06390-259">In an in-memory model, an error is raised if the absolute value of the result is larger than 922337203685477.4784.</span></span>  
  
<span data-ttu-id="06390-260">**A operação resulta em um valor fora do intervalo**</span><span class="sxs-lookup"><span data-stu-id="06390-260">**Operation results in an out-of-range value**</span></span>  
<span data-ttu-id="06390-261">EXEMPLO: `Currency sample 2`</span><span class="sxs-lookup"><span data-stu-id="06390-261">EXAMPLE: `Currency sample 2`</span></span>  
  
<span data-ttu-id="06390-262">Se as operações em quaisquer dois valores de moeda resultarem em um valor que esteja fora do intervalo especificado, um erro será gerado em modelos na memória, mas não em modelos DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="06390-262">If operations on any two currency values result in a value that is outside the specified range, an error is raised in in-memory models, but not in DirectQuery models.</span></span>  
  
<span data-ttu-id="06390-263">**Combinação de currency com outros tipos de dados**</span><span class="sxs-lookup"><span data-stu-id="06390-263">**Combining currency with other data types**</span></span>  
<span data-ttu-id="06390-264">A divisão dos valores de moeda por valores de outros tipos numeric pode apresentar resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="06390-264">Division of currency values by values of other numeric types can result in different results.</span></span>  
  
### <a name="aggregation-functions"></a><a name="bkmk_Aggregations"></a><span data-ttu-id="06390-265">Funções de agregação</span><span class="sxs-lookup"><span data-stu-id="06390-265">Aggregation functions</span></span>  
<span data-ttu-id="06390-266">As funções estatísticas em uma tabela com uma linha retornam resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="06390-266">Statistical functions on a table with one row return different results.</span></span> <span data-ttu-id="06390-267">As funções de agregação em tabelas vazias também se comportam de modo diferente em modelos na memória e no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="06390-267">Aggregation functions over empty tables also behave differently in in-memory models than they do in DirectQuery mode.</span></span>  
  
<span data-ttu-id="06390-268">**Funções estatísticas em uma tabela com uma única linha**</span><span class="sxs-lookup"><span data-stu-id="06390-268">**Statistical functions over a table with a single row**</span></span>  
<span data-ttu-id="06390-269">se a tabela usada como argumento contiver uma única linha, no modo DirectQuery, as funções estatísticas, como STDEV e VAR, retornam nulo.</span><span class="sxs-lookup"><span data-stu-id="06390-269">If the table that is used as argument contains a single row, in DirectQuery mode, statistical functions such as STDEV and VAR return null.</span></span>  
  
<span data-ttu-id="06390-270">Em um modelo na memória, uma fórmula que usa STDEV ou VAR em uma tabela com uma única linha retorna um erro de divisão por zero.</span><span class="sxs-lookup"><span data-stu-id="06390-270">In an in-memory model, a formula that uses STDEV or VAR over a table with a single row returns a division by zero error.</span></span>  
  
### <a name="text-functions"></a><a name="bkmk_Text"></a><span data-ttu-id="06390-271">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="06390-271">Text functions</span></span>  
<span data-ttu-id="06390-272">Como os repositórios de dados relacionais fornecem tipos de dados de texto diferentes dos do Excel, talvez você veja resultados diferentes ao pesquisar cadeias de caracteres ou trabalhar com subcadeias.</span><span class="sxs-lookup"><span data-stu-id="06390-272">Because relational data stores provide different text data types than does Excel, you may see different results when searching strings or working with substrings.</span></span> <span data-ttu-id="06390-273">O comprimento das cadeias de caracteres também pode ser diferente.</span><span class="sxs-lookup"><span data-stu-id="06390-273">The length of strings also can be different.</span></span>  
  
<span data-ttu-id="06390-274">Em geral, qualquer função de manipulação de cadeia de caracteres que use colunas de tamanho fixo como argumentos pode ter resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="06390-274">In general, any string manipulation functions that use fixed-size columns as arguments can have different results.</span></span>  
  
<span data-ttu-id="06390-275">Além disso, no SQL Server, algumas funções de texto oferecem suporte para argumentos adicionais que não são fornecidos no Excel.</span><span class="sxs-lookup"><span data-stu-id="06390-275">Additionally, in SQL Server, some text functions support additional arguments that are not provided in Excel.</span></span> <span data-ttu-id="06390-276">Se a fórmula exigir o argumento ausente, você poderá obter resultados diferentes ou erros no modelo na memória.</span><span class="sxs-lookup"><span data-stu-id="06390-276">If the formula requires the missing argument you can get different results or errors in the in-memory model.</span></span>  
  
<span data-ttu-id="06390-277">**Operações que retornam um caractere usando LEFT, RIGHT etc. podem retornar o caractere correto, mas com o uso de maiúsculas/minúsculas diferente, ou nenhum resultado**</span><span class="sxs-lookup"><span data-stu-id="06390-277">**Operations that return a character using LEFT, RIGHT, etc. may return the correct character but in a different case, or no results**</span></span>  
<span data-ttu-id="06390-278">EXEMPLO: `LEFT(["text"], 2)`</span><span class="sxs-lookup"><span data-stu-id="06390-278">EXAMPLE: `LEFT(["text"], 2)`</span></span>  
  
<span data-ttu-id="06390-279">No modo DirectQuery, o uso de maiúsculas/minúsculas do caractere retornado sempre é exatamente igual ao da letra armazenada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="06390-279">In DirectQuery mode, the case of the character that is returned is always exactly the same as the letter that is stored in the database.</span></span> <span data-ttu-id="06390-280">No entanto, o mecanismo xVelocity usa um algoritmo diferente para compactação e indexação de valores, para melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="06390-280">However, the xVelocity engine uses a different algorithm for compression and indexing of values, to improve performance.</span></span>  
  
<span data-ttu-id="06390-281">Por padrão, é usada a ordenação Latin1_General, que não diferencia maiúsculas/minúsculas, mas diferencia acentos.</span><span class="sxs-lookup"><span data-stu-id="06390-281">By default, the Latin1_General collation is used, which is case-insensitive but accent-sensitive.</span></span> <span data-ttu-id="06390-282">Portanto, se houver várias instâncias de uma cadeia de caracteres de texto em minúsculas, maiúsculas ou minúsculas/maiúsculas, todas as instâncias serão consideradas a mesma cadeia de caracteres e somente a primeira instância da cadeia de caracteres será armazenada no índice.</span><span class="sxs-lookup"><span data-stu-id="06390-282">Therefore, if there are multiple instances of a text string in lower case, upper case, or mixed case, all instances are considered the same string, and only the first instance of the string is stored in the index.</span></span> <span data-ttu-id="06390-283">Todas as funções de texto que operam em cadeias de caracteres armazenadas recuperarão a parte especificada do formulário indexado.</span><span class="sxs-lookup"><span data-stu-id="06390-283">All text functions that operate on stored strings will retrieve the specified portion of the indexed form.</span></span> <span data-ttu-id="06390-284">Assim, a fórmula de exemplo retornaria o mesmo valor de toda a coluna, usando a primeira instância como a entrada.</span><span class="sxs-lookup"><span data-stu-id="06390-284">Therefore, the example formula would return the same value for the entire column, using the first instance as the input.</span></span>  
  
[<span data-ttu-id="06390-285">Ordenação e armazenamento de cadeia de caracteres em modelos tabulares</span><span class="sxs-lookup"><span data-stu-id="06390-285">String Storage and Collation in Tabular Models</span></span>](https://msdn.microsoft.com/8516f0ad-32ee-4688-a304-e705143642ca)  
  
<span data-ttu-id="06390-286">Esse comportamento também se aplica a outras funções de texto, incluindo RIGHT, MID etc.</span><span class="sxs-lookup"><span data-stu-id="06390-286">This behavior also applies to other text functions, including RIGHT, MID, and so forth.</span></span>  
  
<span data-ttu-id="06390-287">**O comprimento da cadeia de caracteres afeta os resultados**</span><span class="sxs-lookup"><span data-stu-id="06390-287">**String length affects results**</span></span>  
<span data-ttu-id="06390-288">EXEMPLO: `SEARCH("within string", "sample target  text", 1, 1)`</span><span class="sxs-lookup"><span data-stu-id="06390-288">EXAMPLE: `SEARCH("within string", "sample target  text", 1, 1)`</span></span>  
  
<span data-ttu-id="06390-289">Se você procurar uma cadeia de caracteres usando a função SEARCH, e a cadeia de caracteres de destino for maior do que a cadeia de caracteres interna, o modo DirectQuery gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="06390-289">If you search for a string using the SEARCH function, and the target string is longer than the within string, DirectQuery mode raises an error.</span></span>  
  
<span data-ttu-id="06390-290">Em um modelo na memória, a cadeia de caracteres pesquisada é retornada, mas com seu comprimento truncado para o comprimento do &lt;texto interno&gt;.</span><span class="sxs-lookup"><span data-stu-id="06390-290">In an in-memory model, the searched string is returned, but with its length truncated to the length of &lt;within text&gt;.</span></span>  
  
<span data-ttu-id="06390-291">EXEMPLO: `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span><span class="sxs-lookup"><span data-stu-id="06390-291">EXAMPLE: `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span></span>  
  
<span data-ttu-id="06390-292">Se o comprimento da cadeia de caracteres de substituição for maior que o comprimento da cadeia de caracteres original, no modo DirectQuery, a fórmula retornará nulo.</span><span class="sxs-lookup"><span data-stu-id="06390-292">If the length of the replacement string is greater than the length of the original string, in DirectQuery mode, the formula returns null.</span></span>  
  
<span data-ttu-id="06390-293">Em modelos na memória, a fórmula seguirá o comportamento do Excel, que concatena a cadeia de caracteres de origem e a cadeia de caracteres de substituição, que retorna CACalifornia.</span><span class="sxs-lookup"><span data-stu-id="06390-293">In in-memory models, the formula follows the behavior of Excel, which concatenates the source string and the replacement string, which returns CACalifornia.</span></span>  
  
<span data-ttu-id="06390-294">**TRIM implícito no meio das cadeias de caracteres**</span><span class="sxs-lookup"><span data-stu-id="06390-294">**Implicit TRIM in the middle of strings**</span></span>  
<span data-ttu-id="06390-295">EXEMPLO: `TRIM(" A sample sentence with leading white space")`</span><span class="sxs-lookup"><span data-stu-id="06390-295">EXAMPLE: `TRIM(" A sample sentence with leading white space")`</span></span>  
  
<span data-ttu-id="06390-296">O modo DirectQuery traduz a função DAX TRIM na instrução SQL `LTRIM(RTRIM(<column>))`.</span><span class="sxs-lookup"><span data-stu-id="06390-296">DirectQuery mode translates the DAX TRIM function to the SQL statement `LTRIM(RTRIM(<column>))`.</span></span> <span data-ttu-id="06390-297">Assim, somente os espaços em branco à esquerda e à direita são removidos.</span><span class="sxs-lookup"><span data-stu-id="06390-297">As a result, only leading and trailing white space is removed.</span></span>  
  
<span data-ttu-id="06390-298">Em contrapartida, a mesma fórmula em um modelo na memória remove espaços na cadeia de caracteres, de acordo com o comportamento do Excel.</span><span class="sxs-lookup"><span data-stu-id="06390-298">In contrast, the same formula in an in-memory model removes spaces within the string, following the behavior of Excel.</span></span>  
  
<span data-ttu-id="06390-299">**RTRIM implícito com o uso da função LEN**</span><span class="sxs-lookup"><span data-stu-id="06390-299">**Implicit RTRIM with use of LEN function**</span></span>  
<span data-ttu-id="06390-300">EXEMPLO: `LEN('string_column')`</span><span class="sxs-lookup"><span data-stu-id="06390-300">EXAMPLE: `LEN('string_column')`</span></span>  
  
<span data-ttu-id="06390-301">Como o SQL Server, o modo DirectQuery remove automaticamente o espaço em branco da extremidade das colunas de cadeia de caracteres: ou seja, ele executa um RTRIM implícito.</span><span class="sxs-lookup"><span data-stu-id="06390-301">Like SQL Server, DirectQuery mode automatically removes white space from the end of string columns: that is, it performs an implicit RTRIM.</span></span> <span data-ttu-id="06390-302">Assim, as fórmulas que usam a função LEN poderão retornar valores diferentes se a cadeia de caracteres tiver espaços à direita.</span><span class="sxs-lookup"><span data-stu-id="06390-302">Therefore, formulas that use the LEN function can return different values if the string has trailing spaces.</span></span>  
  
<span data-ttu-id="06390-303">**O modo Na Memória tem suporte para parâmetros adicionais para SUBSTITUTE**</span><span class="sxs-lookup"><span data-stu-id="06390-303">**In-memory supports additional parameters for SUBSTITUTE**</span></span>  
<span data-ttu-id="06390-304">EXEMPLO: `SUBSTITUTE([Title],"Doctor","Dr.")`</span><span class="sxs-lookup"><span data-stu-id="06390-304">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.")`</span></span>  
  
<span data-ttu-id="06390-305">EXEMPLO: `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span><span class="sxs-lookup"><span data-stu-id="06390-305">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span></span>  
  
<span data-ttu-id="06390-306">No modo DirectQuery, você pode usar apenas a versão dessa função que tem três (3) parâmetros: uma referência a uma coluna, o texto antigo e o novo texto.</span><span class="sxs-lookup"><span data-stu-id="06390-306">In DirectQuery mode, you can use only the version of this function that has three (3) parameters: a reference to a column, the old text, and the new text.</span></span> <span data-ttu-id="06390-307">Se você usar a segunda fórmula, um erro será gerado.</span><span class="sxs-lookup"><span data-stu-id="06390-307">If you use the second formula, an error is raised.</span></span>  
  
<span data-ttu-id="06390-308">Em modelos na memória, você pode usar um quarto parâmetro opcional para especificar o número da instância da cadeia de caracteres a ser substituída.</span><span class="sxs-lookup"><span data-stu-id="06390-308">In in-memory models, you can use an optional fourth parameter to specify the instance number of the string to replace.</span></span> <span data-ttu-id="06390-309">Por exemplo, você pode substituir apenas a segunda instância etc.</span><span class="sxs-lookup"><span data-stu-id="06390-309">For example, you can replace only the second instance, etc.</span></span>  
  
<span data-ttu-id="06390-310">**Restrições em comprimentos de cadeia de caracteres para operações REPT**</span><span class="sxs-lookup"><span data-stu-id="06390-310">**Restrictions on string lengths for REPT operations**</span></span>  
<span data-ttu-id="06390-311">Em modelos na memória, o comprimento de uma cadeia de caracteres resultante de uma operação usando REPT deve ser inferior a 32.767 caracteres.</span><span class="sxs-lookup"><span data-stu-id="06390-311">In in-memory models, the length of a string resulting from an operation using REPT must be less than 32,767 characters.</span></span>  
  
<span data-ttu-id="06390-312">Essa limitação não se aplica no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="06390-312">This limitation does not apply in DirectQuery mode.</span></span>  
  
<span data-ttu-id="06390-313">**As operações de subcadeia retornam resultados diferentes, dependendo do tipo de caractere**</span><span class="sxs-lookup"><span data-stu-id="06390-313">**Substring operations return different results depending on character type**</span></span>  
<span data-ttu-id="06390-314">EXEMPLO: `MID([col], 2, 5)`</span><span class="sxs-lookup"><span data-stu-id="06390-314">EXAMPLE: `MID([col], 2, 5)`</span></span>  
  
<span data-ttu-id="06390-315">Se o texto de entrada for **varchar** ou **nvarchar**, o resultado da fórmula sempre será o mesmo.</span><span class="sxs-lookup"><span data-stu-id="06390-315">If the input text is **varchar** or **nvarchar**, the result of the formula is always the same.</span></span>  
  
<span data-ttu-id="06390-316">No entanto, se o texto for um caractere de comprimento fixo e o valor de \* &lt; num_chars &gt; \* for maior que o comprimento da cadeia de caracteres de destino, no modo DirectQuery, um espaço em branco será adicionado ao final da cadeia de caracteres de resultado.</span><span class="sxs-lookup"><span data-stu-id="06390-316">However, if the text is a fixed-length character and the value for *&lt;num_chars&gt;* is greater than the length of the target string, in DirectQuery mode, a blank is added at the end of the result string.</span></span>  
  
<span data-ttu-id="06390-317">Em um modelo na memória, o resultado termina no último caractere da cadeia de caracteres, sem preenchimento.</span><span class="sxs-lookup"><span data-stu-id="06390-317">In an in-memory model, the result terminates at the last string character, with no padding.</span></span>  
  
## <a name="functions-supported-in-directquery-mode"></a><a name="bkmk_SupportedFunc"></a><span data-ttu-id="06390-318">Funções com suporte no modo DirectQuery</span><span class="sxs-lookup"><span data-stu-id="06390-318">Functions supported in DirectQuery mode</span></span>  
<span data-ttu-id="06390-319">As funções DAX a seguir podem ser usadas no modo DirectQuery, mas com as qualificações conforme descrito na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="06390-319">The following DAX functions can be used in DirectQuery mode, but with the qualifications as described in the preceding section.</span></span>  
  
<span data-ttu-id="06390-320">**Funções de texto**</span><span class="sxs-lookup"><span data-stu-id="06390-320">**Text functions**</span></span>  
  
<span data-ttu-id="06390-321">CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="06390-321">CONCATENATE</span></span>  
  
<span data-ttu-id="06390-322">FIND</span><span class="sxs-lookup"><span data-stu-id="06390-322">FIND</span></span>  
  
<span data-ttu-id="06390-323">LEFT</span><span class="sxs-lookup"><span data-stu-id="06390-323">LEFT</span></span>  
  
<span data-ttu-id="06390-324">LEN</span><span class="sxs-lookup"><span data-stu-id="06390-324">LEN</span></span>  
  
<span data-ttu-id="06390-325">MID</span><span class="sxs-lookup"><span data-stu-id="06390-325">MID</span></span>  
  
<span data-ttu-id="06390-326">REPLACE</span><span class="sxs-lookup"><span data-stu-id="06390-326">REPLACE</span></span>  
  
<span data-ttu-id="06390-327">REPT</span><span class="sxs-lookup"><span data-stu-id="06390-327">REPT</span></span>  
  
<span data-ttu-id="06390-328">RIGHT</span><span class="sxs-lookup"><span data-stu-id="06390-328">RIGHT</span></span>  
  
<span data-ttu-id="06390-329">SUBSTITUTE</span><span class="sxs-lookup"><span data-stu-id="06390-329">SUBSTITUTE</span></span>  
  
<span data-ttu-id="06390-330">TRIM</span><span class="sxs-lookup"><span data-stu-id="06390-330">TRIM</span></span>  
  
<span data-ttu-id="06390-331">**Funções estatísticas**</span><span class="sxs-lookup"><span data-stu-id="06390-331">**Statistical functions**</span></span>  
  
<span data-ttu-id="06390-332">COUNT</span><span class="sxs-lookup"><span data-stu-id="06390-332">COUNT</span></span>  
  
<span data-ttu-id="06390-333">STDEV.P</span><span class="sxs-lookup"><span data-stu-id="06390-333">STDEV.P</span></span>  
  
<span data-ttu-id="06390-334">STDEV.S</span><span class="sxs-lookup"><span data-stu-id="06390-334">STDEV.S</span></span>  
  
<span data-ttu-id="06390-335">STDEVX.P</span><span class="sxs-lookup"><span data-stu-id="06390-335">STDEVX.P</span></span>  
  
<span data-ttu-id="06390-336">STDEVX.S</span><span class="sxs-lookup"><span data-stu-id="06390-336">STDEVX.S</span></span>  
  
<span data-ttu-id="06390-337">VAR.P</span><span class="sxs-lookup"><span data-stu-id="06390-337">VAR.P</span></span>  
  
<span data-ttu-id="06390-338">VAR.S</span><span class="sxs-lookup"><span data-stu-id="06390-338">VAR.S</span></span>  
  
<span data-ttu-id="06390-339">VARX.P</span><span class="sxs-lookup"><span data-stu-id="06390-339">VARX.P</span></span>  
  
<span data-ttu-id="06390-340">VARX.S</span><span class="sxs-lookup"><span data-stu-id="06390-340">VARX.S</span></span>  
  
<span data-ttu-id="06390-341">**Funções de data/hora**</span><span class="sxs-lookup"><span data-stu-id="06390-341">**Date/time functions**</span></span>  
  
<span data-ttu-id="06390-342">DATE</span><span class="sxs-lookup"><span data-stu-id="06390-342">DATE</span></span>  
  
<span data-ttu-id="06390-343">EDATE</span><span class="sxs-lookup"><span data-stu-id="06390-343">EDATE</span></span>  
  
<span data-ttu-id="06390-344">EOMONTH</span><span class="sxs-lookup"><span data-stu-id="06390-344">EOMONTH</span></span>  
  
<span data-ttu-id="06390-345">DATE</span><span class="sxs-lookup"><span data-stu-id="06390-345">DATE</span></span>  
  
<span data-ttu-id="06390-346">TIME</span><span class="sxs-lookup"><span data-stu-id="06390-346">TIME</span></span>  
  
<span data-ttu-id="06390-347">SECOND</span><span class="sxs-lookup"><span data-stu-id="06390-347">SECOND</span></span>  
  
<span data-ttu-id="06390-348">**Funções matemáticas e numéricas**</span><span class="sxs-lookup"><span data-stu-id="06390-348">**Math and number functions**</span></span>  
  
<span data-ttu-id="06390-349">CEILING</span><span class="sxs-lookup"><span data-stu-id="06390-349">CEILING</span></span>  
  
<span data-ttu-id="06390-350">LN</span><span class="sxs-lookup"><span data-stu-id="06390-350">LN</span></span>  
  
<span data-ttu-id="06390-351">LOG</span><span class="sxs-lookup"><span data-stu-id="06390-351">LOG</span></span>  
  
<span data-ttu-id="06390-352">LOG10</span><span class="sxs-lookup"><span data-stu-id="06390-352">LOG10</span></span>  
  
<span data-ttu-id="06390-353">POWER</span><span class="sxs-lookup"><span data-stu-id="06390-353">POWER</span></span>  
  
<span data-ttu-id="06390-354">**Consultas de tabela DAX**</span><span class="sxs-lookup"><span data-stu-id="06390-354">**DAX Table queries**</span></span>  
  
<span data-ttu-id="06390-355">Há algumas limitações quando você avalia fórmulas em relação a um modelo DirectQuery usando consultas de Tabela DAX.</span><span class="sxs-lookup"><span data-stu-id="06390-355">There are some limitations when you evaluate formulas against a DirectQuery model by using DAX Table queries.</span></span> <span data-ttu-id="06390-356">O DirectQuery não oferece suporte para referenciar a mesma coluna duas vezes em uma cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="06390-356">DirectQuery does not support referring to the same column twice in an ORDER BY clause.</span></span> <span data-ttu-id="06390-357">A instrução Transact-SQL equivalente não pode ser criada e a consulta falha.</span><span class="sxs-lookup"><span data-stu-id="06390-357">The equivalent Transact-SQL statement cannot be created and the query fails.</span></span>  
  
<span data-ttu-id="06390-358">Em um modelo na memória, a repetição da cláusula ORDER BY não tem nenhum efeito nos resultados.</span><span class="sxs-lookup"><span data-stu-id="06390-358">In an in-memory model, repeating the ORDER by clause has no effect on the results.</span></span>  
  
## <a name="functions-not-supported-in-directquery-mode"></a><a name="bkmk_NotSupportedFunc"></a><span data-ttu-id="06390-359">Funções sem suporte no modo DirectQuery</span><span class="sxs-lookup"><span data-stu-id="06390-359">Functions not supported in DirectQuery Mode</span></span>  
<span data-ttu-id="06390-360">Algumas funções DAX não têm suporte em modelos implantados no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="06390-360">Some DAX functions are not supported in models that are deployed in DirectQuery mode.</span></span> <span data-ttu-id="06390-361">Os motivos para uma determinada função não ter suporte podem incluir um ou todos estes:</span><span class="sxs-lookup"><span data-stu-id="06390-361">The reasons that a particular function is not supported can include any or a combination of these reasons:</span></span>  
  
-   <span data-ttu-id="06390-362">O mecanismo relacional subjacente não pode executar cálculos equivalentes àqueles executados pelo mecanismo xVelocity.</span><span class="sxs-lookup"><span data-stu-id="06390-362">The underlying relational engine cannot perform calculations equivalent to those performed by the xVelocity engine.</span></span>  
  
-   <span data-ttu-id="06390-363">A fórmula não pode ser convertida em uma expressão SQL equivalente.</span><span class="sxs-lookup"><span data-stu-id="06390-363">The formula cannot be converted to en equivalent SQL expression.</span></span>  
  
-   <span data-ttu-id="06390-364">O desempenho da expressão convertida e dos cálculos resultantes seria inaceitável.</span><span class="sxs-lookup"><span data-stu-id="06390-364">The performance of the converted expression and the resulting calculations would be unacceptable.</span></span>  
  
<span data-ttu-id="06390-365">As funções DAX a seguir não podem ser usadas nos modelos DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="06390-365">The following DAX functions cannot be used in DirectQuery models.</span></span>  
  
<span data-ttu-id="06390-366">**Funções de caminho**</span><span class="sxs-lookup"><span data-stu-id="06390-366">**Path functions**</span></span>  
  
<span data-ttu-id="06390-367">PATH</span><span class="sxs-lookup"><span data-stu-id="06390-367">PATH</span></span>  
  
<span data-ttu-id="06390-368">PATHCONTAINS</span><span class="sxs-lookup"><span data-stu-id="06390-368">PATHCONTAINS</span></span>  
  
<span data-ttu-id="06390-369">PATHITEM</span><span class="sxs-lookup"><span data-stu-id="06390-369">PATHITEM</span></span>  
  
<span data-ttu-id="06390-370">PATHITEMREVERSE</span><span class="sxs-lookup"><span data-stu-id="06390-370">PATHITEMREVERSE</span></span>  
  
<span data-ttu-id="06390-371">PATHLENGTH</span><span class="sxs-lookup"><span data-stu-id="06390-371">PATHLENGTH</span></span>  
  
<span data-ttu-id="06390-372">**Funções diversas**</span><span class="sxs-lookup"><span data-stu-id="06390-372">**Misc functions**</span></span>  
  
<span data-ttu-id="06390-373">COUNTBLANK</span><span class="sxs-lookup"><span data-stu-id="06390-373">COUNTBLANK</span></span>  
  
<span data-ttu-id="06390-374">FIXED</span><span class="sxs-lookup"><span data-stu-id="06390-374">FIXED</span></span>  
  
<span data-ttu-id="06390-375">FORMAT</span><span class="sxs-lookup"><span data-stu-id="06390-375">FORMAT</span></span>  
  
<span data-ttu-id="06390-376">RAND</span><span class="sxs-lookup"><span data-stu-id="06390-376">RAND</span></span>  
  
<span data-ttu-id="06390-377">RANDBETWEEN</span><span class="sxs-lookup"><span data-stu-id="06390-377">RANDBETWEEN</span></span>  
  
<span data-ttu-id="06390-378">**Funções de inteligência de dados temporais: datas de início e término**</span><span class="sxs-lookup"><span data-stu-id="06390-378">**Time intelligence functions: Start and end dates**</span></span>  
  
<span data-ttu-id="06390-379">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="06390-379">DATESQTD</span></span>  
  
<span data-ttu-id="06390-380">DATESYTD</span><span class="sxs-lookup"><span data-stu-id="06390-380">DATESYTD</span></span>  
  
<span data-ttu-id="06390-381">DATESMTD</span><span class="sxs-lookup"><span data-stu-id="06390-381">DATESMTD</span></span>  
  
<span data-ttu-id="06390-382">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="06390-382">DATESQTD</span></span>  
  
<span data-ttu-id="06390-383">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="06390-383">DATESINPERIOD</span></span>  
  
<span data-ttu-id="06390-384">TOTALMTD</span><span class="sxs-lookup"><span data-stu-id="06390-384">TOTALMTD</span></span>  
  
<span data-ttu-id="06390-385">TOTALQTD</span><span class="sxs-lookup"><span data-stu-id="06390-385">TOTALQTD</span></span>  
  
<span data-ttu-id="06390-386">TOTALYTD</span><span class="sxs-lookup"><span data-stu-id="06390-386">TOTALYTD</span></span>  
  
<span data-ttu-id="06390-387">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="06390-387">DATESINPERIOD</span></span>  
  
<span data-ttu-id="06390-388">SAMEPERIODLASTYEAR</span><span class="sxs-lookup"><span data-stu-id="06390-388">SAMEPERIODLASTYEAR</span></span>  
  
<span data-ttu-id="06390-389">PARALLELPERIOD</span><span class="sxs-lookup"><span data-stu-id="06390-389">PARALLELPERIOD</span></span>  
  
<span data-ttu-id="06390-390">**Funções de inteligência de tempo: saldos**</span><span class="sxs-lookup"><span data-stu-id="06390-390">**Time-intelligence functions: Balances**</span></span>  
  
<span data-ttu-id="06390-391">OPENINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="06390-391">OPENINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="06390-392">OPENINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="06390-392">OPENINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="06390-393">OPENINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="06390-393">OPENINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="06390-394">CLOSINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="06390-394">CLOSINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="06390-395">CLOSINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="06390-395">CLOSINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="06390-396">CLOSINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="06390-396">CLOSINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="06390-397">**Funções de inteligência de dados temporais: período anterior e próximo período**</span><span class="sxs-lookup"><span data-stu-id="06390-397">**Time intelligence functions: Previous and next periods**</span></span>  
  
<span data-ttu-id="06390-398">PREVIOUSDAY</span><span class="sxs-lookup"><span data-stu-id="06390-398">PREVIOUSDAY</span></span>  
  
<span data-ttu-id="06390-399">PREVIOUSMONTH</span><span class="sxs-lookup"><span data-stu-id="06390-399">PREVIOUSMONTH</span></span>  
  
<span data-ttu-id="06390-400">PREVIOUSQUARTER</span><span class="sxs-lookup"><span data-stu-id="06390-400">PREVIOUSQUARTER</span></span>  
  
<span data-ttu-id="06390-401">PREVIOUSYEAR</span><span class="sxs-lookup"><span data-stu-id="06390-401">PREVIOUSYEAR</span></span>  
  
<span data-ttu-id="06390-402">NEXTDAY</span><span class="sxs-lookup"><span data-stu-id="06390-402">NEXTDAY</span></span>  
  
<span data-ttu-id="06390-403">NEXTMONTH</span><span class="sxs-lookup"><span data-stu-id="06390-403">NEXTMONTH</span></span>  
  
<span data-ttu-id="06390-404">NEXTQUARTER</span><span class="sxs-lookup"><span data-stu-id="06390-404">NEXTQUARTER</span></span>  
  
<span data-ttu-id="06390-405">NEXTYEAR</span><span class="sxs-lookup"><span data-stu-id="06390-405">NEXTYEAR</span></span>  
  
<span data-ttu-id="06390-406">**Funções de inteligência de dados temporais: períodos e cálculos sobre períodos**</span><span class="sxs-lookup"><span data-stu-id="06390-406">**Time intelligence functions: Periods and calculations over periods**</span></span>  
  
<span data-ttu-id="06390-407">STARTOFMONTH</span><span class="sxs-lookup"><span data-stu-id="06390-407">STARTOFMONTH</span></span>  
  
<span data-ttu-id="06390-408">STARTOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="06390-408">STARTOFQUARTER</span></span>  
  
<span data-ttu-id="06390-409">STARTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="06390-409">STARTOFYEAR</span></span>  
  
<span data-ttu-id="06390-410">ENDOFMONTH</span><span class="sxs-lookup"><span data-stu-id="06390-410">ENDOFMONTH</span></span>  
  
<span data-ttu-id="06390-411">ENDOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="06390-411">ENDOFQUARTER</span></span>  
  
<span data-ttu-id="06390-412">ENDOFYEAR</span><span class="sxs-lookup"><span data-stu-id="06390-412">ENDOFYEAR</span></span>  
  
<span data-ttu-id="06390-413">FIRSTDATE</span><span class="sxs-lookup"><span data-stu-id="06390-413">FIRSTDATE</span></span>  
  
<span data-ttu-id="06390-414">LASTDATE</span><span class="sxs-lookup"><span data-stu-id="06390-414">LASTDATE</span></span>  
  
<span data-ttu-id="06390-415">DATEADD</span><span class="sxs-lookup"><span data-stu-id="06390-415">DATEADD</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06390-416">Confira também</span><span class="sxs-lookup"><span data-stu-id="06390-416">See also</span></span>  
[<span data-ttu-id="06390-417">Modo DirectQuery (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="06390-417">DirectQuery Mode (SSAS Tabular)</span></span>](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5)  
  

