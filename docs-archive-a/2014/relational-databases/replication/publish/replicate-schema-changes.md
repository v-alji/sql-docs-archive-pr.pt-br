---
title: Replicar alterações de esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], schema changes
- schemas [SQL Server replication], replicating changes
ms.assetid: c09007f0-9374-4f60-956b-8a87670cd043
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bec2f363cd8c4f7dea45935568a88722b19323fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574655"
---
# <a name="replicate-schema-changes"></a><span data-ttu-id="5b6a3-102">Replicar alterações de esquema</span><span class="sxs-lookup"><span data-stu-id="5b6a3-102">Replicate Schema Changes</span></span>
  <span data-ttu-id="5b6a3-103">Este tópico descreve como replicar alterações de esquema no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b6a3-103">This topic describes how to replicate schema changes in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5b6a3-104">Se você fizer as seguintes alterações de esquema um artigo publicado, elas serão propagadas, por padrão, a todos os Assinantes do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5b6a3-104">If you make the following schema changes to a published article, they are propagated, by default, to [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers:</span></span>  
  
-   <span data-ttu-id="5b6a3-105">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="5b6a3-105">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="5b6a3-106">ALTER VIEW</span><span class="sxs-lookup"><span data-stu-id="5b6a3-106">ALTER VIEW</span></span>  
  
-   <span data-ttu-id="5b6a3-107">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="5b6a3-107">ALTER PROCEDURE</span></span>  
  
-   <span data-ttu-id="5b6a3-108">ALTER FUNCTION</span><span class="sxs-lookup"><span data-stu-id="5b6a3-108">ALTER FUNCTION</span></span>  
  
-   <span data-ttu-id="5b6a3-109">ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="5b6a3-109">ALTER TRIGGER</span></span>  
  
 <span data-ttu-id="5b6a3-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="5b6a3-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b6a3-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="5b6a3-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b6a3-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5b6a3-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   <span data-ttu-id="5b6a3-113">**Para replicar alterações de esquema usando:**</span><span class="sxs-lookup"><span data-stu-id="5b6a3-113">**To replicate schema changes, using:**</span></span>  
  
     [<span data-ttu-id="5b6a3-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b6a3-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5b6a3-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b6a3-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b6a3-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5b6a3-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5b6a3-117">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5b6a3-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5b6a3-118">A ALTER TABLE ... DROP COLUMN é sempre replicada para todos os Assinantes cuja assinatura contém as colunas que estão sendo descartadas, mesmo se você desabilitar a replicação de alterações de esquema.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-118">The ALTER TABLE ... DROP COLUMN statement is always replicated to all Subscribers whose subscription contains the columns being dropped, even if you disable the replication of schema changes.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5b6a3-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b6a3-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5b6a3-120">Se você não deseja replicar alterações de esquema para uma publicação, desabilite a replicação de alterações de esquema na caixa de diálogo **Propriedades de Publicação – \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="5b6a3-120">If you do not want to replicate schema changes for a publication, disable the replication of schema changes in the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="5b6a3-121">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5b6a3-121">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-disable-replication-of-schema-changes"></a><span data-ttu-id="5b6a3-122">Para desabilitar a replicação de alterações de esquema</span><span class="sxs-lookup"><span data-stu-id="5b6a3-122">To disable replication of schema changes</span></span>  
  
1.  <span data-ttu-id="5b6a3-123">Na página **Opções de Assinatura** da caixa de diálogo **Propriedades de Publicação – \<Publication>** , defina o valor da propriedade **Replicar alterações de esquema** como **False**.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-123">On the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box, set the value of the **Replicate schema changes** property to **False**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="5b6a3-124">Para propagar apenas alterações de esquema específicas, defina a propriedade como **True** antes de uma alteração de esquema e, então, defina-a como **False** depois que a alteração for feita.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-124">To propagate only specific schema changes, set the property to **True** before a schema change, and then set it to **False** after the change is made.</span></span> <span data-ttu-id="5b6a3-125">Por outro lado, para propagar a maioria das alterações de esquema, mas não uma determinada alteração, defina a propriedade como **False** antes da alteração de esquema e, então, defina-a como **True** depois que a alteração for feita.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-125">Conversely, to propagate most schema changes, but not a given change, set the property to **False** before the schema change, and then set it to **True** after the change is made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5b6a3-126">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b6a3-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="5b6a3-127">Você pode usar procedimentos armazenados de replicação para especificar se estas alterações de esquema serão replicadas.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-127">You can use replication stored procedures to specify whether these schema changes are replicated.</span></span> <span data-ttu-id="5b6a3-128">O procedimento armazenado usado depende do tipo de publicação.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-128">The stored procedure that you use depends on the type of publication.</span></span>  
  
#### <a name="to-create-a-snapshot-or-transactional-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="5b6a3-129">Para criar um instantâneo ou publicação transacional que não replicam alterações de esquema</span><span class="sxs-lookup"><span data-stu-id="5b6a3-129">To create a snapshot or transactional publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="5b6a3-130">No Publicador do banco de dados de publicação, execute [sp_addpublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql), especificando um valor de **0** para \*\* \@ replicate_ddl\*\*.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-130">At the Publisher on the publication database, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="5b6a3-131">Para obter mais informações, consulte [Criar uma assinatura](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="5b6a3-131">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-create-a-merge-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="5b6a3-132">Para criar uma publicação de mesclagem que não reproduz alterações de esquema</span><span class="sxs-lookup"><span data-stu-id="5b6a3-132">To create a merge publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="5b6a3-133">No Publicador do banco de dados de publicação, execute [sp_addmergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), especificando um valor de **0** para \*\* \@ replicate_ddl\*\*.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-133">At the Publisher on the publication database, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="5b6a3-134">Para obter mais informações, consulte [Criar uma assinatura](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="5b6a3-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-snapshot-or-transactional-publication"></a><span data-ttu-id="5b6a3-135">Para desabilitar temporariamente a replicação das alterações de esquema para um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="5b6a3-135">To temporarily disable replicating schema changes for a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="5b6a3-136">Para uma publicação com replicação de alterações de esquema, execute [sp_changepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), especificando um valor **de replicate_ddl** para \*\* \@ Propriedade\*\* e um valor de **0** para \*\* \@ valor\*\*.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-136">For a publication with replication of schema changes, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="5b6a3-137">Execute o comando DDL no objeto publicado.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-137">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="5b6a3-138">Adicional Habilite novamente a replicação de alterações de esquema executando [sp_changepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), especificando um valor **de replicate_ddl** para \*\* \@ Propriedade\*\* e um valor de **1** para \*\* \@ valor\*\*.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-138">(Optional) Re-enable replicating schema changes by executing [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-merge-publication"></a><span data-ttu-id="5b6a3-139">Para desabilitar temporariamente a replicação das alterações de esquema para uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="5b6a3-139">To temporarily disable replicating schema changes for a merge publication</span></span>  
  
1.  <span data-ttu-id="5b6a3-140">Para uma publicação com replicação de alterações de esquema, execute [sp_changemergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), especificando um valor **de replicate_ddl** para \*\* \@ Propriedade\*\* e um valor de **0** para \*\* \@ valor\*\*.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-140">For a publication with replication of schema changes, execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="5b6a3-141">Execute o comando DDL no objeto publicado.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-141">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="5b6a3-142">Adicional Habilite novamente a replicação de alterações de esquema executando [sp_changemergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), especificando um valor **de replicate_ddl** para \*\* \@ Propriedade\*\* e um valor de **1** para \*\* \@ valor\*\*.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-142">(Optional) Re-enable replicating schema changes by executing [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6a3-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5b6a3-143">See Also</span></span>  
 <span data-ttu-id="5b6a3-144">[Fazer alterações de esquema em bancos de dados de publicação](make-schema-changes-on-publication-databases.md) </span><span class="sxs-lookup"><span data-stu-id="5b6a3-144">[Make Schema Changes on Publication Databases](make-schema-changes-on-publication-databases.md) </span></span>  
 [<span data-ttu-id="5b6a3-145">Fazer alterações de esquema em bancos de dados de publicação</span><span class="sxs-lookup"><span data-stu-id="5b6a3-145">Make Schema Changes on Publication Databases</span></span>](make-schema-changes-on-publication-databases.md)  
  
  
