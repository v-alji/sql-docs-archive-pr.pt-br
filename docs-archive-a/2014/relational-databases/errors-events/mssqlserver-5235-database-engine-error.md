---
title: MSSQLSERVER_5235 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5235 (Database Engine error)
ms.assetid: 1aa7e6a5-7ccb-43c8-a1fd-d50e92e0a798
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 42c807944d7506a6a118de97ccd8c2c488942c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684762"
---
# <a name="mssqlserver_5235"></a><span data-ttu-id="3303f-102">MSSQLSERVER_5235</span><span class="sxs-lookup"><span data-stu-id="3303f-102">MSSQLSERVER_5235</span></span>
    
## <a name="details"></a><span data-ttu-id="3303f-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3303f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3303f-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="3303f-104">Product Name</span></span>|<span data-ttu-id="3303f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3303f-105">SQL Server</span></span>|  
|<span data-ttu-id="3303f-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3303f-106">Event ID</span></span>|<span data-ttu-id="3303f-107">5235</span><span class="sxs-lookup"><span data-stu-id="3303f-107">5235</span></span>|  
|<span data-ttu-id="3303f-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="3303f-108">Event Source</span></span>|<span data-ttu-id="3303f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3303f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3303f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3303f-110">Component</span></span>|<span data-ttu-id="3303f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3303f-111">SQLEngine</span></span>|  
|<span data-ttu-id="3303f-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="3303f-112">Symbolic Name</span></span>|<span data-ttu-id="3303f-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span><span class="sxs-lookup"><span data-stu-id="3303f-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span></span>|  
|<span data-ttu-id="3303f-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="3303f-114">Message Text</span></span>|<span data-ttu-id="3303f-115">[EMERGENCY] DBCC DBCC_COMMAND_DETAILS executado por USER_NAME foi encerrado de forma anormal devido ao estado de erro ERROR_STATE.</span><span class="sxs-lookup"><span data-stu-id="3303f-115">[EMERGENCY] DBCC DBCC_COMMAND_DETAILS executed by USER_NAME terminated abnormally due to error state ERROR_STATE.</span></span> <span data-ttu-id="3303f-116">Tempo decorrido: HOURS horas MINUTES minutos SECONDS segundos.</span><span class="sxs-lookup"><span data-stu-id="3303f-116">Elapsed time: HOURS hours MINUTES minutes SECONDS seconds.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3303f-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="3303f-117">Explanation</span></span>  
 <span data-ttu-id="3303f-118">Essa é a mensagem de resumo que o DBCC grava no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando ocorre um encerramento inesperado durante a execução do comando.</span><span class="sxs-lookup"><span data-stu-id="3303f-118">This is the summary message that DBCC prints to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log when an unexpected termination occurs while the command is running.</span></span> <span data-ttu-id="3303f-119">O estado de erro informado na mensagem define o tipo de encerramento inesperado.</span><span class="sxs-lookup"><span data-stu-id="3303f-119">The error state reported in the message defines the type of unexpected termination.</span></span>  
  
 <span data-ttu-id="3303f-120">A tabela a seguir lista e define os estados de erro.</span><span class="sxs-lookup"><span data-stu-id="3303f-120">The following table lists and defines the error states.</span></span>  
  
|<span data-ttu-id="3303f-121">Estado de erro</span><span class="sxs-lookup"><span data-stu-id="3303f-121">Error state</span></span>|<span data-ttu-id="3303f-122">Definição</span><span class="sxs-lookup"><span data-stu-id="3303f-122">Definition</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="3303f-123">Estado 0</span><span class="sxs-lookup"><span data-stu-id="3303f-123">State 0</span></span>|<span data-ttu-id="3303f-124">A instrução foi encerrada devido a um dano fatal nos metadados.</span><span class="sxs-lookup"><span data-stu-id="3303f-124">The statement was terminated because of a fatal metadata corruption.</span></span> <span data-ttu-id="3303f-125">Essa mensagem será acompanhada por uma ou mais ocorrências do erro 8930.</span><span class="sxs-lookup"><span data-stu-id="3303f-125">This message will be accompanied by one or more instances of error 8930.</span></span>|  
|<span data-ttu-id="3303f-126">Estado 1</span><span class="sxs-lookup"><span data-stu-id="3303f-126">State 1</span></span>|<span data-ttu-id="3303f-127">A instrução foi encerrada devido a uma falha de verificação interna.</span><span class="sxs-lookup"><span data-stu-id="3303f-127">The statement was terminated because of an internal check failure.</span></span> <span data-ttu-id="3303f-128">Essa mensagem será acompanhada por uma ou mais ocorrências do erro 8967.</span><span class="sxs-lookup"><span data-stu-id="3303f-128">This message will be accompanied by one or more instances of error 8967.</span></span>|  
|<span data-ttu-id="3303f-129">Estado 2</span><span class="sxs-lookup"><span data-stu-id="3303f-129">State 2</span></span>|<span data-ttu-id="3303f-130">Falha nas verificações básicas de tabelas do sistema do mecanismo de armazenamento principal.</span><span class="sxs-lookup"><span data-stu-id="3303f-130">Basic system table checks of the core storage engine system tables failed.</span></span> <span data-ttu-id="3303f-131">Essa mensagem será acompanhada por uma ou mais ocorrências do erro [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md) ou [7988](mssqlserver-7988-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="3303f-131">This message will be accompanied by one or more instances of error [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md), or [7988](mssqlserver-7988-database-engine-error.md).</span></span>|  
|<span data-ttu-id="3303f-132">Estado 3</span><span class="sxs-lookup"><span data-stu-id="3303f-132">State 3</span></span>|<span data-ttu-id="3303f-133">Ocorreu uma falha no reparo do modo de emergência DBCC porque não foi possível iniciar o banco de dados após a recriação do log de transações.</span><span class="sxs-lookup"><span data-stu-id="3303f-133">DBCC emergency-mode repair failed because the database could not be started after rebuilding the transaction log.</span></span> <span data-ttu-id="3303f-134">Essa mensagem será acompanhada pelo erro 7909.</span><span class="sxs-lookup"><span data-stu-id="3303f-134">This message will be accompanied by error 7909.</span></span>|  
|<span data-ttu-id="3303f-135">Estado 4</span><span class="sxs-lookup"><span data-stu-id="3303f-135">State 4</span></span>|<span data-ttu-id="3303f-136">Ocorreu uma falha de asserção ou uma violação de acesso durante a execução do comando.</span><span class="sxs-lookup"><span data-stu-id="3303f-136">A failed assertion or access violation occurred during the execution of the command.</span></span>|  
|<span data-ttu-id="3303f-137">Estado 5</span><span class="sxs-lookup"><span data-stu-id="3303f-137">State 5</span></span>|<span data-ttu-id="3303f-138">Ocorreu uma falha desconhecida que encerrou o comando DBCC inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="3303f-138">An unknown failure occurred that unexpectedly terminated the DBCC command.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="3303f-139">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="3303f-139">User Action</span></span>  
 <span data-ttu-id="3303f-140">A tabela a seguir descreve a ação do usuário apropriada para o estado de erro especificado.</span><span class="sxs-lookup"><span data-stu-id="3303f-140">The following table provides the user action that is appropriate for the specified error state.</span></span>  
  
|<span data-ttu-id="3303f-141">Estado de erro</span><span class="sxs-lookup"><span data-stu-id="3303f-141">Error state</span></span>|<span data-ttu-id="3303f-142">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="3303f-142">User action</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3303f-143">Estado 0</span><span class="sxs-lookup"><span data-stu-id="3303f-143">State 0</span></span>|<span data-ttu-id="3303f-144">Restaure do backup.</span><span class="sxs-lookup"><span data-stu-id="3303f-144">Restore from backup.</span></span>|  
|<span data-ttu-id="3303f-145">Estado 1</span><span class="sxs-lookup"><span data-stu-id="3303f-145">State 1</span></span>|<span data-ttu-id="3303f-146">Entre em contato com o Suporte e Atendimento ao Cliente [!INCLUDE[msCoName](../../includes/msconame-md.md)] (CSS).</span><span class="sxs-lookup"><span data-stu-id="3303f-146">Contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>|  
|<span data-ttu-id="3303f-147">Estado 2</span><span class="sxs-lookup"><span data-stu-id="3303f-147">State 2</span></span>|<span data-ttu-id="3303f-148">Restaure do backup.</span><span class="sxs-lookup"><span data-stu-id="3303f-148">Restore from backup.</span></span>|  
|<span data-ttu-id="3303f-149">Estado 3</span><span class="sxs-lookup"><span data-stu-id="3303f-149">State 3</span></span>|<span data-ttu-id="3303f-150">Restaure do backup.</span><span class="sxs-lookup"><span data-stu-id="3303f-150">Restore from backup.</span></span>|  
|<span data-ttu-id="3303f-151">Estado 4</span><span class="sxs-lookup"><span data-stu-id="3303f-151">State 4</span></span>|<span data-ttu-id="3303f-152">Entre em contato com o CSS.</span><span class="sxs-lookup"><span data-stu-id="3303f-152">Contact CSS.</span></span>|  
|<span data-ttu-id="3303f-153">Estado 5</span><span class="sxs-lookup"><span data-stu-id="3303f-153">State 5</span></span>|<span data-ttu-id="3303f-154">Execute o comando novamente.</span><span class="sxs-lookup"><span data-stu-id="3303f-154">Run the command again.</span></span> <span data-ttu-id="3303f-155">Se o problema persistir, entre em contato com o CSS.</span><span class="sxs-lookup"><span data-stu-id="3303f-155">If the problem persists, contact CSS.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3303f-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3303f-156">See Also</span></span>  
 [<span data-ttu-id="3303f-157">DBCC &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3303f-157">DBCC &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-transact-sql)  
  
  
