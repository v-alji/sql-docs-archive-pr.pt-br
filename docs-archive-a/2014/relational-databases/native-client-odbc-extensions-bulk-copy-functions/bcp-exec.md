---
title: bcp_exec | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_exec
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_exec function
ms.assetid: b23ea2cc-8545-4873-b0c1-57e76b0a3a7b
author: rothja
ms.author: jroth
ms.openlocfilehash: f925c6cb1e3a36f79ba4f560a06c5b6d499ece4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568534"
---
# <a name="bcp_exec"></a><span data-ttu-id="d985e-102">bcp_exec</span><span class="sxs-lookup"><span data-stu-id="d985e-102">bcp_exec</span></span>
  <span data-ttu-id="d985e-103">Executa uma cópia em massa completa dos dados entre uma tabela de banco de dados e um arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="d985e-103">Executes a complete bulk copy of data between a database table and a user file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d985e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d985e-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_exec (  
HDBC   
hdbc  
,  
LPDBINT   
pnRowsProcessed  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d985e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d985e-105">Arguments</span></span>  
 <span data-ttu-id="d985e-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="d985e-106">*hdbc*</span></span>  
 <span data-ttu-id="d985e-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="d985e-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="d985e-108">*pnRowsProcessed*</span><span class="sxs-lookup"><span data-stu-id="d985e-108">*pnRowsProcessed*</span></span>  
 <span data-ttu-id="d985e-109">É um ponteiro para um DBINT.</span><span class="sxs-lookup"><span data-stu-id="d985e-109">Is a pointer to a DBINT.</span></span> <span data-ttu-id="d985e-110">A função **bcp_exec** preenche esse DBINT com o número de linhas copiadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="d985e-110">The **bcp_exec** function fills this DBINT with the number of rows successfully copied.</span></span> <span data-ttu-id="d985e-111">Se *pnRowsProcessed* for NULL, ele será ignorado por **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="d985e-111">If *pnRowsProcessed* is NULL, it is ignored by **bcp_exec**.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d985e-112">Retornos</span><span class="sxs-lookup"><span data-stu-id="d985e-112">Returns</span></span>  
 <span data-ttu-id="d985e-113">SUCCEED, SUCCEED_ASYNC ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="d985e-113">SUCCEED, SUCCEED_ASYNC, or FAIL.</span></span> <span data-ttu-id="d985e-114">Os lucros de função **bcp_exec** retornarão SUCCEED se todas as linhas forem copiadas.</span><span class="sxs-lookup"><span data-stu-id="d985e-114">The **bcp_exec** function returns SUCCEED if all rows are copied.</span></span> <span data-ttu-id="d985e-115">**bcp_exec** retornará SUCCEED_ASYNC se uma operação de cópia em massa assíncrona ainda estiver pendente.</span><span class="sxs-lookup"><span data-stu-id="d985e-115">**bcp_exec** returns SUCCEED_ASYNC if an asynchronous bulk copy operation is still outstanding.</span></span> <span data-ttu-id="d985e-116">**bcp_exec** retornará FAIL se uma falha completa ocorrer, ou se o número de linhas que geram erros alcançar o valor especificado para BCPMAXERRS usando [bcp_control](bcp-control.md).</span><span class="sxs-lookup"><span data-stu-id="d985e-116">**bcp_exec** returns FAIL if a complete failure occurs, or if the number of rows generating errors reaches the value specified for BCPMAXERRS using [bcp_control](bcp-control.md).</span></span> <span data-ttu-id="d985e-117">O padrão de BCPMAXERRS é definido como 10.</span><span class="sxs-lookup"><span data-stu-id="d985e-117">BCPMAXERRS defaults to 10.</span></span> <span data-ttu-id="d985e-118">A opção BCPMAXERRS afeta somente os erros de sintaxe detectados pelo provedor ao ler as linhas do arquivo de dados (e não as linhas enviadas para o servidor).</span><span class="sxs-lookup"><span data-stu-id="d985e-118">The BCPMAXERRS option affects only the syntax errors detected by the provider while reading the rows from the data file (and not the rows sent to the server).</span></span> <span data-ttu-id="d985e-119">O servidor anula o lote ao detectar um erro com uma linha.</span><span class="sxs-lookup"><span data-stu-id="d985e-119">Server aborts the batch when it detects an error with a row.</span></span> <span data-ttu-id="d985e-120">Verifique o parâmetro *pnRowsProcessed* para o número de linhas copiadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="d985e-120">Check the *pnRowsProcessed* parameter for the number of rows successfully copied.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d985e-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="d985e-121">Remarks</span></span>  
 <span data-ttu-id="d985e-122">Esta função copia os dados de um arquivo de usuário para uma tabela de banco de dados ou vice-versa, dependendo do valor do parâmetro *eDirection* em [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="d985e-122">This function copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter in [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="d985e-123">Antes de chamar **bcp_exec**, chame **bcp_init** com um nome de arquivo de usuário válido.</span><span class="sxs-lookup"><span data-stu-id="d985e-123">Before calling **bcp_exec**, call **bcp_init** with a valid user file name.</span></span> <span data-ttu-id="d985e-124">Caso isso não seja feito, será gerado um erro.</span><span class="sxs-lookup"><span data-stu-id="d985e-124">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="d985e-125">**bcp_exec** é a única função de cópia em massa que provavelmente ficará pendente para qualquer duração de tempo.</span><span class="sxs-lookup"><span data-stu-id="d985e-125">**bcp_exec** is the only bulk copy function that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="d985e-126">Portanto, é a única função de cópia em massa que suporta o modo assíncrono.</span><span class="sxs-lookup"><span data-stu-id="d985e-126">It is therefore the only bulk copy function that supports asynchronous mode.</span></span> <span data-ttu-id="d985e-127">Para definir o modo assíncrono, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) para definir SQL_ATTR_ASYNC_ENABLE como SQL_ASYNC_ENABLE_ON antes de chamar **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="d985e-127">To set asynchronous mode, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set SQL_ATTR_ASYNC_ENABLE to SQL_ASYNC_ENABLE_ON before calling **bcp_exec**.</span></span> <span data-ttu-id="d985e-128">Para testar se houve a conclusão, chame **bcp_exec** com os mesmos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d985e-128">To test for completion, call **bcp_exec** with the same parameters.</span></span> <span data-ttu-id="d985e-129">Se a cópia em massa ainda não tiver sido concluída, **bcp_exec** retornará SUCCEED_ASYNC.</span><span class="sxs-lookup"><span data-stu-id="d985e-129">If the bulk copy has not yet completed, **bcp_exec** returns SUCCEED_ASYNC.</span></span> <span data-ttu-id="d985e-130">Retornará também em *pnRowsProcessed* uma contagem de status do número de linhas que foram enviadas para o servidor.</span><span class="sxs-lookup"><span data-stu-id="d985e-130">It also returns in *pnRowsProcessed* a status count of the number of rows that have been sent to the server.</span></span> <span data-ttu-id="d985e-131">As linhas enviadas para o servidor não serão confirmadas até que o fim de um lote seja atingido.</span><span class="sxs-lookup"><span data-stu-id="d985e-131">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
 <span data-ttu-id="d985e-132">Para obter informações sobre uma alteração significativa na cópia em massa a partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , consulte [executando operações de cópia em massa &#40;&#41;ODBC ](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="d985e-132">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d985e-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d985e-133">Example</span></span>  
 <span data-ttu-id="d985e-134">O exemplo a seguir mostra como usar **bcp_exec**:</span><span class="sxs-lookup"><span data-stu-id="d985e-134">The following example shows how to use **bcp_exec**:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("pubs..authors"), _T("authors.sav"), NULL, DB_OUT)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Now, execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   if (nRowsProcessed == -1)  
      {  
      printf_s("No rows processed on bulk copy execution.\n");  
      }  
   else  
      {  
      printf_s("Incomplete bulk copy.   Only %ld row%s copied.\n",  
         nRowsProcessed, (nRowsProcessed == 1) ? "": "s");  
      }  
   return;  
   }  
  
printf_s("%ld rows processed.\n", nRowsProcessed);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="d985e-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d985e-135">See Also</span></span>  
 [<span data-ttu-id="d985e-136">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="d985e-136">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
