---
title: Erro de WMI 0x8007052f | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- 0x8007052f (WMI error)
ms.assetid: a33f12bd-15c4-42a8-b343-de44c3e87729
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d6e857e0ccaad9b6f34bbdc9b88aea2e6d7291d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686204"
---
# <a name="wmi-error-0x8007052f"></a><span data-ttu-id="81f9b-102">Erro de WMI 0x8007052f</span><span class="sxs-lookup"><span data-stu-id="81f9b-102">WMI Error 0x8007052f</span></span>
    
## <a name="details"></a><span data-ttu-id="81f9b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="81f9b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81f9b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="81f9b-104">Product Name</span></span>|<span data-ttu-id="81f9b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="81f9b-105">SQL Server</span></span>|  
|<span data-ttu-id="81f9b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="81f9b-106">Event ID</span></span>|<span data-ttu-id="81f9b-107">0x8007052f</span><span class="sxs-lookup"><span data-stu-id="81f9b-107">0x8007052f</span></span>|  
|<span data-ttu-id="81f9b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="81f9b-108">Event Source</span></span>|<span data-ttu-id="81f9b-109">Erro do Provedor WMI</span><span class="sxs-lookup"><span data-stu-id="81f9b-109">WMI Provider Error</span></span>|  
|<span data-ttu-id="81f9b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="81f9b-110">Component</span></span>|<span data-ttu-id="81f9b-111">SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="81f9b-111">SQL Server Configuration Manager</span></span>|  
|<span data-ttu-id="81f9b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="81f9b-112">Symbolic Name</span></span>|<span data-ttu-id="81f9b-113">NA</span><span class="sxs-lookup"><span data-stu-id="81f9b-113">NA</span></span>|  
|<span data-ttu-id="81f9b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="81f9b-114">Message Text</span></span>|<span data-ttu-id="81f9b-115">Falha de logon: restrição na conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="81f9b-115">Logon failure: user account restriction.</span></span> <span data-ttu-id="81f9b-116">As possíveis razões para isso são senhas em branco não permitidas, restrições de horário de logon ou uma restrição de política que foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="81f9b-116">Possible reasons are blank passwords not allowed, login hour restrictions, or a policy restriction has been enforced.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81f9b-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="81f9b-117">Explanation</span></span>  
 <span data-ttu-id="81f9b-118">Este erro pode ocorrer quando você usa o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Gerenciador de Configurações para alternar para as contas internas (Serviço de Rede, Serviço Local ou Sistema Local) quando o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] está em execução em um Cluster do Windows Server ou em um Controlador de Domínio do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="81f9b-118">This error can occur when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager to switch to the built-in accounts (Network Service, Local Service, or Local System) when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is running on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="81f9b-119">Não execute serviços em contas internas de um Cluster do Windows Server ou de um Controlador de Domínio do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="81f9b-119">Do not run services under built-in accounts on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="81f9b-120">Para recomendações sobre contas de serviço, consulte o tópico Configurando as contas de serviço do Windows nos Manuais Online do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81f9b-120">For recommendations on service accounts, see the topic Setting Up Windows Service Accounts in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81f9b-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="81f9b-121">User Action</span></span>  
 <span data-ttu-id="81f9b-122">Configure o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para usar uma conta de domínio.</span><span class="sxs-lookup"><span data-stu-id="81f9b-122">Configure [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use a domain account.</span></span>  
  
  
