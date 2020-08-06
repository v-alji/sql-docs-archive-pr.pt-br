---
title: Excluindo objetos de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- deleting database objects
ms.assetid: dbb94fdf-c85b-477b-8e84-f830d259bade
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 6bd69935dbfac020c4c75bb391e7932009fd4197
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569801"
---
# <a name="deleting-database-objects"></a><span data-ttu-id="de005-102">Excluindo objetos de bancos de dados</span><span class="sxs-lookup"><span data-stu-id="de005-102">Deleting Database Objects</span></span>
  <span data-ttu-id="de005-103">Para remover todos os rastreamentos deste tutorial, você pode simplesmente excluir o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="de005-103">To remove all traces of this tutorial, you could just delete the database.</span></span> <span data-ttu-id="de005-104">No entanto, neste tópico, você passará pelas etapas para reverter todas as ações feitas durante o tutorial.</span><span class="sxs-lookup"><span data-stu-id="de005-104">However, in this topic, you will go through the steps to reverse every action you took doing the tutorial.</span></span>  
  
### <a name="removing-permissions-and-objects"></a><span data-ttu-id="de005-105">Removendo permissões e objetos</span><span class="sxs-lookup"><span data-stu-id="de005-105">Removing permissions and objects</span></span>  
  
1.  <span data-ttu-id="de005-106">Antes de excluir objetos, tenha certeza de selecionar o banco de dados correto:</span><span class="sxs-lookup"><span data-stu-id="de005-106">Before you delete objects, make sure you are in the correct database:</span></span>  
  
    ```  
    USE TestData;  
    GO  
    ```  
  
2.  <span data-ttu-id="de005-107">Use a instrução `REVOKE` para remover a permissão de execução para `Mary` no procedimento armazenado:</span><span class="sxs-lookup"><span data-stu-id="de005-107">Use the `REVOKE` statement to remove execute permission for `Mary` on the stored procedure:</span></span>  
  
    ```  
    REVOKE EXECUTE ON pr_Names FROM Mary;  
    GO  
  
    ```  
  
3.  <span data-ttu-id="de005-108">Use a instrução `DROP` para remover a permissão de `Mary` para acessar o banco de dados `TestData` :</span><span class="sxs-lookup"><span data-stu-id="de005-108">Use the `DROP` statement to remove permission for `Mary` to access the `TestData` database:</span></span>  
  
    ```  
    DROP USER Mary;  
    GO  
  
    ```  
  
4.  <span data-ttu-id="de005-109">Use a instrução `DROP` para remover a permissão de `Mary` para acessar esta instância do [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="de005-109">Use the `DROP` statement to remove permission for `Mary` to access this instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]:</span></span>  
  
    ```  
    DROP LOGIN [<computer_name>\Mary];  
    GO  
  
    ```  
  
5.  <span data-ttu-id="de005-110">Use a instrução `DROP` para remover ao procedimento armazenado `pr_Names`:</span><span class="sxs-lookup"><span data-stu-id="de005-110">Use the `DROP` statement to remove the store procedure `pr_Names`:</span></span>  
  
    ```  
    DROP PROC pr_Names;  
    GO  
  
    ```  
  
6.  <span data-ttu-id="de005-111">Use a instrução `DROP` para remover a exibição `vw_Names`:</span><span class="sxs-lookup"><span data-stu-id="de005-111">Use the `DROP` statement to remove the view `vw_Names`:</span></span>  
  
    ```  
    DROP View vw_Names;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="de005-112">Use a instrução `DELETE` para remover todas as linhas da tabela `Products` :</span><span class="sxs-lookup"><span data-stu-id="de005-112">Use the `DELETE` statement to remove all rows from the `Products` table:</span></span>  
  
    ```  
    DELETE FROM Products;  
    GO  
  
    ```  
  
8.  <span data-ttu-id="de005-113">Use a instrução `DROP` para remover a tabela `Products` :</span><span class="sxs-lookup"><span data-stu-id="de005-113">Use the `DROP` statement to remove the `Products` table:</span></span>  
  
    ```  
    DROP Table Products;  
    GO  
  
    ```  
  
9. <span data-ttu-id="de005-114">Você não pode remover o banco de dados `TestData` durante seu acesso; portanto, primeiro alterne o contexto para outro banco de dados e, em seguida, use a instrução `DROP` para remover o banco de dados `TestData` :</span><span class="sxs-lookup"><span data-stu-id="de005-114">You cannot remove the `TestData` database while you are in the database; therefore, first switch context to another database, and then use the `DROP` statement to remove the `TestData` database:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    DROP DATABASE TestData;  
    GO  
  
    ```  
  
 <span data-ttu-id="de005-115">Isso conclui o tutorial Escrevendo Instruções [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de005-115">This concludes the Writing [!INCLUDE[tsql](../includes/tsql-md.md)] Statements tutorial.</span></span> <span data-ttu-id="de005-116">Lembre-se, este tutorial é uma visão geral e não descreve todas as opções de instruções que são usadas.</span><span class="sxs-lookup"><span data-stu-id="de005-116">Remember, this tutorial is a brief overview and it does not describe all the options to the statements that are used.</span></span> <span data-ttu-id="de005-117">Projetar e criar uma estrutura de banco de dados eficiente e configurar acesso seguro aos dados requer um banco de dados mais complexo do que o mostrado neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="de005-117">Designing and creating an efficient database structure and configuring secure access to the data requires a more complex database than that shown in this tutorial.</span></span>  
  
## <a name="return-to-sql-server-tools-portal"></a><span data-ttu-id="de005-118">Retorne ao portal Ferramentas do SQL Server</span><span class="sxs-lookup"><span data-stu-id="de005-118">Return to SQL Server Tools Portal</span></span>  
 [<span data-ttu-id="de005-119">Tutorial: Gravando instruções Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="de005-119">Tutorial: Writing Transact-SQL Statements</span></span>](tutorial-writing-transact-sql-statements.md)  
  
## <a name="see-also"></a><span data-ttu-id="de005-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de005-120">See Also</span></span>  
 <span data-ttu-id="de005-121">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="de005-121">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="de005-122">[DROP USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="de005-122">[DROP USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-user-transact-sql) </span></span>  
 <span data-ttu-id="de005-123">[DROP LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="de005-123">[DROP LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-login-transact-sql) </span></span>  
 <span data-ttu-id="de005-124">[Descartar procedimento &#40;&#41;Transact-SQL](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="de005-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="de005-125">[DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="de005-125">[DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql) </span></span>  
 <span data-ttu-id="de005-126">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="de005-126">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="de005-127">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="de005-127">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 [<span data-ttu-id="de005-128">DROP DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="de005-128">DROP DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-database-audit-specification-transact-sql)  
  
  
