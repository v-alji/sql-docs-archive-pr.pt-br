---
title: Executar um procedimento armazenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.executeprocedure.f1
- sql12.swb.executeprocedure.general.f1
helpviewer_keywords:
- stored procedures [SQL Server], parameters
- extended stored procedures [SQL Server], executing
- system stored procedures [SQL Server], executing
- stored procedures [SQL Server], executing
- user-defined stored procedures [SQL Server]
ms.assetid: a0b1337d-2059-4872-8c62-3f967d8b170f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c679ba7af3ac9f60d312b33c0346e50687387476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582347"
---
# <a name="execute-a-stored-procedure"></a><span data-ttu-id="4c6be-102">Executar um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="4c6be-102">Execute a Stored Procedure</span></span>
  <span data-ttu-id="4c6be-103">Este tópico descreve como executar um procedimento armazenado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c6be-103">This topic describes how to execute a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4c6be-104">Há dois modos diferentes de executar um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="4c6be-104">There are two different ways to execute a stored procedure.</span></span> <span data-ttu-id="4c6be-105">A primeira e mais comum abordagem é fazer com que um aplicativo ou usuário chame o procedimento.</span><span class="sxs-lookup"><span data-stu-id="4c6be-105">The first and most common approach is for an application or user to call the procedure.</span></span> <span data-ttu-id="4c6be-106">A segunda abordagem é definir o procedimento para ser executado automaticamente quando uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for iniciada.</span><span class="sxs-lookup"><span data-stu-id="4c6be-106">The second approach is to set the procedure to run automatically when an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="4c6be-107">Quando um procedimento é chamado por um aplicativo ou usuário, a palavra-chave EXECUTE ou EXEC do [!INCLUDE[tsql](../../includes/tsql-md.md)] é declarada explicitamente na chamada.</span><span class="sxs-lookup"><span data-stu-id="4c6be-107">When a procedure is called by an application or user, the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE or EXEC keyword is explicitly stated in the call.</span></span> <span data-ttu-id="4c6be-108">Como alternativa, o procedimento poderá ser chamado e executado sem a palavra-chave se o for a primeira instrução do lote [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c6be-108">Alternatively, the procedure can be called and executed without the keyword if the procedure is the first statement in the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch.</span></span>  
  
 <span data-ttu-id="4c6be-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="4c6be-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4c6be-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="4c6be-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4c6be-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4c6be-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4c6be-112">Recomendações</span><span class="sxs-lookup"><span data-stu-id="4c6be-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4c6be-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="4c6be-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4c6be-114">**Para executar um procedimento armazenado usando:**</span><span class="sxs-lookup"><span data-stu-id="4c6be-114">**To execute a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="4c6be-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c6be-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4c6be-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c6be-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4c6be-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4c6be-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4c6be-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4c6be-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4c6be-119">A ordenação de banco de dados de chamada é usada durante a correspondência de nomes dos procedimentos do sistema.</span><span class="sxs-lookup"><span data-stu-id="4c6be-119">The calling database collation is used when matching system procedure names.</span></span> <span data-ttu-id="4c6be-120">Portanto, em seu aplicativo, você deve sempre fazer a diferenciação exata entre maiúsculas e minúsculas nos nomes em chamadas de procedimento.</span><span class="sxs-lookup"><span data-stu-id="4c6be-120">Therefore, always use the exact case of system procedure names in procedure calls.</span></span> <span data-ttu-id="4c6be-121">Por exemplo, este código falhará se for executado no contexto de um banco de dados que tenha uma ordenação com diferenciação de maiúsculas e minúsculas:</span><span class="sxs-lookup"><span data-stu-id="4c6be-121">For example, this code will fail if it is executed in the context of a database that has a case-sensitive collation:</span></span>  
  
    ```sql  
    EXEC SP_heLP; -- Will fail to resolve because SP_heLP does not equal sp_help  
    ```  
  
     <span data-ttu-id="4c6be-122">Para exibir os nomes exatos do procedimento do sistema, consulte as exibições de catálogo [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) e [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4c6be-122">To display the exact system procedure names, query the [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) and [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) catalog views.</span></span>  
  
-   <span data-ttu-id="4c6be-123">Se um procedimento definido pelo usuário tiver o mesmo nome de um procedimento de sistema, o procedimento definido pelo usuário talvez nunca seja executado.</span><span class="sxs-lookup"><span data-stu-id="4c6be-123">If a user-defined procedure has the same name as a system procedure, the user-defined procedure might not ever execute.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4c6be-124">Recomendações</span><span class="sxs-lookup"><span data-stu-id="4c6be-124">Recommendations</span></span>  
  
-   <span data-ttu-id="4c6be-125">Executando procedimentos armazenados do sistema</span><span class="sxs-lookup"><span data-stu-id="4c6be-125">Executing System Stored Procedures</span></span>  
  
     <span data-ttu-id="4c6be-126">Procedimentos armazenados do sistema começam com o prefixo **sp_** .</span><span class="sxs-lookup"><span data-stu-id="4c6be-126">System procedures begin with the prefix **sp_**.</span></span> <span data-ttu-id="4c6be-127">Como eles aparecem logicamente em todos os bancos de dados definidos pelo usuário e o sistema, podem ser executados de qualquer banco de dados sem ter que qualificar totalmente o nome de procedimento.</span><span class="sxs-lookup"><span data-stu-id="4c6be-127">Because they logically appear in all user- and system- defined databases, they can be executed from any database without having to fully quality the procedure name.</span></span> <span data-ttu-id="4c6be-128">No entanto, recomendamos que você qualifique por esquema todos os nomes dos procedimentos armazenados do sistema com o nome do esquema **sys** para evitar conflitos de nomes.</span><span class="sxs-lookup"><span data-stu-id="4c6be-128">However, we recommend schema-qualifying all system procedure names with the **sys** schema name to prevent name conflicts.</span></span> <span data-ttu-id="4c6be-129">O exemplo a seguir mostra o método recomendado para chamar um procedimento armazenado do sistema.</span><span class="sxs-lookup"><span data-stu-id="4c6be-129">The following example demonstrates the recommended method of calling a system procedure.</span></span>  
  
    ```sql  
    EXEC sys.sp_who;  
    ```  
  
-   <span data-ttu-id="4c6be-130">Executando procedimentos armazenados definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="4c6be-130">Executing User-defined Stored Procedures</span></span>  
  
     <span data-ttu-id="4c6be-131">Ao executar um procedimento definido pelo usuário, nós recomendamos qualificar o nome de procedimento com o nome do esquema.</span><span class="sxs-lookup"><span data-stu-id="4c6be-131">When executing a user-defined procedure, we recommend qualifying the procedure name with the schema name.</span></span> <span data-ttu-id="4c6be-132">Esta prática melhora um pouco o desempenho, pois o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] não tem que pesquisar vários esquemas.</span><span class="sxs-lookup"><span data-stu-id="4c6be-132">This practice gives a small performance boost because the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] does not have to search multiple schemas.</span></span> <span data-ttu-id="4c6be-133">Isso também impedirá a execução do procedimento errado se um banco de dados tiver procedimentos com o mesmo nome em vários esquemas.</span><span class="sxs-lookup"><span data-stu-id="4c6be-133">It also prevents executing the wrong procedure if a database has procedures with the same name in multiple schemas.</span></span>  
  
     <span data-ttu-id="4c6be-134">O exemplo a seguir mostra o método recomendado para executar um procedimento armazenado definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="4c6be-134">The following example demonstrates the recommended method to execute a user-defined procedure.</span></span> <span data-ttu-id="4c6be-135">Observe que o procedimento aceita um parâmetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="4c6be-135">Notice that the procedure accepts one input parameter.</span></span> <span data-ttu-id="4c6be-136">Para obter informações sobre como especificar parâmetros de entrada e saída, veja [Especificar parâmetros](specify-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="4c6be-136">For information about specifying input and output parameters, see [Specify Parameters](specify-parameters.md).</span></span>  
  
    ```sql  
    USE AdventureWorks2012;  
    GO  
    EXEC dbo.uspGetEmployeeManagers @BusinessEntityID = 50;  
    ```  
  
     <span data-ttu-id="4c6be-137">-Ou-</span><span class="sxs-lookup"><span data-stu-id="4c6be-137">-Or-</span></span>  
  
    ```sql  
    EXEC AdventureWorks2012.dbo.uspGetEmployeeManagers 50;  
    GO  
    ```  
  
     <span data-ttu-id="4c6be-138">Se um procedimento não qualificado definido pelo usuário for especificado, o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] pesquisará o procedimento na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="4c6be-138">If a nonqualified user-defined procedure is specified, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] searches for the procedure in the following order:</span></span>  
  
    1.  <span data-ttu-id="4c6be-139">Esquema **sys** do banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="4c6be-139">The **sys** schema of the current database.</span></span>  
  
    2.  <span data-ttu-id="4c6be-140">O esquema padrão do chamador se executado em um lote ou em SQL dinâmico.</span><span class="sxs-lookup"><span data-stu-id="4c6be-140">The caller's default schema if it is executed in a batch or in dynamic SQL.</span></span> <span data-ttu-id="4c6be-141">Ou, se o nome do procedimento não qualificado aparecer no corpo da definição de outro procedimento, o esquema que contém esse outro procedimento será pesquisado a seguir.</span><span class="sxs-lookup"><span data-stu-id="4c6be-141">Or, if the nonqualified procedure name appears inside the body of another procedure definition, the schema that contains this other procedure is searched next.</span></span>  
  
    3.  <span data-ttu-id="4c6be-142">O esquema **dbo** no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="4c6be-142">The **dbo** schema in the current database.</span></span>  
  
-   <span data-ttu-id="4c6be-143">Procedimentos armazenados executados automaticamente</span><span class="sxs-lookup"><span data-stu-id="4c6be-143">Executing Stored Procedures Automatically</span></span>  
  
     <span data-ttu-id="4c6be-144">Os procedimentos marcados para execução automática são executados sempre que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é iniciado e o banco de dados **mestre** é recuperado durante esse processo de inicialização.</span><span class="sxs-lookup"><span data-stu-id="4c6be-144">Procedures marked for automatic execution are executed every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts and the **master** database is recovered during that startup process.</span></span> <span data-ttu-id="4c6be-145">A configuração dos procedimentos para execução automática pode ser útil para executar operações de manutenção de banco de dados ou para que os procedimentos sejam executados continuamente como processos em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4c6be-145">Setting up procedures to execute automatically can be useful for performing database maintenance operations or for having procedures run continuously as background processes.</span></span> <span data-ttu-id="4c6be-146">Um outro uso para a execução automática é o procedimento realizar tarefas do sistema ou de manutenção no **tempdb**, tal como criar uma tabela temporária global.</span><span class="sxs-lookup"><span data-stu-id="4c6be-146">Another use for automatic execution is to have the procedure perform system or maintenance tasks in **tempdb**, such as creating a global temporary table.</span></span> <span data-ttu-id="4c6be-147">Isso garante que essa tabela temporária existirá sempre que o **tempdb** for recriado durante a inicialização do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c6be-147">This makes sure that such a temporary table will always exist when **tempdb** is re-created during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
     <span data-ttu-id="4c6be-148">Um procedimento executado automaticamente funciona com as mesmas permissões dos membros da função de servidor fixa do **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="4c6be-148">A procedure that is automatically executed operates with the same permissions as members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="4c6be-149">Qualquer mensagem de erro gerada pelo procedimento é gravada no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c6be-149">Any error messages generated by the procedure are written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
     <span data-ttu-id="4c6be-150">Não há limite para o número de procedimentos de inicialização que você pode ter, porém lembre-se de que cada um consome um thread de trabalho durante a execução.</span><span class="sxs-lookup"><span data-stu-id="4c6be-150">There is no limit to the number of startup procedures you can have, but be aware that each consumes one worker thread while executing.</span></span> <span data-ttu-id="4c6be-151">Se precisar executar vários procedimentos na inicialização, mas, se não for necessário executá-los em paralelo, torne um procedimento o procedimento de inicialização e faça com que este procedimento chame os demais.</span><span class="sxs-lookup"><span data-stu-id="4c6be-151">If you must execute multiple procedures at startup but do not need to execute them in parallel, make one procedure the startup procedure and have that procedure call the other procedures.</span></span> <span data-ttu-id="4c6be-152">Isto usará apenas um thread de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c6be-152">This uses only one worker thread.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="4c6be-153">Não retorne nenhum conjunto de resultados de um procedimento executado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4c6be-153">Do not return any result sets from a procedure that is executed automatically.</span></span> <span data-ttu-id="4c6be-154">Como o procedimento armazenado é executado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , em vez de pelo aplicativo ou usuário, os conjuntos de resultados não têm para onde ir.</span><span class="sxs-lookup"><span data-stu-id="4c6be-154">Because the procedure is being executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instead of an application or user, there is nowhere for the result sets to go.</span></span>  
  
-   <span data-ttu-id="4c6be-155">Configurando, limpando e controlando a execução automática</span><span class="sxs-lookup"><span data-stu-id="4c6be-155">Setting, Clearing, and Controlling Automatic Execution</span></span>  
  
     <span data-ttu-id="4c6be-156">Somente o administrador de sistema (**sa**) pode marcar um procedimento para ser executado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4c6be-156">Only the system administrator (**sa**) can mark a procedure to execute automatically.</span></span> <span data-ttu-id="4c6be-157">Além disso, o procedimento armazenado deve estar no banco de dados **mestre** , pertencer ao **sa**e não deverá conter parâmetros de entrada ou de saída.</span><span class="sxs-lookup"><span data-stu-id="4c6be-157">In addition, the procedure must be in the **master** database, owned by **sa**, and cannot have input or output parameters.</span></span>  
  
     <span data-ttu-id="4c6be-158">Use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) para:</span><span class="sxs-lookup"><span data-stu-id="4c6be-158">Use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to:</span></span>  
  
    1.  <span data-ttu-id="4c6be-159">Determinar um procedimento existente como um procedimento de inicialização.</span><span class="sxs-lookup"><span data-stu-id="4c6be-159">Designate an existing procedure as a startup procedure.</span></span>  
  
    2.  <span data-ttu-id="4c6be-160">Interromper a execução de um procedimento na inicialização do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c6be-160">Stop a procedure from executing at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4c6be-161">Segurança</span><span class="sxs-lookup"><span data-stu-id="4c6be-161">Security</span></span>  
 <span data-ttu-id="4c6be-162">Para obter mais informações, veja [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql) e [Cláusula EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4c6be-162">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql) and [EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4c6be-163">Permissões</span><span class="sxs-lookup"><span data-stu-id="4c6be-163">Permissions</span></span>  
 <span data-ttu-id="4c6be-164">Para obter mais informações, confira a seção “Permissões” em [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4c6be-164">For more information, see the "Permissions" section in [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4c6be-165">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c6be-165">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="4c6be-166">Para executar um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="4c6be-166">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="4c6be-167">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expanda essa instância e expanda **Bancos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="4c6be-167">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="4c6be-168">Expanda o banco de dados desejado, expanda **Programabilidade**e expanda **Procedimentos Armazenados**.</span><span class="sxs-lookup"><span data-stu-id="4c6be-168">Expand the database that you want, expand **Programmability**, and then expand **Stored Procedures**.</span></span>  
  
3.  <span data-ttu-id="4c6be-169">Clique com o botão direito do mouse no procedimento armazenado definido pelo usuário desejado e clique em **Executar Procedimento Armazenado**.</span><span class="sxs-lookup"><span data-stu-id="4c6be-169">Right-click the user-defined stored procedure that you want and click **Execute Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="4c6be-170">Na caixa de diálogo **Executar Procedimento** , especifique um valor para cada parâmetro e se ele deve passar um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="4c6be-170">In the **Execute Procedure** dialog box, specify a value for each parameter and whether it should pass a null value.</span></span>  
  
     <span data-ttu-id="4c6be-171">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="4c6be-171">**Parameter**</span></span>  
     <span data-ttu-id="4c6be-172">Indica o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4c6be-172">Indicates the name of the parameter.</span></span>  
  
     <span data-ttu-id="4c6be-173">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="4c6be-173">**Data Type**</span></span>  
     <span data-ttu-id="4c6be-174">Indica o tipo de dados do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4c6be-174">Indicates the data type of the parameter.</span></span>  
  
     <span data-ttu-id="4c6be-175">**Parâmetro de Saída**</span><span class="sxs-lookup"><span data-stu-id="4c6be-175">**Output Parameter**</span></span>  
     <span data-ttu-id="4c6be-176">Indica se este é um parâmetro de saída.</span><span class="sxs-lookup"><span data-stu-id="4c6be-176">Indicates if this is an output parameter.</span></span>  
  
     <span data-ttu-id="4c6be-177">**Passar Valor Nulo**</span><span class="sxs-lookup"><span data-stu-id="4c6be-177">**Pass Null Value**</span></span>  
     <span data-ttu-id="4c6be-178">Passe um NULL como valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4c6be-178">Pass a NULL as the value of the parameter.</span></span>  
  
     <span data-ttu-id="4c6be-179">**Valor**</span><span class="sxs-lookup"><span data-stu-id="4c6be-179">**Value**</span></span>  
     <span data-ttu-id="4c6be-180">Digite o valor do parâmetro ao chamar o procedimento.</span><span class="sxs-lookup"><span data-stu-id="4c6be-180">Type the value for the parameter when calling the procedure.</span></span>  
  
5.  <span data-ttu-id="4c6be-181">Para executar o procedimento armazenado, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c6be-181">To execute the stored procedure, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4c6be-182">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c6be-182">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="4c6be-183">Para executar um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="4c6be-183">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="4c6be-184">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c6be-184">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4c6be-185">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4c6be-185">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4c6be-186">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4c6be-186">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4c6be-187">Este exemplo mostra como executar um procedimento armazenado que espera um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4c6be-187">This example shows how to execute a stored procedure that expects one parameter.</span></span> <span data-ttu-id="4c6be-188">O exemplo executa o procedimento armazenado `uspGetEmployeeManagers` com o valor  `6` especificado como o parâmetro `@EmployeeID` .</span><span class="sxs-lookup"><span data-stu-id="4c6be-188">The example executes the `uspGetEmployeeManagers` stored procedure with the value  `6` specified as the `@EmployeeID` parameter.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC dbo.uspGetEmployeeManagers 6;  
GO  
```  
  
#### <a name="to-set-or-clear-a-procedure-for-executing-automatically"></a><span data-ttu-id="4c6be-189">Para definir ou limpar um procedimento para execução automática</span><span class="sxs-lookup"><span data-stu-id="4c6be-189">To set or clear a procedure for executing automatically</span></span>  
  
1.  <span data-ttu-id="4c6be-190">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c6be-190">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4c6be-191">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4c6be-191">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4c6be-192">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4c6be-192">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4c6be-193">Este exemplo mostra como usar [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) para definir um procedimento para execução automática.</span><span class="sxs-lookup"><span data-stu-id="4c6be-193">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to set a procedure for automatic execution.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionName = ] 'startup'   
    , @OptionValue = 'on';  
```  
  
#### <a name="to-stop-a-procedure-from-executing-automatically"></a><span data-ttu-id="4c6be-194">Para interromper a execução de um procedimento automaticamente</span><span class="sxs-lookup"><span data-stu-id="4c6be-194">To stop a procedure from executing automatically</span></span>  
  
1.  <span data-ttu-id="4c6be-195">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c6be-195">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4c6be-196">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4c6be-196">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4c6be-197">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4c6be-197">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4c6be-198">Este exemplo mostra como usar [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) para interromper a execução automática de um procedimento.</span><span class="sxs-lookup"><span data-stu-id="4c6be-198">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to stop a procedure from executing automatically.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionValue = 'off';  
```  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="4c6be-199">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4c6be-199">Example (Transact-SQL)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c6be-200">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4c6be-200">See Also</span></span>  
 <span data-ttu-id="4c6be-201">[Especificar parâmetros](specify-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="4c6be-201">[Specify Parameters](specify-parameters.md) </span></span>  
 <span data-ttu-id="4c6be-202">[Configurar a opção de configuração de servidor scan for startup procs](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="4c6be-202">[Configure the scan for startup procs Server Configuration Option](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span></span>  
 <span data-ttu-id="4c6be-203">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c6be-203">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="4c6be-204">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c6be-204">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="4c6be-205">Procedimentos armazenados &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="4c6be-205">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures-database-engine.md)  
  
  
