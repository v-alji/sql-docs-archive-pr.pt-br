---
title: MSSQLSERVER_9001 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9001 (Database Engine error)
ms.assetid: a54de936-90c6-4845-aa96-29d32f154601
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e61894d0d071fbdb36dcfb77895c46c61d0bbd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682254"
---
# <a name="mssqlserver_9001"></a><span data-ttu-id="4950c-102">MSSQLSERVER_9001</span><span class="sxs-lookup"><span data-stu-id="4950c-102">MSSQLSERVER_9001</span></span>
    
## <a name="details"></a><span data-ttu-id="4950c-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4950c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4950c-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="4950c-104">Product Name</span></span>|<span data-ttu-id="4950c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4950c-105">SQL Server</span></span>|  
|<span data-ttu-id="4950c-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4950c-106">Event ID</span></span>|<span data-ttu-id="4950c-107">9001</span><span class="sxs-lookup"><span data-stu-id="4950c-107">9001</span></span>|  
|<span data-ttu-id="4950c-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="4950c-108">Event Source</span></span>|<span data-ttu-id="4950c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4950c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4950c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4950c-110">Component</span></span>|<span data-ttu-id="4950c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4950c-111">SQLEngine</span></span>|  
|<span data-ttu-id="4950c-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="4950c-112">Symbolic Name</span></span>|<span data-ttu-id="4950c-113">LOG_NOT_AVAIL</span><span class="sxs-lookup"><span data-stu-id="4950c-113">LOG_NOT_AVAIL</span></span>|  
|<span data-ttu-id="4950c-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="4950c-114">Message Text</span></span>|<span data-ttu-id="4950c-115">O log para o banco de dados '%.\*ls' não está disponível.</span><span class="sxs-lookup"><span data-stu-id="4950c-115">The log for database '%.\*ls' is not available.</span></span> <span data-ttu-id="4950c-116">Verifique o log de eventos para obter as mensagens de erro relacionadas.</span><span class="sxs-lookup"><span data-stu-id="4950c-116">Check the event log for related error messages.</span></span> <span data-ttu-id="4950c-117">Resolva todos os erros e reinicie o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4950c-117">Resolve any errors and restart the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4950c-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="4950c-118">Explanation</span></span>  
 <span data-ttu-id="4950c-119">O log do banco de dados foi colocado offline.</span><span class="sxs-lookup"><span data-stu-id="4950c-119">The database log was taken offline.</span></span> <span data-ttu-id="4950c-120">Geralmente, isso indica uma falha catastrófica que exige reinicialização do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4950c-120">Usually this signifies a catastrophic failure that requires the database to restart.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4950c-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="4950c-121">User Action</span></span>  
 <span data-ttu-id="4950c-122">Analise os outros erros e reinicie a instância do SQL Server, caso ela ainda não tenha sido reinicializada.</span><span class="sxs-lookup"><span data-stu-id="4950c-122">Diagnose other errors and restart the instance of SQL Server if it has not already restarted itself.</span></span>  
  
  
