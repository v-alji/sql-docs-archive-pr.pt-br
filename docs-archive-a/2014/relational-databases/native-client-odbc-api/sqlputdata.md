---
title: SQLPutData | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPutData function
ms.assetid: d39aaa5b-7fbc-4315-a7f2-5a7787e04f25
author: rothja
ms.author: jroth
ms.openlocfilehash: 31da9c21f9e4323a492a25629a979c66a4f7d365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583005"
---
# <a name="sqlputdata"></a><span data-ttu-id="f565e-102">SQLPutData</span><span class="sxs-lookup"><span data-stu-id="f565e-102">SQLPutData</span></span>
  <span data-ttu-id="f565e-103">As restrições a seguir se aplicam ao usar o SQLPutData para enviar mais de 65.535 bytes de dados (para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a versão 4.21 a) ou 400 KB de dados (para SQL Server versão 6,0 e posterior) para uma coluna SQL_LONGVARCHAR ( `text` ), SQL_WLONGVARCHAR ( `ntext` ) ou SQL_LONGVARBINARY ( `image` ):</span><span class="sxs-lookup"><span data-stu-id="f565e-103">The following restrictions apply when using SQLPutData to send more than 65,535 bytes of data (for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 4.21a) or 400 KB of data (for SQL Server version 6.0 and later) for a SQL_LONGVARCHAR (`text`), SQL_WLONGVARCHAR (`ntext`) or SQL_LONGVARBINARY (`image`) column:</span></span>  
  
-   <span data-ttu-id="f565e-104">O parâmetro referenciado pode ser o *insert_value* em uma instrução INSERT.</span><span class="sxs-lookup"><span data-stu-id="f565e-104">The referenced parameter can be the *insert_value* in an INSERT statement.</span></span>  
  
-   <span data-ttu-id="f565e-105">O parâmetro referenciado pode ser uma *expressão* na cláusula SET de uma instrução UPDATE.</span><span class="sxs-lookup"><span data-stu-id="f565e-105">The referenced parameter can be an *expression* in the SET clause of an UPDATE statement.</span></span>  
  
 <span data-ttu-id="f565e-106">Cancelar uma sequência de chamadas SQLPutData que fornecem dados em blocos para um servidor em execução [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] causa uma atualização parcial do valor da coluna ao usar a versão 6,5 ou anterior.</span><span class="sxs-lookup"><span data-stu-id="f565e-106">Canceling a sequence of SQLPutData calls that provide data in blocks to a server running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] causes a partial update of the column's value when using version 6.5 or earlier.</span></span> <span data-ttu-id="f565e-107">A `text` `ntext` coluna,, ou `image` que foi referenciada quando SQLCancel foi chamado é definida como um valor de espaço reservado intermediário.</span><span class="sxs-lookup"><span data-stu-id="f565e-107">The `text`, `ntext`, or `image` column that was referenced when SQLCancel was called is set to an intermediate placeholder value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f565e-108">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client não dá suporte à conexão ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versão 6.5 e anteriores.</span><span class="sxs-lookup"><span data-stu-id="f565e-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 6.5 and earlier.</span></span>  
  
## <a name="diagnostics"></a><span data-ttu-id="f565e-109">Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="f565e-109">Diagnostics</span></span>  
 <span data-ttu-id="f565e-110">Há um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQLSTATE específico de cliente nativo para SQLPutData:</span><span class="sxs-lookup"><span data-stu-id="f565e-110">There is one [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client specific SQLSTATE for SQLPutData:</span></span>  
  
|<span data-ttu-id="f565e-111">SQLSTATE</span><span class="sxs-lookup"><span data-stu-id="f565e-111">SQLSTATE</span></span>|<span data-ttu-id="f565e-112">Erro</span><span class="sxs-lookup"><span data-stu-id="f565e-112">Error</span></span>|<span data-ttu-id="f565e-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="f565e-113">Description</span></span>|  
|--------------|-----------|-----------------|  
|<span data-ttu-id="f565e-114">22026</span><span class="sxs-lookup"><span data-stu-id="f565e-114">22026</span></span>|<span data-ttu-id="f565e-115">Incompatibilidade de comprimento de dados String</span><span class="sxs-lookup"><span data-stu-id="f565e-115">String data, length mismatch</span></span>|<span data-ttu-id="f565e-116">Se o comprimento dos dados em bytes a ser enviado tiver sido especificado por um aplicativo, por exemplo, com SQL_LEN_DATA_AT_EXEC (*n*) em que *n* é maior que 0, o número total de bytes fornecidos pelo aplicativo via SQLPutData deve corresponder ao comprimento especificado.</span><span class="sxs-lookup"><span data-stu-id="f565e-116">If the length of data in bytes to be sent has been specified by an application, for example, with SQL_LEN_DATA_AT_EXEC(*n*) where *n* is greater than 0, the total number of bytes given by the application via SQLPutData must match the specified length.</span></span>|  
  
## <a name="sqlputdata-and-table-valued-parameters"></a><span data-ttu-id="f565e-117">SQLPutData e parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="f565e-117">SQLPutData and Table-Valued Parameters</span></span>  
 <span data-ttu-id="f565e-118">SQLPutData é usado por um aplicativo ao usar a associação de linha variável com parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="f565e-118">SQLPutData is used by an application when using variable row binding with table-valued parameters.</span></span> <span data-ttu-id="f565e-119">O parâmetro *StrLen_or_Ind* indica que ele está pronto para o driver coletar dados para a próxima linha ou linhas de dados de parâmetro com valor de tabela, ou que não há mais linhas disponíveis:</span><span class="sxs-lookup"><span data-stu-id="f565e-119">The *StrLen_Or_Ind* parameter indicates that it is ready for the driver to collect data for the next row or rows of table-valued parameter data, or that no more rows are available:</span></span>  
  
-   <span data-ttu-id="f565e-120">Um valor maior que 0 indica que o próximo conjunto de valores de linha está disponível.</span><span class="sxs-lookup"><span data-stu-id="f565e-120">A value greater than 0 indicates that the next set of row values is available.</span></span>  
  
-   <span data-ttu-id="f565e-121">Um valor igual a 0 indica que não há mais linhas a serem enviadas.</span><span class="sxs-lookup"><span data-stu-id="f565e-121">A value of 0 indicates that there are no more rows to be sent.</span></span>  
  
-   <span data-ttu-id="f565e-122">Qualquer valor menor que 0 indica um erro e resulta na geração de um registro de diagnóstico com SQLState igual a HY090 e na mensagem "Comprimento de buffer ou de cadeia de caracteres inválido".</span><span class="sxs-lookup"><span data-stu-id="f565e-122">Any value less than 0 is an error and results in a diagnostic record being logged with SQLState HY090 and the messaage "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="f565e-123">O parâmetro *DataPtr* é ignorado, mas deve ser definido como um valor não nulo.</span><span class="sxs-lookup"><span data-stu-id="f565e-123">The *DataPtr* parameter is ignored, but must be set to a non-NULL value.</span></span> <span data-ttu-id="f565e-124">Para obter mais informações, consulte a seção sobre associação de linha TVP variável em [associação e transferência de dados de parâmetros com valor de tabela e valores de coluna](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span><span class="sxs-lookup"><span data-stu-id="f565e-124">For more information, see the section on Variable TVP row binding in [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="f565e-125">Se *StrLen_or_Ind* tiver qualquer valor diferente de SQL_DEFAULT_PARAM ou um número entre 0 e o SQL_PARAMSET_SIZE (ou seja, o parâmetro *ColumnSize* de SQLBindParameter), será um erro.</span><span class="sxs-lookup"><span data-stu-id="f565e-125">If *StrLen_Or_Ind* has any value other than SQL_DEFAULT_PARAM or a number between 0 and the SQL_PARAMSET_SIZE (that is, the *ColumnSize* parameter of SQLBindParameter), it is an error.</span></span> <span data-ttu-id="f565e-126">Esse erro faz SQLPutData retornar SQL_ERROR: SQLSTATE=HY090, "Comprimento de buffer ou de cadeia de caracteres inválido".</span><span class="sxs-lookup"><span data-stu-id="f565e-126">This error causes SQLPutData to return SQL_ERROR: SQLSTATE=HY090, "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="f565e-127">Para obter mais informações sobre parâmetros com valor de tabela, consulte [parâmetros com valor de tabela &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="f565e-127">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="f565e-128">Suporte de SQLPutData a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="f565e-128">SQLPutData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="f565e-129">Os valores de parâmetro dos tipos de data/hora são convertidos conforme descrito em [conversões de C para SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f565e-129">Parameter values of date/time types are converted as described in [Conversions from C to SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md).</span></span>  
  
 <span data-ttu-id="f565e-130">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="f565e-130">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-large-clr-udts"></a><span data-ttu-id="f565e-131">Suporte de SQLPutData a UDTs grandes do CLR</span><span class="sxs-lookup"><span data-stu-id="f565e-131">SQLPutData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="f565e-132">`SQLPutData` dá suporte a UDTs grandes do CLR.</span><span class="sxs-lookup"><span data-stu-id="f565e-132">`SQLPutData` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="f565e-133">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="f565e-133">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f565e-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f565e-134">See Also</span></span>  
 <span data-ttu-id="f565e-135">[Função SQLPutData](https://go.microsoft.com/fwlink/?LinkId=59365) </span><span class="sxs-lookup"><span data-stu-id="f565e-135">[SQLPutData Function](https://go.microsoft.com/fwlink/?LinkId=59365) </span></span>  
 [<span data-ttu-id="f565e-136">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="f565e-136">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
