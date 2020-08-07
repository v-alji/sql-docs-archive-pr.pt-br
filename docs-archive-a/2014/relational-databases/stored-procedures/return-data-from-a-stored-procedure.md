---
title: Retornar dados de um procedimento armazenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], returning data
- returning data from stored procedure
ms.assetid: 7a428ffe-cd87-4f42-b3f1-d26aa8312bf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 472ca5cf27f7e7ea2b18daa961c19faadcf2251f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584099"
---
# <a name="return-data-from-a-stored-procedure"></a><span data-ttu-id="decc4-102">Retornar dados de um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="decc4-102">Return Data from a Stored Procedure</span></span>
  <span data-ttu-id="decc4-103">Há duas formas de retornar conjuntos de resultados ou dados de um procedimento para um programa de chamada: parâmetros de saída e códigos de retorno.</span><span class="sxs-lookup"><span data-stu-id="decc4-103">There are two ways of returning result sets or data from a procedure to a calling program: output parameters and return codes.</span></span> <span data-ttu-id="decc4-104">Este tópico fornece informações sobre as duas abordagens.</span><span class="sxs-lookup"><span data-stu-id="decc4-104">This topic provides information on both approaches.</span></span>  
  
## <a name="returning-data-using-an-output-parameter"></a><span data-ttu-id="decc4-105">Retornando dados por meio de um parâmetro de saída</span><span class="sxs-lookup"><span data-stu-id="decc4-105">Returning Data Using an Output Parameter</span></span>  
 <span data-ttu-id="decc4-106">Caso a palavra-chave OUTPUT seja especificada para um parâmetro na definição do procedimento, o procedimento poderá retornar o valor atual do parâmetro para o programa de chamada na saída do procedimento.</span><span class="sxs-lookup"><span data-stu-id="decc4-106">If you specify the OUTPUT keyword for a parameter in the procedure definition, the procedure can return the current value of the parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="decc4-107">Para salvar o valor do parâmetro na variável que poderá ser usada no programa de chamada, o programa de chamada precisará usar a palavra-chave OUTPUT ao executar o procedimento.</span><span class="sxs-lookup"><span data-stu-id="decc4-107">To save the value of the parameter in a variable that can be used in the calling program, the calling program must use the OUTPUT keyword when executing the procedure.</span></span> <span data-ttu-id="decc4-108">Para obter mais informações quais tipos de dados podem ser usados como parâmetros de saída, veja [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="decc4-108">For more information about what data types can be used as output parameters, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
### <a name="examples-of-output-parameter"></a><span data-ttu-id="decc4-109">Exemplos de parâmetro de saída</span><span class="sxs-lookup"><span data-stu-id="decc4-109">Examples of Output Parameter</span></span>  
 <span data-ttu-id="decc4-110">O exemplo a seguir mostra um procedimento com parâmetros de entrada e de saída.</span><span class="sxs-lookup"><span data-stu-id="decc4-110">The following example shows a procedure with an input and an output parameter.</span></span> <span data-ttu-id="decc4-111">O parâmetro `@SalesPerson` receberia um valor de entrada especificado pelo programa de chamada.</span><span class="sxs-lookup"><span data-stu-id="decc4-111">The `@SalesPerson` parameter would receive an input value specified by the calling program.</span></span> <span data-ttu-id="decc4-112">A instrução SELECT usa o valor passado para o parâmetro de entrada para obter o valor `SalesYTD` correto.</span><span class="sxs-lookup"><span data-stu-id="decc4-112">The SELECT statement uses the value passed into the input parameter to obtain the correct `SalesYTD` value.</span></span> <span data-ttu-id="decc4-113">A instrução SELECT também atribui o valor ao parâmetro de saída `@SalesYTD` , que retorna o valor ao programa de chamada quando o procedimento sai.</span><span class="sxs-lookup"><span data-stu-id="decc4-113">The SELECT statement also assigns the value to the `@SalesYTD` output parameter, which returns the value to the calling program when the procedure exits.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetEmployeeSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetEmployeeSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetEmployeeSalesYTD  
@SalesPerson nvarchar(50),  
@SalesYTD money OUTPUT  
AS    
  
    SET NOCOUNT ON;  
    SELECT @SalesYTD = SalesYTD  
    FROM Sales.SalesPerson AS sp  
    JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
    WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="decc4-114">O exemplo a seguir chama o procedimento criado no primeiro exemplo e salva o valor de saída retornado do procedimento chamado na variável `@SalesYTD` , que é local para o programa de chamada.</span><span class="sxs-lookup"><span data-stu-id="decc4-114">The following example calls the procedure created in the first example and saves the output value returned from the called procedure in the `@SalesYTD` variable, which is local to the calling program.</span></span>  
  
```  
-- Declare the variable to receive the output value of the procedure.  
DECLARE @SalesYTDBySalesPerson money;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTDBySalesPerson  
EXECUTE Sales.uspGetEmployeeSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDBySalesPerson OUTPUT;  
-- Display the value returned by the procedure.  
PRINT 'Year-to-date sales for this employee is ' +   
    convert(varchar(10),@SalesYTDBySalesPerson);  
GO  
  
```  
  
 <span data-ttu-id="decc4-115">Valores de entrada também podem ser especificados para parâmetros OUTPUT quando o procedimento é executado.</span><span class="sxs-lookup"><span data-stu-id="decc4-115">Input values can also be specified for OUTPUT parameters when the procedure is executed.</span></span> <span data-ttu-id="decc4-116">Isso permite que o procedimento receba um valor do programa de chamada, altere-o ou realize operações com o valor e, em seguida, retorne o novo valor para o programa de chamada.</span><span class="sxs-lookup"><span data-stu-id="decc4-116">This allows the procedure to receive a value from the calling program, change or perform operations with the value, and then return the new value to the calling program.</span></span> <span data-ttu-id="decc4-117">No exemplo anterior, um valor pode ser atribuído à variável `@SalesYTDBySalesPerson` antes de o programa chamar o procedimento `Sales.uspGetEmployeeSalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="decc4-117">In the previous example, the `@SalesYTDBySalesPerson` variable can be assigned a value before the program calls the `Sales.uspGetEmployeeSalesYTD` procedure.</span></span> <span data-ttu-id="decc4-118">A instrução execute passaria o valor de variável `@SalesYTDBySalesPerson` para o parâmetro OUTPUT `@SalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="decc4-118">The execute statement would pass the `@SalesYTDBySalesPerson` variable value into the `@SalesYTD` OUTPUT parameter.</span></span> <span data-ttu-id="decc4-119">Depois, no corpo do procedimento, o valor poderia ser usado em cálculos que geram um novo valor.</span><span class="sxs-lookup"><span data-stu-id="decc4-119">Then in the procedure body, the value could be used for calculations that generate a new value.</span></span> <span data-ttu-id="decc4-120">O novo valor seria devolvido do procedimento pelo parâmetro OUTPUT, atualizando o valor na variável `@SalesYTDBySalesPerson` , quando o procedimento saísse.</span><span class="sxs-lookup"><span data-stu-id="decc4-120">The new value would be passed back out of the procedure through the OUTPUT parameter, updating the value in the `@SalesYTDBySalesPerson` variable when the procedure exits.</span></span> <span data-ttu-id="decc4-121">Isto é denominado frequentemente como "capacidade de passagem-por-referência".</span><span class="sxs-lookup"><span data-stu-id="decc4-121">This is often referred to as "pass-by-reference capability."</span></span>  
  
 <span data-ttu-id="decc4-122">Quando você especifica OUTPUT para um parâmetro ao chamar um procedimento e esse parâmetro não é definido com OUTPUT na definição de procedimento, uma mensagem de erro é exibida.</span><span class="sxs-lookup"><span data-stu-id="decc4-122">If you specify OUTPUT for a parameter when you call a procedure and that parameter is not defined by using OUTPUT in the procedure definition, you get an error message.</span></span> <span data-ttu-id="decc4-123">Entretanto, é possível executar um procedimento com parâmetros de saída e não especificar OUTPUT ao executar o procedimento.</span><span class="sxs-lookup"><span data-stu-id="decc4-123">However, you can execute a procedure with output parameters and not specify OUTPUT when executing the procedure.</span></span> <span data-ttu-id="decc4-124">Uma mensagem de erro é exibida, mas não se pode usar valor de saída no programa de chamada.</span><span class="sxs-lookup"><span data-stu-id="decc4-124">No error is returned, but you cannot use the output value in the calling program.</span></span>  
  
### <a name="using-the-cursor-data-type-in-output-parameters"></a><span data-ttu-id="decc4-125">Usando o tipo de dados de cursor em parâmetros OUTPUT</span><span class="sxs-lookup"><span data-stu-id="decc4-125">Using the Cursor Data Type in OUTPUT Parameters</span></span>  
 [!INCLUDE[tsql](../../../includes/tsql-md.md)]<span data-ttu-id="decc4-126">os procedimentos podem usar o `cursor` tipo de dados somente para parâmetros de saída.</span><span class="sxs-lookup"><span data-stu-id="decc4-126">procedures can use the `cursor` data type only for OUTPUT parameters.</span></span> <span data-ttu-id="decc4-127">Se o `cursor` tipo de dados for especificado para um parâmetro, as palavras-chave Variable e output deverão ser especificadas para esse parâmetro na definição do procedimento.</span><span class="sxs-lookup"><span data-stu-id="decc4-127">If the `cursor` data type is specified for a parameter, both the VARYING and OUTPUT keywords must be specified for that parameter in the procedure definition.</span></span> <span data-ttu-id="decc4-128">Um parâmetro pode ser especificado como somente saída, mas se a palavra-chave VARYing for especificada na declaração de parâmetro, o tipo de dados deverá ser `cursor` e a palavra-chave output também deverá ser especificada.</span><span class="sxs-lookup"><span data-stu-id="decc4-128">A parameter can be specified as only OUTPUT but if the VARYING keyword is specified in the parameter declaration, the data type must be `cursor` and the OUTPUT keyword must also be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="decc4-129">O tipo de dados `cursor` não pode ser associado a variáveis de aplicativos por meio de APIs de banco de dados, como OLE DB, ODBC, ADO e DB-Library.</span><span class="sxs-lookup"><span data-stu-id="decc4-129">The `cursor` data type cannot be bound to application variables through the database APIs such as OLE DB, ODBC, ADO, and DB-Library.</span></span> <span data-ttu-id="decc4-130">Como os parâmetros OUTPUT devem ser associados antes de um aplicativo executar um procedimento, os procedimentos com parâmetros OUTPUT `cursor` não podem ser chamados das APIs do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="decc4-130">Because OUTPUT parameters must be bound before an application can execute a procedure, procedures with `cursor` OUTPUT parameters cannot be called from the database APIs.</span></span> <span data-ttu-id="decc4-131">Esses procedimentos podem ser chamados de lotes, procedimentos ou gatilhos do [!INCLUDE[tsql](../../../includes/tsql-md.md)] apenas quando a variável OUTPUT de `cursor` é atribuída a uma variável [!INCLUDE[tsql](../../../includes/tsql-md.md)]`cursor` local.</span><span class="sxs-lookup"><span data-stu-id="decc4-131">These procedures can be called from [!INCLUDE[tsql](../../../includes/tsql-md.md)] batches, procedures, or triggers only when the `cursor` OUTPUT variable is assigned to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] local `cursor` variable.</span></span>  
  
### <a name="rules-for-cursor-output-parameters"></a><span data-ttu-id="decc4-132">Regras para parâmetros de saída de cursor</span><span class="sxs-lookup"><span data-stu-id="decc4-132">Rules for Cursor Output Parameters</span></span>  
 <span data-ttu-id="decc4-133">As regras seguintes pertencem aos parâmetros de saída de `cursor` quando o procedimento é executado:</span><span class="sxs-lookup"><span data-stu-id="decc4-133">The following rules pertain to `cursor` output parameters when the procedure is executed:</span></span>  
  
-   <span data-ttu-id="decc4-134">Para um cursor de somente avanço, as linhas retornadas no conjunto de resultados do cursor são apenas as que estão na posição do cursor na conclusão da execução do procedimento, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="decc4-134">For a forward-only cursor, the rows returned in the cursor's result set are only those rows at and beyond the position of the cursor at the conclusion of the procedure execution, for example:</span></span>  
  
    -   <span data-ttu-id="decc4-135">Um cursor não rolável é aberto em um procedimento em um conjunto de resultados nomeado RS de 100 linhas.</span><span class="sxs-lookup"><span data-stu-id="decc4-135">A nonscrollable cursor is opened in a procedure on a result set named RS of 100 rows.</span></span>  
  
    -   <span data-ttu-id="decc4-136">O procedimento busca as primeiras 5 linhas de conjunto de resultados RS.</span><span class="sxs-lookup"><span data-stu-id="decc4-136">The procedure fetches the first 5 rows of result set RS.</span></span>  
  
    -   <span data-ttu-id="decc4-137">O procedimento retorna ao chamador.</span><span class="sxs-lookup"><span data-stu-id="decc4-137">The procedure returns to its caller.</span></span>  
  
    -   <span data-ttu-id="decc4-138">O conjunto de resultados RS retornado ao chamador consiste de linhas de 6 a 100 do RS, e o cursor no chamador está posicionado antes da primeira linha do RS.</span><span class="sxs-lookup"><span data-stu-id="decc4-138">The result set RS returned to the caller consists of rows from 6 through 100 of RS, and the cursor in the caller is positioned before the first row of RS.</span></span>  
  
-   <span data-ttu-id="decc4-139">No caso de um cursor de somente avanço, se o cursor estiver posicionado antes da primeira linha quando o procedimento sair, o conjunto de resultados inteiro será retornado ao lote, procedimento ou gatilho de chamada.</span><span class="sxs-lookup"><span data-stu-id="decc4-139">For a forward-only cursor, if the cursor is positioned before the first row when the procedure exits, the entire result set is returned to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="decc4-140">No retorno, a posição do cursor é estabelecida antes da primeira linha.</span><span class="sxs-lookup"><span data-stu-id="decc4-140">When returned, the cursor position is set before the first row.</span></span>  
  
-   <span data-ttu-id="decc4-141">No caso de um cursor de somente avanço, se o cursor estiver posicionado depois do fim da última linha quando o procedimento sair, um conjunto de resultados vazio será retornado ao lote, procedimento ou gatilho de chamada.</span><span class="sxs-lookup"><span data-stu-id="decc4-141">For a forward-only cursor, if the cursor is positioned beyond the end of the last row when the procedure exits, an empty result set is returned to the calling batch, procedure, or trigger.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="decc4-142">Um conjunto de resultados vazio não é igual a um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="decc4-142">An empty result set is not the same as a null value.</span></span>  
  
-   <span data-ttu-id="decc4-143">No caso de um cursor rolável, todas as linhas no conjunto de resultados são retornadas ao lote, procedimento ou gatilho de chamada quando o procedimento sai.</span><span class="sxs-lookup"><span data-stu-id="decc4-143">For a scrollable cursor, all the rows in the result set are returned to the calling batch, procedure, or trigger when the procedure exits.</span></span> <span data-ttu-id="decc4-144">No retorno, a posição de cursor é mantida na posição da última busca executada no procedimento.</span><span class="sxs-lookup"><span data-stu-id="decc4-144">When returned, the cursor position is left at the position of the last fetch executed in the procedure.</span></span>  
  
-   <span data-ttu-id="decc4-145">Para qualquer tipo de cursor, se o cursor for fechado, um valor nulo será retornado ao lote, procedimento ou gatilho de chamada.</span><span class="sxs-lookup"><span data-stu-id="decc4-145">For any type of cursor, if the cursor is closed, then a null value is passed back to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="decc4-146">Isso também acontecerá se o cursor for atribuído a um parâmetro, mas nunca for aberto.</span><span class="sxs-lookup"><span data-stu-id="decc4-146">This will also be the case if a cursor is assigned to a parameter, but that cursor is never opened.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="decc4-147">O estado fechado só tem importância no momento do retorno.</span><span class="sxs-lookup"><span data-stu-id="decc4-147">The closed state matters only at return time.</span></span> <span data-ttu-id="decc4-148">Por exemplo, é válido fechar um cursor durante o procedimento, reabrindo-o no procedimento posteriormente, e retornar o conjunto de resultados desse cursor para o lote, procedimento ou gatilho de chamada.</span><span class="sxs-lookup"><span data-stu-id="decc4-148">For example, it is valid to close a cursor part of the way through the procedure, to open it again later in the procedure, and return that cursor's result set to the calling batch, procedure, or trigger.</span></span>  
  
### <a name="examples-of-cursor-output-parameters"></a><span data-ttu-id="decc4-149">Exemplos de parâmetros de saída de cursor</span><span class="sxs-lookup"><span data-stu-id="decc4-149">Examples of Cursor Output Parameters</span></span>  
 <span data-ttu-id="decc4-150">No exemplo a seguir, é criado um procedimento que especificou um parâmetro de saída, `@currency` _ `cursor` usando o `cursor` tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="decc4-150">In the following example, a procedure is created that specified an output parameter, `@currency`_`cursor` using the `cursor` data type.</span></span> <span data-ttu-id="decc4-151">O procedimento é chamado em um lote.</span><span class="sxs-lookup"><span data-stu-id="decc4-151">The procedure is then called in a batch.</span></span>  
  
 <span data-ttu-id="decc4-152">Primeiro, crie o procedimento que declara e, então, abra um cursor na tabela Moeda.</span><span class="sxs-lookup"><span data-stu-id="decc4-152">First, create the procedure that declares and then opens a cursor on the Currency table.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspCurrencyCursor', 'P' ) IS NOT NULL  
    DROP PROCEDURE dbo.uspCurrencyCursor;  
GO  
CREATE PROCEDURE dbo.uspCurrencyCursor   
    @CurrencyCursor CURSOR VARYING OUTPUT  
AS  
    SET NOCOUNT ON;  
    SET @CurrencyCursor = CURSOR  
    FORWARD_ONLY STATIC FOR  
      SELECT CurrencyCode, Name  
      FROM Sales.Currency;  
    OPEN @CurrencyCursor;  
GO  
  
```  
  
 <span data-ttu-id="decc4-153">A seguir, execute um lote que declare uma variável de cursor local, execute o procedimento para atribuir o cursor à variável local e depois busque as linhas do cursor.</span><span class="sxs-lookup"><span data-stu-id="decc4-153">Next, execute a batch that declares a local cursor variable, executes the procedure to assign the cursor to the local variable, and then fetches the rows from the cursor.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @MyCursor CURSOR;  
EXEC dbo.uspCurrencyCursor @CurrencyCursor = @MyCursor OUTPUT;  
WHILE (@@FETCH_STATUS = 0)  
BEGIN;  
     FETCH NEXT FROM @MyCursor;  
END;  
CLOSE @MyCursor;  
DEALLOCATE @MyCursor;  
GO  
  
```  
  
## <a name="returning-data-using-a-return-code"></a><span data-ttu-id="decc4-154">Retornando dados usando um código de retorno</span><span class="sxs-lookup"><span data-stu-id="decc4-154">Returning Data Using a Return Code</span></span>  
 <span data-ttu-id="decc4-155">Um procedimento pode retornar um valor inteiro chamado de código de retorno para indicar o status de execução de um procedimento.</span><span class="sxs-lookup"><span data-stu-id="decc4-155">A procedure can return an integer value called a return code to indicate the execution status of a procedure.</span></span> <span data-ttu-id="decc4-156">Especifique o código de retorno de um procedimento usando a instrução RETURN.</span><span class="sxs-lookup"><span data-stu-id="decc4-156">You specify the return code for a procedure using the RETURN statement.</span></span> <span data-ttu-id="decc4-157">Assim como em parâmetros OUTPUT, você deve salvar o código de retorno em uma variável quando o procedimento é executado para usar o valor de código de retorno no programa de chamada.</span><span class="sxs-lookup"><span data-stu-id="decc4-157">As with OUTPUT parameters, you must save the return code in a variable when the procedure is executed in order to use the return code value in the calling program.</span></span> <span data-ttu-id="decc4-158">Por exemplo, a variável `@result` de atribuição do tipo de dados `int` é usada para armazenar o código de retorno do procedimento `my_proc` , como:</span><span class="sxs-lookup"><span data-stu-id="decc4-158">For example, the assignment variable `@result` of data type `int` is used to store the return code from the procedure `my_proc`, such as:</span></span>  
  
```  
DECLARE @result int;  
EXECUTE @result = my_proc;  
```  
  
 <span data-ttu-id="decc4-159">Os códigos de retorno são geralmente usados em blocos de controle de fluxo em procedimentos para definir o valor de código de retorno para cada situação de erro possível.</span><span class="sxs-lookup"><span data-stu-id="decc4-159">Return codes are commonly used in control-of-flow blocks within procedures to set the return code value for each possible error situation.</span></span> <span data-ttu-id="decc4-160">Você pode usar a função @@ERROR após uma instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] para detectar se ocorreu um erro durante a execução da instrução.</span><span class="sxs-lookup"><span data-stu-id="decc4-160">You can use the @@ERROR function after a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to detect whether an error occurred during the execution of the statement.</span></span>  
  
### <a name="examples-of-return-codes"></a><span data-ttu-id="decc4-161">Exemplos de códigos de retorno</span><span class="sxs-lookup"><span data-stu-id="decc4-161">Examples of Return Codes</span></span>  
 <span data-ttu-id="decc4-162">O exemplo a seguir mostra o procedimento `usp_GetSalesYTD` com tratamento de erros que define valores de código de retorno especiais para vários erros.</span><span class="sxs-lookup"><span data-stu-id="decc4-162">The following example shows the `usp_GetSalesYTD` procedure with error handling that sets special return code values for various errors.</span></span> <span data-ttu-id="decc4-163">A tabela a seguir mostra o valor de inteiro atribuído pelo procedimento a cada erro possível, e o significado correspondente de cada valor.</span><span class="sxs-lookup"><span data-stu-id="decc4-163">The following table shows the integer value that is assigned by the procedure to each possible error, and the corresponding meaning for each value.</span></span>  
  
|<span data-ttu-id="decc4-164">Valor de código de retorno</span><span class="sxs-lookup"><span data-stu-id="decc4-164">Return code value</span></span>|<span data-ttu-id="decc4-165">Significado</span><span class="sxs-lookup"><span data-stu-id="decc4-165">Meaning</span></span>|  
|-----------------------|-------------|  
|<span data-ttu-id="decc4-166">0</span><span class="sxs-lookup"><span data-stu-id="decc4-166">0</span></span>|<span data-ttu-id="decc4-167">Execução bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="decc4-167">Successful execution.</span></span>|  
|<span data-ttu-id="decc4-168">1</span><span class="sxs-lookup"><span data-stu-id="decc4-168">1</span></span>|<span data-ttu-id="decc4-169">O valor de parâmetro necessário não foi especificado.</span><span class="sxs-lookup"><span data-stu-id="decc4-169">Required parameter value is not specified.</span></span>|  
|<span data-ttu-id="decc4-170">2</span><span class="sxs-lookup"><span data-stu-id="decc4-170">2</span></span>|<span data-ttu-id="decc4-171">O valor de parâmetro especificado não é válido.</span><span class="sxs-lookup"><span data-stu-id="decc4-171">Specified parameter value is not valid.</span></span>|  
|<span data-ttu-id="decc4-172">3</span><span class="sxs-lookup"><span data-stu-id="decc4-172">3</span></span>|<span data-ttu-id="decc4-173">Erro ocorrido ao obter o valor de vendas.</span><span class="sxs-lookup"><span data-stu-id="decc4-173">Error has occurred getting sales value.</span></span>|  
|<span data-ttu-id="decc4-174">4</span><span class="sxs-lookup"><span data-stu-id="decc4-174">4</span></span>|<span data-ttu-id="decc4-175">Valor de vendas NULL encontrado para o vendedor.</span><span class="sxs-lookup"><span data-stu-id="decc4-175">NULL sales value found for the salesperson.</span></span>|  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.usp_GetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.usp_GetSalesYTD;  
GO  
CREATE PROCEDURE Sales.usp_GetSalesYTD  
@SalesPerson nvarchar(50) = NULL,  -- NULL default value  
@SalesYTD money = NULL OUTPUT  
AS    
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
   BEGIN  
       PRINT 'ERROR: You must specify a last name for the sales person.'  
       RETURN(1)  
   END  
ELSE  
   BEGIN  
   -- Make sure the value is valid.  
   IF (SELECT COUNT(*) FROM HumanResources.vEmployee  
          WHERE LastName = @SalesPerson) = 0  
      RETURN(2)  
   END  
-- Get the sales for the specified name and   
-- assign it to the output parameter.  
SELECT @SalesYTD = SalesYTD   
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
-- Check for SQL Server errors.  
IF @@ERROR <> 0   
   BEGIN  
      RETURN(3)  
   END  
ELSE  
   BEGIN  
   -- Check to see if the ytd_sales value is NULL.  
     IF @SalesYTD IS NULL  
       RETURN(4)   
     ELSE  
      -- SUCCESS!!  
        RETURN(0)  
   END  
-- Run the stored procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the stored procedure with an input value.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTD  
EXECUTE Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
PRINT N'Year-to-date sales for this employee is ' +  
    CONVERT(varchar(10), @SalesYTDForSalesPerson);  
  
```  
  
 <span data-ttu-id="decc4-176">O exemplo a seguir cria um programa para controlar os códigos de retorno retornados do procedimento `usp_GetSalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="decc4-176">The following example creates a program to handle the return codes that are returned from the `usp_GetSalesYTD` procedure.</span></span>  
  
```  
-- Declare the variables to receive the output value and return code   
-- of the procedure.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
  
-- Execute the procedure with a title_id value  
-- and save the output value and return code in variables.  
EXECUTE @ret_code = Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
--  Check the return codes.  
IF @ret_code = 0  
BEGIN  
   PRINT 'Procedure executed successfully'  
   -- Display the value returned by the procedure.  
   PRINT 'Year-to-date sales for this employee is ' + CONVERT(varchar(10),@SalesYTDForSalesPerson)  
END  
ELSE IF @ret_code = 1  
   PRINT 'ERROR: You must specify a last name for the sales person.'  
ELSE IF @ret_code = 2   
   PRINT 'EERROR: You must enter a valid last name for the sales person.'  
ELSE IF @ret_code = 3  
   PRINT 'ERROR: An error occurred getting sales value.'  
ELSE IF @ret_code = 4  
   PRINT 'ERROR: No sales recorded for this employee.'     
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="decc4-177">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="decc4-177">See Also</span></span>  
 <span data-ttu-id="decc4-178">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="decc4-178">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="decc4-179">[PRINT &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/print-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="decc4-179">[PRINT &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/print-transact-sql) </span></span>  
 <span data-ttu-id="decc4-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="decc4-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="decc4-181">[Cursores](../cursors.md) </span><span class="sxs-lookup"><span data-stu-id="decc4-181">[Cursors](../cursors.md) </span></span>  
 <span data-ttu-id="decc4-182">[RETURN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/return-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="decc4-182">[RETURN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/return-transact-sql) </span></span>  
 [<span data-ttu-id="decc4-183">@@ERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="decc4-183">@@ERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/error-transact-sql)  
  
  
