---
title: Manipulando dados UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- CAST function
- data deletions [CLR integration]
- data insertions [CLR integration]
- CONVERT function
- data updates [CLR integration]
- comparing data
- updating data [CLR integration]
- removing data
- IsByteOrdered property
- variables [CLR integration]
- data manipulation [CLR integration]
- user-defined types [CLR integration], data manipulation
- deleting data
- UDTs [CLR integration], data manipulation
- invoking UDT methods
- inserting data
ms.assetid: 51b1a5f2-7591-4e11-bfe2-d88e0836403f
author: rothja
ms.author: jroth
ms.openlocfilehash: 75810a2ffd92130e45025f742d43ba7917d73992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679989"
---
# <a name="manipulating-udt-data"></a><span data-ttu-id="5eb83-102">Manipulando dados UDT</span><span class="sxs-lookup"><span data-stu-id="5eb83-102">Manipulating UDT Data</span></span>
  <span data-ttu-id="5eb83-103">O [!INCLUDE[tsql](../../includes/tsql-md.md)] não fornece uma sintaxe especializada para instruções INSERT, UPDATE ou DELETE ao modificar dados nas colunas UDTs (tipos definidos pelo usuário).</span><span class="sxs-lookup"><span data-stu-id="5eb83-103">[!INCLUDE[tsql](../../includes/tsql-md.md)] provides no specialized syntax for INSERT, UPDATE, or DELETE statements when modifying data in user-defined type (UDT) columns.</span></span> <span data-ttu-id="5eb83-104">As funções [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST ou CONVERT são usadas para converter tipos de dados nativos no tipo UDT.</span><span class="sxs-lookup"><span data-stu-id="5eb83-104">The [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST or CONVERT functions are used to cast native data types to the UDT type.</span></span>  
  
## <a name="inserting-data-in-a-udt-column"></a><span data-ttu-id="5eb83-105">Inserindo dados em uma coluna UDT</span><span class="sxs-lookup"><span data-stu-id="5eb83-105">Inserting Data in a UDT Column</span></span>  
 <span data-ttu-id="5eb83-106">As instruções a seguir [!INCLUDE[tsql](../../includes/tsql-md.md)] inserem três linhas de dados de exemplo na tabela **Points** .</span><span class="sxs-lookup"><span data-stu-id="5eb83-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements insert three rows of sample data into the **Points** table.</span></span> <span data-ttu-id="5eb83-107">O tipo de dados **Point** consiste em valores inteiros X e Y expostos como propriedades de UDT.</span><span class="sxs-lookup"><span data-stu-id="5eb83-107">The **Point** data type consists of X and Y integer values that are exposed as properties of the UDT.</span></span> <span data-ttu-id="5eb83-108">Você deve usar a função CAST ou CONVERT para converter os valores X e Y delimitados por vírgula para o tipo de **ponto** .</span><span class="sxs-lookup"><span data-stu-id="5eb83-108">You must use either the CAST or CONVERT function to cast the comma-delimited X and Y values to the **Point** type.</span></span> <span data-ttu-id="5eb83-109">As duas primeiras instruções usam a função CONVERT para converter um valor de cadeia de caracteres para o tipo de **ponto** e a terceira instrução usa a função Cast:</span><span class="sxs-lookup"><span data-stu-id="5eb83-109">The first two statements use the CONVERT function to convert a string value to the **Point** type, and the third statement uses the CAST function:</span></span>  
  
```  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '3,4'));  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '1,5'));  
INSERT INTO dbo.Points (PointValue) VALUES (CAST ('1,99' AS Point));  
```  
  
## <a name="selecting-data"></a><span data-ttu-id="5eb83-110">Selecionando dados</span><span class="sxs-lookup"><span data-stu-id="5eb83-110">Selecting Data</span></span>  
 <span data-ttu-id="5eb83-111">A instrução SELECT a seguir seleciona o valor binário do UDT.</span><span class="sxs-lookup"><span data-stu-id="5eb83-111">The following SELECT statement selects the binary value of the UDT.</span></span>  
  
```  
SELECT ID, PointValue FROM dbo.Points  
```  
  
 <span data-ttu-id="5eb83-112">Para ver a saída exibida em um formato legível, chame o `ToString` método do **ponto** UDT, que converte o valor em sua representação de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5eb83-112">To see the output displayed in a readable format, call the `ToString` method of the **Point** UDT, which converts the value to its string representation.</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="5eb83-113">Isso gera os resultados a seguir.</span><span class="sxs-lookup"><span data-stu-id="5eb83-113">This produces the following results.</span></span>  
  
```  
IDPointValue  
----------  
13,4  
21,5  
31,99  
```  
  
 <span data-ttu-id="5eb83-114">Você também pode usar as funções [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST e CONVERT para obter os mesmos resultados.</span><span class="sxs-lookup"><span data-stu-id="5eb83-114">You can also use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST and CONVERT functions to achieve the same results.</span></span>  
  
```  
SELECT ID, CAST(PointValue AS varchar)   
FROM dbo.Points;  
  
SELECT ID, CONVERT(varchar, PointValue)   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="5eb83-115">O **ponto** UDT expõe suas coordenadas X e Y como propriedades, que você pode selecionar individualmente.</span><span class="sxs-lookup"><span data-stu-id="5eb83-115">The **Point** UDT exposes its X and Y coordinates as properties, which you can then select individually.</span></span> <span data-ttu-id="5eb83-116">A seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] seleciona as coordenadas X e Y separadamente:</span><span class="sxs-lookup"><span data-stu-id="5eb83-116">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects the X and Y coordinates separately:</span></span>  
  
```  
SELECT ID, PointValue.X AS xVal, PointValue.Y AS yVal   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="5eb83-117">As propriedades X e Y retornam um valor inteiro, que é exibido no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="5eb83-117">The X and Y properties return an integer value, which is displayed in the result set.</span></span>  
  
```  
IDxValyVal  
----------  
134  
215  
3199  
```  
  
## <a name="working-with-variables"></a><span data-ttu-id="5eb83-118">Trabalhando com variáveis</span><span class="sxs-lookup"><span data-stu-id="5eb83-118">Working with Variables</span></span>  
 <span data-ttu-id="5eb83-119">Você pode trabalhar com variáveis usam a instrução DECLARE para atribuir uma variável a um tipo UDT.</span><span class="sxs-lookup"><span data-stu-id="5eb83-119">You can work with variables using the DECLARE statement to assign a variable to a UDT type.</span></span> <span data-ttu-id="5eb83-120">As seguintes instruções atribuem um valor usando a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] SET e exibem os resultados chamando o método `ToString` do UDT na variável:</span><span class="sxs-lookup"><span data-stu-id="5eb83-120">The following statements assign a value using the [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement and display the results by calling the UDT's `ToString` method on the variable:</span></span>  
  
```  
DECLARE @PointValue Point;  
SET @PointValue = (SELECT PointValue FROM dbo.Points  
    WHERE ID = 2);  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="5eb83-121">O conjunto de resultados exibe o valor da variável:</span><span class="sxs-lookup"><span data-stu-id="5eb83-121">The result set displays the variable value:</span></span>  
  
```  
PointValue  
----------  
-1,5  
```  
  
 <span data-ttu-id="5eb83-122">As seguintes instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] obtêm o mesmo resultado que usar SELECT em vez de SET para a atribuição de variável:</span><span class="sxs-lookup"><span data-stu-id="5eb83-122">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements achieve the same result using SELECT rather than SET for the variable assignment:</span></span>  
  
```  
DECLARE @PointValue Point;  
SELECT @PointValue = PointValue FROM dbo.Points  
    WHERE ID = 2;  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="5eb83-123">A diferença entre usar SELECT e SET para a atribuição de variável é que SELECT permite atribuir muitas variáveis a uma única instrução SELECT, ao passo que a sintaxe SET exige que cada atribuição de variável tenha sua própria instrução SET.</span><span class="sxs-lookup"><span data-stu-id="5eb83-123">The difference between using SELECT and SET for variable assignment is that SELECT allows you to assign multiple variables in one SELECT statement, whereas the SET syntax requires each variable assignment to have its own SET statement.</span></span>  
  
## <a name="comparing-data"></a><span data-ttu-id="5eb83-124">Comparando dados</span><span class="sxs-lookup"><span data-stu-id="5eb83-124">Comparing Data</span></span>  
 <span data-ttu-id="5eb83-125">Você poderá usar operadores de comparação para comparar valores em seu UDT se tiver definido a propriedade `IsByteOrdered` como `true` ao definir a classe.</span><span class="sxs-lookup"><span data-stu-id="5eb83-125">You can use comparison operators to compare values in your UDT if you have set the `IsByteOrdered` property to `true` when defining the class.</span></span> <span data-ttu-id="5eb83-126">Para obter mais informações, consulte [criando um tipo definido pelo usuário](creating-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="5eb83-126">For more information, see [Creating a User-Defined Type](creating-user-defined-types.md).</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Points   
FROM dbo.Points  
WHERE PointValue > CONVERT(Point, '2,2');  
```  
  
 <span data-ttu-id="5eb83-127">Você poderá comparar os valores internos do UDT independentemente da configuração de `IsByteOrdered` se os próprios valores forem comparáveis.</span><span class="sxs-lookup"><span data-stu-id="5eb83-127">You can compare internal values of the UDT regardless of the `IsByteOrdered` setting if the values themselves are comparable.</span></span> <span data-ttu-id="5eb83-128">A seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] seleciona linhas onde X é maior que Y:</span><span class="sxs-lookup"><span data-stu-id="5eb83-128">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects rows where X is greater than Y:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points  
WHERE PointValue.X < PointValue.Y;  
```  
  
 <span data-ttu-id="5eb83-129">Você também pode usar operadores de comparação com variáveis, como mostrado nesta consulta que procura um PointValue compatível.</span><span class="sxs-lookup"><span data-stu-id="5eb83-129">You can also use comparison operators with variables, as shown in this query that searches for a matching PointValue.</span></span>  
  
```  
DECLARE @ComparePoint Point;  
SET @ComparePoint = CONVERT(Point, '3,4');  
SELECT ID, PointValue.ToString() AS MatchingPoint   
FROM dbo.Points  
WHERE PointValue = @ComparePoint;  
```  
  
## <a name="invoking-udt-methods"></a><span data-ttu-id="5eb83-130">Invocando métodos UDT </span><span class="sxs-lookup"><span data-stu-id="5eb83-130">Invoking UDT Methods</span></span>  
 <span data-ttu-id="5eb83-131">Você também pode invocar métodos definidos em seu UDT no [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5eb83-131">You can also invoke methods that are defined in your UDT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5eb83-132">A classe **Point** contém três métodos, `Distance` , `DistanceFrom` e `DistanceFromXY` .</span><span class="sxs-lookup"><span data-stu-id="5eb83-132">The **Point** class contains three methods, `Distance`, `DistanceFrom`, and `DistanceFromXY`.</span></span> <span data-ttu-id="5eb83-133">Para as listagens de código que definem esses três métodos, consulte [codificação de tipos definidos pelo usuário](creating-user-defined-types-coding.md).</span><span class="sxs-lookup"><span data-stu-id="5eb83-133">For the code listings defining these three methods, see [Coding User-Defined Types](creating-user-defined-types-coding.md).</span></span>  
  
 <span data-ttu-id="5eb83-134">A seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] chama o método `PointValue.Distance`:</span><span class="sxs-lookup"><span data-stu-id="5eb83-134">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement calls the `PointValue.Distance` method:</span></span>  
  
```  
SELECT ID, PointValue.X AS [Point.X],   
    PointValue.Y AS [Point.Y],  
    PointValue.Distance() AS DistanceFromZero   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="5eb83-135">Os resultados são exibidos na `Distance` coluna:</span><span class="sxs-lookup"><span data-stu-id="5eb83-135">The results are displayed in the `Distance` column:</span></span>  
  
```  
IDXYDistance  
------------------------  
1345  
2155.09901951359278  
319999.0050503762308  
```  
  
 <span data-ttu-id="5eb83-136">O `DistanceFrom` método usa um argumento de tipo de dados **Point** e exibe a distância do ponto especificado para o PointValue:</span><span class="sxs-lookup"><span data-stu-id="5eb83-136">The `DistanceFrom` method takes an argument of **Point** data type, and displays the distance from the specified point to the PointValue:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Pnt,  
   PointValue.DistanceFrom(CONVERT(Point, '1,99')) AS DistanceFromPoint  
FROM dbo.Points;  
```  
  
 <span data-ttu-id="5eb83-137">Os resultados exibem os resultados do método `DistanceFrom` para cada linha da tabela:</span><span class="sxs-lookup"><span data-stu-id="5eb83-137">The results display the results of the `DistanceFrom` method for each row in the table:</span></span>  
  
```  
ID PntDistanceFromPoint  
---------------------  
13,495.0210502993942  
21,594  
31,990  
```  
  
 <span data-ttu-id="5eb83-138">O método `DistanceFromXY` usa os pontos individualmente como argumentos:</span><span class="sxs-lookup"><span data-stu-id="5eb83-138">The `DistanceFromXY` method takes the points individually as arguments:</span></span>  
  
```  
SELECT ID, PointValue.X as X, PointValue.Y as Y,   
PointValue.DistanceFromXY(1, 99) AS DistanceFromXY   
FROM dbo.Points  
```  
  
 <span data-ttu-id="5eb83-139">O conjunto de resultados é o mesmo que o método `DistanceFrom`.</span><span class="sxs-lookup"><span data-stu-id="5eb83-139">The result set is the same as the `DistanceFrom` method.</span></span>  
  
## <a name="updating-data-in-a-udt-column"></a><span data-ttu-id="5eb83-140">Atualizando dados em uma coluna UDT</span><span class="sxs-lookup"><span data-stu-id="5eb83-140">Updating Data in a UDT Column</span></span>  
 <span data-ttu-id="5eb83-141">Para atualizar dados em uma coluna UDT, use a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE.</span><span class="sxs-lookup"><span data-stu-id="5eb83-141">To update data in a UDT column, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement.</span></span> <span data-ttu-id="5eb83-142">Você também pode usar um método do UDT para atualizar o estado do objeto.</span><span class="sxs-lookup"><span data-stu-id="5eb83-142">You can also use a method of the UDT to update the state of the object.</span></span> <span data-ttu-id="5eb83-143">A seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] atualiza uma única linha na tabela:</span><span class="sxs-lookup"><span data-stu-id="5eb83-143">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates a single row in the table:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = CAST('1,88' AS Point)  
WHERE ID = 3  
```  
  
 <span data-ttu-id="5eb83-144">Você também pode atualizar elementos UDT separadamente.</span><span class="sxs-lookup"><span data-stu-id="5eb83-144">You can also update UDT elements separately.</span></span> <span data-ttu-id="5eb83-145">A seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] atualiza somente a coordenada Y:</span><span class="sxs-lookup"><span data-stu-id="5eb83-145">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates only the Y coordinate:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="5eb83-146">Se o UDT tiver sido definido com a ordenação de bytes definida como `true`, [!INCLUDE[tsql](../../includes/tsql-md.md)] poderá avaliar a coluna UDT em uma cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="5eb83-146">If the UDT has been defined with byte ordering set to `true`, [!INCLUDE[tsql](../../includes/tsql-md.md)] can evaluate the UDT column in a WHERE clause.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = '4,5'  
WHERE PointValue = '3,4';  
```  
  
### <a name="updating-limitations"></a><span data-ttu-id="5eb83-147">Atualizando limitações</span><span class="sxs-lookup"><span data-stu-id="5eb83-147">Updating Limitations</span></span>  
 <span data-ttu-id="5eb83-148">Você não pode atualizar várias propriedades de uma ver usando [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5eb83-148">You cannot update multiple properties at once using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5eb83-149">Por exemplo, a instrução UPDATE a seguir apresenta uma falha porque você não pode usar o mesmo nome de coluna duas vezes em uma única instrução UDATE.</span><span class="sxs-lookup"><span data-stu-id="5eb83-149">For example, the following UPDATE statement fails with an error because you cannot use the same column name twice in one UDATE statement.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.X = 5, PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="5eb83-150">Para atualizar cada ponto individualmente, você precisaria criar um método modificador no assembly UDT Point.</span><span class="sxs-lookup"><span data-stu-id="5eb83-150">To update each point individually, you would need to create a mutator method in the Point UDT assembly.</span></span> <span data-ttu-id="5eb83-151">Você pode invocar o método modificador para atualizar o objeto em uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5eb83-151">You can then invoke the mutator method to update the object in a [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement, as in the following:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.SetXY(5, 99)  
WHERE ID = 3  
```  
  
## <a name="deleting-data-in-a-udt-column"></a><span data-ttu-id="5eb83-152">Excluindo dados em uma coluna UDT</span><span class="sxs-lookup"><span data-stu-id="5eb83-152">Deleting Data in a UDT Column</span></span>  
 <span data-ttu-id="5eb83-153">Para excluir dados em um UDT, use a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE.</span><span class="sxs-lookup"><span data-stu-id="5eb83-153">To delete data in a UDT, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span> <span data-ttu-id="5eb83-154">A instrução a seguir exclui todas as linhas da tabela que correspondem aos critérios especificadas na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="5eb83-154">The following statement deletes all rows in the table that match the criteria specified in the WHERE clause.</span></span> <span data-ttu-id="5eb83-155">Se você omitir a cláusula WHERE em uma instrução DELETE, todas as linhas da tabela serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="5eb83-155">If you omit the WHERE clause in a DELETE statement, all rows in the table will be deleted.</span></span>  
  
```  
DELETE FROM dbo.Points  
WHERE PointValue = CAST('1,99' AS Point)  
```  
  
 <span data-ttu-id="5eb83-156">Use a instrução UPDATE se quiser remover os valores em uma coluna UDT e deixar os valores de outras linhas intactos.</span><span class="sxs-lookup"><span data-stu-id="5eb83-156">Use the UPDATE statement if you want to remove the values in a UDT column while leaving other row values intact.</span></span> <span data-ttu-id="5eb83-157">Este exemplo define PointValue como nulo.</span><span class="sxs-lookup"><span data-stu-id="5eb83-157">This example sets the PointValue to null.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = null  
WHERE ID = 2  
```  
  
## <a name="see-also"></a><span data-ttu-id="5eb83-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5eb83-158">See Also</span></span>  
 [<span data-ttu-id="5eb83-159">Trabalhando com tipos de dados definidos pelo usuário no SQL Server</span><span class="sxs-lookup"><span data-stu-id="5eb83-159">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
