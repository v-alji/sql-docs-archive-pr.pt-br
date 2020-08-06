---
title: Criar um esquema de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.schemas.general.f1
helpviewer_keywords:
- creating schemas with Management Studio
- CREATE SCHEMA [Management Studio]
- database schemas
- schemas [SQL Server], creating
ms.assetid: ed2a5522-f4d2-4111-95a4-d3e1e5081739
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 3ac0c00768db6501c7d786c35758c1a9d75a5a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679810"
---
# <a name="create-a-database-schema"></a><span data-ttu-id="edf43-102">Criar um esquema de banco de dados</span><span class="sxs-lookup"><span data-stu-id="edf43-102">Create a Database Schema</span></span>
  <span data-ttu-id="edf43-103">Este tópico descreve como criar um esquema no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edf43-103">This topic describes how to create a schema in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="edf43-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="edf43-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="edf43-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="edf43-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="edf43-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="edf43-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="edf43-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="edf43-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="edf43-108">**Para criar um esquema usando:**</span><span class="sxs-lookup"><span data-stu-id="edf43-108">**To create a schema, using:**</span></span>  
  
     [<span data-ttu-id="edf43-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="edf43-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="edf43-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf43-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="edf43-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="edf43-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="edf43-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="edf43-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="edf43-113">O esquema novo é de propriedade de uma das seguintes entidades de segurança em nível de banco de dados: usuário de banco de dados, função de banco de dados ou função de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="edf43-113">The new schema is owned by one of the following database-level principals: database user, database role, or application role.</span></span> <span data-ttu-id="edf43-114">Os objetos criados em um esquema são de propriedade do proprietário do esquema e têm **principal_id** NULL em **sys.objects**.</span><span class="sxs-lookup"><span data-stu-id="edf43-114">Objects created within a schema are owned by the owner of the schema, and have a NULL **principal_id** in **sys.objects**.</span></span> <span data-ttu-id="edf43-115">A propriedade dos objetos contidos pelo esquema pode ser transferida para qualquer entidade de segurança no nível de banco de dados, mas o proprietário do esquema sempre retém a permissão CONTROL nos objetos do esquema.</span><span class="sxs-lookup"><span data-stu-id="edf43-115">Ownership of schema-contained objects can be transferred to any database-level principal, but the schema owner always retains CONTROL permission on objects within the schema.</span></span>  
  
-   <span data-ttu-id="edf43-116">Ao criar um objeto de banco de dados, se você especificar uma entidade de segurança de domínio válida (usuário ou grupo) como proprietária do objeto, a entidade de segurança de domínio será adicionada ao banco de dados como um esquema.</span><span class="sxs-lookup"><span data-stu-id="edf43-116">When creating a database object, if you specify a valid domain principal (user or group) as the object owner, the domain principal will be added to the database as a schema.</span></span> <span data-ttu-id="edf43-117">O novo esquema pertencerá a essa entidade de segurança de domínio.</span><span class="sxs-lookup"><span data-stu-id="edf43-117">The new schema will be owned by that domain principal.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="edf43-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="edf43-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="edf43-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="edf43-119">Permissions</span></span>  
  
-   <span data-ttu-id="edf43-120">Requer a permissão CREATE SCHEMA no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="edf43-120">Requires CREATE SCHEMA permission on the database.</span></span>  
  
-   <span data-ttu-id="edf43-121">Para especificar outro usuário como o proprietário do esquema que está sendo criado, o chamador deve ter a permissão IMPERSONATE no usuário em questão.</span><span class="sxs-lookup"><span data-stu-id="edf43-121">To specify another user as the owner of the schema being created, the caller must have IMPERSONATE permission on that user.</span></span> <span data-ttu-id="edf43-122">Se uma função de banco de dados for especificada como o proprietário, o chamador deve ter o seguinte: associação na função ou a permissão ALTER na função.</span><span class="sxs-lookup"><span data-stu-id="edf43-122">If a database role is specified as the owner, the caller must have one of the following: membership in the role or ALTER permission on the role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="edf43-123">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="edf43-123">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-schema"></a><span data-ttu-id="edf43-124">Para criar um esquema</span><span class="sxs-lookup"><span data-stu-id="edf43-124">To create a schema</span></span>  
  
1.  <span data-ttu-id="edf43-125">No Pesquisador de Objetos, expanda a pasta **Bancos de Dados** .</span><span class="sxs-lookup"><span data-stu-id="edf43-125">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="edf43-126">Expanda o banco de dados no qual o novo esquema de banco de dados será criado.</span><span class="sxs-lookup"><span data-stu-id="edf43-126">Expand the database in which to create the new database schema.</span></span>  
  
3.  <span data-ttu-id="edf43-127">Clique com o botão direito do mouse na pasta **Segurança** , aponte para **Novo**e selecione **Esquema**.</span><span class="sxs-lookup"><span data-stu-id="edf43-127">Right-click the **Security** folder, point to **New**, and select **Schema**.</span></span>  
  
4.  <span data-ttu-id="edf43-128">Na caixa de diálogo **Esquema – Novo** , na página **Geral** , insira um nome do novo esquema na caixa **Nome do esquema** .</span><span class="sxs-lookup"><span data-stu-id="edf43-128">In the **Schema - New** dialog box, on the **General** page, enter a name for the new schema in the **Schema name** box.</span></span>  
  
5.  <span data-ttu-id="edf43-129">Na caixa **Proprietário do esquema** , digite o nome de um usuário de banco de dados ou função para ser o proprietário da propriedade do esquema.</span><span class="sxs-lookup"><span data-stu-id="edf43-129">In the **Schema owner** box, enter the name of a database user or role to own the schema.</span></span> <span data-ttu-id="edf43-130">Como alternativa, clique em **Pesquisar** para abrir a caixa de diálogo **Pesquisar Funções e Usuários** .</span><span class="sxs-lookup"><span data-stu-id="edf43-130">Alternately, click **Search** to open the **Search Roles and Users** dialog box.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="edf43-131">Opções adicionais</span><span class="sxs-lookup"><span data-stu-id="edf43-131">Additional Options</span></span>  
 <span data-ttu-id="edf43-132">A caixa de diálogo **Schema- New** também oferece opções em duas páginas adicionais: **Permissões** e **Propriedades Estendidas**.</span><span class="sxs-lookup"><span data-stu-id="edf43-132">The **Schema- New** dialog box also offers options on two additional pages: **Permissions** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="edf43-133">A página **Permissões** lista todos os protegíveis e as permissões possíveis nesses protegíveis que podem ser concedidos ao logon.</span><span class="sxs-lookup"><span data-stu-id="edf43-133">The **Permissions** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="edf43-134">A página **Propriedades estendidas** permite adicionar propriedades personalizadas a usuários de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="edf43-134">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="edf43-135">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf43-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schema"></a><span data-ttu-id="edf43-136">Para criar um esquema</span><span class="sxs-lookup"><span data-stu-id="edf43-136">To create a schema</span></span>  
  
1.  <span data-ttu-id="edf43-137">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edf43-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="edf43-138">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="edf43-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="edf43-139">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="edf43-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the schema Sprockets owned by Annik that contains table NineProngs.   
    -- The statement grants SELECT to Mandar and denies SELECT to Prasanna.  
  
    CREATE SCHEMA Sprockets AUTHORIZATION Annik  
        CREATE TABLE NineProngs (source int, cost int, partnumber int)  
        GRANT SELECT ON SCHEMA::Sprockets TO Mandar  
        DENY SELECT ON SCHEMA::Sprockets TO Prasanna;  
    GO  
    ```  
  
 <span data-ttu-id="edf43-140">Para obter mais informações, veja [CREATE SCHEMA &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-schema-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="edf43-140">For more information, see [CREATE SCHEMA &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-schema-transact-sql).</span></span>  
  
  
