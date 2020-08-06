---
title: Excluir arquivos de dados ou de log de um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- deleting files
- removing files
- removing data
- data deletions [SQL Server]
- file deletion [SQL Server]
- deleting data
ms.assetid: 0db4018c-ce2c-4ba1-bb29-1e4f3791c925
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6f7bd170e085e9bc94b00446545850e905efaa34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685744"
---
# <a name="delete-data-or-log-files-from-a-database"></a><span data-ttu-id="6dc65-102">Excluir arquivos de dados ou de log de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="6dc65-102">Delete Data or Log Files from a Database</span></span>
  <span data-ttu-id="6dc65-103">Este tópico descreve como excluir arquivos de dados ou de log no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dc65-103">This topic describes how to delete data or log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6dc65-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6dc65-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6dc65-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6dc65-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="6dc65-106">Um arquivo deve estar vazio antes que possa ser excluído.</span><span class="sxs-lookup"><span data-stu-id="6dc65-106">A file must be empty before it can be deleted.</span></span> <span data-ttu-id="6dc65-107">Para saber mais, veja [Reduzir um arquivo](shrink-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="6dc65-107">For more information, see [Shrink a File](shrink-a-file.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6dc65-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="6dc65-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6dc65-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="6dc65-109">Permissions</span></span>  
 <span data-ttu-id="6dc65-110">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6dc65-110">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6dc65-111">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6dc65-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="6dc65-112">Para excluir arquivos de dados ou de log de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="6dc65-112">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="6dc65-113">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="6dc65-113">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6dc65-114">Expanda **Bancos de Dados**, clique com o botão direito do mouse no banco de dados do qual deseja excluir o arquivo e depois clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6dc65-114">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6dc65-115">Selecione a página **Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="6dc65-115">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="6dc65-116">Na grade **Arquivos de bancos de dados** , selecione o arquivo a ser excluído e, depois, clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="6dc65-116">In the **Database files** grid, select the file to delete and then click **Remove**.</span></span>  
  
5.  <span data-ttu-id="6dc65-117">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc65-117">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6dc65-118">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6dc65-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="6dc65-119">Para excluir arquivos de dados ou de log de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="6dc65-119">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="6dc65-120">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dc65-120">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6dc65-121">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6dc65-121">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6dc65-122">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6dc65-122">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6dc65-123">Este exemplo remove o arquivo `test1dat4`.</span><span class="sxs-lookup"><span data-stu-id="6dc65-123">This example removes the file `test1dat4`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase4](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase4)]  
  
 <span data-ttu-id="6dc65-124">Para obter mais exemplos, consulte [Opções de arquivo e grupos de arquivos ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="6dc65-124">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc65-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6dc65-125">See Also</span></span>  
 <span data-ttu-id="6dc65-126">[Reduzir um banco de dados](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="6dc65-126">[Shrink a Database](shrink-a-database.md) </span></span>  
 [<span data-ttu-id="6dc65-127">Adicionar arquivos de dados ou de log a um banco de dados</span><span class="sxs-lookup"><span data-stu-id="6dc65-127">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
