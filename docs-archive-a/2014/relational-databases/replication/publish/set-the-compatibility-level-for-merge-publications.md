---
title: Definir o nível de compatibilidade para publicações de mesclagem | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], replication
- backward compatibility [SQL Server], replication
- publications [SQL Server replication], backward compatibility
ms.assetid: db47ac73-948b-4d77-b272-bb3565135ea5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04ad80b0c99e7282ff2acfa459a08665efbdee1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583497"
---
# <a name="set-the-compatibility-level-for-merge-publications"></a><span data-ttu-id="cbc06-102">Definir o nível de compatibilidade para publicações de mesclagem</span><span class="sxs-lookup"><span data-stu-id="cbc06-102">Set the Compatibility Level for Merge Publications</span></span>
  <span data-ttu-id="cbc06-103">Este tópico descreve como definir o nível de compatibilidade de publicações de mesclagem no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbc06-103">This topic describes how to set the compatibility level for merge publications in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cbc06-104">A replicação de mesclagem usa o nível de compatibilidade da publicação para determinar quais recursos podem ser usados pelas publicações em um determinado banco de dados.</span><span class="sxs-lookup"><span data-stu-id="cbc06-104">Merge replication uses the publication compatibility level to determine which features can be used by publications in a given database.</span></span>  
  
 <span data-ttu-id="cbc06-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="cbc06-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cbc06-106">**Para definir o nível de compatibilidade para publicações de mesclagem, usando:**</span><span class="sxs-lookup"><span data-stu-id="cbc06-106">**To set the compatibility level for merge publications, using:**</span></span>  
  
     [<span data-ttu-id="cbc06-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cbc06-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cbc06-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cbc06-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cbc06-109">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cbc06-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="cbc06-110">Defina o nível de compatibilidade na página **Tipos de Assinante** do Assistente para Nova Publicação.</span><span class="sxs-lookup"><span data-stu-id="cbc06-110">Set the compatibility level on the **Subscriber Types** page of the New Publication Wizard.</span></span> <span data-ttu-id="cbc06-111">Para obter mais informações sobre como acessar esse assistente, consulte [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="cbc06-111">For more information on accessing this wizard, see [Create a Publication](create-a-publication.md).</span></span> <span data-ttu-id="cbc06-112">Depois da criação de um instantâneo de publicação, é possível aumentar mas não diminuir o nível de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="cbc06-112">After a publication snapshot is created, the compatibility level can be increased but cannot be decreased.</span></span> <span data-ttu-id="cbc06-113">Aumente o nível de compatibilidade na página **Geral** da caixa de diálogo **Propriedades de Publicação – \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="cbc06-113">Increase the compatibility level on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="cbc06-114">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="cbc06-114">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="cbc06-115">Se você aumentar o nível de compatibilidade da publicação, quaisquer assinaturas existentes nos servidores que executem versões anteriores ao nível de compatibilidade não conseguirão sincronizar.</span><span class="sxs-lookup"><span data-stu-id="cbc06-115">If you increase the publication compatibility level, any existing subscriptions at servers running versions prior to the compatibility level will no longer be able to synchronize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbc06-116">Como o nível de compatibilidade tem implicações para outras propriedades da publicação e para a definição de quais propriedades de artigo são válidas, não altere o nível de compatibilidade e outras propriedades no mesmo uso da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cbc06-116">Because the compatibility level has implications for other publication properties and for which article properties are valid, do not change the compatibility level and other properties in the same use of the dialog box.</span></span> <span data-ttu-id="cbc06-117">O instantâneo porque a publicação deveria ser regenerada depois que a propriedade seja alterada.</span><span class="sxs-lookup"><span data-stu-id="cbc06-117">The snapshot for the publication should be regenerated after the property is changed.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level"></a><span data-ttu-id="cbc06-118">Para definir o nível de compatibilidade de publicação</span><span class="sxs-lookup"><span data-stu-id="cbc06-118">To set the publication compatibility level</span></span>  
  
-   <span data-ttu-id="cbc06-119">Na página **Tipos de Assinante** do Assistente para Nova Publicação, selecione os tipos de Assinantes para os quais a publicação deve fornecer suporte.</span><span class="sxs-lookup"><span data-stu-id="cbc06-119">On the **Subscriber Types** page of the New Publication Wizard, select the types of Subscribers that the publication should support.</span></span>  
  
#### <a name="to-increase-the-publication-compatibility-level"></a><span data-ttu-id="cbc06-120">Para aumentar o nível de compatibilidade de publicação</span><span class="sxs-lookup"><span data-stu-id="cbc06-120">To increase the publication compatibility level</span></span>  
  
-   <span data-ttu-id="cbc06-121">Na página **Geral** da caixa de diálogo **Propriedades de Publicação – \<Publication>** , selecione **Nível de compatibilidade**.</span><span class="sxs-lookup"><span data-stu-id="cbc06-121">On the **General** page of the **Publication Properties - \<Publication>** dialog box, select for **Compatibility level**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cbc06-122">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cbc06-122">Using Transact-SQL</span></span>  
 <span data-ttu-id="cbc06-123">O nível de compatibilidade para uma publicação de mesclagem, pode ser definida, programaticamente, quando uma publicação é criada ou modificada programaticamente depois.</span><span class="sxs-lookup"><span data-stu-id="cbc06-123">The compatibility level for a merge publication can either be set programmatically when a publication is created or modified programmatically at a later time.</span></span> <span data-ttu-id="cbc06-124">Você pode usar procedimentos armazenados de replicação para definir ou alterar esta propriedade de publicação.</span><span class="sxs-lookup"><span data-stu-id="cbc06-124">You can use replication stored procedures to set or change this publication property.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level-for-a-merge-publication"></a><span data-ttu-id="cbc06-125">Para definir o nível de compatibilidade para uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="cbc06-125">To set the publication compatibility level for a merge publication</span></span>  
  
1.  <span data-ttu-id="cbc06-126">No Publicador, execute [sp_addmergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), especificando um valor para **@publication_compatibility_level** para tornar a publicação compatível com versões mais antigas do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbc06-126">At the Publisher, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value for **@publication_compatibility_level** to make the publication compatible with older versions of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cbc06-127">Para obter mais informações, consulte [Criar uma assinatura](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="cbc06-127">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="cbc06-128">Para definir o nível de compatibilidade da publicação de uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="cbc06-128">To change the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="cbc06-129">Execute [sp_changemergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), especificando **publication_compatibility_level** para **@property** e o nível de compatibilidade de publicação apropriado para o **@value** .</span><span class="sxs-lookup"><span data-stu-id="cbc06-129">Execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying **publication_compatibility_level** for **@property** and the appropriate publication compatibility level for **@value**.</span></span>  
  
#### <a name="to-determine-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="cbc06-130">Para determinar o nível de compatibilidade da publicação de uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="cbc06-130">To determine the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="cbc06-131">Execute [sp_helpmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), especificando a publicação desejada.</span><span class="sxs-lookup"><span data-stu-id="cbc06-131">Execute [sp_helpmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying the desired publication.</span></span>  
  
2.  <span data-ttu-id="cbc06-132">Localize o nível de compatibilidade da publicação na coluna **backward_comp_level** no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="cbc06-132">Locate the publication compatibility level in the **backward_comp_level** column in the result set.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="cbc06-133">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cbc06-133">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="cbc06-134">Esse exemplo cria uma publicação de mesclagem e define o nível de compatibilidade da publicação.</span><span class="sxs-lookup"><span data-stu-id="cbc06-134">This example creates a merge publication and sets the publication compatibility level.</span></span>  
  
```  
-- To avoid storing the login and password in the script file, the values   
-- are passed into SQLCMD as scripting variables. For information about   
-- how to use scripting variables on the command line and in SQL Server  
-- Management Studio, see the "Executing Replication Scripts" section in  
-- the topic "Programming Replication Using System Stored Procedures".  
  
--Add a new merge publication.  
DECLARE @publicationDB AS sysname;  
DECLARE @publication AS sysname;  
DECLARE @login AS sysname;  
DECLARE @password AS sysname;  
SET @publicationDB = N'AdventureWorks2012';   
SET @publication = N'AdvWorksSalesOrdersMerge'   
SET @login = $(Login);  
SET @password = $(Password);  
  
-- Create a new merge publication.   
USE [AdventureWorks2012]  
EXEC sp_addmergepublication   
@publication = @publication,   
-- Set the compatibility level to SQL Server 2014.  
@publication_compatibility_level = '120RTM';   
  
-- Create the snapshot job for the publication.  
EXEC sp_addpublication_snapshot   
@publication = @publication,  
@job_login = @login,  
@job_password = @password;  
GO  
```  
  
 <span data-ttu-id="cbc06-135">Esse exemplo altera uma publicação de mesclagem e define o nível de compatibilidade da publicação.</span><span class="sxs-lookup"><span data-stu-id="cbc06-135">This example changes the publication compatibility level for the merge publication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbc06-136">Alterar o nível de compatibilidade da publicação pode não ser permitido se a publicação usar qualquer recurso que necessite de um nível de compatibilidade específico.</span><span class="sxs-lookup"><span data-stu-id="cbc06-136">Changing the publication compatibility level might not be allowed if the publication uses any features that require a particular compatibility level.</span></span> <span data-ttu-id="cbc06-137">Para obter mais informações, consulte [Compatibilidade com versões anteriores de replicação](../replication-backward-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="cbc06-137">For more information, see [Replication Backward Compatibility](../replication-backward-compatibility.md).</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
  
-- Change the publication compatibility level to   
-- SQL Server 2012.  
EXEC sp_changemergepublication   
@publication = @publication,   
@property = N'publication_compatibility_level',   
@value = N'110RTM';  
GO  
  
```  
  
 <span data-ttu-id="cbc06-138">Esse exemplo retorna o nível de compatibilidade da publicação atual para a publicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="cbc06-138">This example returns the current publication compatibility level for the merge publication.</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
EXEC sp_helpmergepublication   
@publication = @publication;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbc06-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cbc06-139">See Also</span></span>  
 [<span data-ttu-id="cbc06-140">Criar uma publicação</span><span class="sxs-lookup"><span data-stu-id="cbc06-140">Create a Publication</span></span>](create-a-publication.md)  
  
  
