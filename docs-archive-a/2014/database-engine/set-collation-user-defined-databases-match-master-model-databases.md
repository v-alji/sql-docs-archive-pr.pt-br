---
title: Definir o agrupamento de bancos de dados definidos pelo usuário para corresponder aos dos bancos de dados mestre e modelo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: c686446f-dae1-4b05-a3df-837b3422988d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b48696fb56c40062d62f04845715170887f84fda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678948"
---
# <a name="set-the-collation-of-user-defined-databases-to-match-those-of-the-master-and-model-databases"></a><span data-ttu-id="912a4-102">Definir a ordenação de bancos de dados definidos pelo usuário para corresponder aos dos bancos de dados mestre e modelo</span><span class="sxs-lookup"><span data-stu-id="912a4-102">Set the Collation of User-defined Databases to Match Those of the master and model Databases</span></span>
  <span data-ttu-id="912a4-103">Esta regra verifica se os bancos de dados definidos pelo usuário são definidos usando uma ordenação de banco de dados com a mesma ordenação para mestre ou modelo.</span><span class="sxs-lookup"><span data-stu-id="912a4-103">This rule checks whether user-defined databases are defined by using a database collation that is the same as the collation for master or model.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="912a4-104">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="912a4-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="912a4-105">Recomendamos que as ordenações de bancos de dados definidos pelo usuário correspondam à ordenação de mestre ou modelo.</span><span class="sxs-lookup"><span data-stu-id="912a4-105">We recommend that the collations of user-defined databases match the collation of master or model.</span></span> <span data-ttu-id="912a4-106">Caso contrário, conflitos de ordenação podem ocorrer, o que pode impedir a execução do código.</span><span class="sxs-lookup"><span data-stu-id="912a4-106">Otherwise, collation conflicts can occur that might prevent code from executing.</span></span> <span data-ttu-id="912a4-107">Por exemplo, quando um procedimento armazenado une uma tabela a uma tabela temporária, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pode finalizar o lote e retornar um erro de conflito de ordenação, se as ordenações do banco de dados definido pelo usuário e do banco de dados modelo forem diferentes.</span><span class="sxs-lookup"><span data-stu-id="912a4-107">For example, when a stored procedure joins one table to a temporary table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] might end the batch and return a collation conflict error if the collations of the user-defined database and the model database are different.</span></span> <span data-ttu-id="912a4-108">Isto ocorre porque tabelas temporárias são criadas em tempdb, o que serve como base para a ordenação daquele modelo.</span><span class="sxs-lookup"><span data-stu-id="912a4-108">This occurs because temporary tables are created in tempdb, which bases its collation on that of model.</span></span>  
  
 <span data-ttu-id="912a4-109">Se surgirem erros de conflito de ordenação, considere uma das seguintes soluções:</span><span class="sxs-lookup"><span data-stu-id="912a4-109">If you experience collation conflict errors, consider one of the following solutions:</span></span>  
  
-   <span data-ttu-id="912a4-110">Exporte os dados do banco de dados do usuário e importe-os em novas tabelas com a mesma ordenação que os bancos de dados mestre e modelo.</span><span class="sxs-lookup"><span data-stu-id="912a4-110">Export the data from the user database and import it into new tables that have the same collation as the master and model databases.</span></span>  
  
-   <span data-ttu-id="912a4-111">Recrie os bancos de dados do sistema para usar uma ordenação que corresponda à ordenação do banco de dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="912a4-111">Rebuild the system databases to use a collation that matches the user database collation.</span></span> <span data-ttu-id="912a4-112">Para obter mais informações sobre como recriar os bancos de dados do sistema, consulte [Recompilar bancos de dados do sistema](../relational-databases/databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="912a4-112">For more information about how to rebuild the system databases, see [Rebuild System Databases](../relational-databases/databases/system-databases.md).</span></span>  
  
-   <span data-ttu-id="912a4-113">Modifique os procedimentos armazenados que uniram as tabelas do usuário às tabelas em tempdb para criar tabelas no tempdb usando a ordenação do banco de dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="912a4-113">Modify any stored procedures that join user tables to tables in tempdb to create the tables in tempdb by using the collation of the user database.</span></span> <span data-ttu-id="912a4-114">Para isso, adicione a cláusula `COLLATE database_default` às definições de coluna da tabela temporária, como demonstrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="912a4-114">To do this, add the `COLLATE database_default` clause to the column definitions of the temporary table, as shown in the following example:</span></span>  
  
    ```  
    CREATE TABLE #temp1 ( c1 int, c2 varchar(30) COLLATE database_default )  
    ```  
  
## <a name="for-more-information"></a><span data-ttu-id="912a4-115">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="912a4-115">For More Information</span></span>  
 [<span data-ttu-id="912a4-116">Definir ou alterar a ordenação de banco de dados</span><span class="sxs-lookup"><span data-stu-id="912a4-116">Set or Change the Database Collation</span></span>](../relational-databases/collations/set-or-change-the-database-collation.md)  
  
 [<span data-ttu-id="912a4-117">Definir ou alterar a ordenação de coluna</span><span class="sxs-lookup"><span data-stu-id="912a4-117">Set or Change the Column Collation</span></span>](../relational-databases/collations/set-or-change-the-column-collation.md)  
  
 [<span data-ttu-id="912a4-118">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="912a4-118">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
 [<span data-ttu-id="912a4-119">COLLATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="912a4-119">COLLATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/collations)  
  
 [<span data-ttu-id="912a4-120">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="912a4-120">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
 [<span data-ttu-id="912a4-121">Artigo 325335 da base de dados de conhecimento Microsoft</span><span class="sxs-lookup"><span data-stu-id="912a4-121">Microsoft Knowledge Base article 325335</span></span>](https://go.microsoft.com/fwlink/?linkid=117751)  
  
 [<span data-ttu-id="912a4-122">Como instalar o SQL Server 2008 pelo prompt de comando</span><span class="sxs-lookup"><span data-stu-id="912a4-122">How to: Install SQL Server 2008 from the Command Prompt</span></span>](https://go.microsoft.com/fwlink/?LinkId=81585)  
  
## <a name="see-also"></a><span data-ttu-id="912a4-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="912a4-123">See Also</span></span>  
 [<span data-ttu-id="912a4-124">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="912a4-124">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
