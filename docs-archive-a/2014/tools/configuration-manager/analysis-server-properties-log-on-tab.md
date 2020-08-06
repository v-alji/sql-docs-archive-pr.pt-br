---
title: Propriedades do Analysis Server (guia Logon) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: a82e0c98-efaa-4b0b-9582-3c879ee42444
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8db5576e48e7f12ef1733175875d2cd065e376fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685403"
---
# <a name="analysis-server-properties-log-on-tab"></a><span data-ttu-id="1c1b7-102">Propriedades do Analysis Server (guia Fazer Logon)</span><span class="sxs-lookup"><span data-stu-id="1c1b7-102">Analysis Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="1c1b7-103">Use a guia **Fazer Logon** da caixa de diálogo **Propriedades do Analysis Server** para especificar a conta usada pelo serviço [!INCLUDE[ssAS](../../includes/ssas-md.md)] e para iniciar e parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-103">Use the **Log On** tab of the **Analysis Server Properties** dialog box to specify the account used by the [!INCLUDE[ssAS](../../includes/ssas-md.md)] service, and to start and stop the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c1b7-104">Quando ocorrer alteração no **Nome da Conta** usado por um serviço em uma instância clusterizada, a nova conta deverá ser membro do grupo de domínio especificado durante a instalação para o serviço que está sendo alterado, ou você deverá ter permissão para adicionar membros a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-104">When changing the **Account Name** used by a service on a clustered instance, the new account must either be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="1c1b7-105">Se você não tiver permissão para modificar a associação de grupo, contate o administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-105">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1c1b7-106">Opções</span><span class="sxs-lookup"><span data-stu-id="1c1b7-106">Options</span></span>  
 <span data-ttu-id="1c1b7-107">**Conta Sistema Local**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-107">**Local System account**</span></span>  
 <span data-ttu-id="1c1b7-108">Especifique uma conta Sistema Local que não requeira uma senha.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-108">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="1c1b7-109">Porém, essa conta pode restringir a interação do serviço com outros servidores, dependendo dos privilégios concedidos a ela.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-109">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="1c1b7-110">**Esta conta**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-110">**This account**</span></span>  
 <span data-ttu-id="1c1b7-111">Especifique uma conta de usuário local ou de domínio que usa a Autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-111">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="1c1b7-112">recomenda usar uma conta de usuário do domínio com direitos mínimos para serviços.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-112">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="1c1b7-113">Para obter informações sobre como selecionar uma conta, pesquise o tópico "Configurando as contas de serviço do Windows" nos Manuais Online.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-113">For information about selecting an account, search Books Online for the topic Setting Up Windows Service Accounts.</span></span>  
  
 <span data-ttu-id="1c1b7-114">**Nome da Conta**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-114">**Account Name**</span></span>  
 <span data-ttu-id="1c1b7-115">Especifique o nome da conta local ou de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-115">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="1c1b7-116">**Senha**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-116">**Password**</span></span>  
 <span data-ttu-id="1c1b7-117">Digite a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-117">Type the password of the account.</span></span>  
  
 <span data-ttu-id="1c1b7-118">**Confirmar senha**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-118">**Confirm password**</span></span>  
 <span data-ttu-id="1c1b7-119">Digite a senha da conta novamente.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-119">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="1c1b7-120">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-120">**Start**</span></span>  
 <span data-ttu-id="1c1b7-121">Inicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-121">Start the service.</span></span>  
  
 <span data-ttu-id="1c1b7-122">**Parar**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-122">**Stop**</span></span>  
 <span data-ttu-id="1c1b7-123">Parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-123">Stop the service.</span></span>  
  
 <span data-ttu-id="1c1b7-124">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-124">**Pause**</span></span>  
 <span data-ttu-id="1c1b7-125">Pausar o serviço.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-125">Pause the service.</span></span>  
  
 <span data-ttu-id="1c1b7-126">**Retomar**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-126">**Resume**</span></span>  
 <span data-ttu-id="1c1b7-127">Retomar um serviço pausado.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-127">Resume a paused service.</span></span>  
  
  
