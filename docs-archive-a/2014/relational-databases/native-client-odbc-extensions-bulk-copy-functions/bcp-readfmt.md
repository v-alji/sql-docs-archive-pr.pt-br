---
title: bcp_readfmt | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_readfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_readfmt function
ms.assetid: 654001c8-ae9f-425c-b820-f0191bf89367
author: rothja
ms.author: jroth
ms.openlocfilehash: 37032ec276be8b914d73e834453cc5d87cdedbbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572058"
---
# <a name="bcp_readfmt"></a><span data-ttu-id="64f34-102">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="64f34-102">bcp_readfmt</span></span>
  <span data-ttu-id="64f34-103">Lê uma definição de formato do arquivo de dados do arquivo de formato especificado.</span><span class="sxs-lookup"><span data-stu-id="64f34-103">Reads a data file format definition from the specified format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64f34-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="64f34-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_readfmt (  
HDBC   
hdbc  
,  
LPCTSTR   
szFormatFile  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="64f34-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="64f34-105">Arguments</span></span>  
 <span data-ttu-id="64f34-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="64f34-106">*hdbc*</span></span>  
 <span data-ttu-id="64f34-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="64f34-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="64f34-108">*szFormatFile*</span><span class="sxs-lookup"><span data-stu-id="64f34-108">*szFormatFile*</span></span>  
 <span data-ttu-id="64f34-109">É o caminho e o nome do arquivo que contém os valores de formato para o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="64f34-109">Is the path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="64f34-110">Retornos</span><span class="sxs-lookup"><span data-stu-id="64f34-110">Returns</span></span>  
 <span data-ttu-id="64f34-111">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="64f34-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64f34-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="64f34-112">Remarks</span></span>  
 <span data-ttu-id="64f34-113">Depois `bcp_readfmt` de ler os valores de formato, ele faz as chamadas apropriadas para [bcp_columns](bcp-columns.md) e [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="64f34-113">After `bcp_readfmt` reads the format values, it makes the appropriate calls to [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span> <span data-ttu-id="64f34-114">Não há necessidade de você analisar um arquivo de formato e fazer essas chamadas.</span><span class="sxs-lookup"><span data-stu-id="64f34-114">There is no need for you to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="64f34-115">Para manter um arquivo de formato, chame [bcp_writefmt](bcp-writefmt.md).</span><span class="sxs-lookup"><span data-stu-id="64f34-115">To persist a format file, call [bcp_writefmt](bcp-writefmt.md).</span></span> <span data-ttu-id="64f34-116">Chamadas para `bcp_readfmt` podem fazer referência a formatos salvos.</span><span class="sxs-lookup"><span data-stu-id="64f34-116">Calls to `bcp_readfmt` can reference saved formats.</span></span> <span data-ttu-id="64f34-117">Para obter mais informações, consulte [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="64f34-117">For more information, see [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="64f34-118">Como alternativa, o utilitário de cópia em massa (**bcp**) pode salvar formatos de dados definidos pelo usuário em arquivos que podem ser referenciados pelo `bcp_readfmt` .</span><span class="sxs-lookup"><span data-stu-id="64f34-118">Alternately, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by `bcp_readfmt`.</span></span> <span data-ttu-id="64f34-119">Para obter mais informações sobre o utilitário **bcp** e a estrutura de arquivos de formato de dados **bcp** , consulte [importação e exportação em massa de dados &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="64f34-119">For more information about the **bcp** utility and the structure of **bcp** data format files, see [Bulk Import and Export of Data &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="64f34-120">O `BCPDELAYREADFMT` valor do parâmetro *eOption* de [bcp_control](bcp-control.md) modifica o comportamento de bcp_readfmt.</span><span class="sxs-lookup"><span data-stu-id="64f34-120">The `BCPDELAYREADFMT` value of the *eOption* parameter of [bcp_control](bcp-control.md) modifies the behavior of bcp_readfmt.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64f34-121">O arquivo de formato deve ter sido gerado pela versão 4.2 ou posterior do utilitário **bcp** .</span><span class="sxs-lookup"><span data-stu-id="64f34-121">The format file must have been produced by version 4.2 or later of the **bcp** utility.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64f34-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="64f34-122">Example</span></span>  
  
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
if (bcp_init(hdbc, _T("myTable"), _T("myData.csv"),  
   _T("myErrors"),    DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_readfmt(hdbc, _T("myFmtFile.fmt")) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_exec(hdbc, &nRowsProcessed) == SUCCEED)  
   {  
   cout << nRowsProcessed << " rows copied to SQL Server\n";  
   }  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="64f34-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="64f34-123">See Also</span></span>  
 [<span data-ttu-id="64f34-124">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="64f34-124">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
