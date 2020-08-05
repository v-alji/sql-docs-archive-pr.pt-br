---
title: MSSQLSERVER_3271 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3271 (Database Engine error)
ms.assetid: 21b8de4b-6624-4163-9561-1a6cc8fe3d51
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56bdb5875dbba3fbe5037a308d713170a9b6f9ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573066"
---
# <a name="mssqlserver_3271"></a><span data-ttu-id="9e452-102">MSSQLSERVER_3271</span><span class="sxs-lookup"><span data-stu-id="9e452-102">MSSQLSERVER_3271</span></span>
    
## <a name="details"></a><span data-ttu-id="9e452-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9e452-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e452-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="9e452-104">Product Name</span></span>|<span data-ttu-id="9e452-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e452-105">SQL Server</span></span>|  
|<span data-ttu-id="9e452-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="9e452-106">Event ID</span></span>|<span data-ttu-id="9e452-107">3271</span><span class="sxs-lookup"><span data-stu-id="9e452-107">3271</span></span>|  
|<span data-ttu-id="9e452-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="9e452-108">Event Source</span></span>|<span data-ttu-id="9e452-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9e452-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9e452-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9e452-110">Component</span></span>|<span data-ttu-id="9e452-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9e452-111">SQLEngine</span></span>|  
|<span data-ttu-id="9e452-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="9e452-112">Symbolic Name</span></span>|<span data-ttu-id="9e452-113">DMPIO_IO_ERROR</span><span class="sxs-lookup"><span data-stu-id="9e452-113">DMPIO_IO_ERROR</span></span>|  
|<span data-ttu-id="9e452-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="9e452-114">Message Text</span></span>|<span data-ttu-id="9e452-115">Um erro de E/S não recuperável aconteceu no arquivo "%ls": %ls.</span><span class="sxs-lookup"><span data-stu-id="9e452-115">A nonrecoverable I/O error occurred on file "%ls:" %ls.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9e452-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="9e452-116">Explanation</span></span>  
 <span data-ttu-id="9e452-117">Trata-se de um erro geral que ocorre quando o sistema operacional gera um erro ao executar E/S durante uma operação de backup ou restauração.</span><span class="sxs-lookup"><span data-stu-id="9e452-117">This is a general error that occurs when the operating system raises an error while performing I/O during a backup or restore operation.</span></span> <span data-ttu-id="9e452-118">Na maioria das situações, isso ocorre simplesmente porque a mídia de backup está cheia.</span><span class="sxs-lookup"><span data-stu-id="9e452-118">In most situations the cause is simply that the backup medium is full.</span></span>  
  
 <span data-ttu-id="9e452-119">O erro pode incluir um texto adicional do sistema operacional indicando que o disco está cheio.</span><span class="sxs-lookup"><span data-stu-id="9e452-119">The error may include additional text from the operating system indicating that the disk is full.</span></span> <span data-ttu-id="9e452-120">Ao executar uma operação de backup ou restauração com software de terceiros, pode aparecer uma mensagem adicional indicando que o backup falhou.</span><span class="sxs-lookup"><span data-stu-id="9e452-120">When performing a backup or restore operation with third-party backup software an additional message may occur indicating that the backup failed.</span></span> <span data-ttu-id="9e452-121">A mensagem pode ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="9e452-121">The message may look similar to the following text:</span></span>  
  
```  
"2005-08-02 16:05:16.04 spid55 Error: 18210, Severity: 16, State: 1.  
 2005-08-02 16:05:16.04 spid55 BackupVirtualDeviceFile  
::RequestDurableMedia: Flush failure on backup device 'VDINULL'.   
Operating system error 995(The I/O operation has been aborted because   
of either a thread exit or an application request.)."  
```  
  
 <span data-ttu-id="9e452-122">Isso indica que o software de backup solicitou a finalização do processo de backup ou restauração.</span><span class="sxs-lookup"><span data-stu-id="9e452-122">This is an indication that the backup software requested a termination of the backup or restore operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9e452-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="9e452-123">User Action</span></span>  
 <span data-ttu-id="9e452-124">Execute as seguintes tarefas, conforme apropriado:</span><span class="sxs-lookup"><span data-stu-id="9e452-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="9e452-125">Analise as mensagens de erro do sistema e as mensagens de erro do SQL Server que ocorreram antes desse processo para identificar a causa da falha.</span><span class="sxs-lookup"><span data-stu-id="9e452-125">Review the underlying system error messages and SQL Server error messages preceding this one to identify the cause of the failure.</span></span>  
  
-   <span data-ttu-id="9e452-126">Verifique se a mídia de backup e restauração tem espaço suficiente.</span><span class="sxs-lookup"><span data-stu-id="9e452-126">Ensure that the backup and restore medium has sufficient space.</span></span>  
  
-   <span data-ttu-id="9e452-127">Corrija qualquer erro gerado pelo software de backup e restauração de terceiros.</span><span class="sxs-lookup"><span data-stu-id="9e452-127">Correct any errors raised by third-party backup and restore software.</span></span>  
  
  
