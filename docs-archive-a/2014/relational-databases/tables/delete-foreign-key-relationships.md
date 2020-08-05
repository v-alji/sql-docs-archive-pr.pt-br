---
title: Excluir relações de chaves estrangeiras | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], deleting
- removing foreign keys
- deleting foreign keys
ms.assetid: 9c9e9ae4-9e03-4137-acb6-b18928a0c4ca
author: stevestein
ms.author: sstein
ms.openlocfilehash: 86ae466b9fce53073bfc0645c753246023ff3269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573878"
---
# <a name="delete-foreign-key-relationships"></a><span data-ttu-id="5aceb-102">Excluir relações de chaves estrangeiras</span><span class="sxs-lookup"><span data-stu-id="5aceb-102">Delete Foreign Key Relationships</span></span>
  <span data-ttu-id="5aceb-103">Você pode excluir uma restrição de chave estrangeira no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5aceb-103">You can delete a foreign key constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5aceb-104">Excluir uma restrição de chave estrangeira remove o requisito para forçar uma integridade referencial.</span><span class="sxs-lookup"><span data-stu-id="5aceb-104">Deleting a foreign key constraint removes the requirement to enforce referential integrity.</span></span>  
  
 <span data-ttu-id="5aceb-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="5aceb-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5aceb-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="5aceb-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5aceb-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="5aceb-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5aceb-108">**Para excluir uma restrição de chave estrangeira usando:**</span><span class="sxs-lookup"><span data-stu-id="5aceb-108">**To delete a foreign key constraint, using:**</span></span>  
  
     [<span data-ttu-id="5aceb-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5aceb-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5aceb-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5aceb-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5aceb-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5aceb-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5aceb-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="5aceb-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5aceb-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="5aceb-113">Permissions</span></span>  
 <span data-ttu-id="5aceb-114">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="5aceb-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5aceb-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5aceb-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="5aceb-116">Para excluir uma restrição de chave estrangeira</span><span class="sxs-lookup"><span data-stu-id="5aceb-116">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="5aceb-117">No **Pesquisador de Objetos**, expanda a tabela com a restrição e expanda **Chaves**.</span><span class="sxs-lookup"><span data-stu-id="5aceb-117">In **Object Explorer**, expand the table with the constraint and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="5aceb-118">Clique com o botão direito do mouse na restrição e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="5aceb-118">Right-click the constraint and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="5aceb-119">Na caixa de diálogo **Excluir Objeto** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5aceb-119">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5aceb-120">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5aceb-120">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="5aceb-121">Para excluir uma restrição de chave estrangeira</span><span class="sxs-lookup"><span data-stu-id="5aceb-121">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="5aceb-122">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5aceb-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5aceb-123">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5aceb-123">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5aceb-124">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="5aceb-124">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.DocExe   
    DROP CONSTRAINT FK_Column_B;   
    GO  
    ```  
  
 <span data-ttu-id="5aceb-125">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5aceb-125">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
