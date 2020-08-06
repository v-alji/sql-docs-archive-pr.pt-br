---
title: Opção de configuração de servidor blocked process threshold | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- thresholds [SQL Server]
- blocked process threshold option
ms.assetid: 3d46d143-bc6a-4220-8b55-6baa37547c25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9d5b61aaf23a8e74cb11afbf4e8bdb958fde6abe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683681"
---
# <a name="blocked-process-threshold-server-configuration-option"></a><span data-ttu-id="25ee3-102">Opção blocked process threshold de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="25ee3-102">blocked process threshold Server Configuration Option</span></span>
  <span data-ttu-id="25ee3-103">Use a opção **blocked process threshold** para especificar o limite, em segundos, no qual os relatórios de processo bloqueado serão gerados.</span><span class="sxs-lookup"><span data-stu-id="25ee3-103">Use the **blocked process threshold** option to specify the threshold, in seconds, at which blocked process reports are generated.</span></span> <span data-ttu-id="25ee3-104">O limite pode ser definido de 0 a 86.400.</span><span class="sxs-lookup"><span data-stu-id="25ee3-104">The threshold can be set from 0 to 86,400.</span></span> <span data-ttu-id="25ee3-105">Por padrão, não são produzidos relatórios de processo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="25ee3-105">By default, no blocked process reports are produced.</span></span> <span data-ttu-id="25ee3-106">Esse evento não é gerado para tarefas de sistema ou tarefas que estão esperando recursos que não geram deadlocks detectáveis.</span><span class="sxs-lookup"><span data-stu-id="25ee3-106">This event is not generated for system tasks or for tasks that are waiting on resources that do not generate detectable deadlocks.</span></span>  
  
 <span data-ttu-id="25ee3-107">É possível definir um [alerta](../../ssms/agent/alerts.md) a ser executado quando esse evento é gerado.</span><span class="sxs-lookup"><span data-stu-id="25ee3-107">You can define an [alert](../../ssms/agent/alerts.md) to be executed when this event is generated.</span></span> <span data-ttu-id="25ee3-108">Assim, por exemplo, é possível optar por chamar o administrador para tomar medidas adequadas a fim de resolver a situação de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="25ee3-108">So for example, you can choose to page the administrator to take appropriate action to handle the blocking situation.</span></span>  
  
 <span data-ttu-id="25ee3-109">O limite de processo bloqueado utiliza o thread em segundo plano do monitor deadlock para orientar a lista de tarefas que esperam por um tempo maior ou vários limites configurados.</span><span class="sxs-lookup"><span data-stu-id="25ee3-109">Blocked process threshold uses the deadlock monitor background thread to walk through the list of tasks waiting for a time greater than or multiples of the configured threshold.</span></span> <span data-ttu-id="25ee3-110">O evento é gerado uma vez por intervalo de relatório para cada uma das tarefas bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="25ee3-110">The event is generated once per reporting interval for each of the blocked tasks.</span></span>  
  
 <span data-ttu-id="25ee3-111">O relatório de processo bloqueado é feito em uma melhor base de esforço.</span><span class="sxs-lookup"><span data-stu-id="25ee3-111">The blocked process report is done on a best effort basis.</span></span> <span data-ttu-id="25ee3-112">Não há nenhuma garantia de qualquer relatório em tempo real ou até mesmo próximo a tempo real.</span><span class="sxs-lookup"><span data-stu-id="25ee3-112">There is no guarantee of any real-time or even close to real-time reporting.</span></span>  
  
 <span data-ttu-id="25ee3-113">A configuração entra em vigor imediatamente, sem que o servidor seja parado e reiniciado.</span><span class="sxs-lookup"><span data-stu-id="25ee3-113">The setting takes effect immediately without a server stop and restart.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="25ee3-114">Exemplos</span><span class="sxs-lookup"><span data-stu-id="25ee3-114">Examples</span></span>  
 <span data-ttu-id="25ee3-115">O exemplo a seguir define o `blocked process threshold` em `20` segundos, gerando um relatório de processo bloqueado para cada tarefa que é bloqueada.</span><span class="sxs-lookup"><span data-stu-id="25ee3-115">The following example sets the `blocked process threshold` to `20` seconds, generating a blocked process report for each task that is blocked.</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 20 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="25ee3-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25ee3-116">See Also</span></span>  
 <span data-ttu-id="25ee3-117">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="25ee3-117">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="25ee3-118">Classe de evento Blocked Process Report</span><span class="sxs-lookup"><span data-stu-id="25ee3-118">Blocked Process Report Event Class</span></span>](../../relational-databases/event-classes/blocked-process-report-event-class.md)  
  
  
