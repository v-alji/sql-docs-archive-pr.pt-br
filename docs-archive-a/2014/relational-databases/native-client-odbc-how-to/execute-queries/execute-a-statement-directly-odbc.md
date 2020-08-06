---
title: Executar uma instrução diretamente (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
ms.assetid: b690f9de-66e1-4ee5-ab6a-121346fb5f85
author: rothja
ms.author: jroth
ms.openlocfilehash: 2aeada906a925cff93455ffd92e7c17822a80124
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568524"
---
# <a name="execute-a-statement-directly-odbc"></a><span data-ttu-id="65d46-102">Executar diretamente uma instrução (ODBC)</span><span class="sxs-lookup"><span data-stu-id="65d46-102">Execute a Statement Directly (ODBC)</span></span>
    
### <a name="to-execute-a-statement-directly-and-one-time-only"></a><span data-ttu-id="65d46-103">Para executar uma instrução diretamente e apenas uma vez</span><span class="sxs-lookup"><span data-stu-id="65d46-103">To execute a statement directly and one time only</span></span>  
  
1.  <span data-ttu-id="65d46-104">Se a instrução tiver marcadores de parâmetro, use [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) para associar cada parâmetro a uma variável de programa.</span><span class="sxs-lookup"><span data-stu-id="65d46-104">If the statement has parameter markers, use [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind each parameter to a program variable.</span></span> <span data-ttu-id="65d46-105">Preencha as variáveis de programa com valores de dados e configure todos os parâmetros de dados em execução.</span><span class="sxs-lookup"><span data-stu-id="65d46-105">Fill the program variables with data values, and then set up any data-at-execution parameters.</span></span>  
  
2.  <span data-ttu-id="65d46-106">Chame [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) para executar a instrução.</span><span class="sxs-lookup"><span data-stu-id="65d46-106">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span>  
  
3.  <span data-ttu-id="65d46-107">Se forem usados parâmetros de entrada de dados em execução, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) retornará SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="65d46-107">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="65d46-108">Envie os dados em partes useo [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) e [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="65d46-108">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-column-wise-parameter-binding"></a><span data-ttu-id="65d46-109">Para executar uma instrução várias vezes usando a associação de parâmetros por coluna</span><span class="sxs-lookup"><span data-stu-id="65d46-109">To execute a statement multiple times by using column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="65d46-110">Chame [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para definir os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="65d46-110">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="65d46-111">Defina SQL_ATTR_PARAMSET_SIZE como o número de conjuntos (S) de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="65d46-111">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="65d46-112">Defina SQL_ATTR_PARAM_BIND_TYPE como SQL_PARAMETER_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="65d46-112">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
     <span data-ttu-id="65d46-113">Defina o atributo SQL_ATTR_PARAMS_PROCESSED_PTR de forma que aponte para uma variável SQLUINTEGER que contém o número de parâmetros processados.</span><span class="sxs-lookup"><span data-stu-id="65d46-113">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="65d46-114">Defina SQL_ATTR_PARAMS_STATUS_PTR de forma que aponte para uma matriz[S] de variáveis SQLUSSMALLINT que contém os indicadores de status de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="65d46-114">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="65d46-115">Para cada marcador de parâmetro:</span><span class="sxs-lookup"><span data-stu-id="65d46-115">For each parameter marker:</span></span>  
  
     <span data-ttu-id="65d46-116">Aloque uma matriz de S buffers de parâmetro para armazenar valores de dados.</span><span class="sxs-lookup"><span data-stu-id="65d46-116">Allocate an array of S parameter buffers to store data values.</span></span>  
  
     <span data-ttu-id="65d46-117">Aloque uma matriz de S buffers de parâmetro para armazenar comprimentos de dados.</span><span class="sxs-lookup"><span data-stu-id="65d46-117">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
     <span data-ttu-id="65d46-118">Chame [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) para associar as matrizes de comprimento de dados e de valor de dados de parâmetro ao parâmetro de instrução.</span><span class="sxs-lookup"><span data-stu-id="65d46-118">Call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
     <span data-ttu-id="65d46-119">Configure quaisquer parâmetros de imagem ou texto de dados em execução.</span><span class="sxs-lookup"><span data-stu-id="65d46-119">Set up any data-at-execution text or image parameters.</span></span>  
  
     <span data-ttu-id="65d46-120">Coloque os valores de dados S e os comprimentos de dados S nas matrizes de parâmetro associadas.</span><span class="sxs-lookup"><span data-stu-id="65d46-120">Put S data values and S data lengths into the bound parameter arrays.</span></span>  
  
3.  <span data-ttu-id="65d46-121">Chame [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) para executar a instrução.</span><span class="sxs-lookup"><span data-stu-id="65d46-121">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="65d46-122">O driver executa a instrução de maneira eficiente S vezes, sendo uma para cada conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="65d46-122">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
4.  <span data-ttu-id="65d46-123">Se forem usados parâmetros de entrada de dados em execução, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) retornará SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="65d46-123">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="65d46-124">Envie os dados em partes useo [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) e [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="65d46-124">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-row-wise-parameter-binding"></a><span data-ttu-id="65d46-125">Para executar uma instrução várias vezes usando a associação de parâmetros por linha</span><span class="sxs-lookup"><span data-stu-id="65d46-125">To execute a statement multiple times by using row-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="65d46-126">Aloque uma matriz[S] de estruturas, onde S é o número de conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="65d46-126">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="65d46-127">A estrutura tem um elemento para cada parâmetro e cada elemento tem duas partes:</span><span class="sxs-lookup"><span data-stu-id="65d46-127">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
     <span data-ttu-id="65d46-128">A primeira parte é uma variável do tipo de dados apropriado que contém os dados de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="65d46-128">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
     <span data-ttu-id="65d46-129">A segunda parte é uma variável SQLINTEGER que contém o indicador de status.</span><span class="sxs-lookup"><span data-stu-id="65d46-129">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="65d46-130">Chame [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para definir os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="65d46-130">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="65d46-131">Defina SQL_ATTR_PARAMSET_SIZE como o número de conjuntos (S) de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="65d46-131">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="65d46-132">Defina SQL_ATTR_PARAM_BIND_TYPE como o tamanho da estrutura alocada na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="65d46-132">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
     <span data-ttu-id="65d46-133">Defina o atributo SQL_ATTR_PARAMS_PROCESSED_PTR de forma que aponte para uma variável SQLUINTEGER que contém o número de parâmetros processados.</span><span class="sxs-lookup"><span data-stu-id="65d46-133">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="65d46-134">Defina SQL_ATTR_PARAMS_STATUS_PTR de forma que aponte para uma matriz[S] de variáveis SQLUSSMALLINT que contém os indicadores de status de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="65d46-134">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="65d46-135">Para cada marcador de parâmetro, chame [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) para direcionar o ponteiro de comprimento de dados e de valor de dados do parâmetro para suas variáveis no primeiro elemento da matriz de estruturas alocadas na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="65d46-135">For each parameter marker, call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to point the parameter's data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="65d46-136">Se o parâmetro for um parâmetro de dados em execução, configure-o.</span><span class="sxs-lookup"><span data-stu-id="65d46-136">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
4.  <span data-ttu-id="65d46-137">Preencha a matriz de buffers de parâmetros associada com valores de dados.</span><span class="sxs-lookup"><span data-stu-id="65d46-137">Fill the bound parameter buffer array with data values.</span></span>  
  
5.  <span data-ttu-id="65d46-138">Chame [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) para executar a instrução.</span><span class="sxs-lookup"><span data-stu-id="65d46-138">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="65d46-139">O driver executa a instrução de maneira eficiente S vezes, sendo uma para cada conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="65d46-139">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
6.  <span data-ttu-id="65d46-140">Se forem usados parâmetros de entrada de dados em execução, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) retornará SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="65d46-140">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="65d46-141">Envie os dados em partes useo [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) e [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="65d46-141">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
 <span data-ttu-id="65d46-142">**Observação** As associações por coluna e por linha geralmente são mais usadas em conjunto com [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) e [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) do que com [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span><span class="sxs-lookup"><span data-stu-id="65d46-142">**Note** Column-wise and row-wise binding are more typically used in conjunction with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) and [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) than with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d46-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="65d46-143">See Also</span></span>  
 [<span data-ttu-id="65d46-144">Tópicos de instruções sobre como executar consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="65d46-144">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
