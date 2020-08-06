---
title: Opções de linha de comando da ferramenta de administração (utilitário Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: c01b0ed3-67e4-4561-92d2-a8fbb086aca8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 506be071f44937d82902585e5a0621212083dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574962"
---
# <a name="administration-tool-command-line-options-distributed-replay-utility"></a><span data-ttu-id="242b2-102">Opções de linha de comando da ferramenta de administração (Distributed Replay Utility)</span><span class="sxs-lookup"><span data-stu-id="242b2-102">Administration Tool Command-line Options (Distributed Replay Utility)</span></span>
  <span data-ttu-id="242b2-103">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ferramenta de administração de Distributed Replay, `DReplay.exe` , é uma ferramenta de linha de comando que você pode usar para se comunicar com o Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="242b2-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="242b2-104">Use a ferramenta de administração para iniciar, monitorar e cancelar operações no controlador.</span><span class="sxs-lookup"><span data-stu-id="242b2-104">Use the administration tool to initiate, monitor, and cancel operations on the controller.</span></span>  
  
 <span data-ttu-id="242b2-105">![Ícone de link do tópico](../../database-engine/media/topic-link.gif "Ícone de link do tópico") Para obter mais informações sobre as convenções de sintaxe usadas com a sintaxe da ferramenta de administração, confira [Convenções de sintaxe Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="242b2-105">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="242b2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="242b2-106">Syntax</span></span>  
  
```  
  
      dreplay {preprocess|replay|status|cancel} [options] [-?]}  
  
Usage:  
  
  dreplay preprocess [-mcontroller] -iinput_trace_file  
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]  
  
  dreplay replay [-mcontroller] -dcontroller_working_dir [-o]  
    [-starget_server] -wclients [-cconfig_file]  
    [-fstatus_interval]  
  
  dreplay status [-mcontroller] [-fstatus_interval]  
  
  dreplay cancel [-mcontroller] [-q]   
```  
  
## <a name="remarks"></a><span data-ttu-id="242b2-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="242b2-107">Remarks</span></span>  
 <span data-ttu-id="242b2-108">Você pode emitir as seguintes opções de linha de comando com `DReplay.exe`:</span><span class="sxs-lookup"><span data-stu-id="242b2-108">You can issue the following command-line options with `DReplay.exe`:</span></span>  
  
 <span data-ttu-id="242b2-109">**preprocess**</span><span class="sxs-lookup"><span data-stu-id="242b2-109">**preprocess**</span></span>  
 <span data-ttu-id="242b2-110">Inicia o estágio de pré-processamento.</span><span class="sxs-lookup"><span data-stu-id="242b2-110">Initiates the preprocess stage.</span></span> <span data-ttu-id="242b2-111">O controlador prepara os dados de rastreamento de entrada que você capturou do ambiente de produção para a reprodução contra o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="242b2-111">The controller prepares the input trace data, which you captured from the production environment, for replay against the target server.</span></span>  
  
 <span data-ttu-id="242b2-112">**reproduzir**</span><span class="sxs-lookup"><span data-stu-id="242b2-112">**replay**</span></span>  
 <span data-ttu-id="242b2-113">Inicia o estágio de reprodução do evento.</span><span class="sxs-lookup"><span data-stu-id="242b2-113">Initiates the event replay stage.</span></span> <span data-ttu-id="242b2-114">O controlador despacha dados de reprodução aos clientes especificados, inicia a reprodução distribuída e sincroniza os clientes.</span><span class="sxs-lookup"><span data-stu-id="242b2-114">The controller dispatches replay data to the specified clients, launches the distributed replay, and synchronizes the clients.</span></span> <span data-ttu-id="242b2-115">Opcionalmente, cada cliente selecionado registra a atividade de reprodução e salva arquivos de rastreamento de resultado localmente.</span><span class="sxs-lookup"><span data-stu-id="242b2-115">Optionally, each client that was selected records the replay activity and saves result trace files locally.</span></span>  
  
 <span data-ttu-id="242b2-116">**status**</span><span class="sxs-lookup"><span data-stu-id="242b2-116">**status**</span></span>  
 <span data-ttu-id="242b2-117">Consulta o controlador e exibe o status atual.</span><span class="sxs-lookup"><span data-stu-id="242b2-117">Queries the controller and displays the current status.</span></span>  
  
 <span data-ttu-id="242b2-118">**cancel**</span><span class="sxs-lookup"><span data-stu-id="242b2-118">**cancel**</span></span>  
 <span data-ttu-id="242b2-119">Cancela a operação atual em execução no controlador.</span><span class="sxs-lookup"><span data-stu-id="242b2-119">Cancels the current operation that is running on the controller.</span></span>  
  
 <span data-ttu-id="242b2-120">Para obter informações detalhadas de sintaxe, incluindo argumentos e exemplos de comandos, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="242b2-120">For detailed syntax information that includes the command arguments and examples, see the following topics:</span></span>  
  
-   [<span data-ttu-id="242b2-121">Opção Pré-processamento &#40;Ferramenta de administração de reprodução distribuída&#41;</span><span class="sxs-lookup"><span data-stu-id="242b2-121">Preprocess Option &#40;Distributed Replay Administration Tool&#41;</span></span>](preprocess-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="242b2-122">Opção Reprodução &#40;Ferramenta de administração de reprodução distribuída&#41;</span><span class="sxs-lookup"><span data-stu-id="242b2-122">Replay Option &#40;Distributed Replay Administration Tool&#41;</span></span>](replay-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="242b2-123">Opção Status &#40;Ferramenta de administração de reprodução distribuída&#41;</span><span class="sxs-lookup"><span data-stu-id="242b2-123">Status Option &#40;Distributed Replay Administration Tool&#41;</span></span>](status-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="242b2-124">Opção Cancelamento &#40;Ferramenta de administração de reprodução distribuída&#41;</span><span class="sxs-lookup"><span data-stu-id="242b2-124">Cancel Option &#40;Distributed Replay Administration Tool&#41;</span></span>](cancel-option-distributed-replay-administration-tool.md)  
  
 <span data-ttu-id="242b2-125">Os RPCs são executados novamente como RPCs e não como eventos de idioma.</span><span class="sxs-lookup"><span data-stu-id="242b2-125">RPCs are replayed as RPCs and not as language events.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="242b2-126">Permissões</span><span class="sxs-lookup"><span data-stu-id="242b2-126">Permissions</span></span>  
 <span data-ttu-id="242b2-127">Você deve executar a ferramenta de administração como um usuário interativo, um usuário local ou uma conta de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="242b2-127">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="242b2-128">Para usar uma conta de usuário local, a ferramenta de administração e o controlador devem estar em execução no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="242b2-128">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>  
  
 <span data-ttu-id="242b2-129">Para saber mais, confira [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="242b2-129">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="242b2-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="242b2-130">See Also</span></span>  
 [<span data-ttu-id="242b2-131">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="242b2-131">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)  
  
  
