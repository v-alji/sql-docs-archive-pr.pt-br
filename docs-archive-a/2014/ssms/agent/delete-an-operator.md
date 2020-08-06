---
title: Excluir um operador | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- removing operators
- deleting operators
- dropping operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], deleting with Management Studio
ms.assetid: 2b7b8627-082d-4189-8584-abd3a9b604cf
author: stevestein
ms.author: sstein
ms.openlocfilehash: 75bea1c5c5fabff7ce55fe07a5181baa8f99e0fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569817"
---
# <a name="delete-an-operator"></a><span data-ttu-id="4e049-102">Delete an Operator</span><span class="sxs-lookup"><span data-stu-id="4e049-102">Delete an Operator</span></span>
  <span data-ttu-id="4e049-103">Este tópico descreve como remover um operador para que eles não recebam mais [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] notificações de alerta do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e049-103">This topic describes how to remove an operator so they no longer receive [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4e049-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="4e049-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4e049-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="4e049-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4e049-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4e049-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4e049-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="4e049-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4e049-108">**Para excluir um operador usando:**</span><span class="sxs-lookup"><span data-stu-id="4e049-108">**To delete an operator, using:**</span></span>  
  
     [<span data-ttu-id="4e049-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e049-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4e049-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e049-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4e049-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4e049-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4e049-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4e049-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4e049-113">Quando um operador é removido, todas as notificações associadas a ele também são eliminadas.</span><span class="sxs-lookup"><span data-stu-id="4e049-113">When an operator is removed, all the notifications associated with the operator are also removed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4e049-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="4e049-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4e049-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="4e049-115">Permissions</span></span>  
 <span data-ttu-id="4e049-116">Membros da função de servidor fixa **sysadmin** podem excluir operadores.</span><span class="sxs-lookup"><span data-stu-id="4e049-116">Members of the **sysadmin** fixed server role can delete operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4e049-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e049-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-operator"></a><span data-ttu-id="4e049-118">Para excluir um operador</span><span class="sxs-lookup"><span data-stu-id="4e049-118">To delete an operator</span></span>  
  
1.  <span data-ttu-id="4e049-119">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o operador que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="4e049-119">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to delete.</span></span>  
  
2.  <span data-ttu-id="4e049-120">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="4e049-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="4e049-121">Clique no sinal de adição para expandir a pasta **Operadores** .</span><span class="sxs-lookup"><span data-stu-id="4e049-121">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="4e049-122">Clique com o botão direito do mouse no operador a ser excluído e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="4e049-122">Right-click the operator that you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="4e049-123">Na caixa de diálogo **Excluir Objeto** , verifique se o operador correto está selecionado e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e049-123">In the **Delete Object** dialog box, make sure that the correct operator is selected, and then click **OK**.</span></span> <span data-ttu-id="4e049-124">Se desejar que outro operador receba os alertas e trabalhos enviados ao operador excluído, marque **Reatribuir a** e selecione um operador na lista.</span><span class="sxs-lookup"><span data-stu-id="4e049-124">If you want another operator to receive the alerts and jobs sent to the deleted operator, check **Reassign to** and select an operator in the list.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4e049-125">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e049-125">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-operator"></a><span data-ttu-id="4e049-126">Para excluir um operador</span><span class="sxs-lookup"><span data-stu-id="4e049-126">To delete an operator</span></span>  
  
1.  <span data-ttu-id="4e049-127">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e049-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4e049-128">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4e049-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4e049-129">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4e049-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes operator 'Test Operator' and reassigns all alerts and jobs sent to that operator to 'Fran??ois Ajenstat'  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_operator @name = 'Test Operator',  
        @reassign_to_operator = 'Fran??ois Ajenstat';  
    GO  
    ```  
  
 <span data-ttu-id="4e049-130">Para obter mais informações, consulte [sp_delete_operator &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4e049-130">For more information, see [sp_delete_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-operator-transact-sql).</span></span>  
  
  
