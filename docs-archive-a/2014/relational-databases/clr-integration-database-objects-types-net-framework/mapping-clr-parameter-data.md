---
title: Mapeando dados de parâmetro CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlBinary data type
- SqlInt16 data type
- SqlMoney data type
- SqlString data type
- SqlSingle data type
- data types [CLR integration]
- SqlInt64 data type
- SqlDateTime data type
- SqlXml data type
- SqlBoolean data type
- SqlDecimal data type
- SqlBytes data type
- mapping data types [CLR integration]
- SqlChars data type
- SqlInt32 data type
ms.assetid: 89b43ee9-b9ad-4281-a4bf-c7c8d116daa2
author: rothja
ms.author: jroth
ms.openlocfilehash: 7025c5180eac793534961af63df9ac701c95c03f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685785"
---
# <a name="mapping-clr-parameter-data"></a><span data-ttu-id="aa36b-102">Mapeando dados de parâmetro CLR</span><span class="sxs-lookup"><span data-stu-id="aa36b-102">Mapping CLR Parameter Data</span></span>
  <span data-ttu-id="aa36b-103">A tabela a seguir lista os [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados, seus equivalentes no Common Language Runtime (CLR) para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no `System.Data.SqlTypes` namespace e seus equivalentes CLR nativos no [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aa36b-103">The following table lists [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, their equivalents in the common language runtime (CLR) for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the `System.Data.SqlTypes` namespace, and their native CLR equivalents in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="aa36b-104">**Tipo de dados do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="aa36b-104">**SQL Server data type**</span></span>|<span data-ttu-id="aa36b-105">Tipo (em System.Data.SqlTypes ou Microsoft.SqlServer.Types)</span><span class="sxs-lookup"><span data-stu-id="aa36b-105">Type (in System.Data.SqlTypes or Microsoft.SqlServer.Types)</span></span>|<span data-ttu-id="aa36b-106">**Tipo de dados CLR (.NET Framework)**</span><span class="sxs-lookup"><span data-stu-id="aa36b-106">**CLR data type (.NET Framework)**</span></span>|  
|`bigint`|`SqlInt64`|<span data-ttu-id="aa36b-107">**Int64, anulável\<Int64>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-107">**Int64, Nullable\<Int64>**</span></span>|  
|`binary`|`SqlBytes, SqlBinary`|`Byte[]`|  
|`bit`|`SqlBoolean`|<span data-ttu-id="aa36b-108">**Booliano, anulável\<Boolean>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-108">**Boolean, Nullable\<Boolean>**</span></span>|  
|`char`|<span data-ttu-id="aa36b-109">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-109">None</span></span>|<span data-ttu-id="aa36b-110">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-110">None</span></span>|  
|`cursor`|<span data-ttu-id="aa36b-111">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-111">None</span></span>|<span data-ttu-id="aa36b-112">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-112">None</span></span>|  
|`date`|`SqlDateTime`|<span data-ttu-id="aa36b-113">**DateTime, anulável\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-113">**DateTime, Nullable\<DateTime>**</span></span>|  
|`datetime`|`SqlDateTime`|<span data-ttu-id="aa36b-114">**DateTime, anulável\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-114">**DateTime, Nullable\<DateTime>**</span></span>|  
|`datetime2`|<span data-ttu-id="aa36b-115">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-115">None</span></span>|<span data-ttu-id="aa36b-116">**DateTime, anulável\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-116">**DateTime, Nullable\<DateTime>**</span></span>|  
|`DATETIMEOFFSET`|`None`|<span data-ttu-id="aa36b-117">**DateTimeOffset, anulável\<DateTimeOffset>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-117">**DateTimeOffset, Nullable\<DateTimeOffset>**</span></span>|  
|`decimal`|`SqlDecimal`|<span data-ttu-id="aa36b-118">**Decimal, anulável\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-118">**Decimal, Nullable\<Decimal>**</span></span>|  
|`float`|`SqlDouble`|<span data-ttu-id="aa36b-119">**Double, anulável\<Double>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-119">**Double, Nullable\<Double>**</span></span>|  
|`geography`|`SqlGeography`<br /><br /> <span data-ttu-id="aa36b-120">`SqlGeography`é definido no Microsoft.SqlServer.Types.dll, que é instalado com o SQL Server e pode ser baixado do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="aa36b-120">`SqlGeography` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="aa36b-121">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-121">None</span></span>|  
|`geometry`|`SqlGeometry`<br /><br /> <span data-ttu-id="aa36b-122">`SqlGeometry`é definido no Microsoft.SqlServer.Types.dll, que é instalado com o SQL Server e pode ser baixado do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="aa36b-122">`SqlGeometry` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="aa36b-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-123">None</span></span>|  
|`hierarchyid`|`SqlHierarchyId`<br /><br /> <span data-ttu-id="aa36b-124">`SqlHierarchyId`é definido no Microsoft.SqlServer.Types.dll, que é instalado com o SQL Server e pode ser baixado do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="aa36b-124">`SqlHierarchyId` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="aa36b-125">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-125">None</span></span>|  
|`image`|<span data-ttu-id="aa36b-126">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-126">None</span></span>|<span data-ttu-id="aa36b-127">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-127">None</span></span>|  
|`int`|`SqlInt32`|<span data-ttu-id="aa36b-128">**Int32, anulável\<Int32>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-128">**Int32, Nullable\<Int32>**</span></span>|  
|`money`|`SqlMoney`|<span data-ttu-id="aa36b-129">**Decimal, anulável\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-129">**Decimal, Nullable\<Decimal>**</span></span>|  
|`nchar`|`SqlChars, SqlString`|`String, Char[]`|  
|`ntext`|<span data-ttu-id="aa36b-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-130">None</span></span>|<span data-ttu-id="aa36b-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-131">None</span></span>|  
|`numeric`|`SqlDecimal`|<span data-ttu-id="aa36b-132">**Decimal, anulável\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-132">**Decimal, Nullable\<Decimal>**</span></span>|  
|`nvarchar`|`SqlChars, SqlString`<br /><br /> <span data-ttu-id="aa36b-133">`SQLChars` é uma melhor correspondência para transferência e acesso a dados, e `SQLString` é uma melhor correspondência para executar operações de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="aa36b-133">`SQLChars` is a better match for data transfer and access, and `SQLString` is a better match for performing String operations.</span></span>|`String, Char[]`|  
|`nvarchar(1), nchar(1)`|`SqlChars, SqlString`|<span data-ttu-id="aa36b-134">**Char, String, Char [], Nullable\<char>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-134">**Char, String, Char[], Nullable\<char>**</span></span>|  
|`real`|<span data-ttu-id="aa36b-135">`SqlSingle` (o intervalo de `SqlSingle`, no entanto, é maior que `real`)</span><span class="sxs-lookup"><span data-stu-id="aa36b-135">`SqlSingle` (the range of `SqlSingle`, however, is larger than `real`)</span></span>|<span data-ttu-id="aa36b-136">**Única, anulável\<Single>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-136">**Single, Nullable\<Single>**</span></span>|  
|`rowversion`|<span data-ttu-id="aa36b-137">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-137">None</span></span>|`Byte[]`|  
|`smallint`|`SqlInt16`|<span data-ttu-id="aa36b-138">**Int16, anulável\<Int16>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-138">**Int16, Nullable\<Int16>**</span></span>|  
|`smallmoney`|`SqlMoney`|<span data-ttu-id="aa36b-139">**Decimal, anulável\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-139">**Decimal, Nullable\<Decimal>**</span></span>|  
|`sql_variant`|<span data-ttu-id="aa36b-140">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-140">None</span></span>|`Object`|  
|`table`|<span data-ttu-id="aa36b-141">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-141">None</span></span>|<span data-ttu-id="aa36b-142">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-142">None</span></span>|  
|`text`|<span data-ttu-id="aa36b-143">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-143">None</span></span>|<span data-ttu-id="aa36b-144">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-144">None</span></span>|  
|`time`|<span data-ttu-id="aa36b-145">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-145">None</span></span>|<span data-ttu-id="aa36b-146">**TimeSpan, anulável\<TimeSpan>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-146">**TimeSpan, Nullable\<TimeSpan>**</span></span>|  
|`timestamp`|<span data-ttu-id="aa36b-147">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-147">None</span></span>|<span data-ttu-id="aa36b-148">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-148">None</span></span>|  
|`tinyint`|`SqlByte`|<span data-ttu-id="aa36b-149">**Byte, anulável\<Byte>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-149">**Byte, Nullable\<Byte>**</span></span>|  
|`uniqueidentifier`|`SqlGuid`|<span data-ttu-id="aa36b-150">**GUID, anulável\<Guid>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-150">**Guid, Nullable\<Guid>**</span></span>|  
|`User-defined type(UDT)`|<span data-ttu-id="aa36b-151">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-151">None</span></span>|<span data-ttu-id="aa36b-152">A mesma classe que é associada ao tipo definido pelo usuário no mesmo assembly ou em um assembly dependente.</span><span class="sxs-lookup"><span data-stu-id="aa36b-152">The same class that is bound to the user-defined type in the same assembly or a dependent assembly.</span></span>|  
|<span data-ttu-id="aa36b-153">**varbinary**</span><span class="sxs-lookup"><span data-stu-id="aa36b-153">**varbinary**</span></span>|`SqlBytes, SqlBinary`|`Byte[]`|  
|`varbinary(1), binary(1)`|`SqlBytes, SqlBinary`|<span data-ttu-id="aa36b-154">**byte, Byte [], anulável\<byte>**</span><span class="sxs-lookup"><span data-stu-id="aa36b-154">**byte, Byte[], Nullable\<byte>**</span></span>|  
|`varchar`|<span data-ttu-id="aa36b-155">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-155">None</span></span>|<span data-ttu-id="aa36b-156">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-156">None</span></span>|  
|`xml`|`SqlXml`|<span data-ttu-id="aa36b-157">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa36b-157">None</span></span>|  
  
## <a name="automatic-data-type-conversion-with-out-parameters"></a><span data-ttu-id="aa36b-158">Conversão automática de tipo de dados com parâmetros out</span><span class="sxs-lookup"><span data-stu-id="aa36b-158">Automatic Data Type Conversion with Out Parameters</span></span>  
 <span data-ttu-id="aa36b-159">Um método CLR pode retornar informações para o código de chamada ou programa marcando um parâmetro input com o modificador `out` (Microsoft Visual C#) ou `<Out()> ByRef` (Microsoft Visual Basic). Se o parâmetro input for um tipo de dados CLR no namespace `System.Data.SqlTypes`, e o programa de chamada especificar seu tipo de dados equivalente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como o parâmetro input, uma conversão de tipo ocorrerá automaticamente quando o método CLR retorna o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="aa36b-159">A CLR method can return information to the calling code or program by marking an input parameter with the `out` modifier (Microsoft Visual C#) or `<Out()> ByRef` (Microsoft Visual Basic) If the input parameter is a CLR data type in the `System.Data.SqlTypes` namespace, and the calling program specifies its equivalent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type as the input parameter, a type conversion occurs automatically when the CLR method returns the data type.</span></span>  
  
 <span data-ttu-id="aa36b-160">Por exemplo, o seguinte procedimento armazenado CLR tem um parâmetro input do tipo de dados CLR `SqlInt32` que é marcado com `out` (C#) ou `<Out()> ByRef` (Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="aa36b-160">For example, the following CLR stored procedure has an input parameter of `SqlInt32` CLR data type that is marked with `out` (C#) or `<Out()> ByRef` (Visual Basic):</span></span>  
  
```csharp  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void PriceSum(out SqlInt32 value)  
{ ... }  
```  
  
```vb  
<Microsoft.SqlServer.Server.SqlProcedure> _  
Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
...  
End Sub  
```  
  
 <span data-ttu-id="aa36b-161">Depois que o assembly é criado no banco de dados, o procedimento armazenado é criado no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com a seguinte Transact-SQL, que especifica um tipo de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de `int` como um parâmetro OUTPUT:</span><span class="sxs-lookup"><span data-stu-id="aa36b-161">After the assembly is built and created in the database, the stored procedure is created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the following Transact-SQL, which specifies a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of `int` as an OUTPUT parameter:</span></span>  
  
```  
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
```  
  
 <span data-ttu-id="aa36b-162">Quando o procedimento armazenado CLR é chamado, o tipo de dados `SqlInt32` é automaticamente convertido em um tipo de dados `int` e retornado para o programa de chamada.</span><span class="sxs-lookup"><span data-stu-id="aa36b-162">When the CLR stored procedure is called, the `SqlInt32` data type is automatically converted to an `int` data type, and returned to the calling program.</span></span>  
  
 <span data-ttu-id="aa36b-163">Entretanto, nem todos os tipos de dados CLR podem ser automaticamente convertidos em seus tipos de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] equivalentes por um fora parâmetro out.</span><span class="sxs-lookup"><span data-stu-id="aa36b-163">Not all CLR data types can be automatically converted to their equivalent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types through an out parameter, however.</span></span> <span data-ttu-id="aa36b-164">A tabela a seguir lista estas exceções.</span><span class="sxs-lookup"><span data-stu-id="aa36b-164">The following table lists these exceptions.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa36b-165">**Tipo de dados CLR (SQL Server)**</span><span class="sxs-lookup"><span data-stu-id="aa36b-165">**CLR data type (SQL Server)**</span></span>|<span data-ttu-id="aa36b-166">**Tipo de dados do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="aa36b-166">**SQL Server data type**</span></span>|  
|`Decimal`|<span data-ttu-id="aa36b-167">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="aa36b-167">smallmoney</span></span>|  
|`SqlMoney`|<span data-ttu-id="aa36b-168">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="aa36b-168">smallmoney</span></span>|  
|`Decimal`|<span data-ttu-id="aa36b-169">money</span><span class="sxs-lookup"><span data-stu-id="aa36b-169">money</span></span>|  
|`DateTime`|<span data-ttu-id="aa36b-170">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="aa36b-170">smalldatetime</span></span>|  
|`SQLDateTime`|<span data-ttu-id="aa36b-171">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="aa36b-171">smalldatetime</span></span>|  
  
## <a name="change-history"></a><span data-ttu-id="aa36b-172">Histórico de alterações</span><span class="sxs-lookup"><span data-stu-id="aa36b-172">Change History</span></span>  
  
|<span data-ttu-id="aa36b-173">Conteúdo atualizado</span><span class="sxs-lookup"><span data-stu-id="aa36b-173">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="aa36b-174">Adicionados os tipos `SqlGeography`, `SqlGeometry` e `SqlHierarchyId` à tabela de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="aa36b-174">Added `SqlGeography`, `SqlGeometry`, and `SqlHierarchyId` types to the mapping table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa36b-175">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa36b-175">See Also</span></span>  
 [<span data-ttu-id="aa36b-176">Tipos de dados do SQL Server no .NET Framework</span><span class="sxs-lookup"><span data-stu-id="aa36b-176">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
