---
title: Renomear estatísticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- renaming statistics
- statistics [SQL Server], renaming
ms.assetid: a3bed7b7-3dc5-4b33-b1c6-67c27f573764
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1528dcec50a662524531065d597b004fe7f59e5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582359"
---
# <a name="rename-statistics"></a><span data-ttu-id="a128b-102">Renomear estatísticas</span><span class="sxs-lookup"><span data-stu-id="a128b-102">Rename Statistics</span></span>
  <span data-ttu-id="a128b-103">Você pode renomear um objeto de estatísticas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a128b-103">You can rename a statistics object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="a128b-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="a128b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a128b-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="a128b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a128b-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a128b-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a128b-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="a128b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a128b-108">**Para renomear um objeto de estatísticas, usando:**</span><span class="sxs-lookup"><span data-stu-id="a128b-108">**To rename a statistics object, using:**</span></span>  
  
     [<span data-ttu-id="a128b-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a128b-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a128b-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a128b-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a128b-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a128b-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a128b-112">Por padrão, a criação de um índice cria uma estatística nas colunas de chave desse índice.</span><span class="sxs-lookup"><span data-stu-id="a128b-112">By default, creating an index creates a statistic on the key columns of that index.</span></span> <span data-ttu-id="a128b-113">Portanto, a renomeação do índice renomeia automaticamente o objeto de estatísticas e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="a128b-113">Therefore, renaming the index automatically renames the statistics object, and vice versa.</span></span>  
  
 <span data-ttu-id="a128b-114">A alteração de qualquer parte de um nome de objeto pode quebrar scripts e procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="a128b-114">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="a128b-115">Em vez de renomear, é recomendável que você remova o objeto de estatísticas e recrie-o com o novo nome.</span><span class="sxs-lookup"><span data-stu-id="a128b-115">Instead of renaming, we recommend that you drop the statistics object and re-create it with the new name.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a128b-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="a128b-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a128b-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="a128b-117">Permissions</span></span>  
 <span data-ttu-id="a128b-118">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="a128b-118">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a128b-119">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a128b-119">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-statistics-object"></a><span data-ttu-id="a128b-120">Para renomear um objeto de estatísticas</span><span class="sxs-lookup"><span data-stu-id="a128b-120">To rename a statistics object</span></span>  
  
1.  <span data-ttu-id="a128b-121">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a128b-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a128b-122">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="a128b-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a128b-123">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a128b-123">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename N'AK_Employee_LoginID', N'AK_Emp_Login', N'STATISTICS';   
    GO  
    ```  
  
 <span data-ttu-id="a128b-124">Para obter mais informações, veja [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a128b-124">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
