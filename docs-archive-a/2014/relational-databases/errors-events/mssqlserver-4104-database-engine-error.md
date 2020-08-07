---
title: MSSQLSERVER_4104 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4104 (Database Engine error)
ms.assetid: 52dc32d8-97ad-4ef0-834d-2e68f215d007
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbbc28a3e15af6fdc8fd44633ccbdfc46e49149d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576435"
---
# <a name="mssqlserver_4104"></a><span data-ttu-id="26da0-102">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="26da0-102">MSSQLSERVER_4104</span></span>
    
## <a name="details"></a><span data-ttu-id="26da0-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="26da0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26da0-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="26da0-104">Product Name</span></span>|<span data-ttu-id="26da0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="26da0-105">SQL Server</span></span>|  
|<span data-ttu-id="26da0-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="26da0-106">Event ID</span></span>|<span data-ttu-id="26da0-107">4104</span><span class="sxs-lookup"><span data-stu-id="26da0-107">4104</span></span>|  
|<span data-ttu-id="26da0-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="26da0-108">Event Source</span></span>|<span data-ttu-id="26da0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="26da0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="26da0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="26da0-110">Component</span></span>|<span data-ttu-id="26da0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="26da0-111">SQLEngine</span></span>|  
|<span data-ttu-id="26da0-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="26da0-112">Symbolic Name</span></span>|<span data-ttu-id="26da0-113">ALG_MULTI_ID_BAD</span><span class="sxs-lookup"><span data-stu-id="26da0-113">ALG_MULTI_ID_BAD</span></span>|  
|<span data-ttu-id="26da0-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="26da0-114">Message Text</span></span>|<span data-ttu-id="26da0-115">Não foi possível associar o identificador de várias partes "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="26da0-115">The multi-part identifier "%.\*ls" could not be bound.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="26da0-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="26da0-116">Explanation</span></span>  
 <span data-ttu-id="26da0-117">O nome de uma entidade no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é referenciado como seu *identificador*.</span><span class="sxs-lookup"><span data-stu-id="26da0-117">The name of an entity in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is referred to as its *identifier*.</span></span> <span data-ttu-id="26da0-118">Use identificadores sempre que referenciar entidades, por exemplo, especificando nomes de coluna e tabela em uma consulta.</span><span class="sxs-lookup"><span data-stu-id="26da0-118">You use identifiers whenever you reference entities, for example, by specifying column and table names in a query.</span></span> <span data-ttu-id="26da0-119">Um identificador de várias partes contém um ou mais qualificadores como um prefixo do identificador.</span><span class="sxs-lookup"><span data-stu-id="26da0-119">A multi-part identifier contains one or more qualifiers as a prefix for the identifier.</span></span> <span data-ttu-id="26da0-120">Por exemplo, um identificador de tabela pode ter como prefixo qualificadores como o nome do banco de dados e o nome do esquema no qual a tabela está contida, ou um identificador de coluna pode ter como prefixo qualificadores como um nome ou alias de tabela.</span><span class="sxs-lookup"><span data-stu-id="26da0-120">For example, a table identifier may be prefixed with qualifiers such as the database name and schema name in which the table is contained, or a column identifier may be prefixed with qualifiers such as a table name or table alias.</span></span>  
  
 <span data-ttu-id="26da0-121">O erro 4104 indica que o identificador de várias partes especificado não pôde ser mapeado para uma entidade existente.</span><span class="sxs-lookup"><span data-stu-id="26da0-121">Error 4104 indicates that the specified multi-part identifier could not be mapped to an existing entity.</span></span> <span data-ttu-id="26da0-122">Esse erro pode ser retornado nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="26da0-122">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="26da0-123">O qualificador fornecido como prefixo para um nome de coluna não corresponde a nenhum nome de tabela ou alias usado na consulta.</span><span class="sxs-lookup"><span data-stu-id="26da0-123">The qualifier supplied as a prefix for a column name does not correspond to any table or alias name used in the query.</span></span>  
  
     <span data-ttu-id="26da0-124">Por exemplo, a instrução a seguir usa um alias de tabela (`Dept`) como prefixo de coluna, mas esse alias não é referenciado na cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="26da0-124">For example, the following statement uses a table alias (`Dept`) as a column prefix, but the table alias is not referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department;  
    ```  
  
     <span data-ttu-id="26da0-125">Nas instruções a seguir, um identificador de coluna de várias partes `TableB.KeyCol` é especificado na cláusula WHERE como parte de uma condição JOIN entre duas tabelas, no entanto, `TableB` não é referenciado explicitamente na consulta.</span><span class="sxs-lookup"><span data-stu-id="26da0-125">In the following statements, a multi-part column identifier `TableB.KeyCol` is specified in the WHERE clause as part of a JOIN condition between two tables, however, `TableB` is not explicitly referenced in the query.</span></span>  
  
    ```  
    DELETE FROM TableA WHERE TableA.KeyCol = TableB.KeyCol;  
    ```  
  
    ```  
    SELECT 'X' FROM TableA WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="26da0-126">Um nome de alias para a tabela é fornecido na cláusula FROM, mas o qualificador fornecido para uma coluna é o nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="26da0-126">An alias name for the table is supplied in the FROM clause, but the qualifier supplied for a column is the table name.</span></span> <span data-ttu-id="26da0-127">Por exemplo, a instrução a seguir usa o nome de tabela `Department` como prefixo de coluna; entretanto, a tabela tem um alias (`Dept`) referenciado na cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="26da0-127">For example, the following statement uses the table name `Department` as the column prefix; however, the table has an alias (`Dept`) referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department AS Dept;  
    ```  
  
     <span data-ttu-id="26da0-128">Quando um alias é usado, o nome de tabela não pode ser usado em nenhum outro lugar na instrução.</span><span class="sxs-lookup"><span data-stu-id="26da0-128">When an alias is used, the table name cannot be used elsewhere in the statement.</span></span>  
  
-   <span data-ttu-id="26da0-129">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode determinar se o identificador de várias partes se refere a uma coluna com um prefixo de tabela ou a uma propriedade de um tipo de dados CLR definido pelo usuário (UDT) com prefixo de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="26da0-129">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is unable to determine if the multi-part identifier refers to a column prefixed by a table or to a property of a CLR user-defined data type (UDT) prefixed by a column.</span></span> <span data-ttu-id="26da0-130">Isso ocorre porque as propriedades de colunas UDT são referenciadas com o uso do separador de ponto (.) entre o nome da coluna e o nome da propriedade, da mesma maneira que um nome de coluna recebe um nome de tabela como prefixo.</span><span class="sxs-lookup"><span data-stu-id="26da0-130">This happens because properties of UDT columns are referenced by using the period separator (.) between the column name and the property name in the same way that a column name is prefixed with a table name.</span></span> <span data-ttu-id="26da0-131">O exemplo a seguir cria duas tabelas, `a` e `b`.</span><span class="sxs-lookup"><span data-stu-id="26da0-131">The following example creates two tables, `a` and `b`.</span></span> <span data-ttu-id="26da0-132">A tabela `b` contém a coluna `a`, que usa um `dbo.myudt2` CLR UDT como seu tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="26da0-132">Table `b` contains column `a`, which uses a CLR UDT `dbo.myudt2` as its data type.</span></span> <span data-ttu-id="26da0-133">A SELECT instrução contém um identificador de várias partes `a.c2`.</span><span class="sxs-lookup"><span data-stu-id="26da0-133">The SELECT statement contains a multi-part identifier `a.c2`.</span></span>  
  
    ```  
    CREATE TABLE a (c2 int);   
    GO  
    ```  
  
    ```  
    CREATE TABLE b (a dbo.myudt2);   
    GO  
    ```  
  
    ```  
    SELECT a.c2 FROM a, b;   
    ```  
  
     <span data-ttu-id="26da0-134">Pressupondo que UDT `myudt2` não tenha uma propriedade denominada `c2`, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não poderá determinar se o identificador se `a.c2`refere a uma coluna `c2` na tabela `a` ou à coluna `a`, propriedade `c2` na tabela `b`.</span><span class="sxs-lookup"><span data-stu-id="26da0-134">Assuming that the UDT `myudt2` does not have a property named `c2`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot determine whether identifier `a.c2`refers to column `c2` in table `a` or to the column `a`, property `c2` in table `b`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="26da0-135">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="26da0-135">User Action</span></span>  
  
-   <span data-ttu-id="26da0-136">Compare os prefixos de coluna com os nomes de tabela ou de alias especificados na cláusula FROM da consulta.</span><span class="sxs-lookup"><span data-stu-id="26da0-136">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="26da0-137">Se um alias for definido para um nome de tabela na cláusula FROM, você só poderá usar esse alias como um qualificador para colunas associadas à tabela.</span><span class="sxs-lookup"><span data-stu-id="26da0-137">If an alias is defined for a table name in the FROM clause, you can only use the alias as a qualifier for columns associated with that table.</span></span>  
  
     <span data-ttu-id="26da0-138">As instruções acima que referenciam a tabela `HumanResources.Department` podem ser corrigidas da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="26da0-138">The statements above that reference the `HumanResources.Department` table can be corrected as follows:</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department AS Dept;  
    GO  
    ```  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department;  
    GO  
    ```  
  
-   <span data-ttu-id="26da0-139">Verifique se todas as tabelas são especificadas na consulta e se são condições JOIN entre tabelas são especificadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="26da0-139">Ensure that all tables are specified in the query and that the JOIN conditions between tables are specified correctly.</span></span> <span data-ttu-id="26da0-140">A instrução DELETE acima pode ser corrigida da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="26da0-140">The DELETE statement above can be corrected as follows:</span></span>  
  
    ```  
    DELETE FROM dbo.TableA  
    WHERE TableA.KeyCol = (SELECT TableB.KeyCol   
                            FROM TableB   
                            WHERE TableA.KeyCol = TableB.KeyCol);  
    GO  
    ```  
  
     <span data-ttu-id="26da0-141">A instrução SELECT acima para `TableA` pode ser corrigida da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="26da0-141">The SELECT statement above for `TableA` can be corrected as follows:</span></span>  
  
    ```  
    SELECT 'X' FROM TableA, TableB WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
     <span data-ttu-id="26da0-142">ou</span><span class="sxs-lookup"><span data-stu-id="26da0-142">or</span></span>  
  
    ```  
    SELECT 'X' FROM TableA INNER JOIN TableB ON TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="26da0-143">Use nomes exclusivos, claramente definidos como identificadores.</span><span class="sxs-lookup"><span data-stu-id="26da0-143">Use unique, clearly defined names for identifiers.</span></span> <span data-ttu-id="26da0-144">Isso facilitará a leitura e a manutenção do código e também minimizará o risco de referências ambíguas para várias entidades.</span><span class="sxs-lookup"><span data-stu-id="26da0-144">Doing so makes your code easier to read and maintain, and it also minimizes the risk of ambiguous references to multiple entities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26da0-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="26da0-145">See Also</span></span>  
 <span data-ttu-id="26da0-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="26da0-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span></span>  
 [<span data-ttu-id="26da0-147">Identificadores de banco de dados</span><span class="sxs-lookup"><span data-stu-id="26da0-147">Database Identifiers</span></span>](../databases/database-identifiers.md)  
  
  
