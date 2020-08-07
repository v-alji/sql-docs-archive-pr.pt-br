---
title: Renomear funções definidas pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: c2695a5c-9cc5-4b18-8771-53027ca9a9af
author: rothja
ms.author: jroth
ms.openlocfilehash: ec923be64cf7819c4018ebda71a472f58b29cf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584065"
---
# <a name="rename-user-defined-functions"></a><span data-ttu-id="26971-102">Renomear funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="26971-102">Rename User-defined Functions</span></span>
  <span data-ttu-id="26971-103">Você pode renomear funções definidas pelo usuário no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26971-103">You can rename user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="26971-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="26971-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="26971-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="26971-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="26971-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="26971-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="26971-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="26971-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="26971-108">**Para renomear funções definidas pelo usuário utilizando:**</span><span class="sxs-lookup"><span data-stu-id="26971-108">**To rename user-defined functions, using:**</span></span>  
  
     [<span data-ttu-id="26971-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26971-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="26971-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="26971-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="26971-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="26971-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="26971-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="26971-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="26971-113">Os nomes de funções devem ser compatíveis com as regras para [identificadores](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="26971-113">Function names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="26971-114">Renomear uma função definida pelo usuário não alterará o nome do objeto correspondente na coluna de definição da exibição de catálogo **sys.sql_modules** .</span><span class="sxs-lookup"><span data-stu-id="26971-114">Renaming a user-defined function will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="26971-115">Assim, é recomendável não renomear esse tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="26971-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="26971-116">Em vez disso, remova-o e recrie o procedimento armazenado com seu nome novo.</span><span class="sxs-lookup"><span data-stu-id="26971-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="26971-117">A alteração do nome ou definição de uma função definida pelo usuário pode causar falha em objetos dependentes que não são atualizados para refletir as alterações que tenham sido feitas na função.</span><span class="sxs-lookup"><span data-stu-id="26971-117">Changing the name or definition of a user-defined function can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="26971-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="26971-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="26971-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="26971-119">Permissions</span></span>  
 <span data-ttu-id="26971-120">Para remover a função, é necessário ter a permissão ALTER no esquema ao qual pertence a função ou a permissão CONTROL na função.</span><span class="sxs-lookup"><span data-stu-id="26971-120">To drop the function, requires either ALTER permission on the schema to which the function belongs or CONTROL permission on the function.</span></span> <span data-ttu-id="26971-121">Para recriar a função, é necessário ter a permissão CREATE FUNCTION no banco de dados e a permissão ALTER no esquema no qual a função está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="26971-121">To re-create the function, requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="26971-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26971-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-user-defined-functions"></a><span data-ttu-id="26971-123">Para renomear funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="26971-123">To rename user-defined functions</span></span>  
  
1.  <span data-ttu-id="26971-124">No **Pesquisador de Objetos**, clique no sinal de adição ao lado do banco de dados que contém a função que você deseja renomear e</span><span class="sxs-lookup"><span data-stu-id="26971-124">In **Object Explorer**, click the plus sign next to the database that contains the function you wish to rename and then</span></span>  
  
2.  <span data-ttu-id="26971-125">Clique no sinal de adição ao lado da pasta **Programação** .</span><span class="sxs-lookup"><span data-stu-id="26971-125">Click the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="26971-126">Clique no sinal de mais ao lado da pasta que contém a função que você deseja renomear:</span><span class="sxs-lookup"><span data-stu-id="26971-126">Click the plus sign next to the folder that contains the function you wish to rename:</span></span>  
  
    -   <span data-ttu-id="26971-127">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="26971-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="26971-128">Função de valor escalar</span><span class="sxs-lookup"><span data-stu-id="26971-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="26971-129">Função de agregação</span><span class="sxs-lookup"><span data-stu-id="26971-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="26971-130">Clique com o botão direito do mouse na função que você deseja renomear e selecione **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="26971-130">Right-click the function you wish to rename and select **Rename**.</span></span>  
  
5.  <span data-ttu-id="26971-131">Digite o novo nome da função.</span><span class="sxs-lookup"><span data-stu-id="26971-131">Enter the function's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="26971-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="26971-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="26971-133">**Para renomear funções definidas pelo usuário**</span><span class="sxs-lookup"><span data-stu-id="26971-133">**To rename user-defined functions**</span></span>  
  
 <span data-ttu-id="26971-134">Esta tarefa não pode ser executada usando instruções Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="26971-134">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="26971-135">Para renomear uma função definida pelo usuário usando Transact-SQL, primeiro você deve excluir a função existente e depois recriá-la com o novo nome.</span><span class="sxs-lookup"><span data-stu-id="26971-135">To rename a user-defined function using Transact-SQL, you must first delete the existing function and then re-create it with the new name.</span></span> <span data-ttu-id="26971-136">Verifique se todo o código e os aplicativos que usavam o nome antigo da função agora usam o nome novo.</span><span class="sxs-lookup"><span data-stu-id="26971-136">Ensure that all code and applications that used the function's old name now use the new name.</span></span>  
  
 <span data-ttu-id="26971-137">Para obter mais informações, veja [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) e [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="26971-137">For more information, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) and [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26971-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="26971-138">See Also</span></span>  
 <span data-ttu-id="26971-139">[sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="26971-139">[sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span></span>  
 [<span data-ttu-id="26971-140">Exibir funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="26971-140">View User-defined Functions</span></span>](user-defined-functions.md)  
  
  
