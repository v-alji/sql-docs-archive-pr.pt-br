---
title: Processando resultados (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC], about result sets
- SQLRowCount function
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- COMPUTE clause
- result sets [ODBC]
- COMPUTE BY clause
ms.assetid: 61a8db19-6571-47dd-84e8-fcc97cb60b45
author: rothja
ms.author: jroth
ms.openlocfilehash: 72c0d15231b07a23f10a03b0fca270d1d014891c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685631"
---
# <a name="processing-results-odbc"></a><span data-ttu-id="0b54e-102">Processando resultados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="0b54e-102">Processing Results (ODBC)</span></span>
  <span data-ttu-id="0b54e-103">Depois que um aplicativo envia uma instrução SQL, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retorna qualquer dado resultante como um ou mais conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="0b54e-103">After an application submits a SQL statement, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns any resulting data as one or more result sets.</span></span> <span data-ttu-id="0b54e-104">Um conjunto de resultados é um conjunto de linhas e colunas que correspondem aos critérios da consulta.</span><span class="sxs-lookup"><span data-stu-id="0b54e-104">A result set is a set of rows and columns that match the criteria of the query.</span></span> <span data-ttu-id="0b54e-105">As instruções SELECT, funções de catálogo e alguns procedimentos armazenados geram um conjunto de resultados disponibilizado para um aplicativo no formato tabular.</span><span class="sxs-lookup"><span data-stu-id="0b54e-105">SELECT statements, catalog functions, and some stored procedures produce a result set made available to an application in tabular form.</span></span> <span data-ttu-id="0b54e-106">Se a instrução SQL executada for um procedimento armazenado, um lote contendo vários comandos ou uma instrução SELECT contendo palavras-chave, haverá vários conjuntos de resultados a serem processados.</span><span class="sxs-lookup"><span data-stu-id="0b54e-106">If the executed SQL statement is a stored procedure, a batch containing multiple commands, or a SELECT statement containing keywords, there will be multiple result sets to process.</span></span>  
  
 <span data-ttu-id="0b54e-107">As funções de catálogo ODBC também podem recuperar dados.</span><span class="sxs-lookup"><span data-stu-id="0b54e-107">ODBC catalog functions also can retrieve data.</span></span> <span data-ttu-id="0b54e-108">Por exemplo, [SQLColumns](../native-client-odbc-api/sqlcolumns.md) recupera dados sobre colunas na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="0b54e-108">For example, [SQLColumns](../native-client-odbc-api/sqlcolumns.md) retrieves data about columns in the data source.</span></span> <span data-ttu-id="0b54e-109">Esses conjuntos de resultados podem conter zero ou mais linhas.</span><span class="sxs-lookup"><span data-stu-id="0b54e-109">These result sets can contain zero or more rows.</span></span>  
  
 <span data-ttu-id="0b54e-110">Outras instruções SQL, como GRANT ou REVOKE, não retornam conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="0b54e-110">Other SQL statements, such as GRANT or REVOKE, do not return result sets.</span></span> <span data-ttu-id="0b54e-111">Para essas instruções, o código de retorno de **SQLExecute** ou **SQLExecDirect** geralmente é a única indicação de que a instrução foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="0b54e-111">For these statements, the return code from **SQLExecute** or **SQLExecDirect** is usually the only indication the statement was successful.</span></span>  
  
 <span data-ttu-id="0b54e-112">Cada instrução INSERT, UPDATE e DELETE retorna um conjunto de resultados que contém apenas o número de linhas afetado pela modificação.</span><span class="sxs-lookup"><span data-stu-id="0b54e-112">Each INSERT, UPDATE, and DELETE statement returns a result set containing only the number of rows affected by the modification.</span></span> <span data-ttu-id="0b54e-113">Essa contagem é disponibilizada quando o aplicativo chama [SQLRowCount](../native-client-odbc-api/sqlrowcount.md).</span><span class="sxs-lookup"><span data-stu-id="0b54e-113">This count is made available when application calls [SQLRowCount](../native-client-odbc-api/sqlrowcount.md).</span></span> <span data-ttu-id="0b54e-114">ODBC 3. os aplicativos *x* devem chamar **SQLRowCount** para recuperar o conjunto de resultados ou [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) para cancelá-lo.</span><span class="sxs-lookup"><span data-stu-id="0b54e-114">ODBC 3.*x* applications must either call **SQLRowCount** to retrieve the result set or [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) to cancel it.</span></span> <span data-ttu-id="0b54e-115">Quando um aplicativo executa um lote ou procedimento armazenado que contém várias instruções INSERT, UPDATE ou DELETE, o conjunto de resultados de cada instrução de modificação deve ser processado usando **SQLRowCount** ou cancelado usando **SQLMoreResults**.</span><span class="sxs-lookup"><span data-stu-id="0b54e-115">When an application executes a batch or stored procedure containing multiple INSERT, UPDATE, or DELETE statements, the result set from each modification statement must be processed using **SQLRowCount** or cancelled using **SQLMoreResults**.</span></span> <span data-ttu-id="0b54e-116">Essas contagens podem ser canceladas incluindo uma instrução SET NOCOUNT ON no lote ou no procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="0b54e-116">These counts can be cancelled by including a SET NOCOUNT ON statement in the batch or stored procedure.</span></span>  
  
 <span data-ttu-id="0b54e-117">O Transact-SQL inclui a instrução SET NOCOUNT.</span><span class="sxs-lookup"><span data-stu-id="0b54e-117">Transact-SQL includes the SET NOCOUNT statement.</span></span> <span data-ttu-id="0b54e-118">Quando a opção NOCOUNT é definida em, SQL Server não retorna as contagens das linhas afetadas por uma instrução e **SQLRowCount** retorna 0.</span><span class="sxs-lookup"><span data-stu-id="0b54e-118">When the NOCOUNT option is set on, SQL Server does not return the counts of the rows affected by a statement and **SQLRowCount** returns 0.</span></span> <span data-ttu-id="0b54e-119">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versão do driver ODBC do Native Client introduz uma opção [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) específica do driver, SQL_SOPT_SS_NOCOUNT_STATUS, para relatar se a opção NOCOUNT está ativada ou desativada.</span><span class="sxs-lookup"><span data-stu-id="0b54e-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver version introduces a driver-specific [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) option, SQL_SOPT_SS_NOCOUNT_STATUS, to report on whether the NOCOUNT option is on or off.</span></span> <span data-ttu-id="0b54e-120">Sempre que **SQLRowCount** retorna 0, o aplicativo deve testar SQL_SOPT_SS_NOCOUNT_STATUS.</span><span class="sxs-lookup"><span data-stu-id="0b54e-120">Anytime **SQLRowCount** returns 0, the application should test SQL_SOPT_SS_NOCOUNT_STATUS.</span></span> <span data-ttu-id="0b54e-121">Se SQL_NC_ON for retornado, o valor de 0 de **SQLRowCount** indicará apenas que SQL Server não retornou uma contagem de linhas.</span><span class="sxs-lookup"><span data-stu-id="0b54e-121">If SQL_NC_ON is returned, the value of 0 from **SQLRowCount** only indicates that SQL Server has not returned a row count.</span></span> <span data-ttu-id="0b54e-122">Se SQL_NC_OFF for retornado, significa que NOCOUNT está desativado e o valor de 0 de **SQLRowCount** indica que a instrução não afetou nenhuma linha.</span><span class="sxs-lookup"><span data-stu-id="0b54e-122">If SQL_NC_OFF is returned, it means that NOCOUNT is off and the value of 0 from **SQLRowCount** indicates that the statement did not affect any rows.</span></span> <span data-ttu-id="0b54e-123">Os aplicativos não devem exibir o valor de **SQLRowCount** quando SQL_SOPT_SS_NOCOUNT_STATUS for SQL_NC_OFF.</span><span class="sxs-lookup"><span data-stu-id="0b54e-123">Applications should not display the value of **SQLRowCount** when SQL_SOPT_SS_NOCOUNT_STATUS is SQL_NC_OFF.</span></span> <span data-ttu-id="0b54e-124">Lotes ou procedimentos armazenados grandes podem conter várias instruções SET NOCOUNT, de forma que os programadores não podem supor que SQL_SOPT_SS_NOCOUNT_STATUS permaneça constante.</span><span class="sxs-lookup"><span data-stu-id="0b54e-124">Large batches or stored procedures may contain multiple SET NOCOUNT statements so programmers cannot assume SQL_SOPT_SS_NOCOUNT_STATUS remains constant.</span></span> <span data-ttu-id="0b54e-125">A opção deve ser testada cada vez que **SQLRowCount** retornar 0.</span><span class="sxs-lookup"><span data-stu-id="0b54e-125">The option should be tested each time **SQLRowCount** returns 0.</span></span>  
  
 <span data-ttu-id="0b54e-126">Várias outras instruções Transact-SQL retornam seus dados em mensagens e não em conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="0b54e-126">Several other Transact-SQL statements return their data in messages rather than result sets.</span></span> <span data-ttu-id="0b54e-127">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client recebe essas mensagens, ele retorna SQL_SUCCESS_WITH_INFO para permitir que o aplicativo saiba que as mensagens informativas estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0b54e-127">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver receives these messages, it returns SQL_SUCCESS_WITH_INFO to let the application know that informational messages are available.</span></span> <span data-ttu-id="0b54e-128">O aplicativo pode então chamar **SQLGetDiagRec** para recuperar essas mensagens.</span><span class="sxs-lookup"><span data-stu-id="0b54e-128">The application can then call **SQLGetDiagRec** to retrieve these messages.</span></span> <span data-ttu-id="0b54e-129">As instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] que funcionam deste modo são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="0b54e-129">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that work this way are:</span></span>  
  
-   <span data-ttu-id="0b54e-130">DBCC</span><span class="sxs-lookup"><span data-stu-id="0b54e-130">DBCC</span></span>  
  
-   <span data-ttu-id="0b54e-131">SET SHOWPLAN (disponível com versões anteriores do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0b54e-131">SET SHOWPLAN (available with earlier versions of SQL Server)</span></span>  
  
-   <span data-ttu-id="0b54e-132">SET STATISTICS</span><span class="sxs-lookup"><span data-stu-id="0b54e-132">SET STATISTICS</span></span>  
  
-   <span data-ttu-id="0b54e-133">PRINT</span><span class="sxs-lookup"><span data-stu-id="0b54e-133">PRINT</span></span>  
  
-   <span data-ttu-id="0b54e-134">RAISERROR</span><span class="sxs-lookup"><span data-stu-id="0b54e-134">RAISERROR</span></span>  
  
 <span data-ttu-id="0b54e-135">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client retorna SQL_ERROR em um RAISERROR com uma severidade de 11 ou superior.</span><span class="sxs-lookup"><span data-stu-id="0b54e-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns SQL_ERROR on a RAISERROR with a severity of 11 or higher.</span></span> <span data-ttu-id="0b54e-136">Se a severidade do RAISERROR for 19 ou superior, a conexão também será descartada.</span><span class="sxs-lookup"><span data-stu-id="0b54e-136">If the severity of the RAISERROR is 19 or higher, the connection is also dropped.</span></span>  
  
 <span data-ttu-id="0b54e-137">Para processar os conjuntos de resultados a partir de uma instrução SQL, o aplicativo:</span><span class="sxs-lookup"><span data-stu-id="0b54e-137">To process the result sets from an SQL statement, the application:</span></span>  
  
-   <span data-ttu-id="0b54e-138">Determina as características do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0b54e-138">Determines the characteristics of the result set.</span></span>  
  
-   <span data-ttu-id="0b54e-139">Associa as colunas às variáveis do programa.</span><span class="sxs-lookup"><span data-stu-id="0b54e-139">Binds the columns to program variables.</span></span>  
  
-   <span data-ttu-id="0b54e-140">Recupera um único valor, uma linha inteira de valores ou várias linhas de valores.</span><span class="sxs-lookup"><span data-stu-id="0b54e-140">Retrieves a single value, an entire row of values, or multiple rows of values.</span></span>  
  
-   <span data-ttu-id="0b54e-141">Testa se há mais conjuntos de resultados e, se houver, faz loops de volta para determinar as características do novo conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0b54e-141">Tests to see if there are more result sets, and if so, loops back to determining the characteristics of the new result set.</span></span>  
  
 <span data-ttu-id="0b54e-142">O processo de recuperação de linhas da fonte de dados e de seu retorno ao aplicativo é chamado de busca.</span><span class="sxs-lookup"><span data-stu-id="0b54e-142">The process of retrieving rows from the data source and returning them to the application is called fetching.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b54e-143">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0b54e-143">In This Section</span></span>  
  
-   [<span data-ttu-id="0b54e-144">Determinando as características de um conjunto de resultados &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="0b54e-144">Determining the Characteristics of a Result Set &#40;ODBC&#41;</span></span>](determining-the-characteristics-of-a-result-set-odbc.md)  
  
-   [<span data-ttu-id="0b54e-145">Atribuindo armazenamento</span><span class="sxs-lookup"><span data-stu-id="0b54e-145">Assigning Storage</span></span>](assigning-storage.md)  
  
-   [<span data-ttu-id="0b54e-146">Buscando dados de resultados</span><span class="sxs-lookup"><span data-stu-id="0b54e-146">Fetching Result Data</span></span>](fetching-result-data.md)  
  
-   [<span data-ttu-id="0b54e-147">Mapeando tipos de dados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="0b54e-147">Mapping Data Types &#40;ODBC&#41;</span></span>](mapping-data-types-odbc.md)  
  
-   [<span data-ttu-id="0b54e-148">Uso do tipo de dados</span><span class="sxs-lookup"><span data-stu-id="0b54e-148">Data Type Usage</span></span>](data-type-usage.md)  
  
-   [<span data-ttu-id="0b54e-149">Tradução automática de dados de caracteres</span><span class="sxs-lookup"><span data-stu-id="0b54e-149">Autotranslation of Character Data</span></span>](autotranslation-of-character-data.md)  
  
## <a name="see-also"></a><span data-ttu-id="0b54e-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0b54e-150">See Also</span></span>  
 <span data-ttu-id="0b54e-151">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="0b54e-151">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="0b54e-152">Tópicos de instruções sobre o processamento de resultados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="0b54e-152">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
  
