---
title: Gerenciar (abrir, desbloquear, renomear e excluir) um projeto de qualidade de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.opendqproject.f1
helpviewer_keywords:
- data quality project,delete
- data quality project,rename
- data quality project,unlock
- data quality project,open
ms.assetid: de8a2b04-4673-4beb-b4cf-96a28cdf3a93
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 216c95937676954c509890b879abdee8f55b778c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582620"
---
# <a name="manage-open-unlock-rename-and-delete-a-data-quality-project"></a><span data-ttu-id="aeb38-102">Gerenciar (abrir, desbloquear, renomear e excluir) um projeto de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="aeb38-102">Manage (Open, Unlock, Rename, and Delete) a Data Quality Project</span></span>
  <span data-ttu-id="aeb38-103">Este tópico descreve como gerenciar um projeto de qualidade de dados usando o [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , por exemplo, como abrir, desbloquear, renomear e excluir um projeto de qualidade de dados.</span><span class="sxs-lookup"><span data-stu-id="aeb38-103">This topic describes how to manage a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] such as open, unlock, rename, and delete a data quality project.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aeb38-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="aeb38-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="aeb38-105">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="aeb38-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="aeb38-106">Você não pode abrir um projeto bloqueado criado por outro usuário.</span><span class="sxs-lookup"><span data-stu-id="aeb38-106">You cannot open a locked project that is created by another user.</span></span>  
  
-   <span data-ttu-id="aeb38-107">Você não pode desbloquear, renomear ou excluir um projeto de qualidade de dados criado por outro usuário.</span><span class="sxs-lookup"><span data-stu-id="aeb38-107">You cannot unlock, rename, or delete a data quality project that is created by another user.</span></span>  
  
-   <span data-ttu-id="aeb38-108">Você não pode excluir um projeto de qualidade de dados bloqueado.</span><span class="sxs-lookup"><span data-stu-id="aeb38-108">You cannot delete a locked data quality project.</span></span> <span data-ttu-id="aeb38-109">Primeiro você deve desbloqueá-lo para excluir.</span><span class="sxs-lookup"><span data-stu-id="aeb38-109">You must first unlock it to delete.</span></span>  
  
-   <span data-ttu-id="aeb38-110">Você somente pode desbloquear um projeto de qualidade de dados criado por você.</span><span class="sxs-lookup"><span data-stu-id="aeb38-110">You can only unlock a data quality project that is created by you.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="aeb38-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="aeb38-111">Prerequisites</span></span>  
 <span data-ttu-id="aeb38-112">Você deve ter pelo menos um projeto de qualidade de dados para gerenciar.</span><span class="sxs-lookup"><span data-stu-id="aeb38-112">You must have at least one data quality project to manage.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aeb38-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="aeb38-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aeb38-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="aeb38-114">Permissions</span></span>  
 <span data-ttu-id="aeb38-115">Você deve ter a função dqs_kb_editor ou dqs_kb_operator no banco de dados DQS_MAIN para gerenciar um projeto de qualidade de dados.</span><span class="sxs-lookup"><span data-stu-id="aeb38-115">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to manage a data quality project.</span></span>  
  
##  <a name="open-a-data-quality-project"></a><a name="Open"></a> <span data-ttu-id="aeb38-116">Abrir um projeto de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="aeb38-116">Open a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="aeb38-117">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="aeb38-117">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="aeb38-118">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Abrir projeto de qualidade de dados**.</span><span class="sxs-lookup"><span data-stu-id="aeb38-118">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="aeb38-119">A tela **Abrir projeto** é aberta.</span><span class="sxs-lookup"><span data-stu-id="aeb38-119">The **Open project** screen appears.</span></span>  
  
     <span data-ttu-id="aeb38-120">Alternativamente, você pode abrir, de modo direto, um projeto de qualidade de dados listado em **Projeto de qualidade de dados recente** clicando nele.</span><span class="sxs-lookup"><span data-stu-id="aeb38-120">Alternately, you can directly open a data quality project listed under **Recent data quality project** area by clicking it.</span></span>  
  
3.  <span data-ttu-id="aeb38-121">Na tela **Abrir projeto** , clique para selecionar o projeto de qualidade de dados que você deseja abrir e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="aeb38-121">In the **Open project** screen, click to select the data quality project that you want to open, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="aeb38-122">O projeto de qualidade de dados é aberto no mesmo estado da atividade quando foi fechado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="aeb38-122">The data quality project opens at the same state of the activity where it was last closed.</span></span> <span data-ttu-id="aeb38-123">Um projeto de qualidade de dados tem os seguintes estados:</span><span class="sxs-lookup"><span data-stu-id="aeb38-123">A data quality project has the following states:</span></span>  
  
    -   <span data-ttu-id="aeb38-124">Para a atividade de **limpeza** , um projeto de qualidade de dados pode ter os seguintes Estados: **limpeza-mapa**, **limpeza-limpeza**, **limpeza-gerenciar e exibir resultados**e **limpeza-exportar**.</span><span class="sxs-lookup"><span data-stu-id="aeb38-124">For the **Cleansing** activity, a data quality project can have the following states: **Cleansing - Map**, **Cleansing - Cleanse**, **Cleansing - Manage and View Results**, and **Cleansing - Export**.</span></span>  
  
    -   <span data-ttu-id="aeb38-125">Para a atividade de **correspondência** , um projeto de qualidade de dados pode ter os seguintes Estados: **correspondência-mapa**, correspondência **de**correspondência, **correspondência-sobrevivência**e **exportação de correspondência**.</span><span class="sxs-lookup"><span data-stu-id="aeb38-125">For the **Matching** activity, a data quality project can have the following states: **Matching - Map**, **Matching - Matching**, **Matching - Survivorship**, and **Matching - Export**.</span></span>  
  
##  <a name="unlock-a-data-quality-project"></a><a name="Unlock"></a> <span data-ttu-id="aeb38-126">Desbloquear um projeto de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="aeb38-126">Unlock a Data Quality Project</span></span>  
 <span data-ttu-id="aeb38-127">Quando você cria um projeto de qualidade de dados, ele permanece em estado bloqueado para impedir seu uso ou modificação por outros usuários.</span><span class="sxs-lookup"><span data-stu-id="aeb38-127">When you create a data quality project, it is in a locked state to prevent usage or modification by other users.</span></span> <span data-ttu-id="aeb38-128">Você deverá desbloquear o projeto de qualidade de dados depois de concluir seu trabalho se quiser que outros usuários trabalhem no seu projeto de qualidade de dados.</span><span class="sxs-lookup"><span data-stu-id="aeb38-128">You must unlock the data quality project after you have completed your work if you want other users to work on your data quality project.</span></span> <span data-ttu-id="aeb38-129">Um símbolo de bloqueio é exibido para projetos que estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="aeb38-129">A lock symbol is displayed for projects that are locked.</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="aeb38-130">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="aeb38-130">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="aeb38-131">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Abrir projeto de qualidade de dados**.</span><span class="sxs-lookup"><span data-stu-id="aeb38-131">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="aeb38-132">A tela **Abrir projeto** é aberta.</span><span class="sxs-lookup"><span data-stu-id="aeb38-132">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="aeb38-133">Na tela **Abrir projeto** , clique com o botão direito do mouse no projeto de qualidade de dados bloqueado criado por você e clique em **Desbloquear** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="aeb38-133">In the **Open project** screen, right-click a locked data quality project that is created by you, and then click **Unlock** in the shortcut menu.</span></span> <span data-ttu-id="aeb38-134">Uma marca de seleção verde é exibida para o projeto, indicando que ele está desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="aeb38-134">A green check mark is displayed for the project indicating that it is unlocked.</span></span>  
  
##  <a name="rename-a-data-quality-project"></a><a name="Rename"></a> <span data-ttu-id="aeb38-135">Renomear um projeto de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="aeb38-135">Rename a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="aeb38-136">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="aeb38-136">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="aeb38-137">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Abrir projeto de qualidade de dados**.</span><span class="sxs-lookup"><span data-stu-id="aeb38-137">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="aeb38-138">A tela **Abrir projeto** é aberta.</span><span class="sxs-lookup"><span data-stu-id="aeb38-138">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="aeb38-139">Na tela **Abrir projeto** , clique com o botão direito do mouse no projeto de qualidade de dados criado por você e clique em **Renomear** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="aeb38-139">In the **Open project** screen, right-click a data quality project that is created by you, and then click **Rename** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="aeb38-140">O nome de projeto de qualidade de dados fica editável na coluna **Nome** .</span><span class="sxs-lookup"><span data-stu-id="aeb38-140">The data quality project name becomes editable in the **Name** column.</span></span> <span data-ttu-id="aeb38-141">Digite um novo nome e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="aeb38-141">Type a new name, and then press Enter.</span></span>  
  
##  <a name="delete-a-data-quality-project"></a><a name="Delete"></a> <span data-ttu-id="aeb38-142">Excluir um projeto de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="aeb38-142">Delete a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="aeb38-143">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="aeb38-143">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="aeb38-144">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Abrir projeto de qualidade de dados**.</span><span class="sxs-lookup"><span data-stu-id="aeb38-144">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="aeb38-145">A tela **Abrir projeto** é aberta.</span><span class="sxs-lookup"><span data-stu-id="aeb38-145">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="aeb38-146">Na tela **Abrir projeto** , clique com o botão direito do mouse em um projeto de qualidade de dados desbloqueado criado por você e clique em **Excluir** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="aeb38-146">In the **Open project** screen, right-click an unlocked data quality project that is created by you, and then click **Delete** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="aeb38-147">Será exibida uma mensagem de confirmação.</span><span class="sxs-lookup"><span data-stu-id="aeb38-147">A confirmation message appears.</span></span> <span data-ttu-id="aeb38-148">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="aeb38-148">Click **Yes**.</span></span>  
  
  
