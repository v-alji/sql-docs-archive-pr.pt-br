---
title: Propriedades do SQL Server Agent (guia Fazer Logon) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 01fc6329-5d6b-4186-9565-395f375477bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd899e8824adacd07fa1d8d7d51b2143d10cadd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573338"
---
# <a name="sql-server-agent-properties-log-on-tab"></a><span data-ttu-id="3cb59-102">Propriedades do SQL Server Agent (guia Fazer Logon)</span><span class="sxs-lookup"><span data-stu-id="3cb59-102">SQL Server Agent Properties (Log On Tab)</span></span>
  <span data-ttu-id="3cb59-103">Use a guia **Fazer Logon** da caixa de diálogo **Propriedades do SQL Server Agent** para especificar a conta usada pelo serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e para iniciar e parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="3cb59-103">Use the **Log On** tab of the **SQL Server Agent Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and to start and stop the service.</span></span> <span data-ttu-id="3cb59-104">A alteração da senha de uma conta entra em vigor imediatamente sem a reinicialização do serviço.</span><span class="sxs-lookup"><span data-stu-id="3cb59-104">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3cb59-105">Quando ocorrer alteração no nome de conta usado por um serviço em uma instância clusterizada, a nova conta deverá ser membro do grupo de domínio especificado, durante a instalação, para o serviço que está sendo alterado, ou você deverá ter permissão para adicionar membros a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="3cb59-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="3cb59-106">Se você não tiver permissão para modificar a associação de grupo, contate o administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="3cb59-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3cb59-107">Opções</span><span class="sxs-lookup"><span data-stu-id="3cb59-107">Options</span></span>  
 <span data-ttu-id="3cb59-108">**Conta Sistema Local**</span><span class="sxs-lookup"><span data-stu-id="3cb59-108">**Local System account**</span></span>  
 <span data-ttu-id="3cb59-109">Especifique uma conta Sistema Local que não requeira uma senha.</span><span class="sxs-lookup"><span data-stu-id="3cb59-109">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="3cb59-110">Porém, essa conta pode restringir a interação do serviço com outros servidores, dependendo dos privilégios concedidos a ela.</span><span class="sxs-lookup"><span data-stu-id="3cb59-110">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="3cb59-111">**Esta conta**</span><span class="sxs-lookup"><span data-stu-id="3cb59-111">**This account**</span></span>  
 <span data-ttu-id="3cb59-112">Especifique um local ou conta de usuário do domínio que utilize Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="3cb59-112">Specify a local or domain user account that uses Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="3cb59-113">recomenda usar uma conta de usuário do domínio com direitos mínimos para serviços.</span><span class="sxs-lookup"><span data-stu-id="3cb59-113">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="3cb59-114">Para obter informações sobre como selecionar uma conta, pesquise "Configurando as contas de serviço do Windows" nos Manuais Online.</span><span class="sxs-lookup"><span data-stu-id="3cb59-114">For information about selecting an account, search Books Online for "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="3cb59-115">**Nome da Conta**</span><span class="sxs-lookup"><span data-stu-id="3cb59-115">**Account Name**</span></span>  
 <span data-ttu-id="3cb59-116">Especifique o nome da conta local ou de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="3cb59-116">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="3cb59-117">**Senha**</span><span class="sxs-lookup"><span data-stu-id="3cb59-117">**Password**</span></span>  
 <span data-ttu-id="3cb59-118">Digite a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="3cb59-118">Type the password of the account.</span></span>  
  
 <span data-ttu-id="3cb59-119">**Confirmar senha**</span><span class="sxs-lookup"><span data-stu-id="3cb59-119">**Confirm password**</span></span>  
 <span data-ttu-id="3cb59-120">Digite a senha da conta novamente.</span><span class="sxs-lookup"><span data-stu-id="3cb59-120">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="3cb59-121">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="3cb59-121">**Start**</span></span>  
 <span data-ttu-id="3cb59-122">Inicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="3cb59-122">Start the service.</span></span>  
  
 <span data-ttu-id="3cb59-123">**Parar**</span><span class="sxs-lookup"><span data-stu-id="3cb59-123">**Stop**</span></span>  
 <span data-ttu-id="3cb59-124">Parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="3cb59-124">Stop the service.</span></span>  
  
 <span data-ttu-id="3cb59-125">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="3cb59-125">**Pause**</span></span>  
 <span data-ttu-id="3cb59-126">Pausar o serviço.</span><span class="sxs-lookup"><span data-stu-id="3cb59-126">Pause the service.</span></span>  
  
 <span data-ttu-id="3cb59-127">**Retomar**</span><span class="sxs-lookup"><span data-stu-id="3cb59-127">**Resume**</span></span>  
 <span data-ttu-id="3cb59-128">Retomar um serviço pausado.</span><span class="sxs-lookup"><span data-stu-id="3cb59-128">Resume a paused service.</span></span>  
  
  
