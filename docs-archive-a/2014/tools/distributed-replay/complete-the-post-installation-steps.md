---
title: Concluir as etapas pós-instalação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 0a788a2a-9b4f-4bfc-b1b5-83eeb1ea9ab2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1e9aae3dccaa409bcebc473213286f3edf19e7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574960"
---
# <a name="complete-the-post-installation-steps"></a><span data-ttu-id="e94b1-102">Concluir as etapas de pós-instalação</span><span class="sxs-lookup"><span data-stu-id="e94b1-102">Complete the Post-Installation Steps</span></span>
  <span data-ttu-id="e94b1-103">Depois de instalar o Distributed Replay, modifique as contas de serviços cliente e controlador do Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="e94b1-103">After you install Distributed Replay you must modify the Distributed Replay controller and client services accounts.</span></span>  
  
### <a name="to-complete-the-post-installation-steps"></a><span data-ttu-id="e94b1-104">Para concluir as etapas de pós-instalação</span><span class="sxs-lookup"><span data-stu-id="e94b1-104">To complete the post-installation steps</span></span>  
  
1.  <span data-ttu-id="e94b1-105">**Criar regras de firewall**: no controlador e nos computadores cliente, você deve permitir tráfego de entrada pelo firewall para o serviço correspondente.</span><span class="sxs-lookup"><span data-stu-id="e94b1-105">**Create firewall rules**: On the controller and client computers, you must allow inbound traffic through the firewall for the corresponding service.</span></span> <span data-ttu-id="e94b1-106">Especifique as regras de firewall para os executáveis de serviço, localizados nas pastas de instalação.</span><span class="sxs-lookup"><span data-stu-id="e94b1-106">Specify the firewall rules for the service executables, located in the installation folders.</span></span>  
  
    1.  <span data-ttu-id="e94b1-107">Para o serviço de controlador, crie uma regra para **DReplayController.exe**, localizado na pasta de instalação.</span><span class="sxs-lookup"><span data-stu-id="e94b1-107">For the controller service, create a rule for **DReplayController.exe**, located in the installation folder.</span></span> <span data-ttu-id="e94b1-108">Por exemplo, o comando a seguir habilita essa regra, onde `%InstallPath%` é a pasta de instalação do serviço:</span><span class="sxs-lookup"><span data-stu-id="e94b1-108">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay controller" dir=in program="%InstallPath%\DReplayController\DReplayController.exe" action=allow`  
  
    2.  <span data-ttu-id="e94b1-109">Para o serviço de cliente, em cada computador cliente, crie uma regra para **DReplayClient.exe**, localizado na pasta de instalação.</span><span class="sxs-lookup"><span data-stu-id="e94b1-109">For the client service, on each client computer, create a rule for **DReplayClient.exe**, located in the installation folder.</span></span> <span data-ttu-id="e94b1-110">Por exemplo, o comando a seguir habilita essa regra, onde `%InstallPath%` é a pasta de instalação do serviço:</span><span class="sxs-lookup"><span data-stu-id="e94b1-110">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay client" dir=in program="%InstallPath%\DReplayClient\DReplayClient.exe" action=allow`  
  
2.  <span data-ttu-id="e94b1-111">**Conceder permissões a cada cliente no servidor alvo**: depois de concluir a instalação do serviço de cliente nos computadores cliente, adicione manualmente as contas de serviço de cliente à função sysadmin na instância alvo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e94b1-111">**Grant each client permissions on the target server**: After you have completed installing the client service on the client computers, you must manually add the client service accounts to the sysadmin role on the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e94b1-112">Segurança do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e94b1-112">.NET Framework Security</span></span>  
 <span data-ttu-id="e94b1-113">Você deve ter permissões administrativas para instalar qualquer recurso do Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="e94b1-113">You must have administrative permissions in order to install any of the Distributed Replay features.</span></span> <span data-ttu-id="e94b1-114">Apenas um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que tenha permissões sysadmin pode adicionar as contas de serviço de cliente à função de servidor sysadmin do servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="e94b1-114">Only a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login having sysadmin permissions can add the client service accounts to the sysadmin server role of the test server.</span></span> <span data-ttu-id="e94b1-115">Para obter mais informações sobre as considerações de segurança do Distributed Replay, veja [Segurança do Distributed Replay](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="e94b1-115">For more information about Distributed Replay security considerations, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
  
