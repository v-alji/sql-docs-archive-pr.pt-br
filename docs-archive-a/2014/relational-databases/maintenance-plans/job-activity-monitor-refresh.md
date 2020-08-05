---
title: Atualização do Monitor de Atividade do Trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.jobactivitymon.refresh.f1
ms.assetid: 413a368e-fd2b-4e1f-b370-002cdbc85bab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f290825f8a776c954ef802b184f7600aea5dc9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573980"
---
# <a name="job-activity-monitor-refresh"></a><span data-ttu-id="d5ace-102">Atualizar Monitor de Atividade do Trabalho</span><span class="sxs-lookup"><span data-stu-id="d5ace-102">Job Activity Monitor Refresh</span></span>
  <span data-ttu-id="d5ace-103">Use a caixa de diálogo **Atualizar Configurações** para configurar com que frequência o Monitor de Atividade do Trabalho obtém informações novas sobre a atividade de servidor.</span><span class="sxs-lookup"><span data-stu-id="d5ace-103">Use the **Refresh Settings** dialog box to configure how often Job Activity Monitor obtains new information about server activity.</span></span> <span data-ttu-id="d5ace-104">O Monitor de Atividade do Trabalho deve executar consultas no servidor monitorado para obter informações para a grade do Monitor de Atividade do Trabalho.</span><span class="sxs-lookup"><span data-stu-id="d5ace-104">Job Activity Monitor must run queries on the monitored server to obtain information for the Job Activity Monitor grid.</span></span> <span data-ttu-id="d5ace-105">Quando o intervalo de atualização automática for definido como menos de 30 segundos, o tempo usado para executar essas consultas poderá afetar o desempenho do servidor.</span><span class="sxs-lookup"><span data-stu-id="d5ace-105">When the auto-refresh interval is set to less than 30 seconds, the time used to run these queries can affect server performance.</span></span>  
  
 <span data-ttu-id="d5ace-106">Para abrir essa caixa de diálogo, clique em **Exibir configurações de atualização**, na seção **Status** do Monitor de Atividade do Trabalho.</span><span class="sxs-lookup"><span data-stu-id="d5ace-106">To open this dialog, click **View refresh settings**, in the **Status** section of Job Activity Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d5ace-107">Opções</span><span class="sxs-lookup"><span data-stu-id="d5ace-107">Options</span></span>  
 <span data-ttu-id="d5ace-108">**Atualizar automaticamente a cada**</span><span class="sxs-lookup"><span data-stu-id="d5ace-108">**Auto-refresh every**</span></span>  
 <span data-ttu-id="d5ace-109">Marque para iniciar a atualização automática de informações do Monitor de Atividade.</span><span class="sxs-lookup"><span data-stu-id="d5ace-109">Check to initiate automatic refreshing of Activity Monitor information.</span></span> <span data-ttu-id="d5ace-110">Isso está definido como desativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="d5ace-110">This is off by default.</span></span>  
  
 <span data-ttu-id="d5ace-111">**segundos**</span><span class="sxs-lookup"><span data-stu-id="d5ace-111">**seconds**</span></span>  
 <span data-ttu-id="d5ace-112">O número de segundos entre as tentativas de atualização automática.</span><span class="sxs-lookup"><span data-stu-id="d5ace-112">The number of seconds between auto-refresh attempts.</span></span> <span data-ttu-id="d5ace-113">O padrão é 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="d5ace-113">Defaults to 60 seconds.</span></span> <span data-ttu-id="d5ace-114">Faz atualizações a cada 5 segundos quando definido como 5 ou menos.</span><span class="sxs-lookup"><span data-stu-id="d5ace-114">Refreshes every 5 seconds when set to 5 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ace-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d5ace-115">See Also</span></span>  
 [<span data-ttu-id="d5ace-116">Monitorar Atividade do Trabalho</span><span class="sxs-lookup"><span data-stu-id="d5ace-116">Monitor Job Activity</span></span>](../../ssms/agent/monitor-job-activity.md)  
  
  
