---
title: Sinônimos (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synonyms [SQL Server], about synonyms
ms.assetid: 6210e1d5-075f-47e4-ac8d-f84bcf26fbc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3494f4f5b13c422efb8e2a39597e131c10d81ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573881"
---
# <a name="synonyms-database-engine"></a><span data-ttu-id="05621-102">Sinônimos (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="05621-102">Synonyms (Database Engine)</span></span>
  <span data-ttu-id="05621-103">Um sinônimo é um objeto de banco de dados que atende aos seguintes propósitos:</span><span class="sxs-lookup"><span data-stu-id="05621-103">A synonym is a database object that serves the following purposes:</span></span>  
  
-   <span data-ttu-id="05621-104">Fornece um nome alternativo para outro objeto do banco de dados referido como o objeto base que pode existir em um servidor local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="05621-104">Provides an alternative name for another database object, referred to as the base object, that can exist on a local or remote server.</span></span>  
  
-   <span data-ttu-id="05621-105">Fornece uma camada de abstração que protege um aplicativo cliente de alterações feitas no nome ou local do objeto base.</span><span class="sxs-lookup"><span data-stu-id="05621-105">Provides a layer of abstraction that protects a client application from changes made to the name or location of the base object.</span></span>  
  
 <span data-ttu-id="05621-106">Por exemplo, considere a tabela **Employee** do [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)]localizada em um servidor denominado **Server1**.</span><span class="sxs-lookup"><span data-stu-id="05621-106">For example, consider the **Employee** table of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)], located on a server named **Server1**.</span></span> <span data-ttu-id="05621-107">Para fazer referência a esta tabela em outro servidor, **Server2**, um aplicativo precisa usar o nome de quatro partes **Server1.AdventureWorks.Person.Employee**.</span><span class="sxs-lookup"><span data-stu-id="05621-107">To reference this table from another server, **Server2**, a client application would have to use the four-part name **Server1.AdventureWorks.Person.Employee**.</span></span> <span data-ttu-id="05621-108">Além disso, se o local da tabela for alterado, por exemplo, para outro servidor, o aplicativo cliente precisará ser modificado para refletir essa alteração.</span><span class="sxs-lookup"><span data-stu-id="05621-108">Also, if the location of the table were to change, for example, to another server, the client application would have to be modified to reflect that change.</span></span>  
  
 <span data-ttu-id="05621-109">Para resolver os dois problemas, é possível criar um sinônimo, **EmpTable**, no **Server2** para a tabela **Employee** no **Server1**.</span><span class="sxs-lookup"><span data-stu-id="05621-109">To address both these issues, you can create a synonym, **EmpTable**, on **Server2** for the **Employee** table on **Server1**.</span></span> <span data-ttu-id="05621-110">Agora, o aplicativo cliente precisa usar apenas o nome de uma única parte, **EmpTable**, para fazer referência à tabela **Employee** .</span><span class="sxs-lookup"><span data-stu-id="05621-110">Now, the client application only has to use the single-part name, **EmpTable**, to reference the **Employee** table.</span></span> <span data-ttu-id="05621-111">Além disso, se o local da tabela **Employee** for alterado, você precisará modificar o sinônimo, **EmpTable**, para apontar para o novo local da tabela **Employee** .</span><span class="sxs-lookup"><span data-stu-id="05621-111">Also, if the location of the **Employee** table changes, you will have to modify the synonym, **EmpTable**, to point to the new location of the **Employee** table.</span></span> <span data-ttu-id="05621-112">Como não existe nenhuma instrução ALTER SYNONYM, você precisa primeiro remover o sinônimo, **EmpTable**, e criá-lo novamente com o mesmo nome, mas apontá-lo para o novo local **Employee**.</span><span class="sxs-lookup"><span data-stu-id="05621-112">Because there is no ALTER SYNONYM statement, you first have to drop the synonym, **EmpTable**, and then re-create the synonym with the same name, but point the synonym to the new location of **Employee**.</span></span>  
  
 <span data-ttu-id="05621-113">Um sinônimo pertence a um esquema e, como outros objetos de um esquema, seu nome precisa ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="05621-113">A synonym belongs to a schema, and like other objects in a schema, the name of a synonym must be unique.</span></span> <span data-ttu-id="05621-114">É possível criar sinônimos para os seguintes objetos de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="05621-114">You can create synonyms for the following database objects:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05621-115">Procedimento armazenado de assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="05621-115">Assembly (CLR) stored procedure</span></span>|<span data-ttu-id="05621-116">Função com valor de tabela de assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="05621-116">Assembly (CLR) table-valued function</span></span>|  
|<span data-ttu-id="05621-117">Função escalar de assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="05621-117">Assembly (CLR) scalar function</span></span>|<span data-ttu-id="05621-118">Funções de agregação de assembly (CLR)</span><span class="sxs-lookup"><span data-stu-id="05621-118">Assembly (CLR) aggregate functions</span></span>|  
|<span data-ttu-id="05621-119">Procedimento de filtro de replicação</span><span class="sxs-lookup"><span data-stu-id="05621-119">Replication-filter-procedure</span></span>|<span data-ttu-id="05621-120">Procedimento armazenado estendido</span><span class="sxs-lookup"><span data-stu-id="05621-120">Extended stored procedure</span></span>|  
|<span data-ttu-id="05621-121">Função SQL escalar</span><span class="sxs-lookup"><span data-stu-id="05621-121">SQL scalar function</span></span>|<span data-ttu-id="05621-122">Função SQL com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="05621-122">SQL table-valued function</span></span>|  
|<span data-ttu-id="05621-123">Função SQL com valor de tabela embutida</span><span class="sxs-lookup"><span data-stu-id="05621-123">SQL inline-tabled-valued function</span></span>|<span data-ttu-id="05621-124">Procedimento armazenado SQL</span><span class="sxs-lookup"><span data-stu-id="05621-124">SQL stored procedure</span></span>|  
|<span data-ttu-id="05621-125">Exibir</span><span class="sxs-lookup"><span data-stu-id="05621-125">View</span></span>|<span data-ttu-id="05621-126">Tabela<sup>1</sup> (definida pelo usuário)</span><span class="sxs-lookup"><span data-stu-id="05621-126">Table<sup>1</sup> (User-defined)</span></span>|  
  
 <span data-ttu-id="05621-127"><sup>1</sup> inclui tabelas temporárias locais e globais</span><span class="sxs-lookup"><span data-stu-id="05621-127"><sup>1</sup> Includes local and global temporary tables</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05621-128">Não há suporte para nomes de quatro partes para objetos base de função.</span><span class="sxs-lookup"><span data-stu-id="05621-128">Four-part names for function base objects are not supported.</span></span>  
  
 <span data-ttu-id="05621-129">Um sinônimo não pode ser o objeto base de outro sinônimo e um sinônimo não pode fazer referência a uma função de agregação definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="05621-129">A synonym cannot be the base object for another synonym, and a synonym cannot reference a user-defined aggregate function.</span></span>  
  
 <span data-ttu-id="05621-130">A associação entre um sinônimo e seu objeto base é feita apenas pelo nome.</span><span class="sxs-lookup"><span data-stu-id="05621-130">The binding between a synonym and its base object is by name only.</span></span> <span data-ttu-id="05621-131">Toda verificação de existência, tipo e permissões no objeto base é adiada até o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="05621-131">All existence, type, and permissions checking on the base object is deferred until run time.</span></span> <span data-ttu-id="05621-132">Portanto o objeto base pode ser modificado, descartado ou descartado e substituído por outro objeto que tenha o mesmo nome que o objeto base original.</span><span class="sxs-lookup"><span data-stu-id="05621-132">Therefore, the base object can be modified, dropped, or dropped and replaced by another object that has the same name as the original base object.</span></span> <span data-ttu-id="05621-133">Por exemplo, considere um sinônimo, **MyContacts**, que faz referência à tabela **Person.Contact** no [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05621-133">For example, consider a synonym, **MyContacts**, that references the **Person.Contact** table in [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)].</span></span> <span data-ttu-id="05621-134">Se a tabela **Contact** for removida e substituída por uma exibição nomeada **Person.Contact**, **MyContacts** agora fará referência à exibição **Person.Contact** .</span><span class="sxs-lookup"><span data-stu-id="05621-134">If the **Contact** table is dropped and replaced by a view named **Person.Contact**, **MyContacts** now references the **Person.Contact** view.</span></span>  
  
 <span data-ttu-id="05621-135">Referências a sinônimos não são associadas a esquemas.</span><span class="sxs-lookup"><span data-stu-id="05621-135">References to synonyms are not schema-bound.</span></span> <span data-ttu-id="05621-136">Portanto, um sinônimo pode ser descartado a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="05621-136">Therefore, a synonym can be dropped at any time.</span></span> <span data-ttu-id="05621-137">No entanto, ao descartar um sinônimo, você corre o risco de deixar referências pendentes ao sinônimo descartado.</span><span class="sxs-lookup"><span data-stu-id="05621-137">However, by dropping a synonym, you run the risk of leaving dangling references to the synonym that was dropped.</span></span> <span data-ttu-id="05621-138">Essas referências serão localizadas apenas em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="05621-138">These references will only be found at run time.</span></span>  
  
## <a name="synonyms-and-schemas"></a><span data-ttu-id="05621-139">Sinônimos e esquemas</span><span class="sxs-lookup"><span data-stu-id="05621-139">Synonyms and Schemas</span></span>  
 <span data-ttu-id="05621-140">Se você tiver um esquema padrão do qual você não é o proprietário e desejar criar um sinônimo, deverá qualificar o nome do sinônimo com o nome de um esquema que seja de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="05621-140">If you have a default schema that you do not own and want to create a synonym, you must qualify the synonym name with the name of a schema that you do own.</span></span> <span data-ttu-id="05621-141">Por exemplo, se você possuir um esquema **x**, mas **y** for seu esquema padrão e você usar a instrução CREATE SYNONYM, deverá prefixar o nome do sinônimo com o esquema **x**, em vez de nomear o sinônimo usando um nome de uma única parte.</span><span class="sxs-lookup"><span data-stu-id="05621-141">For example, if you own a schema **x**, but **y** is your default schema and you use the CREATE SYNONYM statement, you must prefix the name of the synonym with the schema **x**, instead of naming the synonym by using a single-part name.</span></span> <span data-ttu-id="05621-142">Para obter mais informações sobre como criar sinônimos, veja [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="05621-142">For more information about how to create synonyms, see [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql).</span></span>  
  
## <a name="granting-permissions-on-a-synonym"></a><span data-ttu-id="05621-143">Concedendo permissões em um sinônimo</span><span class="sxs-lookup"><span data-stu-id="05621-143">Granting Permissions on a Synonym</span></span>  
 <span data-ttu-id="05621-144">Apenas os proprietários de sinônimos, membros de **db_owner**, ou membros de **db_ddladmin** podem conceder permissão em um sinônimo.</span><span class="sxs-lookup"><span data-stu-id="05621-144">Only synonym owners, members of **db_owner**, or members of **db_ddladmin** can grant permission on a synonym.</span></span>  
  
 <span data-ttu-id="05621-145">É possível emitir GRANT, DENY, REVOKE de todas ou de qualquer uma das seguintes permissões em um sinônimo:</span><span class="sxs-lookup"><span data-stu-id="05621-145">You can GRANT, DENY, REVOKE all or any of the following permissions on a synonym:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05621-146">CONTROL</span><span class="sxs-lookup"><span data-stu-id="05621-146">CONTROL</span></span>|<span data-ttu-id="05621-147">Delete (excluir)</span><span class="sxs-lookup"><span data-stu-id="05621-147">DELETE</span></span>|  
|<span data-ttu-id="05621-148">Execute</span><span class="sxs-lookup"><span data-stu-id="05621-148">EXECUTE</span></span>|<span data-ttu-id="05621-149">INSERT</span><span class="sxs-lookup"><span data-stu-id="05621-149">INSERT</span></span>|  
|<span data-ttu-id="05621-150">SELECT</span><span class="sxs-lookup"><span data-stu-id="05621-150">SELECT</span></span>|<span data-ttu-id="05621-151">TAKE OWNERSHIP</span><span class="sxs-lookup"><span data-stu-id="05621-151">TAKE OWNERSHIP</span></span>|  
|<span data-ttu-id="05621-152">UPDATE</span><span class="sxs-lookup"><span data-stu-id="05621-152">UPDATE</span></span>|<span data-ttu-id="05621-153">VIEW DEFINITION</span><span class="sxs-lookup"><span data-stu-id="05621-153">VIEW DEFINITION</span></span>|  
  
## <a name="using-synonyms"></a><span data-ttu-id="05621-154">Usando sinônimos</span><span class="sxs-lookup"><span data-stu-id="05621-154">Using Synonyms</span></span>  
 <span data-ttu-id="05621-155">É possível usar sinônimos em lugar do objeto base referenciado em várias instruções SQL e contextos de expressão.</span><span class="sxs-lookup"><span data-stu-id="05621-155">You can use synonyms in place of their referenced base object in several SQL statements and expression contexts.</span></span> <span data-ttu-id="05621-156">A tabela a seguir contém uma lista dessas instruções e contextos de expressão:</span><span class="sxs-lookup"><span data-stu-id="05621-156">The following table contains a list of these statements and expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05621-157">SELECT</span><span class="sxs-lookup"><span data-stu-id="05621-157">SELECT</span></span>|<span data-ttu-id="05621-158">INSERT</span><span class="sxs-lookup"><span data-stu-id="05621-158">INSERT</span></span>|  
|<span data-ttu-id="05621-159">UPDATE</span><span class="sxs-lookup"><span data-stu-id="05621-159">UPDATE</span></span>|<span data-ttu-id="05621-160">Delete (excluir)</span><span class="sxs-lookup"><span data-stu-id="05621-160">DELETE</span></span>|  
|<span data-ttu-id="05621-161">Execute</span><span class="sxs-lookup"><span data-stu-id="05621-161">EXECUTE</span></span>|<span data-ttu-id="05621-162">Subseleções</span><span class="sxs-lookup"><span data-stu-id="05621-162">Sub-selects</span></span>|  
  
 <span data-ttu-id="05621-163">Quando você está trabalhando com sinônimos nos contextos declarados anteriormente, o objeto base é afetado.</span><span class="sxs-lookup"><span data-stu-id="05621-163">When you are working with synonyms in the contexts previously stated, the base object is affected.</span></span> <span data-ttu-id="05621-164">Por exemplo, se um sinônimo fizer referência a um objeto base que está em uma tabela e você inserir uma linha no sinônimo, na verdade você estará inserindo uma linha na tabela referida.</span><span class="sxs-lookup"><span data-stu-id="05621-164">For example, if a synonym references a base object that is a table and you insert a row into the synonym, you are actually inserting a row into the referenced table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05621-165">Não é possível fazer referência a um sinônimo localizado em um servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="05621-165">You cannot reference a synonym that is located on a linked server.</span></span>  
  
 <span data-ttu-id="05621-166">É possível usar um sinônimo como o parâmetro da função OBJECT_ID. No entanto, a função retorna a ID do objeto do sinônimo, não o objeto base.</span><span class="sxs-lookup"><span data-stu-id="05621-166">You can use a synonym as the parameter for the OBJECT_ID function; however, the function returns the object ID of the synonym, not the base object.</span></span>  
  
 <span data-ttu-id="05621-167">Não é possível fazer referência a um sinônimo em uma instrução DDL.</span><span class="sxs-lookup"><span data-stu-id="05621-167">You cannot reference a synonym in a DDL statement.</span></span> <span data-ttu-id="05621-168">Por exemplo, as instruções a seguir que fazem referência a um sinônimo denominado `dbo.MyProduct`geram erros:</span><span class="sxs-lookup"><span data-stu-id="05621-168">For example, the following statements, which reference a synonym named `dbo.MyProduct`, generate errors:</span></span>  
  
```  
ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null;  
EXEC ('ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null');  
```  
  
 <span data-ttu-id="05621-169">As instruções de permissão a seguir são associadas apenas ao sinônimo e não ao objeto base:</span><span class="sxs-lookup"><span data-stu-id="05621-169">The following permission statements are associated only with the synonym and not the base object:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05621-170">GRANT</span><span class="sxs-lookup"><span data-stu-id="05621-170">GRANT</span></span>|<span data-ttu-id="05621-171">NEGAR</span><span class="sxs-lookup"><span data-stu-id="05621-171">DENY</span></span>|  
|<span data-ttu-id="05621-172">REVOKE</span><span class="sxs-lookup"><span data-stu-id="05621-172">REVOKE</span></span>||  
  
 <span data-ttu-id="05621-173">Sinônimos não são associados a esquemas e, portanto, não podem ser referidos pelos seguintes contextos de expressão associados a esquemas:</span><span class="sxs-lookup"><span data-stu-id="05621-173">Synonyms are not schema-bound and, therefore, cannot be referenced by the following schema-bound expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05621-174">Restrições CHECK</span><span class="sxs-lookup"><span data-stu-id="05621-174">CHECK constraints</span></span>|<span data-ttu-id="05621-175">Colunas computadas</span><span class="sxs-lookup"><span data-stu-id="05621-175">Computed columns</span></span>|  
|<span data-ttu-id="05621-176">Expressões padrão</span><span class="sxs-lookup"><span data-stu-id="05621-176">Default expressions</span></span>|<span data-ttu-id="05621-177">Expressões de regra</span><span class="sxs-lookup"><span data-stu-id="05621-177">Rule expressions</span></span>|  
|<span data-ttu-id="05621-178">Exibições associadas a esquema</span><span class="sxs-lookup"><span data-stu-id="05621-178">Schema-bound views</span></span>|<span data-ttu-id="05621-179">Funções associadas a esquema</span><span class="sxs-lookup"><span data-stu-id="05621-179">Schema-bound functions</span></span>|  
  
 <span data-ttu-id="05621-180">Para obter mais informações sobre funções associadas a esquema, veja [Criar funções definidas pelo usuário &#40;Mecanismo de Banco de Dados&#41;](../user-defined-functions/create-user-defined-functions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="05621-180">For more information about schema-bound functions, see [Create User-defined Functions &#40;Database Engine&#41;](../user-defined-functions/create-user-defined-functions-database-engine.md).</span></span>  
  
## <a name="getting-information-about-synonyms"></a><span data-ttu-id="05621-181">Obtendo informações sobre sinônimos</span><span class="sxs-lookup"><span data-stu-id="05621-181">Getting Information About Synonyms</span></span>  
 <span data-ttu-id="05621-182">A exibição do catálogo sys.synonyms contém uma entrada para cada sinônimo em um determinado banco de dados.</span><span class="sxs-lookup"><span data-stu-id="05621-182">The sys.synonyms catalog view contains an entry for each synonym in a given database.</span></span> <span data-ttu-id="05621-183">Essa exibição do catálogo expõe metadados de sinônimos, como o nome do sinônimo e o nome do objeto base.</span><span class="sxs-lookup"><span data-stu-id="05621-183">This catalog view exposes synonym metadata such as the name of the synonym and the name of the base object.</span></span> <span data-ttu-id="05621-184">Para obter mais informações sobre a `sys.synonyms` exibição de catálogo, consulte [Sys. synonyms &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="05621-184">For more information about the `sys.synonyms` catalog view, see [sys.synonyms &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span></span>  
  
 <span data-ttu-id="05621-185">Usando propriedades estendidas é possível adicionar texto descritivo ou instrucional, máscaras de entrada e regras de formatação como propriedades de um sinônimo.</span><span class="sxs-lookup"><span data-stu-id="05621-185">By using extended properties, you can add descriptive or instructional text, input masks, and formatting rules as properties of a synonym.</span></span> <span data-ttu-id="05621-186">Como a propriedade é armazenada em um banco de dados, todos os aplicativos que leem a propriedade podem avaliar o objeto da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="05621-186">Because the property is stored in the database, all applications that read the property can evaluate the object in the same way.</span></span> <span data-ttu-id="05621-187">Para obter mais informações, veja [sp_addextendedproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="05621-187">For more information, see [sp_addextendedproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span></span>  
  
 <span data-ttu-id="05621-188">Para localizar o tipo base do objeto base de um sinônimo, use a função OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="05621-188">To find the base type of the base object of a synonym, use the OBJECTPROPERTYEX function.</span></span> <span data-ttu-id="05621-189">Para obter mais informações, veja [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="05621-189">For more information, see [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="05621-190">Exemplos</span><span class="sxs-lookup"><span data-stu-id="05621-190">Examples</span></span>  
 <span data-ttu-id="05621-191">O exemplo a seguir retorna o tipo básico do objeto base de um sinônimo que é um objeto local.</span><span class="sxs-lookup"><span data-stu-id="05621-191">The following example returns the base type of a synonym's base object that is a local object.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyEmployee   
FOR AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyEmployee'), 'BaseType') AS BaseType;  
```  
  
 <span data-ttu-id="05621-192">O exemplo a seguir retorna o tipo básico do objeto base de um sinônimo que é um objeto remoto localizado em um servidor denominado `Server1`.</span><span class="sxs-lookup"><span data-stu-id="05621-192">The following example returns the base type of a synonym's base object that is a remote object located on a server named `Server1`.</span></span>  
  
```  
EXECUTE sp_addlinkedserver Server1;  
GO  
CREATE SYNONYM MyRemoteEmployee  
FOR Server1.AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyRemoteEmployee'), 'BaseType') AS BaseType;  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="05621-193">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="05621-193">Related Content</span></span>  
 [<span data-ttu-id="05621-194">Criar Sinônimos</span><span class="sxs-lookup"><span data-stu-id="05621-194">Create Synonyms</span></span>](create-synonyms.md)  
  
 [<span data-ttu-id="05621-195">CREATE SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="05621-195">CREATE SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-synonym-transact-sql)  
  
 [<span data-ttu-id="05621-196">DROP SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="05621-196">DROP SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-synonym-transact-sql)  
  
  
