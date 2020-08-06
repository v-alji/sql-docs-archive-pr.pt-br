---
title: Excluir um guia de plano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], deleting
ms.assetid: aa4d3188-6927-43de-a3e3-90fc16eeaca7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 303ad6f59cbe24265aec66f3cb780a5b4ad4f157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679887"
---
# <a name="delete-a-plan-guide"></a><span data-ttu-id="adb24-102">Excluir um guia de plano</span><span class="sxs-lookup"><span data-stu-id="adb24-102">Delete a Plan Guide</span></span>
  <span data-ttu-id="adb24-103">Você pode excluir (cancelar) um guia de plano no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adb24-103">You can delete (drop) a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="adb24-104">Usando o [!INCLUDE[tsql](../../includes/tsql-md.md)], você também pode excluir todas as guias de plano de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="adb24-104">Using [!INCLUDE[tsql](../../includes/tsql-md.md)], you can also delete all of the plan guides in a database.</span></span>  
  
 <span data-ttu-id="adb24-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="adb24-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="adb24-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="adb24-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="adb24-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="adb24-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="adb24-108">**Para excluir um guia de plano usando:**</span><span class="sxs-lookup"><span data-stu-id="adb24-108">**To delete a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="adb24-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="adb24-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="adb24-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="adb24-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="adb24-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="adb24-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="adb24-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="adb24-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="adb24-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="adb24-113">Permissions</span></span>  
 <span data-ttu-id="adb24-114">A exclusão de um guia de plano OBJECT exige a permissão ALTER no objeto (por exemplo: função, procedimento armazenado) que é referenciado pelo guia de plano.</span><span class="sxs-lookup"><span data-stu-id="adb24-114">Deleting an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="adb24-115">Todos os outros guias de plano requerem permissão ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="adb24-115">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="adb24-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="adb24-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-plan-guide"></a><span data-ttu-id="adb24-117">Para excluir um guia de plano</span><span class="sxs-lookup"><span data-stu-id="adb24-117">To delete a plan guide</span></span>  
  
1.  <span data-ttu-id="adb24-118">Clique no sinal de adição para expandir o banco de dados no qual você deseja excluir um guia de plano e clique no sinal de adição para expandir a pasta **Programação** .</span><span class="sxs-lookup"><span data-stu-id="adb24-118">Click the plus sign to expand the database in which you want to delete a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="adb24-119">Clique no sinal de adição para expandir a pasta **Guias de Plano** .</span><span class="sxs-lookup"><span data-stu-id="adb24-119">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="adb24-120">Clique com o botão direito do mouse no guia de plano a ser excluído e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="adb24-120">Right-click the plan guide you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="adb24-121">Na caixa de diálogo **Excluir Objeto** , verifique se o guia de plano correto está selecionado e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="adb24-121">In the **Delete Object** dialog box, ensure that the correct plan guide is selected and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="adb24-122">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="adb24-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-single-plan-guide"></a><span data-ttu-id="adb24-123">Para excluir um único guia de plano</span><span class="sxs-lookup"><span data-stu-id="adb24-123">To delete a single plan guide</span></span>  
  
1.  <span data-ttu-id="adb24-124">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adb24-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="adb24-125">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="adb24-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="adb24-126">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="adb24-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
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
    GO  
    --Drop the plan guide.  
    EXEC sp_control_plan_guide N'DROP', N'Guide3';  
    GO  
    ```  
  
#### <a name="to-delete-all-plan-guides-in-a-database"></a><span data-ttu-id="adb24-127">Para excluir todas as guias de plano de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="adb24-127">To delete all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="adb24-128">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adb24-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="adb24-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="adb24-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="adb24-130">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="adb24-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_control_plan_guide N'DROP ALL';  
    GO  
    ```  
  
 <span data-ttu-id="adb24-131">Para obter mais informações, veja [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="adb24-131">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
