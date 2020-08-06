---
title: Alterar uma sessão eventos estendidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 114ec05b-7eca-4c87-b276-25e37b84be39
author: rothja
ms.author: jroth
ms.openlocfilehash: 14be41e48262bc7ebc8aeeaf55185f5e35d0c72e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568577"
---
# <a name="alter-an-extended-events-session"></a><span data-ttu-id="71752-102">Alterar uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="71752-102">Alter an Extended Events Session</span></span>
  <span data-ttu-id="71752-103">Depois que você criar uma sessão de Eventos Estendidos, poderá alterá-la de acordo com suas necessidades usando o **Assistente de Eventos Estendidos do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="71752-103">After you create an Extended Events session, you can alter it according to your needs using the **SQL Server Extended Events Wizard**.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="71752-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="71752-104">Before you Begin</span></span>  
 <span data-ttu-id="71752-105">Não é possível alterar um destino para sessões ativas e inativas e nem as configurações de propriedades avançadas de uma sessão ativa.</span><span class="sxs-lookup"><span data-stu-id="71752-105">You cannot alter a target for active and inactive sessions, and you cannot change the advanced properties configurations for an active session.</span></span>  
  
 <span data-ttu-id="71752-106">Você pode fazer as seguintes alterações em sessões de evento ativas e inativas:</span><span class="sxs-lookup"><span data-stu-id="71752-106">You can make the following alterations to both active and inactive event sessions:</span></span>  
  
-   <span data-ttu-id="71752-107">Adicione ou remova eventos da sessão e altere as configurações de evento, como campos de evento, filtros e ações.</span><span class="sxs-lookup"><span data-stu-id="71752-107">Add or remove events from the session, and alter the event configurations such as event fields, filters and actions.</span></span>  
  
-   <span data-ttu-id="71752-108">Adicione ou remova um destino da sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="71752-108">Add or remove a target from the event session.</span></span>  
  
-   <span data-ttu-id="71752-109">Habilite a opção **Iniciar a sessão de evento na inicialização do servidor** .</span><span class="sxs-lookup"><span data-stu-id="71752-109">Enable the **Start the event session on server startup** option.</span></span>  
  
 <span data-ttu-id="71752-110">Você pode fazer as seguintes alterações adicionais em uma sessão de evento inativa:</span><span class="sxs-lookup"><span data-stu-id="71752-110">You can make the following additional alterations to an inactive event session:</span></span>  
  
-   <span data-ttu-id="71752-111">Habilite a opção **Rastrear a relação entre eventos** .</span><span class="sxs-lookup"><span data-stu-id="71752-111">Enable the **Track the relationship between events** option.</span></span>  
  
-   <span data-ttu-id="71752-112">Altere a configuração das propriedades avançadas.</span><span class="sxs-lookup"><span data-stu-id="71752-112">Change the advanced properties configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71752-113">O **Assistente de Eventos Estendidos do SQL Server** não dá suporte à modificação da sessão de eventos.</span><span class="sxs-lookup"><span data-stu-id="71752-113">The **SQL Server Extended Events Wizard** does not support event session modification.</span></span>  
  
## <a name="how-to-alter-an-extended-events-session-using-the-sql-server-extended-events-wizard"></a><span data-ttu-id="71752-114">Como alterar uma sessão de Eventos Estendidos usando o Assistente de Eventos Estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="71752-114">How to alter an Extended Events session using the SQL Server Extended Events Wizard</span></span>  
  
-   <span data-ttu-id="71752-115">No Pesquisador de Objetos, expanda **Gerenciamento**, expanda **Eventos Estendidos**e, em seguida, expanda **Sessões**.</span><span class="sxs-lookup"><span data-stu-id="71752-115">In Object Explorer, expand **Management**, expand **Extended Events**, and then expand **Sessions**.</span></span>  
  
-   <span data-ttu-id="71752-116">Clique com o botão direito do mouse na sessão a ser alterada e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="71752-116">Right-click the session you want to alter, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="71752-117">Na caixa de diálogo **Propriedades** , faça as alterações apropriadas e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="71752-117">In the **Properties** dialog box, make the appropriate changes, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71752-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71752-118">See Also</span></span>  
 <span data-ttu-id="71752-119">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="71752-119">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="71752-120">Criar uma sessão de Eventos Estendidos usando o Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="71752-120">Create an Extended Events Session Using Query Editor</span></span>](../../database-engine/create-an-extended-events-session-using-query-editor.md)  
  
  
