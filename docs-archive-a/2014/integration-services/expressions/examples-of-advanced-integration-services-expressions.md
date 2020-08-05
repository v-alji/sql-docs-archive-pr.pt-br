---
title: Exemplos de expressões avançadas do Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- functions [Integration Services]
- operators [Integration Services]
- expressions [Integration Services], examples
- examples [Integration Services]
ms.assetid: c7794ba3-0de5-466b-ae8a-9ddd27360049
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb1e8dc6f9bffd22c917414f80f6ba9f257b25b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573220"
---
# <a name="examples-of-advanced-integration-services-expressions"></a><span data-ttu-id="21423-102">Exemplos de expressões avançadas do Integration Services</span><span class="sxs-lookup"><span data-stu-id="21423-102">Examples of Advanced Integration Services Expressions</span></span>
  <span data-ttu-id="21423-103">Esta seção fornece exemplos de expressões avançadas que combinam múltiplos operadores e funções.</span><span class="sxs-lookup"><span data-stu-id="21423-103">This section provides examples of advanced expressions that combine multiple operators and functions.</span></span> <span data-ttu-id="21423-104">Se uma expressão for usada em uma restrição precedente ou na transformação Divisão Condicional, ela deve ser avaliada como uma expressão Booleana.</span><span class="sxs-lookup"><span data-stu-id="21423-104">If an expression is used in a precedence constraint or the Conditional Split transformation, it must evaluate to a Boolean.</span></span> <span data-ttu-id="21423-105">No entanto, essa restrição não se aplica a expressões usadas em expressões de propriedades, variáveis, na transformação Coluna Derivada ou no contêiner Loop For.</span><span class="sxs-lookup"><span data-stu-id="21423-105">That restriction, however, does not apply to expressions used in property expressions, variables, the Derived Column transformation, or the For Loop container.</span></span>  
  
 <span data-ttu-id="21423-106">Os exemplos a seguir usam os bancos de dados **AdventureWorks** e bancos de dados [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)][!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21423-106">The following examples use the **AdventureWorks** and the [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)][!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="21423-107">Cada exemplo identifica as tabelas que usa.</span><span class="sxs-lookup"><span data-stu-id="21423-107">Each example identifies the tables it uses.</span></span>  
  
## <a name="boolean-expressions"></a><span data-ttu-id="21423-108">Expressões boolianas</span><span class="sxs-lookup"><span data-stu-id="21423-108">Boolean Expressions</span></span>  
  
-   <span data-ttu-id="21423-109">Este exemplo usa a tabela **Product** .</span><span class="sxs-lookup"><span data-stu-id="21423-109">This example uses the **Product** table.</span></span> <span data-ttu-id="21423-110">A expressão avaliará a entrada do mês na coluna **SellStartDate** e retornará TRUE se o mês for junho ou posterior.</span><span class="sxs-lookup"><span data-stu-id="21423-110">The expression evaluates the month entry in the **SellStartDate** column and returns TRUE if the month is June or later.</span></span>  
  
    ```  
    DATEPART("mm",SellStartDate) > 6  
    ```  
  
-   <span data-ttu-id="21423-111">Este exemplo usa a tabela **Product** .</span><span class="sxs-lookup"><span data-stu-id="21423-111">This example uses the **Product** table.</span></span> <span data-ttu-id="21423-112">A expressão avaliará o resultado arredondado da divisão da coluna **ListPrice** pela coluna **StandardCost** e retornará TRUE se o resultado for maior que 1,5.</span><span class="sxs-lookup"><span data-stu-id="21423-112">The expression evaluates the rounded result of dividing the **ListPrice** column by the **StandardCost** column, and returns TRUE if the result is greater than 1.5.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) > 1.50  
    ```  
  
-   <span data-ttu-id="21423-113">Este exemplo usa a tabela **Product** .</span><span class="sxs-lookup"><span data-stu-id="21423-113">This example uses the **Product** table.</span></span> <span data-ttu-id="21423-114">A expressão retornará TRUE se todas as três operações forem avaliadas como TRUE.</span><span class="sxs-lookup"><span data-stu-id="21423-114">The expression returns TRUE if all three operations evaluate to TRUE.</span></span> <span data-ttu-id="21423-115">Se a coluna **Size** e a variável **BikeSize** tiverem tipos de dados incompatíveis, a expressão exigirá uma conversão explícita conforme demonstra o segundo exemplo.</span><span class="sxs-lookup"><span data-stu-id="21423-115">If the **Size** column and the **BikeSize** variable have incompatible data types, the expression requires an explicit cast as shown the second example.</span></span> <span data-ttu-id="21423-116">A conversão para DT_WSTR inclui o comprimento da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="21423-116">The cast to DT_WSTR includes the length of the string.</span></span>  
  
    ```  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE && Size != @BikeSize  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE  && Size != (DT_WSTR,10)@BikeSize  
    ```  
  
-   <span data-ttu-id="21423-117">Este exemplo usa a tabela **CurrencyRate** .</span><span class="sxs-lookup"><span data-stu-id="21423-117">This example uses the **CurrencyRate** table.</span></span> <span data-ttu-id="21423-118">A expressão compara valores em tabelas e variáveis.</span><span class="sxs-lookup"><span data-stu-id="21423-118">The expression compares values in tables and variables.</span></span> <span data-ttu-id="21423-119">Ela retornará TRUE se as entradas nas colunas **FromCurrencyCode** ou **ToCurrencyCode** forem iguais a valores variáveis e se o valor em **AverageRate** for maior do que o valor em **EndOfDayRate**.</span><span class="sxs-lookup"><span data-stu-id="21423-119">It returns TRUE if entries in the **FromCurrencyCode** or **ToCurrencyCode** columns are equal to variable values and if the value in **AverageRate** is greater that the value in **EndOfDayRate**.</span></span>  
  
    ```  
    (FromCurrencyCode == @FromCur || ToCurrencyCode == @ToCur) && AverageRate > EndOfDayRate  
    ```  
  
-   <span data-ttu-id="21423-120">Este exemplo usa a tabela **Currency** .</span><span class="sxs-lookup"><span data-stu-id="21423-120">This example uses the **Currency** table.</span></span> <span data-ttu-id="21423-121">A expressão retornará TRUE se o primeiro caractere na coluna **Name** não for a ou A.</span><span class="sxs-lookup"><span data-stu-id="21423-121">The expression returns TRUE if the first character in the **Name** column is not a or A.</span></span>  
  
    ```  
    SUBSTRING(UPPER(Name),1,1) != "A"  
    ```  
  
     <span data-ttu-id="21423-122">A expressão a seguir fornece os mesmos resultados, mas é mais eficiente porque somente um caractere é convertido em maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="21423-122">The following expression provides the same results, but it is more efficient because only one character is converted to uppercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Name,1,1)) != "A"  
    ```  
  
## <a name="non-boolean-expressions"></a><span data-ttu-id="21423-123">Expressões não Booleanas</span><span class="sxs-lookup"><span data-stu-id="21423-123">Non-Boolean Expressions</span></span>  
 <span data-ttu-id="21423-124">Expressões não Booleanas são usadas na transformação Coluna Derivada, expressões de propriedade e no contêiner Loop For.</span><span class="sxs-lookup"><span data-stu-id="21423-124">Non-Boolean expressions are used in the Derived Column transformation, property expressions, and the For Loop container.</span></span>  
  
-   <span data-ttu-id="21423-125">Este exemplo usa a tabela **Contato** .</span><span class="sxs-lookup"><span data-stu-id="21423-125">This example uses the **Contact** table.</span></span> <span data-ttu-id="21423-126">A expressão remove os espaços à esquerda e à direita das colunas **FirstName**, **MiddleName**e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="21423-126">The expression removes leading and trailing spaces from the **FirstName**, **MiddleName**, and **LastName** columns.</span></span> <span data-ttu-id="21423-127">Ela extrairá a primeira letra da coluna **MiddleName** se não for nula, concatenará a inicial do segundo nome e os valores em **FirstName** e **LastName**e inserirá os espaços apropriados entre os valores.</span><span class="sxs-lookup"><span data-stu-id="21423-127">It extracts the first letter of the **MiddleName** column if it is not null, concatenates the middle initial and the values in **FirstName** and **LastName**, and inserts appropriate spaces between values.</span></span>  
  
    ```  
    TRIM(FirstName) + " " + (!ISNULL(MiddleName) ? SUBSTRING(MiddleName,1,1) + " " : "") + TRIM(LastName)  
    ```  
  
-   <span data-ttu-id="21423-128">Este exemplo usa a tabela **Contato** .</span><span class="sxs-lookup"><span data-stu-id="21423-128">This example uses the **Contact** table.</span></span> <span data-ttu-id="21423-129">A expressão valida entradas na coluna **Salutation** .</span><span class="sxs-lookup"><span data-stu-id="21423-129">The expression validates entries in the **Salutation** column.</span></span> <span data-ttu-id="21423-130">Retorna uma entrada **Salutation** ou uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="21423-130">It returns a **Salutation** entry or an empty string.</span></span>  
  
    ```  
    (Salutation == "Sr." || Salutation == "Ms." || Salutation == "Sra." || Salutation == "Mr.") ? Salutation : ""  
    ```  
  
-   <span data-ttu-id="21423-131">Este exemplo usa a tabela **Product** .</span><span class="sxs-lookup"><span data-stu-id="21423-131">This example uses the **Product** table.</span></span> <span data-ttu-id="21423-132">A expressão converte o primeiro caractere na coluna **Color** em maiúscula e converte os caracteres restantes em minúsculas.</span><span class="sxs-lookup"><span data-stu-id="21423-132">The expression converts the first character in the **Color** column to uppercase and converts remaining characters to lowercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Color,1,1)) + LOWER(SUBSTRING(Color,2,15))  
    ```  
  
-   <span data-ttu-id="21423-133">Este exemplo usa a tabela **Product** .</span><span class="sxs-lookup"><span data-stu-id="21423-133">This example uses the **Product** table.</span></span> <span data-ttu-id="21423-134">A expressão calculará o número de meses em que um produto foi vendido e retornará a cadeia de caracteres “Desconhecido” se a coluna **SellStartDate** ou a coluna **SellEndDate** contiver NULL.</span><span class="sxs-lookup"><span data-stu-id="21423-134">The expression calculates the number of months a product has been sold and returns the string "Unknown" if either the **SellStartDate** or the **SellEndDate** column contains NULL.</span></span>  
  
    ```  
    !(ISNULL(SellStartDate)) && !(ISNULL(SellEndDate)) ? (DT_WSTR,2)DATEDIFF("mm",SellStartDate,SellEndDate) : "Unknown"  
    ```  
  
-   <span data-ttu-id="21423-135">Este exemplo usa a tabela **Product** .</span><span class="sxs-lookup"><span data-stu-id="21423-135">This example uses the **Product** table.</span></span> <span data-ttu-id="21423-136">A expressão calcula a marcação na coluna **StandardCost** e arredonda o resultado a uma precisão de dois.</span><span class="sxs-lookup"><span data-stu-id="21423-136">The expression calculates the markup on the **StandardCost** column and rounds the result to a precision of two.</span></span> <span data-ttu-id="21423-137">O resultado é apresentado como uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="21423-137">The result is presented as a percentage.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) * 100  
    ```  
  
## <a name="related-tasks"></a><span data-ttu-id="21423-138">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="21423-138">Related Tasks</span></span>  
 [<span data-ttu-id="21423-139">Usar uma expressão em um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="21423-139">Use an Expression in a Data Flow Component</span></span>](../use-an-expression-in-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="21423-140">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="21423-140">Related Content</span></span>  
 <span data-ttu-id="21423-141">Artigo técnico, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet), em pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="21423-141">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet), on pragmaticworks.com</span></span>  
  
  
