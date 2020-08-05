---
title: bcp_moretext | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_moretext
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_moretext function
ms.assetid: 23e98015-a8e4-4434-9b3f-9c7350cf965f
author: rothja
ms.author: jroth
ms.openlocfilehash: 00c0eb1c8739e94380b12034cebc70d8e22b79c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572061"
---
# <a name="bcp_moretext"></a><span data-ttu-id="d41e0-102">bcp_moretext</span><span class="sxs-lookup"><span data-stu-id="d41e0-102">bcp_moretext</span></span>
  <span data-ttu-id="d41e0-103">Envia parte de um valor de tipo de dados longo, de tamanho variável, para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d41e0-103">Sends part of a long, variable-length data type value to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d41e0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d41e0-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_moretext (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
LPCBYTE   
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d41e0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d41e0-105">Arguments</span></span>  
 <span data-ttu-id="d41e0-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="d41e0-106">*hdbc*</span></span>  
 <span data-ttu-id="d41e0-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="d41e0-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="d41e0-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="d41e0-108">*cbData*</span></span>  
 <span data-ttu-id="d41e0-109">É o número de bytes de dados que estão sendo copiados para SQL Server dos dados referenciados por *pData*.</span><span class="sxs-lookup"><span data-stu-id="d41e0-109">Is the number of bytes of data being copied to SQL Server from the data referenced by *pData*.</span></span> <span data-ttu-id="d41e0-110">Um valor igual a SQL_NULL_DATA indica NULL.</span><span class="sxs-lookup"><span data-stu-id="d41e0-110">A value of SQL_NULL_DATA indicates NULL.</span></span>  
  
 <span data-ttu-id="d41e0-111">*pData*</span><span class="sxs-lookup"><span data-stu-id="d41e0-111">*pData*</span></span>  
 <span data-ttu-id="d41e0-112">É um ponteiro da parte de dados de tamanho variável, longa, para a qual há suporte a ser enviado para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d41e0-112">Is a pointer to the supported, long, variable-length data chunk to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d41e0-113">Retornos</span><span class="sxs-lookup"><span data-stu-id="d41e0-113">Returns</span></span>  
 <span data-ttu-id="d41e0-114">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="d41e0-114">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d41e0-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="d41e0-115">Remarks</span></span>  
 <span data-ttu-id="d41e0-116">Essa função pode ser usada em conjunto com [bcp_bind](bcp-bind.md) e [bcp_sendrow](bcp-sendrow.md) para copiar valores de dados longos e de comprimento variável para SQL Server em um número de partes menores.</span><span class="sxs-lookup"><span data-stu-id="d41e0-116">This function can be used in conjunction with [bcp_bind](bcp-bind.md) and [bcp_sendrow](bcp-sendrow.md) to copy long, variable-length data values to SQL Server in a number of smaller chunks.</span></span> <span data-ttu-id="d41e0-117">**bcp_moretext** pode ser usado com colunas que têm os seguintes tipos de dados de SQL Server: `text` ,,,, `ntext` `image` `varchar(max)` `nvarchar(max)` , `varbinary(max)` , tipo definido pelo usuário (UDT) e XML.</span><span class="sxs-lookup"><span data-stu-id="d41e0-117">**bcp_moretext** can be used with columns that have the following SQL Server data types: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, user-defined type (UDT), and XML.</span></span> <span data-ttu-id="d41e0-118">**bcp_moretext** não oferece suporte a conversões de dados, os dados fornecidos devem corresponder ao tipo de dados da coluna de destino.</span><span class="sxs-lookup"><span data-stu-id="d41e0-118">**bcp_moretext** does not support data conversions, the data supplied must match the data type of the target column.</span></span>  
  
 <span data-ttu-id="d41e0-119">Se **bcp_bind** for chamado com um parâmetro *pData* não nulo para tipos de dados com suporte no **bcp_moretext**, `bcp_sendrow` o enviará todo o valor dos dados, independentemente do comprimento.</span><span class="sxs-lookup"><span data-stu-id="d41e0-119">If **bcp_bind** is called with a nonNULL *pData* parameter for data types that are supported by **bcp_moretext**, `bcp_sendrow` sends the entire data value, regardless of length.</span></span> <span data-ttu-id="d41e0-120">No entanto, se **bcp_bind** tiver um parâmetro *pData* nulo para tipos de dados com suporte, **bcp_moretext** poderá ser usado para copiar dados imediatamente após um retorno bem-sucedido de `bcp_sendrow` indicar que todas as colunas associadas com dados presentes foram processadas.</span><span class="sxs-lookup"><span data-stu-id="d41e0-120">If, however, **bcp_bind** has a NULL *pData* parameter for supported data types, **bcp_moretext** can be used to copy data immediately after a successful return from `bcp_sendrow` indicating that any bound columns with data present have been processed.</span></span>  
  
 <span data-ttu-id="d41e0-121">Se você usar **bcp_moretext** para enviar uma coluna de tipo de dados com suporte em uma linha, você também deverá usá-la para enviar todas as outras colunas de tipo de dados com suporte na linha.</span><span class="sxs-lookup"><span data-stu-id="d41e0-121">If you use **bcp_moretext** to send one supported data type column in a row, you must also use it to send all other supported data type columns in the row.</span></span> <span data-ttu-id="d41e0-122">Nenhuma coluna pode ser ignorada.</span><span class="sxs-lookup"><span data-stu-id="d41e0-122">No columns may be skipped.</span></span> <span data-ttu-id="d41e0-123">Os tipos de dados para os quais há suporte são SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT e SQLXML.</span><span class="sxs-lookup"><span data-stu-id="d41e0-123">Supported data types are SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT and SQLXML.</span></span> <span data-ttu-id="d41e0-124">SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY e SQLVARBINARY também se encontram nessa categoria caso a coluna seja varchar(max), nvarchar(max) ou varbinary(max), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d41e0-124">SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY and SQLVARBINARY also fall into this category if the column is a varchar(max), nvarchar(max) or varbinary(max), respectively.</span></span>  
  
 <span data-ttu-id="d41e0-125">Chamar **bcp_bind** ou [bcp_collen](bcp-collen.md) define o tamanho total de todas as partes de dados a serem copiadas para a coluna SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d41e0-125">Calling either **bcp_bind** or [bcp_collen](bcp-collen.md) sets the total length of all data parts to be copied to the SQL Server column.</span></span> <span data-ttu-id="d41e0-126">Uma tentativa de enviar SQL Server mais bytes do que o especificado na chamada para **bcp_bind** ou `bcp_collen` gera um erro.</span><span class="sxs-lookup"><span data-stu-id="d41e0-126">An attempt to send SQL Server more bytes than specified in the call to **bcp_bind** or `bcp_collen` generates an error.</span></span> <span data-ttu-id="d41e0-127">Esse erro ocorreria, por exemplo, em um aplicativo que costumava `bcp_collen` definir o comprimento dos dados disponíveis para uma coluna de SQL Server `text` como 4500 e, em seguida, chamado **bcp_moretext** cinco vezes ao indicar em cada chamada que o comprimento do buffer de dados era de 1000 bytes.</span><span class="sxs-lookup"><span data-stu-id="d41e0-127">This error would arise, for example, in an application which used `bcp_collen` to set the length of available data for an SQL Server `text` column to 4500, then called **bcp_moretext** five times while indicating on each call that the data buffer length was 1000 bytes long.</span></span>  
  
 <span data-ttu-id="d41e0-128">Se uma linha copiada contiver mais de uma coluna de comprimento variável longa, **bcp_moretext** primeiro envia seus dados para a coluna numerada ordinal mais baixa, seguida pela próxima coluna numerada ordinal mais baixa e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d41e0-128">If a copied row contains more than one long, variable-length column, **bcp_moretext** first sends its data to the lowest ordinally numbered column, followed by the next lowest ordinally numbered column, and so on.</span></span> <span data-ttu-id="d41e0-129">A configuração correta do comprimento total dos dados esperados é importante.</span><span class="sxs-lookup"><span data-stu-id="d41e0-129">Correct setting of the total length of expected data is important.</span></span> <span data-ttu-id="d41e0-130">Não há nenhuma forma de sinalizar, fora da configuração de comprimento, que todos os dados de uma coluna foram recebidos pela cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="d41e0-130">There is no way to signal, outside of the length setting, that all data for a column has been received by bulk copy.</span></span>  
  
 <span data-ttu-id="d41e0-131">Quando os `var(max)` valores são enviados ao servidor usando bcp_sendrow e bcp_moretext, não é necessário chamar bcp_collen para definir o comprimento da coluna.</span><span class="sxs-lookup"><span data-stu-id="d41e0-131">When `var(max)` values are sent to the server using bcp_sendrow and bcp_moretext, it is not necessary to call bcp_collen to set the column length.</span></span> <span data-ttu-id="d41e0-132">Em vez disso, somente para esses tipos, o valor é encerrado chamando bcp_sendrow com um comprimento de zero.</span><span class="sxs-lookup"><span data-stu-id="d41e0-132">Instead, for these types only, the value is terminated by calling bcp_sendrow with a length of zero.</span></span>  
  
 <span data-ttu-id="d41e0-133">Normalmente, um aplicativo chama `bcp_sendrow` e **bcp_moretext** em loops para enviar um número de linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="d41e0-133">An application normally calls `bcp_sendrow` and **bcp_moretext** within loops to send a number of rows of data.</span></span> <span data-ttu-id="d41e0-134">Aqui está uma descrição de como fazer isso para uma tabela que contém duas `text` colunas:</span><span class="sxs-lookup"><span data-stu-id="d41e0-134">Here's an outline of how to do this for a table containing two `text` columns:</span></span>  
  
```  
while (there are still rows to send)  
{  
bcp_sendrow(...);  
  
for (all the data in the first varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
for (all the data in the second varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
}  
  
```  
  
## <a name="example"></a><span data-ttu-id="d41e0-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d41e0-135">Example</span></span>  
 <span data-ttu-id="d41e0-136">Este exemplo mostra como usar **bcp_moretext** com **bcp_bind** e `bcp_sendrow` :</span><span class="sxs-lookup"><span data-stu-id="d41e0-136">This example shows how to use **bcp_moretext** with **bcp_bind** and `bcp_sendrow`:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      idRow = 5;  
char*      pPart1 = "This text value isn't very long,";  
char*      pPart2 = " but it's broken into three parts";  
char*      pPart3 = " anyhow.";  
DBINT      cbAllParts;  
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
if (bcp_init(hdbc, "comdb..articles", NULL, NULL, DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idRow, 0, SQL_VARLEN_DATA, NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
cbAllParts = (DBINT) (strnlen(pPart1, sizeof(pPart1) + 1) + strnlen(pPart2, sizeof(pPart2) + 1) + strnlen(pPart3, sizeof(pPart3) + 1));  
if (bcp_bind(hdbc, NULL, 0, cbAllParts, NULL, 0, SQLTEXT, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Send this row, with the text value broken into three chunks.   
if (bcp_sendrow(hdbc) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart1, sizeof(pPart1) + 1), pPart1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart2, sizeof(pPart2) + 1), pPart2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart3, sizeof(pPart3) + 1), pPart3) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// All done. Get the number of rows processed (should be one).  
nRowsProcessed = bcp_done(hdbc);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="d41e0-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d41e0-137">See Also</span></span>  
 [<span data-ttu-id="d41e0-138">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="d41e0-138">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
