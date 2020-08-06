---
title: Gerenciador de conexões MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], message queues
- connection managers [Integration Services], MSMQ
- MSMQ connection manager
- message queue connections [Integration Services]
ms.assetid: a86900e2-450e-479f-b207-e1b02361d395
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c51866eeef281f6587bf281461e4faa2278308d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582084"
---
# <a name="msmq-connection-manager"></a><span data-ttu-id="cc858-102">Gerenciador de conexões MSMQ</span><span class="sxs-lookup"><span data-stu-id="cc858-102">MSMQ Connection Manager</span></span>
  <span data-ttu-id="cc858-103">Um gerenciador de conexões MSMQ permite que um pacote se conecte a uma fila de mensagens que usa Serviço de enfileiramento de mensagens (também conhecido como MSMQ).</span><span class="sxs-lookup"><span data-stu-id="cc858-103">An MSMQ connection manager enables a package to connect to a message queue that uses Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="cc858-104">A tarefa Fila de Mensagens que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclui, utiliza um gerenciador de conexões MSMQ.</span><span class="sxs-lookup"><span data-stu-id="cc858-104">The Message Queue task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an MSMQ connection manager.</span></span>  
  
 <span data-ttu-id="cc858-105">Ao adicionar um gerenciador de conexões MSMQ a um pacote, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] cria um gerenciador de conexões que disponibilizará uma conexão do MSMQ em tempo de execução, define as propriedades do gerenciador de conexões e adiciona o gerenciador de conexões à coleção de `Connections` no pacote.</span><span class="sxs-lookup"><span data-stu-id="cc858-105">When you add an MSMQ connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an MSMQ connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="cc858-106">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `MSMQ`.</span><span class="sxs-lookup"><span data-stu-id="cc858-106">The `ConnectionManagerType` property of the connection manager is set to `MSMQ`.</span></span>  
  
 <span data-ttu-id="cc858-107">É possível configurar um gerenciador de conexões MSMQ das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="cc858-107">You can configure an MSMQ connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="cc858-108">Fornecendo uma sequência de conexão.</span><span class="sxs-lookup"><span data-stu-id="cc858-108">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="cc858-109">Fornecendo o caminho da fila de mensagem à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="cc858-109">Provide the path of the message queue to connect to.</span></span>  
  
 <span data-ttu-id="cc858-110">O formato do caminho depende do tipo de fila, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="cc858-110">The format of the path depends on the type of queue, as shown in the following table.</span></span>  
  
|<span data-ttu-id="cc858-111">Tipo de fila</span><span class="sxs-lookup"><span data-stu-id="cc858-111">Queue type</span></span>|<span data-ttu-id="cc858-112">Exemplo de caminho</span><span class="sxs-lookup"><span data-stu-id="cc858-112">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="cc858-113">Público</span><span class="sxs-lookup"><span data-stu-id="cc858-113">Public</span></span>|<span data-ttu-id="cc858-114">\<computer name>\\<nome da fila\></span><span class="sxs-lookup"><span data-stu-id="cc858-114">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="cc858-115">Privado</span><span class="sxs-lookup"><span data-stu-id="cc858-115">Private</span></span>|<span data-ttu-id="cc858-116">\<computer name>\Private$\\<nome da fila\></span><span class="sxs-lookup"><span data-stu-id="cc858-116">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="cc858-117">Você pode usar um ponto (.) para representar o computador local.</span><span class="sxs-lookup"><span data-stu-id="cc858-117">You can use a period (.) to represent the local computer.</span></span>  
  
## <a name="configuration-of-the-msmq-connection-manager"></a><span data-ttu-id="cc858-118">Configuração do gerenciador de conexões MSMQ</span><span class="sxs-lookup"><span data-stu-id="cc858-118">Configuration of the MSMQ Connection Manager</span></span>  
 <span data-ttu-id="cc858-119">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="cc858-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="cc858-120">Para obter mais informações sobre as propriedades que podem ser definidas no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Editor do Gerenciador de Conexões MSMQ](../msmq-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="cc858-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [MSMQ Connection Manager Editor](../msmq-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="cc858-121">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="cc858-121">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc858-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc858-122">See Also</span></span>  
 <span data-ttu-id="cc858-123">[Tarefa Fila de Mensagens](../control-flow/message-queue-task.md) </span><span class="sxs-lookup"><span data-stu-id="cc858-123">[Message Queue Task](../control-flow/message-queue-task.md) </span></span>  
 [<span data-ttu-id="cc858-124">Conexões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cc858-124">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
