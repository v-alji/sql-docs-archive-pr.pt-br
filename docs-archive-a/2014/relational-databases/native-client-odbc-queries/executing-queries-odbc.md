---
title: Executando consultas (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, executing queries
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
- SQL Server Native Client ODBC driver, queries
- queries [ODBC]
ms.assetid: d935bcba-8ce6-4159-8395-6c86431602ad
author: rothja
ms.author: jroth
ms.openlocfilehash: adc51186803148056401f58f1207d3e9a7abf9c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569419"
---
# <a name="executing-queries-odbc"></a><span data-ttu-id="467f8-102">Executando consultas (ODBC)</span><span class="sxs-lookup"><span data-stu-id="467f8-102">Executing Queries (ODBC)</span></span>
  <span data-ttu-id="467f8-103">Depois que um aplicativo ODBC inicializa um identificador de conexão e conecta-se a uma fonte de dados, ele aloca um ou mais identificadores de instrução no identificador de conexão.</span><span class="sxs-lookup"><span data-stu-id="467f8-103">After an ODBC application initializes a connection handle and connects with a data source, it allocates one or more statement handles on the connection handle.</span></span> <span data-ttu-id="467f8-104">O aplicativo pode então executar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instruções no identificador da instrução.</span><span class="sxs-lookup"><span data-stu-id="467f8-104">The application can then execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements on the statement handle.</span></span> <span data-ttu-id="467f8-105">A sequência geral de eventos na execução de uma instrução SQL é:</span><span class="sxs-lookup"><span data-stu-id="467f8-105">The general sequence of events in executing an SQL statement is:</span></span>  
  
1.  <span data-ttu-id="467f8-106">Definir quaisquer atributos de instrução necessários.</span><span class="sxs-lookup"><span data-stu-id="467f8-106">Set any required statement attributes.</span></span>  
  
2.  <span data-ttu-id="467f8-107">Construir a instrução.</span><span class="sxs-lookup"><span data-stu-id="467f8-107">Construct the statement.</span></span>  
  
3.  <span data-ttu-id="467f8-108">Executar a instrução.</span><span class="sxs-lookup"><span data-stu-id="467f8-108">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="467f8-109">Recuperar quaisquer conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="467f8-109">Retrieve any result sets.</span></span>  
  
 <span data-ttu-id="467f8-110">Depois que um aplicativo recuperar todas as linhas em todos os conjuntos de resultados retornados pela instrução SQL, ele pode executar outra consulta no mesmo identificador de instrução.</span><span class="sxs-lookup"><span data-stu-id="467f8-110">After an application retrieves all the rows in all of the result sets returned by the SQL statement, it can execute another query on the same statement handle.</span></span> <span data-ttu-id="467f8-111">Se um aplicativo determinar que não é necessário recuperar todas as linhas em um determinado conjunto de resultados, ele poderá cancelar o restante do conjunto de resultados chamando [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) ou [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="467f8-111">If an application determines that it is not required to retrieve all the rows in a particular result set, it can cancel the rest of the result set by calling either [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
 <span data-ttu-id="467f8-112">Se você precisar executar a mesma instrução SQL várias vezes com dados diferentes em um aplicativo ODBC, use um marcador de parâmetros indicado por um ponto de interrogação (?) na construção de uma instrução SQL:</span><span class="sxs-lookup"><span data-stu-id="467f8-112">If, in an ODBC application, you must execute the same SQL statement multiple times with different data, use a parameter marker denoted by a question mark (?) in the construction of an SQL statement:</span></span>  
  
```  
INSERT INTO MyTable VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="467f8-113">Cada marcador de parâmetro pode então ser associado a uma variável de programa chamando [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="467f8-113">Each parameter marker can then be bound to a program variable by calling [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).</span></span>  
  
 <span data-ttu-id="467f8-114">Depois que todas as instruções SQL forem executadas e seus conjuntos de resultados forem processados, o aplicativo liberará a alça de instrução.</span><span class="sxs-lookup"><span data-stu-id="467f8-114">After all SQL statements execute and their result sets process, the application frees the statement handle.</span></span>  
  
 <span data-ttu-id="467f8-115">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client dá suporte a vários identificadores de instrução por identificador de conexão.</span><span class="sxs-lookup"><span data-stu-id="467f8-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports multiple statement handles per connection handle.</span></span> <span data-ttu-id="467f8-116">As transações são gerenciadas no nível da conexão. Dessa forma, todo o trabalho realizado em todos os identificadores de instrução em um único identificador de conexão é gerenciado como parte da mesma transação.</span><span class="sxs-lookup"><span data-stu-id="467f8-116">Transactions are managed at the connection level, so that all work performed on all statement handles on a single connection handle are managed as part of the same transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="467f8-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="467f8-117">In This Section</span></span>  
  
-   [<span data-ttu-id="467f8-118">Alocando um identificador de instrução</span><span class="sxs-lookup"><span data-stu-id="467f8-118">Allocating a Statement Handle</span></span>](allocating-a-statement-handle.md)  
  
-   [<span data-ttu-id="467f8-119">Construindo uma instrução SQL &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="467f8-119">Constructing an SQL Statement &#40;ODBC&#41;</span></span>](constructing-an-sql-statement-odbc.md)  
  
-   [<span data-ttu-id="467f8-120">Construindo instruções SQL para cursores</span><span class="sxs-lookup"><span data-stu-id="467f8-120">Constructing SQL Statements for Cursors</span></span>](constructing-sql-statements-for-cursors.md)  
  
-   [<span data-ttu-id="467f8-121">Usando parâmetros de instrução</span><span class="sxs-lookup"><span data-stu-id="467f8-121">Using Statement Parameters</span></span>](using-statement-parameters.md)  
  
-   [<span data-ttu-id="467f8-122">Executando instruções &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="467f8-122">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements/executing-statements-odbc.md)  
  
-   [<span data-ttu-id="467f8-123">Liberando um identificador de instrução</span><span class="sxs-lookup"><span data-stu-id="467f8-123">Freeing a Statement Handle</span></span>](freeing-a-statement-handle.md)  
  
## <a name="see-also"></a><span data-ttu-id="467f8-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="467f8-124">See Also</span></span>  
 [<span data-ttu-id="467f8-125">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="467f8-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
