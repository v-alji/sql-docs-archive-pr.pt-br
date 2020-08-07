---
title: Modificar restrições de verificação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, modifying
- modifying constraints
- constraints [SQL Server], check
- constraints [SQL Server], modifying
ms.assetid: f22daef8-e350-40ef-8ff0-b5f87d1d9e56
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8377c80590612c8b68c315f7c37823eb8f5c5093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575035"
---
# <a name="modify-check-constraints"></a><span data-ttu-id="16025-102">Modificar restrições de verificação</span><span class="sxs-lookup"><span data-stu-id="16025-102">Modify Check Constraints</span></span>
  <span data-ttu-id="16025-103">Você pode modificar uma restrição de verificação no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] quando você quiser alterar a expressão de restrição ou as opções que habilitam ou desabilitam a restrição de condições específicas.</span><span class="sxs-lookup"><span data-stu-id="16025-103">You can modify a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] when you want to change the constraint expression or the options that enable or disable the constraint for specific conditions.</span></span>  
  
 <span data-ttu-id="16025-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="16025-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="16025-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="16025-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="16025-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="16025-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="16025-107">**Para modificar uma restrição de verificação usando:**</span><span class="sxs-lookup"><span data-stu-id="16025-107">**To modify a check constraint using:**</span></span>  
  
     [<span data-ttu-id="16025-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="16025-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="16025-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="16025-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="16025-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="16025-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="16025-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="16025-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="16025-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="16025-112">Permissions</span></span>  
 <span data-ttu-id="16025-113">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="16025-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="16025-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="16025-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-check-constraint"></a><span data-ttu-id="16025-115">Para modificar uma restrição de verificação</span><span class="sxs-lookup"><span data-stu-id="16025-115">To modify a check constraint</span></span>  
  
1.  <span data-ttu-id="16025-116">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela que contém restrição de verificação e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="16025-116">In the **Object Explorer**, right-click the table containing the check constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="16025-117">No menu **Designer de Tabela**, clique em **Verificar Restrições...** .</span><span class="sxs-lookup"><span data-stu-id="16025-117">On the **Table Designer** menu, click **Check Constraints...**.</span></span>  
  
3.  <span data-ttu-id="16025-118">Na caixa de diálogo **Verificar Restrições** , em **Restrição de Verificação Selecionada**, selecione a restrição que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="16025-118">In the **Check Constraints** dialog box, under **Selected Check Constraint**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="16025-119">Complete uma ação da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="16025-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="16025-120">Para</span><span class="sxs-lookup"><span data-stu-id="16025-120">To</span></span>|<span data-ttu-id="16025-121">Siga estas etapas</span><span class="sxs-lookup"><span data-stu-id="16025-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="16025-122">Editar a expressão de restrição</span><span class="sxs-lookup"><span data-stu-id="16025-122">Edit the constraint expression</span></span>|<span data-ttu-id="16025-123">Digite uma nova expressão no campo **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="16025-123">Type the new expression in the **Expression** field.</span></span>|  
    |<span data-ttu-id="16025-124">Renomear a restrição</span><span class="sxs-lookup"><span data-stu-id="16025-124">Rename the constraint</span></span>|<span data-ttu-id="16025-125">Digite um nome novo no campo **Nome** .</span><span class="sxs-lookup"><span data-stu-id="16025-125">Type a new name in the **Name** field.</span></span>|  
    |<span data-ttu-id="16025-126">Aplicar a restrição a dados existentes</span><span class="sxs-lookup"><span data-stu-id="16025-126">Apply the constraint to existing data</span></span>|<span data-ttu-id="16025-127">Selecione a opção **Verificar Dados Existentes ao Criar ou Habilitar** .</span><span class="sxs-lookup"><span data-stu-id="16025-127">Select the **Check Existing Data on Creation or Enabling** option.</span></span>|  
    |<span data-ttu-id="16025-128">Desabilitar a restrição quando são adicionados dados novos à tabela ou quando dados existentes são atualizados na tabela.</span><span class="sxs-lookup"><span data-stu-id="16025-128">Disable the constraint when new data is added to the table or when existing data is updated in the table.</span></span>|<span data-ttu-id="16025-129">Desmarque a opção **Aplicar restrições para INSERTs e UPDATEs** .</span><span class="sxs-lookup"><span data-stu-id="16025-129">Clear the **Enforce Constraint for INSERTs and UPDATEs** option.</span></span>|  
    |<span data-ttu-id="16025-130">Desabilitar a restrição quando um agente de replicação inserir ou atualizar dados em sua tabela.</span><span class="sxs-lookup"><span data-stu-id="16025-130">Disable the constraint when a replication agent inserts or updates data in your table.</span></span>|<span data-ttu-id="16025-131">Desmarque a opção **Impor para Replicação** .</span><span class="sxs-lookup"><span data-stu-id="16025-131">Clear the **Enforce For Replication** option.</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="16025-132">Alguns bancos de dados têm funcionalidade diferente para restrições de verificação.</span><span class="sxs-lookup"><span data-stu-id="16025-132">Some databases have different functionality for check constraints.</span></span>  
  
5.  <span data-ttu-id="16025-133">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="16025-133">Click **Close**.</span></span>  
  
6.  <span data-ttu-id="16025-134">No menu **Arquivo**, clique em **Salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="16025-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="16025-135">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="16025-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="16025-136">**Para modificar uma restrição de verificação**</span><span class="sxs-lookup"><span data-stu-id="16025-136">**To modify a check constraint**</span></span>  
  
 <span data-ttu-id="16025-137">Para modificar a restrição `CHECK` usando o [!INCLUDE[tsql](../../includes/tsql-md.md)], exclua primeiramente a restrição `CHECK` e, em seguida, recrie-a com a nova definição.</span><span class="sxs-lookup"><span data-stu-id="16025-137">To modify a `CHECK` constraint using [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first delete the existing `CHECK` constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="16025-138">Para obter mais informações, veja [Excluir restrições de verificação](delete-check-constraints.md) e [Criar restrições de verificação](create-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="16025-138">For more information, see [Delete Check Constraints](delete-check-constraints.md) and [Create Check Constraints](create-check-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
