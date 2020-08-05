---
title: 'Tutorial: administrando servidores com o gerenciamento baseado em políticas | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: 7de96e7b-9fb8-4cc8-8d85-61345d68a1e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b707a5ecd362c6b3b54e853f89d79e25a9e1428
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571998"
---
# <a name="tutorial-administering-servers-by-using-policy-based-management"></a><span data-ttu-id="b2e35-102">Tutorial: administração de servidores com Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="b2e35-102">Tutorial: Administering Servers by Using Policy-Based Management</span></span>
  <span data-ttu-id="b2e35-103">Bem-vindo ao tutorial Administrando servidores com o uso do Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="b2e35-103">Welcome to the Administering Servers by Using Policy-Based Management Policies tutorial.</span></span> <span data-ttu-id="b2e35-104">Este tutorial é dirigido a usuários que estão familiarizado com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mas ainda não conhecem o Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="b2e35-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but new to the Policy-Based Management.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="b2e35-105">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="b2e35-105">What You Will Learn</span></span>  
 <span data-ttu-id="b2e35-106">Este tutorial cria uma política para administrar seu servidor e outra que se aplica a um único banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b2e35-106">This tutorial creates a policy to administer your server and a policy that applies to a single database.</span></span> <span data-ttu-id="b2e35-107">Uma política é executada sob demanda para testar a conformidade.</span><span class="sxs-lookup"><span data-stu-id="b2e35-107">One policy is run on demand to test for compliance.</span></span> <span data-ttu-id="b2e35-108">A outra política aplica conformidade futura.</span><span class="sxs-lookup"><span data-stu-id="b2e35-108">The other policy enforces future compliance.</span></span>  
  
 <span data-ttu-id="b2e35-109">Este tutorial é dividido em duas lições:</span><span class="sxs-lookup"><span data-stu-id="b2e35-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="b2e35-110">Lição 1: Criar e aplicar uma política desativada por padrão</span><span class="sxs-lookup"><span data-stu-id="b2e35-110">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
 <span data-ttu-id="b2e35-111">Esta lição cria uma política que especifica que o Database Mail não está habilitado no servidor.</span><span class="sxs-lookup"><span data-stu-id="b2e35-111">This lesson creates a policy that specifies that Database Mail is not enabled on the server.</span></span> <span data-ttu-id="b2e35-112">Em seguida, ela verifica se o servidor está em conformidade com a política e configura o servidor desabilitando o Database Mail.</span><span class="sxs-lookup"><span data-stu-id="b2e35-112">Then, it checks to see whether your server complies with the policy, and configures the server by disabling Database Mail.</span></span>  
  
 [<span data-ttu-id="b2e35-113">Lição 2: Criar e aplicar uma política de nomeação de padrões</span><span class="sxs-lookup"><span data-stu-id="b2e35-113">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
 <span data-ttu-id="b2e35-114">Esta lição cria uma política que define e aplica uma nomeação padrão para tabelas.</span><span class="sxs-lookup"><span data-stu-id="b2e35-114">This lesson creates a policy that defines and enforces a naming standard for tables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2e35-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2e35-115">Requirements</span></span>  
 <span data-ttu-id="b2e35-116">Esta lição requer conhecimento básico em banco de dados e uma compreensão básica do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2e35-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="b2e35-117">Para usar este tutorial, o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] deve estar instalado no seu sistema:</span><span class="sxs-lookup"><span data-stu-id="b2e35-117">To use this tutorial, your system must have [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="b2e35-118">Inicie o tutorial</span><span class="sxs-lookup"><span data-stu-id="b2e35-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="b2e35-119">Lição 1: Criar e aplicar uma política desativada por padrão</span><span class="sxs-lookup"><span data-stu-id="b2e35-119">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="b2e35-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b2e35-120">See Also</span></span>  
 [<span data-ttu-id="b2e35-121">Administrar servidores com Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="b2e35-121">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
