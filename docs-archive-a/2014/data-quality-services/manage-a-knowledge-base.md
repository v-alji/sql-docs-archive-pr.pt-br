---
title: Gerenciar uma base de dados de conhecimento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 27f306f4-d67c-47f5-b35c-4260cc5d36e3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cc5fdd87ddb3ea687db10a29d7001564fd8ff107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582633"
---
# <a name="manage-a-knowledge-base"></a><span data-ttu-id="3dd98-102">Gerenciar uma base de dados de conhecimento</span><span class="sxs-lookup"><span data-stu-id="3dd98-102">Manage a Knowledge Base</span></span>
  <span data-ttu-id="3dd98-103">Este tópico descreve como executar funções de gerenciamento em uma base de dados de conhecimento no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="3dd98-103">This topic describes how to perform management functions on a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="3dd98-104">Você pode excluir uma base de dados de conhecimento, desbloqueá-la, descartar seu trabalho nela, renomeá-la e exibir suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="3dd98-104">You can delete a knowledge base, unlock it, discard your work on it, rename it, and display its properties.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3dd98-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3dd98-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="3dd98-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3dd98-106">Prerequisites</span></span>  
 <span data-ttu-id="3dd98-107">Para gerenciar uma base de dados de conhecimento, ela já deve ter sido criada e publicada (caso outra pessoa a tenha criado) ou fechada (se você a criou).</span><span class="sxs-lookup"><span data-stu-id="3dd98-107">To manage a knowledge base, the knowledge base must have already been created, and either published (if another person created it) or have been closed (if you created it).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3dd98-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="3dd98-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3dd98-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="3dd98-109">Permissions</span></span>  
 <span data-ttu-id="3dd98-110">Você deve ter a função dqs_kb_editor ou dqs_administrator no banco de dados DQS_MAIN para abrir uma base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="3dd98-110">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to open a knowledge base.</span></span>  
  
##  <a name="manage-a-knowledge-base"></a><a name="Manage"></a><span data-ttu-id="3dd98-111">Gerenciar uma base de dados de conhecimento</span><span class="sxs-lookup"><span data-stu-id="3dd98-111">Manage a Knowledge Base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="3dd98-112">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="3dd98-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="3dd98-113">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Abrir base de dados de conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="3dd98-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base**.</span></span>  
  
3.  <span data-ttu-id="3dd98-114">Clique com o botão direito do mouse em uma base de dados de conhecimento na tabela de bases de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="3dd98-114">Right-click a knowledge base in the knowledge base table.</span></span>  
  
4.  <span data-ttu-id="3dd98-115">No menu de contexto, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3dd98-115">In the context menu, you can do the following:</span></span>  
  
    1.  <span data-ttu-id="3dd98-116">**Abrir**: clique para abrir a base de dados de conhecimento na atividade selecionada do painel **Selecionar Atividade** .</span><span class="sxs-lookup"><span data-stu-id="3dd98-116">**Open**: Click to open the knowledge base in the activity selected in the **Select Activity** pane.</span></span>  
  
    2.  <span data-ttu-id="3dd98-117">**Desbloquear**: você pode desbloquear a base de dados de conhecimento se você for o usuário que estava trabalhando nela em uma das etapas do gerenciamento de domínio, da descoberta de conhecimento e da atividade de política de correspondência, e a fechou.</span><span class="sxs-lookup"><span data-stu-id="3dd98-117">**Unlock**: You can unlock the knowledge base if you are the user who was working on the knowledge base in one of the steps of domain management, knowledge discovery, and the matching policy activity, and closed it.</span></span> <span data-ttu-id="3dd98-118">Se você descarregar a base de dados de conhecimento, outra pessoa poderá abri-la e trabalhar nela.</span><span class="sxs-lookup"><span data-stu-id="3dd98-118">If you unload the knowledge base, another person will be able to open it and work on it.</span></span> <span data-ttu-id="3dd98-119">Este comando não estará disponível se a base de dados de conhecimento não estiver no estado de uma atividade.</span><span class="sxs-lookup"><span data-stu-id="3dd98-119">This command is not available if the knowledge base is not in a state of an activity.</span></span> <span data-ttu-id="3dd98-120">Para obter mais informações, consulte [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="3dd98-120">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    3.  <span data-ttu-id="3dd98-121">**Descartar trabalho**: clique quando a base de dados de conhecimento estiver em um estado que indique que ela está sendo usado no momento, conforme mostrado no campo Estado da tabela.</span><span class="sxs-lookup"><span data-stu-id="3dd98-121">**Discard work**: Click when the knowledge base is in a state of being worked on, as shown with an entry in the State field in the table.</span></span> <span data-ttu-id="3dd98-122">Este comando não estará disponível se a base de dados de conhecimento não estiver no estado de uma atividade e se a base de dados de conhecimento estiver bloqueada.</span><span class="sxs-lookup"><span data-stu-id="3dd98-122">This command is not available if the knowledge base is not in a state of an activity, and it is not available if the knowledge base is locked.</span></span> <span data-ttu-id="3dd98-123">Para obter mais informações, consulte [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="3dd98-123">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    4.  <span data-ttu-id="3dd98-124">**Renomear**: clique para tornar o campo Base de Dados de Conhecimento da tabela editável para a base de dados de conhecimento na qual você clicou o botão direito do mouse.</span><span class="sxs-lookup"><span data-stu-id="3dd98-124">**Rename**: Click to make the Knowledge Base field of the table editable for the knowledge base that you right-clicked on.</span></span> <span data-ttu-id="3dd98-125">Altere o nome e clique nessa base de dados de conhecimento e em outra no campo p0ara aceitar a alteração do nome.</span><span class="sxs-lookup"><span data-stu-id="3dd98-125">Change the name, and then click on that knowledge base and another one in the field to accept the name change.</span></span>  
  
    5.  <span data-ttu-id="3dd98-126">**Excluir**: clique para remover a base de dados de conhecimento do banco de dados DQS_MAIN no [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3dd98-126">**Delete**: Click to remove the knowledge base from the DQS_MAIN database on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
    6.  <span data-ttu-id="3dd98-127">**Propriedades**: clique para exibir as propriedades do banco de dados em uma exibição somente leitura.</span><span class="sxs-lookup"><span data-stu-id="3dd98-127">**Properties**: Click to display properties for the database in a read-only display.</span></span>  
  
        1.  <span data-ttu-id="3dd98-128">**Base de Dados de Conhecimento de Origem**: a base de dados de conhecimento na qual este banco de dados se baseia.</span><span class="sxs-lookup"><span data-stu-id="3dd98-128">**Source Knowledge Base**: the knowledge base that this database was based on.</span></span> <span data-ttu-id="3dd98-129">Esse campo é opcional.</span><span class="sxs-lookup"><span data-stu-id="3dd98-129">This is optional.</span></span>  
  
        2.  <span data-ttu-id="3dd98-130">**Estado**: indicará se a base de dados de conhecimento está **Em Serviço** e se está em uma atividade de gerenciamento de conhecimento específica, conforme determinado quando ela foi fechada pela última vez.</span><span class="sxs-lookup"><span data-stu-id="3dd98-130">**State**: Indicates if the knowledge base is **In Work** and if it is in a specific knowledge management activity, as determined when it was last closed.</span></span> <span data-ttu-id="3dd98-131">O estado pode ser **Em Serviço**, no qual a base de dados de conhecimento é aberta em uma sessão de gerenciamento de conhecimento, mas não em uma atividade específica, ou **Em Serviço** mais uma atividade de gerenciamento de conhecimento, na qual a base de dados de conhecimento é aberta em uma sessão de gerenciamento de conhecimento, e em uma atividade específica.</span><span class="sxs-lookup"><span data-stu-id="3dd98-131">The state can be **In Work**, in which the knowledge base is opened in a knowledge management session, but not in a specific activity, or **In Work** plus a knowledge management activity, in which the knowledge base is opened in a knowledge management session, and in a specific activity.</span></span>  
  
        3.  <span data-ttu-id="3dd98-132">**Está Bloqueado**: **Verdadeiro** se a base de dados de conhecimento foi bloqueada; **Falso** se a base de dados de conhecimento não foi bloqueada.</span><span class="sxs-lookup"><span data-stu-id="3dd98-132">**Is Locked**: **True** if the knowledge base was locked, **False** if not</span></span>  
  
        4.  <span data-ttu-id="3dd98-133">**Contém conteúdo não publicado**: Verdadeiro se a base de dados de conhecimento contiver algum conteúdo que não foi salvo durante a publicação; caso contrário, será Falso.</span><span class="sxs-lookup"><span data-stu-id="3dd98-133">**Contains unpublished content**: True if the knowledge base contains content that has not been saved by publishing, False if not</span></span>  
  
        5.  <span data-ttu-id="3dd98-134">**Bloqueado por**: o nome do usuário que fechou a base de dados de conhecimento, bloqueando-a</span><span class="sxs-lookup"><span data-stu-id="3dd98-134">**Locked By**: the name of the user who closed the knowledge base, locking it</span></span>  
  
        6.  <span data-ttu-id="3dd98-135">**Data do Bloqueio**: data em que o bloqueio foi feito</span><span class="sxs-lookup"><span data-stu-id="3dd98-135">**Locked Date**: date when locked</span></span>  
  
        7.  <span data-ttu-id="3dd98-136">**Criado por**: o nome do usuário que criou a base de dados de conhecimento, com a rede à qual ele pertence</span><span class="sxs-lookup"><span data-stu-id="3dd98-136">**Created By**: the name of the user who created the knowledge base, with the network that he or she belongs to</span></span>  
  
        8.  <span data-ttu-id="3dd98-137">**Data de Criação**: data em que a criação foi realizada</span><span class="sxs-lookup"><span data-stu-id="3dd98-137">**Created Date**: date when created</span></span>  
  
##  <a name="follow-up-after-managing-a-knowledge-base"></a><a name="FollowUp"></a><span data-ttu-id="3dd98-138">Acompanhamento: depois de gerenciar uma base de dados de conhecimento</span><span class="sxs-lookup"><span data-stu-id="3dd98-138">Follow Up: After Managing a Knowledge Base</span></span>  
 <span data-ttu-id="3dd98-139">Depois que você gerenciar uma base de dados de conhecimento, a próxima etapa dependerá da ação executada na base de dados de conhecimento:</span><span class="sxs-lookup"><span data-stu-id="3dd98-139">After you manage a knowledge base, your next step depends upon the action you took on the knowledge base:</span></span>  
  
-   <span data-ttu-id="3dd98-140">Se você abriu a base de dados de conhecimento, continuará na atividade que selecionou.</span><span class="sxs-lookup"><span data-stu-id="3dd98-140">If you opened the knowledge base, you will continue in the activity that you selected.</span></span>  
  
-   <span data-ttu-id="3dd98-141">Se você a desbloqueou, ela estará disponível para outra pessoa abrir e trabalhar nela, no estado indicado.</span><span class="sxs-lookup"><span data-stu-id="3dd98-141">If you unlocked it, it will be available for another person to open and work on, in the state indicated.</span></span>  
  
-   <span data-ttu-id="3dd98-142">Se você descartou o trabalho nela, a base de dados de conhecimento estará disponível em seu último estado publicado.</span><span class="sxs-lookup"><span data-stu-id="3dd98-142">If you discarded the work on it, the knowledge base will be available in its last published state.</span></span>  
  
-   <span data-ttu-id="3dd98-143">Se você a renomeou, precisará abrir a base de dados de conhecimento renomeada para trabalhar nela.</span><span class="sxs-lookup"><span data-stu-id="3dd98-143">If you renamed it, you will have to open the renamed knowledge base to work on it.</span></span>  
  
-   <span data-ttu-id="3dd98-144">Se você a excluiu, precisará selecionar outra base de dados de conhecimento para trabalhar ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="3dd98-144">If you delete it, you will have to select another knowledge base to work on, or create a new one.</span></span>  
  
  
