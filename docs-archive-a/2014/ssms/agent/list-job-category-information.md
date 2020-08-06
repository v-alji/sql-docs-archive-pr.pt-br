---
title: Listar informações de categoria do trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 0fc668d4-6244-4fef-b90e-62d2c776cd7c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 924e2b064980b2ea7068230610414262995da1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683306"
---
# <a name="list-job-category-information"></a><span data-ttu-id="c7b78-102">Listar informações de categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="c7b78-102">List Job Category Information</span></span>
  <span data-ttu-id="c7b78-103">Como listar informações de categoria de trabalho no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="c7b78-103">How to list job category information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  

  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c7b78-104">Segurança</span><span class="sxs-lookup"><span data-stu-id="c7b78-104">Security</span></span>  
 <span data-ttu-id="c7b78-105">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="c7b78-105">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="c7b78-106">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c7b78-106">Using Transact-SQL</span></span>  
  
#### <a name="to-list-job-category-information"></a><span data-ttu-id="c7b78-107">Para listar informações de categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="c7b78-107">To list job category information</span></span>  
  
1.  <span data-ttu-id="c7b78-108">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7b78-108">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c7b78-109">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c7b78-109">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c7b78-110">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c7b78-110">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- returns information about jobs that are administered locally  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_category  
        @type = N'LOCAL' ;  
    GO  
    ```  
  
 <span data-ttu-id="c7b78-111">Para obter mais informações, consulte [sp_help_category &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c7b78-111">For more information, see [sp_help_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span></span>  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="c7b78-112">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c7b78-112">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="c7b78-113">**Para listar informações de categoria de trabalho**</span><span class="sxs-lookup"><span data-stu-id="c7b78-113">**To list job category information**</span></span>  
  
 <span data-ttu-id="c7b78-114">Use a classe `JobCategory` usando uma linguagem de programação que você possa escolher, como Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7b78-114">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell..</span></span> <span data-ttu-id="c7b78-115">Para obter mais informações, consulte [Guia de programação do SQL Server Management Objects &#40;SMO&#41;](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span><span class="sxs-lookup"><span data-stu-id="c7b78-115">For more information, see [SQL Server Management Objects &#40;SMO&#41; Programming Guide](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span></span>  
