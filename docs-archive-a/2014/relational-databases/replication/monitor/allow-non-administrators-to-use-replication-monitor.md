---
title: Permitir que não administradores usem o Replication Monitor, | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, non-administrators access
ms.assetid: 1cf21d9e-831d-41a1-a5a0-83ff6d22fa86
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f4a7699c555086d627e4c3a52ea70acf931ea1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571944"
---
# <a name="allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="a9b0d-102">Permitir que não administradores usem o Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="a9b0d-102">Allow Non-Administrators to Use Replication Monitor</span></span>
  <span data-ttu-id="a9b0d-103">Este tópico descreve como permitir que não administradores usem o Replication Monitor no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9b0d-103">This topic describes how to allow non-administrators to use Replication Monitor in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a9b0d-104">O Replication Monitor pode ser usado por usuários que são membros das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="a9b0d-104">Replication Monitor can be used by users who are members of the following roles:</span></span>  
  
-   <span data-ttu-id="a9b0d-105">A função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="a9b0d-105">The **sysadmin** fixed server role.</span></span>  
  
     <span data-ttu-id="a9b0d-106">Esses usuários podem monitorar a replicação e possuem controle total sobre a modificação de propriedades de replicação como cronogramas de agentes, perfis de agentes, etc...</span><span class="sxs-lookup"><span data-stu-id="a9b0d-106">These users can monitor replication and have full control over changing replication properties such as agent schedules, agent profiles, and so on.</span></span>  
  
-   <span data-ttu-id="a9b0d-107">A `replmonitor` função de banco de dados no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="a9b0d-107">The `replmonitor` database role in the distribution database.</span></span>  
  
     <span data-ttu-id="a9b0d-108">Esses usuários podem monitorar a replicação, mas não podem modificar nenhuma propriedade de replicação.</span><span class="sxs-lookup"><span data-stu-id="a9b0d-108">These users can monitor replication, but cannot change any replication properties.</span></span>  
  
 <span data-ttu-id="a9b0d-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="a9b0d-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a9b0d-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="a9b0d-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a9b0d-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="a9b0d-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a9b0d-112">**Para permitir que não administradores usem o Replication Monitor, usando:**</span><span class="sxs-lookup"><span data-stu-id="a9b0d-112">**To allow non-administrators to use Replication Monitor, using:**</span></span>  
  
     [<span data-ttu-id="a9b0d-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a9b0d-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a9b0d-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a9b0d-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a9b0d-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a9b0d-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a9b0d-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="a9b0d-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a9b0d-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="a9b0d-117">Permissions</span></span>  
 <span data-ttu-id="a9b0d-118">Para permitir que não administradores usem o Replication Monitor, um membro da função de servidor fixa **sysadmin** deve adicionar o usuário ao banco de dados de distribuição e atribuir esse usuário à `replmonitor` função.</span><span class="sxs-lookup"><span data-stu-id="a9b0d-118">To allow non-administrators to use Replication Monitor, a member of the **sysadmin** fixed server role must add the user to the distribution database and assign that user to the `replmonitor` role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a9b0d-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a9b0d-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="a9b0d-120">Para permitir que não administradores usem o Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="a9b0d-120">To allow non-administrators to use Replication Monitor</span></span>  
  
1.  <span data-ttu-id="a9b0d-121">No [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], conecte-se ao Distribuidor e, em seguida, expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="a9b0d-121">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the Distributor, and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="a9b0d-122">Expanda **Bancos de Dados**, expanda **Bancos de Dados do Sistema**e, em seguida, expanda o banco de dados de distribuição (nomeado **distribuição** por padrão).</span><span class="sxs-lookup"><span data-stu-id="a9b0d-122">Expand **Databases**, expand **System Databases**, and then expand the distribution database (named **distribution** by default).</span></span>  
  
3.  <span data-ttu-id="a9b0d-123">Expanda **Segurança**, clique com o botão direito do mouse em **Usuários**e, em seguida, clique em **Novo Usuário**.</span><span class="sxs-lookup"><span data-stu-id="a9b0d-123">Expand **Security**, right-click **Users**, and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="a9b0d-124">Digite um nome de usuário e logon para o usuário.</span><span class="sxs-lookup"><span data-stu-id="a9b0d-124">Enter a user name and login for the user.</span></span>  
  
5.  <span data-ttu-id="a9b0d-125">Selecione um esquema padrão de `replmonitor` .</span><span class="sxs-lookup"><span data-stu-id="a9b0d-125">Select a default schema of `replmonitor`.</span></span>  
  
6.  <span data-ttu-id="a9b0d-126">Marque a `replmonitor` caixa de seleção na grade **associação da função de banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="a9b0d-126">Select the `replmonitor` check box in the **Database role membership** grid.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a9b0d-127">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a9b0d-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-user-to-the-replmonitor-fixed-database-role"></a><span data-ttu-id="a9b0d-128">Para adicionar um usuário à função de banco de dados fixo replmonitor</span><span class="sxs-lookup"><span data-stu-id="a9b0d-128">To add a user to the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="a9b0d-129">No Distribuidor no banco de dados de distribuição, execute [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a9b0d-129">At the Distributor on the distribution database, execute [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql).</span></span> <span data-ttu-id="a9b0d-130">Se o usuário não estiver listado no `UserName` conjunto de resultados, o usuário deverá receber acesso ao banco de dados de distribuição usando a instrução [CREATE USER &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="a9b0d-130">If the user is not listed in `UserName` in the result set, the user must be granted access to the distribution database using the [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) statement.</span></span>  
  
2.  <span data-ttu-id="a9b0d-131">No distribuidor no banco de dados de distribuição, execute [sp_helprolemember &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql), especificando um valor de `replmonitor` para o **@rolename** parâmetro.</span><span class="sxs-lookup"><span data-stu-id="a9b0d-131">At the Distributor on the distribution database, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql), specifying a value of `replmonitor` for the **@rolename** parameter.</span></span> <span data-ttu-id="a9b0d-132">Se o usuário estiver listado no `MemberName` conjunto de resultados, o usuário já pertence a essa função.</span><span class="sxs-lookup"><span data-stu-id="a9b0d-132">If the user is listed in `MemberName` in the result set, the user already belongs to this role.</span></span>  
  
3.  <span data-ttu-id="a9b0d-133">Se o usuário não pertencer à `replmonitor` função, execute [sp_addrolemember &#40;&#41;TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) no distribuidor no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="a9b0d-133">If the user does not belong to the `replmonitor` role, execute [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="a9b0d-134">Especifique um valor de `replmonitor` para **@rolename** e o nome do usuário do banco de dados ou o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] logon do Windows que está sendo adicionado para **@membername** .</span><span class="sxs-lookup"><span data-stu-id="a9b0d-134">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows login being added for **@membername**.</span></span>  
  
#### <a name="to-remove-a-user-from-the-replmonitor-fixed-database-role"></a><span data-ttu-id="a9b0d-135">Para remover um usuário da função de banco de dados fixo replmonitor</span><span class="sxs-lookup"><span data-stu-id="a9b0d-135">To remove a user from the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="a9b0d-136">Para verificar se o usuário pertence à `replmonitor` função, execute [sp_helprolemember &#40;&#41;TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) no distribuidor no banco de dados de distribuição e especifique um valor de `replmonitor` para **@rolename** .</span><span class="sxs-lookup"><span data-stu-id="a9b0d-136">To verify that the user belongs to the `replmonitor` role, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) at the Distributor on the distribution database, and specify a value of `replmonitor` for **@rolename**.</span></span> <span data-ttu-id="a9b0d-137">Se o usuário não estiver listado em `MemberName` no conjunto de resultados, o usuário não pertence atualmente à essa função.</span><span class="sxs-lookup"><span data-stu-id="a9b0d-137">If the user is not listed in `MemberName` in the result set, the user does not currently belong to this role.</span></span>  
  
2.  <span data-ttu-id="a9b0d-138">Se o usuário pertencer à `replmonitor` função, execute [sp_droprolemember &#40;&#41;TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) no distribuidor no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="a9b0d-138">If the user does belong to the `replmonitor` role, execute [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="a9b0d-139">Especifique um valor de `replmonitor` para **@rolename** e o nome do usuário do banco de dados ou o logon do Windows que está sendo removido para o **@membername** .</span><span class="sxs-lookup"><span data-stu-id="a9b0d-139">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the Windows login being removed for **@membername**.</span></span>  
  
  
