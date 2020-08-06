---
title: Parâmetros com valor de tabela (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC)
- ODBC, table-valued parameters
ms.assetid: ef06cd13-18e2-4c65-8ede-c3955d820e54
author: rothja
ms.author: jroth
ms.openlocfilehash: fedfd63f7cbafd68d39aeb62dd29c046df8ab100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569398"
---
# <a name="table-valued-parameters-odbc"></a><span data-ttu-id="3eca5-102">Parâmetros com valor de tabela (ODBC)</span><span class="sxs-lookup"><span data-stu-id="3eca5-102">Table-Valued Parameters (ODBC)</span></span>
  <span data-ttu-id="3eca5-103">O suporte de ODBC para parâmetros com valor de tabela permite que o aplicativo cliente envie dados com parâmetros para o servidor de forma mais eficiente, enviando várias linhas ao servidor com uma chamada.</span><span class="sxs-lookup"><span data-stu-id="3eca5-103">ODBC support for table-valued parameters lets a client application send parameterized data to the server more efficiently, by sending multiple rows to the server with one call.</span></span>  
  
 <span data-ttu-id="3eca5-104">Para obter informações sobre parâmetros com valor de tabela no servidor, consulte [usar parâmetros com valor de tabela &#40;Mecanismo de Banco de Dados&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="3eca5-104">For information about table-valued parameters on the server, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
 <span data-ttu-id="3eca5-105">No ODBC, há duas formas de enviar parâmetros com valor de tabela para o servidor:</span><span class="sxs-lookup"><span data-stu-id="3eca5-105">In ODBC, there are two ways that you can send table-valued parameters to the server:</span></span>  
  
-   <span data-ttu-id="3eca5-106">Todos os dados de parâmetro com valor de tabela podem estar na memória no momento em que SQLExecDirect ou SQLExecute é chamado.</span><span class="sxs-lookup"><span data-stu-id="3eca5-106">All the table-valued parameter data can be in memory at the time SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="3eca5-107">Esses dados são armazenados em matrizes, se houver várias linhas com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="3eca5-107">This data is stored in arrays if there are multiple rows in the table-value.</span></span>  
  
-   <span data-ttu-id="3eca5-108">Um aplicativo pode especificar dados em execução para um parâmetro com valor de tabela quando SQLExecDirect ou SQLExecute é chamado.</span><span class="sxs-lookup"><span data-stu-id="3eca5-108">An application can specify data-at-execution for a table-valued parameter when SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="3eca5-109">Nesse caso, linhas de dados com valor de tabela podem ser fornecidas em lotes ou a qualquer momento, a fim de reduzir os requisitos de memória.</span><span class="sxs-lookup"><span data-stu-id="3eca5-109">In this case, rows of data for the table-value can be provided in batches, or one at a time to reduce memory requirements.</span></span>  
  
 <span data-ttu-id="3eca5-110">A primeira opção permite que os procedimentos armazenados encapsulem mais lógica corporativa.</span><span class="sxs-lookup"><span data-stu-id="3eca5-110">The first option enables stored procedures to encapsulate more business logic.</span></span> <span data-ttu-id="3eca5-111">Por exemplo, um único procedimento armazenado pode encapsular toda uma transação de entrada de pedido quando o item solicitado for transmitido como um parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="3eca5-111">For example, a single stored procedure could encapsulate a whole order entry transaction when the order items are passed as a table-valued parameter.</span></span> <span data-ttu-id="3eca5-112">Essa opção é muito eficiente, porque é necessária apenas uma viagem de ida e volta ao servidor.</span><span class="sxs-lookup"><span data-stu-id="3eca5-112">This option is very efficient, because only a single round trip to the server is required.</span></span> <span data-ttu-id="3eca5-113">Como alternativa, você pode usar procedimentos diferentes para lidar com o cabeçalho do pedido e itens do pedido separadamente, o que exigiria mais código e um contrato mais complexo entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="3eca5-113">Alternatively, you could use different procedures to handle the order header and order items separately, which would require more code and a more complex contract between the client and server.</span></span>  
  
 <span data-ttu-id="3eca5-114">O segundo método fornece um mecanismo eficiente para operações em massa com grandes quantidades de dados.</span><span class="sxs-lookup"><span data-stu-id="3eca5-114">The second method provides an efficient mechanism for bulk operations with very large amounts of data.</span></span> <span data-ttu-id="3eca5-115">Isso permite que um aplicativo transmita linhas de dados para o servidor sem precisar armazenar todas elas em buffer na memória antes.</span><span class="sxs-lookup"><span data-stu-id="3eca5-115">This enables an application to stream rows of data to the server without having to buffer them all in memory first.</span></span>  
  
 <span data-ttu-id="3eca5-116">Você pode criar restrições e chaves primárias quando criar a variável da tabela.</span><span class="sxs-lookup"><span data-stu-id="3eca5-116">You can create constraints and primary keys when you create the table variable.</span></span> <span data-ttu-id="3eca5-117">Restrições são uma boa forma de assegurar que os dados de uma tabela atendam a requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="3eca5-117">Constraints are a good way to ensure that the data in a table meets specific requirements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3eca5-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3eca5-118">In This Section</span></span>  
 [<span data-ttu-id="3eca5-119">Usos de parâmetros ODBC com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="3eca5-119">Uses of ODBC Table-Valued Parameters</span></span>](uses-of-odbc-table-valued-parameters.md)  
 <span data-ttu-id="3eca5-120">Descreve os cenários principais de usuário para parâmetros com valor de tabela e ODBC.</span><span class="sxs-lookup"><span data-stu-id="3eca5-120">Describes the primary user scenarios for table-valued parameters and ODBC.</span></span>  
  
 [<span data-ttu-id="3eca5-121">Tipo ODBC SQL para parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="3eca5-121">ODBC SQL Type for Table-Valued Parameters</span></span>](odbc-sql-type-for-table-valued-parameters.md)  
 <span data-ttu-id="3eca5-122">Descreve o tipo SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="3eca5-122">Describes the SQL_SS_TABLE type.</span></span> <span data-ttu-id="3eca5-123">Esse é um novo tipo ODBC SQL que oferece suporte a parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="3eca5-123">This is a new ODBC SQL type that supports table-valued parameters.</span></span>  
  
 [<span data-ttu-id="3eca5-124">Campos do descritor de parâmetro com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="3eca5-124">Table-Valued Parameter Descriptor Fields</span></span>](table-valued-parameter-descriptor-fields.md)  
 <span data-ttu-id="3eca5-125">Descreve campos do descritor que oferece suporte a parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="3eca5-125">Describes descriptor fields that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="3eca5-126">Campos descritores para colunas constituintes do parâmetro com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="3eca5-126">Descriptor Fields for Table-Valued Parameter Constituent Columns</span></span>](descriptor-fields-for-table-valued-parameter-constituent-columns.md)  
 <span data-ttu-id="3eca5-127">Descreve campos de descritor que têm significado para parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="3eca5-127">Describes descriptor fields that have meaning for table-valued parameters.</span></span>  
  
 [<span data-ttu-id="3eca5-128">Campos de registro de diagnóstico de parâmetro com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="3eca5-128">Table-Valued Parameter Diagnostic Record Fields</span></span>](table-valued-parameter-diagnostic-record-fields.md)  
 <span data-ttu-id="3eca5-129">Descreve dois campos de diagnóstico que foram acrescentados a registros de diagnóstico para oferecer suporte a parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="3eca5-129">Describes two diagnostic fields that have been added to diagnostic records to support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="3eca5-130">Atributos de instruções que afetam parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="3eca5-130">Statement Attributes that Affect Table-Valued Parameters</span></span>](statement-attributes-that-affect-table-valued-parameters.md)  
 <span data-ttu-id="3eca5-131">Descreve um novo campo de cabeçalho do descritor que permite tratar as colunas de parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="3eca5-131">Describes a new descriptor header field that enables table-valued parameters columns to be addressed.</span></span>  
  
 [<span data-ttu-id="3eca5-132">Associação e transferência de dados de parâmetros com valor de tabela e valores de coluna</span><span class="sxs-lookup"><span data-stu-id="3eca5-132">Binding and Data Transfer of Table-Valued Parameters and Column Values</span></span>](binding-and-data-transfer-of-table-valued-parameters-and-column-values.md)  
 <span data-ttu-id="3eca5-133">Descreve a associação de parâmetro e como transmitir um parâmetro com valor de tabela ao servidor.</span><span class="sxs-lookup"><span data-stu-id="3eca5-133">Describes parameter binding and how to pass a table-valued parameter to the server.</span></span>  
  
 [<span data-ttu-id="3eca5-134">Metadados do parâmetro com valor de tabela para instruções preparadas</span><span class="sxs-lookup"><span data-stu-id="3eca5-134">Table-Valued Parameter Metadata for Prepared Statements</span></span>](table-valued-parameter-metadata-for-prepared-statements.md)  
 <span data-ttu-id="3eca5-135">Descreve como um aplicativo pode obter metadados para uma chamada de procedimento preparada.</span><span class="sxs-lookup"><span data-stu-id="3eca5-135">Describes how an application can obtain metadata for a prepared procedure call.</span></span>  
  
 [<span data-ttu-id="3eca5-136">Metadados adicionais de parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="3eca5-136">Additional Table-Valued Parameter Metadata</span></span>](additional-table-valued-parameter-metadata.md)  
 <span data-ttu-id="3eca5-137">Descreve como usar SQLProcedureColumns, SQLTables e SQLColumns para recuperar metadados para um parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="3eca5-137">Describes how to use SQLProcedureColumns, SQLTables, and SQLColumns to retrieve metadata for a table-valued parameter.</span></span>  
  
 [<span data-ttu-id="3eca5-138">Conversão de dados de parâmetros com valor de tabela e outros erros e avisos</span><span class="sxs-lookup"><span data-stu-id="3eca5-138">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>](table-valued-parameter-data-conversion-and-other-errors-and-warnings.md)  
 <span data-ttu-id="3eca5-139">Descreve como processar erros em valores de colunas de parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="3eca5-139">Describes how to process errors on table-valued parameter column values.</span></span>  
  
 [<span data-ttu-id="3eca5-140">Compatibilidade entre versões</span><span class="sxs-lookup"><span data-stu-id="3eca5-140">Cross-Version Compatibility</span></span>](cross-version-compatibility.md)  
 <span data-ttu-id="3eca5-141">Descreve conflitos que podem ocorrer quando parâmetros com valor de tabela são usados por um cliente ou servidor com versão anterior ao [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3eca5-141">Describes conflicts that can occur when table-valued parameters are used by a client or server of a version earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 [<span data-ttu-id="3eca5-142">Resumo de APIs de parâmetros com valor de tabela ODBC</span><span class="sxs-lookup"><span data-stu-id="3eca5-142">ODBC Table-Valued Parameter API Summary</span></span>](odbc-table-valued-parameter-api-summary.md)  
 <span data-ttu-id="3eca5-143">Lista as funções do ODBC com suporte a parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="3eca5-143">Lists the ODBC functions that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="3eca5-144">Exemplos de programação de parâmetros com valor de tabela (ODBC)</span><span class="sxs-lookup"><span data-stu-id="3eca5-144">ODBC Table-Valued Parameter Programming Examples</span></span>](../../database-engine/dev-guide/odbc-table-valued-parameter-programming-examples.md)  
 <span data-ttu-id="3eca5-145">Descreve como executar tarefas comuns.</span><span class="sxs-lookup"><span data-stu-id="3eca5-145">Describes how to perform common tasks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eca5-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3eca5-146">See Also</span></span>  
 <span data-ttu-id="3eca5-147">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="3eca5-147">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="3eca5-148">Os parâmetros com valor de tabela &#40;SQL Server Native Client&#41;</span><span class="sxs-lookup"><span data-stu-id="3eca5-148">Table-Valued Parameters &#40;SQL Server Native Client&#41;</span></span>](../native-client/features/table-valued-parameters-sql-server-native-client.md)  
  
  
