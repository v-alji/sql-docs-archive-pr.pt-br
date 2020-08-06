---
title: Exibir uma lista de bancos de dados em uma instância do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- current databases
- databases currently on server [SQL Server]
- database list [SQL Server]
- viewing database list
- displaying database list
- databases [SQL Server], viewing
- servers [SQL Server], databases listed on
- listing databases
ms.assetid: 7ee7a789-db36-4be9-8a0e-0362a1e152dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 47283fa9065a0b9d6238dab804094d9a65d17897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685182"
---
# <a name="view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="336ca-102">Exibir uma lista de bancos de dados em uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="336ca-102">View a List of Databases on an Instance of SQL Server</span></span>
  <span data-ttu-id="336ca-103">Este tópico descreve como exibir uma lista de bancos de dados em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="336ca-103">This topic describes how to view a list of databases on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="336ca-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="336ca-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="336ca-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="336ca-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="336ca-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="336ca-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="336ca-107">**Para exibir uma lista de bancos de dados em uma instância do SQL Server usando:**</span><span class="sxs-lookup"><span data-stu-id="336ca-107">**To view a list of databases on an instance of SQL Server, using:**</span></span>  
  
     [<span data-ttu-id="336ca-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="336ca-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="336ca-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="336ca-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="336ca-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="336ca-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="336ca-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="336ca-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="336ca-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="336ca-112">Permissions</span></span>  
 <span data-ttu-id="336ca-113">Se o chamador de **sys.databases** não for o proprietário do banco de dados e o banco de dados não for o **master** ou **tempdb**, as permissões mínimas necessárias para ver a linha correspondente serão as permissões em nível de servidor ALTER ANY DATABASE ou VIEW ANY DATABASE ou a permissão CREATE DATABASE no banco de dados **master** .</span><span class="sxs-lookup"><span data-stu-id="336ca-113">If the caller of **sys.databases** is not the owner of the database and the database is not **master** or **tempdb**, the minimum permissions required to see the corresponding row are ALTER ANY DATABASE or VIEW ANY DATABASE server-level permission, or CREATE DATABASE permission in the **master** database.</span></span> <span data-ttu-id="336ca-114">O banco de dados ao qual o chamador está conectado sempre pode ser exibido em **sys.databases**.</span><span class="sxs-lookup"><span data-stu-id="336ca-114">The database to which the caller is connected can always be viewed in **sys.databases**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="336ca-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="336ca-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="336ca-116">Para exibir uma lista de bancos de dados em uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="336ca-116">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="336ca-117">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="336ca-117">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="336ca-118">Para consultar uma lista de todos os bancos de dados na instância, expanda **Bancos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="336ca-118">To see a list of all databases on the instance, expand **Databases**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="336ca-119">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="336ca-119">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="336ca-120">Para exibir uma lista de bancos de dados em uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="336ca-120">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="336ca-121">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="336ca-121">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="336ca-122">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="336ca-122">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="336ca-123">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="336ca-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="336ca-124">Este exemplo retorna uma lista dos bancos de dados na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="336ca-124">This example returns a list of databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="336ca-125">A lista inclui os nomes dos bancos de dados, suas IDs de banco de dados e as datas de criação dos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="336ca-125">The list includes the names of the databases, their database IDs, and the dates when the databases were created.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT name, database_id, create_date  
FROM sys.databases ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="336ca-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="336ca-126">See Also</span></span>  
 <span data-ttu-id="336ca-127">[Exibição de catálogo do bancos de dados e de arquivos &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="336ca-127">[Databases and Files Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="336ca-128">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="336ca-128">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
