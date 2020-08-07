---
title: Executar funções definidas pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- invoking user-defined functions
- user-defined functions [SQL Server], executing
ms.assetid: 0de7744d-9b73-463f-ae80-e31a020004b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4446f3b3a132488fdac6e859f30abaca40a193d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584068"
---
# <a name="execute-user-defined-functions"></a><span data-ttu-id="ef593-102">Executar funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ef593-102">Execute User-defined Functions</span></span>
  <span data-ttu-id="ef593-103">Você pode executar uma função definida pelo usuário no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef593-103">You can execute a user defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ef593-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ef593-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ef593-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="ef593-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ef593-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="ef593-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ef593-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="ef593-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ef593-108">**Para executar uma função definida pelo usuário, usando:**</span><span class="sxs-lookup"><span data-stu-id="ef593-108">**To execute a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="ef593-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef593-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ef593-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ef593-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ef593-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="ef593-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ef593-112">No Transact-SQL, os parâmetros podem ser fornecidos usando *valor* ou usando @*parameter_name*=*valor.*</span><span class="sxs-lookup"><span data-stu-id="ef593-112">In Transact-SQL, parameters can be supplied either by using *value* or by using @*parameter_name*=*value.*</span></span> <span data-ttu-id="ef593-113">. Um parâmetro não faz parte de uma transação; portanto, se um parâmetro for alterado em uma transação que for posteriormente revertida, o parâmetro não será revertido para seu valor anterior.</span><span class="sxs-lookup"><span data-stu-id="ef593-113">A parameter is not part of a transaction; therefore, if a parameter is changed in a transaction that is later rolled back, the value of the parameter does not revert to its previous value.</span></span> <span data-ttu-id="ef593-114">O valor retornado ao chamador será sempre o valor no momento do retorno do módulo.</span><span class="sxs-lookup"><span data-stu-id="ef593-114">The value returned to the caller is always the value at the time the module returns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ef593-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="ef593-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ef593-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="ef593-116">Permissions</span></span>  
 <span data-ttu-id="ef593-117">Não são solicitadas permissões para executar a instrução EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="ef593-117">Permissions are not required to run the EXECUTE statement.</span></span> <span data-ttu-id="ef593-118">Porém, são solicitadas permissões nos protegíveis mencionados na cadeia de caracteres EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="ef593-118">However, permissions are required on the securables that are referenced within the EXECUTE string.</span></span> <span data-ttu-id="ef593-119">Por exemplo, se a cadeia de caracteres tiver uma instrução INSERT, o chamador da instrução EXECUTE deverá ter a permissão INSERT na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="ef593-119">For example, if the string contains an INSERT statement, the caller of the EXECUTE statement must have INSERT permission on the target table.</span></span> <span data-ttu-id="ef593-120">As permissões são verificadas quando a instrução EXECUTE for encontrada, mesmo se ela estiver incluída em um módulo.</span><span class="sxs-lookup"><span data-stu-id="ef593-120">Permissions are checked at the time EXECUTE statement is encountered, even if the EXECUTE statement is included within a module.</span></span> <span data-ttu-id="ef593-121">Para obter mais informações, consulte [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="ef593-121">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ef593-122">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef593-122">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-user-defined-function"></a><span data-ttu-id="ef593-123">Para executar uma função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="ef593-123">To execute a user-defined function</span></span>  
  
1.  <span data-ttu-id="ef593-124">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef593-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ef593-125">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ef593-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ef593-126">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="ef593-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Declares a variable and sets it to zero.  
    -- This variable is used to return the results of the function.  
    DECLARE @ret nvarchar(15)= NULL;   
  
    -- Executes the dbo.ufnGetSalesOrderStatusText function.  
    --The function requires a value for one parameter, @Status.   
    EXEC @ret = dbo.ufnGetSalesOrderStatusText @Status= 5;   
    --Returns the result in the message tab.  
    PRINT @ret;  
    ```  
  
 <span data-ttu-id="ef593-127">Para obter mais informações, veja [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ef593-127">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
  
