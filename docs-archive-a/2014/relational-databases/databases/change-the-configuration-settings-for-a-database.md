---
title: Alterar as definições de configuração de um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database configuration [SQL Server]
- configuration options [SQL Server], databases
- modifying database configuration settings
ms.assetid: c29c3385-5043-400f-bb4e-044a4c9a9a4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f9edecefae5154bb66a65e38724d9e77a94fdbb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685761"
---
# <a name="change-the-configuration-settings-for-a-database"></a><span data-ttu-id="28ac0-102">Alterar as definições de configuração de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="28ac0-102">Change the Configuration Settings for a Database</span></span>
  <span data-ttu-id="28ac0-103">Este tópico descreve como alterar opções em nível de banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28ac0-103">This topic describes how to change database-level options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="28ac0-104">Essas opções são exclusivas de cada banco de dados e não afetam outros bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="28ac0-104">These options are unique to each database and do not affect other databases.</span></span>  
  
 <span data-ttu-id="28ac0-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="28ac0-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="28ac0-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="28ac0-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="28ac0-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="28ac0-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="28ac0-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="28ac0-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="28ac0-109">**Para alterar as configurações de opção para um banco de dados, usando:**</span><span class="sxs-lookup"><span data-stu-id="28ac0-109">**To change the option settings for a database, using:**</span></span>  
  
     [<span data-ttu-id="28ac0-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="28ac0-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="28ac0-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28ac0-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="28ac0-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="28ac0-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="28ac0-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="28ac0-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="28ac0-114">Apenas o administrador do sistema, proprietário do banco de dados, membros das funções de servidor fixas **sysadmin** e **dbcreator** e da função de banco de dados fixa **db_owner** podem modificar essas opções.</span><span class="sxs-lookup"><span data-stu-id="28ac0-114">Only the system administrator, database owner, members of the **sysadmin** and **dbcreator** fixed server roles and **db_owner** fixed database roles can modify these options.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="28ac0-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="28ac0-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="28ac0-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="28ac0-116">Permissions</span></span>  
 <span data-ttu-id="28ac0-117">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="28ac0-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="28ac0-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="28ac0-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="28ac0-119">Para alterar as configurações de opção para um banco de dados</span><span class="sxs-lookup"><span data-stu-id="28ac0-119">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="28ac0-120">No Pesquisador de Objetos conecte-se a uma instância [!INCLUDE[ssDE](../../includes/ssde-md.md)] , expanda o servidor, expanda **Bancos de Dados**, clique com o botão direito do mouse em um banco de dados e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="28ac0-120">In Object Explorer, connect to a [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, expand the server, expand **Databases**, right-click a database, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="28ac0-121">Na caixa de diálogo **Propriedades de Banco de Dados** , clique em **Opções** para acessar a maioria das definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="28ac0-121">In the **Database Properties** dialog box, click **Options** to access most of the configuration settings.</span></span> <span data-ttu-id="28ac0-122">As configurações de arquivo e grupo de arquivos, espelhamento e envio de logs estão em suas páginas respectivas.</span><span class="sxs-lookup"><span data-stu-id="28ac0-122">File and filegroup configurations, mirroring and log shipping are on their respective pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="28ac0-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28ac0-123">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="28ac0-124">Para alterar as configurações de opção para um banco de dados</span><span class="sxs-lookup"><span data-stu-id="28ac0-124">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="28ac0-125">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28ac0-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="28ac0-126">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="28ac0-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="28ac0-127">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="28ac0-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="28ac0-128">Este exemplo define o modelo de recuperação e as opções de verificação de página de dados para o banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28ac0-128">This example sets the recovery model and data page verification options for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase7](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase7)]  
  
 <span data-ttu-id="28ac0-129">Para obter mais exemplos, veja [Opções ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="28ac0-129">For more examples, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ac0-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="28ac0-130">See Also</span></span>  
 <span data-ttu-id="28ac0-131">[Nível de compatibilidade de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="28ac0-131">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 <span data-ttu-id="28ac0-132">[Espelhamento de banco de dados ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="28ac0-132">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="28ac0-133">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="28ac0-133">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="28ac0-134">[Renomear um banco de dados](rename-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="28ac0-134">[Rename a Database](rename-a-database.md) </span></span>  
 [<span data-ttu-id="28ac0-135">Reduzir um banco de dados</span><span class="sxs-lookup"><span data-stu-id="28ac0-135">Shrink a Database</span></span>](shrink-a-database.md)  
  
  
