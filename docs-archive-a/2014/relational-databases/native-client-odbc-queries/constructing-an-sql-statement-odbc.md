---
title: Construindo uma instrução SQL (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
ms.assetid: 0acc71e2-8004-4dd8-8592-05c022bdd692
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c454f936c49335555ca09b190e4d604c9fbad64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569422"
---
# <a name="constructing-an-sql-statement-odbc"></a><span data-ttu-id="7c09a-102">Construindo uma instrução SQL (ODBC)</span><span class="sxs-lookup"><span data-stu-id="7c09a-102">Constructing an SQL Statement (ODBC)</span></span>
  <span data-ttu-id="7c09a-103">Aplicativos ODBC realizam quase todo o acesso ao banco de dados executando instruções [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c09a-103">ODBC applications perform almost all of their database access by executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="7c09a-104">A forma dessas instruções depende dos requisitos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7c09a-104">The form of these statements depends on the application requirements.</span></span> <span data-ttu-id="7c09a-105">As instruções SQL podem ser construídas das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="7c09a-105">SQL statements can be constructed in the following ways:</span></span>  
  
-   <span data-ttu-id="7c09a-106">Embutidas em código</span><span class="sxs-lookup"><span data-stu-id="7c09a-106">Hard-coded</span></span>  
  
     <span data-ttu-id="7c09a-107">Instruções estáticas executadas por um aplicativo como uma tarefa fixa.</span><span class="sxs-lookup"><span data-stu-id="7c09a-107">Static statements performed by an application as a fixed task.</span></span>  
  
-   <span data-ttu-id="7c09a-108">Construídas em tempo de execução</span><span class="sxs-lookup"><span data-stu-id="7c09a-108">Constructed at run time</span></span>  
  
     <span data-ttu-id="7c09a-109">Instruções SQL construídas em tempo de execução que permitem ao usuário adaptar a instrução usando cláusulas comuns, como SELECT, WHERE e ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="7c09a-109">SQL statements constructed at run time that enable the user to tailor the statement by using common clauses, such as SELECT, WHERE, and ORDER BY.</span></span> <span data-ttu-id="7c09a-110">Isso inclui consultas ad hoc inseridas por usuários.</span><span class="sxs-lookup"><span data-stu-id="7c09a-110">This includes ad hoc queries entered by users.</span></span>  
  
 <span data-ttu-id="7c09a-111">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do cliente analisa instruções SQL somente para sintaxe ODBC e ISO sem suporte direto do [!INCLUDE[ssDE](../../includes/ssde-md.md)] , que o driver transforma em [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c09a-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client ODBC driver parses SQL statements only for ODBC and ISO syntax not directly supported by the [!INCLUDE[ssDE](../../includes/ssde-md.md)], which the driver transforms into [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7c09a-112">Todas as outras sintaxes SQL são transmitidas inalteradas ao [!INCLUDE[ssDE](../../includes/ssde-md.md)], onde o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] determinará se é um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] válido.</span><span class="sxs-lookup"><span data-stu-id="7c09a-112">All other SQL syntax is passed to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] unchanged, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will determine if it is valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7c09a-113">Essa abordagem gera dois benefícios:</span><span class="sxs-lookup"><span data-stu-id="7c09a-113">This approach yields two benefits:</span></span>  
  
-   <span data-ttu-id="7c09a-114">Redução da sobrecarga</span><span class="sxs-lookup"><span data-stu-id="7c09a-114">Reduced overhead</span></span>  
  
     <span data-ttu-id="7c09a-115">A sobrecarga de processamento do driver é minimizada porque ele só precisa examinar um conjunto pequeno de cláusulas ODBC e ISO.</span><span class="sxs-lookup"><span data-stu-id="7c09a-115">Processing overhead for the driver is minimized because it only has to scan for a small set of ODBC and ISO clauses.</span></span>  
  
-   <span data-ttu-id="7c09a-116">Flexibilidade</span><span class="sxs-lookup"><span data-stu-id="7c09a-116">Flexibility</span></span>  
  
     <span data-ttu-id="7c09a-117">Os programadores podem adaptar a portabilidade dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="7c09a-117">Programmers can tailor the portability of their applications.</span></span> <span data-ttu-id="7c09a-118">Para aumentar a portabilidade em vários bancos de dados, use principalmente as sintaxes ISO e ODBC.</span><span class="sxs-lookup"><span data-stu-id="7c09a-118">To enhance portability against multiple databases, use primarily ODBC and ISO syntax.</span></span> <span data-ttu-id="7c09a-119">Para usar aprimoramentos específicos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use a sintaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] apropriada.</span><span class="sxs-lookup"><span data-stu-id="7c09a-119">To use enhancements specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the appropriate [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax.</span></span> <span data-ttu-id="7c09a-120">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client dá suporte à [!INCLUDE[tsql](../../includes/tsql-md.md)] sintaxe completa, portanto, os aplicativos baseados em ODBC podem aproveitar todos os recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c09a-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the complete [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax so ODBC-based applications can take advantage of all the features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7c09a-121">A lista de colunas em uma instrução SELECT deverá conter apenas as colunas necessárias para executar a tarefa atual.</span><span class="sxs-lookup"><span data-stu-id="7c09a-121">The column list in a SELECT statement should contain only the columns required to perform the current task.</span></span> <span data-ttu-id="7c09a-122">Isso não apenas reduz a quantidade de dados enviados pela rede, mas também reduz o efeito das alterações no banco de dados no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7c09a-122">Not only does this reduce the amount of data sent across the network, but also it reduces the effect of database changes on the application.</span></span> <span data-ttu-id="7c09a-123">Se um aplicativo não fizer referência a uma coluna de uma tabela, ele não será afetado por qualquer alteração feita nessa coluna.</span><span class="sxs-lookup"><span data-stu-id="7c09a-123">If an application does not reference a column from a table, then the application is not affected by any changes made to that column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c09a-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7c09a-124">See Also</span></span>  
 [<span data-ttu-id="7c09a-125">Executando consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="7c09a-125">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
