---
title: Desabilitar restrições Foreign Key para replicação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
ms.assetid: 4211f2fd-d16a-4081-995c-43f1f0827f0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4ee7f2fb7b0a27870a09a9d99b723b7faf739aeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572969"
---
# <a name="disable-foreign-key-constraints-for-replication"></a><span data-ttu-id="eccc4-102">Desabilitar restrições FOREIGN KEY para replicação</span><span class="sxs-lookup"><span data-stu-id="eccc4-102">Disable Foreign Key Constraints for Replication</span></span>
  <span data-ttu-id="eccc4-103">Você pode desabilitar as restrições de chave estrangeira para replicação no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eccc4-103">You can disable foreign key constraints for replication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="eccc4-104">Isso pode ser útil se você publicar dados de uma versão anterior do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eccc4-104">This can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eccc4-105">Se uma tabela for publicada utilizando replicação, as restrições de chave estrangeira serão desabilitadas automaticamente para operações executadas por agentes de replicação.</span><span class="sxs-lookup"><span data-stu-id="eccc4-105">If a table is published using replication, foreign key constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="eccc4-106">Quando um agente de replicação executa uma inserção, atualização ou exclusão em um Assinante, a restrição não é verificada; se um usuário executar uma inserção, atualização ou exclusão, a restrição será verificada.</span><span class="sxs-lookup"><span data-stu-id="eccc4-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="eccc4-107">A restrição está desabilitada para o agente de replicação porque a restrição já foi verificada no Publicador quando os dados foram inseridos, atualizados ou excluídos originalmente.</span><span class="sxs-lookup"><span data-stu-id="eccc4-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span>  
  
 <span data-ttu-id="eccc4-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="eccc4-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="eccc4-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="eccc4-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="eccc4-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="eccc4-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="eccc4-111">**Para desabilitar uma restrição de chave estrangeira para replicação usando:**</span><span class="sxs-lookup"><span data-stu-id="eccc4-111">**To disable a foreign key constraint for replication, using:**</span></span>  
  
     [<span data-ttu-id="eccc4-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eccc4-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="eccc4-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eccc4-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eccc4-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="eccc4-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="eccc4-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="eccc4-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="eccc4-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="eccc4-116">Permissions</span></span>  
 <span data-ttu-id="eccc4-117">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="eccc4-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="eccc4-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eccc4-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="eccc4-119">Para desabilitar uma restrição de chave estrangeira para replicação</span><span class="sxs-lookup"><span data-stu-id="eccc4-119">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="eccc4-120">No **Pesquisador de Objetos**, expanda a tabela com a restrição de chave estrangeira que você deseja modificar e expanda a pasta **Chaves** .</span><span class="sxs-lookup"><span data-stu-id="eccc4-120">In **Object Explorer**, expand the table with the foreign key constraint you want to modify, and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="eccc4-121">Clique com o botão direito do mouse na restrição de chave estrangeira e clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="eccc4-121">Right-click the foreign key constraint and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="eccc4-122">Na caixa de diálogo **Relações de Chaves Estrangeiras** , selecione o valor **Não** em **Impor para Replicação**.</span><span class="sxs-lookup"><span data-stu-id="eccc4-122">In the **Foreign Key Relationships** dialog box, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="eccc4-123">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="eccc4-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="eccc4-124">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eccc4-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="eccc4-125">Para desabilitar uma restrição de chave estrangeira para replicação</span><span class="sxs-lookup"><span data-stu-id="eccc4-125">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="eccc4-126">Para executar esta tarefa no [!INCLUDE[tsql](../../includes/tsql-md.md)], descarte a restrição de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="eccc4-126">To perform this task in [!INCLUDE[tsql](../../includes/tsql-md.md)], drop the foreign key constraint.</span></span> <span data-ttu-id="eccc4-127">Em seguida, adicione uma nova restrição de chave estrangeira e especifique a opção NOT FOR REPLICATION.</span><span class="sxs-lookup"><span data-stu-id="eccc4-127">Then add a new foreign key constraint and specify the NOT FOR REPLICATION option.</span></span>  
  
 <span data-ttu-id="eccc4-128">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eccc4-128">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
