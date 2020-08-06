---
title: MSSQLSERVER_1505 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1505 (Database Engine error)
ms.assetid: ef4df75d-0f36-4c8b-b36c-e427f65f91ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 74c152404cf2d3710bbe98b29da7a96d86f58859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679979"
---
# <a name="mssqlserver_1505"></a><span data-ttu-id="aeef6-102">MSSQLSERVER_1505</span><span class="sxs-lookup"><span data-stu-id="aeef6-102">MSSQLSERVER_1505</span></span>
    
## <a name="details"></a><span data-ttu-id="aeef6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="aeef6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aeef6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="aeef6-104">Product Name</span></span>|<span data-ttu-id="aeef6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aeef6-105">SQL Server</span></span>|  
|<span data-ttu-id="aeef6-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="aeef6-106">Event ID</span></span>|<span data-ttu-id="aeef6-107">1505</span><span class="sxs-lookup"><span data-stu-id="aeef6-107">1505</span></span>|  
|<span data-ttu-id="aeef6-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="aeef6-108">Event Source</span></span>|<span data-ttu-id="aeef6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aeef6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aeef6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="aeef6-110">Component</span></span>|<span data-ttu-id="aeef6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aeef6-111">SQLEngine</span></span>|  
|<span data-ttu-id="aeef6-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="aeef6-112">Symbolic Name</span></span>|<span data-ttu-id="aeef6-113">DUP_KEY</span><span class="sxs-lookup"><span data-stu-id="aeef6-113">DUP_KEY</span></span>|  
|<span data-ttu-id="aeef6-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="aeef6-114">Message Text</span></span>|<span data-ttu-id="aeef6-115">A instrução CREATE UNIQUE INDEX foi encerrada porque foi encontrada uma chave duplicada para o nome de objeto '%.\*ls' e para o nome de índice '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="aeef6-115">CREATE UNIQUE INDEX terminated because a duplicate key was found for object name '%.\*ls' and index name '%.\*ls'.</span></span>  <span data-ttu-id="aeef6-116">O valor da chave duplicada é %ls.</span><span class="sxs-lookup"><span data-stu-id="aeef6-116">The duplicate key value is %ls.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aeef6-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="aeef6-117">Explanation</span></span>  
 <span data-ttu-id="aeef6-118">Esse erro ocorre quando você tenta criar um índice exclusivo e mais de uma linha da tabela contém o valor duplicado especificado.</span><span class="sxs-lookup"><span data-stu-id="aeef6-118">This error occurs when you attempt to create a unique index and more than one row in the table contains the specified duplicate value.</span></span> <span data-ttu-id="aeef6-119">Um índice exclusivo é criado quando você cria um índice e especifica a palavra-chave UNIQUE ou quando cria uma restrição UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="aeef6-119">A unique index is created when you create an index and specify the UNIQUE keyword, or when you create a UNIQUE constraint.</span></span> <span data-ttu-id="aeef6-120">A tabela não pode conter linhas que tenham valores duplicados nas colunas definidas no índice ou na restrição.</span><span class="sxs-lookup"><span data-stu-id="aeef6-120">The table cannot contain any rows that have duplicate values in the columns defined in the index or constraint.</span></span>  
  
 <span data-ttu-id="aeef6-121">Considere os dados da seguinte tabela **Employee**:</span><span class="sxs-lookup"><span data-stu-id="aeef6-121">Consider the data in the following **Employee** table:</span></span>  
  
|<span data-ttu-id="aeef6-122">LastName</span><span class="sxs-lookup"><span data-stu-id="aeef6-122">LastName</span></span>|<span data-ttu-id="aeef6-123">Nome</span><span class="sxs-lookup"><span data-stu-id="aeef6-123">FirstName</span></span>|<span data-ttu-id="aeef6-124">JobTitle</span><span class="sxs-lookup"><span data-stu-id="aeef6-124">JobTitle</span></span>|<span data-ttu-id="aeef6-125">HireDate</span><span class="sxs-lookup"><span data-stu-id="aeef6-125">HireDate</span></span>|  
|--------------|---------------|--------------|--------------|  
|<span data-ttu-id="aeef6-126">Walters</span><span class="sxs-lookup"><span data-stu-id="aeef6-126">Walters</span></span>|<span data-ttu-id="aeef6-127">Rob</span><span class="sxs-lookup"><span data-stu-id="aeef6-127">Rob</span></span>|<span data-ttu-id="aeef6-128">Designer de ferramentas sênior</span><span class="sxs-lookup"><span data-stu-id="aeef6-128">Senior Tool Designer</span></span>|<span data-ttu-id="aeef6-129">2004-11-19</span><span class="sxs-lookup"><span data-stu-id="aeef6-129">2004-11-19</span></span>|  
|<span data-ttu-id="aeef6-130">Brown</span><span class="sxs-lookup"><span data-stu-id="aeef6-130">Brown</span></span>|<span data-ttu-id="aeef6-131">Kevin</span><span class="sxs-lookup"><span data-stu-id="aeef6-131">Kevin</span></span>|<span data-ttu-id="aeef6-132">Assistente de marketing</span><span class="sxs-lookup"><span data-stu-id="aeef6-132">Marketing Assistant</span></span>|<span data-ttu-id="aeef6-133">NULO</span><span class="sxs-lookup"><span data-stu-id="aeef6-133">NULL</span></span>|  
|<span data-ttu-id="aeef6-134">Brown</span><span class="sxs-lookup"><span data-stu-id="aeef6-134">Brown</span></span>|<span data-ttu-id="aeef6-135">Jo</span><span class="sxs-lookup"><span data-stu-id="aeef6-135">Jo</span></span>|<span data-ttu-id="aeef6-136">Engenheiro de design</span><span class="sxs-lookup"><span data-stu-id="aeef6-136">Design Engineer</span></span>|<span data-ttu-id="aeef6-137">NULO</span><span class="sxs-lookup"><span data-stu-id="aeef6-137">NULL</span></span>|  
|<span data-ttu-id="aeef6-138">Walters</span><span class="sxs-lookup"><span data-stu-id="aeef6-138">Walters</span></span>|<span data-ttu-id="aeef6-139">Rob</span><span class="sxs-lookup"><span data-stu-id="aeef6-139">Rob</span></span>|<span data-ttu-id="aeef6-140">Designer de ferramentas</span><span class="sxs-lookup"><span data-stu-id="aeef6-140">Tool Designer</span></span>|<span data-ttu-id="aeef6-141">2001-08-09</span><span class="sxs-lookup"><span data-stu-id="aeef6-141">2001-08-09</span></span>|  
  
 <span data-ttu-id="aeef6-142">Não é possível criar um índice exclusivo com as combinações de coluna **LastName** ou **LastName** e **FirstName** devido aos valores duplicados nas linhas.</span><span class="sxs-lookup"><span data-stu-id="aeef6-142">A unique index can not be created on the column combinations **LastName** or **LastName**, **FirstName** because of duplicate values in the rows.</span></span>  
  
 <span data-ttu-id="aeef6-143">Menos óbvia é a possibilidade de ocorrer uma violação de exclusividade na coluna **HireDate**.</span><span class="sxs-lookup"><span data-stu-id="aeef6-143">Less obvious is the potential for a uniqueness violation in the **HireDate** column.</span></span> <span data-ttu-id="aeef6-144">Para fins de indexação, valores NULL são comparados como iguais.</span><span class="sxs-lookup"><span data-stu-id="aeef6-144">For indexing purposes, NULL values compare as equal.</span></span> <span data-ttu-id="aeef6-145">Portanto, você não poderá criar um índice exclusivo ou uma restrição exclusiva se os valores de chave forem NULL em mais de uma linha.</span><span class="sxs-lookup"><span data-stu-id="aeef6-145">Therefore, you cannot create a unique index or constraint if the key values are NULL in more than one row.</span></span> <span data-ttu-id="aeef6-146">Considerando os dados acima, não é possível criar um índice exclusivo com base nas combinações de coluna **HireDate** ou **LastName** e **HireDate**.</span><span class="sxs-lookup"><span data-stu-id="aeef6-146">Given the data above, a unique index cannot be created on the column combinations **HireDate** or **LastName**, **HireDate**.</span></span>  
  
 <span data-ttu-id="aeef6-147">A mensagem de erro 1505 retorna a primeira linha que viola a restrição de exclusividade.</span><span class="sxs-lookup"><span data-stu-id="aeef6-147">Error message 1505 returns the first row that violates the uniqueness constraint.</span></span> <span data-ttu-id="aeef6-148">Pode haver outras linhas duplicadas na tabela.</span><span class="sxs-lookup"><span data-stu-id="aeef6-148">There may be other duplicate rows in the table.</span></span> <span data-ttu-id="aeef6-149">Para encontrar todas as linhas duplicadas, consulte a tabela especificada e use as cláusulas GROUP BY e HAVING para reportar essas linhas.</span><span class="sxs-lookup"><span data-stu-id="aeef6-149">To find all duplicate rows, query the specified table and use the GROUP BY and HAVING clauses to report the duplicate rows.</span></span> <span data-ttu-id="aeef6-150">Por exemplo, a consulta a seguir retorna as linhas da tabela **Employee** que têm nomes e sobrenomes duplicados.</span><span class="sxs-lookup"><span data-stu-id="aeef6-150">For example, the following query returns the rows in the **Employee** table that have duplicate first and last names.</span></span>  
  
 <span data-ttu-id="aeef6-151">Selecione LastName, FirstName, Count ( \* ) de dbo. GRUPO de funcionários por LastName, FirstName com Count ( \* ) > 1;</span><span class="sxs-lookup"><span data-stu-id="aeef6-151">SELECT LastName, FirstName, count(\*) FROM dbo.Employee GROUP BY LastName, FirstName HAVING count(\*) > 1;</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aeef6-152">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="aeef6-152">User Action</span></span>  
 <span data-ttu-id="aeef6-153">Considere as soluções descritas a seguir.</span><span class="sxs-lookup"><span data-stu-id="aeef6-153">Consider the following solutions.</span></span>  
  
-   <span data-ttu-id="aeef6-154">Adicione ou remova colunas na definição do índice ou da restrição para criar uma composição exclusiva.</span><span class="sxs-lookup"><span data-stu-id="aeef6-154">Add or remove columns in the index or constraint definition to create a unique composite.</span></span> <span data-ttu-id="aeef6-155">No exemplo anterior, adicionar uma coluna **MiddleName** à definição do índice ou da restrição pode resolver o problema de duplicação.</span><span class="sxs-lookup"><span data-stu-id="aeef6-155">In the previous example, adding a **MiddleName** column to the index or constraint definition might resolve the duplication problem.</span></span>  
  
-   <span data-ttu-id="aeef6-156">Selecione colunas definidas como NOT NULL quando escolher colunas para um índice exclusivo ou para uma restrição exclusiva.</span><span class="sxs-lookup"><span data-stu-id="aeef6-156">Select columns that are defined as NOT NULL when you choose columns for a unique index or constraint.</span></span> <span data-ttu-id="aeef6-157">Isso elimina a possibilidade de ocorrer uma violação de exclusividade gerada quando mais de uma linha contiver NULL nos valores de chave.</span><span class="sxs-lookup"><span data-stu-id="aeef6-157">This eliminates the possibility of a uniqueness violation caused when more than one row contains NULL in the key values.</span></span>  
  
-   <span data-ttu-id="aeef6-158">Se os valores duplicados forem o resultado de erros de entrada de dados, corrija os dados manualmente e, em seguida, crie o índice ou a restrição.</span><span class="sxs-lookup"><span data-stu-id="aeef6-158">If the duplicate values are the result of data entry errors, manually correct the data and then create the index or constraint.</span></span> <span data-ttu-id="aeef6-159">Para obter informações sobre como remover linhas duplicadas de uma tabela, veja o artigo 139444 da base de dados de conhecimento: [Como remover linhas duplicadas de uma tabela no SQL Server](https://support.microsoft.com/kb/139444).</span><span class="sxs-lookup"><span data-stu-id="aeef6-159">For information about removing duplicate rows in a table, see Knowledge Base article 139444: [How to remove duplicate rows from a table in SQL Server](https://support.microsoft.com/kb/139444).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeef6-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aeef6-160">See Also</span></span>  
 <span data-ttu-id="aeef6-161">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aeef6-161">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="aeef6-162">[Criar índices exclusivos](../indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="aeef6-162">[Create Unique Indexes](../indexes/indexes.md) </span></span>  
 [<span data-ttu-id="aeef6-163">Criar restrições exclusivas</span><span class="sxs-lookup"><span data-stu-id="aeef6-163">Create Unique Constraints</span></span>](../tables/create-unique-constraints.md)  
  
  
