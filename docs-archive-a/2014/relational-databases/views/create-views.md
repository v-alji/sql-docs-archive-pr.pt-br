---
title: Criar exibições | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], creating
ms.assetid: 0b7bd2a1-544c-42ba-8e7b-4822f34d7b64
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8280f6d65d7252cad423abef849207111492c044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569270"
---
# <a name="create-views"></a><span data-ttu-id="8e4dd-102">Criar exibições</span><span class="sxs-lookup"><span data-stu-id="8e4dd-102">Create Views</span></span>
  <span data-ttu-id="8e4dd-103">Você pode criar exibições no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e4dd-103">You can create views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8e4dd-104">Uma exibição pode ser usada para as finalidades a seguir:</span><span class="sxs-lookup"><span data-stu-id="8e4dd-104">A view can be used for the following purposes:</span></span>  
  
-   <span data-ttu-id="8e4dd-105">Para focalizar, simplificar e personalizar a percepção que cada usuário tem do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-105">To focus, simplify, and customize the perception each user has of the database.</span></span>  
  
-   <span data-ttu-id="8e4dd-106">Como um mecanismo de segurança permitindo que os usuários acessem dados por meio da exibição, sem conceder permissões aos usuários para acessar diretamente as tabelas base subjacentes.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-106">As a security mechanism by allowing users to access data through the view, without granting the users permissions to directly access the underlying base tables.</span></span>  
  
-   <span data-ttu-id="8e4dd-107">Para fornecer uma interface compatível com versões anteriores para emular uma tabela cujo esquema foi alterado.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-107">To provide a backward compatible interface to emulate a table whose schema has changed.</span></span>  
  
 <span data-ttu-id="8e4dd-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8e4dd-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8e4dd-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8e4dd-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8e4dd-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8e4dd-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8e4dd-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="8e4dd-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8e4dd-112">**Para criar uma exibição usando:**</span><span class="sxs-lookup"><span data-stu-id="8e4dd-112">**To create a view, using:**</span></span>  
  
     [<span data-ttu-id="8e4dd-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8e4dd-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8e4dd-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8e4dd-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8e4dd-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8e4dd-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8e4dd-116">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8e4dd-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="8e4dd-117">A exibição só pode ser criada no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-117">A view can be created only in the current database.</span></span>  
  
 <span data-ttu-id="8e4dd-118">Uma exibição pode ter, no máximo, 1.024 partições.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-118">A view can have a maximum of 1,024 columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8e4dd-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="8e4dd-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8e4dd-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="8e4dd-120">Permissions</span></span>  
 <span data-ttu-id="8e4dd-121">Requer a permissão CREATE VIEW no banco de dados e a permissão ALTER no esquema no qual a exibição está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-121">Requires CREATE VIEW permission in the database and ALTER permission on the schema in which the view is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8e4dd-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8e4dd-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-view-by-using-the-query-and-view-designer"></a><span data-ttu-id="8e4dd-123">Para criar uma exibição usando o Designer de Consulta e Exibição</span><span class="sxs-lookup"><span data-stu-id="8e4dd-123">To create a view by using the Query and View Designer</span></span>  
  
1.  <span data-ttu-id="8e4dd-124">No **Pesquisador de Objetos**, expanda o banco de dados em que você deseja criar a nova exibição.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-124">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="8e4dd-125">Clique com o botão direito do mouse na pasta **Exibições** objeto e clique em **Nova Exibição...** .</span><span class="sxs-lookup"><span data-stu-id="8e4dd-125">Right-click the **Views** folder, then click **New View...**.</span></span>  
  
3.  <span data-ttu-id="8e4dd-126">Na caixa de diálogo **Adicionar Tabela** , selecione o elemento ou elementos que você deseja incluir em sua nova exibição de uma destas guias: Tabelas, Exibições, Funções e Sinônimos.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-126">In the **Add Table** dialog box, select the element or elements that you want to include in your new view from one of the following tabs: Tables, Views, Functions, and Synonyms.</span></span>  
  
4.  <span data-ttu-id="8e4dd-127">Clique em **Adicionar**e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-127">Click **Add**, then click **Close**.</span></span>  
  
5.  <span data-ttu-id="8e4dd-128">No **Painel de Diagrama**, selecione as colunas ou outros elementos para incluir na nova exibição.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-128">In the **Diagram Pane**, select the columns or other elements to include in the new view.</span></span>  
  
6.  <span data-ttu-id="8e4dd-129">No **Painel de Critérios**, selecione os critérios adicionais de classificação ou filtragem para as colunas.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-129">In the **Criteria Pane**, select additional sort or filter criteria for the columns.</span></span>  
  
7.  <span data-ttu-id="8e4dd-130">No menu **Arquivo** , clique em **Salvar**_view name_.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-130">On the **File** menu, click **Save**_view name_.</span></span>  
  
8.  <span data-ttu-id="8e4dd-131">Na caixa de diálogo **Escolher Nome** , digite um nome para a nova exibição e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-131">In the **Choose Name** dialog box, enter a name for the new view and click **OK**.</span></span>  
  
     <span data-ttu-id="8e4dd-132">Para obter mais informações sobre o designer de consultas e exibição, veja [Ferramentas de Designer de Consultas e Exibição&#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8e4dd-132">For more information about the query and view designer, see [Query and View Designer Tools &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8e4dd-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8e4dd-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-view"></a><span data-ttu-id="8e4dd-134">Para criar uma exibição</span><span class="sxs-lookup"><span data-stu-id="8e4dd-134">To create a view</span></span>  
  
1.  <span data-ttu-id="8e4dd-135">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e4dd-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8e4dd-136">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8e4dd-137">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8e4dd-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
    GO  
    -- Query the view  
    SELECT FirstName, LastName, HireDate  
    FROM HumanResources.EmployeeHireDate  
    ORDER BY LastName;  
  
    ```  
  
 <span data-ttu-id="8e4dd-138">Para obter mais informações, veja [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8e4dd-138">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
  
