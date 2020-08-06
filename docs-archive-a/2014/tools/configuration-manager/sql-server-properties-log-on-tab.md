---
title: Propriedades do SQL Server (guia Logon) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 405073fc-eaa3-43c6-bf82-2cd58cacc1c3
author: stevestein
ms.author: sstein
ms.openlocfilehash: adec9ed7c69023218baa96ab8f8edbb6f2b365bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574413"
---
# <a name="sql-server-properties-log-on-tab"></a><span data-ttu-id="4f05c-102">Propriedades do SQL Server (guia Fazer Logon)</span><span class="sxs-lookup"><span data-stu-id="4f05c-102">SQL Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="4f05c-103">Use a guia **Fazer Logon** da caixa de diálogo **Propriedades do SQL Server** para especificar a conta usada pelo serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , para alterar a senha de uma conta e para iniciar e parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="4f05c-103">Use the **Log On** tab of the **SQL Server Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="4f05c-104">A alteração da senha de uma conta entra em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="4f05c-104">Changing the password of an account takes effect immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f05c-105">Quando ocorrer alteração no nome de conta usado por um serviço em uma instância clusterizada, a nova conta deverá ser membro do grupo de domínio especificado, durante a instalação, para o serviço que está sendo alterado, ou você deverá ter permissão para adicionar membros a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="4f05c-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="4f05c-106">Se você não tiver permissão para modificar a associação de grupo, contate o administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="4f05c-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="4f05c-107">Para obter mais informações sobre como selecionar uma conta para executar o serviço, consulte "Configurando as contas de serviço do Windows" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f05c-107">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4f05c-108">Opções</span><span class="sxs-lookup"><span data-stu-id="4f05c-108">Options</span></span>  
 <span data-ttu-id="4f05c-109">**Conta interna**</span><span class="sxs-lookup"><span data-stu-id="4f05c-109">**Built-in account**</span></span>  
 <span data-ttu-id="4f05c-110">**Sistema Local**</span><span class="sxs-lookup"><span data-stu-id="4f05c-110">**Local System**</span></span>  
 -   <span data-ttu-id="4f05c-111">Especifique a conta Sistema Local.</span><span class="sxs-lookup"><span data-stu-id="4f05c-111">Specify the local system account.</span></span> <span data-ttu-id="4f05c-112">Essa conta não requer uma senha.</span><span class="sxs-lookup"><span data-stu-id="4f05c-112">This account does not require a password.</span></span> <span data-ttu-id="4f05c-113">No entanto, ela pode impedir a interação do serviço com outros servidores, dependendo dos privilégios concedidos a ela.</span><span class="sxs-lookup"><span data-stu-id="4f05c-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="4f05c-114">**Serviço Local**</span><span class="sxs-lookup"><span data-stu-id="4f05c-114">**Local Service**</span></span>  
 -   <span data-ttu-id="4f05c-115">Especifique a conta de serviço local.</span><span class="sxs-lookup"><span data-stu-id="4f05c-115">Specify the local service account.</span></span> <span data-ttu-id="4f05c-116">Essa conta não requer uma senha.</span><span class="sxs-lookup"><span data-stu-id="4f05c-116">This account does not require a password.</span></span> <span data-ttu-id="4f05c-117">No entanto, ela pode impedir a interação do serviço com outros servidores, dependendo dos privilégios concedidos a ela.</span><span class="sxs-lookup"><span data-stu-id="4f05c-117">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="4f05c-118">**Serviço de Rede**</span><span class="sxs-lookup"><span data-stu-id="4f05c-118">**Network Service**</span></span>  
 -   <span data-ttu-id="4f05c-119">É recomendável não usar a conta do Serviço de Rede para os serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="4f05c-119">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="4f05c-120">As contas de Usuário Local ou Usuário de Domínio são mais apropriadas para esses serviços.</span><span class="sxs-lookup"><span data-stu-id="4f05c-120">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="4f05c-121">**Esta conta**</span><span class="sxs-lookup"><span data-stu-id="4f05c-121">**This account**</span></span>  
 <span data-ttu-id="4f05c-122">Especifique um local ou conta de usuário do domínio que utilize Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="4f05c-122">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="4f05c-123">É recomendável usar uma conta de usuário de domínio com direitos mínimos para serviços.</span><span class="sxs-lookup"><span data-stu-id="4f05c-123">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="4f05c-124">**Nome da Conta**</span><span class="sxs-lookup"><span data-stu-id="4f05c-124">**Account Name**</span></span>  
 <span data-ttu-id="4f05c-125">Especifique o nome da conta local ou de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="4f05c-125">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="4f05c-126">**Senha**</span><span class="sxs-lookup"><span data-stu-id="4f05c-126">**Password**</span></span>  
 <span data-ttu-id="4f05c-127">Digite a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="4f05c-127">Type the password of the account.</span></span>  
  
 <span data-ttu-id="4f05c-128">**Confirmar senha**</span><span class="sxs-lookup"><span data-stu-id="4f05c-128">**Confirm password**</span></span>  
 <span data-ttu-id="4f05c-129">Digite a senha da conta novamente.</span><span class="sxs-lookup"><span data-stu-id="4f05c-129">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="4f05c-130">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="4f05c-130">**Start**</span></span>  
 <span data-ttu-id="4f05c-131">Inicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="4f05c-131">Start the service.</span></span>  
  
 <span data-ttu-id="4f05c-132">**Parar**</span><span class="sxs-lookup"><span data-stu-id="4f05c-132">**Stop**</span></span>  
 <span data-ttu-id="4f05c-133">Parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="4f05c-133">Stop the service.</span></span>  
  
 <span data-ttu-id="4f05c-134">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="4f05c-134">**Pause**</span></span>  
 <span data-ttu-id="4f05c-135">Pausar o serviço.</span><span class="sxs-lookup"><span data-stu-id="4f05c-135">Pause the service.</span></span>  
  
 <span data-ttu-id="4f05c-136">**Retomar**</span><span class="sxs-lookup"><span data-stu-id="4f05c-136">**Resume**</span></span>  
 <span data-ttu-id="4f05c-137">Retomar um serviço pausado.</span><span class="sxs-lookup"><span data-stu-id="4f05c-137">Resume a paused service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4f05c-138">Por padrão, apenas membros do grupo de administradores local podem iniciar, interromper, pausar, retomar ou reiniciar um serviço.</span><span class="sxs-lookup"><span data-stu-id="4f05c-138">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="4f05c-139">Para conceder a capacidade de gerenciar serviços a não administradores, consulte [Como conceder aos usuários direitos para gerenciar serviços no Windows Server 2003](https://support.microsoft.com/kb/325349).</span><span class="sxs-lookup"><span data-stu-id="4f05c-139">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="4f05c-140">(O processo é semelhante em outras versões do Windows.)</span><span class="sxs-lookup"><span data-stu-id="4f05c-140">(The process is similar on other versions of Windows.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f05c-141">Ao iniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], um erro do WMI com a frase "not implemented [0x80004001]" pode indicar que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não está instalado no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="4f05c-141">When starting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a WMI error containing the phrase "not implemented [0x80004001]" may indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not installed on the target computer.</span></span>  
  
  
