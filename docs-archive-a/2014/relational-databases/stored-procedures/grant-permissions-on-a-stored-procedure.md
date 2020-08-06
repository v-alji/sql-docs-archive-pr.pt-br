---
title: Conceder permissões em um procedimento armazenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], permissions
ms.assetid: a7d15816-a788-4099-ad91-dc4b26618299
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23ea130b9d2033128adc99413c053d66936e3ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574572"
---
# <a name="grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="55577-102">Conceder permissões em um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="55577-102">Grant Permissions on a Stored Procedure</span></span>
  <span data-ttu-id="55577-103">Este tópico descreve como conceder permissões em um procedimento armazenado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55577-103">This topic describes how to grant permissions on a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="55577-104">As permissões podem ser concedidas a um usuário existente, a uma função de banco de dados ou a uma função de aplicativo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55577-104">Permissions can be granted to an existing user, database role, or application role in the database.</span></span>  
  
 <span data-ttu-id="55577-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="55577-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="55577-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="55577-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="55577-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="55577-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="55577-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="55577-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="55577-109">**Para conceder permissões em um procedimento armazenado usando:**</span><span class="sxs-lookup"><span data-stu-id="55577-109">**To grant permissions on a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="55577-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55577-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="55577-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55577-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="55577-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="55577-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="55577-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="55577-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="55577-114">Não é possível usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para conceder permissões nos procedimentos do sistema ou funções do sistema.</span><span class="sxs-lookup"><span data-stu-id="55577-114">You cannot use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to grant permissions on system procedures or system functions.</span></span> <span data-ttu-id="55577-115">Em vez disso, use [Permissões do objeto GRANT](/sql/t-sql/statements/grant-object-permissions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="55577-115">Use [GRANT Object Permissions](/sql/t-sql/statements/grant-object-permissions-transact-sql) instead.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="55577-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="55577-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="55577-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="55577-117">Permissions</span></span>  
 <span data-ttu-id="55577-118">O concessor (ou a entidade de segurança especificada com a opção AS) deve ter a própria permissão com GRANT OPTION ou uma permissão superior que tenha a permissão que está sendo concedida implícita.</span><span class="sxs-lookup"><span data-stu-id="55577-118">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION, or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="55577-119">Requer permissão ALTER no esquema ao qual o procedimento pertence ou permissão CONTROL no procedimento.</span><span class="sxs-lookup"><span data-stu-id="55577-119">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span> <span data-ttu-id="55577-120">Para obter mais informações, veja [Permissões de objeto GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55577-120">For more information, see [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="55577-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55577-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="55577-122">Para conceder permissões em um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="55577-122">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="55577-123">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="55577-123">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="55577-124">Expanda **Bancos de Dados**, expanda o banco de dados ao qual pertence o procedimento e expanda **Programação**.</span><span class="sxs-lookup"><span data-stu-id="55577-124">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="55577-125">Expanda **Procedimentos Armazenados**, clique com o botão direito do mouse no procedimento para conceder permissões e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="55577-125">Expand **Stored Procedures**, right-click the procedure to grant permissions on, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="55577-126">De **Propriedades do Procedimento Armazenado**, selecione a página **Permissões** .</span><span class="sxs-lookup"><span data-stu-id="55577-126">From **Stored Procedure Properties**, select the **Permissions** page.</span></span>  
  
5.  <span data-ttu-id="55577-127">Para conceder permissões a um usuário, a uma função de banco de dados ou a uma função de aplicativo, clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="55577-127">To grant permissions to a user, database role, or application role, click **Search**.</span></span>  
  
6.  <span data-ttu-id="55577-128">Em **Selecionar Usuários ou Funções**, clique em **Tipos de Objeto** para adicionar ou desmarcar os usuários ou funções que desejar.</span><span class="sxs-lookup"><span data-stu-id="55577-128">In **Select Users or Roles**, click **Object Types** to add or clear the users and roles you want.</span></span>  
  
7.  <span data-ttu-id="55577-129">Clique em **Procurar** para exibir a lista de usuários ou funções.</span><span class="sxs-lookup"><span data-stu-id="55577-129">Click **Browse** to display the list of users or roles.</span></span> <span data-ttu-id="55577-130">Selecione os usuários ou funções aos quais as permissões devem ser concedidas.</span><span class="sxs-lookup"><span data-stu-id="55577-130">Select the users or roles to whom permissions should be granted.</span></span>  
  
8.  <span data-ttu-id="55577-131">Na grade **Permissões Explícitas** , selecione as permissões para concedê-las ao usuário especificado ou função.</span><span class="sxs-lookup"><span data-stu-id="55577-131">In the **Explicit Permissions** grid, select the permissions to grant to the specified user or role.</span></span> <span data-ttu-id="55577-132">Para obter uma descrição das permissões, veja [Permissões &#40;Mecanismo de Banco de Dados&#41;](../security/permissions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="55577-132">For a description of the permissions, see [Permissions &#40;Database Engine&#41;](../security/permissions-database-engine.md).</span></span>  
  
 <span data-ttu-id="55577-133">Ao selecionar **Conceder** , uma permissão específica será dada ao beneficiado.</span><span class="sxs-lookup"><span data-stu-id="55577-133">Selecting **Grant** indicates the grantee will be given the specified permission.</span></span> <span data-ttu-id="55577-134">Ao selecionar **Conceder Com** o beneficiado também poderá conceder a permissão específica a outros principais.</span><span class="sxs-lookup"><span data-stu-id="55577-134">Selecting **Grant With** indicates that the grantee will also be able to grant the specified permission to other principals.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="55577-135">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55577-135">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="55577-136">Para conceder permissões em um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="55577-136">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="55577-137">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55577-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="55577-138">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="55577-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="55577-139">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="55577-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="55577-140">Este exemplo concede a permissão `EXECUTE` no procedimento armazenado `HumanResources.uspUpdateEmployeeHireInfo` para uma função de aplicativo chamada `Recruiting11`.</span><span class="sxs-lookup"><span data-stu-id="55577-140">This example grants `EXECUTE` permission on the stored procedure `HumanResources.uspUpdateEmployeeHireInfo` to an application role named `Recruiting11`.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
    TO Recruiting11;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="55577-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55577-141">See Also</span></span>  
 <span data-ttu-id="55577-142">[sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="55577-142">[sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span></span>  
 <span data-ttu-id="55577-143">[Permissões de objeto GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="55577-143">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="55577-144">[Criar um procedimento armazenado](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="55577-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="55577-145">[Modificar um procedimento armazenado](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="55577-145">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="55577-146">[Excluir um procedimento armazenado](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="55577-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="55577-147">Renomear um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="55577-147">Rename a Stored Procedure</span></span>](rename-a-stored-procedure.md)  
  
  
