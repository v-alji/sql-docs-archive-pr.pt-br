---
title: Distributed Replay a configuração do cliente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccf03e32-6bd9-43c0-b9b6-9fe0d9163339
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 53124029483c25ed7894b279283e1de02c647350
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583352"
---
# <a name="distributed-replay-client-configuration"></a><span data-ttu-id="898d0-102">Configuração do Distributed Replay Client</span><span class="sxs-lookup"><span data-stu-id="898d0-102">Distributed Replay Client Configuration</span></span>
  <span data-ttu-id="898d0-103">Use a página **Configuração do Distributed Replay Client** do Assistente de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para especificar os usuários aos quais você deseja conceder permissões administrativas para o serviço Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="898d0-103">Use the **Distributed Replay Client Configuration** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the users you want to grant administrative permissions to for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="898d0-104">Usuários que têm permissões administrativas terão acesso ilimitado ao serviço Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="898d0-104">Users that have administrative permissions will have unlimited access to the Distributed Replay client service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="898d0-105">Opções</span><span class="sxs-lookup"><span data-stu-id="898d0-105">Options</span></span>  
 <span data-ttu-id="898d0-106">**Nome do Controlador**</span><span class="sxs-lookup"><span data-stu-id="898d0-106">**Controller Name**</span></span>  
 <span data-ttu-id="898d0-107">Esse é um parâmetro opcional, e o valor padrão é \<*blank*> .</span><span class="sxs-lookup"><span data-stu-id="898d0-107">This is an optional parameter, and the default value is \<*blank*>.</span></span>  
  
 <span data-ttu-id="898d0-108">Digite o nome do controlador com o qual o computador cliente se comunicará para o serviço Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="898d0-108">Enter the name of the controller that the client computer will communicate with for the Distributed Replay client service.</span></span> <span data-ttu-id="898d0-109">Observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="898d0-109">Note the following:</span></span>  
  
-   <span data-ttu-id="898d0-110">O nome deve ser um FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="898d0-110">The name must be a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="898d0-111">Por exemplo, um host chamado server1 na hierarquia de produtos na Microsoft pode ter um FQDN de server1.products.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="898d0-111">For example, a host called server1 in the products hierarchy at Microsoft may have an FQDN of server1.products.microsoft.com.</span></span>  
  
-   <span data-ttu-id="898d0-112">Se você já tiver configurado um controlador, digite o nome do controlador enquanto configura cada cliente.</span><span class="sxs-lookup"><span data-stu-id="898d0-112">If you have already set up a controller, enter the name of the controller while configuring each client.</span></span>  
  
-   <span data-ttu-id="898d0-113">Se você ainda não tiver configurado um controlador, poderá deixar o nome do controlador em branco.</span><span class="sxs-lookup"><span data-stu-id="898d0-113">If you have net yet set up a controller, you can leave the controller name blank.</span></span> <span data-ttu-id="898d0-114">No entanto, digite manualmente o nome do controlador no arquivo de **configuração do cliente** .</span><span class="sxs-lookup"><span data-stu-id="898d0-114">However, you must manually enter the controller name in the **client configuration** file.</span></span>  
  
 <span data-ttu-id="898d0-115">**Diretório de trabalho**</span><span class="sxs-lookup"><span data-stu-id="898d0-115">**Working Directory**</span></span>  
 <span data-ttu-id="898d0-116">Especifique o diretório de trabalho para o serviço Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="898d0-116">Specify the working directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="898d0-117">O diretório de trabalho padrão é \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span><span class="sxs-lookup"><span data-stu-id="898d0-117">The default working directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span></span>  
  
 <span data-ttu-id="898d0-118">**Diretório de Resultado**</span><span class="sxs-lookup"><span data-stu-id="898d0-118">**Result Directory**</span></span>  
 <span data-ttu-id="898d0-119">Especifique o diretório de resultado para o serviço Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="898d0-119">Specify the result directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="898d0-120">O diretório de resultado padrão é \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span><span class="sxs-lookup"><span data-stu-id="898d0-120">The default result directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span></span>  
  
  
