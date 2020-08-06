---
title: Página minhas assinaturas (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 491a85a3-f323-4155-a0a8-de2779899995
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 891796ec491b157f3c9bb5b4adfd15daedbc7c88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684593"
---
# <a name="my-subscriptions-page-report-manager"></a><span data-ttu-id="cbf91-102">Página Minhas Assinaturas (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="cbf91-102">My Subscriptions Page (Report Manager)</span></span>
  <span data-ttu-id="cbf91-103">Use a página Minhas Assinaturas para exibir todas as suas assinaturas em um lugar.</span><span class="sxs-lookup"><span data-stu-id="cbf91-103">Use the My Subscriptions page to view all of your subscriptions in one place.</span></span> <span data-ttu-id="cbf91-104">Desta página, você pode acessar e modificar ou excluir qualquer assinatura que possui.</span><span class="sxs-lookup"><span data-stu-id="cbf91-104">From this page, you can access and modify or delete any subscription that you own.</span></span> <span data-ttu-id="cbf91-105">Você só possui as assinaturas que cria.</span><span class="sxs-lookup"><span data-stu-id="cbf91-105">You own only the subscriptions that you create.</span></span> <span data-ttu-id="cbf91-106">Você não pode acessar as de outros usuários nem pode acessar assinaturas que você usa, mas não possui (por exemplo, se seu nome foi adicionado a uma assinatura existente definida por outro usuário).</span><span class="sxs-lookup"><span data-stu-id="cbf91-106">You cannot access those of other users, nor can you access subscriptions that you use but do not own (for example, if your name has been added to an existing subscription defined by another user).</span></span> <span data-ttu-id="cbf91-107">Você não pode criar assinaturas nesta página.</span><span class="sxs-lookup"><span data-stu-id="cbf91-107">You cannot create subscriptions from this page.</span></span> <span data-ttu-id="cbf91-108">Para obter mais informações sobre como criar assinaturas, consulte a [página nova assinatura ou editar assinatura &#40;Report Manager&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cbf91-108">For more information about creating subscriptions, see the [New Subscription or Edit Subscription Page &#40;Report Manager&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md).</span></span>  
  
 <span data-ttu-id="cbf91-109">Por padrão, as assinaturas são classificadas em ordem alfabética pelo nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="cbf91-109">By default, subscriptions are sorted in alphabetical order by report name.</span></span> <span data-ttu-id="cbf91-110">Clique em um cabeçalho de coluna diferente para alterar o modo de classificação das assinaturas.</span><span class="sxs-lookup"><span data-stu-id="cbf91-110">Click a different column heading to change how subscriptions are sorted.</span></span> <span data-ttu-id="cbf91-111">Se você não tiver assinaturas ou se a permissão para criar ou gerenciar assinaturas estiver desabilitada, nenhuma assinatura será exibida na página.</span><span class="sxs-lookup"><span data-stu-id="cbf91-111">If you have no subscriptions or if permission to create or manage subscriptions is disabled, no subscriptions appear on the page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbf91-112">Este recurso não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbf91-112">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cbf91-113">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="cbf91-113">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="cbf91-114">Navegação</span><span class="sxs-lookup"><span data-stu-id="cbf91-114">Navigation</span></span>  
 <span data-ttu-id="cbf91-115">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="cbf91-115">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-my-subscriptions-page"></a><span data-ttu-id="cbf91-116">Para abrir a página Minhas Assinaturas</span><span class="sxs-lookup"><span data-stu-id="cbf91-116">To open the My Subscriptions page</span></span>  
  
1.  <span data-ttu-id="cbf91-117">Abra o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="cbf91-117">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="cbf91-118">Na parte superior da página, no canto direito, clique em Minhas Assinaturas.</span><span class="sxs-lookup"><span data-stu-id="cbf91-118">At the top of the page, in the right-hand corner, click My Subscriptions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbf91-119">A página Minhas Assinaturas está sempre disponível, mesmo que você não tenha permissão para criar assinaturas.</span><span class="sxs-lookup"><span data-stu-id="cbf91-119">My Subscriptions is always available, even if you lack permission to create subscriptions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cbf91-120">Opções</span><span class="sxs-lookup"><span data-stu-id="cbf91-120">Options</span></span>  
 <span data-ttu-id="cbf91-121">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="cbf91-121">**Delete**</span></span>  
 <span data-ttu-id="cbf91-122">Marque a caixa de seleção ao lado de cada assinatura que você deseja excluir e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="cbf91-122">Select the check box next to each subscription that you want to delete and click **Delete**.</span></span>  
  
 <span data-ttu-id="cbf91-123">**Editar**</span><span class="sxs-lookup"><span data-stu-id="cbf91-123">**Edit**</span></span>  
 <span data-ttu-id="cbf91-124">Clique para exibir ou editar a descrição.</span><span class="sxs-lookup"><span data-stu-id="cbf91-124">Click to view or edit the description.</span></span>  
  
 <span data-ttu-id="cbf91-125">**Report**</span><span class="sxs-lookup"><span data-stu-id="cbf91-125">**Report**</span></span>  
 <span data-ttu-id="cbf91-126">Mostra o relatório que é especificado na assinatura.</span><span class="sxs-lookup"><span data-stu-id="cbf91-126">Shows the report that is specified in the subscription.</span></span> <span data-ttu-id="cbf91-127">Clique no nome do relatório para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="cbf91-127">Click the report name to view the report.</span></span>  
  
 <span data-ttu-id="cbf91-128">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cbf91-128">**Description**</span></span>  
 <span data-ttu-id="cbf91-129">Mostra uma descrição da assinatura.</span><span class="sxs-lookup"><span data-stu-id="cbf91-129">Shows a description of the subscription.</span></span> <span data-ttu-id="cbf91-130">Clique na descrição para exibir ou editar as informações de assinatura para o relatório.</span><span class="sxs-lookup"><span data-stu-id="cbf91-130">Click the description to view or edit the subscription information for the report.</span></span>  
  
 <span data-ttu-id="cbf91-131">**Pasta**</span><span class="sxs-lookup"><span data-stu-id="cbf91-131">**Folder**</span></span>  
 <span data-ttu-id="cbf91-132">Exibe a pasta que contém o relatório especificado na assinatura.</span><span class="sxs-lookup"><span data-stu-id="cbf91-132">Shows the folder that contains the report that is specified in the subscription.</span></span> <span data-ttu-id="cbf91-133">Clique no nome de pasta para exibir o conteúdo da pasta.</span><span class="sxs-lookup"><span data-stu-id="cbf91-133">Click the folder name to view the contents of the folder.</span></span>  
  
 <span data-ttu-id="cbf91-134">**Gatilho**</span><span class="sxs-lookup"><span data-stu-id="cbf91-134">**Trigger**</span></span>  
 <span data-ttu-id="cbf91-135">Identifica critérios que causam a execução da assinatura.</span><span class="sxs-lookup"><span data-stu-id="cbf91-135">Identifies criteria that cause the subscription to run.</span></span> <span data-ttu-id="cbf91-136">Um gatilho **TimedSubscription** é baseado em uma agenda que define quando a assinatura é executada.</span><span class="sxs-lookup"><span data-stu-id="cbf91-136">A **TimedSubscription** trigger is based on a schedule that defines when the subscription runs.</span></span> <span data-ttu-id="cbf91-137">Um gatilho **SnapshotUpdated** é baseado em uma atualização de um instantâneo de relatório.</span><span class="sxs-lookup"><span data-stu-id="cbf91-137">A **SnapshotUpdated** trigger is based on an update to a report snapshot.</span></span>  
  
 <span data-ttu-id="cbf91-138">**Última Execução**</span><span class="sxs-lookup"><span data-stu-id="cbf91-138">**Last Run**</span></span>  
 <span data-ttu-id="cbf91-139">Exibe a última vez em que a assinatura foi processada.</span><span class="sxs-lookup"><span data-stu-id="cbf91-139">Shows the last time that the subscription was processed.</span></span>  
  
 <span data-ttu-id="cbf91-140">**Status**</span><span class="sxs-lookup"><span data-stu-id="cbf91-140">**Status**</span></span>  
 <span data-ttu-id="cbf91-141">Exibe o status da assinatura.</span><span class="sxs-lookup"><span data-stu-id="cbf91-141">Shows the status of the subscription.</span></span> <span data-ttu-id="cbf91-142">Geralmente, o valor do status é "Novo" ou a data e hora da última execução da assinatura.</span><span class="sxs-lookup"><span data-stu-id="cbf91-142">Usually, the status value is either "New" or the date and time at which the subscription last ran.</span></span>  
  
 <span data-ttu-id="cbf91-143">Um valor de status "Dados Incorretos" ocorre quando a assinatura inclui um ponteiro para valores criptografados que não são mais válidos (ou seja, para as credenciais armazenadas usadas para executar o relatório).</span><span class="sxs-lookup"><span data-stu-id="cbf91-143">A status value of "Bad Data" occurs when the subscription includes a pointer to encrypted values that are no longer valid (that is, to the stored credentials used to run the report).</span></span> <span data-ttu-id="cbf91-144">Valores criptografados existentes se tornam inutilizáveis quando as chaves simétricas usadas para criptografar e descriptografar dados são recriadas no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="cbf91-144">Existing encrypted values become unusable when the symmetric keys used to encrypt and decrypt data are recreated on the report server.</span></span>  
  
 <span data-ttu-id="cbf91-145">Uma assinatura não poderá ser processada se tiver sido desativada.</span><span class="sxs-lookup"><span data-stu-id="cbf91-145">A subscription cannot be processed if it has been deactivated.</span></span> <span data-ttu-id="cbf91-146">Para atualizar a assinatura e torná-la operacional, abra e depois salve a assinatura.</span><span class="sxs-lookup"><span data-stu-id="cbf91-146">To update the subscription and make it operational, open and then save the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf91-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cbf91-147">See Also</span></span>  
 <span data-ttu-id="cbf91-148">[Assinaturas e entrega &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="cbf91-148">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="cbf91-149">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="cbf91-149">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
