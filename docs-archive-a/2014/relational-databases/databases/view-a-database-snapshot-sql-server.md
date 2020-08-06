---
title: Exibir um instantâneo de banco de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], viewing
- displaying database snapshots
- viewing database snapshots
ms.assetid: 123f19b2-0850-4033-8507-59ebdfb368ee
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92c5c557656e87be562e9d5477f14f66b2c39e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685183"
---
# <a name="view-a-database-snapshot-sql-server"></a><span data-ttu-id="f0adc-102">Exibir um instantâneo de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f0adc-102">View a Database Snapshot (SQL Server)</span></span>
  <span data-ttu-id="f0adc-103">Este tópico explica como exibir um instantâneo do banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0adc-103">This topic explains how to view a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0adc-104">Para criar, reverter ou excluir um instantâneo do banco de dados, você deve usar o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0adc-104">To create, revert to, or delete a database snapshot, you must use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f0adc-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="f0adc-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f0adc-106">**Para exibir um instantâneo do banco de dados, usando:**</span><span class="sxs-lookup"><span data-stu-id="f0adc-106">**To view a database snapshot, using:**</span></span>  
  
     [<span data-ttu-id="f0adc-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0adc-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f0adc-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0adc-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f0adc-109">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0adc-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="f0adc-110">**Para exibir um instantâneo do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="f0adc-110">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="f0adc-111">No Pesquisador de Objetos, conecte-se à instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="f0adc-111">In Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f0adc-112">Expandir os **Bancos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="f0adc-112">Expand **Databases.**</span></span>  
  
3.  <span data-ttu-id="f0adc-113">Expanda o **Instantâneo do Banco de Dados**e selecione o instantâneo que você quer exibir.</span><span class="sxs-lookup"><span data-stu-id="f0adc-113">Expand **Database Snapshots**, and select the snapshot you want to view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f0adc-114">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0adc-114">Using Transact-SQL</span></span>  
 <span data-ttu-id="f0adc-115">**Para exibir um instantâneo do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="f0adc-115">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="f0adc-116">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0adc-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0adc-117">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f0adc-117">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0adc-118">Para listar os instantâneos do banco de dados da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte a coluna **source_database_id** da exibição do catálogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) para obter valores não nulos.</span><span class="sxs-lookup"><span data-stu-id="f0adc-118">To list the database snapshots of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], query the **source_database_id** column of the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view for non-NULL values.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f0adc-119">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="f0adc-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f0adc-120">Criar um instantâneo de banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0adc-120">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="f0adc-121">Reverter um banco de dados para um instantâneo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="f0adc-121">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="f0adc-122">Remover um instantâneo do banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0adc-122">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="f0adc-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f0adc-123">See Also</span></span>  
 [<span data-ttu-id="f0adc-124">Instantâneos de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0adc-124">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
