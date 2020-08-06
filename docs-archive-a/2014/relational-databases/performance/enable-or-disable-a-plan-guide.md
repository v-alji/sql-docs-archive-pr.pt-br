---
title: Habilitar ou desabilitar um guia de plano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], disabling
- enabling plan guides
- plan guides [SQL Server], enabling
- disabling plan guides
ms.assetid: b00ab550-5308-4cb8-8330-483cd1d25654
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2611697e479d318245d8306b28c826e744ae85ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683512"
---
# <a name="enable-or-disable-a-plan-guide"></a><span data-ttu-id="eb87d-102">Habilitar ou desabilitar um guia de plano</span><span class="sxs-lookup"><span data-stu-id="eb87d-102">Enable or Disable a Plan Guide</span></span>
  <span data-ttu-id="eb87d-103">Você pode desabilitar e habilitar guias de plano no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb87d-103">You can disable and enable plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="eb87d-104">Um único ou todos os guias de plano de um banco de dados podem ser habilitados ou desabilitados.</span><span class="sxs-lookup"><span data-stu-id="eb87d-104">Either a single plan guides or all plan guides in a database can be enabled or disabled.</span></span>  
  
 <span data-ttu-id="eb87d-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="eb87d-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="eb87d-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="eb87d-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="eb87d-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="eb87d-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="eb87d-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="eb87d-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="eb87d-109">**Para desabilitar e habilitar guias de plano usando:**</span><span class="sxs-lookup"><span data-stu-id="eb87d-109">**To disable and enable plan guides, using:**</span></span>  
  
     [<span data-ttu-id="eb87d-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eb87d-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="eb87d-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eb87d-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eb87d-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="eb87d-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="eb87d-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="eb87d-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="eb87d-114">A tentativa de cancelar ou modificar uma função, procedimento armazenado ou gatilho DML referenciado por um guia de plano, habilitado ou desabilitado, provoca um erro.</span><span class="sxs-lookup"><span data-stu-id="eb87d-114">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="eb87d-115">Sempre verifique se há dependências antes de cancelar ou modificar qualquer um dos objetos listados acima.</span><span class="sxs-lookup"><span data-stu-id="eb87d-115">Always check for dependencies before dropping or modifying any of the objects listed above.</span></span>  
  
-   <span data-ttu-id="eb87d-116">A desabilitação de um guia de plano desabilitado ou a habilitação de um guia de plano habilitado não tem nenhum efeito e ocorre sem erro.</span><span class="sxs-lookup"><span data-stu-id="eb87d-116">Disabling a disabled plan guide or enabling an enabled plan guide has no effect and runs without error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="eb87d-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="eb87d-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="eb87d-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="eb87d-118">Permissions</span></span>  
 <span data-ttu-id="eb87d-119">A habilitação ou desabilitação de um guia de plano OBJECT exige a permissão ALTER no objeto (por exemplo: função, procedimento armazenado) que é referenciado pelo guia de plano.</span><span class="sxs-lookup"><span data-stu-id="eb87d-119">Disabling or enabling an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="eb87d-120">Todos os outros guias de plano requerem permissão ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="eb87d-120">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="eb87d-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eb87d-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="eb87d-122">Para habilitar ou desabilitar um guia de plano</span><span class="sxs-lookup"><span data-stu-id="eb87d-122">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="eb87d-123">Clique no sinal de adição para expandir o banco de dados no qual você deseja desabilitar ou habilitar um guia de plano e clique no sinal de adição para expandir a pasta **Programação** .</span><span class="sxs-lookup"><span data-stu-id="eb87d-123">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="eb87d-124">Clique no sinal de adição para expandir a pasta **Guias de Plano** .</span><span class="sxs-lookup"><span data-stu-id="eb87d-124">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="eb87d-125">Clique com o botão direito do mouse no guia de plano que você deseja habilitar ou desabilitar e selecione **Habilitar** ou **Desabilitar**.</span><span class="sxs-lookup"><span data-stu-id="eb87d-125">Right-click the plan guide you want to disable or enable and select either **Disable** or **Enable**.</span></span>  
  
4.  <span data-ttu-id="eb87d-126">Na caixa de diálogo **Desabilitar Guia de Plano** ou **Habilitar Guia de Plano** , verifique se a ação escolhida foi bem-sucedida e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="eb87d-126">In either the **Disable Plan Guide** or **Enable Plan Guide** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="eb87d-127">Para desabilitar ou habilitar todos os guias de plano de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="eb87d-127">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="eb87d-128">Clique no sinal de adição para expandir o banco de dados no qual você deseja desabilitar ou habilitar um guia de plano e clique no sinal de adição para expandir a pasta **Programação** .</span><span class="sxs-lookup"><span data-stu-id="eb87d-128">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="eb87d-129">Clique com o botão direito do mouse na pasta **Guias de Plano** e selecione **Habilitar Tudo** ou **Desabilitar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="eb87d-129">Right-click the **Plan Guides** folder and then select either **Enable All** or **Disable All**.</span></span>  
  
3.  <span data-ttu-id="eb87d-130">Na caixa de diálogo **Desabilitar Todos os Guias de Plano** ou **Habilitar Todos os Guias de Plano** , verifique se a ação escolhida foi bem-sucedida e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="eb87d-130">In either the **Disable all Plan Guides** or **Enable all Plan Guides** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="eb87d-131">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eb87d-131">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="eb87d-132">Para habilitar ou desabilitar um guia de plano</span><span class="sxs-lookup"><span data-stu-id="eb87d-132">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="eb87d-133">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb87d-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="eb87d-134">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="eb87d-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="eb87d-135">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="eb87d-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Create a procedure on which to define the plan guide.  
    IF OBJECT_ID(N'Sales.GetSalesOrderByCountry', N'P') IS NOT NULL  
        DROP PROCEDURE Sales.GetSalesOrderByCountry;  
    GO  
    CREATE PROCEDURE Sales.GetSalesOrderByCountry   
        (@Country nvarchar(60))  
    AS  
    BEGIN  
        SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country;  
    END  
    GO  
    --Create the plan guide.  
    EXEC sp_create_plan_guide N'Guide3',  
        N'SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country',  
        N'OBJECT',  
        N'Sales.GetSalesOrderByCountry',  
        NULL,  
        N'OPTION (OPTIMIZE FOR (@Country = N''US''))';  
    --Disable the plan guide.  
    EXEC sp_control_plan_guide N'DISABLE', N'Guide3';  
    GO  
    --Enable the plan guide.  
    EXEC sp_control_plan_guide N'ENABLE', N'Guide3';  
    GO  
  
    ```  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="eb87d-136">Para desabilitar ou habilitar todos os guias de plano de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="eb87d-136">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="eb87d-137">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb87d-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="eb87d-138">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="eb87d-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="eb87d-139">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="eb87d-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Disable all plan guides in the database.  
    EXEC sp_control_plan_guide N'DISABLE ALL';  
    GO  
    --Enable all plan guides in the database.  
    EXEC sp_control_plan_guide N'ENABLE ALL';  
    GO  
  
    ```  
  
 <span data-ttu-id="eb87d-140">Para obter mais informações, veja [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb87d-140">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
