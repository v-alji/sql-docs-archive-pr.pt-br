---
title: Avaliar uma política do gerenciamento baseado em políticas em um agendamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: bea09522-ff47-4037-ab55-a98ea7c10099
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f1c6b1a7d13d14c02f4b4e537c2dbdb2df39d02c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680373"
---
# <a name="evaluate-a-policy-based-management-policy-on-a-schedule"></a><span data-ttu-id="11882-102">Avaliar uma política do Gerenciamento Baseado em Políticas em um agendamento</span><span class="sxs-lookup"><span data-stu-id="11882-102">Evaluate a Policy-Based Management Policy on a Schedule</span></span>
  <span data-ttu-id="11882-103">Este tópico descreve como avaliar uma faceta do Gerenciamento Baseado em Políticas em um agendamento no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11882-103">This topic describes how to evaluate a Policy-Based Management policy on a schedule in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="11882-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="11882-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="11882-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="11882-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="11882-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="11882-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="11882-107">**Para avaliar uma política em um agendamento, usando:**</span><span class="sxs-lookup"><span data-stu-id="11882-107">**To evaluate a policy on a schedule, using:**</span></span>  
  
     [<span data-ttu-id="11882-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="11882-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="11882-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="11882-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="11882-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="11882-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="11882-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="11882-111">Permissions</span></span>  
 <span data-ttu-id="11882-112">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="11882-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="11882-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="11882-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-on-a-schedule"></a><span data-ttu-id="11882-114">Para avaliar uma política em um agendamento</span><span class="sxs-lookup"><span data-stu-id="11882-114">To evaluate a policy on a schedule</span></span>  
  
1.  <span data-ttu-id="11882-115">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o agendamento da política que você deseja avaliar.</span><span class="sxs-lookup"><span data-stu-id="11882-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy schedule that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="11882-116">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="11882-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="11882-117">Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.</span><span class="sxs-lookup"><span data-stu-id="11882-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="11882-118">Clique no sinal de adição para expandir a pasta **Políticas** .</span><span class="sxs-lookup"><span data-stu-id="11882-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="11882-119">Clique com o botão direito do mouse na política cujo agendamento você deseja avaliar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="11882-119">Right-click the policy whose schedule you what to evaluate and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="11882-120">Na caixa de diálogo **Abrir Política -** _nome_da_política_, na lista **Modo de Avaliação**, selecione **Ao agendar**.</span><span class="sxs-lookup"><span data-stu-id="11882-120">On the **Open Policy -**_policy_name_ dialog box, in the **Evaluation Mode** list, select **On schedule**.</span></span>  
  
7.  <span data-ttu-id="11882-121">Em **Agenda**, clique em **Escolher** para especificar uma agenda existente ou em **Novo** para criar uma agenda nova.</span><span class="sxs-lookup"><span data-stu-id="11882-121">Under **Schedule**, click either **Pick** to specify an existing schedule or **New** to create a new schedule.</span></span>  
  
8.  <span data-ttu-id="11882-122">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="11882-122">When finished, click **OK**.</span></span>  
  
  
