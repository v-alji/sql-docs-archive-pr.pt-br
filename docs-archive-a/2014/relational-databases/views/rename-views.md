---
title: Renomear exibições | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- renaming views
ms.assetid: 5eed0488-81d2-40e8-8fdf-b0a640a591d0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc76ced033a69788270c3fa9277bcca6972e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679276"
---
# <a name="rename-views"></a><span data-ttu-id="61e53-102">Renomear exibições</span><span class="sxs-lookup"><span data-stu-id="61e53-102">Rename Views</span></span>
  <span data-ttu-id="61e53-103">Você pode renomear uma exibição no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61e53-103">You can rename a view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="61e53-104">Se você renomear uma exibição, os códigos e aplicativos dependentes da exibição poderão falhar.</span><span class="sxs-lookup"><span data-stu-id="61e53-104">If you rename a view, code and applications that depend on the view may fail.</span></span> <span data-ttu-id="61e53-105">Isso inclui outras consultas, exibições, procedimentos armazenados, funções definidas pelo usuário e aplicativos clientes.</span><span class="sxs-lookup"><span data-stu-id="61e53-105">These include other views, queries, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="61e53-106">Observe que essas falhas ocorrerão em cascata.</span><span class="sxs-lookup"><span data-stu-id="61e53-106">Note that these failures will cascade.</span></span>  
  
 <span data-ttu-id="61e53-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="61e53-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="61e53-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="61e53-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="61e53-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="61e53-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="61e53-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="61e53-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="61e53-111">**Para renomear uma exibição usando:**</span><span class="sxs-lookup"><span data-stu-id="61e53-111">**To rename a view, using:**</span></span>  
  
     [<span data-ttu-id="61e53-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61e53-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="61e53-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="61e53-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="61e53-114">**Acompanhamento:**  [Depois de renomear uma exibição](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="61e53-114">**Follow Up:**  [After renaming a view](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="61e53-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="61e53-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="61e53-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="61e53-116">Prerequisites</span></span>  
 <span data-ttu-id="61e53-117">Obtenha uma lista de todas as dependências da exibição.</span><span class="sxs-lookup"><span data-stu-id="61e53-117">Obtain a list of all dependencies on the view.</span></span> <span data-ttu-id="61e53-118">Qualquer objeto, script ou aplicativo que faça referência à exibição deve ser modificado para refletir o novo nome da exibição.</span><span class="sxs-lookup"><span data-stu-id="61e53-118">Any objects, scripts or applications that reference the view must be modified to reflect the new name of the view.</span></span> <span data-ttu-id="61e53-119">Para obter mais informações, consulte [Get Information About a View](get-information-about-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="61e53-119">For more information, see [Get Information About a View](get-information-about-a-view.md).</span></span> <span data-ttu-id="61e53-120">Recomendamos que você remova a exibição e a recrie com um novo nome em vez de renomear a exibição.</span><span class="sxs-lookup"><span data-stu-id="61e53-120">We recommend that you drop the view and recreate it with a new name instead of renaming the view.</span></span> <span data-ttu-id="61e53-121">Recriando a exibição, você atualiza a informações de dependência dos objetos que são referenciados na exibição.</span><span class="sxs-lookup"><span data-stu-id="61e53-121">By recreating the view, you update the dependency information for the objects that are referenced in the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="61e53-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="61e53-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="61e53-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="61e53-123">Permissions</span></span>  
 <span data-ttu-id="61e53-124">Exige a permissão ALTER em SCHEMA ou a permissão CONTROL em OBJECT, e a permissão CREATE VIEW no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="61e53-124">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT is required, and CREATE VIEW permission in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="61e53-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61e53-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-view"></a><span data-ttu-id="61e53-126">Para renomear uma exibição</span><span class="sxs-lookup"><span data-stu-id="61e53-126">To rename a view</span></span>  
  
1.  <span data-ttu-id="61e53-127">No **Pesquisador de Objetos**, expanda o banco de dados que contém a exibição que deseja renomear e expanda a pasta **Exibição** .</span><span class="sxs-lookup"><span data-stu-id="61e53-127">In **Object Explorer**, expand the database that contains the view you wish to rename and then expand the **View** folder.</span></span>  
  
2.  <span data-ttu-id="61e53-128">Clique com o botão direito do mouse na exibição que você deseja renomear e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="61e53-128">Right-click the view you wish to rename and select **Rename**.</span></span>  
  
3.  <span data-ttu-id="61e53-129">Digite o novo nome da exibição.</span><span class="sxs-lookup"><span data-stu-id="61e53-129">Enter the view's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="61e53-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="61e53-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="61e53-131">**Para renomear uma exibição**</span><span class="sxs-lookup"><span data-stu-id="61e53-131">**To rename a view**</span></span>  
  
 <span data-ttu-id="61e53-132">Embora seja possível usar **sp_rename** para alterar o nome da exibição, recomendamos que você exclua a exibição existente e a crie novamente com o novo nome.</span><span class="sxs-lookup"><span data-stu-id="61e53-132">While you can use **sp_rename** to change the name of the view, we recommend that you delete the existing view and then re-create it with the new name.</span></span>  
  
 <span data-ttu-id="61e53-133">Para obter mais informações, veja [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) e [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="61e53-133">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) and [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
##  <a name="follow-up-after-renaming-a-view"></a><a name="FollowUp"></a> <span data-ttu-id="61e53-134">Acompanhamento: Depois de renomear uma exibição</span><span class="sxs-lookup"><span data-stu-id="61e53-134">Follow Up: After Renaming a View</span></span>  
 <span data-ttu-id="61e53-135">Verifique se todos os objetos, scripts e aplicativos que fazem referência ao nome antigo da exibição agora usam o novo nome.</span><span class="sxs-lookup"><span data-stu-id="61e53-135">Ensure that all objects, scripts, and applications that reference the view's old name now use the new name.</span></span>  
  
  
