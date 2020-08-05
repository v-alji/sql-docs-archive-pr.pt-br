---
title: Exibir informações sobre um operador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- viewing operators
- operators (users) [Database Engine], viewing with Management Studio
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- displaying operators
ms.assetid: 92c82cdf-f704-444e-9539-82aea7fe6fb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 680b90401f800a9c435bdae33b8e55385541cc4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572321"
---
# <a name="view-information-about-an-operator"></a><span data-ttu-id="8d423-102">Exibir informações sobre um operador</span><span class="sxs-lookup"><span data-stu-id="8d423-102">View Information About an Operator</span></span>
  <span data-ttu-id="8d423-103">Este tópico descreve como exibir informações sobre um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] operador de agente no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ou o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d423-103">This topic describes how to view information about a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8d423-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8d423-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8d423-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8d423-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8d423-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="8d423-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8d423-107">**Para exibir informações sobre um operador, usando:**</span><span class="sxs-lookup"><span data-stu-id="8d423-107">**To view information about an operator, using:**</span></span>  
  
     [<span data-ttu-id="8d423-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8d423-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8d423-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8d423-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8d423-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8d423-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8d423-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="8d423-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8d423-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="8d423-112">Permissions</span></span>  
 <span data-ttu-id="8d423-113">Por padrão, os membros da função de servidor fixa **sysadmin** podem executar este procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="8d423-113">By default, members of the **sysadmin** fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="8d423-114">Deve ser concedida a outros usuários uma das seguintes funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no banco de dados **msdb** :</span><span class="sxs-lookup"><span data-stu-id="8d423-114">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="8d423-115">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="8d423-115">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="8d423-116">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="8d423-116">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="8d423-117">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="8d423-117">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="8d423-118">Para obter detalhes sobre as permissões dessas funções, consulte [Funções de banco de dados fixas do SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8d423-118">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8d423-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8d423-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="8d423-120">Para exibir informações sobre um operador</span><span class="sxs-lookup"><span data-stu-id="8d423-120">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="8d423-121">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o operador que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="8d423-121">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to view.</span></span>  
  
2.  <span data-ttu-id="8d423-122">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="8d423-122">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="8d423-123">Clique no sinal de adição para expandir a pasta **Operadores** .</span><span class="sxs-lookup"><span data-stu-id="8d423-123">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="8d423-124">Clique com o botão direito do mouse no operador que você deseja exibir e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8d423-124">Right-click the operator that you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="8d423-125">Para obter mais informações sobre as opções disponíveis contidas na caixa de diálogo**Propriedades** de _operator_name_, consulte:</span><span class="sxs-lookup"><span data-stu-id="8d423-125">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="8d423-126">Propriedades do operador e novo operador &#40;página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="8d423-126">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="8d423-127">Propriedades do operador: nova página de notificações de &#40;de operador&#41;</span><span class="sxs-lookup"><span data-stu-id="8d423-127">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="8d423-128">Propriedades do operador &#40;página Histórico&#41;</span><span class="sxs-lookup"><span data-stu-id="8d423-128">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="8d423-129">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d423-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8d423-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8d423-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="8d423-131">Para exibir informações sobre um operador</span><span class="sxs-lookup"><span data-stu-id="8d423-131">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="8d423-132">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d423-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8d423-133">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8d423-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8d423-134">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8d423-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about operator Fran??ois Ajenstat   
    -- This example assumes that the operator exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_operator  
        @operator_name = N'Fran??ois Ajenstat' ;  
    GO  
    ```  
  
 <span data-ttu-id="8d423-135">Para obter mais informações, consulte [sp_help_operator &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8d423-135">For more information, see [sp_help_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span></span>  
  
  
