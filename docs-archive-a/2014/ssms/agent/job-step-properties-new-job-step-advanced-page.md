---
title: 'Propriedades da etapa de trabalho: nova etapa de trabalho (página avançado) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepadvanced.f1
ms.assetid: bdecfd4f-bcd8-4ba2-8ada-fbb636314f40
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42820ffbdbb89261e839b5d1011f3a91b5841c86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683896"
---
# <a name="job-step-properties-new-job-step-advanced-page"></a><span data-ttu-id="31151-102">Propriedades da Etapa de Trabalho: Nova Etapa de Trabalho (página Avançado)</span><span class="sxs-lookup"><span data-stu-id="31151-102">Job Step Properties: New Job Step (Advanced Page)</span></span>
  <span data-ttu-id="31151-103">Use esta página para exibir e alterar as propriedades de uma [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] etapa de trabalho do Agent.</span><span class="sxs-lookup"><span data-stu-id="31151-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step.</span></span>  
  
## <a name="options"></a><span data-ttu-id="31151-104">Opções</span><span class="sxs-lookup"><span data-stu-id="31151-104">Options</span></span>  
 <span data-ttu-id="31151-105">**Ação ao obter êxito**</span><span class="sxs-lookup"><span data-stu-id="31151-105">**On success action**</span></span>  
 <span data-ttu-id="31151-106">Define a ação que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent executará se a etapa de trabalho obtiver êxito.</span><span class="sxs-lookup"><span data-stu-id="31151-106">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step succeeds.</span></span>  
  
 <span data-ttu-id="31151-107">**Tentativas de repetição**</span><span class="sxs-lookup"><span data-stu-id="31151-107">**Retry attempts**</span></span>  
 <span data-ttu-id="31151-108">Define o número de vezes que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent tentará repetir uma etapa de trabalho que apresentou falha.</span><span class="sxs-lookup"><span data-stu-id="31151-108">Sets the number of times that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent attempts to retry a failed job step.</span></span>  
  
 <span data-ttu-id="31151-109">**Intervalo de repetição (minutos)**</span><span class="sxs-lookup"><span data-stu-id="31151-109">**Retry interval (minutes)**</span></span>  
 <span data-ttu-id="31151-110">Define o tempo que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent esperará entre as tentativas de repetição.</span><span class="sxs-lookup"><span data-stu-id="31151-110">Sets the amount of time for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to wait between retry attempts.</span></span>  
  
 <span data-ttu-id="31151-111">**Ação ao falhar**</span><span class="sxs-lookup"><span data-stu-id="31151-111">**On failure action**</span></span>  
 <span data-ttu-id="31151-112">Define a ação que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent executará se a etapa de trabalho apresentar falha.</span><span class="sxs-lookup"><span data-stu-id="31151-112">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step fails.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="31151-113">Opções para etapas de trabalho Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="31151-113">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="31151-114">**Arquivo de saída**</span><span class="sxs-lookup"><span data-stu-id="31151-114">**Output file**</span></span>  
 <span data-ttu-id="31151-115">Define o arquivo a usar para saída da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-115">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="31151-116">Essa opção só está disponível para os membros da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="31151-116">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="31151-117">**...**</span><span class="sxs-lookup"><span data-stu-id="31151-117">**...**</span></span>  
 <span data-ttu-id="31151-118">Procura o arquivo a usar para saída da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-118">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="31151-119">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="31151-119">**View**</span></span>  
 <span data-ttu-id="31151-120">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , esse botão é desabilitado para exibir arquivos de saída.</span><span class="sxs-lookup"><span data-stu-id="31151-120">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="31151-121">Em vez disso, use o Bloco de Notas para exibir arquivos de saída de etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-121">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="31151-122">**Anexar saída ao arquivo existente**</span><span class="sxs-lookup"><span data-stu-id="31151-122">**Append output to existing file**</span></span>  
 <span data-ttu-id="31151-123">Anexa a saída aos conteúdos existentes no arquivo.</span><span class="sxs-lookup"><span data-stu-id="31151-123">Append output to the existing contents of the file.</span></span> <span data-ttu-id="31151-124">Caso contrário, os conteúdos anteriores do arquivo serão substituídos a cada vez que a etapa de trabalho for executada.</span><span class="sxs-lookup"><span data-stu-id="31151-124">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="31151-125">**Registrar na tabela**</span><span class="sxs-lookup"><span data-stu-id="31151-125">**Log to table**</span></span>  
 <span data-ttu-id="31151-126">Registra a saída da etapa de trabalho na tabela **sysjobstepslogs** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="31151-126">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="31151-127">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="31151-127">**View**</span></span>  
 <span data-ttu-id="31151-128">Depois de a etapa de trabalho ter sido executada pelo menos uma vez, clique em **Exibir** para exibir sua saída na tabela.</span><span class="sxs-lookup"><span data-stu-id="31151-128">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="31151-129">**Anexar saída à entrada existente na tabela**</span><span class="sxs-lookup"><span data-stu-id="31151-129">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="31151-130">Anexa a saída aos conteúdos existentes na tabela.</span><span class="sxs-lookup"><span data-stu-id="31151-130">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="31151-131">Caso contrário, os conteúdos anteriores da tabela serão substituídos a cada vez que a etapa de trabalho for executada.</span><span class="sxs-lookup"><span data-stu-id="31151-131">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="31151-132">**Incluir saída da etapa no histórico**</span><span class="sxs-lookup"><span data-stu-id="31151-132">**Include step output in history**</span></span>  
 <span data-ttu-id="31151-133">Selecione esta opção para incluir a saída da etapa de trabalho no histórico de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-133">Select this option to include output from the job step in the job history.</span></span>  
  
 <span data-ttu-id="31151-134">**Executar como usuário**</span><span class="sxs-lookup"><span data-stu-id="31151-134">**Run as user**</span></span>  
 <span data-ttu-id="31151-135">Se você for um membro da função de servidor fixa **sysadmin** , poderá selecionar outro logon do SQL para executar essa etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-135">If you are a member of the **sysadmin** fixed server role, you can select another SQL login to run this job step.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="31151-136">Opções para etapas de trabalho do sistema operacional (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="31151-136">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="31151-137">**Arquivo de saída**</span><span class="sxs-lookup"><span data-stu-id="31151-137">**Output file**</span></span>  
 <span data-ttu-id="31151-138">Define o arquivo a usar para saída da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-138">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="31151-139">**...**</span><span class="sxs-lookup"><span data-stu-id="31151-139">**...**</span></span>  
 <span data-ttu-id="31151-140">Procura o arquivo a usar para saída da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-140">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="31151-141">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="31151-141">**View**</span></span>  
 <span data-ttu-id="31151-142">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , esse botão é desabilitado para exibir arquivos de saída.</span><span class="sxs-lookup"><span data-stu-id="31151-142">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="31151-143">Em vez disso, use o Bloco de Notas para exibir arquivos de saída de etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-143">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="31151-144">**Anexar saída ao arquivo existente**</span><span class="sxs-lookup"><span data-stu-id="31151-144">**Append output to existing file**</span></span>  
 <span data-ttu-id="31151-145">Anexa a saída da etapa de trabalho aos conteúdos anteriores do arquivo a cada vez que é executada.</span><span class="sxs-lookup"><span data-stu-id="31151-145">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="31151-146">**Registrar na tabela**</span><span class="sxs-lookup"><span data-stu-id="31151-146">**Log to table**</span></span>  
 <span data-ttu-id="31151-147">Registra a saída da etapa de trabalho na tabela **sysjobstepslogs** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="31151-147">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="31151-148">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="31151-148">**View**</span></span>  
 <span data-ttu-id="31151-149">Depois de a etapa de trabalho ter sido executada pelo menos uma vez, clique em **Exibir** para exibir sua saída na tabela.</span><span class="sxs-lookup"><span data-stu-id="31151-149">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="31151-150">**Anexar saída à entrada existente na tabela**</span><span class="sxs-lookup"><span data-stu-id="31151-150">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="31151-151">Anexa a saída aos conteúdos existentes na tabela.</span><span class="sxs-lookup"><span data-stu-id="31151-151">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="31151-152">Caso contrário, os conteúdos anteriores da tabela serão substituídos a cada vez que a etapa de trabalho for executada.</span><span class="sxs-lookup"><span data-stu-id="31151-152">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="31151-153">**Incluir saída da etapa no histórico**</span><span class="sxs-lookup"><span data-stu-id="31151-153">**Include step output in history**</span></span>  
 <span data-ttu-id="31151-154">Selecione esta opção para incluir a saída da etapa de trabalho no histórico de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-154">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="31151-155">Opções para etapas de trabalho do PowerShell</span><span class="sxs-lookup"><span data-stu-id="31151-155">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="31151-156">**Arquivo de saída**</span><span class="sxs-lookup"><span data-stu-id="31151-156">**Output file**</span></span>  
 <span data-ttu-id="31151-157">Define o arquivo a usar para saída da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-157">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="31151-158">**...**</span><span class="sxs-lookup"><span data-stu-id="31151-158">**...**</span></span>  
 <span data-ttu-id="31151-159">Procura o arquivo a usar para saída da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-159">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="31151-160">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="31151-160">**View**</span></span>  
 <span data-ttu-id="31151-161">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , esse botão é desabilitado para exibir arquivos de saída.</span><span class="sxs-lookup"><span data-stu-id="31151-161">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="31151-162">Em vez disso, use o Bloco de Notas para exibir arquivos de saída de etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-162">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="31151-163">**Anexar saída ao arquivo existente**</span><span class="sxs-lookup"><span data-stu-id="31151-163">**Append output to existing file**</span></span>  
 <span data-ttu-id="31151-164">Anexa a saída da etapa de trabalho aos conteúdos anteriores do arquivo a cada vez que é executada.</span><span class="sxs-lookup"><span data-stu-id="31151-164">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="31151-165">**Registrar na tabela**</span><span class="sxs-lookup"><span data-stu-id="31151-165">**Log to table**</span></span>  
 <span data-ttu-id="31151-166">Registra a saída da etapa de trabalho na tabela **sysjobstepslogs** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="31151-166">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="31151-167">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="31151-167">**View**</span></span>  
 <span data-ttu-id="31151-168">Depois de a etapa de trabalho ter sido executada pelo menos uma vez, clique em **Exibir** para exibir sua saída na tabela.</span><span class="sxs-lookup"><span data-stu-id="31151-168">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="31151-169">**Anexar saída à entrada existente na tabela**</span><span class="sxs-lookup"><span data-stu-id="31151-169">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="31151-170">Anexa a saída aos conteúdos existentes na tabela.</span><span class="sxs-lookup"><span data-stu-id="31151-170">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="31151-171">Caso contrário, os conteúdos anteriores da tabela serão substituídos a cada vez que a etapa de trabalho for executada.</span><span class="sxs-lookup"><span data-stu-id="31151-171">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="31151-172">**Incluir saída da etapa no histórico**</span><span class="sxs-lookup"><span data-stu-id="31151-172">**Include step output in history**</span></span>  
 <span data-ttu-id="31151-173">Selecione esta opção para incluir a saída da etapa de trabalho no histórico de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-173">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="31151-174">Opções para etapas de trabalho do Replication Queue Reader</span><span class="sxs-lookup"><span data-stu-id="31151-174">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="31151-175">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="31151-175">**Server**</span></span>  
 <span data-ttu-id="31151-176">Define o servidor a usar para uma etapa de trabalho do Replication Queue Reader.</span><span class="sxs-lookup"><span data-stu-id="31151-176">Sets the server to use for a replication queue reader job step.</span></span>  
  
 <span data-ttu-id="31151-177">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="31151-177">**Database**</span></span>  
 <span data-ttu-id="31151-178">Define o banco de dados a usar para uma etapa de trabalho do Replication Queue Reader.</span><span class="sxs-lookup"><span data-stu-id="31151-178">Sets the database to use for a replication queue reader job step.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-job-steps"></a><span data-ttu-id="31151-179">Opções para etapas de trabalho do SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="31151-179">Options for SQL Server Analysis Services Job Steps</span></span>  
 <span data-ttu-id="31151-180">**Arquivo de saída**</span><span class="sxs-lookup"><span data-stu-id="31151-180">**Output file**</span></span>  
 <span data-ttu-id="31151-181">Define o arquivo a usar para saída da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-181">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="31151-182">Essa opção só está disponível para os membros da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="31151-182">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="31151-183">**...**</span><span class="sxs-lookup"><span data-stu-id="31151-183">**...**</span></span>  
 <span data-ttu-id="31151-184">Procura o arquivo a usar para saída da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-184">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="31151-185">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="31151-185">**View**</span></span>  
 <span data-ttu-id="31151-186">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], esse botão está desabilitado para exibir os arquivos de saída.</span><span class="sxs-lookup"><span data-stu-id="31151-186">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="31151-187">Em vez disso, use o Bloco de Notas para exibir arquivos de saída de etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-187">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="31151-188">**Anexar saída ao arquivo existente**</span><span class="sxs-lookup"><span data-stu-id="31151-188">**Append output to existing file**</span></span>  
 <span data-ttu-id="31151-189">Anexa a saída aos conteúdos existentes no arquivo.</span><span class="sxs-lookup"><span data-stu-id="31151-189">Append output to the existing contents of the file.</span></span> <span data-ttu-id="31151-190">Caso contrário, os conteúdos anteriores do arquivo serão substituídos a cada vez que a etapa de trabalho for executada.</span><span class="sxs-lookup"><span data-stu-id="31151-190">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="31151-191">**Registrar na tabela**</span><span class="sxs-lookup"><span data-stu-id="31151-191">**Log to table**</span></span>  
 <span data-ttu-id="31151-192">Registra a saída da etapa de trabalho na tabela **sysjobstepslogs** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="31151-192">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="31151-193">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="31151-193">**View**</span></span>  
 <span data-ttu-id="31151-194">Depois de a etapa de trabalho ter sido executada pelo menos uma vez, clique em **Exibir** para exibir sua saída na tabela.</span><span class="sxs-lookup"><span data-stu-id="31151-194">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="31151-195">**Anexar saída à entrada existente na tabela**</span><span class="sxs-lookup"><span data-stu-id="31151-195">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="31151-196">Anexa a saída aos conteúdos existentes na tabela.</span><span class="sxs-lookup"><span data-stu-id="31151-196">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="31151-197">Caso contrário, os conteúdos anteriores da tabela serão substituídos a cada vez que a etapa de trabalho for executada.</span><span class="sxs-lookup"><span data-stu-id="31151-197">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="31151-198">**Incluir saída da etapa no histórico**</span><span class="sxs-lookup"><span data-stu-id="31151-198">**Include step output in history**</span></span>  
 <span data-ttu-id="31151-199">Selecione esta opção para incluir a saída da etapa de trabalho no histórico de trabalho.</span><span class="sxs-lookup"><span data-stu-id="31151-199">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31151-200">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31151-200">See Also</span></span>  
 [<span data-ttu-id="31151-201">Gerenciar etapas de trabalho</span><span class="sxs-lookup"><span data-stu-id="31151-201">Manage Job Steps</span></span>](manage-job-steps.md)  
  
  
