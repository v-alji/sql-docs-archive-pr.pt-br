---
title: Usando arquivos de dados e arquivos de formato | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- ODBC, functions
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [SQL Server Native Client]
- ODBC, bulk copy operations
- bulk copy [ODBC], data files
ms.assetid: c01b7155-3f0a-473d-90b7-87a97bc56ca5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e0ee92f79e2c8cab9605db0188e01898df8c23e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685660"
---
# <a name="using-data-files-and-format-files"></a><span data-ttu-id="d962e-102">Usando arquivos de dados e de formato</span><span class="sxs-lookup"><span data-stu-id="d962e-102">Using Data Files and Format Files</span></span>
  <span data-ttu-id="d962e-103">O programa de cópia em massa mais simples executa estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="d962e-103">The simplest bulk copy program does the following:</span></span>  
  
1.  <span data-ttu-id="d962e-104">Chama [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) para especificar a cópia em massa (Set BCP_OUT) de uma tabela ou exibição para um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="d962e-104">Calls [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to specify bulk copying out (set BCP_OUT) from a table or view to a data file.</span></span>  
  
2.  <span data-ttu-id="d962e-105">Chama [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) para executar a operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="d962e-105">Calls [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="d962e-106">O arquivo de dados é criado em modo nativo; portanto, os dados de todas as colunas na tabela ou exibição são armazenados no arquivo de dados com o mesmo formato do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d962e-106">The data file is created in native mode; therefore, data from all columns in the table or view are stored in the data file in the same format as in the database.</span></span> <span data-ttu-id="d962e-107">É possível executar cópia em massa de entrada do arquivo em um servidor usando essas mesmas etapas e definindo DB_IN em vez de DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="d962e-107">The file can then be bulk copied into a server by using these same steps and setting DB_IN instead of DB_OUT.</span></span> <span data-ttu-id="d962e-108">Isso só funcionará se ambas as tabelas (origem e destino) tiverem exatamente a mesma estrutura.</span><span class="sxs-lookup"><span data-stu-id="d962e-108">This works only if both the source and target tables have exactly the same structure.</span></span> <span data-ttu-id="d962e-109">O arquivo de dados resultante também pode ser inserido para o utilitário **bcp** usando a opção **/n** (modo nativo).</span><span class="sxs-lookup"><span data-stu-id="d962e-109">The resulting data file can also be input to the **bcp** utility by using the **/n** (native mode) switch.</span></span>  
  
 <span data-ttu-id="d962e-110">Para executar a cópia em massa de saída do conjunto de resultados de uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)], em vez de diretamente de uma tabela ou exibição:</span><span class="sxs-lookup"><span data-stu-id="d962e-110">To bulk copy out the result set of a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement instead of directly from a table or view:</span></span>  
  
1.  <span data-ttu-id="d962e-111">Chame **bcp_init** para especificar a cópia em massa, mas especifique NULL para o nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="d962e-111">Call **bcp_init** to specify bulk copying out, but specify NULL for the table name.</span></span>  
  
2.  <span data-ttu-id="d962e-112">Chame [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) com *EOPTION* definido como BCPHINTS e *iValue* definido como um ponteiro para uma cadeia de caracteres SQLTCHAR que contém a instrução Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="d962e-112">Call [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) with *eOption* set to BCPHINTS and *iValue* set to a pointer to a SQLTCHAR string containing the Transact-SQL statement.</span></span>  
  
3.  <span data-ttu-id="d962e-113">Chame **bcp_exec** para executar a operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="d962e-113">Call **bcp_exec** to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="d962e-114">A instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] pode ser qualquer instrução que gera um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="d962e-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be any statement that generates a result set.</span></span> <span data-ttu-id="d962e-115">Será criado o arquivo de dados que contém o primeiro conjunto de resultados da instrução [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d962e-115">The data file is created containing the first result set of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="d962e-116">A cópia em massa ignora qualquer conjunto de resultados após o primeiro se a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] gera vários conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="d962e-116">Bulk copy ignores any result set after the first if the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement generates multiple result sets.</span></span>  
  
 <span data-ttu-id="d962e-117">Para criar um arquivo de dados no qual os dados de coluna são armazenados em um formato diferente daquele na tabela, chame [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) para especificar quantas colunas serão alteradas e, em seguida, chame [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) para cada coluna cujo formato você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="d962e-117">To create a data file in which column data is stored in a different format than in the table, call [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) to specify how many columns will be changed, then call [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) for each column whose format you want to change.</span></span> <span data-ttu-id="d962e-118">Isso é feito depois de chamar **bcp_init** , mas antes de chamar **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="d962e-118">This is done after calling **bcp_init** but before calling **bcp_exec**.</span></span> <span data-ttu-id="d962e-119">**bcp_colfmt** especifica o formato no qual os dados da coluna são armazenados no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="d962e-119">**bcp_colfmt** specifies the format in which the column's data is stored in the data file.</span></span> <span data-ttu-id="d962e-120">Ele pode ser usado durante a cópia de entrada ou saída em massa. Você também pode usar **bcp_colfmt** para definir os terminadores de linha e coluna.</span><span class="sxs-lookup"><span data-stu-id="d962e-120">It can be used when bulk copying in or out. You can also use **bcp_colfmt** to set the row and column terminators.</span></span> <span data-ttu-id="d962e-121">Por exemplo, se seus dados não contiverem caracteres de tabulação, você poderá criar um arquivo delimitado por tabulação usando **bcp_colfmt** para definir o caractere de tabulação como o terminador para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="d962e-121">For example, if your data contains no tab characters, you can create a tab-delimited file by using **bcp_colfmt** to set the tab character as the terminator for each column.</span></span>  
  
 <span data-ttu-id="d962e-122">Ao copiar e usar **bcp_colfmt**em massa, você pode criar facilmente um arquivo de formato que descreve o arquivo de dados que você criou chamando [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) após a última chamada para **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="d962e-122">When bulk copying out and using **bcp_colfmt**, you can easily create a format file describing the data file you have created by calling [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) after the last call to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="d962e-123">Ao copiar em massa de um arquivo de dados descrito por um arquivo de formato, leia o arquivo de formato chamando [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) após **bcp_init** , mas antes de **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="d962e-123">When bulk copying in from a data file described by a format file, read the format file by calling [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) after **bcp_init** but before **bcp_exec**.</span></span>  
  
 <span data-ttu-id="d962e-124">A função **bcp_control** controla várias opções ao copiar em massa em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="d962e-124">The **bcp_control** function controls several options when bulk copying into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file.</span></span> <span data-ttu-id="d962e-125">**bcp_control** define opções, como o número máximo de erros antes do encerramento, a linha no arquivo no qual iniciar a cópia em massa, a linha a ser interrompida e o tamanho do lote.</span><span class="sxs-lookup"><span data-stu-id="d962e-125">**bcp_control** sets options, such as the maximum number of errors before termination, the row in the file on which to start the bulk copy, the row to stop on, and the batch size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d962e-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d962e-126">See Also</span></span>  
 [<span data-ttu-id="d962e-127">Executando operações de cópia em massa &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="d962e-127">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  
