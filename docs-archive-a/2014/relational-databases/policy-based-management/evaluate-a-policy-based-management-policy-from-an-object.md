---
title: Avaliar uma política do gerenciamento baseado em políticas de um objeto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: b9e9d646-4894-4dee-a02a-0c71a8dc020e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f0de02092c87a727b723a5940805f34a75052e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575777"
---
# <a name="evaluate-a-policy-based-management-policy-from-an-object"></a><span data-ttu-id="f1a12-102">Avaliar uma política do Gerenciamento Baseado em Políticas de um objeto</span><span class="sxs-lookup"><span data-stu-id="f1a12-102">Evaluate a Policy-Based Management Policy from an Object</span></span>
  <span data-ttu-id="f1a12-103">Este tópico descreve como avaliar uma política de uma instância de servidor, banco de dados ou objeto de banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1a12-103">This topic describes how to evaluate a policy from a server instance, database, or database object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f1a12-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="f1a12-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f1a12-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="f1a12-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f1a12-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="f1a12-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f1a12-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="f1a12-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f1a12-108">**Para avaliar uma política em um objeto, usando:**</span><span class="sxs-lookup"><span data-stu-id="f1a12-108">**To evaluate a policy from an object, using:**</span></span>  
  
     [<span data-ttu-id="f1a12-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1a12-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f1a12-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f1a12-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f1a12-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="f1a12-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f1a12-112">O modo de execução é definido como parte da política e não pode ser alterado na caixa de diálogo **Avaliar Políticas** .</span><span class="sxs-lookup"><span data-stu-id="f1a12-112">The execution mode is defined as part of the policy and cannot be changed in the **Evaluate Policies** dialog box.</span></span>  
  
-   <span data-ttu-id="f1a12-113">A caixa de diálogo **Avaliar Políticas** só mostra políticas apropriadas para o objeto de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f1a12-113">The **Evaluate Policies** dialog box only shows policies appropriate for the database object.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f1a12-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="f1a12-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f1a12-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="f1a12-115">Permissions</span></span>  
 <span data-ttu-id="f1a12-116">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="f1a12-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f1a12-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1a12-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-from-an-object"></a><span data-ttu-id="f1a12-118">Para avaliar uma política em um objeto</span><span class="sxs-lookup"><span data-stu-id="f1a12-118">To evaluate a policy from an object</span></span>  
  
1.  <span data-ttu-id="f1a12-119">No Pesquisador de Objetos, clique com o botão direito do mouse em uma instância de servidor, um banco de dados ou um objeto de banco de dados, aponte para **Políticas**e selecione **Avaliar**.</span><span class="sxs-lookup"><span data-stu-id="f1a12-119">In Object Explorer, right-click a server instance, a database, or a database object, point to **Policies**, and select **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="f1a12-120">Na caixa de diálogo **Avaliar Políticas** , selecione uma ou mais políticas e clique em **Avaliar** para executar a política no modo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="f1a12-120">In the **Evaluate Policies** dialog box, select one or more policies and click **Evaluate** to run the policy in evaluation mode.</span></span> <span data-ttu-id="f1a12-121">Isso gera um relatório de conformidade para o conjunto de destino, mas não reconfigura o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nem impõe conformidade no futuro.</span><span class="sxs-lookup"><span data-stu-id="f1a12-121">This generates a compliance report for the target set but does not reconfigure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or enforce future compliance.</span></span> <span data-ttu-id="f1a12-122">Para destinos que não seguem as políticas selecionadas e têm propriedades que podem ser reconfiguradas pelo Gerenciamento de Política, é possível impor a conformidade com a política clicando em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f1a12-122">For targets that do not comply with the selected policies and have properties that can be reconfigured by Policy-Based Management, you can enforce policy compliance by clicking **Apply**.</span></span> <span data-ttu-id="f1a12-123">Para obter mais informações sobre as opções disponíveis contidas na caixa de diálogo **Avaliar Políticas** , consulte [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md)e [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md)e [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="f1a12-123">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md), [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md), and [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="f1a12-124">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="f1a12-124">When finished, click **Close**.</span></span>  
  
  
