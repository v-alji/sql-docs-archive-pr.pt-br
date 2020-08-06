---
title: Conceder uma permissão a uma entidade de segurança | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Grant permission to a principal
ms.assetid: 4107389d-05b6-4aa3-9fa8-95b40cdf05dc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4256d62bdeac2d79c51e5f3792c991e0e3b15096
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685513"
---
# <a name="grant-a-permission-to-a-principal"></a><span data-ttu-id="845fa-102">Conceder uma permissão a uma entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="845fa-102">Grant a Permission to a Principal</span></span>
  <span data-ttu-id="845fa-103">Este tópico descreve como conceder permissão a uma entidade de segurança no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="845fa-103">This topic describes how to grant permission to a principal in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="845fa-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="845fa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="845fa-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="845fa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="845fa-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="845fa-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="845fa-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="845fa-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="845fa-108">**Para conceder permissão a uma entidade de segurança usando:**</span><span class="sxs-lookup"><span data-stu-id="845fa-108">**To grant permission to a principal, using:**</span></span>  
  
     [<span data-ttu-id="845fa-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="845fa-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="845fa-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="845fa-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="845fa-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="845fa-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="845fa-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="845fa-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="845fa-113">Considere as práticas recomendadas a seguir que podem facilitar o gerenciamento de permissões.</span><span class="sxs-lookup"><span data-stu-id="845fa-113">Consider the following best practices that can make managing permissions easier.</span></span>  
  
-   <span data-ttu-id="845fa-114">Conceda permissão para funções, em vez de logons individuais ou usuários.</span><span class="sxs-lookup"><span data-stu-id="845fa-114">Grant permission to roles, instead of individual logins or users.</span></span> <span data-ttu-id="845fa-115">Quando um indivíduo for substituído por outro, remova o indivíduo que está deixando a função e adicione o novo indivíduo a ela.</span><span class="sxs-lookup"><span data-stu-id="845fa-115">When one individual is replaced by another, remove the departing individual from the role and add the new individual to the role.</span></span> <span data-ttu-id="845fa-116">As muitas permissões que podem ser associadas à função estarão automaticamente disponíveis para o novo indivíduo.</span><span class="sxs-lookup"><span data-stu-id="845fa-116">The many permissions that might be associated with the role will automatically be available to the new individual.</span></span> <span data-ttu-id="845fa-117">Se várias pessoas em uma organização precisarem das mesmas permissões, adicionar cada uma dessas pessoas à função concederá as mesmas permissões.</span><span class="sxs-lookup"><span data-stu-id="845fa-117">If several people in an organization require the same permissions, adding each of them to the role will grant them the same permissions.</span></span>  
  
-   <span data-ttu-id="845fa-118">Configure protegíveis semelhantes (tabelas, exibições e procedimentos) para pertencer a um esquema e conceder permissões ao esquema.</span><span class="sxs-lookup"><span data-stu-id="845fa-118">Configure similar securables (tables, views, and procedures) to be owned by a schema, then grant permissions to the schema.</span></span> <span data-ttu-id="845fa-119">Por exemplo, o esquema de folha de pagamento pode possuir várias tabelas, exibições e procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="845fa-119">For example, the payroll schema might own several tables, views, and stored procedures.</span></span> <span data-ttu-id="845fa-120">Quando o acesso é concedido ao esquema, todas as permissões necessárias para executar a função de folha de pagamento podem ser concedidas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="845fa-120">By granting access to the schema, all the necessary permissions to perform the payroll function can be granted at the same time.</span></span> <span data-ttu-id="845fa-121">Para obter mais informações sobre quais protegíveis podem receber permissões, consulte [Securables](../securables.md).</span><span class="sxs-lookup"><span data-stu-id="845fa-121">For more information about what securables can be granted permissions, see [Securables](../securables.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="845fa-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="845fa-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="845fa-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="845fa-123">Permissions</span></span>  
 <span data-ttu-id="845fa-124">O concessor (ou o principal especificado com a opção AS) deve ter a permissão em si com GRANT OPTION ou uma permissão superior que implique na concessão da permissão.</span><span class="sxs-lookup"><span data-stu-id="845fa-124">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="845fa-125">Membros da função de servidor fixa **sysadmin** podem conceder qualquer permissão.</span><span class="sxs-lookup"><span data-stu-id="845fa-125">Members of the **sysadmin** fixed server role can grant any permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="845fa-126">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="845fa-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="845fa-127">Para conceder permissão a uma entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="845fa-127">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="845fa-128">No Pesquisador de Objetos, expanda o banco de dados que contém o objeto para o qual você deseja conceder permissões.</span><span class="sxs-lookup"><span data-stu-id="845fa-128">In Object Explorer, expand the database that contains the object to which you want to grant permissions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="845fa-129">Estas etapas lidam especificamente com a concessão de permissões a um procedimento armazenado, mas você pode usar etapas semelhantes para adicionar permissões a tabelas, exibições, funções e assemblies, bem como a outro protegíveis.</span><span class="sxs-lookup"><span data-stu-id="845fa-129">These steps deal specifically with granting permissions to a stored procedure, but you can use similar steps to add permissions to tables, views, functions, and assemblies, as well as other securables.</span></span> <span data-ttu-id="845fa-130">Para obter mais informações, veja [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="845fa-130">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)</span></span>  
  
2.  <span data-ttu-id="845fa-131">Expanda a pasta **Programação** .</span><span class="sxs-lookup"><span data-stu-id="845fa-131">Expand the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="845fa-132">Expanda a pasta **Procedimentos Armazenados** .</span><span class="sxs-lookup"><span data-stu-id="845fa-132">Expand the **Stored Procedures** folder.</span></span>  
  
4.  <span data-ttu-id="845fa-133">Clique com o botão direito do mouse em um procedimento armazenado e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="845fa-133">Right-click a stored procedure and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="845fa-134">Na caixa de diálogo **Propriedades do procedimento armazenado –**_stored_procedure_name_ , em selecionar uma página, selecione **permissões**.</span><span class="sxs-lookup"><span data-stu-id="845fa-134">In the **Stored Procedure Properties -**_stored_procedure_name_ dialog box, under select a page, select **Permissions**.</span></span> <span data-ttu-id="845fa-135">Use essa página para adicionar usuários ou funções ao procedimento armazenado e especificar as permissões que esses usuários ou funções têm.</span><span class="sxs-lookup"><span data-stu-id="845fa-135">Use this page to add users or roles to the stored procedure and specify the permissions those users or roles have.</span></span>  
  
6.  <span data-ttu-id="845fa-136">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="845fa-136">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="845fa-137">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="845fa-137">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="845fa-138">Para conceder permissão a uma entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="845fa-138">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="845fa-139">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="845fa-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="845fa-140">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="845fa-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="845fa-141">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="845fa-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Grants EXECUTE permission on stored procedure HumanResources.uspUpdateEmployeeHireInfo to an application role called Recruiting11.   
    USE AdventureWorks2012;  
    GO  
    GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
        TO Recruiting11;  
    GO  
    ```  
  
 <span data-ttu-id="845fa-142">Para obter mais informações, veja [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) e [Permissões de objeto GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="845fa-142">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="845fa-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="845fa-143">See Also</span></span>  
 [<span data-ttu-id="845fa-144">Entidades &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="845fa-144">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
