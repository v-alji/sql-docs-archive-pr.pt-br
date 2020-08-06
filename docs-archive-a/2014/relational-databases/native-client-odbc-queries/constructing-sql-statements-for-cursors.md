---
title: Construindo instruções SQL para cursores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], statement construction
- ODBC applications, cursors
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
- statements [ODBC], cursors
ms.assetid: 134003fd-9c93-4f5c-a988-045990933b80
author: rothja
ms.author: jroth
ms.openlocfilehash: b0fe0831b97c13c5d20067386f4e9d8c97ee19ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569421"
---
# <a name="constructing-sql-statements-for-cursors"></a><span data-ttu-id="87dc0-102">Construindo instruções SQL para cursores</span><span class="sxs-lookup"><span data-stu-id="87dc0-102">Constructing SQL Statements for Cursors</span></span>
  <span data-ttu-id="87dc0-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client usa cursores de servidor para implementar a funcionalidade de cursor definida na especificação ODBC.</span><span class="sxs-lookup"><span data-stu-id="87dc0-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses server cursors to implement the cursor functionality defined in the ODBC specification.</span></span> <span data-ttu-id="87dc0-104">Um aplicativo ODBC controla o comportamento do cursor usando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) para definir atributos de instrução diferentes.</span><span class="sxs-lookup"><span data-stu-id="87dc0-104">An ODBC application controls the cursor behavior by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) to set different statement attributes.</span></span> <span data-ttu-id="87dc0-105">Estes são os atributos e seus padrões.</span><span class="sxs-lookup"><span data-stu-id="87dc0-105">These are the attributes and their defaults.</span></span>  
  
|<span data-ttu-id="87dc0-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="87dc0-106">Attribute</span></span>|<span data-ttu-id="87dc0-107">Padrão</span><span class="sxs-lookup"><span data-stu-id="87dc0-107">Default</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="87dc0-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="87dc0-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="87dc0-109">SQL_CONCUR_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="87dc0-109">SQL_CONCUR_READ_ONLY</span></span>|  
|<span data-ttu-id="87dc0-110">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="87dc0-110">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="87dc0-111">SQL_CURSOR_FORWARD_ONLY</span><span class="sxs-lookup"><span data-stu-id="87dc0-111">SQL_CURSOR_FORWARD_ONLY</span></span>|  
|<span data-ttu-id="87dc0-112">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="87dc0-112">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="87dc0-113">SQL_NONSCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="87dc0-113">SQL_NONSCROLLABLE</span></span>|  
|<span data-ttu-id="87dc0-114">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="87dc0-114">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="87dc0-115">SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="87dc0-115">SQL_UNSPECIFIED</span></span>|  
|<span data-ttu-id="87dc0-116">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="87dc0-116">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="87dc0-117">1</span><span class="sxs-lookup"><span data-stu-id="87dc0-117">1</span></span>|  
  
 <span data-ttu-id="87dc0-118">Quando essas opções são definidas para seus padrões no momento em que uma instrução SQL é executada, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client não usa um cursor de servidor para implementar o conjunto de resultados; em vez disso, ele usa um conjunto de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="87dc0-118">When these options are set to their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not use a server cursor to implement the result set; instead, it uses a default result set.</span></span> <span data-ttu-id="87dc0-119">Se qualquer uma dessas opções for alterada de seus padrões no momento em que uma instrução SQL for executada, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client tentará usar um cursor de servidor para implementar o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="87dc0-119">If any of these options are changed from their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver attempts to use a server cursor to implement the result set.</span></span>  
  
 <span data-ttu-id="87dc0-120">Conjuntos de resultados padrão oferecem suporte a todas as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87dc0-120">Default result sets support all of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="87dc0-121">Não há nenhuma restrição quanto aos tipos de instruções SQL que podem ser executados ao usar um conjunto de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="87dc0-121">There are no restrictions on the types of SQL statements that can be executed when using a default result set.</span></span>  
  
 <span data-ttu-id="87dc0-122">Os cursores de servidor não oferecem suporte a todas as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87dc0-122">Server cursors do not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="87dc0-123">Os cursores de servidor não oferecem suporte a nenhuma instrução SQL que gera vários conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="87dc0-123">Server cursors do not support any SQL statement that generates multiple result sets.</span></span>  
  
 <span data-ttu-id="87dc0-124">Os seguintes tipos de instruções não oferecem suporte por meio de cursores de servidor:</span><span class="sxs-lookup"><span data-stu-id="87dc0-124">The following types of statements are not supported by server cursors:</span></span>  
  
-   <span data-ttu-id="87dc0-125">Lotes</span><span class="sxs-lookup"><span data-stu-id="87dc0-125">Batches</span></span>  
  
     <span data-ttu-id="87dc0-126">Instruções SQL criadas a partir de duas ou mais instruções SQL SELECT individuais, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="87dc0-126">SQL statements built from two or more individual SQL SELECT statements, for example:</span></span>  
  
    ```  
    SELECT * FROM Authors; SELECT * FROM Titles  
    ```  
  
-   <span data-ttu-id="87dc0-127">Procedimentos armazenados com várias instruções SELECT</span><span class="sxs-lookup"><span data-stu-id="87dc0-127">Stored procedures with multiple SELECT statements</span></span>  
  
     <span data-ttu-id="87dc0-128">As instruções SQL que executam um procedimento armazenado contendo mais de uma instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="87dc0-128">SQL statements that execute a stored procedure containing more than one SELECT statement.</span></span> <span data-ttu-id="87dc0-129">Isso inclui instruções SELECT que preenchem parâmetros ou variáveis.</span><span class="sxs-lookup"><span data-stu-id="87dc0-129">This includes SELECT statements that fill parameters or variables.</span></span>  
  
-   <span data-ttu-id="87dc0-130">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="87dc0-130">Keywords</span></span>  
  
     <span data-ttu-id="87dc0-131">Instruções SQL que contêm as palavras-chave FOR BROWSE ou INTO.</span><span class="sxs-lookup"><span data-stu-id="87dc0-131">SQL statements containing the keywords FOR BROWSE, or INTO.</span></span>  
  
 <span data-ttu-id="87dc0-132">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], caso uma instrução SQL correspondente a alguma dessas condições seja executada com um cursor de servidor, este é implicitamente convertido em um conjunto de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="87dc0-132">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if an SQL statement that matches any of these conditions is executed with a server cursor, the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="87dc0-133">Após **SQLExecDirect** ou **SQLExecute** retornar SQL_SUCCESS_WITH_INFO, os atributos de cursor serão definidos de volta para suas configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="87dc0-133">After **SQLExecDirect** or **SQLExecute** returns SQL_SUCCESS_WITH_INFO, the cursor attributes will be set back to their default settings.</span></span>  
  
 <span data-ttu-id="87dc0-134">As instruções SQL que não se enquadram nas categorias acima podem ser executadas com qualquer configuração de atributo da instrução; elas funcionam igualmente bem com um conjunto de resultados padrão ou um cursor de servidor.</span><span class="sxs-lookup"><span data-stu-id="87dc0-134">SQL statements that do not fit the categories above can be executed with any statement attribute settings; they work equally well with either a default result set or a server cursor.</span></span>  
  
## <a name="errors"></a><span data-ttu-id="87dc0-135">Errors</span><span class="sxs-lookup"><span data-stu-id="87dc0-135">Errors</span></span>  
 <span data-ttu-id="87dc0-136">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 e posterior, uma tentativa de executar uma instrução que produz vários conjuntos de resultados gera SQL_SUCCESS_WITH INFO, além da seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="87dc0-136">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 and later, an attempt to execute a statement that produces multiple result sets generates SQL_SUCCESS_WITH INFO and the following message:</span></span>  
  
```  
SqlState: 01S02"  
pfNative: 0  
szErrorMsgString: "[Microsoft][SQL Server Native Client][SQL Server]  
               Cursor type changed."  
```  
  
 <span data-ttu-id="87dc0-137">Os aplicativos ODBC que recebem essa mensagem podem chamar [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) para determinar as configurações atuais do cursor.</span><span class="sxs-lookup"><span data-stu-id="87dc0-137">ODBC applications receiving this message can call [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) to determine the current cursor settings.</span></span>  
  
 <span data-ttu-id="87dc0-138">Uma tentativa de executar um procedimento com várias instruções SELECT durante o uso de cursores de servidor gera o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="87dc0-138">An attempt to execute a procedure with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16937  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               A server cursor is not allowed on a stored procedure  
               with more than one SELECT statement in it. Use a  
               default result set or client cursor.  
```  
  
 <span data-ttu-id="87dc0-139">Uma tentativa de executar um lote com várias instruções SELECT durante o uso de cursores de servidor gera o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="87dc0-139">An attempt to execute a batch with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16938  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               sp_cursoropen. The statement parameter can only  
               be a single SELECT statement or a single stored   
               procedure.  
```  
  
 <span data-ttu-id="87dc0-140">Aplicativos ODBC que recebem esses erros devem restaurar todos padrões dos atributos de instrução de cursor antes de tentar executá-la.</span><span class="sxs-lookup"><span data-stu-id="87dc0-140">ODBC applications receiving these errors must reset all the cursor statement attributes to their defaults before attempting to execute the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87dc0-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="87dc0-141">See Also</span></span>  
 [<span data-ttu-id="87dc0-142">Executando consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="87dc0-142">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
