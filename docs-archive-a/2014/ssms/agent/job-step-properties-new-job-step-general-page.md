---
title: 'Propriedades da etapa de trabalho: nova etapa de trabalho (página Geral) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepgeneral.f1
ms.assetid: 8d1885ba-4386-4528-8f2b-68c16852720c
author: stevestein
ms.author: sstein
ms.openlocfilehash: c76e1ecb69a1475ec102f143a6a1ca34fbf91e3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576113"
---
# <a name="job-step-properties-new-job-step-general-page"></a><span data-ttu-id="a236a-102">Propriedades da Etapa de Trabalho: Nova Etapa de Trabalho (página Geral)</span><span class="sxs-lookup"><span data-stu-id="a236a-102">Job Step Properties: New Job Step (General Page)</span></span>
  <span data-ttu-id="a236a-103">Use esta página para exibir e alterar as propriedades de uma [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] etapa de trabalho do Agent ou para definir uma nova etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a236a-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step, or to define a new job step.</span></span>  
  
 <span data-ttu-id="a236a-104">Para navegar até essa página, no Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , expanda o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, clique com o botão direito do mouse em **Trabalhos**, clique em **Novos Trabalhos**, selecione a página **Etapas** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a236a-104">To navigate to this page, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, click **New Jobs**, select the **Steps** page, and click **New**.</span></span> <span data-ttu-id="a236a-105">Você também pode navegar até essa página. Para isso, clique com o botão direito do mouse em um trabalho no Pesquisador de Objetos, clique em **Propriedades**, selecione a página **Etapas** e clique em **Novo**, **Inserir**ou **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a236a-105">You can also navigate to this page by right-clicking a job in Object Explorer, clicking **Properties**, selecting the **Steps** page, and clicking **New**, **Insert**, or **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a236a-106">Opções</span><span class="sxs-lookup"><span data-stu-id="a236a-106">Options</span></span>  
 <span data-ttu-id="a236a-107">**Nome da etapa**</span><span class="sxs-lookup"><span data-stu-id="a236a-107">**Step name**</span></span>  
 <span data-ttu-id="a236a-108">Defina o nome da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a236a-108">Set the name of the job step.</span></span>  
  
 <span data-ttu-id="a236a-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a236a-109">**Type**</span></span>  
 <span data-ttu-id="a236a-110">Defina o subsistema usado pela etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a236a-110">Set the subsystem that the job step uses.</span></span> <span data-ttu-id="a236a-111">Dependendo do subsistema que você escolher as opções exibidas para definir a etapa de trabalho serão diferentes.</span><span class="sxs-lookup"><span data-stu-id="a236a-111">Based on the subsystem you choose, the options displayed for defining the job step change.</span></span>  
  
 <span data-ttu-id="a236a-112">**Executar como**</span><span class="sxs-lookup"><span data-stu-id="a236a-112">**Run as**</span></span>  
 <span data-ttu-id="a236a-113">Defina a conta proxy para a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a236a-113">Set the proxy account for the job step.</span></span> <span data-ttu-id="a236a-114">Membros da função de servidor fixa sysadmin também podem especificar a **Conta de Serviço do SQL Agent**.</span><span class="sxs-lookup"><span data-stu-id="a236a-114">Members of the sysadmin fixed server role may also specify the **SQL Agent Service Account**.</span></span>  
  
 <span data-ttu-id="a236a-115">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="a236a-115">**Database**</span></span>  
 <span data-ttu-id="a236a-116">Defina o banco de dados no qual a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="a236a-116">Set the database that the job step runs in.</span></span> <span data-ttu-id="a236a-117">Esta opção não está disponível para todos os tipos de etapas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a236a-117">This option is not available for all job step types.</span></span>  
  
 <span data-ttu-id="a236a-118">**Comando**</span><span class="sxs-lookup"><span data-stu-id="a236a-118">**Command**</span></span>  
 <span data-ttu-id="a236a-119">Defina o comando executado pela etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a236a-119">Set the command that the job step runs.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="a236a-120">Opções para etapas de trabalho Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a236a-120">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="a236a-121">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="a236a-121">**Open**</span></span>  
 <span data-ttu-id="a236a-122">Carregue o comando de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a236a-122">Load the command from a file.</span></span>  
  
 <span data-ttu-id="a236a-123">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="a236a-123">**Select All**</span></span>  
 <span data-ttu-id="a236a-124">Selecione o texto do comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-124">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a236a-125">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="a236a-125">**Copy**</span></span>  
 <span data-ttu-id="a236a-126">Copie o texto selecionado para a Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-126">Copy the selected text to the Clipboard.</span></span>  
  
 <span data-ttu-id="a236a-127">**Colar**</span><span class="sxs-lookup"><span data-stu-id="a236a-127">**Paste**</span></span>  
 <span data-ttu-id="a236a-128">Cole o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-128">Paste the contents of the Clipboard.</span></span>  
  
 <span data-ttu-id="a236a-129">**Analisar**</span><span class="sxs-lookup"><span data-stu-id="a236a-129">**Parse**</span></span>  
 <span data-ttu-id="a236a-130">Verifique a sintaxe do comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-130">Check the syntax of the command.</span></span>  
  
## <a name="options-for-activex-script-job-steps"></a><span data-ttu-id="a236a-131">Opções para etapas de trabalho ActiveX Script</span><span class="sxs-lookup"><span data-stu-id="a236a-131">Options for ActiveX Script Job Steps</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a236a-132">O subsistema de script do ActiveX será removido do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent em uma futura versão do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a236a-132">The ActiveX Scripting subsystem will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a236a-133">Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam.</span><span class="sxs-lookup"><span data-stu-id="a236a-133">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="a236a-134">**VBScript**</span><span class="sxs-lookup"><span data-stu-id="a236a-134">**VBScript**</span></span>  
 <span data-ttu-id="a236a-135">Especifique o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic Scripting Edition como a linguagem para a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a236a-135">Specify [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic Scripting Edition as the language for the job steps.</span></span>  
  
 <span data-ttu-id="a236a-136">**JScript**</span><span class="sxs-lookup"><span data-stu-id="a236a-136">**JScript**</span></span>  
 <span data-ttu-id="a236a-137">Especifique JScript como a linguagem para a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a236a-137">Specify JScript as the language for the job steps.</span></span>  
  
 <span data-ttu-id="a236a-138">**Outras**</span><span class="sxs-lookup"><span data-stu-id="a236a-138">**Other**</span></span>  
 <span data-ttu-id="a236a-139">Digite o nome da linguagem para etapas de trabalho escritas em outra linguagem de criação de scripts.</span><span class="sxs-lookup"><span data-stu-id="a236a-139">Type the name of the language for job steps written in another scripting language.</span></span>  
  
 <span data-ttu-id="a236a-140">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="a236a-140">**Open**</span></span>  
 <span data-ttu-id="a236a-141">Carregue o comando de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a236a-141">Load the command from a file.</span></span>  
  
 <span data-ttu-id="a236a-142">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="a236a-142">**Select All**</span></span>  
 <span data-ttu-id="a236a-143">Selecione o texto do comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-143">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a236a-144">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="a236a-144">**Copy**</span></span>  
 <span data-ttu-id="a236a-145">Copie o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-145">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a236a-146">**Colar**</span><span class="sxs-lookup"><span data-stu-id="a236a-146">**Paste**</span></span>  
 <span data-ttu-id="a236a-147">Cole o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-147">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="a236a-148">Opções para etapas de trabalho do sistema operacional (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="a236a-148">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="a236a-149">**Código de saída do processo de um comando bem sucedido**</span><span class="sxs-lookup"><span data-stu-id="a236a-149">**Process exit code of a successful command**</span></span>  
 <span data-ttu-id="a236a-150">Digite o código de saída que o comando retorna para indicar sucesso.</span><span class="sxs-lookup"><span data-stu-id="a236a-150">Type the exit code that the command returns to indicate success.</span></span>  
  
 <span data-ttu-id="a236a-151">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="a236a-151">**Open**</span></span>  
 <span data-ttu-id="a236a-152">Carregue o comando de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a236a-152">Load the command from a file.</span></span>  
  
 <span data-ttu-id="a236a-153">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="a236a-153">**Select All**</span></span>  
 <span data-ttu-id="a236a-154">Selecione o texto do comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-154">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a236a-155">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="a236a-155">**Copy**</span></span>  
 <span data-ttu-id="a236a-156">Copie o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-156">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a236a-157">**Colar**</span><span class="sxs-lookup"><span data-stu-id="a236a-157">**Paste**</span></span>  
 <span data-ttu-id="a236a-158">Cole o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-158">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="a236a-159">Opções para etapas de trabalho do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a236a-159">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="a236a-160">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="a236a-160">**Open**</span></span>  
 <span data-ttu-id="a236a-161">Carregue o script de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a236a-161">Load the script from a file.</span></span>  
  
 <span data-ttu-id="a236a-162">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="a236a-162">**Select All**</span></span>  
 <span data-ttu-id="a236a-163">Selecione o texto do script.</span><span class="sxs-lookup"><span data-stu-id="a236a-163">Select the text of the script.</span></span>  
  
 <span data-ttu-id="a236a-164">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="a236a-164">**Copy**</span></span>  
 <span data-ttu-id="a236a-165">Copie o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-165">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a236a-166">**Colar**</span><span class="sxs-lookup"><span data-stu-id="a236a-166">**Paste**</span></span>  
 <span data-ttu-id="a236a-167">Cole o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-167">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-distributor-job-steps"></a><span data-ttu-id="a236a-168">Opções para etapas de trabalho do Distribuidor de Replicação</span><span class="sxs-lookup"><span data-stu-id="a236a-168">Options for Replication Distributor Job Steps</span></span>  
 <span data-ttu-id="a236a-169">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="a236a-169">**Select All**</span></span>  
 <span data-ttu-id="a236a-170">Selecione o texto do comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-170">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a236a-171">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="a236a-171">**Copy**</span></span>  
 <span data-ttu-id="a236a-172">Copie o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-172">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a236a-173">**Colar**</span><span class="sxs-lookup"><span data-stu-id="a236a-173">**Paste**</span></span>  
 <span data-ttu-id="a236a-174">Cole o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-174">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-merge-job-steps"></a><span data-ttu-id="a236a-175">Opções para etapas de trabalho de Mesclagem de Replicação</span><span class="sxs-lookup"><span data-stu-id="a236a-175">Options for Replication Merge Job Steps</span></span>  
 <span data-ttu-id="a236a-176">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="a236a-176">**Select All**</span></span>  
 <span data-ttu-id="a236a-177">Selecione o texto do comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-177">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a236a-178">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="a236a-178">**Copy**</span></span>  
 <span data-ttu-id="a236a-179">Copie o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-179">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a236a-180">**Colar**</span><span class="sxs-lookup"><span data-stu-id="a236a-180">**Paste**</span></span>  
 <span data-ttu-id="a236a-181">Cole o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-181">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="a236a-182">Opções para etapas de trabalho do Replication Queue Reader</span><span class="sxs-lookup"><span data-stu-id="a236a-182">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="a236a-183">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="a236a-183">**Database**</span></span>  
 <span data-ttu-id="a236a-184">O banco de dados a ser usado para a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a236a-184">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="a236a-185">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="a236a-185">**Select All**</span></span>  
 <span data-ttu-id="a236a-186">Selecione o texto do comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-186">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a236a-187">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="a236a-187">**Copy**</span></span>  
 <span data-ttu-id="a236a-188">Copie o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-188">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a236a-189">**Colar**</span><span class="sxs-lookup"><span data-stu-id="a236a-189">**Paste**</span></span>  
 <span data-ttu-id="a236a-190">Cole o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-190">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-snapshot-job-steps"></a><span data-ttu-id="a236a-191">Opções para etapas de trabalho do instantâneo de replicação</span><span class="sxs-lookup"><span data-stu-id="a236a-191">Options for Replication Snapshot Job Steps</span></span>  
 <span data-ttu-id="a236a-192">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="a236a-192">**Select All**</span></span>  
 <span data-ttu-id="a236a-193">Selecione o texto do comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-193">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a236a-194">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="a236a-194">**Copy**</span></span>  
 <span data-ttu-id="a236a-195">Copie o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-195">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a236a-196">**Colar**</span><span class="sxs-lookup"><span data-stu-id="a236a-196">**Paste**</span></span>  
 <span data-ttu-id="a236a-197">Cole o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-197">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-transaction-log-reader-job-steps"></a><span data-ttu-id="a236a-198">Opções para etapas de trabalho do Leitor do Log de Transações da Replicação</span><span class="sxs-lookup"><span data-stu-id="a236a-198">Options for Replication Transaction-Log Reader Job Steps</span></span>  
 <span data-ttu-id="a236a-199">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="a236a-199">**Select All**</span></span>  
 <span data-ttu-id="a236a-200">Selecione o texto do comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-200">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a236a-201">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="a236a-201">**Copy**</span></span>  
 <span data-ttu-id="a236a-202">Copie o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-202">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a236a-203">**Colar**</span><span class="sxs-lookup"><span data-stu-id="a236a-203">**Paste**</span></span>  
 <span data-ttu-id="a236a-204">Cole o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-204">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-command-job-steps"></a><span data-ttu-id="a236a-205">Opções para etapas de trabalho do comando do SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a236a-205">Options for SQL Server Analysis Services Command Job Steps</span></span>  
 <span data-ttu-id="a236a-206">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="a236a-206">**Server**</span></span>  
 <span data-ttu-id="a236a-207">Selecione o servidor onde a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="a236a-207">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="a236a-208">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="a236a-208">**Open**</span></span>  
 <span data-ttu-id="a236a-209">Carregue o comando de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a236a-209">Load the command from a file.</span></span>  
  
 <span data-ttu-id="a236a-210">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="a236a-210">**Select All**</span></span>  
 <span data-ttu-id="a236a-211">Selecione o texto do comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-211">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a236a-212">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="a236a-212">**Copy**</span></span>  
 <span data-ttu-id="a236a-213">Copie o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-213">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a236a-214">**Colar**</span><span class="sxs-lookup"><span data-stu-id="a236a-214">**Paste**</span></span>  
 <span data-ttu-id="a236a-215">Cole o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-215">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-query-job-steps"></a><span data-ttu-id="a236a-216">Opções para etapas de trabalho da consulta do SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a236a-216">Options for SQL Server Analysis Services Query Job Steps</span></span>  
 <span data-ttu-id="a236a-217">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="a236a-217">**Server**</span></span>  
 <span data-ttu-id="a236a-218">Selecione o servidor onde a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="a236a-218">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="a236a-219">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="a236a-219">**Database**</span></span>  
 <span data-ttu-id="a236a-220">O banco de dados a ser usado para a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a236a-220">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="a236a-221">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="a236a-221">**Open**</span></span>  
 <span data-ttu-id="a236a-222">Carregue o comando de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a236a-222">Load the command from a file.</span></span>  
  
 <span data-ttu-id="a236a-223">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="a236a-223">**Select All**</span></span>  
 <span data-ttu-id="a236a-224">Selecione o texto do comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-224">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a236a-225">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="a236a-225">**Copy**</span></span>  
 <span data-ttu-id="a236a-226">Copie o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-226">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a236a-227">**Colar**</span><span class="sxs-lookup"><span data-stu-id="a236a-227">**Paste**</span></span>  
 <span data-ttu-id="a236a-228">Cole o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a236a-228">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-integration-services-package-execution-job-steps"></a><span data-ttu-id="a236a-229">Opções para etapas de trabalho de execução de pacotes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="a236a-229">Options for Integration Services Package Execution Job Steps</span></span>  
  
### <a name="general-tab"></a><span data-ttu-id="a236a-230">Guia Geral</span><span class="sxs-lookup"><span data-stu-id="a236a-230">General Tab</span></span>  
 <span data-ttu-id="a236a-231">Especifique onde o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) está localizado e qual o método de autenticação a ser usado.</span><span class="sxs-lookup"><span data-stu-id="a236a-231">Specify where the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package is located and what authentication method to use.</span></span> <span data-ttu-id="a236a-232">As seguintes opções estão disponíveis quando você seleciona essa guia.</span><span class="sxs-lookup"><span data-stu-id="a236a-232">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="a236a-233">**Origem do pacote**</span><span class="sxs-lookup"><span data-stu-id="a236a-233">**Package source**</span></span>  
 <span data-ttu-id="a236a-234">Especifique onde o pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] está armazenado.</span><span class="sxs-lookup"><span data-stu-id="a236a-234">Specify where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="a236a-235">Escolha uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="a236a-235">Choose one of the following:</span></span>  
  
-   <span data-ttu-id="a236a-236">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a236a-236">**SQL Server**</span></span>  
  
-   <span data-ttu-id="a236a-237">**Sistema de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="a236a-237">**File system**</span></span>  
  
-   <span data-ttu-id="a236a-238">**Armazenamento de Pacotes SSIS**</span><span class="sxs-lookup"><span data-stu-id="a236a-238">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="a236a-239">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="a236a-239">**Server**</span></span>  
 <span data-ttu-id="a236a-240">Digite o nome do servidor em que o pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] está armazenado.</span><span class="sxs-lookup"><span data-stu-id="a236a-240">Type the server name where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="a236a-241">Essa opção só está disponível quando **SQL Server** ou **Repositório de Pacotes SSIS** está especificado para **Origem do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="a236a-241">This option is only available when **SQL Server** or **SSIS Package Store** is specified for **Package Source**.</span></span>  
  
 <span data-ttu-id="a236a-242">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="a236a-242">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="a236a-243">Logons para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usam a autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="a236a-243">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="a236a-244">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a236a-244">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="a236a-245">Logons para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usam a autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a236a-245">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="a236a-246">Se este método de autenticação for selecionado, digite o **Nome de usuário** e a **Senha**apropriados.</span><span class="sxs-lookup"><span data-stu-id="a236a-246">If this method of authentication is selected, enter the appropriate **User name** and **Password**.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a236a-247">A autenticação é fornecida para fins de compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="a236a-247">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="a236a-248">Para maior segurança, use a autenticação do Windows, se possível.</span><span class="sxs-lookup"><span data-stu-id="a236a-248">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="a236a-249">**Pacote**</span><span class="sxs-lookup"><span data-stu-id="a236a-249">**Package**</span></span>  
 <span data-ttu-id="a236a-250">Digite o local do pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-250">Type the location of the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a236a-251">Para pacotes [!INCLUDE[ssIS](../../includes/ssis-md.md)] protegidos por senha, clique na guia **Configurações** para digitar a senha na caixa de diálogo **Senha do Pacote** .</span><span class="sxs-lookup"><span data-stu-id="a236a-251">For password-protected [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages, click the **Configurations** tab to enter the password in the **Package Password** dialog box.</span></span> <span data-ttu-id="a236a-252">Caso contrário, o trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que executa o pacote protegido por senha falhará.</span><span class="sxs-lookup"><span data-stu-id="a236a-252">Otherwise, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that executes the password-protected package will fail.</span></span>  
  
### <a name="configurations-tab"></a><span data-ttu-id="a236a-253">Guia Configurações</span><span class="sxs-lookup"><span data-stu-id="a236a-253">Configurations Tab</span></span>  
 <span data-ttu-id="a236a-254">Especifique as opções de configuração para o pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a236a-254">Specify configuration options for the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span> <span data-ttu-id="a236a-255">As seguintes opções estão disponíveis quando essa guia é selecionada.</span><span class="sxs-lookup"><span data-stu-id="a236a-255">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="a236a-256">**Arquivos de configuração**</span><span class="sxs-lookup"><span data-stu-id="a236a-256">**Configuration files**</span></span>  
 <span data-ttu-id="a236a-257">Lista os arquivos de configuração para o pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-257">Lists the configuration files for the package.</span></span>  
  
 <span data-ttu-id="a236a-258">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="a236a-258">**Add**</span></span>  
 <span data-ttu-id="a236a-259">Adicione um arquivo de configuração para o pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-259">Add a configuration file for the package.</span></span>  
  
 <span data-ttu-id="a236a-260">**Remover**</span><span class="sxs-lookup"><span data-stu-id="a236a-260">**Remove**</span></span>  
 <span data-ttu-id="a236a-261">Remova um arquivo de configuração para o pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-261">Remove a configuration file for the package.</span></span>  
  
 <span data-ttu-id="a236a-262">**Mover para Cima**</span><span class="sxs-lookup"><span data-stu-id="a236a-262">**Move Up**</span></span>  
 <span data-ttu-id="a236a-263">Mova para cima o arquivo de configuração selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-263">Move the selected configuration file up.</span></span>  
  
 <span data-ttu-id="a236a-264">**Mover para Baixo**</span><span class="sxs-lookup"><span data-stu-id="a236a-264">**Move Down**</span></span>  
 <span data-ttu-id="a236a-265">Mova para baixo o arquivo de configuração selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-265">Move the selected configuration file down.</span></span>  
  
### <a name="command-files-tab"></a><span data-ttu-id="a236a-266">Guia Arquivos de Comando</span><span class="sxs-lookup"><span data-stu-id="a236a-266">Command Files Tab</span></span>  
 <span data-ttu-id="a236a-267">Selecione os arquivos de comando para o pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-267">Select command files for the package.</span></span> <span data-ttu-id="a236a-268">Os arquivos de comando são processados na ordem em que aparecem na lista.</span><span class="sxs-lookup"><span data-stu-id="a236a-268">Command files are processed in the order in which they appear in the list.</span></span> <span data-ttu-id="a236a-269">As seguintes opções estão disponíveis quando você seleciona essa guia.</span><span class="sxs-lookup"><span data-stu-id="a236a-269">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="a236a-270">**Arquivos de comando**</span><span class="sxs-lookup"><span data-stu-id="a236a-270">**Command files**</span></span>  
 <span data-ttu-id="a236a-271">Lista os arquivos de comando para o pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-271">Lists the command files for the package.</span></span>  
  
 <span data-ttu-id="a236a-272">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="a236a-272">**Add**</span></span>  
 <span data-ttu-id="a236a-273">Adicione um arquivo de comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-273">Add a command file.</span></span>  
  
 <span data-ttu-id="a236a-274">**Remover**</span><span class="sxs-lookup"><span data-stu-id="a236a-274">**Remove**</span></span>  
 <span data-ttu-id="a236a-275">Remova o arquivo de comando selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-275">Remove the selected command file.</span></span>  
  
 <span data-ttu-id="a236a-276">**Mover para Cima**</span><span class="sxs-lookup"><span data-stu-id="a236a-276">**Move Up**</span></span>  
 <span data-ttu-id="a236a-277">Mova para cima o arquivo de comando selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-277">Move the selected command file up.</span></span>  
  
 <span data-ttu-id="a236a-278">**Mover para Baixo**</span><span class="sxs-lookup"><span data-stu-id="a236a-278">**Move Down**</span></span>  
 <span data-ttu-id="a236a-279">Mova para baixo o arquivo de comando selecionado.</span><span class="sxs-lookup"><span data-stu-id="a236a-279">Move the selected command file down.</span></span>  
  
### <a name="data-sources-tab"></a><span data-ttu-id="a236a-280">Guia Fontes de Dados</span><span class="sxs-lookup"><span data-stu-id="a236a-280">Data Sources Tab</span></span>  
 <span data-ttu-id="a236a-281">Esta guia exibe as fontes de dados especificadas no pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-281">View the data sources specified in the package on this tab.</span></span>  
  
 <span data-ttu-id="a236a-282">**Gerenciador de Conexões**</span><span class="sxs-lookup"><span data-stu-id="a236a-282">**Connection Manager**</span></span>  
 <span data-ttu-id="a236a-283">Exibe o nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="a236a-283">View the name of the data source.</span></span>  
  
 <span data-ttu-id="a236a-284">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a236a-284">**Description**</span></span>  
 <span data-ttu-id="a236a-285">Exiba a descrição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="a236a-285">View the description of the data source.</span></span>  
  
 <span data-ttu-id="a236a-286">**Cadeia de conexão**</span><span class="sxs-lookup"><span data-stu-id="a236a-286">**Connection String**</span></span>  
 <span data-ttu-id="a236a-287">Exiba a cadeia de conexão para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="a236a-287">View the connection string for the data source.</span></span>  
  
### <a name="execution-options-tab"></a><span data-ttu-id="a236a-288">Guia Opções de Execução</span><span class="sxs-lookup"><span data-stu-id="a236a-288">Execution Options Tab</span></span>  
 <span data-ttu-id="a236a-289">Exiba ou altere as opções de execução para o pacote nesta guia.</span><span class="sxs-lookup"><span data-stu-id="a236a-289">View or change the execution options for the package on this tab.</span></span>  
  
 <span data-ttu-id="a236a-290">**Falha de pacote com avisos de validação**</span><span class="sxs-lookup"><span data-stu-id="a236a-290">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="a236a-291">Selecione essa opção para que a execução do pacote falhe se ocorrerem avisos de validação.</span><span class="sxs-lookup"><span data-stu-id="a236a-291">Select this option for package execution to fail if validation warnings occur.</span></span>  
  
 <span data-ttu-id="a236a-292">**Validar pacote sem executar**</span><span class="sxs-lookup"><span data-stu-id="a236a-292">**Validate package without executing**</span></span>  
 <span data-ttu-id="a236a-293">Selecione esta opção para que a etapa de trabalho valide, mas não execute, o pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-293">Select this option for the job step to validate, but not execute, the package.</span></span>  
  
 <span data-ttu-id="a236a-294">**Executáveis máximos simultâneos**</span><span class="sxs-lookup"><span data-stu-id="a236a-294">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="a236a-295">Número máximo de arquivos executáveis que podem ser executados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="a236a-295">Maximum number of executable files that can run at one time.</span></span>  
  
 <span data-ttu-id="a236a-296">**Ativar pontos de verificação do pacote**</span><span class="sxs-lookup"><span data-stu-id="a236a-296">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="a236a-297">Selecione esta opção para que a etapa de trabalho use pontos de verificação do pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-297">Select this option for the job step to use package checkpoints.</span></span>  
  
 <span data-ttu-id="a236a-298">**Arquivo de ponto de verificação**</span><span class="sxs-lookup"><span data-stu-id="a236a-298">**Checkpoint file**</span></span>  
 <span data-ttu-id="a236a-299">Digite o nome do arquivo do ponto de verificação do pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-299">Type the name of the package checkpoint file.</span></span>  
  
 <span data-ttu-id="a236a-300">**...**</span><span class="sxs-lookup"><span data-stu-id="a236a-300">**...**</span></span>  
 <span data-ttu-id="a236a-301">Procure para localizar o arquivo do ponto de verificação do pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-301">Browse to find the package checkpoint file.</span></span>  
  
 <span data-ttu-id="a236a-302">**Substituir opções de reinicialização**</span><span class="sxs-lookup"><span data-stu-id="a236a-302">**Override restart options**</span></span>  
 <span data-ttu-id="a236a-303">Selecione esta opção para especificar opções de reinício para essa etapa de trabalho que sejam diferentes das opções de reinício especificadas no pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-303">Select this option to specify restart options for this job step that are different from the restart options specified in the package.</span></span>  
  
 <span data-ttu-id="a236a-304">**Opção de reinicialização**</span><span class="sxs-lookup"><span data-stu-id="a236a-304">**Restart option**</span></span>  
 <span data-ttu-id="a236a-305">Selecione a ação a ser tomada quando o pacote reiniciar.</span><span class="sxs-lookup"><span data-stu-id="a236a-305">Select the action to take when the package restarts.</span></span>  
  
### <a name="logging-tab"></a><span data-ttu-id="a236a-306">Guia Log</span><span class="sxs-lookup"><span data-stu-id="a236a-306">Logging Tab</span></span>  
 <span data-ttu-id="a236a-307">Exiba ou altere as opções de provedores de log para o pacote nesta guia.</span><span class="sxs-lookup"><span data-stu-id="a236a-307">View or change the log providers for the package on this tab.</span></span>  
  
 <span data-ttu-id="a236a-308">**Provedor de log**</span><span class="sxs-lookup"><span data-stu-id="a236a-308">**Log Provider**</span></span>  
 <span data-ttu-id="a236a-309">Selecione o ClassID para o provedor de log.</span><span class="sxs-lookup"><span data-stu-id="a236a-309">Select the ClassID for the log provider.</span></span>  
  
 <span data-ttu-id="a236a-310">**Cadeia de Caracteres de Configuração**</span><span class="sxs-lookup"><span data-stu-id="a236a-310">**Configuration String**</span></span>  
 <span data-ttu-id="a236a-311">Digite a cadeia de caracteres de configuração para o provedor de log.</span><span class="sxs-lookup"><span data-stu-id="a236a-311">Type the configuration string for the log provider.</span></span>  
  
 <span data-ttu-id="a236a-312">**Remover**</span><span class="sxs-lookup"><span data-stu-id="a236a-312">**Remove**</span></span>  
 <span data-ttu-id="a236a-313">Remova o provedor de log.</span><span class="sxs-lookup"><span data-stu-id="a236a-313">Removes the log provider.</span></span>  
  
### <a name="set-values-tab"></a><span data-ttu-id="a236a-314">Guia Definir Valores</span><span class="sxs-lookup"><span data-stu-id="a236a-314">Set Values Tab</span></span>  
 <span data-ttu-id="a236a-315">Exiba ou altere os valores de propriedade para o pacote nesta guia.</span><span class="sxs-lookup"><span data-stu-id="a236a-315">View or change property values for the package on this tab.</span></span>  
  
 <span data-ttu-id="a236a-316">**Caminho da propriedade**</span><span class="sxs-lookup"><span data-stu-id="a236a-316">**Property path**</span></span>  
 <span data-ttu-id="a236a-317">Exiba ou altere o caminho para a propriedade.</span><span class="sxs-lookup"><span data-stu-id="a236a-317">View or change the path for the property.</span></span>  
  
 <span data-ttu-id="a236a-318">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a236a-318">**Value**</span></span>  
 <span data-ttu-id="a236a-319">Exiba ou altere o valor para a propriedade.</span><span class="sxs-lookup"><span data-stu-id="a236a-319">View or change the value for the property.</span></span>  
  
 <span data-ttu-id="a236a-320">**Remover**</span><span class="sxs-lookup"><span data-stu-id="a236a-320">**Remove**</span></span>  
 <span data-ttu-id="a236a-321">Remova a propriedade.</span><span class="sxs-lookup"><span data-stu-id="a236a-321">Removes the property.</span></span>  
  
### <a name="verification-tab"></a><span data-ttu-id="a236a-322">Guia Verificação</span><span class="sxs-lookup"><span data-stu-id="a236a-322">Verification Tab</span></span>  
 <span data-ttu-id="a236a-323">Selecione as opções de verificação para a etapa de trabalho nesta guia.</span><span class="sxs-lookup"><span data-stu-id="a236a-323">Select the verification options for the job step on this tab.</span></span>  
  
 <span data-ttu-id="a236a-324">**Executar apenas pacotes assinados**</span><span class="sxs-lookup"><span data-stu-id="a236a-324">**Execute only signed packages**</span></span>  
 <span data-ttu-id="a236a-325">Execute apenas pacotes que tenham sido assinados.</span><span class="sxs-lookup"><span data-stu-id="a236a-325">Run only packages that have been signed.</span></span> <span data-ttu-id="a236a-326">Quando esta opção está selecionada, a etapa de trabalho apresentará falha se o pacote não estiver assinado.</span><span class="sxs-lookup"><span data-stu-id="a236a-326">When this option is selected, the job step fails if the package is unsigned.</span></span>  
  
 <span data-ttu-id="a236a-327">**Verificar compilação do pacote**</span><span class="sxs-lookup"><span data-stu-id="a236a-327">**Verify package build**</span></span>  
 <span data-ttu-id="a236a-328">Execute apenas pacotes com um número de construção específico.</span><span class="sxs-lookup"><span data-stu-id="a236a-328">Run only packages with a specific build number.</span></span> <span data-ttu-id="a236a-329">Quando esta opção está selecionada, a etapa de trabalho apresentará falha se o pacote não tiver o número de construção especificado.</span><span class="sxs-lookup"><span data-stu-id="a236a-329">When this option is selected, the job step fails if the package does not have the specified build number.</span></span>  
  
 <span data-ttu-id="a236a-330">**Compilar**</span><span class="sxs-lookup"><span data-stu-id="a236a-330">**Build**</span></span>  
 <span data-ttu-id="a236a-331">Digite o número de construção do pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-331">Type the build number of the package.</span></span>  
  
 <span data-ttu-id="a236a-332">**Verificar ID do pacote**</span><span class="sxs-lookup"><span data-stu-id="a236a-332">**Verify package ID**</span></span>  
 <span data-ttu-id="a236a-333">Execute apenas pacotes com um ID específico.</span><span class="sxs-lookup"><span data-stu-id="a236a-333">Run only packages with a specific ID.</span></span> <span data-ttu-id="a236a-334">Quando esta opção está selecionada, a etapa de trabalho apresentará falha se o pacote não tiver o ID especificado.</span><span class="sxs-lookup"><span data-stu-id="a236a-334">When this option is selected, the job step fails if the package does not have the specified ID.</span></span>  
  
 <span data-ttu-id="a236a-335">**ID do Pacote**</span><span class="sxs-lookup"><span data-stu-id="a236a-335">**Package ID**</span></span>  
 <span data-ttu-id="a236a-336">Digite o ID do pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-336">Type the package ID.</span></span>  
  
 <span data-ttu-id="a236a-337">**Verificar ID da versão**</span><span class="sxs-lookup"><span data-stu-id="a236a-337">**Verify version ID**</span></span>  
 <span data-ttu-id="a236a-338">Execute apenas pacotes com uma ID de versão específica.</span><span class="sxs-lookup"><span data-stu-id="a236a-338">Run only packages with a specific version ID.</span></span> <span data-ttu-id="a236a-339">Quando esta opção está selecionada, a etapa de trabalho apresentará falha se o pacote não tiver a ID da versão especificada.</span><span class="sxs-lookup"><span data-stu-id="a236a-339">When this option is selected, the job step fails if the package does not have the specified version ID.</span></span>  
  
 <span data-ttu-id="a236a-340">**ID da Versão**</span><span class="sxs-lookup"><span data-stu-id="a236a-340">**Version ID**</span></span>  
 <span data-ttu-id="a236a-341">Digite o ID da versão.</span><span class="sxs-lookup"><span data-stu-id="a236a-341">Type the version ID.</span></span>  
  
### <a name="command-line-tab"></a><span data-ttu-id="a236a-342">Guia Linha de Comando</span><span class="sxs-lookup"><span data-stu-id="a236a-342">Command Line Tab</span></span>  
 <span data-ttu-id="a236a-343">Especifique as opções de linha de comando para o pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-343">Specify command-line options for the package.</span></span> <span data-ttu-id="a236a-344">As seguintes opções estão disponíveis quando essa guia é selecionada.</span><span class="sxs-lookup"><span data-stu-id="a236a-344">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="a236a-345">**Restaurar as opções originais**</span><span class="sxs-lookup"><span data-stu-id="a236a-345">**Restore the original options**</span></span>  
 <span data-ttu-id="a236a-346">Use o conjunto de opções de linha de comando nesta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a236a-346">Use the command-line options set in this dialog.</span></span>  
  
 <span data-ttu-id="a236a-347">**Editar a linha de comando manualmente**</span><span class="sxs-lookup"><span data-stu-id="a236a-347">**Edit the command line manually**</span></span>  
 <span data-ttu-id="a236a-348">Especifique opções na janela de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="a236a-348">Specify options in the command-line window.</span></span>  
  
 <span data-ttu-id="a236a-349">**Linha de comando**</span><span class="sxs-lookup"><span data-stu-id="a236a-349">**Command line**</span></span>  
 <span data-ttu-id="a236a-350">Digite as opções de linha de comando a usar para o pacote.</span><span class="sxs-lookup"><span data-stu-id="a236a-350">Type the command line options to use for this package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a236a-351">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a236a-351">See Also</span></span>  
 <span data-ttu-id="a236a-352">[Gerenciar etapas de trabalho](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="a236a-352">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="a236a-353">[SQL Server Agent trabalhos para pacotes](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span><span class="sxs-lookup"><span data-stu-id="a236a-353">[SQL Server Agent Jobs for Packages](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span></span>  
 [<span data-ttu-id="a236a-354">Administração do agente de replicação</span><span class="sxs-lookup"><span data-stu-id="a236a-354">Replication Agent Administration</span></span>](../../relational-databases/replication/agents/replication-agent-administration.md)  
  
  
