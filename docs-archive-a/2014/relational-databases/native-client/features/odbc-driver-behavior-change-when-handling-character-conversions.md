---
title: Alteração de comportamento do driver ODBC ao manipular conversões de caracteres | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 682a232a-bf89-4849-88a1-95b2fbac1467
author: rothja
ms.author: jroth
ms.openlocfilehash: 5334b4268559ba155a53b3be655d87f7867779df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679908"
---
# <a name="odbc-driver-behavior-change-when-handling-character-conversions"></a><span data-ttu-id="8b07d-102">Alteração de comportamento do driver ODBC ao lidar com conversões de caracteres</span><span class="sxs-lookup"><span data-stu-id="8b07d-102">ODBC Driver Behavior Change When Handling Character Conversions</span></span>
  <span data-ttu-id="8b07d-103">O [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] driver ODBC do Native Client (SQLNCLI11.dll) alterou como ele faz de SQL_WCHAR \* (nchar/nvarchar/nvarchar (max)) e SQL_CHAR \* (char/varchar/NARCHAR (max)) conversões.</span><span class="sxs-lookup"><span data-stu-id="8b07d-103">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC Driver (SQLNCLI11.dll) changed how it does of SQL_WCHAR\* (NCHAR/NVARCHAR/NVARCHAR(MAX)) and SQL_CHAR\* (CHAR/VARCHAR/NARCHAR(MAX)) conversions.</span></span> <span data-ttu-id="8b07d-104">As funções ODBC, como SQLGetData, SQLBindCol, SQLBindParameter, retornam (-4) SQL_NO_TOTAL como o parâmetro de comprimento/indicador ao usar o driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client.</span><span class="sxs-lookup"><span data-stu-id="8b07d-104">ODBC functions, such as SQLGetData, SQLBindCol, SQLBindParameter, return (-4) SQL_NO_TOTAL as the length/indicator parameter when using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client ODBC driver.</span></span> <span data-ttu-id="8b07d-105">As versões anteriores do driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client retornaram um valor de comprimento, que pode estar incorreto.</span><span class="sxs-lookup"><span data-stu-id="8b07d-105">Prior versions of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver returned a length value, which can be incorrect.</span></span>  
  
## <a name="sqlgetdata-behavior"></a><span data-ttu-id="8b07d-106">Comportamento de SQLGetData</span><span class="sxs-lookup"><span data-stu-id="8b07d-106">SQLGetData Behavior</span></span>  
 <span data-ttu-id="8b07d-107">Muitas funções do Windows permitem especificar um tamanho do buffer de 0 e o comprimento retornado é o tamanho dos dados retornados.</span><span class="sxs-lookup"><span data-stu-id="8b07d-107">Many Windows functions let you specify a buffer size of 0 and the returned length is the size of the returned data.</span></span> <span data-ttu-id="8b07d-108">O seguinte padrão é comum para programadores do Windows:</span><span class="sxs-lookup"><span data-stu-id="8b07d-108">The following pattern is common for Windows programmers:</span></span>  
  
```  
int iSize = 0;  
BYTE * pBuffer = NULL;  
GetMyFavoriteAPI(pBuffer, &iSize);   // Returns needed size in iSize  
pBuffer = new BYTE[iSize];   // Allocate buffer   
GetMyFavoriteAPI(pBuffer, &iSize);   // Retrieve actual data  
```  
  
 <span data-ttu-id="8b07d-109">No entanto, **SQLGetData** não deve ser usado neste cenário.</span><span class="sxs-lookup"><span data-stu-id="8b07d-109">However, **SQLGetData** should not be used in this scenario.</span></span> <span data-ttu-id="8b07d-110">Os padrões a seguir não devem ser usados:</span><span class="sxs-lookup"><span data-stu-id="8b07d-110">The following pattern should not be used:</span></span>  
  
```  
// bad  
int iSize = 0;  
WCHAR * pBuffer = NULL;  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)0x1, 0, &iSize);   // Get storage size needed  
pBuffer = new WCHAR[(iSize/sizeof(WCHAR)) + 1];   // Allocate buffer  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)pBuffer, iSize, &iSize);   // Retrieve data  
```  
  
 <span data-ttu-id="8b07d-111">**SQLGetData** só pode ser chamado para recuperar partes de dados reais.</span><span class="sxs-lookup"><span data-stu-id="8b07d-111">**SQLGetData** can only be called to retrieve chunks of actual data.</span></span> <span data-ttu-id="8b07d-112">Não há suporte para o uso de **SQLGetData** para obter o tamanho dos dados.</span><span class="sxs-lookup"><span data-stu-id="8b07d-112">Using **SQLGetData** to get the size of data is not unsupported.</span></span>  
  
 <span data-ttu-id="8b07d-113">O exemplo a seguir mostra o impacto da alteração do driver quando você usa o padrão incorreto.</span><span class="sxs-lookup"><span data-stu-id="8b07d-113">The following shows the impact of the driver change when you use the incorrect pattern.</span></span> <span data-ttu-id="8b07d-114">Esse aplicativo consulta uma coluna e uma associação `varchar` como Unicode (SQL_UNICODE/SQL_WCHAR):</span><span class="sxs-lookup"><span data-stu-id="8b07d-114">This application queries a `varchar` column and binding as Unicode (SQL_UNICODE/SQL_WCHAR):</span></span>  
  
 <span data-ttu-id="8b07d-115">Consultá`select convert(varchar(36), '123')`</span><span class="sxs-lookup"><span data-stu-id="8b07d-115">Query:  `select convert(varchar(36), '123')`</span></span>  
  
```  
SQLGetData(hstmt, SQL_WCHAR, ....., (SQLPOINTER*) 0x1, 0 , &iSize);   // Attempting to determine storage size needed  
```  
  
|<span data-ttu-id="8b07d-116">Versão do driver ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="8b07d-116">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="8b07d-117">Comprimento ou resultado do indicador</span><span class="sxs-lookup"><span data-stu-id="8b07d-117">Length or Indicator Outcome</span></span>|<span data-ttu-id="8b07d-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="8b07d-118">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="8b07d-119">Native Client ou anterior</span><span class="sxs-lookup"><span data-stu-id="8b07d-119">Native Client or earlier</span></span>|<span data-ttu-id="8b07d-120">6</span><span class="sxs-lookup"><span data-stu-id="8b07d-120">6</span></span>|<span data-ttu-id="8b07d-121">O driver presumiu incorretamente que a conversão de CHAR para WCHAR poderia ser realizada como o comprimento \* 2.</span><span class="sxs-lookup"><span data-stu-id="8b07d-121">The driver incorrectly assumed that converting CHAR to WCHAR could be accomplished as length \* 2.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="8b07d-122">Native Client (versão 11.0.2100.60) ou posterior</span><span class="sxs-lookup"><span data-stu-id="8b07d-122">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="8b07d-123">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="8b07d-123">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="8b07d-124">O driver não assume mais que a conversão de CHAR para WCHAR ou WCHAR em CHAR é uma ação (multiplicar) \* 2 ou (dividir)/2.</span><span class="sxs-lookup"><span data-stu-id="8b07d-124">The driver no longer assumes that converting from CHAR to WCHAR or WCHAR to CHAR is a (multiply) \*2 or (divide)/2 action.</span></span><br /><br /> <span data-ttu-id="8b07d-125">Chamar **SQLGetData** não retorna mais o comprimento da conversão esperada.</span><span class="sxs-lookup"><span data-stu-id="8b07d-125">Calling **SQLGetData** no longer returns the length of the expected conversion.</span></span> <span data-ttu-id="8b07d-126">O driver detecta a conversão para ou de CHAR e WCHAR e retorna (- 4) SQL_NO_TOTAL em vez do comportamento de \*2 ou /2 que poderia estar incorreto.</span><span class="sxs-lookup"><span data-stu-id="8b07d-126">The driver detects the conversion to or from CHAR and WCHAR and returns (-4) SQL_NO_TOTAL instead of \*2 or /2 behavior that could be incorrect.</span></span>|  
  
 <span data-ttu-id="8b07d-127">Use **SQLGetData** para recuperar as partes dos dados.</span><span class="sxs-lookup"><span data-stu-id="8b07d-127">Use **SQLGetData** to retrieve the chunks of the data.</span></span> <span data-ttu-id="8b07d-128">(Pseudocódigo mostrado:)</span><span class="sxs-lookup"><span data-stu-id="8b07d-128">(Pseudo code shown:)</span></span>  
  
```  
while( (SQL_SUCCESS or SQL_SUCCESS_WITH_INFO) == SQLFetch(...) ) {  
   SQLNumCols(...iTotalCols...)  
   for(int iCol = 1; iCol < iTotalCols; iCol++) {  
      WCHAR* pBufOrig, pBuffer = new WCHAR[100];  
      SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get original chunk  
      while(NOT ALL DATA RETREIVED (SQL_NO_TOTAL, ...) ) {  
         pBuffer += 50;   // Advance buffer for data retrieved  
         // May need to realloc the buffer when you reach current size  
         SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get next chunk  
      }  
   }  
}  
```  
  
## <a name="sqlbindcol-behavior"></a><span data-ttu-id="8b07d-129">Comportamento de SQLBindCol</span><span class="sxs-lookup"><span data-stu-id="8b07d-129">SQLBindCol Behavior</span></span>  
 <span data-ttu-id="8b07d-130">Consultá`select convert(varchar(36), '1234567890')`</span><span class="sxs-lookup"><span data-stu-id="8b07d-130">Query:  `select convert(varchar(36), '1234567890')`</span></span>  
  
```  
SQLBindCol(... SQL_W_CHAR, ...)   // Only bound a buffer of WCHAR[4] - Expecting String Data Right Truncation behavior  
```  
  
|<span data-ttu-id="8b07d-131">Versão do driver ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="8b07d-131">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="8b07d-132">Comprimento ou resultado do indicador</span><span class="sxs-lookup"><span data-stu-id="8b07d-132">Length or Indicator Outcome</span></span>|<span data-ttu-id="8b07d-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="8b07d-133">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="8b07d-134">Native Client ou anterior</span><span class="sxs-lookup"><span data-stu-id="8b07d-134">Native Client or earlier</span></span>|<span data-ttu-id="8b07d-135">20</span><span class="sxs-lookup"><span data-stu-id="8b07d-135">20</span></span>|<span data-ttu-id="8b07d-136">-   **SQLFetch** relata que há um truncamento no lado direito dos dados.</span><span class="sxs-lookup"><span data-stu-id="8b07d-136">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="8b07d-137">-Length é o comprimento dos dados retornados, não o que foi armazenado (pressupõe \* 2 caracteres para a conversão WCHAR que pode estar incorreta para glifos).</span><span class="sxs-lookup"><span data-stu-id="8b07d-137">-   Length is the length of the data returned, not what was stored (assumes \*2 CHAR to WCHAR conversion which can be incorrect for glyphs).</span></span><br /><span data-ttu-id="8b07d-138">-Os dados armazenados no buffer são 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="8b07d-138">-   Data stored in buffer is 123\0.</span></span> <span data-ttu-id="8b07d-139">O buffer é garantido para ser terminado em NULL.</span><span class="sxs-lookup"><span data-stu-id="8b07d-139">Buffer is guaranteed to be NULL terminated.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="8b07d-140">Native Client (versão 11.0.2100.60) ou posterior</span><span class="sxs-lookup"><span data-stu-id="8b07d-140">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="8b07d-141">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="8b07d-141">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="8b07d-142">-   **SQLFetch** relata que há um truncamento no lado direito dos dados.</span><span class="sxs-lookup"><span data-stu-id="8b07d-142">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="8b07d-143">-Length indica-4 (SQL_NO_TOTAL) porque o restante dos dados não foi convertido.</span><span class="sxs-lookup"><span data-stu-id="8b07d-143">-   Length indicates -4 (SQL_NO_TOTAL) because the rest of the data was not converted.</span></span><br /><span data-ttu-id="8b07d-144">-Os dados armazenados no buffer são 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="8b07d-144">-   Data stored in the buffer is 123\0.</span></span> <span data-ttu-id="8b07d-145">- O buffer é garantido para ser terminado em NULL.</span><span class="sxs-lookup"><span data-stu-id="8b07d-145">- Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="sqlbindparameter-output-parameter-behavior"></a><span data-ttu-id="8b07d-146">SQLBindParameter (comportamento de parâmetro OUTPUT)</span><span class="sxs-lookup"><span data-stu-id="8b07d-146">SQLBindParameter (OUTPUT Parameter Behavior)</span></span>  
 <span data-ttu-id="8b07d-147">Consultá`create procedure spTest @p1 varchar(max) OUTPUT`</span><span class="sxs-lookup"><span data-stu-id="8b07d-147">Query:  `create procedure spTest @p1 varchar(max) OUTPUT`</span></span>  
  
 `select @p1 = replicate('B', 1234)`  
  
```  
SQLBindParameter(... SQL_W_CHAR, ...)   // Only bind up to first 64 characters  
```  
  
|<span data-ttu-id="8b07d-148">Versão do driver ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="8b07d-148">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="8b07d-149">Comprimento ou resultado do indicador</span><span class="sxs-lookup"><span data-stu-id="8b07d-149">Length or Indicator Outcome</span></span>|<span data-ttu-id="8b07d-150">Descrição</span><span class="sxs-lookup"><span data-stu-id="8b07d-150">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="8b07d-151">Native Client ou anterior</span><span class="sxs-lookup"><span data-stu-id="8b07d-151">Native Client or earlier</span></span>|<span data-ttu-id="8b07d-152">2468</span><span class="sxs-lookup"><span data-stu-id="8b07d-152">2468</span></span>|<span data-ttu-id="8b07d-153">-   **SQLFetch** não retorna mais dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8b07d-153">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="8b07d-154">-   **SQLMoreResults** não retorna mais dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8b07d-154">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="8b07d-155">-Length indica o tamanho dos dados retornados do servidor, não armazenados no buffer.</span><span class="sxs-lookup"><span data-stu-id="8b07d-155">-   Length indicates the size of the data returned from server, not stored in buffer.</span></span><br /><span data-ttu-id="8b07d-156">-O buffer original contém 63 bytes e um terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="8b07d-156">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="8b07d-157">O buffer é garantido para ser terminado em NULL.</span><span class="sxs-lookup"><span data-stu-id="8b07d-157">Buffer is guaranteed to be NULL terminated.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="8b07d-158">Native Client (versão 11.0.2100.60) ou posterior</span><span class="sxs-lookup"><span data-stu-id="8b07d-158">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="8b07d-159">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="8b07d-159">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="8b07d-160">-   **SQLFetch** não retorna mais dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8b07d-160">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="8b07d-161">-   **SQLMoreResults** não retorna mais dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8b07d-161">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="8b07d-162">-Length indica (-4) SQL_NO_TOTAL porque o restante dos dados não foi convertido.</span><span class="sxs-lookup"><span data-stu-id="8b07d-162">-   Length indicates (-4) SQL_NO_TOTAL because the rest of the data was not converted.</span></span><br /><span data-ttu-id="8b07d-163">-O buffer original contém 63 bytes e um terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="8b07d-163">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="8b07d-164">O buffer é garantido para ser terminado em NULL.</span><span class="sxs-lookup"><span data-stu-id="8b07d-164">Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="performing-char-and-wchar-conversions"></a><span data-ttu-id="8b07d-165">Execução de conversões CHAR e WCHAR</span><span class="sxs-lookup"><span data-stu-id="8b07d-165">Performing CHAR and WCHAR Conversions</span></span>  
 <span data-ttu-id="8b07d-166">O driver ODBC do [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client oferece várias maneiras de executar conversões CHAR e WCHAR.</span><span class="sxs-lookup"><span data-stu-id="8b07d-166">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC driver offers several ways to perform CHAR and WCHAR conversions.</span></span> <span data-ttu-id="8b07d-167">A lógica é semelhante à manipulação de BLOBs (varchar (max), nvarchar (max),...):</span><span class="sxs-lookup"><span data-stu-id="8b07d-167">The logic is similar to manipulating blobs (varchar(max), nvarchar(max), ...):</span></span>  
  
-   <span data-ttu-id="8b07d-168">Os dados são salvos ou truncados no buffer especificado durante a associação com **SQLBindCol** ou **SQLBindParameter**.</span><span class="sxs-lookup"><span data-stu-id="8b07d-168">Data is saved or truncated into the specified buffer when binding with **SQLBindCol** or **SQLBindParameter**.</span></span>  
  
-   <span data-ttu-id="8b07d-169">Se você não associar, poderá recuperar os dados em partes usando **SQLGetData** e **SQLParamData**.</span><span class="sxs-lookup"><span data-stu-id="8b07d-169">If you do not bind, you can retrieve the data in chunks by using **SQLGetData** and **SQLParamData**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b07d-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b07d-170">See Also</span></span>  
 [<span data-ttu-id="8b07d-171">Recursos do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="8b07d-171">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
