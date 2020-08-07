---
title: Excluir um alerta | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], deleting
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- removing alerts
ms.assetid: c982b208-e2d1-4d34-8cee-940b9baf6586
author: stevestein
ms.author: sstein
ms.openlocfilehash: 15fdae19b150a5a06a32e91ec1947a0acfa5f900
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576112"
---
# <a name="delete-an-alert"></a><span data-ttu-id="4f35d-102">Delete an Alert</span><span class="sxs-lookup"><span data-stu-id="4f35d-102">Delete an Alert</span></span>
  <span data-ttu-id="4f35d-103">Este tópico descreve como excluir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas de agente no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f35d-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4f35d-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="4f35d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4f35d-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="4f35d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4f35d-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4f35d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4f35d-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="4f35d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4f35d-108">**Para excluir um alerta, usando:**</span><span class="sxs-lookup"><span data-stu-id="4f35d-108">**To delete an alert, using:**</span></span>  
  
     [<span data-ttu-id="4f35d-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f35d-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4f35d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f35d-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4f35d-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4f35d-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4f35d-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4f35d-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4f35d-113">A remoção de um alerta também remove qualquer notificação associada a ele.</span><span class="sxs-lookup"><span data-stu-id="4f35d-113">Removing an alert also removes any notifications associated with the alert.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4f35d-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="4f35d-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4f35d-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="4f35d-115">Permissions</span></span>  
 <span data-ttu-id="4f35d-116">Por padrão, somente membros da função de servidor fixa **sysadmin** podem excluir alertas.</span><span class="sxs-lookup"><span data-stu-id="4f35d-116">By default, only members of the **sysadmin** fixed server role can delete alerts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4f35d-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f35d-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="4f35d-118">Para excluir um alerta</span><span class="sxs-lookup"><span data-stu-id="4f35d-118">To delete an alert</span></span>  
  
1.  <span data-ttu-id="4f35d-119">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor que contém o alerta do SQL Server Agent que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="4f35d-119">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent alert that you want to delete.</span></span>  
  
2.  <span data-ttu-id="4f35d-120">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="4f35d-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="4f35d-121">Clique no sinal de adição para expandir a pasta **Alertas** .</span><span class="sxs-lookup"><span data-stu-id="4f35d-121">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="4f35d-122">Clique com o botão direito do mouse no alerta a ser excluído e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="4f35d-122">Right-click the alert you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="4f35d-123">Na caixa de diálogo **Excluir Objeto** , confirme se o alerta correto está selecionado e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f35d-123">In the **Delete Object** dialog box, confirm that the correct alert is selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4f35d-124">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f35d-124">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="4f35d-125">Para excluir um alerta</span><span class="sxs-lookup"><span data-stu-id="4f35d-125">To delete an alert</span></span>  
  
1.  <span data-ttu-id="4f35d-126">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f35d-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4f35d-127">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4f35d-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4f35d-128">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4f35d-128">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the SQL Server Agent alert called 'Test Alert.'  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_alert  
       @name = N'Test Alert' ;  
    GO  
    ```  
  
 <span data-ttu-id="4f35d-129">Para obter mais informações, consulte s[sp_delete_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4f35d-129">For more information, see s[sp_delete_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span></span>  
  
  
