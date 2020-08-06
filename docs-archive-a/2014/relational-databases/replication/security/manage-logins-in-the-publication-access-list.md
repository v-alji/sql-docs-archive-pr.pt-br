---
title: Gerenciar logons na Lista de Acesso à Publicação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server replication], publication access list
- publications [SQL Server replication], publication access lists
- publication access list (PAL)
- PAL (publication access list)
- logins [SQL Server replication], managing
ms.assetid: fceb216b-0b18-4e3b-8ae0-13e35920dcbc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b96e6f46403cf3a482f00a3f5155527177920967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571925"
---
# <a name="manage-logins-in-the-publication-access-list"></a><span data-ttu-id="3cab4-102">Gerenciar logons na lista de acesso à publicação</span><span class="sxs-lookup"><span data-stu-id="3cab4-102">Manage Logins in the Publication Access List</span></span>
  <span data-ttu-id="3cab4-103">Este tópico descreve como gerenciar logons na Lista de Acesso à Publicação no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cab4-103">This topic describes how to manage logins in the Publication Access List in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3cab4-104">O acesso a uma publicação é controlado pela PAL (lista de acesso à publicação).</span><span class="sxs-lookup"><span data-stu-id="3cab4-104">Access to a publication is controlled by the publication access list (PAL).</span></span> <span data-ttu-id="3cab4-105">É possível adicionar e remover logons e grupos do PAL.</span><span class="sxs-lookup"><span data-stu-id="3cab4-105">Logins and groups can be added and removed from the PAL.</span></span>  
  
 <span data-ttu-id="3cab4-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="3cab4-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3cab4-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="3cab4-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3cab4-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3cab4-108">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="3cab4-109">**Para gerenciar logons na Lista de Acesso à Publicação, usando:**</span><span class="sxs-lookup"><span data-stu-id="3cab4-109">**To manage logins in the Publication Access List, using:**</span></span>  
  
     [<span data-ttu-id="3cab4-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3cab4-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3cab4-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cab4-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3cab4-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3cab4-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="3cab4-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3cab4-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="3cab4-114">Você deve associar o logon do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] com um usuário de banco de dados no banco de dados de publicação antes de adicionar o logon à PAL.</span><span class="sxs-lookup"><span data-stu-id="3cab4-114">You must associate the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login with a database user in the publication database before you add the login to the PAL.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3cab4-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3cab4-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3cab4-116">Use a PAL (lista de acesso à publicação) na página **Lista de Acesso à Publicação** da caixa de diálogo **Propriedades da Publicação – \<Publication>** para gerenciar logons.</span><span class="sxs-lookup"><span data-stu-id="3cab4-116">You use the publication access list (PAL) on the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box to manage logins.</span></span> <span data-ttu-id="3cab4-117">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [Exibir e modificar as propriedades da publicação](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3cab4-117">For more information about how to access this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-manage-logins-in-the-pal"></a><span data-ttu-id="3cab4-118">Para gerenciar logons na PAL</span><span class="sxs-lookup"><span data-stu-id="3cab4-118">To manage logins in the PAL</span></span>  
  
1.  <span data-ttu-id="3cab4-119">Na página **Lista de Acesso à Publicação** da caixa de diálogo **Propriedades da Publicação – \<Publication>** , use os botões **Adicionar**, **Remover** e **Remover Tudo** para adicionar e remover logons e grupos da PAL.</span><span class="sxs-lookup"><span data-stu-id="3cab4-119">On the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box, use the **Add**, **Remove**, and **Remove All** buttons to add and remove logins and groups from the PAL.</span></span> <span data-ttu-id="3cab4-120">Não remova o **distributor_admin** da PAL.</span><span class="sxs-lookup"><span data-stu-id="3cab4-120">Do not remove **distributor_admin** from the PAL.</span></span> <span data-ttu-id="3cab4-121">Essa conta é usada para replicação.</span><span class="sxs-lookup"><span data-stu-id="3cab4-121">This account is used by replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3cab4-122">Se for usado um Distribuidor remoto, as contas da PAL precisarão estar disponíveis tanto no Publicador quanto no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="3cab4-122">If a remote Distributor is used, accounts in the PAL must be available at both the Publisher and the Distributor.</span></span> <span data-ttu-id="3cab4-123">A conta ou deve ser uma conta de domínio ou uma conta local que é definida em ambos os servidores.</span><span class="sxs-lookup"><span data-stu-id="3cab4-123">The account must be either a domain account or a local account that is defined at both servers.</span></span> <span data-ttu-id="3cab4-124">As senhas associadas a ambos os logons devem ser as mesmas.</span><span class="sxs-lookup"><span data-stu-id="3cab4-124">The passwords that are associated with both logins must be the same.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3cab4-125">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cab4-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-groups-and-logins-that-belong-to-the-pal"></a><span data-ttu-id="3cab4-126">Para exibir grupos e logons que pertencem à PAL</span><span class="sxs-lookup"><span data-stu-id="3cab4-126">To view groups and logins that belong to the PAL</span></span>  
  
1.  <span data-ttu-id="3cab4-127">No Publicador do banco de dados da publicação, execute [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cab4-127">At the Publisher on the publication database, execute [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql).</span></span> <span data-ttu-id="3cab4-128">Para \*\* \@ publicação\*\*, especifique o nome da publicação.</span><span class="sxs-lookup"><span data-stu-id="3cab4-128">For **\@publication**, specify the publication name.</span></span> <span data-ttu-id="3cab4-129">Isso exibe informações sobre os grupos e logons na PAL.</span><span class="sxs-lookup"><span data-stu-id="3cab4-129">This displays information about the groups and logins in the PAL.</span></span>  
  
#### <a name="to-add-groups-and-logins-to-the-pal"></a><span data-ttu-id="3cab4-130">Para adicionar grupos e logons à PAL</span><span class="sxs-lookup"><span data-stu-id="3cab4-130">To add groups and logins to the PAL</span></span>  
  
1.  <span data-ttu-id="3cab4-131">No Publicador do banco de dados da publicação, execute [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cab4-131">At the Publisher on the publication database, execute [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql).</span></span> <span data-ttu-id="3cab4-132">Para \*\* \@ publicação**, especifique o nome da publicação e, para \*\* \@ logon**, especifique o nome do logon ou grupo que está sendo adicionado.</span><span class="sxs-lookup"><span data-stu-id="3cab4-132">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being added.</span></span>  
  
#### <a name="to-remove-groups-and-logins-from-the-pal"></a><span data-ttu-id="3cab4-133">Para remover grupos e logons da PAL</span><span class="sxs-lookup"><span data-stu-id="3cab4-133">To remove groups and logins from the PAL</span></span>  
  
1.  <span data-ttu-id="3cab4-134">No Publicador do banco de dados da publicação, execute [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cab4-134">At the Publisher on the publication database, execute [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql).</span></span> <span data-ttu-id="3cab4-135">Para \*\* \@ publicação**, especifique o nome da publicação e, para \*\* \@ logon**, especifique o nome do logon ou grupo que está sendo removido.</span><span class="sxs-lookup"><span data-stu-id="3cab4-135">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cab4-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3cab4-136">See Also</span></span>  
 <span data-ttu-id="3cab4-137">[Modelo de segurança do agente de replicação](replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="3cab4-137">[Replication Agent Security Model](replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="3cab4-138">[Proteger uma topologia de replicação](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="3cab4-138">[Secure a Replication Topology](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="3cab4-139">Proteger o Publicador</span><span class="sxs-lookup"><span data-stu-id="3cab4-139">Secure the Publisher</span></span>](secure-the-publisher.md)  
  
  
