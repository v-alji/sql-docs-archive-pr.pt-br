---
title: Serviço desconhecido (guia fazer logon) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e9b35cb5-d8ae-42ea-b59e-deedc99c4823
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0bda49cd95475d4f922f41ebe1701a814c3f60fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570421"
---
# <a name="unknown-service-log-on-tab"></a><span data-ttu-id="52491-102">Serviço desconhecido (guia Fazer Logon)</span><span class="sxs-lookup"><span data-stu-id="52491-102">Unknown Service (Log On Tab)</span></span>
  <span data-ttu-id="52491-103">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager não pode identificar este serviço.</span><span class="sxs-lookup"><span data-stu-id="52491-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is unable to identify this service.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="52491-104">Configuration Manager recebe informações de serviço do provedor WMI no computador que está executando o serviço.</span><span class="sxs-lookup"><span data-stu-id="52491-104">Configuration Manager receives service information from the WMI provider on the computer running the service.</span></span> <span data-ttu-id="52491-105">Ocorreu um erro ao ler as propriedades do serviço ou essas propriedades não estão completas.</span><span class="sxs-lookup"><span data-stu-id="52491-105">Either there was an error while reading the service properties, or the service properties are not complete.</span></span> <span data-ttu-id="52491-106">Para resolver o problema, tente fechar e reabrir o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager ou verifique o provedor WMI no computador que está executando o serviço.</span><span class="sxs-lookup"><span data-stu-id="52491-106">To resolve the problem, try closing and reopening [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or check the WMI provider on the computer running the service.</span></span>  
  
 <span data-ttu-id="52491-107">O provedor WMI é um componente do Windows.</span><span class="sxs-lookup"><span data-stu-id="52491-107">The WMI provider is a Windows component.</span></span> <span data-ttu-id="52491-108">Para obter informações sobre como verificar as permissões no provedor WMI, consulte "Como configurar o WMI para que mostre o status do servidor nas ferramentas do SQL Server" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="52491-108">For information on how to check permissions on the WMI provider, see "How to: Configure WMI to Show Server Status in SQL Server Tools" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="52491-109">Se você achar que está exibindo o serviço correto, use a guia **Fazer Logon** da caixa de diálogo **Propriedades de Serviço Desconhecido** para especificar a conta usada por esse serviço e para iniciar e parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="52491-109">If you believe you are viewing the correct service, use the **Log On** tab of the **Unknown Service Properties** dialog box to specify the account used by this service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="52491-110">Opções</span><span class="sxs-lookup"><span data-stu-id="52491-110">Options</span></span>  
 <span data-ttu-id="52491-111">**Conta Sistema Local**</span><span class="sxs-lookup"><span data-stu-id="52491-111">**Local System account**</span></span>  
 <span data-ttu-id="52491-112">Especifique uma conta Sistema Local que não requeira uma senha.</span><span class="sxs-lookup"><span data-stu-id="52491-112">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="52491-113">No entanto, ela pode impedir a interação do serviço com outros servidores, dependendo dos privilégios concedidos a ela.</span><span class="sxs-lookup"><span data-stu-id="52491-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="52491-114">**Esta conta**</span><span class="sxs-lookup"><span data-stu-id="52491-114">**This account**</span></span>  
 <span data-ttu-id="52491-115">Especifique um local ou conta de usuário do domínio que utilize Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="52491-115">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="52491-116">É recomendável usar uma conta de usuário do domínio com direitos mínimos para serviços.</span><span class="sxs-lookup"><span data-stu-id="52491-116">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="52491-117">Para obter informações sobre como selecionar uma conta, consulte "Configurando as contas de serviço do Windows" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="52491-117">For information about selecting an account, "Setting Up Windows Service Accounts" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="52491-118">**Nome da Conta**</span><span class="sxs-lookup"><span data-stu-id="52491-118">**Account Name**</span></span>  
 <span data-ttu-id="52491-119">Especifique o nome da conta local ou de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="52491-119">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="52491-120">**Senha**</span><span class="sxs-lookup"><span data-stu-id="52491-120">**Password**</span></span>  
 <span data-ttu-id="52491-121">Digite a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="52491-121">Type the password of the account.</span></span>  
  
 <span data-ttu-id="52491-122">**Confirmar senha**</span><span class="sxs-lookup"><span data-stu-id="52491-122">**Confirm password**</span></span>  
 <span data-ttu-id="52491-123">Digite a senha da conta novamente.</span><span class="sxs-lookup"><span data-stu-id="52491-123">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="52491-124">**Iniciar**</span><span class="sxs-lookup"><span data-stu-id="52491-124">**Start**</span></span>  
 <span data-ttu-id="52491-125">Inicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="52491-125">Start the service.</span></span>  
  
 <span data-ttu-id="52491-126">**Parar**</span><span class="sxs-lookup"><span data-stu-id="52491-126">**Stop**</span></span>  
 <span data-ttu-id="52491-127">Parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="52491-127">Stop the service.</span></span>  
  
 <span data-ttu-id="52491-128">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="52491-128">**Pause**</span></span>  
 <span data-ttu-id="52491-129">Pausar o serviço.</span><span class="sxs-lookup"><span data-stu-id="52491-129">Pause the service.</span></span>  
  
 <span data-ttu-id="52491-130">**Retomar**</span><span class="sxs-lookup"><span data-stu-id="52491-130">**Resume**</span></span>  
 <span data-ttu-id="52491-131">Retomar um serviço pausado.</span><span class="sxs-lookup"><span data-stu-id="52491-131">Resume a paused service.</span></span>  
  
  
