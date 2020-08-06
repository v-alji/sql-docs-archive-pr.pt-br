---
title: MSSQLSERVER_107 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 107 (Database Engine error)
ms.assetid: f33f514c-56aa-42e2-841b-e91244da90e2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b9388bbda6f00b1aafd02caee1b6a7b8387564f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576448"
---
# <a name="mssqlserver_107"></a><span data-ttu-id="33831-102">MSSQLSERVER_107</span><span class="sxs-lookup"><span data-stu-id="33831-102">MSSQLSERVER_107</span></span>
    
## <a name="details"></a><span data-ttu-id="33831-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="33831-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33831-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="33831-104">Product Name</span></span>|<span data-ttu-id="33831-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="33831-105">SQL Server</span></span>|  
|<span data-ttu-id="33831-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="33831-106">Event ID</span></span>|<span data-ttu-id="33831-107">107</span><span class="sxs-lookup"><span data-stu-id="33831-107">107</span></span>|  
|<span data-ttu-id="33831-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="33831-108">Event Source</span></span>|<span data-ttu-id="33831-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="33831-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="33831-110">Componente</span><span class="sxs-lookup"><span data-stu-id="33831-110">Component</span></span>|<span data-ttu-id="33831-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="33831-111">SQLEngine</span></span>|  
|<span data-ttu-id="33831-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="33831-112">Symbolic Name</span></span>|<span data-ttu-id="33831-113">P_NOCORRMATCH</span><span class="sxs-lookup"><span data-stu-id="33831-113">P_NOCORRMATCH</span></span>|  
|<span data-ttu-id="33831-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="33831-114">Message Text</span></span>|<span data-ttu-id="33831-115">O prefixo de coluna '%.\*ls' não coincide com um nome de tabela ou nome de alias usado na consulta.</span><span class="sxs-lookup"><span data-stu-id="33831-115">The column prefix '%.\*ls' does not match with a table name or alias name used in the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="33831-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="33831-116">Explanation</span></span>  
 <span data-ttu-id="33831-117">A lista de seleção da consulta contém um asterisco (\*) que é qualificado incorretamente com um prefixo de coluna.</span><span class="sxs-lookup"><span data-stu-id="33831-117">The select list of the query contains an asterisk (\*) that is incorrectly qualified with a column prefix.</span></span> <span data-ttu-id="33831-118">Esse erro pode ser retornado nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="33831-118">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="33831-119">O prefixo de coluna não corresponde a nenhum nome de tabela ou de alias usado na consulta.</span><span class="sxs-lookup"><span data-stu-id="33831-119">The column prefix does not correspond to any table or alias name used in the query.</span></span> <span data-ttu-id="33831-120">Por exemplo, a instrução a seguir utiliza um nome de alias (`T1`) como prefixo de coluna, mas o alias não está definido na cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="33831-120">For example, the following statement uses an alias name (`T1`) as a column prefix, but the alias is not defined in the FROM clause.</span></span>  
  
    ```  
    SELECT T1.* FROM dbo.ErrorLog;  
    ```  
  
-   <span data-ttu-id="33831-121">Um nome de tabela é especificado como prefixo de coluna quando um nome de alias da tabela é informado na cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="33831-121">A table name is specified as a column prefix when an alias name for the table is supplied in the FROM clause.</span></span> <span data-ttu-id="33831-122">Por exemplo, a instrução a seguir usa o nome de tabela `ErrorLog` como prefixo de coluna; entretanto, a tabela tem um alias (`T1`) definido na cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="33831-122">For example, the following statement uses the table name `ErrorLog` as the column prefix; however, the table has an alias (`T1`) defined in the FROM clause.</span></span>  
  
    ```  
    SELECT ErrorLog.* FROM dbo.ErrorLog AS T1;  
    ```  
  
     <span data-ttu-id="33831-123">Se um nome de alias tiver sido especificado para um nome de tabela na cláusula FROM, você só poderá usar o alias para prefixar colunas da tabela.</span><span class="sxs-lookup"><span data-stu-id="33831-123">If an alias has been provided for a table name in the FROM clause, you can only use the alias to prefix columns from the table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="33831-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="33831-124">User Action</span></span>  
 <span data-ttu-id="33831-125">Compare os prefixos de coluna com os nomes de tabela ou de alias especificados na cláusula FROM da consulta.</span><span class="sxs-lookup"><span data-stu-id="33831-125">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="33831-126">Por exemplo, as instruções acima podem ser corrigidas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="33831-126">For example, the statements above can be corrected as follows:</span></span>  
  
```  
SELECT T1.* FROM dbo.ErrorLog AS T1;  
```  
  
 <span data-ttu-id="33831-127">ou</span><span class="sxs-lookup"><span data-stu-id="33831-127">or</span></span>  
  
```  
SELECT ErrorLog.* FROM dbo.ErrorLog;  
```  
  
## <a name="see-also"></a><span data-ttu-id="33831-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="33831-128">See Also</span></span>  
 [<span data-ttu-id="33831-129">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="33831-129">MSSQLSERVER_4104</span></span>](mssqlserver-4104-database-engine-error.md)  
  
  
