---
title: MSSQLSERVER_137 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 137 (Database Engine error)
ms.assetid: 47fb4212-2165-4fec-bc41-6d548465d7be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e0142cd53006609e9274972e4f5964132f5982c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581912"
---
# <a name="mssqlserver_137"></a><span data-ttu-id="361a9-102">MSSQLSERVER_137</span><span class="sxs-lookup"><span data-stu-id="361a9-102">MSSQLSERVER_137</span></span>
    
## <a name="details"></a><span data-ttu-id="361a9-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="361a9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="361a9-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="361a9-104">Product Name</span></span>|<span data-ttu-id="361a9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="361a9-105">SQL Server</span></span>|  
|<span data-ttu-id="361a9-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="361a9-106">Event ID</span></span>|<span data-ttu-id="361a9-107">137</span><span class="sxs-lookup"><span data-stu-id="361a9-107">137</span></span>|  
|<span data-ttu-id="361a9-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="361a9-108">Event Source</span></span>|<span data-ttu-id="361a9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="361a9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="361a9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="361a9-110">Component</span></span>|<span data-ttu-id="361a9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="361a9-111">SQLEngine</span></span>|  
|<span data-ttu-id="361a9-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="361a9-112">Symbolic Name</span></span>|<span data-ttu-id="361a9-113">P_SCALAR_VAR_NOTFOUND</span><span class="sxs-lookup"><span data-stu-id="361a9-113">P_SCALAR_VAR_NOTFOUND</span></span>|  
|<span data-ttu-id="361a9-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="361a9-114">Message Text</span></span>|<span data-ttu-id="361a9-115">É necessário declarar a variável escalar "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="361a9-115">Must declare the scalar variable "%.\*ls".</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="361a9-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="361a9-116">Explanation</span></span>  
 <span data-ttu-id="361a9-117">Esse erro ocorre quando uma variável é usada em um script SQL sem primeiro declarar a variável.</span><span class="sxs-lookup"><span data-stu-id="361a9-117">This error occurs when a variable is used in a SQL script without first declaring the variable.</span></span> <span data-ttu-id="361a9-118">O exemplo a seguir retorna o erro 137 para as instruções SET e SELECT porque **@mycol** não está declarado.</span><span class="sxs-lookup"><span data-stu-id="361a9-118">The following example returns error 137 for both the SET and SELECT statements because **@mycol** is not declared.</span></span>  
  
 <span data-ttu-id="361a9-119">SET @mycol = 'ContactName';</span><span class="sxs-lookup"><span data-stu-id="361a9-119">SET @mycol = 'ContactName';</span></span>  
  
 <span data-ttu-id="361a9-120">SELECT @mycol;</span><span class="sxs-lookup"><span data-stu-id="361a9-120">SELECT @mycol;</span></span>  
  
 <span data-ttu-id="361a9-121">Uma das causas mais complexas desse erro inclui o uso de uma variável que é declarada fora da instrução EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="361a9-121">One of the more complicated causes of this error includes the use of a variable that is declared outside the EXECUTE statement.</span></span> <span data-ttu-id="361a9-122">Por exemplo, a variável **@mycol** especificada na instrução SELECT é local para a instrução SELECT; portanto, ela está fora da instrução EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="361a9-122">For example, the variable **@mycol** specified in the SELECT statement is local to the SELECT statement; thus it is outside the EXECUTE statement.</span></span>  
  
 <span data-ttu-id="361a9-123">USE AdventureWorks2012;</span><span class="sxs-lookup"><span data-stu-id="361a9-123">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="361a9-124">GO</span><span class="sxs-lookup"><span data-stu-id="361a9-124">GO</span></span>  
  
 <span data-ttu-id="361a9-125">DECLARE @mycol nvarchar(20);</span><span class="sxs-lookup"><span data-stu-id="361a9-125">DECLARE @mycol nvarchar(20);</span></span>  
  
 <span data-ttu-id="361a9-126">SET @mycol = 'Name';</span><span class="sxs-lookup"><span data-stu-id="361a9-126">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="361a9-127">EXECUTE ('SELECT @mycol FROM Production.Product;');</span><span class="sxs-lookup"><span data-stu-id="361a9-127">EXECUTE ('SELECT @mycol FROM Production.Product;');</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="361a9-128">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="361a9-128">User Action</span></span>  
 <span data-ttu-id="361a9-129">Verifique se alguma das variáveis usadas em um script SQL foi declarada antes de ser usada em outro lugar no script.</span><span class="sxs-lookup"><span data-stu-id="361a9-129">Verify that any variables used in a SQL script are declared before being used elsewhere in the script.</span></span>  
  
 <span data-ttu-id="361a9-130">Reescreva o script de modo que ele não faça referência a variáveis na instrução EXECUTE que estejam declaradas fora dela.</span><span class="sxs-lookup"><span data-stu-id="361a9-130">Rewrite the script so that it does not reference variables in the EXECUTE statement that are declared outside of it.</span></span> <span data-ttu-id="361a9-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="361a9-131">For example:</span></span>  
  
 <span data-ttu-id="361a9-132">USE AdventureWorks2012;</span><span class="sxs-lookup"><span data-stu-id="361a9-132">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="361a9-133">GO</span><span class="sxs-lookup"><span data-stu-id="361a9-133">GO</span></span>  
  
 <span data-ttu-id="361a9-134">DECLARE @mycol nvarchar(20) ;</span><span class="sxs-lookup"><span data-stu-id="361a9-134">DECLARE @mycol nvarchar(20) ;</span></span>  
  
 <span data-ttu-id="361a9-135">SET @mycol = 'Name';</span><span class="sxs-lookup"><span data-stu-id="361a9-135">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="361a9-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;</span><span class="sxs-lookup"><span data-stu-id="361a9-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="361a9-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="361a9-137">See Also</span></span>  
 <span data-ttu-id="361a9-138">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="361a9-138">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="361a9-139">[Instruções SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="361a9-139">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 [<span data-ttu-id="361a9-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="361a9-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
  
