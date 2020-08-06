---
title: Designar um servidor de encaminhamento de eventos (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- alerts [SQL Server], forwarded events
ms.assetid: 81dfcbe4-3000-4e77-99de-bf85fef63a12
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc5f01507bf893d1bffc682f65a01b9ff48ffa9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683905"
---
# <a name="designate-an-events-forwarding-server-sql-server-management-studio"></a><span data-ttu-id="0c864-102">Designate an Events Forwarding Server (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0c864-102">Designate an Events Forwarding Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="0c864-103">Este tópico descreve como designar um servidor no qual o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encaminha eventos no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c864-103">This topic describes how to designate a server to which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] forwards events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span></span> <span data-ttu-id="0c864-104">Observe que o encaminhamento de eventos se aplica a eventos encaminhados entre servidores, não a eventos encaminhados entre instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hospedadas em um único computador.</span><span class="sxs-lookup"><span data-stu-id="0c864-104">Note that event forwarding applies to events forwarded between servers, not to events forwarded between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hosted on a single computer.</span></span> <span data-ttu-id="0c864-105">Note também que, para receber eventos encaminhados, o servidor de gerenciamento de alertas deve ser uma instância padrão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c864-105">Also note that in order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
 <span data-ttu-id="0c864-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="0c864-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0c864-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="0c864-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0c864-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="0c864-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0c864-109">**Para designar um servidor de encaminhamento de eventos, usando:**</span><span class="sxs-lookup"><span data-stu-id="0c864-109">**To designate an events forwarding server, using:**</span></span>  
  
     [<span data-ttu-id="0c864-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c864-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0c864-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0c864-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0c864-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="0c864-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0c864-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="0c864-113">Permissions</span></span>  
 <span data-ttu-id="0c864-114">Exige associação à função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="0c864-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0c864-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c864-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-an-events-forwarding-server"></a><span data-ttu-id="0c864-116">Para designar um servidor de encaminhamento de eventos</span><span class="sxs-lookup"><span data-stu-id="0c864-116">To designate an events forwarding server</span></span>  
  
1.  <span data-ttu-id="0c864-117">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor do qual você deseja encaminhar eventos para outro servidor.</span><span class="sxs-lookup"><span data-stu-id="0c864-117">In **Object Explorer,** click the plus sign to expand the server from which you want to forward events to another server.</span></span>  
  
2.  <span data-ttu-id="0c864-118">Clique com o botão direito do mouse em **SQL Server Agent** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0c864-118">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="0c864-119">Na caixa de diálogo **Propriedades do SQL Server Agent –**_nome_do_servidor_, em **Selecionar uma página**, selecione **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="0c864-119">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Advanced**.</span></span>  

4.  <span data-ttu-id="0c864-120">Em **Encaminhamento de evento do SQL Server**, marque a caixa de seleção **Encaminhar eventos para um servidor diferente** .</span><span class="sxs-lookup"><span data-stu-id="0c864-120">Under **SQL Server event forwarding**, select the **Forward events to a different server** check box.</span></span>  
  
5.  <span data-ttu-id="0c864-121">Na lista **Servidor** , selecione um servidor e, em **Eventos**, selecione um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="0c864-121">In the **Server** list, select a server, and then, under **Events**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="0c864-122">Selecione **Eventos sem tratamento** para encaminhar apenas os eventos que não foram manipulados por alertas locais.</span><span class="sxs-lookup"><span data-stu-id="0c864-122">Select **Unhandled events** to forward only the events that have not been handled by local alerts.</span></span>  
  
    -   <span data-ttu-id="0c864-123">Selecione **Todos os eventos** para encaminhar todos os eventos, independentemente de terem sido manipulados por alertas locais.</span><span class="sxs-lookup"><span data-stu-id="0c864-123">Select **All events** to forward all events regardless of whether they have been handled by local alerts.</span></span>  
  
6.  <span data-ttu-id="0c864-124">Na lista **Se a severidade do evento for esta ou acima** , clique no nível de severidade em que os eventos devem ser encaminhados para o servidor selecionado.</span><span class="sxs-lookup"><span data-stu-id="0c864-124">In the **If event has severity at or above** list, click the severity level at which events are forwarded to the selected server.</span></span>  
  
7.  <span data-ttu-id="0c864-125">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c864-125">When finished, click **OK**.</span></span>  
  
  
