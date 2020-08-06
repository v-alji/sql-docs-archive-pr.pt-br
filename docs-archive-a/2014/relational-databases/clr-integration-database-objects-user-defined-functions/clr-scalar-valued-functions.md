---
title: Funções de valor escalar CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- SVF
- scalar-valued functions
ms.assetid: 20dcf802-c27d-4722-9cd3-206b1e77bee0
author: rothja
ms.author: jroth
ms.openlocfilehash: be8f9616fb285d6a68d6734924874ded06fb3bd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679991"
---
# <a name="clr-scalar-valued-functions"></a><span data-ttu-id="a356a-102">Funções de valor escalar CLR</span><span class="sxs-lookup"><span data-stu-id="a356a-102">CLR Scalar-Valued Functions</span></span>
  <span data-ttu-id="a356a-103">Uma função de valor escalar (SVF) retorna um único valor, como uma cadeia de caracteres, um inteiro ou um valor de bit. Você pode criar funções de valor escalar definidas pelo usuário em código gerenciado usando qualquer linguagem de programação do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a356a-103">A scalar-valued function (SVF) returns a single value, such as a string, integer, or bit value.You can create scalar-valued user-defined functions in managed code using any .NET Framework programming language.</span></span> <span data-ttu-id="a356a-104">Essas funções são acessíveis a [!INCLUDE[tsql](../../includes/tsql-md.md)] ou outro código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="a356a-104">These functions are accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span> <span data-ttu-id="a356a-105">Para obter informações sobre as vantagens da integração CLR e como escolher entre código gerenciado e [!INCLUDE[tsql](../../includes/tsql-md.md)] , consulte [visão geral da integração do CLR](../clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a356a-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-scalar-valued-functions"></a><span data-ttu-id="a356a-106">Requisitos das funções de valor escalar do CLR</span><span class="sxs-lookup"><span data-stu-id="a356a-106">Requirements for CLR Scalar-Valued Functions</span></span>  
 <span data-ttu-id="a356a-107">As SVFs do .NET Framework são implementadas como métodos em uma classe de um assembly do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a356a-107">.NET Framework SVFs are implemented as methods on a class in a .NET Framework assembly.</span></span> <span data-ttu-id="a356a-108">Os parâmetros de entrada e o tipo retornado de um SVF podem ser qualquer um dos tipos de dados escalares com suporte no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , exceto `varchar` ,,,,,, `char` `rowversion` `text` `ntext` `image` `timestamp` , `table` ou `cursor` .</span><span class="sxs-lookup"><span data-stu-id="a356a-108">The input parameters and the type returned from a SVF can be any of the scalar data types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except `varchar`, `char`, `rowversion`, `text`, `ntext`, `image`, `timestamp`, `table`, or `cursor`.</span></span> <span data-ttu-id="a356a-109">As SVFs devem garantir uma correspondência entre o tipo de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o tipo de dados de retorno do método de implementação.</span><span class="sxs-lookup"><span data-stu-id="a356a-109">SVFs must ensure a match between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type and the return data type of the implementation method.</span></span> <span data-ttu-id="a356a-110">Para obter mais informações sobre conversões de tipo, consulte [mapeando dados de parâmetro CLR](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="a356a-110">For more information about type conversions, see [Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
 <span data-ttu-id="a356a-111">Ao implementar uma SVF do .NET Framework em uma linguagem do .NET Framework, o atributo personalizado `SqlFunction` pode ser especificado para incluir informações adicionais sobre a função.</span><span class="sxs-lookup"><span data-stu-id="a356a-111">When implementing a .NET Framework SVF in a .NET Framework language, the `SqlFunction` custom attribute can be specified to include additional information about the function.</span></span> <span data-ttu-id="a356a-112">O atributo `SqlFunction` indica se a função acessa ou modifica os dados, se é determinística e se envolve operações de ponto flutuante.</span><span class="sxs-lookup"><span data-stu-id="a356a-112">The `SqlFunction` attribute indicates whether or not the function accesses or modifies data, if it is deterministic, and if the function involves floating point operations.</span></span>  
  
 <span data-ttu-id="a356a-113">Funções de valor escalar definidas pelo usuário podem ser determinísticas ou não.</span><span class="sxs-lookup"><span data-stu-id="a356a-113">Scalar-valued user-defined functions may be deterministic or non-deterministic.</span></span> <span data-ttu-id="a356a-114">Uma função determinística sempre retorna o mesmo resultado quando chamada com um conjunto de parâmetros de entrada específico.</span><span class="sxs-lookup"><span data-stu-id="a356a-114">A deterministic function always returns the same result when it is called with a specific set of input parameters.</span></span> <span data-ttu-id="a356a-115">Uma função não determinística pode retornar resultados diferentes quando chamada com um conjunto de parâmetros de entrada específico.</span><span class="sxs-lookup"><span data-stu-id="a356a-115">A non-deterministic function may return different results when it is called with a specific set of input parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a356a-116">Não marque uma função como determinística se ela sempre produzir os mesmos valores de saída, considerando os mesmos valores de entrada e o mesmo estado do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a356a-116">Do not mark a function as deterministic if the function does not always produces the same output values, given the same input values and the same database state.</span></span> <span data-ttu-id="a356a-117">A marcação de uma função como determinística, quando a função, de fato, não é pode resultar em exibições indexadas e colunas computadas danificadas.</span><span class="sxs-lookup"><span data-stu-id="a356a-117">Marking a function as deterministic, when the function isn't truly deterministic can result in corrupted indexed views and computed columns.</span></span> <span data-ttu-id="a356a-118">Você marca uma função como determinística definindo a propriedade `IsDeterministic` como true.</span><span class="sxs-lookup"><span data-stu-id="a356a-118">You mark a function as deterministic by setting the `IsDeterministic` property to true.</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="a356a-119">Parâmetros de valores de tabela</span><span class="sxs-lookup"><span data-stu-id="a356a-119">Table-Valued Parameters</span></span>  
 <span data-ttu-id="a356a-120">Os TVPs (parâmetros com valor de tabela), ou seja, tipos de tabela definidos pelo usuário transmitidos para um procedimento ou uma função, oferecem uma maneira eficiente de passar várias linhas de dados para o servidor.</span><span class="sxs-lookup"><span data-stu-id="a356a-120">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="a356a-121">Os TVPs proporcionam funcionalidade semelhante para matrizes de parâmetro, porém com maior flexibilidade e integração com [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a356a-121">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a356a-122">Eles também fornecem o potencial para melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="a356a-122">They also provide the potential for better performance.</span></span> <span data-ttu-id="a356a-123">Os TVPs também ajudam a reduzir o número de viagens de ida e volta para o servidor.</span><span class="sxs-lookup"><span data-stu-id="a356a-123">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="a356a-124">Em vez de enviar várias solicitações ao servidor, como com uma lista de parâmetros escalares, os dados podem ser enviados ao servidor como um TVP.</span><span class="sxs-lookup"><span data-stu-id="a356a-124">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="a356a-125">Um tipo de tabela definido pelo usuário não pode ser passado como um parâmetro com valor de tabela para, ou ser retornado de, um procedimento armazenado ou uma função gerenciada(o) que é executada(o) no processo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a356a-125">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="a356a-126">Para obter mais informações sobre TVPs, consulte [usar parâmetros com valor de tabela &#40;Mecanismo de Banco de Dados&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="a356a-126">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="example-of-a-clr-scalar-valued-function"></a><span data-ttu-id="a356a-127">Exemplo de uma função de valor escalar do CLR</span><span class="sxs-lookup"><span data-stu-id="a356a-127">Example of a CLR Scalar-Valued Function</span></span>  
 <span data-ttu-id="a356a-128">Eis uma SVF simples que acessa dados e retorna um valor inteiro:</span><span class="sxs-lookup"><span data-stu-id="a356a-128">Here is a simple SVF that accesses data and returns an integer value:</span></span>  
  
```csharp  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public class T  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static int ReturnOrderCount()  
    {  
        using (SqlConnection conn   
            = new SqlConnection("context connection=true"))  
        {  
            conn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
            return (int)cmd.ExecuteScalar();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public Class T  
    <SqlFunction(DataAccess:=DataAccessKind.Read)> _  
    Public Shared Function ReturnOrderCount() As Integer  
        Using conn As New SqlConnection("context connection=true")  
            conn.Open()  
            Dim cmd As New SqlCommand("SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
            Return CType(cmd.ExecuteScalar(), Integer)  
        End Using  
    End Function  
End Class  
```  
  
 <span data-ttu-id="a356a-129">A primeira linha de código referencia `Microsoft.SqlServer.Server` para acessar atributos e `System.Data.SqlClient` para acessar o namespace do ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a356a-129">The first line of code references `Microsoft.SqlServer.Server` to access attributes and `System.Data.SqlClient` to access the ADO.NET namespace.</span></span> <span data-ttu-id="a356a-130">(Esse namespace contém `SqlClient`, o provedor de dados .NET Framework para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="a356a-130">(This namespace contains `SqlClient`, the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="a356a-131">Em seguida, a função recebe o atributo personalizado `SqlFunction`, encontrado no namespace `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="a356a-131">Next, the function receives the `SqlFunction` custom attribute, which is found in the `Microsoft.SqlServer.Server` namespace.</span></span> <span data-ttu-id="a356a-132">O atributo personalizado indica se a UDF (função definida pelo usuário) usa ou não o provedor em processo para ler dados no servidor.</span><span class="sxs-lookup"><span data-stu-id="a356a-132">The custom attribute indicates whether or not the user-defined function (UDF) uses the in-process provider to read data in the server.</span></span> <span data-ttu-id="a356a-133">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não permite que as UDFs atualizem, insiram ou excluam dados.</span><span class="sxs-lookup"><span data-stu-id="a356a-133">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow UDFs to update, insert, or delete data.</span></span> <span data-ttu-id="a356a-134">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode otimizar a execução de uma UDF que não usa o provedor em processo.</span><span class="sxs-lookup"><span data-stu-id="a356a-134">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can optimize execution of a UDF that does not use the in-process provider.</span></span> <span data-ttu-id="a356a-135">Isso é indicado com a definição de `DataAccessKind` como `DataAccessKind.None`.</span><span class="sxs-lookup"><span data-stu-id="a356a-135">This is indicated by setting `DataAccessKind` to `DataAccessKind.None`.</span></span> <span data-ttu-id="a356a-136">Na próxima linha, o método de destino é uma estática pública (compartilhada no Visual Basic .NET).</span><span class="sxs-lookup"><span data-stu-id="a356a-136">On the next line, the target method is a public static (shared in Visual Basic .NET).</span></span>  
  
 <span data-ttu-id="a356a-137">Dessa forma, a classe `SqlContext`, localizada no namespace `Microsoft.SqlServer.Server`, pode acessar um objeto `SqlCommand` com uma conexão com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] já configurada.</span><span class="sxs-lookup"><span data-stu-id="a356a-137">The `SqlContext` class, located in the `Microsoft.SqlServer.Server` namespace, can then access a `SqlCommand` object with a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is already set up.</span></span> <span data-ttu-id="a356a-138">Embora não seja usado aqui, o contexto de transação atual também está disponível por meio da API `System.Transactions`.</span><span class="sxs-lookup"><span data-stu-id="a356a-138">Although not used here, the current transaction context is also available through the `System.Transactions` application programming interface (API).</span></span>  
  
 <span data-ttu-id="a356a-139">A maior parte das linhas de código no corpo da função deve parecer familiar aos desenvolvedores que já criaram aplicativos cliente que usam os tipos encontrados no namespace `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="a356a-139">Most of the lines of code in the function body should look familiar to developers who have written client applications that use the types found in the `System.Data.SqlClient` namespace.</span></span>  
  
 <span data-ttu-id="a356a-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="a356a-140">[C#]</span></span>  
  
```  
using(SqlConnection conn = new SqlConnection("context connection=true"))   
{  
   conn.Open();  
   SqlCommand cmd = new SqlCommand(  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
   return (int) cmd.ExecuteScalar();  
}    
```  
  
 <span data-ttu-id="a356a-141">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="a356a-141">[Visual Basic]</span></span>  
  
```  
Using conn As New SqlConnection("context connection=true")  
   conn.Open()  
   Dim cmd As New SqlCommand( _  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
   Return CType(cmd.ExecuteScalar(), Integer)  
End Using  
```  
  
 <span data-ttu-id="a356a-142">O texto de comando apropriado é especificado com a inicialização do objeto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="a356a-142">The appropriate command text is specified by initializing the `SqlCommand` object.</span></span> <span data-ttu-id="a356a-143">O exemplo anterior conta o número de linhas na tabela `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="a356a-143">The previous example counts the number of rows in table `SalesOrderHeader`.</span></span> <span data-ttu-id="a356a-144">Em seguida, o método `ExecuteScalar` do objeto `cmd` é chamado.</span><span class="sxs-lookup"><span data-stu-id="a356a-144">Next, the `ExecuteScalar` method of the `cmd` object is called.</span></span> <span data-ttu-id="a356a-145">Isso retorna um valor do tipo `int` com base na consulta.</span><span class="sxs-lookup"><span data-stu-id="a356a-145">This returns a value of type `int` based on the query.</span></span> <span data-ttu-id="a356a-146">Por fim, a contagem da ordem retorna ao chamador.</span><span class="sxs-lookup"><span data-stu-id="a356a-146">Finally, the order count is returned to the caller.</span></span>  
  
 <span data-ttu-id="a356a-147">Caso seja salvo em um arquivo chamado FirstUdf.cs, esse código pode ser compilado como assembly da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="a356a-147">If this code is saved in a file called FirstUdf.cs, it could be compiled into as assembly as follows:</span></span>  
  
 <span data-ttu-id="a356a-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="a356a-148">[C#]</span></span>  
  
```  
csc.exe /t:library /out:FirstUdf.dll FirstUdf.cs   
```  
  
 <span data-ttu-id="a356a-149">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="a356a-149">[Visual Basic]</span></span>  
  
```  
vbc.exe /t:library /out:FirstUdf.dll FirstUdf.vb  
```  
  
> [!NOTE]  
>  <span data-ttu-id="a356a-150">`/t:library` indica que uma biblioteca, e não um executável, deve ser produzida.</span><span class="sxs-lookup"><span data-stu-id="a356a-150">`/t:library` indicates that a library, rather than an executable, should be produced.</span></span> <span data-ttu-id="a356a-151">Os executáveis não podem ser registrados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a356a-151">Executables cannot be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a356a-152">Não há suporte para objetos de banco de dados do Visual C++ compilados com `/clr:pure` para a execução no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a356a-152">Visual C++ database objects compiled with `/clr:pure` are not supported for execution on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a356a-153">Por exemplo, entre esses objetos de banco de dados estão funções de valor escalar.</span><span class="sxs-lookup"><span data-stu-id="a356a-153">For example, such database objects include scalar-valued functions.</span></span>  
  
 <span data-ttu-id="a356a-154">A consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] e uma invocação de exemplo de registro do assembly e da UDF são:</span><span class="sxs-lookup"><span data-stu-id="a356a-154">The [!INCLUDE[tsql](../../includes/tsql-md.md)] query and a sample invocation to register the assembly and UDF are:</span></span>  
  
```  
CREATE ASSEMBLY FirstUdf FROM 'FirstUdf.dll';  
GO  
  
CREATE FUNCTION CountSalesOrderHeader() RETURNS INT   
AS EXTERNAL NAME FirstUdf.T.ReturnOrderCount;   
GO  
  
SELECT dbo.CountSalesOrderHeader();  
GO  
  
```  
  
 <span data-ttu-id="a356a-155">Observe que o nome da função como exposto em [!INCLUDE[tsql](../../includes/tsql-md.md)] não precisa corresponder ao nome do método estático público de destino.</span><span class="sxs-lookup"><span data-stu-id="a356a-155">Note that the function name as exposed in [!INCLUDE[tsql](../../includes/tsql-md.md)] does not need to match the name of the target public static method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a356a-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a356a-156">See Also</span></span>  
 <span data-ttu-id="a356a-157">[Mapeando dados de parâmetro CLR](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span><span class="sxs-lookup"><span data-stu-id="a356a-157">[Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span></span>  
 <span data-ttu-id="a356a-158">[Visão geral dos atributos personalizados de integração CLR](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="a356a-158">[Overview of CLR Integration Custom Attributes](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span></span>  
 <span data-ttu-id="a356a-159">[Funções definidas pelo usuário](../user-defined-functions/user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="a356a-159">[User-Defined Functions](../user-defined-functions/user-defined-functions.md) </span></span>  
 [<span data-ttu-id="a356a-160">Acesso aos dados dos objetos de banco de dados CLR</span><span class="sxs-lookup"><span data-stu-id="a356a-160">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
