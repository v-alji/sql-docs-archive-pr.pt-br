---
title: SQLColAttribute | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLColAttribute function
ms.assetid: a5387d9e-a243-4cfe-b786-7fad5842b1d6
author: rothja
ms.author: jroth
ms.openlocfilehash: 10207fe12a7bea5b5edb8c6e558aec6ce3b2f148
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572999"
---
# <a name="sqlcolattribute"></a><span data-ttu-id="4f19a-102">SQLColAttribute</span><span class="sxs-lookup"><span data-stu-id="4f19a-102">SQLColAttribute</span></span>
  <span data-ttu-id="4f19a-103">Você pode usar `SQLColAttribute` para recuperar um atributo de uma coluna de conjunto de resultados para instruções ODBC preparadas ou executadas.</span><span class="sxs-lookup"><span data-stu-id="4f19a-103">You can use `SQLColAttribute` to retrieve an attribute of a result set column for either prepared or executed ODBC statements.</span></span> <span data-ttu-id="4f19a-104">Chamar as `SQLColAttribute` instruções preparadas causa uma ida e volta para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f19a-104">Calling `SQLColAttribute` on prepared statements causes a roundtrip to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4f19a-105">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client recebe dados de coluna do conjunto de resultados como parte da execução da instrução, portanto, chamar `SQLColAttribute` após a conclusão de **SQLExecute** ou **SQLExecDirect** não envolve um ida e volta do servidor.</span><span class="sxs-lookup"><span data-stu-id="4f19a-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver receives result set column data as part of statement execution, so calling `SQLColAttribute` after the completion of **SQLExecute** or **SQLExecDirect** does not involve a server roundtrip.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f19a-106">Os atributos do identificador de coluna ODBC não estão disponíveis em todos os conjuntos de resultados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f19a-106">ODBC column identifier attributes are not available on all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] result sets.</span></span>  
  
|<span data-ttu-id="4f19a-107">Identificador de campo</span><span class="sxs-lookup"><span data-stu-id="4f19a-107">Field identifier</span></span>|<span data-ttu-id="4f19a-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="4f19a-108">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="4f19a-109">SQL_COLUMN_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-109">SQL_COLUMN_TABLE_NAME</span></span>|<span data-ttu-id="4f19a-110">Disponível em conjuntos de resultados recuperados de instruções que geram cursores de servidor ou em instruções SELECT executadas que contêm uma cláusula FOR BROWSE.</span><span class="sxs-lookup"><span data-stu-id="4f19a-110">Available on result sets retrieved from statements that generate server cursors or on executed SELECT statements containing a FOR BROWSE clause.</span></span>|  
|<span data-ttu-id="4f19a-111">SQL_DESC_BASE_COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-111">SQL_DESC_BASE_COLUMN_NAME</span></span>|<span data-ttu-id="4f19a-112">Disponível em conjuntos de resultados recuperados de instruções que geram cursores de servidor ou em instruções SELECT executadas que contêm uma cláusula FOR BROWSE.</span><span class="sxs-lookup"><span data-stu-id="4f19a-112">Available on result sets retrieved from statements that generate server cursors or on executed SELECT statements containing a FOR BROWSE clause.</span></span>|  
|<span data-ttu-id="4f19a-113">SQL_DESC_BASE_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-113">SQL_DESC_BASE_TABLE_NAME</span></span>|<span data-ttu-id="4f19a-114">Disponível em conjuntos de resultados recuperados de instruções que geram cursores de servidor ou em instruções SELECT executadas que contêm uma cláusula FOR BROWSE.</span><span class="sxs-lookup"><span data-stu-id="4f19a-114">Available on result sets retrieved from statements that generate server cursors or on executed SELECT statements containing a FOR BROWSE clause.</span></span>|  
|<span data-ttu-id="4f19a-115">SQL_DESC_CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-115">SQL_DESC_CATALOG_NAME</span></span>|<span data-ttu-id="4f19a-116">nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4f19a-116">Database name.</span></span> <span data-ttu-id="4f19a-117">Disponível em conjuntos de resultados recuperados de instruções que geram cursores de servidor ou em instruções SELECT executadas que contêm uma cláusula FOR BROWSE.</span><span class="sxs-lookup"><span data-stu-id="4f19a-117">Available on result sets retrieved from statements that generate server cursors or on executed SELECT statements containing a FOR BROWSE clause.</span></span>|  
|<span data-ttu-id="4f19a-118">SQL_DESC_LABEL</span><span class="sxs-lookup"><span data-stu-id="4f19a-118">SQL_DESC_LABEL</span></span>|<span data-ttu-id="4f19a-119">Disponível em todos os conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="4f19a-119">Available on all result sets.</span></span> <span data-ttu-id="4f19a-120">O valor é idêntico ao valor do campo SQL_DESC_NAME.</span><span class="sxs-lookup"><span data-stu-id="4f19a-120">The value is identical to the value of the SQL_DESC_NAME field.</span></span><br /><br /> <span data-ttu-id="4f19a-121">O campo só terá comprimento zero se uma coluna for o resultado de uma expressão e a expressão não contiver uma atribuição de rótulo.</span><span class="sxs-lookup"><span data-stu-id="4f19a-121">The field is zero length only if a column is the result of an expression and the expression does not contain a label assignment.</span></span>|  
|<span data-ttu-id="4f19a-122">SQL_DESC_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-122">SQL_DESC_NAME</span></span>|<span data-ttu-id="4f19a-123">Disponível em todos os conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="4f19a-123">Available on all result sets.</span></span> <span data-ttu-id="4f19a-124">O valor é idêntico ao valor do campo SQL_DESC_LABEL.</span><span class="sxs-lookup"><span data-stu-id="4f19a-124">The value is identical to the value of the SQL_DESC_LABEL field.</span></span><br /><br /> <span data-ttu-id="4f19a-125">O campo só terá comprimento zero se uma coluna for o resultado de uma expressão e a expressão não contiver uma atribuição de rótulo.</span><span class="sxs-lookup"><span data-stu-id="4f19a-125">The field is zero length only if a column is the result of an expression and the expression does not contain a label assignment.</span></span>|  
|<span data-ttu-id="4f19a-126">SQL_DESC_SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-126">SQL_DESC_SCHEMA_NAME</span></span>|<span data-ttu-id="4f19a-127">Nome do proprietário.</span><span class="sxs-lookup"><span data-stu-id="4f19a-127">Owner name.</span></span> <span data-ttu-id="4f19a-128">Disponível em conjuntos de resultados recuperados de instruções que geram cursores de servidor ou em instruções SELECT executadas que contêm uma cláusula FOR BROWSE.</span><span class="sxs-lookup"><span data-stu-id="4f19a-128">Available on result sets retrieved from statements that generate server cursors or on executed SELECT statements containing a FOR BROWSE clause.</span></span><br /><br /> <span data-ttu-id="4f19a-129">Disponível somente se o nome do proprietário for especificado para a coluna na instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="4f19a-129">Available only if the owner name is specified for the column in the SELECT statement.</span></span>|  
|<span data-ttu-id="4f19a-130">SQL_DESC_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-130">SQL_DESC_TABLE_NAME</span></span>|<span data-ttu-id="4f19a-131">Disponível em conjuntos de resultados recuperados de instruções que geram cursores de servidor ou em instruções SELECT executadas que contêm uma cláusula FOR BROWSE.</span><span class="sxs-lookup"><span data-stu-id="4f19a-131">Available on result sets retrieved from statements that generate server cursors or on executed SELECT statements containing a FOR BROWSE clause.</span></span>|  
|<span data-ttu-id="4f19a-132">SQL_DESC_UNNAMED</span><span class="sxs-lookup"><span data-stu-id="4f19a-132">SQL_DESC_UNNAMED</span></span>|<span data-ttu-id="4f19a-133">SQL_NAMED para todas as colunas de um conjunto de resultados, a menos que uma coluna seja o resultado de uma expressão que não contém uma atribuição de rótulo como parte da expressão.</span><span class="sxs-lookup"><span data-stu-id="4f19a-133">SQL_NAMED for all columns in a result set unless a column is the result of an expression that does not contain a label assignment as part of the expression.</span></span> <span data-ttu-id="4f19a-134">Quando SQL_DESC_UNNAMED retorna SQL_UNNAMED, todos os atributos de identificador de coluna ODBC contêm cadeias de caracteres de comprimento zero para a coluna.</span><span class="sxs-lookup"><span data-stu-id="4f19a-134">When SQL_DESC_UNNAMED returns SQL_UNNAMED, all ODBC column identifier attributes contain zero length strings for the column.</span></span>|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="4f19a-135">O driver ODBC do Native Client usa a instrução SET FMTONLY para reduzir a sobrecarga do servidor quando `SQLColAttribute` é chamado para instruções preparadas, mas não executadas.</span><span class="sxs-lookup"><span data-stu-id="4f19a-135">Native Client ODBC driver uses the SET FMTONLY statement to reduce server overhead when `SQLColAttribute` is called for prepared but unexecuted statements.</span></span>  
  
 <span data-ttu-id="4f19a-136">Para tipos de valor grande, `SQLColAttribute` o retornará os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="4f19a-136">For large value types, `SQLColAttribute` will return the following values:</span></span>  
  
|<span data-ttu-id="4f19a-137">Identificador de campo</span><span class="sxs-lookup"><span data-stu-id="4f19a-137">Field identifier</span></span>|<span data-ttu-id="4f19a-138">Descrição de alteração</span><span class="sxs-lookup"><span data-stu-id="4f19a-138">Description of change</span></span>|  
|----------------------|---------------------------|  
|<span data-ttu-id="4f19a-139">SQL_DESC_DISPLAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="4f19a-139">SQL_DESC_DISPLAY_SIZE</span></span>|<span data-ttu-id="4f19a-140">Esse é o número máximo de caracteres necessários para exibir dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="4f19a-140">This is the maximum number of characters required to display data from the column.</span></span> <span data-ttu-id="4f19a-141">Para colunas de tipos de valores grandes, o valor retornado é SQL_SS_LENGTH_UNLIMITED.</span><span class="sxs-lookup"><span data-stu-id="4f19a-141">For large value type columns, the value returned is SQL_SS_LENGTH_UNLIMITED.</span></span>|  
|<span data-ttu-id="4f19a-142">SQL_DESC_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4f19a-142">SQL_DESC_LENGTH</span></span>|<span data-ttu-id="4f19a-143">Retorna o comprimento real da coluna no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4f19a-143">Returns the actual length of the column in the result set.</span></span> <span data-ttu-id="4f19a-144">Para colunas de tipos de valores grandes, o valor retornado é SQL_SS_LENGTH_UNLIMITED.</span><span class="sxs-lookup"><span data-stu-id="4f19a-144">For large value type columns, the value returned is SQL_SS_LENGTH_UNLIMITED.</span></span>|  
|<span data-ttu-id="4f19a-145">SQL_DESC_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="4f19a-145">SQL_DESC_OCTET_LENGTH</span></span>|<span data-ttu-id="4f19a-146">Retorna o comprimento de máximo de uma coluna de tipo de valor grande.</span><span class="sxs-lookup"><span data-stu-id="4f19a-146">Returns the maximum length of a large value type column.</span></span> <span data-ttu-id="4f19a-147">SQL_SS_LENGTH_UNLIMITED é usado para indicar tamanho ilimitado.</span><span class="sxs-lookup"><span data-stu-id="4f19a-147">SQL_SS_LENGTH_UNLIMITED is used to indicate unlimited size.</span></span>|  
|<span data-ttu-id="4f19a-148">SQL_DESC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="4f19a-148">SQL_DESC_PRECISION</span></span>|<span data-ttu-id="4f19a-149">Retorna o valor SQL_SS_LENGTH_UNLIMITED para colunas de tipo de valor grande.</span><span class="sxs-lookup"><span data-stu-id="4f19a-149">Returns the value SQL_SS_LENGTH_UNLIMITED for large value type columns.</span></span>|  
|<span data-ttu-id="4f19a-150">SQL_DESC_TYPE</span><span class="sxs-lookup"><span data-stu-id="4f19a-150">SQL_DESC_TYPE</span></span>|<span data-ttu-id="4f19a-151">Retorna SQL_VARCHAR, SQL_WVARCHAR e SQL_VARBINARY para tipos de valor grande.</span><span class="sxs-lookup"><span data-stu-id="4f19a-151">Returns SQL_VARCHAR, SQL_WVARCHAR, and SQL_VARBINARY for large value types.</span></span>|  
|<span data-ttu-id="4f19a-152">SQL_DESC_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-152">SQL_DESC_TYPE_NAME</span></span>|<span data-ttu-id="4f19a-153">Retorna "varchar", "varbinary", "nvarchar" para os tipos de valor grande.</span><span class="sxs-lookup"><span data-stu-id="4f19a-153">Returns "varchar", "varbinary", "nvarchar" for the large value types.</span></span>|  
  
 <span data-ttu-id="4f19a-154">Para todas as versões, os atributos de coluna são informados somente para o primeiro conjunto de resultados quando vários conjuntos são gerados por um lote preparado de instruções SQL.</span><span class="sxs-lookup"><span data-stu-id="4f19a-154">For all versions, column attributes are reported for only the first result set when multiple result sets are generated by a prepared batch of SQL statements.</span></span>  
  
 <span data-ttu-id="4f19a-155">Os atributos de coluna a seguir são extensões expostas pelo driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="4f19a-155">The following column attributes are extensions exposed by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="4f19a-156">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client retorna todos os valores no parâmetro *NumericAttrPtr* .</span><span class="sxs-lookup"><span data-stu-id="4f19a-156">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns all values in the *NumericAttrPtr* parameter.</span></span> <span data-ttu-id="4f19a-157">Os valores são retornados como SDWORD (signed long) com exceção de SQL_CA_SS_COMPUTE_BYLIST, que é um ponteiro para uma matriz de WORD.</span><span class="sxs-lookup"><span data-stu-id="4f19a-157">The values are returned as SDWORD (signed long) except SQL_CA_SS_COMPUTE_BYLIST, which is a pointer to a WORD array.</span></span>  
  
|<span data-ttu-id="4f19a-158">Identificador de campo</span><span class="sxs-lookup"><span data-stu-id="4f19a-158">Field identifier</span></span>|<span data-ttu-id="4f19a-159">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="4f19a-159">Value returned</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="4f19a-160">SQL_CA_SS_COLUMN_HIDDEN\*</span><span class="sxs-lookup"><span data-stu-id="4f19a-160">SQL_CA_SS_COLUMN_HIDDEN\*</span></span>|<span data-ttu-id="4f19a-161">TRUE se a coluna referenciada fizer parte de uma chave primária oculta criada para suportar uma instrução SELECT Transact-SQL que contém FOR BROWSE.</span><span class="sxs-lookup"><span data-stu-id="4f19a-161">TRUE if the column referenced is part of a hidden primary key created to support a Transact-SQL SELECT statement containing FOR BROWSE.</span></span>|  
|<span data-ttu-id="4f19a-162">SQL_CA_SS_COLUMN_ID</span><span class="sxs-lookup"><span data-stu-id="4f19a-162">SQL_CA_SS_COLUMN_ID</span></span>|<span data-ttu-id="4f19a-163">Posição ordinal de uma coluna de resultados de cláusula COMPUTE na instrução SELECT Transact-SQL atual.</span><span class="sxs-lookup"><span data-stu-id="4f19a-163">Ordinal position of a COMPUTE clause result column within the current Transact-SQL SELECT statement.</span></span>|  
|<span data-ttu-id="4f19a-164">SQL_CA_SS_COLUMN_KEY \*</span><span class="sxs-lookup"><span data-stu-id="4f19a-164">SQL_CA_SS_COLUMN_KEY\*</span></span>|<span data-ttu-id="4f19a-165">TRUE se a coluna referenciada fizer parte de uma chave primária para a linha e a instrução SELECT Transact-SQL contiver FOR BROWSE.</span><span class="sxs-lookup"><span data-stu-id="4f19a-165">TRUE if the column referenced is part of a primary key for the row and the Transact-SQL SELECT statement contains FOR BROWSE.</span></span>|  
|<span data-ttu-id="4f19a-166">SQL_CA_SS_COLUMN_OP</span><span class="sxs-lookup"><span data-stu-id="4f19a-166">SQL_CA_SS_COLUMN_OP</span></span>|<span data-ttu-id="4f19a-167">Inteiro que especifica o operador de agregação responsável pelo valor em uma coluna de cláusula COMPUTE.</span><span class="sxs-lookup"><span data-stu-id="4f19a-167">Integer specifying the aggregate operator responsible for the value in a COMPUTE clause column.</span></span> <span data-ttu-id="4f19a-168">As definições dos valores inteiros estão em sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="4f19a-168">Definitions of the integer values are in sqlncli.h.</span></span>|  
|<span data-ttu-id="4f19a-169">SQL_CA_SS_COLUMN_ORDER</span><span class="sxs-lookup"><span data-stu-id="4f19a-169">SQL_CA_SS_COLUMN_ORDER</span></span>|<span data-ttu-id="4f19a-170">Posição ordinal da coluna em uma cláusula ORDER BY da instrução SELECT Transact-SQL ou ODBC.</span><span class="sxs-lookup"><span data-stu-id="4f19a-170">Ordinal position of the column within an ODBC or Transact-SQL SELECT statement's ORDER BY clause.</span></span>|  
|<span data-ttu-id="4f19a-171">SQL_CA_SS_COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="4f19a-171">SQL_CA_SS_COLUMN_SIZE</span></span>|<span data-ttu-id="4f19a-172">Comprimento máximo, em bytes, necessário para associar um valor de dados recuperado da coluna a uma variável SQL_C_BINARY.</span><span class="sxs-lookup"><span data-stu-id="4f19a-172">Maximum length, in bytes, required to bind a data value retrieved from the column to a SQL_C_BINARY variable.</span></span>|  
|<span data-ttu-id="4f19a-173">SQL_CA_SS_COLUMN_SSTYPE</span><span class="sxs-lookup"><span data-stu-id="4f19a-173">SQL_CA_SS_COLUMN_SSTYPE</span></span>|<span data-ttu-id="4f19a-174">Tipo de dados nativo de dados armazenados na coluna do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f19a-174">Native data type of data stored in the SQL Server column.</span></span> <span data-ttu-id="4f19a-175">As definições dos valores de tipo estão em sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="4f19a-175">Definitions of the type values are in sqlncli.h.</span></span>|  
|<span data-ttu-id="4f19a-176">SQL_CA_SS_COLUMN_UTYPE</span><span class="sxs-lookup"><span data-stu-id="4f19a-176">SQL_CA_SS_COLUMN_UTYPE</span></span>|<span data-ttu-id="4f19a-177">Tipo de dados básico do tipo de dados definido pelo usuário da coluna do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f19a-177">Base data type of the SQL Server column's user-defined data type.</span></span> <span data-ttu-id="4f19a-178">As definições dos valores de tipo estão em sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="4f19a-178">Definitions of the type values are in sqlncli.h.</span></span>|  
|<span data-ttu-id="4f19a-179">SQL_CA_SS_COLUMN_VARYLEN</span><span class="sxs-lookup"><span data-stu-id="4f19a-179">SQL_CA_SS_COLUMN_VARYLEN</span></span>|<span data-ttu-id="4f19a-180">TRUE se os dados da coluna puderem variar em comprimento; ou FALSE em caso contrário.</span><span class="sxs-lookup"><span data-stu-id="4f19a-180">TRUE if the column's data can vary in length, FALSE otherwise.</span></span>|  
|<span data-ttu-id="4f19a-181">SQL_CA_SS_COMPUTE_BYLIST</span><span class="sxs-lookup"><span data-stu-id="4f19a-181">SQL_CA_SS_COMPUTE_BYLIST</span></span>|<span data-ttu-id="4f19a-182">Ponteiro para uma matriz de WORD (unsigned short) que especifica as colunas usadas na frase BY de uma cláusula COMPUTE.</span><span class="sxs-lookup"><span data-stu-id="4f19a-182">Pointer to an array of WORD (unsigned short) specifying the columns used in the BY phrase of a COMPUTE clause.</span></span> <span data-ttu-id="4f19a-183">Se a cláusula COMPUTE não especificar uma frase BY, um ponteiro NULL será retornado.</span><span class="sxs-lookup"><span data-stu-id="4f19a-183">If the COMPUTE clause does not specify a BY phrase, a NULL pointer is returned.</span></span><br /><br /> <span data-ttu-id="4f19a-184">O primeiro elemento da matriz contém a contagem de colunas de lista BY.</span><span class="sxs-lookup"><span data-stu-id="4f19a-184">The first element of the array contains the count of BY list columns.</span></span> <span data-ttu-id="4f19a-185">Os elementos adicionais são os ordinais da coluna.</span><span class="sxs-lookup"><span data-stu-id="4f19a-185">Additional elements are the column ordinals.</span></span>|  
|<span data-ttu-id="4f19a-186">SQL_CA_SS_COMPUTE_ID</span><span class="sxs-lookup"><span data-stu-id="4f19a-186">SQL_CA_SS_COMPUTE_ID</span></span>|<span data-ttu-id="4f19a-187">*computeid* de uma linha que é o resultado de uma cláusula COMPUTE na instrução SELECT Transact-SQL atual.</span><span class="sxs-lookup"><span data-stu-id="4f19a-187">*computeid* of a row that is the result of a COMPUTE clause in the current Transact-SQL SELECT statement.</span></span>|  
|<span data-ttu-id="4f19a-188">SQL_CA_SS_NUM_COMPUTES</span><span class="sxs-lookup"><span data-stu-id="4f19a-188">SQL_CA_SS_NUM_COMPUTES</span></span>|<span data-ttu-id="4f19a-189">Número de cláusulas COMPUTE especificado na instrução SELECT Transact-SQL atual.</span><span class="sxs-lookup"><span data-stu-id="4f19a-189">Number of COMPUTE clauses specified in the current Transact-SQL SELECT statement.</span></span>|  
|<span data-ttu-id="4f19a-190">SQL_CA_SS_NUM_ORDERS</span><span class="sxs-lookup"><span data-stu-id="4f19a-190">SQL_CA_SS_NUM_ORDERS</span></span>|<span data-ttu-id="4f19a-191">Número de colunas especificado em uma cláusula ORDER BY da instrução SELECT Transact-SQL ou ODBC.</span><span class="sxs-lookup"><span data-stu-id="4f19a-191">Number of columns specified in an ODBC or Transact-SQL SELECT statement's ORDER BY clause.</span></span>|  
  
 <span data-ttu-id="4f19a-192">\*Disponível se o atributo de instrução SQL_SOPT_SS_HIDDEN_COLUMNS estiver definido como SQL_HC_ON.</span><span class="sxs-lookup"><span data-stu-id="4f19a-192">\*   Available if statement attribute SQL_SOPT_SS_HIDDEN_COLUMNS is set to SQL_HC_ON.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="4f19a-193">introduziu campos de descritor específicos de driver para fornecer informações adicionais para indicar o nome da coleção de esquemas XML, o nome do esquema e o nome do catálogo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4f19a-193">introduced driver-specific descriptor fields to provide additional information to denote the XML schema collection name, the schema name, and the catalog name, respectively.</span></span> <span data-ttu-id="4f19a-194">Essas propriedades não exigem aspas ou um caractere de escape se eles contiverem caracteres não alfanuméricos.</span><span class="sxs-lookup"><span data-stu-id="4f19a-194">These properties do not require quotation marks or an escape character if they contain non-alphanumeric characters.</span></span> <span data-ttu-id="4f19a-195">A tabela a seguir lista esses novos campos de descritor:</span><span class="sxs-lookup"><span data-stu-id="4f19a-195">The following table lists these new descriptor fields:</span></span>  
  
|<span data-ttu-id="4f19a-196">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="4f19a-196">Column name</span></span>|<span data-ttu-id="4f19a-197">Type</span><span class="sxs-lookup"><span data-stu-id="4f19a-197">Type</span></span>|<span data-ttu-id="4f19a-198">Descrição</span><span class="sxs-lookup"><span data-stu-id="4f19a-198">Description</span></span>|  
|-----------------|----------|-----------------|  
|<span data-ttu-id="4f19a-199">SQL_CA_SS_XML_SCHEMACOLLECTION_CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-199">SQL_CA_SS_XML_SCHEMACOLLECTION_CATALOG_NAME</span></span>|<span data-ttu-id="4f19a-200">CharacterAttributePtr</span><span class="sxs-lookup"><span data-stu-id="4f19a-200">CharacterAttributePtr</span></span>|<span data-ttu-id="4f19a-201">O nome do catálogo em que é definido um nome da coleção de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="4f19a-201">The name of the catalog where an XML schema collection name is defined.</span></span> <span data-ttu-id="4f19a-202">Se não for possível localizar o nome do catálogo, essa variável conterá uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="4f19a-202">If the catalog name cannot be found, then this variable contains an empty string.</span></span><br /><br /> <span data-ttu-id="4f19a-203">Essas informações são retornadas do campo de registro SQL_DESC_SS_XML_SCHEMACOLLECTION_CATALOG_NAME do IRD, que é um campo de leitura-gravação.</span><span class="sxs-lookup"><span data-stu-id="4f19a-203">This information is returned from the SQL_DESC_SS_XML_SCHEMACOLLECTION_CATALOG_NAME record field of the IRD, which is a read-write field.</span></span>|  
|<span data-ttu-id="4f19a-204">SQL_CA_SS_XML_SCHEMACOLLECTION_SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-204">SQL_CA_SS_XML_SCHEMACOLLECTION_SCHEMA_NAM E</span></span>|<span data-ttu-id="4f19a-205">CharacterAttributePtr</span><span class="sxs-lookup"><span data-stu-id="4f19a-205">CharacterAttributePtr</span></span>|<span data-ttu-id="4f19a-206">O nome do esquema no qual é definido um nome da coleção de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="4f19a-206">The name of the schema where an XML schema collection name is defined.</span></span> <span data-ttu-id="4f19a-207">Se não for possível localizar o nome do esquema, essa variável conterá uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="4f19a-207">If the schema name cannot be found, then this variable contains an empty string.</span></span><br /><br /> <span data-ttu-id="4f19a-208">Essas informações são retornadas do campo de registro SQL_DESC_SS_XML_SCHEMACOLLECTION_SCHEMA_NAME do IRD, que é um campo de leitura-gravação.</span><span class="sxs-lookup"><span data-stu-id="4f19a-208">This information is returned from the SQL_DESC_SS_XML_SCHEMACOLLECTION_SCHEMA_NAME record field of the IRD, which is a read-write field.</span></span>|  
|<span data-ttu-id="4f19a-209">SQL_CA_SS_XML_SCHEMACOLLECTION_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-209">SQL_CA_SS_XML_SCHEMACOLLECTION_NAME</span></span>|<span data-ttu-id="4f19a-210">CharacterAttributePtr</span><span class="sxs-lookup"><span data-stu-id="4f19a-210">CharacterAttributePtr</span></span>|<span data-ttu-id="4f19a-211">O nome de uma coleção de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="4f19a-211">The name of an XML schema collection.</span></span> <span data-ttu-id="4f19a-212">Se não for possível localizar o nome, essa variável conterá uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="4f19a-212">If the name cannot be found, then this variable contains an empty string.</span></span><br /><br /> <span data-ttu-id="4f19a-213">Essas informações são retornadas do campo de registro SQL_DESC_SS_XML_SCHEMACOLLECTION_NAME do IRD, que é um campo de leitura-gravação.</span><span class="sxs-lookup"><span data-stu-id="4f19a-213">This information is returned from the SQL_DESC_SS_XML_SCHEMACOLLECTION_NAME record field of the IRD, which is a read-write field.</span></span>|  
  
 <span data-ttu-id="4f19a-214">Além disso, o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] introduziu campos de descritor específicos de driver para fornecer informações adicionais para uma coluna de UDT (tipo definido pelo usuário) de um conjunto de resultados ou um parâmetro de UDT de um procedimento armazenado ou consulta parametrizada.</span><span class="sxs-lookup"><span data-stu-id="4f19a-214">Also, [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] introduced new driver-specific descriptor fields to provide additional information for either a user-defined type (UDT) column of a result set or a UDT parameter of a stored procedure or parameterized query.</span></span> <span data-ttu-id="4f19a-215">Essas propriedades não exigem aspas ou um caractere de escape se eles contiverem caracteres não alfanuméricos.</span><span class="sxs-lookup"><span data-stu-id="4f19a-215">These properties do not require quotation marks or an escape character if they contain non-alphanumeric characters.</span></span> <span data-ttu-id="4f19a-216">A tabela a seguir lista esses novos campos de descritor:</span><span class="sxs-lookup"><span data-stu-id="4f19a-216">The following table lists these new descriptor fields:</span></span>  
  
|<span data-ttu-id="4f19a-217">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="4f19a-217">Column Name</span></span>|<span data-ttu-id="4f19a-218">Type</span><span class="sxs-lookup"><span data-stu-id="4f19a-218">Type</span></span>|<span data-ttu-id="4f19a-219">Descrição</span><span class="sxs-lookup"><span data-stu-id="4f19a-219">Description</span></span>|  
|-----------------|----------|-----------------|  
|<span data-ttu-id="4f19a-220">SQL_CA_SS_UDT_CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-220">SQL_CA_SS_UDT_CATALOG_NAME</span></span>|<span data-ttu-id="4f19a-221">CharacterAttributePtr</span><span class="sxs-lookup"><span data-stu-id="4f19a-221">CharacterAttributePtr</span></span>|<span data-ttu-id="4f19a-222">O nome do catálogo que contém o UDT.</span><span class="sxs-lookup"><span data-stu-id="4f19a-222">The name of the catalog containing the UDT.</span></span>|  
|<span data-ttu-id="4f19a-223">SQL_CA_SS_UDT_SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-223">SQL_CA_SS_UDT_SCHEMA_NAME</span></span>|<span data-ttu-id="4f19a-224">CharacterAttributePtr</span><span class="sxs-lookup"><span data-stu-id="4f19a-224">CharacterAttributePtr</span></span>|<span data-ttu-id="4f19a-225">O nome do esquema que contém o UDT.</span><span class="sxs-lookup"><span data-stu-id="4f19a-225">The name of the schema containing the UDT.</span></span>|  
|<span data-ttu-id="4f19a-226">SQL_CA_SS_UDT_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-226">SQL_CA_SS_UDT_TYPE_NAME</span></span>|<span data-ttu-id="4f19a-227">CharacterAttributePtr</span><span class="sxs-lookup"><span data-stu-id="4f19a-227">CharacterAttributePtr</span></span>|<span data-ttu-id="4f19a-228">O nome do UDT.</span><span class="sxs-lookup"><span data-stu-id="4f19a-228">The name of the UDT.</span></span>|  
|<span data-ttu-id="4f19a-229">SQL_CA_SS_UDT_ASSEMBLY_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f19a-229">SQL_CA_SS_UDT_ASSEMBLY_TYPE_NAME</span></span>|<span data-ttu-id="4f19a-230">CharacterAttributePtr</span><span class="sxs-lookup"><span data-stu-id="4f19a-230">CharacterAttributePtr</span></span>|<span data-ttu-id="4f19a-231">O nome qualificado do assembly do UDT.</span><span class="sxs-lookup"><span data-stu-id="4f19a-231">The assembly qualified name of the UDT.</span></span>|  
  
 <span data-ttu-id="4f19a-232">O identificador do campo de descritor SQL_DESC_TYPE_NAME existente é usado para indicar o nome do UDT.</span><span class="sxs-lookup"><span data-stu-id="4f19a-232">The existing descriptor field identifier SQL_DESC_TYPE_NAME is used to indicate the name of the UDT.</span></span> <span data-ttu-id="4f19a-233">O campo SQL_DESC_TYPE para uma coluna de tipo UDT é SQL_SS_UDT.</span><span class="sxs-lookup"><span data-stu-id="4f19a-233">The SQL_DESC_TYPE field for a UDT type column is SQL_SS_UDT.</span></span>  
  
## <a name="sqlcolattribute-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="4f19a-234">Suporte do SQLColAttribute a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="4f19a-234">SQLColAttribute Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="4f19a-235">Para obter os valores retornados para tipos de data/hora, consulte a seção sobre informações retornadas em campos IRD em [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="4f19a-235">For the values returned for date/time types, see the "Information Returned in IRD Fields" section in [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="4f19a-236">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="4f19a-236">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlcolattribute-support-for-large-clr-udts"></a><span data-ttu-id="4f19a-237">Suporte do SQLColAttribute a UDTs CLR grandes</span><span class="sxs-lookup"><span data-stu-id="4f19a-237">SQLColAttribute Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="4f19a-238">`SQLColAttribute` dá suporte a UDTs grandes do CLR.</span><span class="sxs-lookup"><span data-stu-id="4f19a-238">`SQLColAttribute` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="4f19a-239">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="4f19a-239">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlcolattribute-support-for-sparse-columns"></a><span data-ttu-id="4f19a-240">Suporte do SQLColAttribute a colunas esparsas</span><span class="sxs-lookup"><span data-stu-id="4f19a-240">SQLColAttribute Support for Sparse Columns</span></span>  
 <span data-ttu-id="4f19a-241">SQLColAttribute consulta o novo campo IRD (descritor de linha de implementação), SQL_CA_SS_IS_COLUMN_SET, para determinar se uma coluna é uma `column_set` coluna.</span><span class="sxs-lookup"><span data-stu-id="4f19a-241">SQLColAttribute queries the new implementation row descriptor (IRD) field, SQL_CA_SS_IS_COLUMN_SET, to determine if a column is a `column_set` column.</span></span>  
  
 <span data-ttu-id="4f19a-242">Para obter mais informações, consulte [suporte a colunas esparsas &#40;&#41;ODBC ](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="4f19a-242">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f19a-243">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f19a-243">See Also</span></span>  
 <span data-ttu-id="4f19a-244">[Função SQLColAttribute](https://go.microsoft.com/fwlink/?LinkId=59334) </span><span class="sxs-lookup"><span data-stu-id="4f19a-244">[SQLColAttribute Function](https://go.microsoft.com/fwlink/?LinkId=59334) </span></span>  
 <span data-ttu-id="4f19a-245">[Detalhes de implementação da API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="4f19a-245">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 [<span data-ttu-id="4f19a-246">SQLSetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="4f19a-246">SQLSetStmtAttr</span></span>](sqlsetstmtattr.md)  
  
  