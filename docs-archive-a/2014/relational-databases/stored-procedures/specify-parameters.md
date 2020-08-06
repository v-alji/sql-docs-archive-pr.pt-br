---
title: Especificar parâmetros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- parameters [SQL Server], stored procedures
- stored procedures [SQL Server], parameters
- output parameters [SQL Server]
- input parameters [SQL Server]
ms.assetid: 902314fe-5f9c-4d0d-a0b7-27e67c9c70ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: d93a04281839c4db26cbab16ac166af3cdb7c9a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584098"
---
# <a name="specify-parameters"></a><span data-ttu-id="182cc-102">Especificar parâmetros</span><span class="sxs-lookup"><span data-stu-id="182cc-102">Specify Parameters</span></span>
  <span data-ttu-id="182cc-103">Ao especificar parâmetros de procedimento, programas de chamada podem passar valores para o corpo do procedimento.</span><span class="sxs-lookup"><span data-stu-id="182cc-103">By specifying procedure parameters, calling programs are able to pass values into the body of the procedure.</span></span> <span data-ttu-id="182cc-104">Esses valores podem ser usados com vários propósitos durante a execução do procedimento.</span><span class="sxs-lookup"><span data-stu-id="182cc-104">Those values can be used for a variety of purposes during procedure execution.</span></span> <span data-ttu-id="182cc-105">Parâmetros de procedimento também retornam valores ao programa de chamada quando o parâmetro é marcado como um parâmetro OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="182cc-105">Procedure parameters can also return values to the calling program if the parameter is marked as an OUTPUT parameter.</span></span>  
  
 <span data-ttu-id="182cc-106">Um procedimento pode ter no máximo 2100 parâmetros; a cada um é atribuído um nome, um tipo de dados e uma direção.</span><span class="sxs-lookup"><span data-stu-id="182cc-106">A procedure can have a maximum of 2100 parameters; each assigned a name, data type, and direction.</span></span> <span data-ttu-id="182cc-107">Outra opção é atribuir valores padrão aos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="182cc-107">Optionally, parameters can be assigned default values.</span></span>  
  
 <span data-ttu-id="182cc-108">A seção a seguir fornece informações sobre como passar valores para parâmetros e como cada atributo de parâmetro é usado durante uma chamada de procedimento.</span><span class="sxs-lookup"><span data-stu-id="182cc-108">The following section provides information about passing values into parameters and about how each of the parameter attributes is used during a procedure call.</span></span>  
  
## <a name="passing-values-into-parameters"></a><span data-ttu-id="182cc-109">Passando valores para parâmetros</span><span class="sxs-lookup"><span data-stu-id="182cc-109">Passing Values into Parameters</span></span>  
 <span data-ttu-id="182cc-110">Os valores de parâmetros fornecidos com uma chamada de procedimento devem ser constantes ou uma variável; um nome de função não pode ser usado como um valor de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="182cc-110">The parameter values supplied with a procedure call must be constants or a variable; a function name cannot be used as a parameter value.</span></span> <span data-ttu-id="182cc-111">As variáveis podem ser definidas pelo usuário ou pelas variáveis de sistema como \@\@spid.</span><span class="sxs-lookup"><span data-stu-id="182cc-111">Variables can be user-defined or system variables such as \@\@spid.</span></span>  
  
 <span data-ttu-id="182cc-112">Os exemplos a seguir demonstram a passagem de valores de parâmetro para o procedimento `uspGetWhereUsedProductID`.</span><span class="sxs-lookup"><span data-stu-id="182cc-112">The following examples demonstrate passing parameter values to the procedure `uspGetWhereUsedProductID`.</span></span> <span data-ttu-id="182cc-113">Eles ilustram como passar parâmetros como constantes e variáveis e também como usar uma variável para passar o valor de uma função.</span><span class="sxs-lookup"><span data-stu-id="182cc-113">They illustrate how to pass parameters as constants and variables and also how to use a variable to pass the value of a function.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Passing values as constants.  
EXEC dbo.uspGetWhereUsedProductID 819, '20050225';  
GO  
-- Passing values as variables.  
DECLARE @ProductID int, @CheckDate datetime;  
SET @ProductID = 819;  
SET @CheckDate = '20050225';  
EXEC dbo.uspGetWhereUsedProductID @ProductID, @CheckDate;  
GO  
-- Try to use a function as a parameter value.  
-- This produces an error message.  
EXEC dbo.uspGetWhereUsedProductID 819, GETDATE();  
GO  
-- Passing the function value as a variable.  
DECLARE @CheckDate datetime;  
SET @CheckDate = GETDATE();  
EXEC dbo.uspGetWhereUsedProductID 819, @CheckDate;  
GO  
```  
  
## <a name="specifying-parameter-names"></a><span data-ttu-id="182cc-114">Especificando nomes de parâmetro</span><span class="sxs-lookup"><span data-stu-id="182cc-114">Specifying Parameter Names</span></span>  
 <span data-ttu-id="182cc-115">Na criação de um procedimento e declaração de um nome de parâmetro, o nome de parâmetro deve começar com um único caractere \@ e deve ser exclusivo no escopo do procedimento.</span><span class="sxs-lookup"><span data-stu-id="182cc-115">When creating a procedure and declaring a parameter name, the parameter name must begin with a single \@ character and must be unique in the scope of the procedure.</span></span>  
  
 <span data-ttu-id="182cc-116">A nomeação explícita dos parâmetros e a atribuição dos valores apropriados a cada parâmetro em uma chamada de procedimento permitem o fornecimento dos parâmetros em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="182cc-116">Explicitly naming the parameters and assigning the appropriate values to each parameter in a procedure call allows the parameters to be supplied in any order.</span></span> <span data-ttu-id="182cc-117">Por exemplo, se o procedimento **my_proc** espera três parâmetros com os nomes **\@first**, **\@second** e **\@third**, os valores passados ao procedimento podem ser atribuídos aos nomes de parâmetros, como: `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`</span><span class="sxs-lookup"><span data-stu-id="182cc-117">For example, if the procedure **my_proc** expects three parameters named **\@first**, **\@second**, and **\@third**, the values passed to the procedure can be assigned to the parameter names, such as: `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="182cc-118">Se um valor de parâmetro for fornecido no formato **\@parameter =** _value_, todos os parâmetros subsequentes deverão ser fornecidos dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="182cc-118">If one parameter value is supplied in the form **\@parameter =**_value_, all subsequent parameters must be supplied in this manner.</span></span> <span data-ttu-id="182cc-119">Se os valores de parâmetros não forem passados no formato **\@parameter =** _value_, os valores deverão ser fornecidos na mesma ordem (da esquerda para a direita) em que os parâmetros serão listados na instrução CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="182cc-119">If the parameter values are not passed in the form **\@parameter =**_value_, the values must be supplied in the identical order (left to right) as the parameters are listed in the CREATE PROCEDURE statement.</span></span>  
> 
> [!WARNING]
>  <span data-ttu-id="182cc-120">Qualquer parâmetro passado no formato **\@parameter =** _value_, com o parâmetro digitado incorretamente, fará com que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gere um erro e impedirá a execução do procedimento.</span><span class="sxs-lookup"><span data-stu-id="182cc-120">Any parameter passed in the form **\@parameter =**_value_ with the parameter misspelled, will cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to generate an error and prevent procedure execution.</span></span>  
  
## <a name="specifying-parameter-data-types"></a><span data-ttu-id="182cc-121">Especificando tipos de dados de parâmetros</span><span class="sxs-lookup"><span data-stu-id="182cc-121">Specifying Parameter Data Types</span></span>  
 <span data-ttu-id="182cc-122">Parâmetros devem ser definidos com um tipo de dados quando são declarados em uma instrução CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="182cc-122">Parameters must be defined with a data type when they are declared in a CREATE PROCEDURE statement.</span></span> <span data-ttu-id="182cc-123">O tipo de dados de um parâmetro determina o tipo e o intervalo dos valores aceitos pelo parâmetro quando o procedimento é chamado.</span><span class="sxs-lookup"><span data-stu-id="182cc-123">The data type of a parameter determines the type and range of values that are accepted for the parameter when the procedure is called.</span></span> <span data-ttu-id="182cc-124">Por exemplo, se você definir um parâmetro com um tipo de dados `tinyint`, somente valores numéricos no intervalo entre 0 e 255 serão aceitos quando passados para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="182cc-124">For example, if you define a parameter with a `tinyint` data type, only numeric values ranging from 0 to 255 are accepted when passed into that parameter.</span></span> <span data-ttu-id="182cc-125">Um erro será retornado se um procedimento for executado com um valor incompatível com o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="182cc-125">An error is returned if a procedure is executed with a value incompatible with the data type.</span></span>  
  
## <a name="specifying-parameter-default-values"></a><span data-ttu-id="182cc-126">Especificando valores padrão de parâmetro</span><span class="sxs-lookup"><span data-stu-id="182cc-126">Specifying Parameter Default Values</span></span>  
 <span data-ttu-id="182cc-127">Um parâmetro é considerado opcional se o parâmetro tem um valor padrão especificado quando é declarado.</span><span class="sxs-lookup"><span data-stu-id="182cc-127">A parameter is considered optional if the parameter has a default value specified when it is declared.</span></span> <span data-ttu-id="182cc-128">Não é necessário fornecer um valor para um parâmetro opcional em uma chamada de procedimento.</span><span class="sxs-lookup"><span data-stu-id="182cc-128">It is not necessary to provide a value for an optional parameter in a procedure call.</span></span>  
  
 <span data-ttu-id="182cc-129">O valor padrão de um parâmetro é usado quando:</span><span class="sxs-lookup"><span data-stu-id="182cc-129">The default value of a parameter is used when:</span></span>  
  
-   <span data-ttu-id="182cc-130">Nenhum valor é especificado para o parâmetro na chamada do procedimento.</span><span class="sxs-lookup"><span data-stu-id="182cc-130">No value for the parameter is specified in the procedure call.</span></span>  
  
-   <span data-ttu-id="182cc-131">A palavra-chave DEFAULT é especificada como o valor na chamada do procedimento.</span><span class="sxs-lookup"><span data-stu-id="182cc-131">The DEFAULT keyword is specified as the value in the procedure call.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="182cc-132">Se o valor padrão for uma cadeia de caracteres contendo pontuação ou espaços em branco inseridos, ou caso ela comece com um número (por exemplo, 6xxx), ela deverá ser colocada entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="182cc-132">If the default value is a character string that contains embedded blanks or punctuation, or if it starts with a number (for example, 6xxx), it must be enclosed in single, straight quotation marks.</span></span>  
  
 <span data-ttu-id="182cc-133">Se nenhum valor puder ser especificado adequadamente como um padrão para o parâmetro, especifique NULL como o padrão.</span><span class="sxs-lookup"><span data-stu-id="182cc-133">If no value can be specified appropriately as a default for the parameter, specify NULL as the default.</span></span> <span data-ttu-id="182cc-134">Convém levar o procedimento a retornar uma mensagem personalizada se ele for executado sem um valor para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="182cc-134">It is a good idea to have the procedure return a customized message if the procedure is executed without a value for the parameter.</span></span>  
  
 <span data-ttu-id="182cc-135">O exemplo a seguir cria o procedimento armazenado `usp_GetSalesYTD` com um parâmetro de entrada, `@SalesPerson`.</span><span class="sxs-lookup"><span data-stu-id="182cc-135">The following example creates the `usp_GetSalesYTD` procedure with one input parameter, `@SalesPerson`.</span></span> <span data-ttu-id="182cc-136">NULL será atribuído como valor padrão para o parâmetro e será utilizado em instruções de tratamento de erros para retornar uma mensagem de erro personalizada nos casos de execução do procedimento sem um valor para o parâmetro `@SalesPerson` .</span><span class="sxs-lookup"><span data-stu-id="182cc-136">NULL is assigned as the default value for the parameter and is used in error handling statements to return a custom error message for cases when the procedure is executed without a value for the `@SalesPerson` parameter.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetSalesYTD  
@SalesPerson nvarchar(50) = NULL  -- NULL default value  
AS   
    SET NOCOUNT ON;   
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
BEGIN  
   PRINT 'ERROR: You must specify the last name of the sales person.'  
   RETURN  
END  
-- Get the sales for the specified sales person and   
-- assign it to the output parameter.  
SELECT SalesYTD  
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="182cc-137">O exemplo a seguir executa o procedimento.</span><span class="sxs-lookup"><span data-stu-id="182cc-137">The following example executes the procedure.</span></span> <span data-ttu-id="182cc-138">A primeira instrução executa o procedimento sem especificar um valor de entrada.</span><span class="sxs-lookup"><span data-stu-id="182cc-138">The first statement executes the procedure without specifying an input value.</span></span> <span data-ttu-id="182cc-139">Isso leva as instruções de tratamento de erros no procedimento a retornarem a mensagem de erro personalizada.</span><span class="sxs-lookup"><span data-stu-id="182cc-139">This causes the error handling statements in the procedure to return the custom error message.</span></span> <span data-ttu-id="182cc-140">A segunda instrução fornece um valor de entrada e retorna o conjunto de resultados esperado.</span><span class="sxs-lookup"><span data-stu-id="182cc-140">The second statement supplies an input value and returns the expected result set.</span></span>  
  
```  
-- Run the procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the procedure with an input value.  
EXEC Sales.usp_GetSalesYTD N'Blythe';  
GO  
```  
  
 <span data-ttu-id="182cc-141">Embora seja possível omitir os parâmetros para os quais foram fornecidos padrões, a lista de parâmetros só poderá ser truncada.</span><span class="sxs-lookup"><span data-stu-id="182cc-141">Although parameters for which defaults have been supplied can be omitted, the list of parameters can only be truncated.</span></span> <span data-ttu-id="182cc-142">Por exemplo, se um procedimento tiver cinco parâmetros, o quarto e o quinto parâmetros poderão ser omitidos.</span><span class="sxs-lookup"><span data-stu-id="182cc-142">For example, if a procedure has five parameters, both the fourth and the fifth parameters can be omitted.</span></span> <span data-ttu-id="182cc-143">Entretanto, o quarto parâmetro não poderá ser ignorado desde que o quinto parâmetro seja incluído, a menos que os parâmetros sejam fornecidos no formato **\@parameter =** _value_.</span><span class="sxs-lookup"><span data-stu-id="182cc-143">However the fourth parameter cannot be skipped as long as the fifth parameter is included, unless the parameters are supplied in the form **\@parameter =**_value_.</span></span>  
  
## <a name="specifying-parameter-direction"></a><span data-ttu-id="182cc-144">Especificando a direção do parâmetro</span><span class="sxs-lookup"><span data-stu-id="182cc-144">Specifying Parameter Direction</span></span>  
 <span data-ttu-id="182cc-145">A direção de um parâmetro é de entrada, em que um valor é passado para o corpo do procedimento armazenado, ou de saída, em que o procedimento retorna um valor ao programa de chamada.</span><span class="sxs-lookup"><span data-stu-id="182cc-145">The direction of a parameter is either input, a value is passed into the body of the procedure, or output, the procedure returns a value to the calling program.</span></span> <span data-ttu-id="182cc-146">O padrão é um parâmetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="182cc-146">The default is an input parameter.</span></span>  
  
 <span data-ttu-id="182cc-147">Para especificar um parâmetro de saída, especifique a palavra-chave OUTPUT na definição do parâmetro na instrução CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="182cc-147">To specify an output parameter, the OUTPUT keyword must be specified in the definition of the parameter in the CREATE PROCEDURE statement.</span></span> <span data-ttu-id="182cc-148">O procedimento retorna o valor atual do parâmetro de saída ao programa de chamada quando o procedimento existe.</span><span class="sxs-lookup"><span data-stu-id="182cc-148">The procedure returns the current value of the output parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="182cc-149">O programa de chamada também deve usar a palavra-chave OUTPUT ao executar o procedimento a fim de salvar o valor do parâmetro em uma variável que pode ser usada no programa de chamada.</span><span class="sxs-lookup"><span data-stu-id="182cc-149">The calling program must also use the OUTPUT keyword when executing the procedure to save the parameter's value in a variable that can be used in the calling program.</span></span>  
  
 <span data-ttu-id="182cc-150">O exemplo a seguir cria o procedimento `Production.usp`_`GetList` , que retorna uma lista de produtos com preços que não excedem um valor especificado.</span><span class="sxs-lookup"><span data-stu-id="182cc-150">The following example creates the `Production.usp`_`GetList` procedure, which returns a list of products that have prices that do not exceed a specified amount.</span></span> <span data-ttu-id="182cc-151">O exemplo mostra o uso de várias instruções SELECT e vários parâmetros OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="182cc-151">The example shows using multiple SELECT statements and multiple OUTPUT parameters.</span></span> <span data-ttu-id="182cc-152">Os parâmetros OUTPUT permitem que um procedimento externo, um lote ou mais de uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] acessem um valor definido durante a execução do procedimento.</span><span class="sxs-lookup"><span data-stu-id="182cc-152">OUTPUT parameters allow an external procedure, a batch, or more than one [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to access a value set during the procedure execution.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'Production.uspGetList', 'P' ) IS NOT NULL   
    DROP PROCEDURE Production.uspGetList;  
GO  
CREATE PROCEDURE Production.uspGetList @Product varchar(40)   
    , @MaxPrice money   
    , @ComparePrice money OUTPUT  
    , @ListPrice money OUT  
AS  
    SET NOCOUNT ON;  
    SELECT p.[Name] AS Product, p.ListPrice AS 'List Price'  
    FROM Production.Product AS p  
    JOIN Production.ProductSubcategory AS s   
      ON p.ProductSubcategoryID = s.ProductSubcategoryID  
    WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice;  
-- Populate the output variable @ListPprice.  
SET @ListPrice = (SELECT MAX(p.ListPrice)  
        FROM Production.Product AS p  
        JOIN  Production.ProductSubcategory AS s   
          ON p.ProductSubcategoryID = s.ProductSubcategoryID  
        WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice);  
-- Populate the output variable @compareprice.  
SET @ComparePrice = @MaxPrice;  
GO  
  
```  
  
 <span data-ttu-id="182cc-153">Execute `usp_GetList` para retornar uma lista de produtos (bicicletas) da [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] que custam menos que $ 700.</span><span class="sxs-lookup"><span data-stu-id="182cc-153">Execute `usp_GetList` to return a list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] products (Bikes) that cost less than $700.</span></span> <span data-ttu-id="182cc-154">Os parâmetros OUTPUT **\@cost** e **\@compareprices** são usados com linguagem de controle de fluxo para retornar uma mensagem na janela **Mensagens**.</span><span class="sxs-lookup"><span data-stu-id="182cc-154">The OUTPUT parameters **\@cost** and **\@compareprices** are used with control-of-flow language to return a message in the **Messages** window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="182cc-155">A variável OUTPUT deve ser definida durante a criação do procedimento e também durante o uso da variável.</span><span class="sxs-lookup"><span data-stu-id="182cc-155">The OUTPUT variable must be defined during the procedure creation and also during the use of the variable.</span></span> <span data-ttu-id="182cc-156">O nome de parâmetro e o nome de variável não precisam coincidir.</span><span class="sxs-lookup"><span data-stu-id="182cc-156">The parameter name and variable name do not have to match.</span></span> <span data-ttu-id="182cc-157">Porém, o tipo de dados e o posicionamento do parâmetro precisam ser correspondentes (a menos que **\@listprice=** _variable_ seja usado).</span><span class="sxs-lookup"><span data-stu-id="182cc-157">However, the data type and parameter positioning must match (unless **\@listprice=** _variable_ is used).</span></span>  
  
```  
DECLARE @ComparePrice money, @Cost money ;  
EXECUTE Production.uspGetList '%Bikes%', 700,   
    @ComparePrice OUT,   
    @Cost OUTPUT  
IF @Cost <= @ComparePrice   
BEGIN  
    PRINT 'These products can be purchased for less than   
    $'+RTRIM(CAST(@ComparePrice AS varchar(20)))+'.'  
END  
ELSE  
    PRINT 'The prices for all products in this category exceed   
    $'+ RTRIM(CAST(@ComparePrice AS varchar(20)))+'.';  
  
```  
  
 <span data-ttu-id="182cc-158">Este é o conjunto de resultados parcial:</span><span class="sxs-lookup"><span data-stu-id="182cc-158">Here is the partial result set:</span></span>  
  
```  
Product                                            List Price  
-------------------------------------------------- ------------------  
Road-750 Black, 58                                 539.99  
Mountain-500 Silver, 40                            564.99  
Mountain-500 Silver, 42                            564.99  
...  
Road-750 Black, 48                                 539.99  
Road-750 Black, 52                                 539.99  
  
(14 row(s) affected)  
  
These items can be purchased for less than $700.00.  
```  
  
## <a name="see-also"></a><span data-ttu-id="182cc-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="182cc-159">See Also</span></span>  
 [<span data-ttu-id="182cc-160">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="182cc-160">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
