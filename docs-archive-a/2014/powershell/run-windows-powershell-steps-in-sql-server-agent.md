---
title: Executar etapas do Windows PowerShell no SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f25f7549-c9b3-4618-85f2-c9a08adbe0e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8c100e2eaf1f9b706087bd991fbc268540c29a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573148"
---
# <a name="run-windows-powershell-steps-in-sql-server-agent"></a><span data-ttu-id="7eb72-102">Executar etapas do Windows PowerShell no SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="7eb72-102">Run Windows PowerShell Steps in SQL Server Agent</span></span>
  <span data-ttu-id="7eb72-103">Use o SQL Server Agent para executar scripts do SQL Server PowerShell nas horas agendadas.</span><span class="sxs-lookup"><span data-stu-id="7eb72-103">Use SQL Server Agent to run SQL Server PowerShell scripts at schedule times.</span></span>  
  
1.  <span data-ttu-id="7eb72-104">**Antes de começar:**  [Limitações e restrições](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="7eb72-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="7eb72-105">**Para executar o PowerShell no SQL Server Agent, usando:**  [Etapa de trabalho do PowerShell](#PShellJob), [Etapa de trabalho de prompt de comando](#CmdExecJob)</span><span class="sxs-lookup"><span data-stu-id="7eb72-105">**To run PowerShell from SQL Server Agent, using:**  [PowerShell Job Step](#PShellJob), [Command Prompt Job Step](#CmdExecJob)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="7eb72-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7eb72-106">Before You Begin</span></span>  
 <span data-ttu-id="7eb72-107">Existem vários tipos de etapas de trabalho do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="7eb72-107">There are several types of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="7eb72-108">Cada tipo está associado a um subsistema que implementa um ambiente específico, como um agente de replicação ou ambiente de prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="7eb72-108">Each type is associated with a subsystem that implements a specific environment, such as a replication agent or command prompt environment.</span></span> <span data-ttu-id="7eb72-109">Você pode codificar os scripts do Windows PowerShell e usar o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent para incluir os scripts em trabalhos que são executados em horários programados ou em resposta a eventos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7eb72-109">You can code Windows PowerShell scripts, and then use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to include the scripts in jobs that run at scheduled times or in response to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="7eb72-110">Scripts do Windows PowerShell podem ser executados usando uma etapa de trabalho de prompt de comando ou uma etapa de trabalho do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7eb72-110">Windows PowerShell scripts can be run using either a command prompt job step or a PowerShell job step.</span></span>  
  
1.  <span data-ttu-id="7eb72-111">Use uma etapa de trabalho do PowerShell para fazer com que o subsistema do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent execute o utilitário `sqlps`, que inicia o PowerShell 2.0 e importa o módulo `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="7eb72-111">Use a PowerShell job step to have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent subsystem run the `sqlps` utility, which launches PowerShell 2.0 and imports the `sqlps` module.</span></span>  
  
2.  <span data-ttu-id="7eb72-112">Use uma etapa de trabalho de prompt de comando para executar o PowerShell.exe e especifique um script que importa o módulo `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="7eb72-112">Use a command prompt job step to run PowerShell.exe, and specify a script that imports the `sqlps` module.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="7eb72-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="7eb72-113">Limitations and Restrictions</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7eb72-114">Cada etapa de trabalho do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent que executa o PowerShell com o módulo `sqlps` inicia um processo que consome aproximadamente 20 MB de memória.</span><span class="sxs-lookup"><span data-stu-id="7eb72-114">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job step that runs PowerShell with the `sqlps` module launches a process which consumes approximately 20 MB of memory.</span></span> <span data-ttu-id="7eb72-115">A execução de um grande número de etapas de trabalho concorrentes do Windows PowerShell pode afetar o desempenho de forma negativa.</span><span class="sxs-lookup"><span data-stu-id="7eb72-115">Running large numbers of concurrent Windows PowerShell job steps can adversely impact performance.</span></span>  
  
##  <a name="create-a-powershell-job-step"></a><a name="PShellJob"></a><span data-ttu-id="7eb72-116">Criar uma etapa de trabalho do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7eb72-116">Create a PowerShell Job Step</span></span>  
 <span data-ttu-id="7eb72-117">**Para criar uma etapa de trabalho do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7eb72-117">**To create a PowerShell job step**</span></span>  
  
1.  <span data-ttu-id="7eb72-118">Expanda **SQL Server Agent**, crie um novo trabalho ou clique com o botão direito do mouse em um trabalho existente e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7eb72-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="7eb72-119">Para obter mais informações sobre como criar um trabalho, consulte [Criando trabalhos](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="7eb72-119">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="7eb72-120">Na caixa de diálogo **Propriedades do Trabalho** , clique na página **Etapas** e, em seguida, em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="7eb72-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="7eb72-121">Na caixa de diálogo **Nova Etapa de Trabalho** , digite o **Nome da etapa**de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7eb72-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="7eb72-122">Na lista **Tipo** , clique em **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7eb72-122">In the **Type** list, click **PowerShell**.</span></span>  
  
5.  <span data-ttu-id="7eb72-123">Na lista **Executar como** , selecione a conta proxy com as credenciais que o trabalho usará.</span><span class="sxs-lookup"><span data-stu-id="7eb72-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
6.  <span data-ttu-id="7eb72-124">Na caixa **Comando** , digite a sintaxe do script PowerShell que será executada para a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7eb72-124">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="7eb72-125">Como alternativa, clique em **Abrir** e selecione um arquivo que contenha a sintaxe de script.</span><span class="sxs-lookup"><span data-stu-id="7eb72-125">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
7.  <span data-ttu-id="7eb72-126">Clique na página **Avançado** para definir as seguintes opções de etapa de trabalho: a ação a tomar em caso de êxito ou falha da etapa, quantas vezes o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent deve tentar executar a etapa e com que frequência.</span><span class="sxs-lookup"><span data-stu-id="7eb72-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="create-a-command-prompt-job-step"></a><a name="CmdExecJob"></a><span data-ttu-id="7eb72-127">Criar uma etapa de trabalho de prompt de comando</span><span class="sxs-lookup"><span data-stu-id="7eb72-127">Create a Command Prompt Job Step</span></span>  
 <span data-ttu-id="7eb72-128">**Para criar uma etapa de trabalho CmdExec**</span><span class="sxs-lookup"><span data-stu-id="7eb72-128">**To create a CmdExec job step**</span></span>  
  
1.  <span data-ttu-id="7eb72-129">Expanda **SQL Server Agent**, crie um novo trabalho ou clique com o botão direito do mouse em um trabalho existente e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7eb72-129">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="7eb72-130">Para obter mais informações sobre como criar um trabalho, consulte [Criando trabalhos](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="7eb72-130">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="7eb72-131">Na caixa de diálogo **Propriedades do Trabalho** , clique na página **Etapas** e, em seguida, em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="7eb72-131">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="7eb72-132">Na caixa de diálogo **Nova Etapa de Trabalho** , digite o **Nome da etapa**de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7eb72-132">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="7eb72-133">Na lista **Tipo** , escolha **Sistema operacional (CmdExec)**.</span><span class="sxs-lookup"><span data-stu-id="7eb72-133">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
5.  <span data-ttu-id="7eb72-134">Na lista **Executar como** , selecione a conta proxy com as credenciais que o trabalho usará.</span><span class="sxs-lookup"><span data-stu-id="7eb72-134">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="7eb72-135">Por padrão, etapas de trabalho CmdExec são executadas no contexto da conta do serviço do SQL Server Agent .</span><span class="sxs-lookup"><span data-stu-id="7eb72-135">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
6.  <span data-ttu-id="7eb72-136">Na caixa **Código de saída do processo de um comando bem sucedido** , insira um valor de 0 a 999999.</span><span class="sxs-lookup"><span data-stu-id="7eb72-136">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
7.  <span data-ttu-id="7eb72-137">Na caixa **Comando** , digite powershell.exe com parâmetros que especificam o script do PowerShell a ser executado.</span><span class="sxs-lookup"><span data-stu-id="7eb72-137">In the **Command** box, enter powershell.exe with parameters specifying the PowerShell script to be run.</span></span>  
  
8.  <span data-ttu-id="7eb72-138">Clique na página **Avançado** para definir opções para a etapa de trabalho, como a ação a tomar em caso de êxito ou falha da etapa, quantas vezes o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent deve tentar executar a etapa e o arquivo onde o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent pode gravar a saída da etapa.</span><span class="sxs-lookup"><span data-stu-id="7eb72-138">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="7eb72-139">Só membros da função de servidor fixa **sysadmin** podem gravar a saída de etapas de trabalho em um arquivo do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="7eb72-139">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb72-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7eb72-140">See Also</span></span>  
 [<span data-ttu-id="7eb72-141">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="7eb72-141">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
