---
title: Conexões regulares vs. de contexto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: a1dead02-be88-4b16-8cb2-db1284856764
author: rothja
ms.author: jroth
ms.openlocfilehash: ce531129099a8f4908bdc4b29920696d4ba3c505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583650"
---
# <a name="regular-vs-context-connections"></a><span data-ttu-id="3a02e-102">Regular vs. Conexões de contexto</span><span class="sxs-lookup"><span data-stu-id="3a02e-102">Regular vs. Context Connections</span></span>
  <span data-ttu-id="3a02e-103">Se você estiver conectando a um servidor remoto, sempre use conexões normais, em vez de conexões de contexto.</span><span class="sxs-lookup"><span data-stu-id="3a02e-103">If you are connecting to a remote server, always use regular connections rather than context connections.</span></span> <span data-ttu-id="3a02e-104">Se você precisar se conectar ao mesmo servidor em que o procedimento armazenado ou a função está sendo executado, use a conexão de contexto na maioria dos casos.</span><span class="sxs-lookup"><span data-stu-id="3a02e-104">If you need to connect to the same server on which the stored procedure or function is running, use the context connection in most cases.</span></span> <span data-ttu-id="3a02e-105">Isto tem benefícios, como executar no mesmo espaço de transação e não precisar se autenticar novamente.</span><span class="sxs-lookup"><span data-stu-id="3a02e-105">This has benefits such as running in the same transaction space and not having to reauthenticate.</span></span>  
  
 <span data-ttu-id="3a02e-106">Além disso, o uso da conexão de contexto normalmente resulta em melhor desempenho e menos uso de recurso.</span><span class="sxs-lookup"><span data-stu-id="3a02e-106">Additionally, using the context connection typically results in better performance and less resource usage.</span></span> <span data-ttu-id="3a02e-107">A conexão de contexto é uma conexão somente em processo, portanto, ela pode entrar em contato com o servidor "diretamente", ignorando as camadas de protocolo de rede e transporte para enviar instruções Transact-SQL e receber resultados.</span><span class="sxs-lookup"><span data-stu-id="3a02e-107">The context connection is an in-process-only connection, so it can contact the server "directly" by bypassing the network protocol and transport layers to send Transact-SQL statements and receive results.</span></span> <span data-ttu-id="3a02e-108">O processo de autenticação é ignorado também.</span><span class="sxs-lookup"><span data-stu-id="3a02e-108">The authentication process is bypassed, as well.</span></span> <span data-ttu-id="3a02e-109">A figura a seguir mostra os principais componentes do provedor gerenciado por `SqlClient`, e também como os diferentes componentes interagem entre si durante o uso de uma conexão normal e da conexão de contexto.</span><span class="sxs-lookup"><span data-stu-id="3a02e-109">The following figure shows the primary components of the `SqlClient` managed provider, as well as how the different components interact with each other when using a regular connection, and when using the context connection.</span></span>  
  
 <span data-ttu-id="3a02e-110">![Caminhos de código de um contexto e uma conexão regular.](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Caminhos de código de um contexto e uma conexão regular.")</span><span class="sxs-lookup"><span data-stu-id="3a02e-110">![Code paths of a context and a regular connnection.](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Code paths of a context and a regular connnection.")</span></span>  
  
 <span data-ttu-id="3a02e-111">A conexão de contexto segue um caminho de código mais curto e envolve menos componentes. Dessa forma, você pode esperar que as solicitações e os resultados sejam enviados e recebidos do servidor mais rapidamente do que em uma conexão normal.</span><span class="sxs-lookup"><span data-stu-id="3a02e-111">The context connection follows a shorter code path and involves fewer components, so you can expect requests and results to get to and from the server faster than in a regular connection.</span></span> <span data-ttu-id="3a02e-112">O tempo de execução da consulta no servidor é o mesmo para conexões de contexto e normais.</span><span class="sxs-lookup"><span data-stu-id="3a02e-112">Query execution time on the server is the same for context and regular connections.</span></span>  
  
 <span data-ttu-id="3a02e-113">Há alguns casos em que você pode precisar abrir uma conexão normal separada para o mesmo servidor.</span><span class="sxs-lookup"><span data-stu-id="3a02e-113">There are some cases in which you may need to open a separate regular connection to the same server.</span></span> <span data-ttu-id="3a02e-114">Por exemplo, há certas restrições no uso da conexão de contexto, descritas em [restrições em conexões regulares e de contexto](context-connections-and-regular-connections-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="3a02e-114">For example, there are certain restrictions on using the context connection, described in [Restrictions on Regular and Context Connections](context-connections-and-regular-connections-restrictions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a02e-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3a02e-115">See Also</span></span>  
 [<span data-ttu-id="3a02e-116">Conexão de contexto</span><span class="sxs-lookup"><span data-stu-id="3a02e-116">Context Connection</span></span>](context-connection.md)  
  
  
