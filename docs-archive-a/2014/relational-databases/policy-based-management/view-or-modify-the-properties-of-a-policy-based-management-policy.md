---
title: Exibir ou modificar as propriedades de uma política de gerenciamento baseado em políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, modify policies
- Policy-Based Management, view policies
ms.assetid: ba805504-5db5-4731-a8da-a0e89cb20c37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: da2226d3049a84098eb8e561635161f73b71ab10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571986"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-policy"></a><span data-ttu-id="96a79-102">Exibir ou modificar as propriedades de uma política de gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="96a79-102">View or Modify the Properties of a Policy-Based Management Policy</span></span>
  <span data-ttu-id="96a79-103">Este tópico descreve como exibir ou modificar as propriedades de uma política de gerenciamento baseado em políticas [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96a79-103">This topic describes how to view or modify a Policy-Based Management policy's properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="96a79-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="96a79-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="96a79-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="96a79-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="96a79-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="96a79-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="96a79-107">**Para exibir ou modificar as propriedades de uma política, usando:**</span><span class="sxs-lookup"><span data-stu-id="96a79-107">**To view or modify a policy's properties, using:**</span></span>  
  
     [<span data-ttu-id="96a79-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96a79-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="96a79-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96a79-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="96a79-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="96a79-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="96a79-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="96a79-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="96a79-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="96a79-112">Permissions</span></span>  
 <span data-ttu-id="96a79-113">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="96a79-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="96a79-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96a79-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-all-policies-on-an-object"></a><span data-ttu-id="96a79-115">Para exibir as propriedades de todas as políticas em um objeto</span><span class="sxs-lookup"><span data-stu-id="96a79-115">To view the properties of all policies on an object</span></span>  
  
1.  <span data-ttu-id="96a79-116">Em Pesquisador de Objetos, clique com o botão direito do mouse em um servidor, objeto de servidor, banco de dados ou objeto de banco de dados, aponte para **Políticas** e selecione **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="96a79-116">In Object Explorer, right-click a server, server object, database, or database object, point to **Policies** and select **View**.</span></span> <span data-ttu-id="96a79-117">Para obter mais informações sobre as opções disponíveis na caixa de diálogo **Exibir políticas-**_nome_do_objeto_, confira [Caixa de diálogo Exibir Políticas](view-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="96a79-117">For more information on the available options in the **View Policies -**_object_name_ dialog box, see [View Policies Dialog Box](view-policies-dialog-box.md).</span></span>  
  
2.  <span data-ttu-id="96a79-118">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="96a79-118">When finished, click **Close**.</span></span>  
  
#### <a name="to-view-or-modify-a-specific-policys-properties"></a><span data-ttu-id="96a79-119">Para exibir ou modificar as propriedades de uma política específica</span><span class="sxs-lookup"><span data-stu-id="96a79-119">To view or modify a specific policy's properties</span></span>  
  
1.  <span data-ttu-id="96a79-120">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém a Política de Gerenciamento Baseado em Políticas que você deseja exibir ou modificar.</span><span class="sxs-lookup"><span data-stu-id="96a79-120">In **Object Explorer**, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="96a79-121">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="96a79-121">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="96a79-122">Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.</span><span class="sxs-lookup"><span data-stu-id="96a79-122">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="96a79-123">Clique no sinal de adição para expandir a pasta **Políticas** .</span><span class="sxs-lookup"><span data-stu-id="96a79-123">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="96a79-124">Clique com o botão direito do mouse na política que você deseja exibir ou modificar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="96a79-124">Right-click the policy that you want to view or modify and select **Properties**.</span></span> <span data-ttu-id="96a79-125">Para obter mais informações sobre as opções disponíveis na caixa de diálogo **Abrir Política -**_nome_da_política_, confira [Caixa de diálogo Criar Política ou Abrir Política, página Geral](../../integration-services/general-page-of-integration-services-designers-options.md) e [Caixa de diálogo Criar Política ou Abrir Política, página Descrição](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="96a79-125">For more information on the available options in the **Open Policy -**_policy_name_ dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) and [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
6.  <span data-ttu-id="96a79-126">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="96a79-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="96a79-127">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96a79-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-policys-properties"></a><span data-ttu-id="96a79-128">Para exibir as propriedades de uma política</span><span class="sxs-lookup"><span data-stu-id="96a79-128">To view a policy's properties</span></span>  
  
1.  <span data-ttu-id="96a79-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96a79-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="96a79-130">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="96a79-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="96a79-131">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="96a79-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       execution_mode,  
       description,  
       is_enabled,  
       job_id  
    FROM syspolicy_policies;  
    GO  
    ```  
  
 <span data-ttu-id="96a79-132">Para obter mais informações, veja [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="96a79-132">For more information, see [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span></span>  
  
  
