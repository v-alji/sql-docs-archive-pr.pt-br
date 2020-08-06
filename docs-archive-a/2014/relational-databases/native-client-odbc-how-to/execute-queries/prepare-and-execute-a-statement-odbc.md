---
title: Preparar e executar uma instrução (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
- statement preparation
ms.assetid: 0adecc63-4da5-486c-bc48-09a004a2fae6
author: rothja
ms.author: jroth
ms.openlocfilehash: 607d8ad1509eca1204f6d029842b04120d3f5d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684711"
---
# <a name="prepare-and-execute-a-statement-odbc"></a><span data-ttu-id="fde7c-102">Preparar e executar uma instrução (ODBC)</span><span class="sxs-lookup"><span data-stu-id="fde7c-102">Prepare and Execute a Statement (ODBC)</span></span>
    
### <a name="to-prepare-a-statement-once-and-then-execute-it-multiple-times"></a><span data-ttu-id="fde7c-103">Para preparar uma instrução uma vez e, depois, executá-la várias vezes</span><span class="sxs-lookup"><span data-stu-id="fde7c-103">To prepare a statement once, and then execute it multiple times</span></span>  
  
1.  <span data-ttu-id="fde7c-104">Chame a [Função SQL Prepare](https://go.microsoft.com/fwlink/?LinkId=59360) para preparar a instrução.</span><span class="sxs-lookup"><span data-stu-id="fde7c-104">Call [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) to prepare the statement.</span></span>  
  
2.  <span data-ttu-id="fde7c-105">Opcionalmente, chame [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) para determinar o número de parâmetros na instrução preparada.</span><span class="sxs-lookup"><span data-stu-id="fde7c-105">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
3.  <span data-ttu-id="fde7c-106">Opcionalmente, para cada parâmetro na instrução preparada:</span><span class="sxs-lookup"><span data-stu-id="fde7c-106">Optionally, for each parameter in the prepared statement:</span></span>  
  
    -   <span data-ttu-id="fde7c-107">Chame [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) para obter informações de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fde7c-107">Call [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to get parameter information.</span></span>  
  
    -   <span data-ttu-id="fde7c-108">Associe cada parâmetro a uma variável de programa usando [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="fde7c-108">Bind each parameter to a program variable by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="fde7c-109">Configure qualquer parâmetro de dados em execução.</span><span class="sxs-lookup"><span data-stu-id="fde7c-109">Set up any data-at-execution parameters.</span></span>  
  
4.  <span data-ttu-id="fde7c-110">Para cada execução de uma instrução preparada:</span><span class="sxs-lookup"><span data-stu-id="fde7c-110">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="fde7c-111">Se a instrução tiver marcadores de parâmetro, coloque os valores de dados no buffer de parâmetros associado.</span><span class="sxs-lookup"><span data-stu-id="fde7c-111">If the statement has parameter markers, put the data values into the bound parameter buffer.</span></span>  
  
    -   <span data-ttu-id="fde7c-112">Chame [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) para executar a instrução preparada.</span><span class="sxs-lookup"><span data-stu-id="fde7c-112">Call [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="fde7c-113">Se forem usados parâmetros de entrada de dados em execução, [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) retornará SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="fde7c-113">If data-at-execution input parameters are used, [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="fde7c-114">Envie os dados em partes useo [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) e [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="fde7c-114">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-prepare-a-statement-with-column-wise-parameter-binding"></a><span data-ttu-id="fde7c-115">Para preparar uma instrução com associação de parâmetro de coluna</span><span class="sxs-lookup"><span data-stu-id="fde7c-115">To prepare a statement with column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="fde7c-116">Chame [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para definir os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="fde7c-116">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="fde7c-117">Defina SQL_ATTR_PARAMSET_SIZE como o número de conjuntos (S) de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="fde7c-117">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="fde7c-118">Defina SQL_ATTR_PARAM_BIND_TYPE como SQL_PARAMETER_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="fde7c-118">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="fde7c-119">Defina o atributo SQL_ATTR_PARAMS_PROCESSED_PTR de forma que aponte para uma variável SQLUINTEGER que contém o número de parâmetros processados.</span><span class="sxs-lookup"><span data-stu-id="fde7c-119">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="fde7c-120">Defina SQL_ATTR_PARAMS_STATUS_PTR de forma que aponte para uma matriz[S] de variáveis SQLUSSMALLINT que contém indicadores de status de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fde7c-120">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="fde7c-121">Chame SQLPrepare para preparar a instrução.</span><span class="sxs-lookup"><span data-stu-id="fde7c-121">Call SQLPrepare to prepare the statement.</span></span>  
  
3.  <span data-ttu-id="fde7c-122">Opcionalmente, chame [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) para determinar o número de parâmetros na instrução preparada.</span><span class="sxs-lookup"><span data-stu-id="fde7c-122">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
4.  <span data-ttu-id="fde7c-123">Opcionalmente, para cada parâmetro na instrução preparada, chame SQLDescribeParam para obter informações de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fde7c-123">Optionally, for each parameter in the prepared statement, call SQLDescribeParam to get parameter information.</span></span>  
  
5.  <span data-ttu-id="fde7c-124">Para cada marcador de parâmetro:</span><span class="sxs-lookup"><span data-stu-id="fde7c-124">For each parameter marker:</span></span>  
  
    -   <span data-ttu-id="fde7c-125">Aloque uma matriz de S buffers de parâmetro para armazenar valores de dados.</span><span class="sxs-lookup"><span data-stu-id="fde7c-125">Allocate an array of S parameter buffers to store data values.</span></span>  
  
    -   <span data-ttu-id="fde7c-126">Aloque uma matriz de S buffers de parâmetro para armazenar comprimentos de dados.</span><span class="sxs-lookup"><span data-stu-id="fde7c-126">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="fde7c-127">Chame SQLBindParameter para associar as matrizes de comprimento de dados e de valor de dados de parâmetro ao parâmetro de instrução.</span><span class="sxs-lookup"><span data-stu-id="fde7c-127">Call SQLBindParameter to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
    -   <span data-ttu-id="fde7c-128">Se o parâmetro for um parâmetro de imagem ou de texto de dados em execução, configure-o.</span><span class="sxs-lookup"><span data-stu-id="fde7c-128">If the parameter is a data-at-execution text or image parameter, set it up.</span></span>  
  
    -   <span data-ttu-id="fde7c-129">Se qualquer parâmetro de dados em execução for usado, configure-o.</span><span class="sxs-lookup"><span data-stu-id="fde7c-129">If any data-at-execution parameters are used, set them up.</span></span>  
  
6.  <span data-ttu-id="fde7c-130">Para cada execução de uma instrução preparada:</span><span class="sxs-lookup"><span data-stu-id="fde7c-130">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="fde7c-131">Coloque os S valores de dados e os S comprimentos de dados nas matrizes de parâmetros associadas.</span><span class="sxs-lookup"><span data-stu-id="fde7c-131">Put the S data values and S data lengths into the bound parameter arrays.</span></span>  
  
    -   <span data-ttu-id="fde7c-132">Chame SQLExecute para executar a instrução preparada.</span><span class="sxs-lookup"><span data-stu-id="fde7c-132">Call SQLExecute to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="fde7c-133">Se forem usados parâmetros de entrada de dados em execução, SQLExecute retornará SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="fde7c-133">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="fde7c-134">Envie os dados em partes useo SQLParamData e SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="fde7c-134">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
### <a name="to-prepare-a-statement-with-row-wise-bound-parameters"></a><span data-ttu-id="fde7c-135">Para preparar uma instrução com parâmetros associados de linha</span><span class="sxs-lookup"><span data-stu-id="fde7c-135">To prepare a statement with row-wise bound parameters</span></span>  
  
1.  <span data-ttu-id="fde7c-136">Aloque uma matriz[S] de estruturas, onde S é o número de conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="fde7c-136">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="fde7c-137">A estrutura tem um elemento para cada parâmetro e cada elemento tem duas partes:</span><span class="sxs-lookup"><span data-stu-id="fde7c-137">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="fde7c-138">A primeira parte é uma variável do tipo de dados apropriado que contém os dados de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fde7c-138">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
    -   <span data-ttu-id="fde7c-139">A segunda parte é uma variável SQLINTEGER que contém o indicador de status.</span><span class="sxs-lookup"><span data-stu-id="fde7c-139">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="fde7c-140">Chame [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para definir os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="fde7c-140">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="fde7c-141">Defina SQL_ATTR_PARAMSET_SIZE como o número de conjuntos (S) de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="fde7c-141">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="fde7c-142">Defina SQL_ATTR_PARAM_BIND_TYPE como o tamanho da estrutura alocada na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="fde7c-142">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="fde7c-143">Defina o atributo SQL_ATTR_PARAMS_PROCESSED_PTR de forma que aponte para uma variável SQLUINTEGER que contém o número de parâmetros processados.</span><span class="sxs-lookup"><span data-stu-id="fde7c-143">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="fde7c-144">Defina SQL_ATTR_PARAMS_STATUS_PTR de forma que aponte para uma matriz[S] de variáveis SQLUSSMALLINT que contém indicadores de status de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="fde7c-144">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="fde7c-145">Chame SQLPrepare para preparar a instrução.</span><span class="sxs-lookup"><span data-stu-id="fde7c-145">Call SQLPrepare to prepare the statement.</span></span>  
  
4.  <span data-ttu-id="fde7c-146">Para cada marcador de parâmetro, chame SQLBindParameter para apontar o valor de dados de parâmetro e o ponteiro de comprimento de dados para suas variáveis no primeiro elemento da matriz de estruturas alocada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="fde7c-146">For each parameter marker, call SQLBindParameter to point the parameter data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="fde7c-147">Se o parâmetro for um parâmetro de dados em execução, configure-o.</span><span class="sxs-lookup"><span data-stu-id="fde7c-147">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
5.  <span data-ttu-id="fde7c-148">Para cada execução de uma instrução preparada:</span><span class="sxs-lookup"><span data-stu-id="fde7c-148">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="fde7c-149">Preencha a matriz de buffers de parâmetros associada com valores de dados.</span><span class="sxs-lookup"><span data-stu-id="fde7c-149">Fill the bound parameter buffer array with data values.</span></span>  
  
    -   <span data-ttu-id="fde7c-150">Chame SQLExecute para executar a instrução preparada.</span><span class="sxs-lookup"><span data-stu-id="fde7c-150">Call SQLExecute to execute the prepared statement.</span></span> <span data-ttu-id="fde7c-151">O driver executa, com eficiência, a instrução SQL S vezes, uma vez para cada conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="fde7c-151">The driver efficiently executes the SQL statement S times, once for each set of parameters.</span></span>  
  
    -   <span data-ttu-id="fde7c-152">Se forem usados parâmetros de entrada de dados em execução, SQLExecute retornará SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="fde7c-152">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="fde7c-153">Envie os dados em partes useo SQLParamData e SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="fde7c-153">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde7c-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fde7c-154">See Also</span></span>  
 [<span data-ttu-id="fde7c-155">Tópicos de instruções sobre como executar consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="fde7c-155">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
