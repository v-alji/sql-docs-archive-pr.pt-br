---
title: Gerenciar categorias de política | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.policycategories.f1
ms.assetid: d188a819-731f-4029-98aa-780d3299a0ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 168d05dd88286263da1dca5456a2c6072e946786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572007"
---
# <a name="manage-policy-categories"></a><span data-ttu-id="57f09-102">Gerenciar Categorias de Política</span><span class="sxs-lookup"><span data-stu-id="57f09-102">Manage Policy Categories</span></span>
  <span data-ttu-id="57f09-103">Este tópico descreve como aplicar uma ou todas as políticas disponíveis em uma categoria a toda a instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57f09-103">This topic describes how to apply any or all available policies in a category to the whole instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="57f09-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="57f09-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="57f09-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="57f09-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="57f09-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="57f09-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="57f09-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="57f09-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="57f09-108">**Para aplicar políticas de categoria a uma instância do SQL Server usando:**</span><span class="sxs-lookup"><span data-stu-id="57f09-108">**To apply category policies to a SQL Server instance, using:**</span></span>  
  
     [<span data-ttu-id="57f09-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="57f09-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="57f09-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57f09-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="57f09-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="57f09-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="57f09-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="57f09-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="57f09-113">Ao usar o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], se a caixa de seleção **Autorizar Assinaturas de Banco de Dados** não estiver selecionada, a categoria de política deve ser aplicada individualmente a cada parte relevante do servidor, como em um ou mais bancos de dados e tabelas.</span><span class="sxs-lookup"><span data-stu-id="57f09-113">When using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], if the **Mandate Database Subscriptions** check box is not selected, the policy category must be individually applied to each relevant portion of the server, such as one or more databases or tables.</span></span>  
  
-   <span data-ttu-id="57f09-114">Se você especificar uma categoria de política que não existe, uma nova categoria de política será criada e a assinatura será designada para todos os bancos de dados quando você executar o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="57f09-114">If you specify a policy category that does not exist, a new policy category is created and the subscription is mandated for all databases when you execute the stored procedure.</span></span> <span data-ttu-id="57f09-115">Se você desmarcar a assinatura designada para a nova categoria, a assinatura só se aplicará ao banco de dados que você especificou como *target_object*.</span><span class="sxs-lookup"><span data-stu-id="57f09-115">If you then clear the mandated subscription for the new category, the subscription will only apply for the database that you specified as the *target_object*.</span></span> <span data-ttu-id="57f09-116">Para obter mais informações sobre como alterar uma configuração de assinatura designada, veja [sp_syspolicy_update_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="57f09-116">For more information about how to change a mandated subscription setting, see [sp_syspolicy_update_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="57f09-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="57f09-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="57f09-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="57f09-118">Permissions</span></span>  
 <span data-ttu-id="57f09-119">Este procedimento armazenado é executado no contexto de seu proprietário atual.</span><span class="sxs-lookup"><span data-stu-id="57f09-119">This stored procedure runs in the context of the current owner of the stored procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="57f09-120">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="57f09-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="57f09-121">Para aplicar políticas de categoria a uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="57f09-121">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="57f09-122">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você aplicará políticas de categoria.</span><span class="sxs-lookup"><span data-stu-id="57f09-122">In **Object Explorer**, click the plus sign to expand the server where you will apply category policies.</span></span>  
  
2.  <span data-ttu-id="57f09-123">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="57f09-123">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="57f09-124">Clique com o botão direito do mouse em **Gerenciamento de Política** e selecione **Gerenciar Categorias**.</span><span class="sxs-lookup"><span data-stu-id="57f09-124">Right-click **Policy Management** and select **Manage Categories**.</span></span>  
  
     <span data-ttu-id="57f09-125">As seguintes informações estão disponíveis na caixa de diálogo **Gerenciar Categorias de Política** :</span><span class="sxs-lookup"><span data-stu-id="57f09-125">The following information is available in the **Manage Policy Categories** dialog box:</span></span>  
  
     <span data-ttu-id="57f09-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="57f09-126">**Name**</span></span>  
     <span data-ttu-id="57f09-127">O nome da categoria de política.</span><span class="sxs-lookup"><span data-stu-id="57f09-127">The name of the policy category.</span></span>  
  
     <span data-ttu-id="57f09-128">**Autorizar Assinaturas de Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="57f09-128">**Mandate Database Subscriptions**</span></span>  
     <span data-ttu-id="57f09-129">Obriga que todos os bancos de dados na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] imponham políticas na categoria de política.</span><span class="sxs-lookup"><span data-stu-id="57f09-129">Forces all databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to enforce policies in the policy category.</span></span>  
  
4.  <span data-ttu-id="57f09-130">Marque ou desmarque uma ou todas as caixas de seleção em **Autorizar Assinaturas de Banco de Dados** para aplicar essa categoria de política à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="57f09-130">Select or clear any or all check boxes under **Mandate Database Subscriptions** to apply that policy category to the SQL Server instance.</span></span>  
  
5.  <span data-ttu-id="57f09-131">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="57f09-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="57f09-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57f09-132">Using Transact-SQL</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="57f09-133">Para aplicar políticas de categoria a uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="57f09-133">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="57f09-134">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57f09-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="57f09-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="57f09-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="57f09-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="57f09-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    -- configures the specified database to subscribe to a policy category that is named 'Table Naming Policies'.  
    EXEC dbo.sp_syspolicy_add_policy_category_subscription @target_type = N'DATABASE'  
    , @target_object = N'AdventureWorks2012'  
    , @policy_category = N'Table Naming Policies';  
    GO  
    ```  
  
 <span data-ttu-id="57f09-137">Para obter mais informações, veja [sp_syspolicy_add_policy_category_subscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="57f09-137">For more information, see [sp_syspolicy_add_policy_category_subscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span></span>  
  
  
