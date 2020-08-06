---
title: Criar uma especificação de auditoria de servidor e de auditoria de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlaudit.dbaudit.general.f1
helpviewer_keywords:
- audits [SQL Server], creating database specification
- database audit [SQL Server]
ms.assetid: 26ee85de-6e97-4318-b526-900924d96e62
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0cad01eae45d534f0f74911ce8f57827858cc920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680875"
---
# <a name="create-a-server-audit-and-database-audit-specification"></a><span data-ttu-id="87463-102">Criar uma especificação de auditoria de banco de dados e de servidor</span><span class="sxs-lookup"><span data-stu-id="87463-102">Create a Server Audit and Database Audit Specification</span></span>
  <span data-ttu-id="87463-103">Este tópico descreve como criar uma especificação de auditoria de servidor e de banco de dados no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87463-103">This topic describes how to create a server audit and database audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="87463-104">*Auditar* uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou um banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] envolve eventos de rastreamento e de log que ocorrem no sistema.</span><span class="sxs-lookup"><span data-stu-id="87463-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="87463-105">O objeto *SQL Server Audit* coleta uma instância única de ações no nível do servidor e/ou do banco de dados e grupos de ações a serem monitoradas.</span><span class="sxs-lookup"><span data-stu-id="87463-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="87463-106">A auditoria está no nível de instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="87463-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="87463-107">Você pode ter várias auditorias por instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="87463-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="87463-108">O objeto *Especificação de Auditoria de Banco de Dados* pertence a uma auditoria.</span><span class="sxs-lookup"><span data-stu-id="87463-108">The *Database-Level Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="87463-109">É possível criar uma especificação da auditoria de banco de dados por banco de dados do SQL Server por auditoria.</span><span class="sxs-lookup"><span data-stu-id="87463-109">You can create one database audit specification per SQL Server database per audit.</span></span> <span data-ttu-id="87463-110">Para obter mais informações, veja [Auditoria do SQL Server &#40;Mecanismo de Banco de Dados&#41;](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="87463-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="87463-111">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="87463-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="87463-112">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="87463-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="87463-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="87463-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="87463-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="87463-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="87463-115">**Para criar uma especificação de auditoria de servidor e de banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="87463-115">**To create a server audit and database audit specification, using:**</span></span>  
  
     [<span data-ttu-id="87463-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="87463-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="87463-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="87463-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="87463-118">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="87463-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="87463-119">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="87463-119">Limitations and Restrictions</span></span>  
 <span data-ttu-id="87463-120">As especificações de auditoria de banco de dados são objetos não protegidos que residem em um determinado banco de dados.</span><span class="sxs-lookup"><span data-stu-id="87463-120">Database audit specifications are non-securable objects that reside in a given database.</span></span> <span data-ttu-id="87463-121">Quando uma especificação de auditoria de banco de dados é criada, ela fica em um estado desabilitado.</span><span class="sxs-lookup"><span data-stu-id="87463-121">When a database audit specification is created, it is in a disabled state.</span></span>  
  
 <span data-ttu-id="87463-122">Quando você estiver criando ou modificando uma especificação de auditoria de banco de dados em um banco de dados de usuário, não inclua ações de auditoria em objetos do escopo de servidor, como as exibições do sistema.</span><span class="sxs-lookup"><span data-stu-id="87463-122">When you are creating or modifying a database audit specification in a user database, do not include audit actions on server-scope objects, such as the system views.</span></span> <span data-ttu-id="87463-123">Se forem incluídos objetos de escopo do servidor, a auditoria será criada.</span><span class="sxs-lookup"><span data-stu-id="87463-123">If server-scoped objects are included, the audit will be created.</span></span> <span data-ttu-id="87463-124">No entanto, os objetos de escopo do servidor não serão incluídos e nenhum erro será retornado.</span><span class="sxs-lookup"><span data-stu-id="87463-124">However, the server-scoped objects will not be included, and no error will be returned.</span></span> <span data-ttu-id="87463-125">Para auditar objetos de escopo do servidor, use uma especificação de auditoria de banco de dados no banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="87463-125">To audit server-scope objects, use a database audit specification in the master database.</span></span>  
  
 <span data-ttu-id="87463-126">As especificações de auditoria de banco de dados residem no banco de dados onde são criadas, com exceção do banco de dados de sistema `tempdb`.</span><span class="sxs-lookup"><span data-stu-id="87463-126">Database audit specifications reside in the database where they are created, with the exception of the `tempdb` system database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="87463-127">Segurança</span><span class="sxs-lookup"><span data-stu-id="87463-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="87463-128">Permissões</span><span class="sxs-lookup"><span data-stu-id="87463-128">Permissions</span></span>  
  
-   <span data-ttu-id="87463-129">Os usuários com a permissão ALTER ANY DATABASE AUDIT podem criar especificações de auditoria de banco de dados e associá-las a qualquer auditoria.</span><span class="sxs-lookup"><span data-stu-id="87463-129">Users with the ALTER ANY DATABASE AUDIT permission can create database audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="87463-130">Depois que uma especificação de auditoria de banco de dados é criada, ela pode ser exibida por entidades que tenham a permissão CONTROL SERVER, ALTER ANY DATABASE AUDIT ou com a conta sysadmin.</span><span class="sxs-lookup"><span data-stu-id="87463-130">After a database audit specification is created, it can be viewed by principals with the CONTROL SERVER,  ALTER ANY DATABASE AUDIT permissions, or the sysadmin account.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="87463-131">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="87463-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="87463-132">Para criar uma auditoria de servidor</span><span class="sxs-lookup"><span data-stu-id="87463-132">To create a server audit</span></span>  
  
1.  <span data-ttu-id="87463-133">No Pesquisador de Objetos, expanda a pasta **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="87463-133">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="87463-134">Clique com o botão direito do mouse na pasta **auditorias** e selecione **nova auditoria...**. Para obter mais informações, consulte [criar uma auditoria de servidor e uma especificação de auditoria de servidor](create-a-server-audit-and-server-audit-specification.md).</span><span class="sxs-lookup"><span data-stu-id="87463-134">Right-click the **Audits** folder and select **New Audit...**. For more information, see [Create a Server Audit and Server Audit Specification](create-a-server-audit-and-server-audit-specification.md).</span></span>  
  
3.  <span data-ttu-id="87463-135">Quando terminar de selecionar as opções, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="87463-135">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="87463-136">Para criar uma especificação de auditoria no nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="87463-136">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="87463-137">No Pesquisador de Objetos, expanda o banco de dados onde você deseja criar uma especificação de auditoria.</span><span class="sxs-lookup"><span data-stu-id="87463-137">In Object Explorer, expand the database where you want to create an audit specification.</span></span>  
  
2.  <span data-ttu-id="87463-138">Expanda a pasta **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="87463-138">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="87463-139">Clique com o botão direito do mouse na pasta **especificações de auditoria** e selecione **nova especificação de auditoria de banco de dados...**.</span><span class="sxs-lookup"><span data-stu-id="87463-139">Right-click the **Database Audit Specifications** folder and select **New Database Audit Specification...**.</span></span>  
  
     <span data-ttu-id="87463-140">As opções a seguir estão disponíveis na caixa de diálogo **Criar Especificação de Auditoria de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="87463-140">The following options are available on the **Create Database Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="87463-141">**Nome**</span><span class="sxs-lookup"><span data-stu-id="87463-141">**Name**</span></span>  
     <span data-ttu-id="87463-142">O nome da especificação de auditoria de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="87463-142">The name of the database audit specification.</span></span> <span data-ttu-id="87463-143">Esse nome é gerado automaticamente quando você cria uma nova especificação de auditoria de servidor, mas é editável.</span><span class="sxs-lookup"><span data-stu-id="87463-143">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="87463-144">**Auditoria**</span><span class="sxs-lookup"><span data-stu-id="87463-144">**Audit**</span></span>  
     <span data-ttu-id="87463-145">O nome de uma auditoria de banco de dados existente.</span><span class="sxs-lookup"><span data-stu-id="87463-145">The name of an existing database audit.</span></span> <span data-ttu-id="87463-146">Digite o nome da auditoria ou selecione-o na lista.</span><span class="sxs-lookup"><span data-stu-id="87463-146">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="87463-147">**Tipo de Ação de Auditoria**</span><span class="sxs-lookup"><span data-stu-id="87463-147">**Audit Action Type**</span></span>  
     <span data-ttu-id="87463-148">Especifica os grupos de ação de auditoria no nível de banco de dados e as ações de auditoria a capturar.</span><span class="sxs-lookup"><span data-stu-id="87463-148">Specifies the database-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="87463-149">Para obter a lista de grupos de ação de auditoria no nível de banco de dados, ações de auditoria e uma descrição dos eventos que eles contêm, veja [Ações e grupos de ações de auditoria do SQL Server](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="87463-149">For the list of database-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="87463-150">**Esquema de Objeto**</span><span class="sxs-lookup"><span data-stu-id="87463-150">**Object Schema**</span></span>  
     <span data-ttu-id="87463-151">Exibe o esquema para **Object Name**especificado.</span><span class="sxs-lookup"><span data-stu-id="87463-151">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="87463-152">**Object Name**</span><span class="sxs-lookup"><span data-stu-id="87463-152">**Object Name**</span></span>  
     <span data-ttu-id="87463-153">Nome do objeto a ser auditado.</span><span class="sxs-lookup"><span data-stu-id="87463-153">The name of the object to audit.</span></span> <span data-ttu-id="87463-154">Isso só está disponível para ações de auditoria e não se aplica a grupos de auditoria.</span><span class="sxs-lookup"><span data-stu-id="87463-154">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="87463-155">**Reticências (...)**</span><span class="sxs-lookup"><span data-stu-id="87463-155">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="87463-156">Abre a caixa de diálogo **Selecionar Objetos** para procurar e selecionar um objeto disponível, com base no **Tipo de Ação de Auditoria**especificado.</span><span class="sxs-lookup"><span data-stu-id="87463-156">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="87463-157">**Nome Principal**</span><span class="sxs-lookup"><span data-stu-id="87463-157">**Principal Name**</span></span>  
     <span data-ttu-id="87463-158">A conta para filtrar a auditoria para o objeto que está sendo auditado.</span><span class="sxs-lookup"><span data-stu-id="87463-158">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="87463-159">**Reticências (...)**</span><span class="sxs-lookup"><span data-stu-id="87463-159">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="87463-160">Abre a caixa de diálogo **Selecionar Objetos** para procurar e selecionar um objeto disponível, com base no **Nome do Objeto**especificado.</span><span class="sxs-lookup"><span data-stu-id="87463-160">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
4.  <span data-ttu-id="87463-161">Quando terminar de selecionar as opções, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="87463-161">When you are finished selecting option, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="87463-162">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="87463-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="87463-163">Para criar uma auditoria de servidor</span><span class="sxs-lookup"><span data-stu-id="87463-163">To create a server audit</span></span>  
  
1.  <span data-ttu-id="87463-164">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87463-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="87463-165">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="87463-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="87463-166">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="87463-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE master ;  
    GO  
    -- Create the server audit.   
    CREATE SERVER AUDIT Payrole_Security_Audit  
        TO FILE ( FILEPATH =   
    'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA' ) ;   
    GO  
    -- Enable the server audit.   
    ALTER SERVER AUDIT Payrole_Security_Audit   
    WITH (STATE = ON) ;  
    ```  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="87463-167">Para criar uma especificação de auditoria no nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="87463-167">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="87463-168">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87463-168">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="87463-169">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="87463-169">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="87463-170">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="87463-170">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="87463-171">O exemplo a seguir cria uma especificação de auditoria de banco de dados denominada `Audit_Pay_Tables` que audita instruções SELECT e INSERT pelo usuário `dbo` , para a tabela `HumanResources.EmployeePayHistory` baseada na auditoria de servidor definida acima.</span><span class="sxs-lookup"><span data-stu-id="87463-171">The example creates a database audit specification called `Audit_Pay_Tables` that audits SELECT and INSERT statements by the `dbo` user, for the `HumanResources.EmployeePayHistory` table based on the server audit defined above.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    -- Create the database audit specification.   
    CREATE DATABASE AUDIT SPECIFICATION Audit_Pay_Tables  
    FOR SERVER AUDIT Payrole_Security_Audit  
    ADD (SELECT , INSERT  
         ON HumanResources.EmployeePayHistory BY dbo )   
    WITH (STATE = ON) ;   
    GO  
  
    ```  
  
 <span data-ttu-id="87463-172">Para obter mais informações, veja [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) e [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="87463-172">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span></span>  
  
  
