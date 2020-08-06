---
title: Avaliar uma política do gerenciamento baseado em políticas dessa política | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: 0b3214bd-d0ab-45ab-9281-3d95507abe54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 207c86f1465c49238fc9b50ee75489b43d956caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575779"
---
# <a name="evaluate-a-policy-based-management-policy-from-that-policy"></a><span data-ttu-id="541a7-102">Avaliar uma política do Gerenciamento Baseado em Políticas dessa política</span><span class="sxs-lookup"><span data-stu-id="541a7-102">Evaluate a Policy-Based Management Policy from That Policy</span></span>
  <span data-ttu-id="541a7-103">Este tópico descreve como avaliar uma política usando essa política no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="541a7-103">This topic describes how to evaluate a policy using that policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="541a7-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="541a7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="541a7-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="541a7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="541a7-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="541a7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="541a7-107">**Para avaliar uma política, usando:**</span><span class="sxs-lookup"><span data-stu-id="541a7-107">**To evaluate a policy, using:**</span></span>  
  
     [<span data-ttu-id="541a7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="541a7-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="541a7-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="541a7-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="541a7-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="541a7-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="541a7-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="541a7-111">Permissions</span></span>  
 <span data-ttu-id="541a7-112">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="541a7-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="541a7-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="541a7-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy"></a><span data-ttu-id="541a7-114">Para avaliar uma política</span><span class="sxs-lookup"><span data-stu-id="541a7-114">To evaluate a policy</span></span>  
  
1.  <span data-ttu-id="541a7-115">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém a política que você deseja avaliar.</span><span class="sxs-lookup"><span data-stu-id="541a7-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="541a7-116">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="541a7-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="541a7-117">Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.</span><span class="sxs-lookup"><span data-stu-id="541a7-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="541a7-118">Clique no sinal de adição para expandir a pasta **Políticas** .</span><span class="sxs-lookup"><span data-stu-id="541a7-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="541a7-119">Clique com o botão direito do mouse na política a ser avaliada e selecione **Avaliar**.</span><span class="sxs-lookup"><span data-stu-id="541a7-119">Right-click the policy that you want to evaluate and select **Evaluate**.</span></span>  
  
6.  <span data-ttu-id="541a7-120">Na caixa de diálogo **Avaliar Resultados**  , você pode ver os resultados da avaliação de política.</span><span class="sxs-lookup"><span data-stu-id="541a7-120">In the **Evaluate Results**  dialog box, you see the results of the policy evaluation.</span></span> <span data-ttu-id="541a7-121">Para destinos que não obedecem à política e têm propriedades que podem ser reconfiguradas pelo Gerenciamento de Política, é possível impor a conformidade com a política clicando em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="541a7-121">For targets that do not comply with the policy and have properties that can be reconfigured by Policy-Based Management, you can enforce compliance by clicking **Apply**.</span></span> <span data-ttu-id="541a7-122">Para obter mais informações sobre as opções disponíveis contidas na caixa de diálogo **Avaliar Políticas** , consulte [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) e [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span><span class="sxs-lookup"><span data-stu-id="541a7-122">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) and [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span></span>  
  
7.  <span data-ttu-id="541a7-123">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="541a7-123">When finished, click **Close**.</span></span>  
  
  
