---
title: Excluir exibições | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- dropping views
- deleting views
- views [SQL Server], deleting
- removing views
ms.assetid: 6823c7f8-06ca-4bda-8482-7092f03d52a0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3e05724f7d6384d0407e915207ad60a1cdfb01b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569269"
---
# <a name="delete-views"></a><span data-ttu-id="687b0-102">Excluir exibições</span><span class="sxs-lookup"><span data-stu-id="687b0-102">Delete Views</span></span>
  <span data-ttu-id="687b0-103">Você pode excluir (remover) exibições no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="687b0-103">You can delete (drop) views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="687b0-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="687b0-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="687b0-105">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="687b0-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="687b0-106">Quando você descarta uma exibição, a definição da exibição e outras informações sobre ela são excluídas do catálogo do sistema.</span><span class="sxs-lookup"><span data-stu-id="687b0-106">When you drop a view, the definition of the view and other information about the view is deleted from the system catalog.</span></span> <span data-ttu-id="687b0-107">Todas as permissões para a exibição também são excluídas.</span><span class="sxs-lookup"><span data-stu-id="687b0-107">All permissions for the view are also deleted.</span></span>  
  
-   <span data-ttu-id="687b0-108">Qualquer exibição em uma tabela descartada pelo uso de `DROP TABLE` deve ser descartada explicitamente usando `DROP VIEW`.</span><span class="sxs-lookup"><span data-stu-id="687b0-108">Any view on a table that is dropped by using `DROP TABLE` must be dropped explicitly by using `DROP VIEW`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="687b0-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="687b0-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="687b0-110">Permissões</span><span class="sxs-lookup"><span data-stu-id="687b0-110">Permissions</span></span>  
 <span data-ttu-id="687b0-111">Requer a permissão ALTER na permissão SCHEMA ou CONTROL em OBJECT.</span><span class="sxs-lookup"><span data-stu-id="687b0-111">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="687b0-112">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="687b0-112">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="687b0-113">Para excluir uma exibição de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="687b0-113">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="687b0-114">No **Pesquisador de Objetos**, expanda o banco de dados que contém a exibição que deseja excluir e expanda a pasta **Exibições** .</span><span class="sxs-lookup"><span data-stu-id="687b0-114">In **Object Explorer**, expand the database that contains the view you want to delete, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="687b0-115">Clique com o botão direito do mouse na exibição que você deseja excluir e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="687b0-115">Right-click the view you want to delete and click **Delete**.</span></span>  
  
3.  <span data-ttu-id="687b0-116">Na caixa de diálogo **Excluir Objeto** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="687b0-116">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="687b0-117">Clique em **Mostrar dependências** na caixa de diálogo **excluir objeto** para abrir a caixa de diálogo _view_name_**dependências** .</span><span class="sxs-lookup"><span data-stu-id="687b0-117">Click **Show Dependencies** in the **Delete Object** dialog box to open the _view_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="687b0-118">Isso mostrará todos os objetos que dependem da exibição e todos os objetos dos quais a exibição depende.</span><span class="sxs-lookup"><span data-stu-id="687b0-118">This will show all of the objects that depend on the view and all of the objects on which the view depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="687b0-119">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="687b0-119">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="687b0-120">Para excluir uma exibição de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="687b0-120">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="687b0-121">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="687b0-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="687b0-122">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="687b0-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="687b0-123">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="687b0-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="687b0-124">O exemplo excluirá a exibição especificada somente se a exibição já existir.</span><span class="sxs-lookup"><span data-stu-id="687b0-124">The example deletes the specified view only if the view already exists.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    IF OBJECT_ID ('HumanResources.EmployeeHireDate', 'V') IS NOT NULL  
    DROP VIEW HumanResources.EmployeeHireDate;  
    GO  
    ```  
  
 <span data-ttu-id="687b0-125">Para obter mais informações, veja [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="687b0-125">For more information, see [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
  
