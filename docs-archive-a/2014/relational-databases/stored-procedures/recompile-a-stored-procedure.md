---
title: Recompilar um procedimento armazenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- sp_recompile
- WITH RECOMPILE clause
- recompiling stored procedures
- stored procedures [SQL Server], recompiling
ms.assetid: b90deb27-0099-4fe7-ba60-726af78f7c18
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a9bc0e1d4baecb7f4c66b83b57081ed3131123d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584103"
---
# <a name="recompile-a-stored-procedure"></a><span data-ttu-id="29e46-102">Recompilar um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="29e46-102">Recompile a Stored Procedure</span></span>
  <span data-ttu-id="29e46-103">Este tópico descreve como recompilar um procedimento armazenado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29e46-103">This topic describes how to recompile a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="29e46-104">Há três maneiras de fazer isso: `WITH RECOMPILE` opção na definição do procedimento ou quando o procedimento é chamado, a `RECOMPILE` dica de consulta em instruções individuais ou usando o `sp_recompile` procedimento armazenado do sistema.</span><span class="sxs-lookup"><span data-stu-id="29e46-104">There are three ways to do this: `WITH RECOMPILE` option in the procedure definition or when the procedure is called, the `RECOMPILE` query hint on individual statements, or by using the `sp_recompile` system stored procedure.</span></span> <span data-ttu-id="29e46-105">Este tópico descreve como usar a opção WITH RECOMPILE ao criar uma definição de procedimento e executar um procedimento existente.</span><span class="sxs-lookup"><span data-stu-id="29e46-105">This topic describes using the WITH RECOMPILE option when creating a procedure definition and executing an existing procedure.</span></span> <span data-ttu-id="29e46-106">Também descreve como usar o procedimento armazenado do sistema sp_recompile para recompilar um procedimento existente.</span><span class="sxs-lookup"><span data-stu-id="29e46-106">It also describes using the sp_recompile system stored procedure to recompile an existing procedure.</span></span>  
  
 <span data-ttu-id="29e46-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="29e46-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="29e46-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="29e46-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="29e46-109">Recomendações</span><span class="sxs-lookup"><span data-stu-id="29e46-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="29e46-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="29e46-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="29e46-111">**Para recompilar um procedimento armazenado usando:**</span><span class="sxs-lookup"><span data-stu-id="29e46-111">**To recompile a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="29e46-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29e46-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="29e46-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="29e46-113">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="29e46-114">Recomendações</span><span class="sxs-lookup"><span data-stu-id="29e46-114">Recommendations</span></span>  
  
-   <span data-ttu-id="29e46-115">Quando um procedimento é compilado pela primeira vez ou recompilado, o plano de consulta do procedimento é otimizado para o estado atual do banco de dados e seus objetos.</span><span class="sxs-lookup"><span data-stu-id="29e46-115">When a procedure is compiled for the first time or recompiled, the procedure's query plan is optimized for the current state of the database and its objects.</span></span> <span data-ttu-id="29e46-116">Se um banco de dados passar por alterações significativas em seus dados ou estrutura, a recompilação de um procedimento atualizará e otimizará o plano de consulta do procedimento para essas alterações.</span><span class="sxs-lookup"><span data-stu-id="29e46-116">If a database undergoes significant changes to its data or structure, recompiling a procedure updates and optimizes the procedure's query plan for those changes.</span></span> <span data-ttu-id="29e46-117">Isso pode melhorar o desempenho do processamento do procedimento.</span><span class="sxs-lookup"><span data-stu-id="29e46-117">This can improve the procedure's processing performance.</span></span>  
  
-   <span data-ttu-id="29e46-118">Há momentos em que a recompilação de procedimento deve ser forçada e outros em que ela ocorre automaticamente.</span><span class="sxs-lookup"><span data-stu-id="29e46-118">There are times when procedure recompilation must be forced and other times when it occurs automatically.</span></span> <span data-ttu-id="29e46-119">A recompilação automática ocorre sempre que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é reiniciado.</span><span class="sxs-lookup"><span data-stu-id="29e46-119">Automatic recompiling occurs whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is restarted.</span></span> <span data-ttu-id="29e46-120">Isso também ocorrerá se uma tabela subjacente referenciada pelo procedimento tiver passado por alterações de design físicas.</span><span class="sxs-lookup"><span data-stu-id="29e46-120">It also occurs if an underlying table referenced by the procedure has undergone physical design changes.</span></span>  
  
-   <span data-ttu-id="29e46-121">Outro motivo para forçar a recompilação de um procedimento é neutralizar o comportamento “sugador de parâmetro” da compilação de procedimento.</span><span class="sxs-lookup"><span data-stu-id="29e46-121">Another reason to force a procedure to recompile is to counteract the "parameter sniffing" behavior of procedure compilation.</span></span> <span data-ttu-id="29e46-122">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa procedimentos armazenados, quaisquer valores de parâmetro usados pelo procedimento em sua compilação são incluídos como parte da geração do plano de consulta.</span><span class="sxs-lookup"><span data-stu-id="29e46-122">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes procedures, any parameter values that are used by the procedure when it compiles are included as part of generating the query plan.</span></span> <span data-ttu-id="29e46-123">Se esses valores representam aqueles típicos com os quais o procedimento é chamado subsequentemente, então o procedimento beneficia-se do plano de consulta cada vez que ele é compilado e executado.</span><span class="sxs-lookup"><span data-stu-id="29e46-123">If these values represent the typical ones with which the procedure is subsequently called, then the procedure benefits from the query plan every time that it compiles and executes.</span></span> <span data-ttu-id="29e46-124">Se valores de parâmetros no procedimento forem frequentemente atípicos, forçar uma recompilação do procedimento e um novo plano baseado em valores de parâmetros diferentes poderá melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="29e46-124">If parameter values on the procedure are frequently atypical, forcing a recompile of the procedure and a new plan based on different parameter values can improve performance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="29e46-125">oferece recompilação no nível da instrução de procedimentos.</span><span class="sxs-lookup"><span data-stu-id="29e46-125">features statement-level recompilation of procedures.</span></span> <span data-ttu-id="29e46-126">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recompila procedimentos armazenados, apenas a instrução que causou a recompilação é compilada, e não o procedimento completo.</span><span class="sxs-lookup"><span data-stu-id="29e46-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recompiles stored procedures, only the statement that caused the recompilation is compiled, instead of the complete procedure.</span></span>  
  
-   <span data-ttu-id="29e46-127">Se certas consultas em um procedimento usarem valores atípicos ou temporários regularmente, o desempenho do procedimento poderá ser melhorado com o uso da dica de consulta RECOMPILE nessas consultas.</span><span class="sxs-lookup"><span data-stu-id="29e46-127">If certain queries in a procedure regularly use atypical or temporary values, procedure performance can be improved by using the RECOMPILE query hint inside those queries.</span></span> <span data-ttu-id="29e46-128">Como apenas as consultas que usam a dica de consulta serão recompiladas, em vez de o procedimento completo, o comportamento de recompilação no nível da instrução no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será imitado.</span><span class="sxs-lookup"><span data-stu-id="29e46-128">Since only the queries using the query hint will be recompiled instead of the complete procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]'s statement-level recompilation behavior is mimicked.</span></span> <span data-ttu-id="29e46-129">Além de usar os valores de parâmetro atuais do procedimento, a dica de consulta RECOMPILE também usa os valores de todas as variáveis locais no procedimento armazenado quando você compila a instrução.</span><span class="sxs-lookup"><span data-stu-id="29e46-129">But in addition to using the procedure's current parameter values, the RECOMPILE query hint also uses the values of any local variables inside the stored procedure when you compile the statement.</span></span> <span data-ttu-id="29e46-130">Para obter mais informações, veja [Dica de consulta (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="29e46-130">For more information, see [Query Hint (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="29e46-131">Segurança</span><span class="sxs-lookup"><span data-stu-id="29e46-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="29e46-132">Permissões</span><span class="sxs-lookup"><span data-stu-id="29e46-132">Permissions</span></span>  
 <span data-ttu-id="29e46-133">`WITH RECOMPILE`Option</span><span class="sxs-lookup"><span data-stu-id="29e46-133">`WITH RECOMPILE` Option</span></span>  
 <span data-ttu-id="29e46-134">Se a opção for usada quando a definição de procedimento for criada, serão necessárias as permissões CREATE PROCEDURE no banco de dados e ALTER no esquema no qual o procedimento está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="29e46-134">If this option is used when the procedure definition is created, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="29e46-135">Se essa opção for usada em uma instrução EXECUTE, as permissões de EXECUTE serão necessárias no procedimento.</span><span class="sxs-lookup"><span data-stu-id="29e46-135">If this option is used in an EXECUTE statement, it requires EXECUTE permissions on the procedure.</span></span> <span data-ttu-id="29e46-136">As permissões não são necessárias na instrução EXECUTE em si, mas permissões de execução são necessárias no procedimento referenciado na instrução EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="29e46-136">Permissions are not required on the EXECUTE statement itself but execute permissions are required on the procedure referenced in the EXECUTE statement.</span></span> <span data-ttu-id="29e46-137">Para obter mais informações, veja [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="29e46-137">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
 <span data-ttu-id="29e46-138">`RECOMPILE`Dica de consulta</span><span class="sxs-lookup"><span data-stu-id="29e46-138">`RECOMPILE` Query Hint</span></span>  
 <span data-ttu-id="29e46-139">Esse recurso é usado quando o procedimento é criado e a dica é incluída em instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] no procedimento.</span><span class="sxs-lookup"><span data-stu-id="29e46-139">This feature is used when the procedure is created and the hint is included in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure.</span></span> <span data-ttu-id="29e46-140">Portanto, isso requer a permissão CREATE PROCEDURE no banco de dados e a permissão ALTER no esquema no qual o procedimento está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="29e46-140">Therefore, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="29e46-141">`sp_recompile`Procedimento armazenado do sistema</span><span class="sxs-lookup"><span data-stu-id="29e46-141">`sp_recompile` System Stored Procedure</span></span>  
 <span data-ttu-id="29e46-142">Exige a permissão ALTER no procedimento especificado.</span><span class="sxs-lookup"><span data-stu-id="29e46-142">Requires ALTER permission on the specified procedure.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="29e46-143">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29e46-143">Using Transact-SQL</span></span>  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="29e46-144">Para recompilar um procedimento armazenado usando a opção WITH RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="29e46-144">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="29e46-145">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29e46-145">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="29e46-146">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="29e46-146">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="29e46-147">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="29e46-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="29e46-148">Este exemplo cria a definição de procedimento.</span><span class="sxs-lookup"><span data-stu-id="29e46-148">This example creates the procedure definition.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspProductByVendor', 'P' ) IS NOT NULL   
    DROP PROCEDURE dbo.uspProductByVendor;  
GO  
CREATE PROCEDURE dbo.uspProductByVendor @Name varchar(30) = '%'  
WITH RECOMPILE  
AS  
    SET NOCOUNT ON;  
    SELECT v.Name AS 'Vendor name', p.Name AS 'Product name'  
    FROM Purchasing.Vendor AS v   
    JOIN Purchasing.ProductVendor AS pv   
      ON v.BusinessEntityID = pv.BusinessEntityID   
    JOIN Production.Product AS p   
      ON pv.ProductID = p.ProductID  
    WHERE v.Name LIKE @Name;  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="29e46-149">Para recompilar um procedimento armazenado usando a opção WITH RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="29e46-149">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="29e46-150">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29e46-150">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="29e46-151">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="29e46-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="29e46-152">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="29e46-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="29e46-153">Este exemplo cria um procedimento simples que retorna todos os funcionários (com os nomes e sobrenomes fornecidos), os cargos e os nomes de departamento em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="29e46-153">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="29e46-154">E copie e cole o segundo exemplo de código na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="29e46-154">And then copy and paste the second code example into the query window and click **Execute**.</span></span> <span data-ttu-id="29e46-155">Isso executa o procedimento e recompila o plano de consulta do procedimento.</span><span class="sxs-lookup"><span data-stu-id="29e46-155">This executes the procedure and recompiles the procedure's query plan.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXECUTE HumanResources.uspGetAllEmployees WITH RECOMPILE;  
GO  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-sp_recompile"></a><span data-ttu-id="29e46-156">Para recompilar um procedimento armazenado usando sp_recompile</span><span class="sxs-lookup"><span data-stu-id="29e46-156">To recompile a stored procedure by using sp_recompile</span></span>  
  
1.  <span data-ttu-id="29e46-157">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29e46-157">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="29e46-158">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="29e46-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="29e46-159">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="29e46-159">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="29e46-160">Este exemplo cria um procedimento simples que retorna todos os funcionários (com os nomes e sobrenomes fornecidos), os cargos e os nomes de departamento em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="29e46-160">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="29e46-161">Em seguida, copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="29e46-161">Then, copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="29e46-162">Isso não executa o procedimento, mas marca-o para recompilação de modo que seu plano de consulta seja atualizada na próxima vez em que o procedimento for executado.</span><span class="sxs-lookup"><span data-stu-id="29e46-162">This does not execute the procedure but it does mark the procedure to be recompiled so that its query plan is updated the next time that the procedure is executed.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_recompile N'HumanResources.uspGetAllEmployees';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="29e46-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29e46-163">See Also</span></span>  
 <span data-ttu-id="29e46-164">[Criar um procedimento armazenado](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="29e46-164">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="29e46-165">[Modificar um procedimento armazenado](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="29e46-165">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="29e46-166">[Renomear um procedimento armazenado](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="29e46-166">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="29e46-167">[Exibir a definição de um procedimento armazenado](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="29e46-167">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="29e46-168">[Exibir as dependências de um procedimento armazenado](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="29e46-168">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="29e46-169">DROP PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="29e46-169">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
