---
title: Assinar ou cancelar a assinatura de um banco de dados a uma categoria de política | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.groupsubscription.f1
ms.assetid: d2c31769-7098-428e-ad9c-ef56541b7c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2b4ca6f804352b57b30b42012da93e0d031be8d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680371"
---
# <a name="subscribe-or-unsubscribe-a-database--to-a-policy-category"></a><span data-ttu-id="d1d51-102">Assinar ou cancelar a assinatura de um banco de dados a uma categoria de política</span><span class="sxs-lookup"><span data-stu-id="d1d51-102">Subscribe or Unsubscribe a Database  to a Policy Category</span></span>
  <span data-ttu-id="d1d51-103">Este tópico descreve como assinar ou cancelar a assinatura de um banco de dados para uma categoria de política no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1d51-103">This topic describes how to subscribe or unsubscribe a database to a policy category.in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d1d51-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="d1d51-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d1d51-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="d1d51-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d1d51-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="d1d51-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d1d51-107">**Para assinar ou cancelar a assinatura de um banco de dados a uma categoria de política usando:**</span><span class="sxs-lookup"><span data-stu-id="d1d51-107">**To subscribe or unsubscribe a database to a policy category., using:**</span></span>  
  
     [<span data-ttu-id="d1d51-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d1d51-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d1d51-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d1d51-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d1d51-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d1d51-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d1d51-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="d1d51-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d1d51-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="d1d51-112">Permissions</span></span>  
 <span data-ttu-id="d1d51-113">Requer associação na função de banco de dados fixa db_owner.</span><span class="sxs-lookup"><span data-stu-id="d1d51-113">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d1d51-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d1d51-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-subscribe-or-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="d1d51-115">Para assinar ou cancelar a assinatura de um banco de dados a uma categoria de política</span><span class="sxs-lookup"><span data-stu-id="d1d51-115">To subscribe or unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="d1d51-116">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o banco de dados em que você deseja gerenciar assinaturas de categoria.</span><span class="sxs-lookup"><span data-stu-id="d1d51-116">In **Object Explorer**, click the plus sign to expand the server that contains the database wherein you want to manage category subscriptions.</span></span>  
  
2.  <span data-ttu-id="d1d51-117">Clique no sinal de adição para expandir a pasta **Bancos de dados** .</span><span class="sxs-lookup"><span data-stu-id="d1d51-117">Click the plus sign to expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="d1d51-118">Clique com o botão direito do mouse no banco de dados em que você deseja gerenciar assinaturas de categoria, aponte para **Políticas**e selecione **Categorias**</span><span class="sxs-lookup"><span data-stu-id="d1d51-118">Right-click the database wherein you want to manage category subscriptions, point to **Policies**, and select **Categories**</span></span>  
  
     <span data-ttu-id="d1d51-119">As opções a seguir estão disponíveis na caixa de diálogo **Categorias** :</span><span class="sxs-lookup"><span data-stu-id="d1d51-119">The following options are available in the **Categories** dialog box:</span></span>  
  
     <span data-ttu-id="d1d51-120">Expandir coluna</span><span class="sxs-lookup"><span data-stu-id="d1d51-120">Expand column</span></span>  
     <span data-ttu-id="d1d51-121">Clique para expandir uma categoria de política.</span><span class="sxs-lookup"><span data-stu-id="d1d51-121">Click to expand a policy category.</span></span> <span data-ttu-id="d1d51-122">Assim, todas as políticas incluídas na categoria serão listadas.</span><span class="sxs-lookup"><span data-stu-id="d1d51-122">This lists all the policies that are included in the category.</span></span>  
  
     <span data-ttu-id="d1d51-123">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d1d51-123">**Name**</span></span>  
     <span data-ttu-id="d1d51-124">O nome da categoria de política.</span><span class="sxs-lookup"><span data-stu-id="d1d51-124">The name of the policy category.</span></span>  
  
     <span data-ttu-id="d1d51-125">**Assinado**</span><span class="sxs-lookup"><span data-stu-id="d1d51-125">**Subscribed**</span></span>  
     <span data-ttu-id="d1d51-126">Indica se o destino se inscreveu na categoria de política.</span><span class="sxs-lookup"><span data-stu-id="d1d51-126">Indicates whether the target has subscribed to the policy category.</span></span> <span data-ttu-id="d1d51-127">Se esta caixa de seleção for desabilitada, a categoria de política será definida como **Autorizar Assinaturas de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="d1d51-127">If this check box is disabled, the policy category is set for **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="d1d51-128">Isto significa que a categoria de política se aplica a todos os bancos de dados no servidor.</span><span class="sxs-lookup"><span data-stu-id="d1d51-128">This means that the policy category applies to all databases on the server.</span></span>  
  
     <span data-ttu-id="d1d51-129">**Política**</span><span class="sxs-lookup"><span data-stu-id="d1d51-129">**Policy**</span></span>  
     <span data-ttu-id="d1d51-130">Quando os grupos de políticas são expandidos, exibe as políticas da categoria de políticas.</span><span class="sxs-lookup"><span data-stu-id="d1d51-130">When policy groups are expanded, displays the policies in the policy category.</span></span>  
  
     <span data-ttu-id="d1d51-131">**Habilitado**</span><span class="sxs-lookup"><span data-stu-id="d1d51-131">**Enabled**</span></span>  
     <span data-ttu-id="d1d51-132">Indica se as políticas estão habilitadas ou desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="d1d51-132">Indicates whether the policies are enabled or disabled.</span></span>  
  
     <span data-ttu-id="d1d51-133">**Modo de Execução**</span><span class="sxs-lookup"><span data-stu-id="d1d51-133">**Execution Mode**</span></span>  
     <span data-ttu-id="d1d51-134">Exibe o modo de execução da política.</span><span class="sxs-lookup"><span data-stu-id="d1d51-134">Displays the execution mode of the policy.</span></span>  
  
     <span data-ttu-id="d1d51-135">**Histórico**</span><span class="sxs-lookup"><span data-stu-id="d1d51-135">**History**</span></span>  
     <span data-ttu-id="d1d51-136">Clique no hiperlink Exibir Histórico para abrir o Visualizador do Arquivo de Log e ver o histórico de políticas.</span><span class="sxs-lookup"><span data-stu-id="d1d51-136">Click the View History hyperlink to open the Log File Viewer to see the policy history.</span></span>  
  
4.  <span data-ttu-id="d1d51-137">Para assinar uma categoria de Gerenciamento Baseada em Políticas, marque a caixa de seleção de categoria na coluna **Assinado** .</span><span class="sxs-lookup"><span data-stu-id="d1d51-137">To subscribe to a Policy-Based Management category, select the category's check box under the **Subscribed** column.</span></span> <span data-ttu-id="d1d51-138">Para cancelar a assinatura de uma categoria, desmarque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="d1d51-138">To unsubscribe from a category, clear the check box.</span></span>  
  
5.  <span data-ttu-id="d1d51-139">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1d51-139">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d1d51-140">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d1d51-140">Using Transact-SQL</span></span>  
  
#### <a name="to-subscribe-a-database-to-a-policy-category"></a><span data-ttu-id="d1d51-141">Para assinar um banco de dados para uma categoria de política</span><span class="sxs-lookup"><span data-stu-id="d1d51-141">To subscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="d1d51-142">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1d51-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d1d51-143">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="d1d51-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d1d51-144">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="d1d51-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Adds a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_subscribe_to_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="d1d51-145">Para obter mais informações, veja [sp_syspolicy_subscribe_to_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d1d51-145">For more information, see [sp_syspolicy_subscribe_to_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span></span>  
  
#### <a name="to-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="d1d51-146">Para cancelar a assinatura de um banco de dados para uma categoria de política</span><span class="sxs-lookup"><span data-stu-id="d1d51-146">To unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="d1d51-147">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1d51-147">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d1d51-148">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="d1d51-148">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d1d51-149">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="d1d51-149">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Deletes a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_unsubscribe_from_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="d1d51-150">Para obter mais informações, veja [sp_syspolicy_unsubscribe_from_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d1d51-150">For more information, see [sp_syspolicy_unsubscribe_from_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span></span>  
  
  
