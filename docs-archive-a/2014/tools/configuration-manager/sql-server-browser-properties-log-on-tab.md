---
title: Propriedades do SQL Server Browser (guia Logon) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c77871ec-c2f4-4e4a-9a10-5aeb4ae70507
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c1f7d0cfd9e9b05a2a04f3c3e9efba687522298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678465"
---
# <a name="sql-server-browser-properties-log-on-tab"></a><span data-ttu-id="3db80-102">Propriedades do Navegador do SQL Server (guia Fazer Logon)</span><span class="sxs-lookup"><span data-stu-id="3db80-102">SQL Server Browser Properties (Log On Tab)</span></span>
  <span data-ttu-id="3db80-103">O programa Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é executado como um serviço no servidor.</span><span class="sxs-lookup"><span data-stu-id="3db80-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> <span data-ttu-id="3db80-104">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser escuta as solicitações de entrada de recursos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e fornece informações sobre as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="3db80-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3db80-105">O Navegador escuta em uma porta UDP e aceita as solicitações não autenticadas usando o protocolo SSRP do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3db80-105">Browser listens on a UDP port and accepts unauthenticated requests using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resolution Protocol (SSRP).</span></span>  
  
 <span data-ttu-id="3db80-106">A alteração da senha de uma conta entra em vigor imediatamente sem a reinicialização do serviço.</span><span class="sxs-lookup"><span data-stu-id="3db80-106">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3db80-107">Opções</span><span class="sxs-lookup"><span data-stu-id="3db80-107">Options</span></span>  
 <span data-ttu-id="3db80-108">**Conta Sistema Local**</span><span class="sxs-lookup"><span data-stu-id="3db80-108">**Local System account**</span></span>  
 <span data-ttu-id="3db80-109">Execute o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no contexto de segurança da conta Sistema Local.</span><span class="sxs-lookup"><span data-stu-id="3db80-109">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service in the security context of the Local System account.</span></span> <span data-ttu-id="3db80-110">Quando possível, use uma conta de baixa permissão.</span><span class="sxs-lookup"><span data-stu-id="3db80-110">When possible, use a low-permission account instead.</span></span>  
  
 <span data-ttu-id="3db80-111">**Esta conta**</span><span class="sxs-lookup"><span data-stu-id="3db80-111">**This account**</span></span>  
 <span data-ttu-id="3db80-112">Especifique um local ou conta de usuário do domínio que utilize Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="3db80-112">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="3db80-113">É recomendável usar uma conta de usuário do domínio com direitos mínimos para serviços.</span><span class="sxs-lookup"><span data-stu-id="3db80-113">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="3db80-114">Para obter informações sobre como selecionar uma conta, consulte "Configurando as contas de serviço do Windows" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3db80-114">For information about selecting an account, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="3db80-115">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="3db80-115">**Browse**</span></span>  
 <span data-ttu-id="3db80-116">Procure um usuário ou uma entidade de segurança incorporada.</span><span class="sxs-lookup"><span data-stu-id="3db80-116">Browse for a user or built-in security principal.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3db80-117">Use uma conta da baixa-permissão.</span><span class="sxs-lookup"><span data-stu-id="3db80-117">Use a low-permission account.</span></span> <span data-ttu-id="3db80-118">Para obter informações sobre as permissões necessárias para o Serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte a seção Segurança do tópico [Serviço Navegador do SQL Server](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="3db80-118">For information about the permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service, see the Security section of [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="3db80-119">**Senha**</span><span class="sxs-lookup"><span data-stu-id="3db80-119">**Password**</span></span>  
 <span data-ttu-id="3db80-120">Digite a senha da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="3db80-120">Enter the password of the security principal.</span></span>  
  
 <span data-ttu-id="3db80-121">**Confirmar senha**</span><span class="sxs-lookup"><span data-stu-id="3db80-121">**Confirm password**</span></span>  
 <span data-ttu-id="3db80-122">Confirme a senha da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="3db80-122">Confirm the password of the security principal.</span></span>  
  
 <span data-ttu-id="3db80-123">**Status de serviço**</span><span class="sxs-lookup"><span data-stu-id="3db80-123">**Service status**</span></span>  
 <span data-ttu-id="3db80-124">Indica se este serviço está sendo executado, se está parado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="3db80-124">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="3db80-125">" **...** " indica que há uma alteração de estado pendente.</span><span class="sxs-lookup"><span data-stu-id="3db80-125">"**...**" indicates a state change is pending.</span></span>  
  
 <span data-ttu-id="3db80-126">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="3db80-126">**Start**</span></span>  
 <span data-ttu-id="3db80-127">Iniciar o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3db80-127">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="3db80-128">**Parar**</span><span class="sxs-lookup"><span data-stu-id="3db80-128">**Stop**</span></span>  
 <span data-ttu-id="3db80-129">Parar o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3db80-129">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="3db80-130">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="3db80-130">**Pause**</span></span>  
 <span data-ttu-id="3db80-131">Pausar o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3db80-131">Pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="3db80-132">**Retomar**</span><span class="sxs-lookup"><span data-stu-id="3db80-132">**Resume**</span></span>  
 <span data-ttu-id="3db80-133">Retomar um serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em pausa.</span><span class="sxs-lookup"><span data-stu-id="3db80-133">Resume a paused [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db80-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3db80-134">See Also</span></span>  
 [<span data-ttu-id="3db80-135">Serviço Navegador do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3db80-135">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
