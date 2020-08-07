---
title: Editar um alerta | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], modifying
- modifying alerts
ms.assetid: f518e528-cc8f-446a-b37d-98505b86e430
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1eae606b3c2ca4c18d088e650e774986d4e31387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574999"
---
# <a name="edit-an-alert"></a><span data-ttu-id="f661e-102">Edit an Alert</span><span class="sxs-lookup"><span data-stu-id="f661e-102">Edit an Alert</span></span>
  <span data-ttu-id="f661e-103">Este tópico descreve como editar um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerta do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f661e-103">This topic describes how to edit a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f661e-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="f661e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f661e-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="f661e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f661e-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="f661e-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f661e-107">**Para editar um alerta usando:**</span><span class="sxs-lookup"><span data-stu-id="f661e-107">**To edit an alert, using:**</span></span>  
  
     [<span data-ttu-id="f661e-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f661e-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f661e-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f661e-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f661e-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f661e-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f661e-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="f661e-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f661e-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="f661e-112">Permissions</span></span>  
 <span data-ttu-id="f661e-113">Por padrão, os membros da função de servidor fixa **sysadmin** podem editar as informações em um alerta.</span><span class="sxs-lookup"><span data-stu-id="f661e-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="f661e-114">Deve ser concedida a outros usuários a função de banco de dados fixa **SQLAgentOperatorRole** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="f661e-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f661e-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f661e-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="f661e-116">Para editar um alerta</span><span class="sxs-lookup"><span data-stu-id="f661e-116">To edit an alert</span></span>  
  
1.  <span data-ttu-id="f661e-117">No **Pesquisador de Objetos** , clique no sinal de mais para expandir o servidor que contém o alerta que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="f661e-117">In **Object Explorer,** click the plus sign to expand the server containing the alert you want to edit.</span></span>  
  
2.  <span data-ttu-id="f661e-118">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="f661e-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="f661e-119">Clique no sinal de adição para expandir a pasta **Alertas** .</span><span class="sxs-lookup"><span data-stu-id="f661e-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="f661e-120">Clique com o botão direito do mouse no alerta que deseja editar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f661e-120">Right-click the alert you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="f661e-121">Atualize as propriedades do alerta nas páginas **Geral**, **Resposta**e **Opções** .</span><span class="sxs-lookup"><span data-stu-id="f661e-121">Update the alert properties on the **General**, **Response**, and **Options** pages.</span></span>  
  
6.  <span data-ttu-id="f661e-122">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f661e-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f661e-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f661e-123">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="f661e-124">Para editar um alerta</span><span class="sxs-lookup"><span data-stu-id="f661e-124">To edit an alert</span></span>  
  
1.  <span data-ttu-id="f661e-125">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f661e-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f661e-126">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f661e-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f661e-127">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="f661e-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="f661e-128">Para obter mais informações, consulte [sp_update_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f661e-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  
