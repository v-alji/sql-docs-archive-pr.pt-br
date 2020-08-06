---
title: Criar um evento definido pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent alerts, user-defined events
- user-defined events [SQL Server]
- multiple language support [SQL Server], alerts
- languages [SQL Server], alerts
- severity levels [SQL Server]
- global considerations [SQL Server], alerts
- events [SQL Server], user-defined
- SQL Server Agent alerts, multiple-language environments
- alerts [SQL Server], user-defined events
- alerts [SQL Server], multiple-language environments
- custom events [SQL Server Agent]
- international considerations [SQL Server], alerts
ms.assetid: 03d71a35-97fa-4bba-aa9a-23ac9c9cf879
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2323dc4da3d1a8a67dad41ea189877ade25eff0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686018"
---
# <a name="create-a-user-defined-event"></a><span data-ttu-id="afad5-102">Criar um evento definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="afad5-102">Create a User-Defined Event</span></span>
  <span data-ttu-id="afad5-103">Você pode criar eventos definidos pelo usuário caso deseje monitorar eventos diferentes daqueles predefinidos pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afad5-103">You can create user-defined events if you want to monitor events other than events that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="afad5-104">Você também pode atribuir um nível de severidade a cada evento definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="afad5-104">You can also assign a severity level to each user-defined event.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="afad5-105">Ao usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], selecione a opção **Gravar no log de eventos de aplicativo do Windows** para cada mensagem de evento definido pelo usuário, a fim de garantir que as mensagens sejam registradas.</span><span class="sxs-lookup"><span data-stu-id="afad5-105">When using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Write to Windows application event log** option for each user-defined event message, to ensure that the messages are logged.</span></span> <span data-ttu-id="afad5-106">Por padrão, as mensagens definidas pelo usuário que tenham severidade abaixo de 19 não são enviadas ao log de aplicativos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows quando ocorrem.</span><span class="sxs-lookup"><span data-stu-id="afad5-106">By default, user-defined messages of severity lower than 19 are not sent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log when they occur.</span></span> <span data-ttu-id="afad5-107">Portanto, as mensagens definidas pelo usuário que tenham severidade abaixo de 19 não disparam alertas do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="afad5-107">User-defined messages of severity lower than 19 therefore do not trigger SQL Server Agent alerts.</span></span>  
  
 <span data-ttu-id="afad5-108">Os eventos definidos pelo usuário devem ter um número de mensagem exclusivo.</span><span class="sxs-lookup"><span data-stu-id="afad5-108">User-defined events must have a unique message number.</span></span> <span data-ttu-id="afad5-109">Os números de mensagem de um evento definido pelo usuário devem ser maiores que 50.000.</span><span class="sxs-lookup"><span data-stu-id="afad5-109">Message numbers for a user-defined event must be greater than 50,000.</span></span> <span data-ttu-id="afad5-110">Você pode definir mensagens para o evento em múltiplos idiomas.</span><span class="sxs-lookup"><span data-stu-id="afad5-110">You can define messages for the event in multiple languages.</span></span> <span data-ttu-id="afad5-111">No entanto, deve existir uma mensagem de erro em **En-US** para que possam ser adicionadas mensagens em outros idiomas.</span><span class="sxs-lookup"><span data-stu-id="afad5-111">However, an **En-US** error message must exist before messages in other languages can be added.</span></span>  
  
 <span data-ttu-id="afad5-112">Se você administra um ambiente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] multilíngue, crie mensagens definidas pelo usuário em cada um dos idiomas com suporte.</span><span class="sxs-lookup"><span data-stu-id="afad5-112">If you administer a multiple-language [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment, create user-defined messages in each of the languages that are supported.</span></span> <span data-ttu-id="afad5-113">Por exemplo, se estiver criando uma nova mensagem de evento a ser usada em dois servidores, um em inglês e outro em alemão, use o mesmo número de mensagem e de severidade para ambos, mas atribua um idioma diferente a cada um.</span><span class="sxs-lookup"><span data-stu-id="afad5-113">For example, if you are creating a new event message to be used on both an English and a German server, use the same message number and severity for both, but assign a different language to each.</span></span>  
  
 <span data-ttu-id="afad5-114">As seguintes tarefas proporcionam informações sobre como criar eventos definidos pelo usuário e alertas em resposta a eles:</span><span class="sxs-lookup"><span data-stu-id="afad5-114">The following tasks provide information about how to create user-defined events and alerts that respond to them:</span></span>  
  
 <span data-ttu-id="afad5-115">**Para criar um alerta com base em um número de mensagem**</span><span class="sxs-lookup"><span data-stu-id="afad5-115">**To create an alert based on a message number**</span></span>  
  
-   [<span data-ttu-id="afad5-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="afad5-116">SQL Server Management Studio</span></span>](create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="afad5-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="afad5-117">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="afad5-118">**Para criar um alerta com base em níveis de severidade**</span><span class="sxs-lookup"><span data-stu-id="afad5-118">**To create an alert based on severity levels**</span></span>  
  
-   [<span data-ttu-id="afad5-119">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="afad5-119">SQL Server Management Studio</span></span>](create-an-alert-using-severity-level.md)  
  
-   [<span data-ttu-id="afad5-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="afad5-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="afad5-121">**Para definir uma resposta a um alerta**</span><span class="sxs-lookup"><span data-stu-id="afad5-121">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="afad5-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="afad5-122">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="afad5-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="afad5-123">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
 <span data-ttu-id="afad5-124">**Para criar uma mensagem de erro de evento definida pelo usuário**</span><span class="sxs-lookup"><span data-stu-id="afad5-124">**To create a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="afad5-125">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="afad5-125">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql)  
  
 <span data-ttu-id="afad5-126">**Para modificar uma mensagem de erro de evento definida pelo usuário**</span><span class="sxs-lookup"><span data-stu-id="afad5-126">**To modify a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="afad5-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="afad5-127">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
 <span data-ttu-id="afad5-128">**Para excluir uma mensagem de erro de evento definida pelo usuário**</span><span class="sxs-lookup"><span data-stu-id="afad5-128">**To delete a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="afad5-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="afad5-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropmessage-transact-sql)  
  
 <span data-ttu-id="afad5-130">**Para desabilitar ou reativar um alerta**</span><span class="sxs-lookup"><span data-stu-id="afad5-130">**To disable or reactivate an alert**</span></span>  
  
-   [<span data-ttu-id="afad5-131">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="afad5-131">SQL Server Management Studio</span></span>](disable-or-reactivate-an-alert.md)  
  
-   [<span data-ttu-id="afad5-132">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="afad5-132">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="afad5-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="afad5-133">See Also</span></span>  
 [<span data-ttu-id="afad5-134">&#41;&#40;Transact-SQL de sp_update_alert</span><span class="sxs-lookup"><span data-stu-id="afad5-134">sp_update_alert &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
  
