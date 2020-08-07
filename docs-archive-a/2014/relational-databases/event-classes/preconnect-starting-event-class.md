---
title: Classe de evento PreConnect:Starting | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- PreConnect:Starting Event Class
ms.assetid: d43ed0ad-3dbd-42e0-9cef-8320b8d87497
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b642d369c73cc144af31f835786613766045f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575813"
---
# <a name="preconnectstarting-event-class"></a><span data-ttu-id="01624-102">Classe de evento PreConnect:Starting</span><span class="sxs-lookup"><span data-stu-id="01624-102">PreConnect:Starting Event Class</span></span>
  <span data-ttu-id="01624-103">A classe de evento PreConnect:Starting indica quando um gatilho LOGON ou a função classificador do Administrador de Recursos inicia a execução.</span><span class="sxs-lookup"><span data-stu-id="01624-103">The PreConnect:Starting event class indicates when a LOGON trigger or the Resource Governor classifier function starts execution.</span></span>  
  
## <a name="preconnectstarting-event-class-data-columns"></a><span data-ttu-id="01624-104">Colunas de dados da classe de evento PreConnect:Starting</span><span class="sxs-lookup"><span data-stu-id="01624-104">PreConnect:Starting Event Class Data Columns</span></span>  
  
|<span data-ttu-id="01624-105">Nome da coluna de dados</span><span class="sxs-lookup"><span data-stu-id="01624-105">Data column name</span></span>|<span data-ttu-id="01624-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="01624-106">Data type</span></span>|<span data-ttu-id="01624-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="01624-107">Description</span></span>|<span data-ttu-id="01624-108">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="01624-108">Column ID</span></span>|<span data-ttu-id="01624-109">Filtrável</span><span class="sxs-lookup"><span data-stu-id="01624-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="01624-110">EventClass</span><span class="sxs-lookup"><span data-stu-id="01624-110">EventClass</span></span>|`int`|<span data-ttu-id="01624-111">215</span><span class="sxs-lookup"><span data-stu-id="01624-111">215</span></span>|<span data-ttu-id="01624-112">27</span><span class="sxs-lookup"><span data-stu-id="01624-112">27</span></span>|<span data-ttu-id="01624-113">Não</span><span class="sxs-lookup"><span data-stu-id="01624-113">No</span></span>|  
|<span data-ttu-id="01624-114">SPID</span><span class="sxs-lookup"><span data-stu-id="01624-114">SPID</span></span>|`int`|<span data-ttu-id="01624-115">O ID de processo de servidor que dispara este evento.</span><span class="sxs-lookup"><span data-stu-id="01624-115">The ID of server process that fires this event.</span></span>|<span data-ttu-id="01624-116">12</span><span class="sxs-lookup"><span data-stu-id="01624-116">12</span></span>|<span data-ttu-id="01624-117">Sim</span><span class="sxs-lookup"><span data-stu-id="01624-117">Yes</span></span>|  
|<span data-ttu-id="01624-118">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="01624-118">EventSubClass</span></span>|`int`|<span data-ttu-id="01624-119">1 para a função de classificador definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="01624-119">1 for the user-defined classifier function.</span></span>|<span data-ttu-id="01624-120">21</span><span class="sxs-lookup"><span data-stu-id="01624-120">21</span></span>|<span data-ttu-id="01624-121">Sim</span><span class="sxs-lookup"><span data-stu-id="01624-121">Yes</span></span>|  
|<span data-ttu-id="01624-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="01624-122">StartTime</span></span>|`datetime`|<span data-ttu-id="01624-123">A hora que inicia a função de classificador definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="01624-123">The time when the user-defined classifier function starts.</span></span>|<span data-ttu-id="01624-124">14</span><span class="sxs-lookup"><span data-stu-id="01624-124">14</span></span>|<span data-ttu-id="01624-125">Sim</span><span class="sxs-lookup"><span data-stu-id="01624-125">Yes</span></span>|  
|<span data-ttu-id="01624-126">ObjectID</span><span class="sxs-lookup"><span data-stu-id="01624-126">ObjectID</span></span>|`int`|<span data-ttu-id="01624-127">A ID do objeto do classificador definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="01624-127">The ID of the user-defined classifier object.</span></span>|<span data-ttu-id="01624-128">22</span><span class="sxs-lookup"><span data-stu-id="01624-128">22</span></span>|<span data-ttu-id="01624-129">Sim</span><span class="sxs-lookup"><span data-stu-id="01624-129">Yes</span></span>|  
|<span data-ttu-id="01624-130">ObjectName</span><span class="sxs-lookup"><span data-stu-id="01624-130">ObjectName</span></span>|`nvarchar(256)`|<span data-ttu-id="01624-131">O nome de duas partes da função de classificador definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="01624-131">The two-part name of the classifier user-defined function.</span></span> <span data-ttu-id="01624-132">Por exemplo, dbo.classifier.</span><span class="sxs-lookup"><span data-stu-id="01624-132">For example, dbo.classifier.</span></span>|<span data-ttu-id="01624-133">34</span><span class="sxs-lookup"><span data-stu-id="01624-133">34</span></span>|<span data-ttu-id="01624-134">Sim</span><span class="sxs-lookup"><span data-stu-id="01624-134">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01624-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="01624-135">See Also</span></span>  
 <span data-ttu-id="01624-136">[Eventos estendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="01624-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="01624-137">[Classe de evento PreConnect: Completed](preconnect-completed-event-class.md) </span><span class="sxs-lookup"><span data-stu-id="01624-137">[PreConnect:Completed Event Class](preconnect-completed-event-class.md) </span></span>  
 [<span data-ttu-id="01624-138">Resource Governor</span><span class="sxs-lookup"><span data-stu-id="01624-138">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
