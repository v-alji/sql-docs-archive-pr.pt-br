---
title: 'Propriedades do alerta: novo alerta (página Opções) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.options.f1
ms.assetid: 6e4f41aa-832d-46ba-b6b5-cf1d3b15d33f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a1507372aa1516c2a88b8682faa77a7d57e58f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683919"
---
# <a name="alert-properties-new-alert-options-page"></a><span data-ttu-id="43e72-102">Propriedades do Alerta: Novo Alerta (página Opções)</span><span class="sxs-lookup"><span data-stu-id="43e72-102">Alert Properties: New Alert (Options Page)</span></span>
  <span data-ttu-id="43e72-103">Use esta página para exibir e modificar opções de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas de agente.</span><span class="sxs-lookup"><span data-stu-id="43e72-103">Use this page to view and modify options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="43e72-104">Opções</span><span class="sxs-lookup"><span data-stu-id="43e72-104">Options</span></span>  
 <span data-ttu-id="43e72-105">**Mensagens**</span><span class="sxs-lookup"><span data-stu-id="43e72-105">**E-mail**</span></span>  
 <span data-ttu-id="43e72-106">Inclua texto de erro do evento, se houver, em notificações de email.</span><span class="sxs-lookup"><span data-stu-id="43e72-106">Include error text from the event, if any, in e-mail notifications.</span></span>  
  
 <span data-ttu-id="43e72-107">**Pager**</span><span class="sxs-lookup"><span data-stu-id="43e72-107">**Pager**</span></span>  
 <span data-ttu-id="43e72-108">Inclua texto de erro do evento, se houver, em notificações de pager.</span><span class="sxs-lookup"><span data-stu-id="43e72-108">Include error text from the event, if any, in pager notifications.</span></span>  
  
 <span data-ttu-id="43e72-109">**Net send**</span><span class="sxs-lookup"><span data-stu-id="43e72-109">**Net send**</span></span>  
 <span data-ttu-id="43e72-110">Inclua texto de erro do evento, se houver, em notificações enviadas pela net.</span><span class="sxs-lookup"><span data-stu-id="43e72-110">Include error text from the event, if any, in net send notifications.</span></span>  
  
 <span data-ttu-id="43e72-111">**Mensagem de notificação adicional para enviar**</span><span class="sxs-lookup"><span data-stu-id="43e72-111">**Additional notification message to send**</span></span>  
 <span data-ttu-id="43e72-112">Digite qualquer texto adicional para incluir em mensagens de notificação.</span><span class="sxs-lookup"><span data-stu-id="43e72-112">Type any additional text to include in notification messages.</span></span>  
  
 <span data-ttu-id="43e72-113">**Atraso entre as respostas**</span><span class="sxs-lookup"><span data-stu-id="43e72-113">**Delay between responses**</span></span>  
 <span data-ttu-id="43e72-114">Especifique um intervalo para ocorrências repetidas do evento.</span><span class="sxs-lookup"><span data-stu-id="43e72-114">Specify a delay for repeated occurrences of the event.</span></span> <span data-ttu-id="43e72-115">Alguns eventos podem acontecer com frequência durante um curto intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="43e72-115">Some events may occur frequently during a short period of time.</span></span> <span data-ttu-id="43e72-116">Nesse caso, você pode desejar saber que o evento ocorreu, mas talvez não queira uma resposta para cada evento.</span><span class="sxs-lookup"><span data-stu-id="43e72-116">In this case, you may want to know that the event has occurred, but you may not want a response for every event.</span></span> <span data-ttu-id="43e72-117">Use esta opção para especificar um tempo limite. Com um atraso, depois que o alerta responde a um evento, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent aguarda o atraso especificado antes de responder novamente, independentemente de o evento ocorrer durante o atraso.</span><span class="sxs-lookup"><span data-stu-id="43e72-117">Use this option to specify a time-out. With a delay, after the alert responds to an event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for the delay specified before responding again, regardless of whether the event occurs during the delay.</span></span>  
  
 <span data-ttu-id="43e72-118">**Alguns**</span><span class="sxs-lookup"><span data-stu-id="43e72-118">**Minutes**</span></span>  
 <span data-ttu-id="43e72-119">Especifique um intervalo em minutos.</span><span class="sxs-lookup"><span data-stu-id="43e72-119">Specify a delay in minutes.</span></span> <span data-ttu-id="43e72-120">Para responder todas as vezes que o evento ocorrer, especifique 0 minuto e 0 segundo.</span><span class="sxs-lookup"><span data-stu-id="43e72-120">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
 <span data-ttu-id="43e72-121">**Seg**</span><span class="sxs-lookup"><span data-stu-id="43e72-121">**Seconds**</span></span>  
 <span data-ttu-id="43e72-122">Especifique um intervalo em segundos.</span><span class="sxs-lookup"><span data-stu-id="43e72-122">Specify a delay in seconds.</span></span> <span data-ttu-id="43e72-123">Para responder todas as vezes que o evento ocorrer, especifique 0 minuto e 0 segundo.</span><span class="sxs-lookup"><span data-stu-id="43e72-123">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e72-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="43e72-124">See Also</span></span>  
 [<span data-ttu-id="43e72-125">Alertas</span><span class="sxs-lookup"><span data-stu-id="43e72-125">Alerts</span></span>](alerts.md)  
  
  
