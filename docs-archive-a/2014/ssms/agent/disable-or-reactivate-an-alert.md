---
title: Desabilitar ou reativar um alerta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], reactivating
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- alerts [SQL Server], disabling
- reactivating alerts
- removing alerts
ms.assetid: 4cb37dc6-1134-405d-8590-58b44dcf63b2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3eec4ea7288f4847c0e9b861d80f23eb9c9ddba8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682077"
---
# <a name="disable-or-reactivate-an-alert"></a><span data-ttu-id="10999-102">Disable or Reactivate an Alert</span><span class="sxs-lookup"><span data-stu-id="10999-102">Disable or Reactivate an Alert</span></span>
  <span data-ttu-id="10999-103">Este tópico descreve como desabilitar ou reativar um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerta do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10999-103">This topic describes how to disable or reactivate a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="10999-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="10999-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="10999-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="10999-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="10999-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="10999-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="10999-107">**Para desabilitar ou reativar um alerta usando:**</span><span class="sxs-lookup"><span data-stu-id="10999-107">**To disable or reactivate an alert, using:**</span></span>  
  
     [<span data-ttu-id="10999-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10999-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="10999-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="10999-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="10999-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="10999-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="10999-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="10999-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="10999-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="10999-112">Permissions</span></span>  
 <span data-ttu-id="10999-113">Por padrão, os membros da função de servidor fixa **sysadmin** podem editar as informações em um alerta.</span><span class="sxs-lookup"><span data-stu-id="10999-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="10999-114">Deve ser concedida a outros usuários a função de banco de dados fixa **SQLAgentOperatorRole** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="10999-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="10999-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10999-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="10999-116">Para desabilitar ou reativar um alerta</span><span class="sxs-lookup"><span data-stu-id="10999-116">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="10999-117">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o alerta que você deseja desabilitar ou reativar.</span><span class="sxs-lookup"><span data-stu-id="10999-117">In **Object Explorer**, click the plus sign to expand server that contains the alert you wish to disable or reactivate.</span></span>  
  
2.  <span data-ttu-id="10999-118">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="10999-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="10999-119">Clique no sinal de adição para expandir a pasta **Alertas** .</span><span class="sxs-lookup"><span data-stu-id="10999-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="10999-120">Clique com o botão direito do mouse no alerta que deseja habilitar e selecione **Habilitar** . Para desabilitar um alerta, clique com o botão direito do mouse no alerta que deseja desabilitar e selecione **Desabilitar**.</span><span class="sxs-lookup"><span data-stu-id="10999-120">Right-click the alert you wish to enable and select **Enable** To disable an alert, right-click the alert you want to disable and select **Disable**.</span></span>  
  
5.  <span data-ttu-id="10999-121">É exibida a caixa de diálogo **Desabilitar Alerta** ou **Habilitar Alerta** , mostrando o status do processo.</span><span class="sxs-lookup"><span data-stu-id="10999-121">The **Disable Alert** or **Enable Alert** dialog box displays showing the status of the process.</span></span> <span data-ttu-id="10999-122">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="10999-122">When finished, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="10999-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="10999-123">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="10999-124">Para desabilitar ou reativar um alerta</span><span class="sxs-lookup"><span data-stu-id="10999-124">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="10999-125">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10999-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="10999-126">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="10999-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="10999-127">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="10999-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="10999-128">Para obter mais informações, consulte [sp_update_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="10999-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  
