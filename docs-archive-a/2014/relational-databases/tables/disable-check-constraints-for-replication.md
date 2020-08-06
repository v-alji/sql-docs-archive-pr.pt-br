---
title: Desabilitar verificação de restrições para replicação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, disabling
- constraints [SQL Server], disabling
- disabling constraints
- constraints [SQL Server], check
ms.assetid: af98fc70-24dd-4bd3-a0a3-f701dfa67b2c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 98b6ca7c3525edeffdb47f294db568d3c115b2c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568410"
---
# <a name="disable-check-constraints-for-replication"></a><span data-ttu-id="003ee-102">Desabilitar verificação de restrições para replicação</span><span class="sxs-lookup"><span data-stu-id="003ee-102">Disable Check Constraints for Replication</span></span>
  <span data-ttu-id="003ee-103">Você pode desabilitar restrições de verificação no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="003ee-103">You can disable check constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="003ee-104">Você também poderá desabilitar explicitamente as verificações de restrições de replicações, o que pode ser útil se você estiver publicando dados de uma versão anterior do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="003ee-104">You can also explicitly disable check constraints for replication, which can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="003ee-105">Se a uma tabela for publicada utilizando replicação, as verificações de restrições serão desabilitadas automaticamente em operações executadas por agentes de replicação.</span><span class="sxs-lookup"><span data-stu-id="003ee-105">If a table is published using replication, check constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="003ee-106">Quando um agente de replicação executa uma inserção, atualização ou exclusão em um Assinante, a restrição não é verificada; se um usuário executar uma inserção, atualização ou exclusão, a restrição será verificada.</span><span class="sxs-lookup"><span data-stu-id="003ee-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="003ee-107">A restrição está desabilitada para o agente de replicação porque a restrição já foi verificada no Publicador quando os dados foram inseridos, atualizados ou excluídos originalmente.</span><span class="sxs-lookup"><span data-stu-id="003ee-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span> <span data-ttu-id="003ee-108">Para obter mais informações, veja [Especificar opções de esquema](../replication/publish/specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="003ee-108">For more information, see [Specify Schema Options](../replication/publish/specify-schema-options.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="003ee-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="003ee-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="003ee-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="003ee-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="003ee-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="003ee-111">Permissions</span></span>  
 <span data-ttu-id="003ee-112">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="003ee-112">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="003ee-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="003ee-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="003ee-114">Desabilitar uma verificação de restrição de replicação</span><span class="sxs-lookup"><span data-stu-id="003ee-114">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="003ee-115">No **Pesquisador de Objetos**, expanda a tabela com a restrição de verificação a ser modificada e expanda a pasta **Restrições** .</span><span class="sxs-lookup"><span data-stu-id="003ee-115">In **Object Explorer**, expand the table with the check constraint you want to modify, and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="003ee-116">Clique com o botão direito do mouse na restrição de verificação que você deseja modificar e clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="003ee-116">Right-click the check constraint you wish to modify and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="003ee-117">Na caixa de diálogo **Verificar Restrições** , em **Designer de Tabela**, selecione um valor de **Não** para **Impor para replicação**.</span><span class="sxs-lookup"><span data-stu-id="003ee-117">In the **Check Constraints** dialog box, under **Table Designer**, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="003ee-118">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="003ee-118">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="003ee-119">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="003ee-119">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="003ee-120">Desabilitar uma verificação de restrição de replicação</span><span class="sxs-lookup"><span data-stu-id="003ee-120">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="003ee-121">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="003ee-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="003ee-122">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="003ee-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="003ee-123">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="003ee-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="003ee-124">O exemplo cria uma tabela com uma coluna IDENTITY e uma restrição CHECK na tabela.</span><span class="sxs-lookup"><span data-stu-id="003ee-124">The example creates a table with an IDENTITY column and a CHECK constraint on the table.</span></span> <span data-ttu-id="003ee-125">Em seguida, o exemplo remove a restrição e a recria especificando a cláusula NOT FOR REPLICATION.</span><span class="sxs-lookup"><span data-stu-id="003ee-125">The example then drops the constraint and recreates it specifying the NOT FOR REPLICATION clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.doc_exd (column_a int IDENTITY (1,1)   
    CONSTRAINT exd_check CHECK (column_a > 1))   
  
    ALTER TABLE dbo.doc_exd   
    DROP CONSTRAINT exd_check;   
    GO  
    ALTER TABLE dbo.doc_exd    
    ADD CONSTRAINT exd_check CHECK NOT FOR REPLICATION (column_a > 1);  
    ```  
  
 <span data-ttu-id="003ee-126">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="003ee-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>   
## <a name="see-also"></a><span data-ttu-id="003ee-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="003ee-127">See Also</span></span>  
 [<span data-ttu-id="003ee-128">Especificar opções de esquema</span><span class="sxs-lookup"><span data-stu-id="003ee-128">Specify Schema Options</span></span>](../replication/publish/specify-schema-options.md)  
  
  
