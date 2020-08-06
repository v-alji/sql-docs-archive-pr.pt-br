---
title: Iniciador do Daemon de Filtro de Texto Completo do SQL (guia Logon) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 13e260f9-a75f-430b-88a3-959ddcead8fe
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb3f23907e96214929617bf2923e46148c0ab1f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582710"
---
# <a name="sql-full-text-filter-daemon-launcher-log-on-tab"></a><span data-ttu-id="3061f-102">Iniciador do Daemon de Filtro de Texto Completo do SQL (guia Fazer Logon)</span><span class="sxs-lookup"><span data-stu-id="3061f-102">SQL Full-text Filter Daemon Launcher (Log On Tab)</span></span>
  <span data-ttu-id="3061f-103">A partir do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], o serviço do Iniciador do Daemon de Filtro de Texto Completo do SQL (Iniciador FDHOST) é usado pela pesquisa de texto completo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3061f-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text search.</span></span> <span data-ttu-id="3061f-104">Este serviço deverá estar em execução se você usar a pesquisa de texto completo.</span><span class="sxs-lookup"><span data-stu-id="3061f-104">This service must be running if you use full-text search.</span></span> <span data-ttu-id="3061f-105">Para obter informações sobre os processos do host do daemon de filtro, consulte "Arquitetura da pesquisa de texto completo" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3061f-105">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="3061f-106">Use a guia **Fazer Logon** da caixa de diálogo **Propriedades do Iniciador do Daemon de Filtro de Texto Completo do SQL** para especificar a conta usada pelo serviço de texto completo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , para alterar a senha de uma conta e para iniciar e parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="3061f-106">Use the **Log On** tab of the **SQL Full-text Filter Daemon Launcher  Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="3061f-107">A alteração da senha de uma conta entra em vigor após o reinício do serviço.</span><span class="sxs-lookup"><span data-stu-id="3061f-107">Changing the password of an account takes affect after restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3061f-108">Ao alterar o nome da conta usado por um serviço em uma instância clusterizada, a nova conta deverá ser membro do grupo de domínio especificado durante a instalação do serviço ou você deverá ter permissão para adicionar membros a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="3061f-108">When changing the account name used by a service on a clustered instance, either the new account must be a member of the domain group specified during setup for the service, or you must have permission to add members to that group.</span></span> <span data-ttu-id="3061f-109">Se você não tiver permissão para modificar a associação de grupo, contate o administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="3061f-109">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="3061f-110">Para obter mais informações sobre como selecionar uma conta para executar o serviço, consulte "Configurando as contas de serviço do Windows" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3061f-110">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3061f-111">Opções</span><span class="sxs-lookup"><span data-stu-id="3061f-111">Options</span></span>  
 <span data-ttu-id="3061f-112">**Conta interna**</span><span class="sxs-lookup"><span data-stu-id="3061f-112">**Built-in account**</span></span>  
 <span data-ttu-id="3061f-113">**Sistema Local**</span><span class="sxs-lookup"><span data-stu-id="3061f-113">**Local System**</span></span>  
 <span data-ttu-id="3061f-114">Especifique a conta Sistema Local.</span><span class="sxs-lookup"><span data-stu-id="3061f-114">Specify the local system account.</span></span> <span data-ttu-id="3061f-115">Essa conta não requer uma senha.</span><span class="sxs-lookup"><span data-stu-id="3061f-115">This account does not require a password.</span></span> <span data-ttu-id="3061f-116">No entanto, ela pode impedir a interação do serviço com outros servidores, dependendo dos privilégios concedidos a ela.</span><span class="sxs-lookup"><span data-stu-id="3061f-116">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="3061f-117">**Serviço Local**</span><span class="sxs-lookup"><span data-stu-id="3061f-117">**Local Service**</span></span>  
 <span data-ttu-id="3061f-118">Especifique a conta de serviço local.</span><span class="sxs-lookup"><span data-stu-id="3061f-118">Specify the local service account.</span></span> <span data-ttu-id="3061f-119">Essa conta não requer uma senha.</span><span class="sxs-lookup"><span data-stu-id="3061f-119">This account does not require a password.</span></span> <span data-ttu-id="3061f-120">No entanto, ela pode impedir a interação do serviço com outros servidores, dependendo dos privilégios concedidos a ela.</span><span class="sxs-lookup"><span data-stu-id="3061f-120">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="3061f-121">**Serviço de Rede**</span><span class="sxs-lookup"><span data-stu-id="3061f-121">**Network Service**</span></span>  
 <span data-ttu-id="3061f-122">É recomendável não usar a conta do Serviço de Rede para os serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="3061f-122">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="3061f-123">As contas de Usuário Local ou Usuário de Domínio são mais apropriadas para esses serviços.</span><span class="sxs-lookup"><span data-stu-id="3061f-123">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="3061f-124">**Esta conta**</span><span class="sxs-lookup"><span data-stu-id="3061f-124">**This account**</span></span>  
 <span data-ttu-id="3061f-125">Especifique um local ou conta de usuário do domínio que utilize Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="3061f-125">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="3061f-126">É recomendável usar uma conta de usuário de domínio com direitos mínimos para serviços.</span><span class="sxs-lookup"><span data-stu-id="3061f-126">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="3061f-127">**Nome da Conta**</span><span class="sxs-lookup"><span data-stu-id="3061f-127">**Account Name**</span></span>  
 <span data-ttu-id="3061f-128">Especifique o nome da conta local ou de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="3061f-128">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="3061f-129">**Senha**</span><span class="sxs-lookup"><span data-stu-id="3061f-129">**Password**</span></span>  
 <span data-ttu-id="3061f-130">Digite a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="3061f-130">Type the password of the account.</span></span>  
  
 <span data-ttu-id="3061f-131">**Confirmar senha**</span><span class="sxs-lookup"><span data-stu-id="3061f-131">**Confirm password**</span></span>  
 <span data-ttu-id="3061f-132">Digite a senha da conta novamente.</span><span class="sxs-lookup"><span data-stu-id="3061f-132">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="3061f-133">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="3061f-133">**Start**</span></span>  
 <span data-ttu-id="3061f-134">Inicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="3061f-134">Start the service.</span></span>  
  
 <span data-ttu-id="3061f-135">**Parar**</span><span class="sxs-lookup"><span data-stu-id="3061f-135">**Stop**</span></span>  
 <span data-ttu-id="3061f-136">Parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="3061f-136">Stop the service.</span></span>  
  
 <span data-ttu-id="3061f-137">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="3061f-137">**Pause**</span></span>  
 <span data-ttu-id="3061f-138">Pausar o serviço.</span><span class="sxs-lookup"><span data-stu-id="3061f-138">Pause the service.</span></span> <span data-ttu-id="3061f-139">Não disponível para este serviço.</span><span class="sxs-lookup"><span data-stu-id="3061f-139">Not available for this service.</span></span>  
  
 <span data-ttu-id="3061f-140">**Retomar**</span><span class="sxs-lookup"><span data-stu-id="3061f-140">**Resume**</span></span>  
 <span data-ttu-id="3061f-141">Retomar um serviço pausado.</span><span class="sxs-lookup"><span data-stu-id="3061f-141">Resume a paused service.</span></span>  
  
  
