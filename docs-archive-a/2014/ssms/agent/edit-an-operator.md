---
title: Editar um operador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- modifying operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], modifying with Management Studio
ms.assetid: b2ba2168-ca0b-4b59-9007-4e1e4c30679e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 45ffb520e240dfd97002060370ff6dcf7c60d083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569023"
---
# <a name="edit-an-operator"></a><span data-ttu-id="3d2da-102">Editar um operador</span><span class="sxs-lookup"><span data-stu-id="3d2da-102">Edit an Operator</span></span>
  <span data-ttu-id="3d2da-103">Este tópico descreve como editar a disponibilidade de operadores para o recebimento de notificações e seus endereços de email, pager e net send no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d2da-103">This topic describes how to edit an operators' availability for receiving notifications and their e-mail, pager, and net send addresses in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3d2da-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="3d2da-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3d2da-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="3d2da-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3d2da-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="3d2da-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3d2da-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="3d2da-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3d2da-108">**Para editar um operador, usando:**</span><span class="sxs-lookup"><span data-stu-id="3d2da-108">**To edit an operator, using:**</span></span>  
  
     [<span data-ttu-id="3d2da-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3d2da-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3d2da-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3d2da-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3d2da-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3d2da-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3d2da-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="3d2da-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3d2da-113">As opções Pager e **net send** serão removidas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent em uma versão futura do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d2da-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3d2da-114">Evite usar esses recursos em novo trabalho de desenvolvimento e planeje modificar os aplicativos que os usam atualmente.</span><span class="sxs-lookup"><span data-stu-id="3d2da-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="3d2da-115">Observe que o SQL Server Agent deve ser configurado para usar o Database Mail a fim de enviar notificações por pager ou email a operadores.</span><span class="sxs-lookup"><span data-stu-id="3d2da-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="3d2da-116">Para obter mais informações, consulte [Atribuir alertas a um operador](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="3d2da-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="3d2da-117">gerencia trabalhos de forma fácil e com representação gráfica. Além disso, ele é recomendado para criar e gerenciar a infraestrutura de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="3d2da-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3d2da-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="3d2da-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3d2da-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="3d2da-119">Permissions</span></span>  
 <span data-ttu-id="3d2da-120">Somente membros da função de servidor fixa **sysadmin** podem editar operadores.</span><span class="sxs-lookup"><span data-stu-id="3d2da-120">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3d2da-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3d2da-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="3d2da-122">Para editar um operador</span><span class="sxs-lookup"><span data-stu-id="3d2da-122">To edit an operator</span></span>  
  
1.  <span data-ttu-id="3d2da-123">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o operador que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="3d2da-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to edit.</span></span>  
  
2.  <span data-ttu-id="3d2da-124">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="3d2da-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="3d2da-125">Clique no sinal de adição para expandir a pasta **Operadores** .</span><span class="sxs-lookup"><span data-stu-id="3d2da-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="3d2da-126">Clique com o botão direito do mouse no operador que você deseja editar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3d2da-126">Right-click the operator that you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="3d2da-127">Para obter mais informações sobre as opções disponíveis contidas na caixa de diálogo**Propriedades** de _operator_name_, consulte:</span><span class="sxs-lookup"><span data-stu-id="3d2da-127">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="3d2da-128">Propriedades do operador e novo operador &#40;página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="3d2da-128">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="3d2da-129">Propriedades do operador: nova página de notificações de &#40;de operador&#41;</span><span class="sxs-lookup"><span data-stu-id="3d2da-129">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="3d2da-130">Propriedades do operador &#40;página Histórico&#41;</span><span class="sxs-lookup"><span data-stu-id="3d2da-130">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="3d2da-131">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d2da-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3d2da-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3d2da-132">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="3d2da-133">Para editar um operador</span><span class="sxs-lookup"><span data-stu-id="3d2da-133">To edit an operator</span></span>  
  
1.  <span data-ttu-id="3d2da-134">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d2da-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3d2da-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="3d2da-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3d2da-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3d2da-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- updates the operator status to enabled, and sets the days   
    -- (from Monday through Friday, from 8 A.M. through 5 P.M.) when the operator can be paged.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 1,  
        @email_address = N'fran??oisa',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 64 ;  
    GO  
    ```  
  
 <span data-ttu-id="3d2da-137">Para obter mais informações, consulte [sp_update_operator &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3d2da-137">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  
