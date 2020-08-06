---
title: Exibir funções definidas pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.udfproperties.general.f1
- sql12.swb.functionproperties.general.f1
helpviewer_keywords:
- displaying user-defined functions
- viewing user-defined functions
- user-defined functions [SQL Server], viewing
- status information [SQL Server], user-defined functions
ms.assetid: a45dfab5-6384-4311-b935-2e23a70c5c10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5248f75540b72b489a7605b2cca34144dfcfedbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568393"
---
# <a name="view-user-defined-functions"></a><span data-ttu-id="7a1db-102">Exibir funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="7a1db-102">View User-defined Functions</span></span>
  <span data-ttu-id="7a1db-103">Você pode obter informações sobre a definição ou as propriedades de uma função definida pelo usuário no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a1db-103">You can gain information about the definition or properties of a user-defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7a1db-104">Talvez seja necessário observar a definição da função para entender como seus dados são derivados das tabelas de origem, ou consultar os dados definidos pela função.</span><span class="sxs-lookup"><span data-stu-id="7a1db-104">You may need to see the definition of the function to understand how its data is derived from the source tables or to see the data defined by the function.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7a1db-105">Se você alterar o nome de um objeto referenciado por uma função, deverá modificar essa função, de modo que seu texto reflita o novo nome.</span><span class="sxs-lookup"><span data-stu-id="7a1db-105">If you change the name of an object referenced by a function, you must modify that function so that its text reflects the new name.</span></span> <span data-ttu-id="7a1db-106">Portanto, antes de renomear um objeto, exiba primeiramente as dependências do objeto para determinar se alguma função é afetada pela mudança proposta.</span><span class="sxs-lookup"><span data-stu-id="7a1db-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any functions are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="7a1db-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="7a1db-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7a1db-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="7a1db-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7a1db-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="7a1db-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7a1db-110">**Para obter informações sobre uma função usando:**</span><span class="sxs-lookup"><span data-stu-id="7a1db-110">**To get information about a function, using:**</span></span>  
  
     [<span data-ttu-id="7a1db-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a1db-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7a1db-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a1db-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7a1db-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7a1db-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7a1db-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="7a1db-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7a1db-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="7a1db-115">Permissions</span></span>  
 <span data-ttu-id="7a1db-116">O uso de **sys.sql_expression_dependencies** para localizar todas as dependências em uma função exige a permissão VIEW DEFINITION no banco de dados e a permissão SELECT em **sys.sql_expression_dependencies** no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7a1db-116">Using **sys.sql_expression_dependencies** to find all the dependencies on a function requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="7a1db-117">As definições de objeto de sistema, como as retornadas em OBJECT_DEFINITION, são publicamente visíveis.</span><span class="sxs-lookup"><span data-stu-id="7a1db-117">System object definitions, like the ones returned in OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7a1db-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a1db-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-a-user-defined-functions-properties"></a><span data-ttu-id="7a1db-119">Para mostrar as propriedades de uma função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="7a1db-119">To show a user-defined function's properties</span></span>  
  
1.  <span data-ttu-id="7a1db-120">No **Pesquisador de Objetos**, clique no sinal de adição ao lado do banco de dados que contém a função na qual você deseja ver as propriedades e clique no sinal de adição para expandir a pasta **Programabilidade** .</span><span class="sxs-lookup"><span data-stu-id="7a1db-120">In **Object Explorer**, click the plus sign next to the database that contains the function to which you want to view the properties, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="7a1db-121">Clique no sinal de adição para expandir a pasta **Funções** .</span><span class="sxs-lookup"><span data-stu-id="7a1db-121">Click the plus sign to expand the **Functions** folder.</span></span>  
  
3.  <span data-ttu-id="7a1db-122">Clique no sinal de adição para expandir a pasta que contém a função na qual você deseja exibir as propriedades:</span><span class="sxs-lookup"><span data-stu-id="7a1db-122">Click the plus sign to expand the folder that contains the function to which you want to view the properties:</span></span>  
  
    -   <span data-ttu-id="7a1db-123">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="7a1db-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="7a1db-124">Função de valor escalar</span><span class="sxs-lookup"><span data-stu-id="7a1db-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="7a1db-125">Função de agregação</span><span class="sxs-lookup"><span data-stu-id="7a1db-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="7a1db-126">Clique com o botão direito do mouse na função da qual você deseja ver as propriedades e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7a1db-126">Right-click the function of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="7a1db-127">As propriedades a seguir aparecem na caixa de diálogo **Propriedades de Função –** _function_name_.</span><span class="sxs-lookup"><span data-stu-id="7a1db-127">The following properties appear in the **Function Properties -** _function_name_ dialog box.</span></span>  
  
     <span data-ttu-id="7a1db-128">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="7a1db-128">**Database**</span></span>  
     <span data-ttu-id="7a1db-129">Nome do banco de dados que contém essa função.</span><span class="sxs-lookup"><span data-stu-id="7a1db-129">The name of the database containing this function.</span></span>  
  
     <span data-ttu-id="7a1db-130">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="7a1db-130">**Server**</span></span>  
     <span data-ttu-id="7a1db-131">O nome da instância do servidor atual.</span><span class="sxs-lookup"><span data-stu-id="7a1db-131">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="7a1db-132">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="7a1db-132">**User**</span></span>  
     <span data-ttu-id="7a1db-133">Nome do usuário desta conexão.</span><span class="sxs-lookup"><span data-stu-id="7a1db-133">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="7a1db-134">**Data da criação**</span><span class="sxs-lookup"><span data-stu-id="7a1db-134">**Created date**</span></span>  
     <span data-ttu-id="7a1db-135">Exibe a data em que a função foi criada.</span><span class="sxs-lookup"><span data-stu-id="7a1db-135">Displays the date the function was created.</span></span>  
  
     <span data-ttu-id="7a1db-136">**Executar como**</span><span class="sxs-lookup"><span data-stu-id="7a1db-136">**Execute As**</span></span>  
     <span data-ttu-id="7a1db-137">Contexto de execução da função.</span><span class="sxs-lookup"><span data-stu-id="7a1db-137">Execution context for the function.</span></span>  
  
     <span data-ttu-id="7a1db-138">**Nome**</span><span class="sxs-lookup"><span data-stu-id="7a1db-138">**Name**</span></span>  
     <span data-ttu-id="7a1db-139">Nome da função atual.</span><span class="sxs-lookup"><span data-stu-id="7a1db-139">The name of the current function.</span></span>  
  
     <span data-ttu-id="7a1db-140">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="7a1db-140">**Schema**</span></span>  
     <span data-ttu-id="7a1db-141">Exibe o esquema que possui a função.</span><span class="sxs-lookup"><span data-stu-id="7a1db-141">Displays the schema that owns the function.</span></span>  
  
     <span data-ttu-id="7a1db-142">**Objeto do sistema**</span><span class="sxs-lookup"><span data-stu-id="7a1db-142">**System object**</span></span>  
     <span data-ttu-id="7a1db-143">Indica se a função é um objeto do sistema.</span><span class="sxs-lookup"><span data-stu-id="7a1db-143">Indicates whether the function is a system object.</span></span> <span data-ttu-id="7a1db-144">Os valores são True e False.</span><span class="sxs-lookup"><span data-stu-id="7a1db-144">Values are True and False.</span></span>  
  
     <span data-ttu-id="7a1db-145">**ANSI NULLs**</span><span class="sxs-lookup"><span data-stu-id="7a1db-145">**ANSI NULLs**</span></span>  
     <span data-ttu-id="7a1db-146">Indica se o objeto foi criado com a opção ANSI NULLs.</span><span class="sxs-lookup"><span data-stu-id="7a1db-146">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="7a1db-147">**Criptografado**</span><span class="sxs-lookup"><span data-stu-id="7a1db-147">**Encrypted**</span></span>  
     <span data-ttu-id="7a1db-148">Indica se a função é criptografada.</span><span class="sxs-lookup"><span data-stu-id="7a1db-148">Indicates whether the function is encrypted.</span></span> <span data-ttu-id="7a1db-149">Os valores são True e False.</span><span class="sxs-lookup"><span data-stu-id="7a1db-149">Values are True and False.</span></span>  
  
     <span data-ttu-id="7a1db-150">**Tipo de função**</span><span class="sxs-lookup"><span data-stu-id="7a1db-150">**Function Type**</span></span>  
     <span data-ttu-id="7a1db-151">O tipo de função definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7a1db-151">The type of user defined function.</span></span>  
  
     <span data-ttu-id="7a1db-152">**Identificador entre aspas**</span><span class="sxs-lookup"><span data-stu-id="7a1db-152">**Quoted identifier**</span></span>  
     <span data-ttu-id="7a1db-153">Indica se o objeto foi criado com a opção de identificador entre aspas.</span><span class="sxs-lookup"><span data-stu-id="7a1db-153">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="7a1db-154">**Ligado a esquema**</span><span class="sxs-lookup"><span data-stu-id="7a1db-154">**Schema bound**</span></span>  
     <span data-ttu-id="7a1db-155">Indica se a função é ligada a esquema.</span><span class="sxs-lookup"><span data-stu-id="7a1db-155">Indicates whether the function is schema-bound.</span></span> <span data-ttu-id="7a1db-156">Os valores são True e False.</span><span class="sxs-lookup"><span data-stu-id="7a1db-156">Values are True and False.</span></span> <span data-ttu-id="7a1db-157">Para obter informações sobre funções associadas ao esquema, veja a seção SCHEMABINDING de [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a1db-157">For information about schema-bound functions, see the SCHEMABINDING section of [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7a1db-158">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a1db-158">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-function"></a><span data-ttu-id="7a1db-159">Para obter a definição e as propriedades de uma função</span><span class="sxs-lookup"><span data-stu-id="7a1db-159">To get the definition and properties of a function</span></span>  
  
1.  <span data-ttu-id="7a1db-160">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a1db-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7a1db-161">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="7a1db-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a1db-162">Copie e cole um dos exemplos a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7a1db-162">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the function name, definition, and relevant properties  
    SELECT sm.object_id,   
       OBJECT_NAME(sm.object_id) AS object_name,   
       o.type,   
       o.type_desc,   
       sm.definition,  
       sm.uses_ansi_nulls,  
       sm.uses_quoted_identifier,  
       sm.is_schema_bound,  
       sm.execute_as_principal_id  
    -- using the two system tables sys.sql_modules and sys.objects  
    FROM sys.sql_modules AS sm  
    JOIN sys.objects AS o ON sm.object_id = o.object_id  
    -- from the function 'dbo.ufnGetProductDealerPrice'  
    WHERE sm.object_id = OBJECT_ID('dbo.ufnGetProductDealerPrice')  
    ORDER BY o.type;  
    GO  
  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the definition of the function dbo.ufnGetProductDealerPrice  
    SELECT OBJECT_DEFINITION (OBJECT_ID('dbo.ufnGetProductDealerPrice')) AS ObjectDefinition;  
    GO  
    ```  
  
 <span data-ttu-id="7a1db-163">Para obter mais informações, veja [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) e [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a1db-163">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) and [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-function"></a><span data-ttu-id="7a1db-164">Para obter as dependências de uma função</span><span class="sxs-lookup"><span data-stu-id="7a1db-164">To get the dependencies of a function</span></span>  
  
1.  <span data-ttu-id="7a1db-165">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a1db-165">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7a1db-166">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="7a1db-166">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a1db-167">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7a1db-167">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get all of the dependency information  
    SELECT OBJECT_NAME(sed.referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(sed.referencing_id, sed.referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        sed.referencing_class_desc, sed.referenced_class_desc,  
        sed.referenced_server_name, sed.referenced_database_name, sed.referenced_schema_name,  
        sed.referenced_entity_name,   
        COALESCE(COL_NAME(sed.referenced_id, sed.referenced_minor_id), '(n/a)') AS referenced_column_name,  
        sed.is_caller_dependent, sed.is_ambiguous  
    -- from the two system tables sys.sql_expression_dependencies and sys.object  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    -- on the function dbo.ufnGetProductDealerPrice  
    WHERE sed.referencing_id = OBJECT_ID('dbo.ufnGetProductDealerPrice');  
    GO  
    ```  
  
 <span data-ttu-id="7a1db-168">Para obter mais informações, veja [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) e [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a1db-168">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
