---
title: Exibir ou modificar as propriedades de uma condição de gerenciamento baseado em políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view policy conditions
- Policy-Based Management, modify policy conditions
ms.assetid: 890d7384-8444-4767-bb6f-f5debb155747
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 08baec48bd13445ef56ea6a29520d23ebaf683b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571985"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-condition"></a><span data-ttu-id="2c91f-102">Exibir ou modificar as propriedades de uma condição de gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="2c91f-102">View or Modify the Properties of a Policy-Based Management Condition</span></span>
  <span data-ttu-id="2c91f-103">Este tópico descreve como exibir ou modificar as propriedades de uma condição de gerenciamento baseado em políticas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c91f-103">This topic describes how to view or modify the properties of a Policy-Based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2c91f-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="2c91f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2c91f-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="2c91f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2c91f-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="2c91f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2c91f-107">**Para exibir ou modificar as propriedades de uma condição, usando:**</span><span class="sxs-lookup"><span data-stu-id="2c91f-107">**To view or modify a condition's properties, using:**</span></span>  
  
     [<span data-ttu-id="2c91f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2c91f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2c91f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2c91f-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2c91f-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2c91f-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2c91f-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="2c91f-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2c91f-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="2c91f-112">Permissions</span></span>  
 <span data-ttu-id="2c91f-113">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="2c91f-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2c91f-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2c91f-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-modify-a-conditions-properties"></a><span data-ttu-id="2c91f-115">Para exibir ou modificar as propriedades de uma condição</span><span class="sxs-lookup"><span data-stu-id="2c91f-115">To view or modify a condition's properties</span></span>  
  
1.  <span data-ttu-id="2c91f-116">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém a condição que você deseja exibir ou modificar.</span><span class="sxs-lookup"><span data-stu-id="2c91f-116">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="2c91f-117">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="2c91f-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="2c91f-118">Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.</span><span class="sxs-lookup"><span data-stu-id="2c91f-118">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="2c91f-119">Clique no sinal de adição para expandir a pasta **Condições** .</span><span class="sxs-lookup"><span data-stu-id="2c91f-119">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="2c91f-120">Clique com o botão direito do mouse na condição que você deseja exibir ou editar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2c91f-120">Right-click the condition that you want to view or edit and select **Properties**.</span></span> <span data-ttu-id="2c91f-121">Para obter mais informações sobre as opções disponíveis na caixa de diálogo **Abrir Condição -**_nome_da_condição_, confira [Caixa de diálogo Criar Condição ou Abrir Condição, página Geral](../../integration-services/general-page-of-integration-services-designers-options.md), [Caixa de diálogo Abrir Condição, página Políticas Dependentes](open-condition-dialog-box-dependent-policies-page.md), [Caixa de diálogo Criar Condição ou Abrir Condição, página Descrição](create-new-condition-or-open-condition-dialog-box-description-page.md) e [Caixa de diálogo Edição Avançada &#40;Condição&#41;](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="2c91f-121">For more information on the available options in the **Open Condition -**_condition_name_ dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Open Condition Dialog Box, Dependent Policies Page](open-condition-dialog-box-dependent-policies-page.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="2c91f-122">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c91f-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2c91f-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2c91f-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-conditions-properties"></a><span data-ttu-id="2c91f-124">Para exibir as propriedades de uma condição</span><span class="sxs-lookup"><span data-stu-id="2c91f-124">To view a condition's properties</span></span>  
  
1.  <span data-ttu-id="2c91f-125">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c91f-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2c91f-126">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2c91f-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2c91f-127">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2c91f-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       description,  
       facet,  
       expression,  
       is_name_condition,  
       obj_name  
    FROM syspolicy_conditions;  
    GO  
  
    ```  
  
 <span data-ttu-id="2c91f-128">Para obter mais informações, veja [syspolicy_conditions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c91f-128">For more information, see [syspolicy_conditions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span></span>  
  
  
