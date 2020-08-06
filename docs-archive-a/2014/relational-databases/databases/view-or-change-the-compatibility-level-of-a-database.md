---
title: Exibir ou alterar o nível de compatibilidade de um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- compatibility levels [SQL Server], viewing
- compatibility [SQL Server], databases
- compatibility levels [SQL Server], changing
ms.assetid: 579867ec-57cb-4cb8-af35-9688c1e9e15d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35cf7af50eba333440c42a1bac428df1fff156b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685186"
---
# <a name="view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="4c3b4-102">Exibir ou alterar o nível de compatibilidade de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="4c3b4-102">View or Change the Compatibility Level of a Database</span></span>
  <span data-ttu-id="4c3b4-103">Este tópico descreve como exibir ou alterar o nível de compatibilidade de um banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c3b4-103">This topic describes how to view or change the compatibility level of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4c3b4-104">Antes de alterar o nível de compatibilidade de um banco de dados, você deve entender o impacto da alteração em seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-104">Before you change the compatibility level of a database, you should understand the impact of the change on your applications.</span></span> <span data-ttu-id="4c3b4-105">Para obter mais informações, veja [Nível de compatibilidade de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="4c3b4-105">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
 <span data-ttu-id="4c3b4-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="4c3b4-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4c3b4-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="4c3b4-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4c3b4-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="4c3b4-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4c3b4-109">**Para exibir ou alterar o nível de compatibilidade de um banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="4c3b4-109">**To view or change the compatibility level of a database, using:**</span></span>  
  
     [<span data-ttu-id="4c3b4-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c3b4-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4c3b4-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c3b4-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4c3b4-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4c3b4-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4c3b4-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="4c3b4-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4c3b4-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="4c3b4-114">Permissions</span></span>  
 <span data-ttu-id="4c3b4-115">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4c3b4-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c3b4-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="4c3b4-117">Para exibir ou alterar o nível de compatibilidade de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="4c3b4-117">To view or change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="4c3b4-118">Depois de conectar-se à instância adequada do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], no Pesquisador de Objetos, clique no nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-118">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name.</span></span>  
  
2.  <span data-ttu-id="4c3b4-119">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de dados de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="4c3b4-120">Clique com o botão direito do mouse no banco de dados e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-120">Right-click the database, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="4c3b4-121">A caixa de diálogo **Database Properties** abre.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-121">The **Database Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="4c3b4-122">No painel **Selecionar uma página** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-122">In the **Select a page** pane, click **Options**.</span></span>  
  
     <span data-ttu-id="4c3b4-123">O nível de compatibilidade atual é exibido na caixa de listagem **Nível de compatibilidade** .</span><span class="sxs-lookup"><span data-stu-id="4c3b4-123">The current compatibility level is displayed in the **Compatibility level** list box.</span></span>  
  
5.  <span data-ttu-id="4c3b4-124">Para alterar o nível de compatibilidade, selecione uma opção diferente da lista.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-124">To change the compatibility level, select a different option from the list.</span></span> <span data-ttu-id="4c3b4-125">As escolhas são **SQL Server 2008 (100)**, **SQL Server 2012 (110)** ou **SQL Server 2014 (120)**.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-125">The choices are **SQL Server 2008 (100)**, **SQL Server 2012 (110)**, or **SQL Server 2014 (120)**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4c3b4-126">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c3b4-126">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-compatibility-level-of-a-database"></a><span data-ttu-id="4c3b4-127">Para exibir as informações sobre o nível de compatibilidade de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="4c3b4-127">To view the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="4c3b4-128">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c3b4-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4c3b4-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4c3b4-130">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4c3b4-131">Este exemplo retorna o nível de compatibilidade do banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c3b4-131">This example returns the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="4c3b4-132">Para alterar o nível de compatibilidade de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="4c3b4-132">To change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="4c3b4-133">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c3b4-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4c3b4-134">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4c3b4-135">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4c3b4-136">Este exemplo altera o nível de compatibilidade do [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c3b4-136">This example changes the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)].</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET COMPATIBILITY_LEVEL = 120;  
GO  
```  
  
  
