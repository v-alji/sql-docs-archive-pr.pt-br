---
title: Gerar script de uma sessão de evento estendido | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f9fdde-1f13-4292-a4fc-55da826be3b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11adc60ae7c7e0f8b8012d06f56c83874d3708ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572674"
---
# <a name="script-an-extended-event-session"></a><span data-ttu-id="68f3b-102">Criar script de uma sessão de evento estendido</span><span class="sxs-lookup"><span data-stu-id="68f3b-102">Script an Extended Event Session</span></span>
  <span data-ttu-id="68f3b-103">Este tópico descreve como criar o script de uma sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="68f3b-103">This topic describes how to script an event session.</span></span> <span data-ttu-id="68f3b-104">Você pode exportar, alterar ou remover a sessão de evento, ou remover e criar a sessão de evento para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="68f3b-104">You can export, alter, or drop the event session, or drop and create the event session to the following:</span></span>  
  
-   <span data-ttu-id="68f3b-105">**Janela do Editor de Nova Consulta**</span><span class="sxs-lookup"><span data-stu-id="68f3b-105">**New Query Editor Window**</span></span>  
  
-   <span data-ttu-id="68f3b-106">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="68f3b-106">**File**</span></span>  
  
-   <span data-ttu-id="68f3b-107">**Área de transferência**</span><span class="sxs-lookup"><span data-stu-id="68f3b-107">**Clipboard**</span></span>  
  
-   <span data-ttu-id="68f3b-108">**Trabalho do Agente**</span><span class="sxs-lookup"><span data-stu-id="68f3b-108">**Agent Job**</span></span>  
  
### <a name="to-script-an-existing-event-session"></a><span data-ttu-id="68f3b-109">Para criar o script de uma sessão de evento existente</span><span class="sxs-lookup"><span data-stu-id="68f3b-109">To script an existing event session</span></span>  
  
1.  <span data-ttu-id="68f3b-110">No Pesquisador de Objetos, expanda o nó **Gerenciamento** e, em seguida, expanda **Eventos Estendidos**.</span><span class="sxs-lookup"><span data-stu-id="68f3b-110">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="68f3b-111">Clique com o botão direito do mouse na sessão para a qual deseja criar um script, aponte para **Sessão de Script como**, aponte para **CREATE to**e selecione o local onde deseja criar o script da sessão.</span><span class="sxs-lookup"><span data-stu-id="68f3b-111">Right-click the session you want to script, point to **Script Session as**, point to **CREATE to**, and then select where you want to script the session.</span></span>  
  
### <a name="to-script-a-new-event-session"></a><span data-ttu-id="68f3b-112">Para criar o script de uma nova sessão de evento</span><span class="sxs-lookup"><span data-stu-id="68f3b-112">To script a new event session</span></span>  
  
1.  <span data-ttu-id="68f3b-113">No Pesquisador de Objetos, expanda o nó **Gerenciamento** e, em seguida, expanda **Eventos Estendidos**.</span><span class="sxs-lookup"><span data-stu-id="68f3b-113">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="68f3b-114">Clique com o botão direito do mouse em **Sessões**e clique em **Nova Sessão**.</span><span class="sxs-lookup"><span data-stu-id="68f3b-114">Right-click **Sessions**, and then click **New Session**.</span></span>  
  
3.  <span data-ttu-id="68f3b-115">Na interface do usuário **Nova Sessão** , crie a sessão de evento e selecione o local onde deseja criar o script da sessão de evento na lista suspensa **Script** .</span><span class="sxs-lookup"><span data-stu-id="68f3b-115">In the **New Session** UI, create the event session, and then select where you want to script the event session from the **Script** drop-down list.</span></span>  
  
### <a name="to-script-a-modified-event-session"></a><span data-ttu-id="68f3b-116">Para criar o script de uma sessão de evento modificada</span><span class="sxs-lookup"><span data-stu-id="68f3b-116">To script a modified event session</span></span>  
  
1.  <span data-ttu-id="68f3b-117">No Pesquisador de Objetos, expanda o nó **Gerenciamento** e, em seguida, expanda **Eventos Estendidos**.</span><span class="sxs-lookup"><span data-stu-id="68f3b-117">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="68f3b-118">Clique com o botão direito do mouse na sessão a ser modificada e clique com o botão direito do mouse em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="68f3b-118">Right-click the session you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="68f3b-119">Na interface do usuário **Propriedades da Sessão** , modifique a sessão de evento e selecione o local onde deseja criar o script da sessão de modificada na lista suspensa **Script** .</span><span class="sxs-lookup"><span data-stu-id="68f3b-119">In the **Session Properties** dialog box, modify the event session, and then select where you want to script the modified session from the **Script** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f3b-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="68f3b-120">See Also</span></span>  
 [<span data-ttu-id="68f3b-121">Eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="68f3b-121">Extended Events</span></span>](../relational-databases/extended-events/extended-events.md)  
  
  
