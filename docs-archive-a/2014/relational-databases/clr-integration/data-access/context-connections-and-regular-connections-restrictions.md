---
title: Restrições em conexões regulares e de contexto | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: 0c6fe4cb-d846-40b5-8884-35a9c770f5e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 52f50347a27cdaffe83b252d86c56382b5ef4f31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575170"
---
# <a name="restrictions-on-regular-and-context-connections"></a><span data-ttu-id="c252e-102">Restrições em conexões comuns e de contexto</span><span class="sxs-lookup"><span data-stu-id="c252e-102">Restrictions on Regular and Context Connections</span></span>
  <span data-ttu-id="c252e-103">Este tópico discute as restrições associadas ao código em execução no [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] processo por meio de contexto e conexões regulares.</span><span class="sxs-lookup"><span data-stu-id="c252e-103">This topic discusses the restrictions associated with code executing in the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] process through context and regular connections.</span></span>  
  
## <a name="restrictions-on-context-connections"></a><span data-ttu-id="c252e-104">Restrições em conexões de contexto</span><span class="sxs-lookup"><span data-stu-id="c252e-104">Restrictions on Context Connections</span></span>  
 <span data-ttu-id="c252e-105">Ao desenvolver seu aplicativo, leve em consideração as restrições a seguir que se aplicam a conexões de contexto:</span><span class="sxs-lookup"><span data-stu-id="c252e-105">When developing your application, take into account the following restrictions that apply to context connections:</span></span>  
  
-   <span data-ttu-id="c252e-106">Você pode ter apenas uma conexão de contexto aberta em um determinado momento para uma determinada conexão.</span><span class="sxs-lookup"><span data-stu-id="c252e-106">You can have only one context connection open at a given time for a given connection.</span></span> <span data-ttu-id="c252e-107">Se você tiver várias instruções em execução simultânea em conexões separadas, cada uma delas poderá obter sua própria conexão de contexto.</span><span class="sxs-lookup"><span data-stu-id="c252e-107">If you have multiple statements running concurrently in separate connections, each one of them can get their own context connection.</span></span> <span data-ttu-id="c252e-108">A restrição não afeta solicitações simultâneas de conexões diferentes; ela afeta apenas uma determinada solicitação em uma determinada conexão.</span><span class="sxs-lookup"><span data-stu-id="c252e-108">The restriction does not affect concurrent requests from different connections; it only affects a given request on a given connection.</span></span>  
  
-   <span data-ttu-id="c252e-109">Uma conexão de contexto não oferece suporte a Vários Conjuntos de Resultados Ativos (MARS).</span><span class="sxs-lookup"><span data-stu-id="c252e-109">Multiple Active Result Sets (MARS) is not supported in a context connection.</span></span>  
  
-   <span data-ttu-id="c252e-110">A classe `SqlBulkCopy` não opera em uma conexão de contexto.</span><span class="sxs-lookup"><span data-stu-id="c252e-110">The `SqlBulkCopy` class does not operate in a context connection.</span></span>  
  
-   <span data-ttu-id="c252e-111">Não existe suporte para a execução de atualizações em lote em uma conexão de contexto.</span><span class="sxs-lookup"><span data-stu-id="c252e-111">Update batching in a context connection is not supported</span></span>  
  
-   <span data-ttu-id="c252e-112">`SqlNotificationRequest` não pode ser usado com comandos que são executados em uma conexão de contexto.</span><span class="sxs-lookup"><span data-stu-id="c252e-112">`SqlNotificationRequest` cannot be used with commands that execute against a context connection.</span></span>  
  
-   <span data-ttu-id="c252e-113">Não existe suporte para o cancelamento de comandos que estão sendo executados na conexão de contexto.</span><span class="sxs-lookup"><span data-stu-id="c252e-113">Canceling commands that are running against the context connection is not supported.</span></span> <span data-ttu-id="c252e-114">O método `SqlCommand.Cancel` ignora a solicitação silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="c252e-114">The `SqlCommand.Cancel` method silently ignores the request.</span></span>  
  
-   <span data-ttu-id="c252e-115">Nenhuma outra palavra-chave de cadeia de conexão poderá ser usada quando você usar "context connection=true".</span><span class="sxs-lookup"><span data-stu-id="c252e-115">No other connection string keywords can be used when you use "context connection=true".</span></span>  
  
-   <span data-ttu-id="c252e-116">A propriedade `SqlConnection.DataSource` retornará nulo se a cadeia de conexão para `SqlConnection` for "context connection=true", em vez do nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c252e-116">The `SqlConnection.DataSource` property returns null if the connection string for the `SqlConnection` is "context connection=true", instead of the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="c252e-117">Definir a propriedade `SqlCommand.CommandTimeout` não tem nenhum efeito quando o comando é executado em uma conexão de contexto.</span><span class="sxs-lookup"><span data-stu-id="c252e-117">Setting the `SqlCommand.CommandTimeout` property has no effect when the command is executed against a context connection.</span></span>  
  
## <a name="restrictions-on-regular-connections"></a><span data-ttu-id="c252e-118">Restrições em conexões comuns</span><span class="sxs-lookup"><span data-stu-id="c252e-118">Restrictions on Regular Connections</span></span>  
 <span data-ttu-id="c252e-119">Ao desenvolver seu aplicativo, leve em consideração as restrições a seguir que se aplicam a conexões comuns:</span><span class="sxs-lookup"><span data-stu-id="c252e-119">When developing your application, take into account the following restrictions that apply to regular connections:</span></span>  
  
-   <span data-ttu-id="c252e-120">Não existe suporte para a execução assíncrona de comandos em servidores internos.</span><span class="sxs-lookup"><span data-stu-id="c252e-120">Asynchronous command execution against internal servers is not supported.</span></span> <span data-ttu-id="c252e-121">Incluir "async=true" na cadeia de conexão de um comando e, depois, executar o comando resultará na geração de `System.NotSupportedException`.</span><span class="sxs-lookup"><span data-stu-id="c252e-121">Including "async=true" in the connection string of a command, and then executing the command, results in `System.NotSupportedException` being thrown.</span></span> <span data-ttu-id="c252e-122">Esta mensagem será exibida: "Não existe suporte para processamento assíncrono quando executado dentro do processo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c252e-122">This message appears: "Asynchronous processing is not supported when running inside the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process."</span></span>  
  
-   <span data-ttu-id="c252e-123">Não existe suporte para o objeto `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="c252e-123">`SqlDependency` object is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c252e-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c252e-124">See Also</span></span>  
 [<span data-ttu-id="c252e-125">Conexão de contexto</span><span class="sxs-lookup"><span data-stu-id="c252e-125">Context Connection</span></span>](context-connection.md)  
  
  
