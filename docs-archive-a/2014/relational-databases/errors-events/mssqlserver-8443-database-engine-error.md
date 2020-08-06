---
title: MSSQLSERVER_8443 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8443 (Database Engine error)
ms.assetid: a3541b9c-b1a8-4280-add1-275f08696b62
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae02cc0d9e5661f4069884c22bf6eea0697bd2d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682255"
---
# <a name="mssqlserver_8443"></a><span data-ttu-id="e374b-102">MSSQLSERVER_8443</span><span class="sxs-lookup"><span data-stu-id="e374b-102">MSSQLSERVER_8443</span></span>
    
## <a name="details"></a><span data-ttu-id="e374b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e374b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e374b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="e374b-104">Product Name</span></span>|<span data-ttu-id="e374b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e374b-105">SQL Server</span></span>|  
|<span data-ttu-id="e374b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e374b-106">Event ID</span></span>|<span data-ttu-id="e374b-107">8443</span><span class="sxs-lookup"><span data-stu-id="e374b-107">8443</span></span>|  
|<span data-ttu-id="e374b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="e374b-108">Event Source</span></span>|<span data-ttu-id="e374b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e374b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e374b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e374b-110">Component</span></span>|<span data-ttu-id="e374b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e374b-111">SQLEngine</span></span>|  
|<span data-ttu-id="e374b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="e374b-112">Symbolic Name</span></span>|<span data-ttu-id="e374b-113">SB_DIALOG_WO_CONV_GROUP</span><span class="sxs-lookup"><span data-stu-id="e374b-113">SB_DIALOG_WO_CONV_GROUP</span></span>|  
|<span data-ttu-id="e374b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="e374b-114">Message Text</span></span>|<span data-ttu-id="e374b-115">A conversa com a ID '%.\*ls' e o iniciador %d referencia um grupo de conversa ausente '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="e374b-115">The conversation with ID '%.\*ls' and initiator %d references a missing conversation group '%.\*ls'.</span></span> <span data-ttu-id="e374b-116">Execute DBCC CHECKDB para analisar e reparar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e374b-116">Run DBCC CHECKDB to analyze and repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e374b-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="e374b-117">Explanation</span></span>  
 <span data-ttu-id="e374b-118">A camada de metadados retornou NULL para o grupo de conversa.</span><span class="sxs-lookup"><span data-stu-id="e374b-118">The metadata layer returned NULL for the conversation group.</span></span> <span data-ttu-id="e374b-119">O banco de dados foi corrompido de algum modo.</span><span class="sxs-lookup"><span data-stu-id="e374b-119">The database has been corrupted in some way.</span></span> <span data-ttu-id="e374b-120">Uma possível origem da corrupção é um erro de disco.</span><span class="sxs-lookup"><span data-stu-id="e374b-120">One possible source of corruption is a disk error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e374b-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="e374b-121">User Action</span></span>  
 <span data-ttu-id="e374b-122">Execute DBCC CHECKDB no modo de correção para deixar novamente o banco de dados em um estado consistente.</span><span class="sxs-lookup"><span data-stu-id="e374b-122">Run DBCC CHECKDB in repair mode to bring the database back into a consistent state.</span></span> <span data-ttu-id="e374b-123">É possível excluir mensagens, se necessário, para restaurar a consistência.</span><span class="sxs-lookup"><span data-stu-id="e374b-123">It may delete messages if necessary to restore consistency.</span></span> <span data-ttu-id="e374b-124">Investigue os logs de erros do sistema para saber se o erro foi causado por outra falha no sistema.</span><span class="sxs-lookup"><span data-stu-id="e374b-124">Investigate system error logs to see if this error was caused by another failure in the system.</span></span>  
  
  
