---
title: Criar um plano de manutenção (superfície de design do plano de manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Maintenance Plan Design Surface
ms.assetid: 2ef803ee-a9f8-454a-ad63-fedcbe6838d1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77e347720824198ba7d6abaddedd7a581ace98a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576363"
---
# <a name="create-a-maintenance-plan-maintenance-plan-design-surface"></a><span data-ttu-id="d8d44-102">Criar um plano de manutenção (Superfície de Design do Plano de Manutenção)</span><span class="sxs-lookup"><span data-stu-id="d8d44-102">Create a Maintenance Plan (Maintenance Plan Design Surface)</span></span>
  <span data-ttu-id="d8d44-103">Este tópico descreve como criar um plano de manutenção de servidor único ou vários servidores usando a Superfície de Design do Plano de Manutenção no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8d44-103">This topic describes how to create a single server or multiserver maintenance plan using the Maintenance Plan Design Surface in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d8d44-104">Embora o **Assistente de Plano de Manutenção** seja melhor para criar planos de manutenção básicos, a criação de planos usando a superfície de design permite utilizar o fluxo de trabalho aprimorado.</span><span class="sxs-lookup"><span data-stu-id="d8d44-104">While the **Maintenance Plan Wizard** is best for creating basic maintenance plans, creating a plan using the design surface allows you to utilize enhanced workflow.</span></span>  
  
 <span data-ttu-id="d8d44-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="d8d44-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d8d44-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="d8d44-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d8d44-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="d8d44-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d8d44-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="d8d44-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="d8d44-109">Criando um plano de manutenção usando a Superfície de Design do Plano de Manutenção</span><span class="sxs-lookup"><span data-stu-id="d8d44-109">Creating a maintenance plan using the Maintenance Plan Design Surface</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d8d44-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d8d44-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d8d44-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="d8d44-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d8d44-112">Para criar um plano de manutenção multisservidor, é necessário configurar um ambiente multisservidor contendo um servidor mestre e um ou mais servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="d8d44-112">To create a multiserver maintenance plan, a multiserver environment containing one master server and one or more target servers must be configured.</span></span> <span data-ttu-id="d8d44-113">Devem ser criados e mantidos planos de manutenção multisservidor no servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="d8d44-113">Multiserver maintenance plans must be created and maintained on the master server.</span></span> <span data-ttu-id="d8d44-114">Os planos podem ser exibidos, mas não mantidos, nos servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="d8d44-114">These plans can be viewed, but not maintained, on target servers.</span></span>  
  
-   <span data-ttu-id="d8d44-115">Os membros das funções **db_ssisadmin** e **dc_admin** podem elevar seus privilégios para **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-115">Members of the **db_ssisadmin** and **dc_admin** roles may be able to elevate their privileges to **sysadmin**.</span></span> <span data-ttu-id="d8d44-116">Essa elevação de privilégios pode ocorrer porque essas funções podem modificar pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ; esses pacotes podem ser executados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o contexto de segurança **sysadmin** do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="d8d44-116">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages; these packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **sysadmin** security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="d8d44-117">Para se proteger contra essa elevação de privilégio ao executar planos de manutenção, conjuntos de coletas de dados e outros pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , configure os trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que executam pacotes para usar uma conta proxy com privilégios limitados ou apenas adicione membros **sysadmin** às funções **db_ssisadmin** e **dc_admin** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-117">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add **sysadmin** members to the **db_ssisadmin** and **dc_admin** roles.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d8d44-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="d8d44-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d8d44-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="d8d44-119">Permissions</span></span>  
 <span data-ttu-id="d8d44-120">Para criar ou gerenciar planos de manutenção, é necessário ser membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-120">To create or manage maintenance plans, you must be a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="d8d44-121">O Pesquisador de Objetos só exibe o nó **Planos de Manutenção** para usuários que são membros da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-121">Object Explorer only displays the **Maintenance Plans** node for users who are members of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-maintenance-plan-design-surface"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d8d44-122">Usando a Superfície de Design do Plano de Manutenção</span><span class="sxs-lookup"><span data-stu-id="d8d44-122">Using Maintenance Plan Design Surface</span></span>  
  
#### <a name="to-create-a-maintenance-plan"></a><span data-ttu-id="d8d44-123">Para criar um plano de manutenção</span><span class="sxs-lookup"><span data-stu-id="d8d44-123">To create a maintenance plan</span></span>  
  
1.  <span data-ttu-id="d8d44-124">No Pesquisador de Objetos, clique no sinal de adição para expandir o servidor em que você deseja criar um plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d8d44-124">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="d8d44-125">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-125">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="d8d44-126">Clique com o botão direito do mouse na pasta **Planos de Manutenção** e selecione **Novo Plano de Manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-126">Right-click the **Maintenance Plans** folder and select **New Maintenance Plan**.</span></span>  
  
4.  <span data-ttu-id="d8d44-127">Na caixa de diálogo **Novo Plano de Manutenção** , na caixa **Nome** , digite um nome para o plano e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-127">In the **New Maintenance Plan** dialog box, in the **Name** box, type a name for the plan and click **OK**.</span></span> <span data-ttu-id="d8d44-128">Isso abre a Caixa de Ferramentas e a superfície _maintenance_plan_name_ **[Design]** com o subplano **Subplan_1** criado na grade principal.</span><span class="sxs-lookup"><span data-stu-id="d8d44-128">This opens the  Toolbox and the _maintenance_plan_name_ **[Design]** surface with the **Subplan_1** subplan created in the main grid.</span></span>  
  
     <span data-ttu-id="d8d44-129">As opções a seguir estão disponíveis no cabeçalho do espaço de design.</span><span class="sxs-lookup"><span data-stu-id="d8d44-129">The following options are available in the design space's header.</span></span>  
  
     <span data-ttu-id="d8d44-130">**Adicionar Subplano**</span><span class="sxs-lookup"><span data-stu-id="d8d44-130">**Add Subplan**</span></span>  
     <span data-ttu-id="d8d44-131">Adiciona um subplano que você pode configurar.</span><span class="sxs-lookup"><span data-stu-id="d8d44-131">Adds a subplan that you can configure.</span></span>  
  
     <span data-ttu-id="d8d44-132">**Propriedades do Subplano**</span><span class="sxs-lookup"><span data-stu-id="d8d44-132">**Subplan Properties**</span></span>  
     <span data-ttu-id="d8d44-133">Exibe a caixa de diálogo **Propriedades do Subplano** do subplano selecionado na grade principal.</span><span class="sxs-lookup"><span data-stu-id="d8d44-133">Displays the **Subplan Properties** dialog box for the selected subplan in the main grid.</span></span> <span data-ttu-id="d8d44-134">Alternativamente, clique duas vezes no subplano na grade para exibir a caixa de diálogo **Propriedades do Subplano** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-134">Alternately, double-click a subplan in the grid to display the **Subplan Properties** dialog box.</span></span> <span data-ttu-id="d8d44-135">Consulte abaixo para obter mais informações sobre essa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d8d44-135">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="d8d44-136">**Exclua o Subplano Selecionado**</span><span class="sxs-lookup"><span data-stu-id="d8d44-136">**Delete Selected Subplan**</span></span>  
     <span data-ttu-id="d8d44-137">Exclui o subplano selecionado.</span><span class="sxs-lookup"><span data-stu-id="d8d44-137">Deletes the selected subplan.</span></span>  
  
     <span data-ttu-id="d8d44-138">**Agenda do Subplano**</span><span class="sxs-lookup"><span data-stu-id="d8d44-138">**Subplan Schedule**</span></span>  
     <span data-ttu-id="d8d44-139">Exibe a caixa de diálogo **Nova Agenda de Trabalho** para o subplano selecionado.</span><span class="sxs-lookup"><span data-stu-id="d8d44-139">Displays the **New Job Schedule** dialog box for the selected subplan.</span></span>  
  
     <span data-ttu-id="d8d44-140">**Remover Agenda**</span><span class="sxs-lookup"><span data-stu-id="d8d44-140">**Remove Schedule**</span></span>  
     <span data-ttu-id="d8d44-141">Remove uma agenda do subplano selecionado.</span><span class="sxs-lookup"><span data-stu-id="d8d44-141">Removes a schedule from the selected subplan.</span></span>  
  
     <span data-ttu-id="d8d44-142">**Gerenciar Conexões**</span><span class="sxs-lookup"><span data-stu-id="d8d44-142">**Manage Connections**</span></span>  
     <span data-ttu-id="d8d44-143">Exibe a caixa de diálogo **Gerenciar Conexões** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-143">Displays the **Manage Connections** dialog box.</span></span> <span data-ttu-id="d8d44-144">Usado para adicionar conexões de instância [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adicionais ao plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d8d44-144">Used to add additional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance connections to the maintenance plan.</span></span> <span data-ttu-id="d8d44-145">Consulte abaixo para obter mais informações sobre essa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d8d44-145">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="d8d44-146">**Relatório e Registro em Log**</span><span class="sxs-lookup"><span data-stu-id="d8d44-146">**Reporting and Logging**</span></span>  
     <span data-ttu-id="d8d44-147">Exibe a caixa de diálogo **Relatório e Registro em Log** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-147">Displays the **Reporting and Logging** dialog box.</span></span> <span data-ttu-id="d8d44-148">Consulte abaixo para obter mais informações sobre essa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d8d44-148">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="d8d44-149">**Servidores**</span><span class="sxs-lookup"><span data-stu-id="d8d44-149">**Servers**</span></span>  
     <span data-ttu-id="d8d44-150">Exiba a caixa de diálogo **Servidores** , que é usada para selecionar os servidores em que serão executadas as tarefas do subplano.</span><span class="sxs-lookup"><span data-stu-id="d8d44-150">Display the **Servers** dialog box, which is used to select the servers where the subplan tasks will be run.</span></span> <span data-ttu-id="d8d44-151">Essa opção só está habilitada em servidores mestre em ambientes multisservidor.</span><span class="sxs-lookup"><span data-stu-id="d8d44-151">This option is enabled only on master servers in multiserver environments.</span></span> <span data-ttu-id="d8d44-152">Para obter mais informações, consulte [Criar um ambiente multisservidor](../../ssms/agent/create-a-multiserver-environment.md) e [Plano de manutenção &#40;Servers&#41;](maintenance-plan-servers.md).</span><span class="sxs-lookup"><span data-stu-id="d8d44-152">For more information, see [Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) and [Maintenance Plan &#40;Servers&#41;](maintenance-plan-servers.md).</span></span>  
  
     <span data-ttu-id="d8d44-153">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d8d44-153">**Name**</span></span>  
     <span data-ttu-id="d8d44-154">Exibe o nome do plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d8d44-154">Display the maintenance plan name.</span></span> <span data-ttu-id="d8d44-155">Para planos de manutenção novos, o nome é especificado em uma caixa de diálogo antes que o designer de plano de manutenção seja aberto.</span><span class="sxs-lookup"><span data-stu-id="d8d44-155">For new maintenance plans, the name is specified in a dialog box before the maintenance plan designer opens.</span></span> <span data-ttu-id="d8d44-156">Para renomear um plano de manutenção, clique com o botão direito do mouse no plano no Pesquisador de Objetos e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-156">To rename a maintenance plan, right-click the plan in Object Explorer, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="d8d44-157">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d8d44-157">**Description**</span></span>  
     <span data-ttu-id="d8d44-158">Exiba ou especifique uma descrição para o plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d8d44-158">View or specify a description for the maintenance plan.</span></span> <span data-ttu-id="d8d44-159">O comprimento máximo para uma descrição é 512 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d8d44-159">The maximum length for a description is 512 characters.</span></span>  
  
     <span data-ttu-id="d8d44-160">**Superfície do Designer**</span><span class="sxs-lookup"><span data-stu-id="d8d44-160">**Designer Surface**</span></span>  
     <span data-ttu-id="d8d44-161">Executa design e mantém os planos de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d8d44-161">Design and maintain maintenance plans.</span></span> <span data-ttu-id="d8d44-162">Use a superfície de designer para adicionar tarefas de manutenção a um plano, remover tarefas de um plano, especificar os links com precedência entre tarefas e para indicar a ramificação ou paralelismo de uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="d8d44-162">Use the designer surface to add maintenance tasks to a plan, remove tasks from a plan, specify precedence links between the tasks, and indicate task branching and parallelism.</span></span>  
  
     <span data-ttu-id="d8d44-163">Um link de precedência entre duas tarefas estabelece uma relação entre elas.</span><span class="sxs-lookup"><span data-stu-id="d8d44-163">A precedence link between two tasks establishes a relationship between the tasks.</span></span> <span data-ttu-id="d8d44-164">A segunda tarefa (a *tarefa dependente*) é executada somente se o resultado da execução da primeira tarefa (a *tarefa precedente*) corresponde aos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="d8d44-164">The second task (the *dependent task*) executes only if the execution result of the first task (the *precedent task*) matches specified criteria.</span></span> <span data-ttu-id="d8d44-165">Normalmente o resultado da execução especificado é **Êxito**, **Falha**ou **Conclusão**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-165">Typically the execution result specified is **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="d8d44-166">Para obter mais informações, consulte a etapa **8** abaixo.</span><span class="sxs-lookup"><span data-stu-id="d8d44-166">For more information, see step **8** below.</span></span>  
  
5.  <span data-ttu-id="d8d44-167">No cabeçalho do espaço de design, clique duas vezes em **Subplano_1** e insira um nome e uma descrição para o subplano na caixa de diálogo **Propriedades do Subplano** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-167">In the design space's header, double-click **Subplan_1** and enter a name and description for the subplan in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="d8d44-168">As opções a seguir estão disponíveis na caixa de diálogo **Propriedades do Subplano** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-168">The following options are available in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="d8d44-169">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d8d44-169">**Name**</span></span>  
     <span data-ttu-id="d8d44-170">O nome do subplano.</span><span class="sxs-lookup"><span data-stu-id="d8d44-170">The name of the subplan.</span></span>  
  
     <span data-ttu-id="d8d44-171">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d8d44-171">**Description**</span></span>  
     <span data-ttu-id="d8d44-172">Uma descrição breve do subplano.</span><span class="sxs-lookup"><span data-stu-id="d8d44-172">A brief description of the subplan.</span></span>  
  
     <span data-ttu-id="d8d44-173">**Agenda**</span><span class="sxs-lookup"><span data-stu-id="d8d44-173">**Schedule**</span></span>  
     <span data-ttu-id="d8d44-174">Indica em qual agendamento o subplano será executado.</span><span class="sxs-lookup"><span data-stu-id="d8d44-174">Indicates on what schedule the subplan will be run.</span></span> <span data-ttu-id="d8d44-175">Clique em **Agenda do Subplano** para abrir a caixa de diálogo **Nova Agenda de Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-175">Click **Subplan Schedule** to open the **New Job Schedule** dialog box.</span></span> <span data-ttu-id="d8d44-176">Clique em **Remover Agenda** para excluir a agenda do subplano.</span><span class="sxs-lookup"><span data-stu-id="d8d44-176">Click **Remove Schedule** to delete the schedule from the subplan.</span></span>  
  
     <span data-ttu-id="d8d44-177">Lista**Executar como**</span><span class="sxs-lookup"><span data-stu-id="d8d44-177">**Run as** list</span></span>  
     <span data-ttu-id="d8d44-178">Selecione a conta a ser usada para executar esta subtarefa.</span><span class="sxs-lookup"><span data-stu-id="d8d44-178">Select the account to use to run this subtask.</span></span>  
  
6.  <span data-ttu-id="d8d44-179">Clique no ícone **Agenda do Subplano** para inserir detalhes de agenda na caixa de diálogo **Nova Agenda de Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-179">Click **Subplan Schedule** to enter schedule details in the **New Job Schedule** dialog box.</span></span>  
  
7.  <span data-ttu-id="d8d44-180">Para criar o subplano, arraste e solte elementos de fluxo de tarefas da **Caixa de Ferramentas** para a superfície de design do plano.</span><span class="sxs-lookup"><span data-stu-id="d8d44-180">To build the subplan, drag and drop task flow elements from the **Toolbox** to the plan design surface.</span></span> <span data-ttu-id="d8d44-181">Clique duas vezes nas tarefas, para abrir as caixas de diálogo e configurar suas opções.</span><span class="sxs-lookup"><span data-stu-id="d8d44-181">Double-click tasks to open dialog boxes to configure the task options.</span></span>  
  
     <span data-ttu-id="d8d44-182">As seguintes tarefas de plano de manutenção estão disponíveis na **Caixa de Ferramentas**:</span><span class="sxs-lookup"><span data-stu-id="d8d44-182">The following maintenance plan tasks are available in the **Toolbox**:</span></span>  
  
    -   <span data-ttu-id="d8d44-183">**Tarefa Backup de Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="d8d44-183">**Back up Database Task**</span></span>  
  
    -   <span data-ttu-id="d8d44-184">**Tarefa Verificar Integridade do Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="d8d44-184">**Check Database Integrity Task**</span></span>  
  
    -   <span data-ttu-id="d8d44-185">**Tarefa Executar Trabalho do SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="d8d44-185">**Execute SQL Server Agent Job Task**</span></span>  
  
    -   <span data-ttu-id="d8d44-186">**Tarefa Executar Instrução T-SQL**</span><span class="sxs-lookup"><span data-stu-id="d8d44-186">**Execute T-SQL Statement Task**</span></span>  
  
    -   <span data-ttu-id="d8d44-187">**Tarefa Limpeza do Histórico**</span><span class="sxs-lookup"><span data-stu-id="d8d44-187">**History Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="d8d44-188">**Tarefa Limpeza de Manutenção**</span><span class="sxs-lookup"><span data-stu-id="d8d44-188">**Maintenance Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="d8d44-189">**Tarefa de Notificação do Operador**</span><span class="sxs-lookup"><span data-stu-id="d8d44-189">**Notify Operator Task**</span></span>  
  
    -   <span data-ttu-id="d8d44-190">**Tarefa Recriar Índice**</span><span class="sxs-lookup"><span data-stu-id="d8d44-190">**Rebuild Index Task**</span></span>  
  
    -   <span data-ttu-id="d8d44-191">**Tarefa Reorganizar Índice**</span><span class="sxs-lookup"><span data-stu-id="d8d44-191">**Reorganize Index Task**</span></span>  
  
    -   <span data-ttu-id="d8d44-192">**Tarefa Reduzir Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="d8d44-192">**Shrink Database Task**</span></span>  
  
    -   <span data-ttu-id="d8d44-193">**Tarefa Atualizar Estatísticas**</span><span class="sxs-lookup"><span data-stu-id="d8d44-193">**Update Statistics Task**</span></span>  
  
     <span data-ttu-id="d8d44-194">Para adicionar tarefas à **Caixa de Ferramentas**:</span><span class="sxs-lookup"><span data-stu-id="d8d44-194">To add tasks to the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="d8d44-195">No menu **Ferramentas** , clique em **Escolher Itens da Caixa de Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-195">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="d8d44-196">Selecione as ferramentas que devem aparecer na **Caixa de Ferramentas**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-196">Select the tools you want to appear in the **Toolbox**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d8d44-197">A adição de tarefas do plano de manutenção à **Caixa de Ferramentas** também as disponibiliza no **Assistente de Plano de Manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-197">Adding maintenance plan tasks to the **Toolbox** also makes them available in the **Maintenance Plan Wizard**.</span></span> <span data-ttu-id="d8d44-198">Para obter mais informações sobre as tarefas individuais acima, consulte [Usando o Assistente de Plano de Manutenção](use-the-maintenance-plan-wizard.md#SSMSProcedure) em **Iniciar o Assistente de Plano de Manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-198">For more information on the individual tasks above, see [Using Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md#SSMSProcedure) under **Start the Maintenance Plan Wizard**.</span></span>  
  
8.  <span data-ttu-id="d8d44-199">Para definir um fluxo de trabalho entre tarefas:</span><span class="sxs-lookup"><span data-stu-id="d8d44-199">To define a workflow between tasks:</span></span>  
  
    1.  <span data-ttu-id="d8d44-200">Clique com o botão direito do mouse na tarefa anterior e selecione **Adicionar Restrição de Precedência**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-200">Right-click the precedent task and select **Add Precedence Constraint**.</span></span>  
  
    2.  <span data-ttu-id="d8d44-201">Na caixa de diálogo **Fluxo de Controle** , na lista **Para** , selecione a tarefa dependente e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-201">In the **Control Flow** dialog box, in the **To** list, select the dependent task and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="d8d44-202">Clique duas vezes no conector entre as duas tarefas para abrir a caixa de diálogo **Editor de Restrição de Precedência** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-202">Double click the connector between the two tasks to open the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="d8d44-203">As opções a seguir estão disponíveis na caixa de diálogo **Editor de Restrição de Precedência** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-203">The following options are available in the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="d8d44-204">**Opção de restrição**</span><span class="sxs-lookup"><span data-stu-id="d8d44-204">**Constraint option**</span></span>  
         <span data-ttu-id="d8d44-205">Define como uma restrição funciona entre duas tarefas.</span><span class="sxs-lookup"><span data-stu-id="d8d44-205">Defines how a constraint works between two tasks.</span></span>  
  
         <span data-ttu-id="d8d44-206">Lista**Operação de avaliação**</span><span class="sxs-lookup"><span data-stu-id="d8d44-206">**Evaluation operation**  list</span></span>  
         <span data-ttu-id="d8d44-207">Especifica a operação de avaliação usada pela restrição de precedência.</span><span class="sxs-lookup"><span data-stu-id="d8d44-207">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="d8d44-208">As operações são: **Constraint**, **Expression**, **Expression and Constraint** e **Expression or Constraint**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-208">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
         <span data-ttu-id="d8d44-209">Lista**Valor**</span><span class="sxs-lookup"><span data-stu-id="d8d44-209">**Value** list</span></span>  
         <span data-ttu-id="d8d44-210">Especifique o valor de restrição: **Success**, **Failure** ou **Completion**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-210">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="d8d44-211">**Êxito** é o padrão.</span><span class="sxs-lookup"><span data-stu-id="d8d44-211">**Success** is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d8d44-212">A linha de restrição de precedência é verde para **Êxito**, vermelha para **Falha**e azul para **Conclusão**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-212">The precedence constraint line is green for **Success**, red for **Failure**, and blue for **Completion**.</span></span>  
  
         <span data-ttu-id="d8d44-213">**Expression**</span><span class="sxs-lookup"><span data-stu-id="d8d44-213">**Expression**</span></span>  
         <span data-ttu-id="d8d44-214">Se usar as operações **Expression**, **Expression and Constraint**ou **Expression or Constraint**, digite uma expressão.</span><span class="sxs-lookup"><span data-stu-id="d8d44-214">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression.</span></span> <span data-ttu-id="d8d44-215">A expressão deve ser avaliada como um booliano.</span><span class="sxs-lookup"><span data-stu-id="d8d44-215">The expression must evaluate to a Boolean.</span></span>  
  
         <span data-ttu-id="d8d44-216">**Test**</span><span class="sxs-lookup"><span data-stu-id="d8d44-216">**Test**</span></span>  
         <span data-ttu-id="d8d44-217">Valide a expressão.</span><span class="sxs-lookup"><span data-stu-id="d8d44-217">Validate the expression.</span></span>  
  
         <span data-ttu-id="d8d44-218">**Várias restrições**</span><span class="sxs-lookup"><span data-stu-id="d8d44-218">**Multiple constraints**</span></span>  
         <span data-ttu-id="d8d44-219">Defina como várias restrições interoperam para controlar a execução da tarefa restrita.</span><span class="sxs-lookup"><span data-stu-id="d8d44-219">Define how multiple constraints interoperate to control the execution of the constrained task.</span></span>  
  
         <span data-ttu-id="d8d44-220">**AND lógico**</span><span class="sxs-lookup"><span data-stu-id="d8d44-220">**Logical AND**</span></span>  
         <span data-ttu-id="d8d44-221">Selecione para especificar que várias restrições de precedência no mesmo executável devem ser avaliadas juntas.</span><span class="sxs-lookup"><span data-stu-id="d8d44-221">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="d8d44-222">Todas as restrições devem ser avaliadas como True.</span><span class="sxs-lookup"><span data-stu-id="d8d44-222">All constraints must evaluate to True.</span></span> <span data-ttu-id="d8d44-223">Essa é a opção padrão.</span><span class="sxs-lookup"><span data-stu-id="d8d44-223">This option is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d8d44-224">Este tipo de restrição de precedência aparece como uma linha sólida nas cores verde, vermelho ou azul.</span><span class="sxs-lookup"><span data-stu-id="d8d44-224">This type of precedence constraint appears as a solid green, red, or blue line.</span></span>  
  
         <span data-ttu-id="d8d44-225">**OR lógico**</span><span class="sxs-lookup"><span data-stu-id="d8d44-225">**Logical OR**</span></span>  
         <span data-ttu-id="d8d44-226">Selecione para especificar que várias restrições de precedência no mesmo executável devem ser avaliadas juntas.</span><span class="sxs-lookup"><span data-stu-id="d8d44-226">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="d8d44-227">Pelo menos uma restrição deve ser avaliada como True.</span><span class="sxs-lookup"><span data-stu-id="d8d44-227">At least one constraint must evaluate to True.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d8d44-228">Este tipo de restrição de precedência aparece como uma linha pontilhada nas cores verde, vermelho ou azul.</span><span class="sxs-lookup"><span data-stu-id="d8d44-228">This type of precedence constraint appears as a dotted green, red, or blue line.</span></span>  
  
9. <span data-ttu-id="d8d44-229">Para adicionar outro subplano, contendo tarefas executadas em uma agenda diferente, clique em **Adicionar Subplano** na barra de ferramentas para abrir a caixa de diálogo **Propriedades do Subplano** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-229">To add another subplan that contains tasks run on a different schedule, click **Add Subplan** on the toolbar to open the **Subplan Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="d8d44-230">Para adicionar conexões a servidores diferentes:</span><span class="sxs-lookup"><span data-stu-id="d8d44-230">To add connections to different servers:</span></span>  
  
    1.  <span data-ttu-id="d8d44-231">Na barra de ferramentas do espaço de design, clique em **Gerenciar Conexões**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-231">In the design space's toolbar, click **Manage Connections**.</span></span>  
  
    2.  <span data-ttu-id="d8d44-232">Na caixa de diálogo **Gerenciar Conexões** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-232">In the **Manage Connections** dialog box, click **Add**.</span></span>  
  
    3.  <span data-ttu-id="d8d44-233">Na caixa de diálogo **Propriedades de Conexão** , na caixa **Nome da conexão** , insira o nome da conexão que você está criando.</span><span class="sxs-lookup"><span data-stu-id="d8d44-233">In the **Connection Properties** dialog box, in the **Connection name** box, enter the name of the connection you are creating.</span></span>  
  
    4.  <span data-ttu-id="d8d44-234">Em **Especifique o seguinte para conectar-se aos dados do SQL Server**, na caixa **Selecione ou digite o nome do servidor**, digite o nome do SQL Server que deseja usar ou clique nas reticências **(...)** e selecione um servidor na caixa de diálogo **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-234">Under **Specify the following to connect to SQL Server data**, in the **Select or enter a server name** box, either enter the name of the SQL server you want to use or click the ellipsis **(...)** and select a server in the **SQL Server** dialog box.</span></span> <span data-ttu-id="d8d44-235">Se você selecionar um servidor na caixa de diálogo **SQL Server** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-235">If you select a server from the **SQL Server** dialog box, click **OK**.</span></span>  
  
    5.  <span data-ttu-id="d8d44-236">Em **Insira as informações para fazer logon no servidor**, selecione **Usar Segurança Integrada do Windows NT** ou **Usar nome de usuário e senha específicos**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-236">Under **Enter information to log on to the server**, select either **Use Windows NT Integrated security** or **Use a specific user name and password**.</span></span> <span data-ttu-id="d8d44-237">Se você optar por usar um nome e uma senha de usuário específicos, insira essas informações nas caixas **Nome de usuário** e **Senha** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d8d44-237">If you elect to use a specific user name and password, enter that information in the **User name** and **Password** boxes, respectively.</span></span>  
  
    6.  <span data-ttu-id="d8d44-238">Na caixa de diálogo **Propriedades de Conexão** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-238">In the **Connection Properties** dialog box, click **OK**.</span></span>  
  
    7.  <span data-ttu-id="d8d44-239">Na caixa de diálogo **Gerenciar Conexões** , clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-239">In the **Manage Connections** dialog box, click **Close**.</span></span>  
  
11. <span data-ttu-id="d8d44-240">Para especificar opções de relatório:</span><span class="sxs-lookup"><span data-stu-id="d8d44-240">To specify reporting options:</span></span>  
  
    1.  <span data-ttu-id="d8d44-241">Na barra de ferramentas do espaço de design, clique em **Relatório e Registro em Log**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-241">In the design space's toolbar, click **Reporting and Logging**.</span></span>  
  
    2.  <span data-ttu-id="d8d44-242">Na caixa de diálogo **Relatório e Registro em Log** , em **Relatório**, selecione **Gerar um relatório de arquivo de texto** ou **Enviar relatório para um destinatário de email** ou ambas as opções.</span><span class="sxs-lookup"><span data-stu-id="d8d44-242">In the **Reporting and Logging** dialog box, under **Reporting**, select **Generate a text file report** or **Send report to an email recipient** or both.</span></span>  
  
        1.  <span data-ttu-id="d8d44-243">Se você selecionar **Gerar um relatório de arquivo de texto**, selecione **Criar um novo arquivo** ou **Acrescentar ao arquivo**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-243">If you select **Generate a text file report**, select either **Create a new file** or **Append to file**.</span></span>  
  
        2.  <span data-ttu-id="d8d44-244">Dependendo da seleção acima, insira o nome e o caminho completo do novo arquivo ou do arquivo a ser adicionado inserindo as informações nas caixas **Pasta** ou **Nome do arquivo** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-244">Depending on the selection above, enter the name and full path of the new file or file to be appended by entering the information in the **Folder** or **File name** boxes.</span></span> <span data-ttu-id="d8d44-245">Como alternativa, clique nas reticências **(...)** e selecione o caminho para a pasta ou nome do arquivo nas caixas de diálogo **Localizar pasta-**_server_name_ ou **Localizar arquivos de banco de dados-**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="d8d44-245">Alternately, click on the ellipsis **(...)** and select the path to the folder or file name from the **Locate Folder -**_server_name_ or **Locate Database Files -**_server_name_ dialog boxes.</span></span>  
  
        3.  <span data-ttu-id="d8d44-246">Se você selecionar **Enviar relatório para um destinatário de email**, na lista **Operador do agente** , selecione o destinatário do relatório enviado por e-mail.</span><span class="sxs-lookup"><span data-stu-id="d8d44-246">If you select **Send report to an email recipient**, on the **Agent operator** list, select the recipient of the emailed report.</span></span>  
  
            > [!NOTE]  
            >  <span data-ttu-id="d8d44-247">O SQL Server Agent deve ser configurado para usar o Database Mail para o envio de email.</span><span class="sxs-lookup"><span data-stu-id="d8d44-247">SQL Server Agent must be configured to use Database Mail in order to send mail.</span></span> <span data-ttu-id="d8d44-248">Para obter mais informações, consulte [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="d8d44-248">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)</span></span>  
  
    3.  <span data-ttu-id="d8d44-249">Para salvar informações mais detalhadas, em **Log**, selecione **Registrar informações estendidas em log**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-249">To save more detailed information, under **Logging**, select **Log extended information**.</span></span>  
  
    4.  <span data-ttu-id="d8d44-250">Para gravar informações de resultados do plano de manutenção em outro servidor, selecione **Registrar no servidor remoto** e selecione uma conexão de servidor na lista **Conexão** ou clique em **Nova** e insira as informações de conexão na caixa de diálogo **Propriedades de Conexão** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-250">To write maintenance plan results information to another server, select **Log to remote server** and either select a server connection from the **Connection** list or click **New** and enter the connection information in the **Connection Properties** dialog box.</span></span>  
  
    5.  <span data-ttu-id="d8d44-251">Na caixa de diálogo **Relatório e Registro em Log** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-251">In the **Reporting and Logging** dialog box, click **OK**.</span></span>  
  
12. <span data-ttu-id="d8d44-252">Para exibir os resultados no visualizador de arquivo de log, no **Pesquisador de Objetos**, clique com o botão direito do mouse na pasta **Planos de Manutenção** ou no plano de manutenção específico e selecione **Exibir Histórico**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-252">To view the results in the log file viewer, in **Object Explorer**, right-click either the **Maintenance Plans** folder or the specific maintenance plan and select **View History**.</span></span>  
  
     <span data-ttu-id="d8d44-253">As opções a seguir estão disponíveis na caixa de diálogo **Visualizador do arquivo de log-**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="d8d44-253">The following options are available on the **Log File Viewer -**_server_name_ dialog box.</span></span>  
  
     <span data-ttu-id="d8d44-254">**Carregar Log**</span><span class="sxs-lookup"><span data-stu-id="d8d44-254">**Load Log**</span></span>  
     <span data-ttu-id="d8d44-255">Abra uma caixa de diálogo onde seja possível especificar um arquivo de log a ser carregado.</span><span class="sxs-lookup"><span data-stu-id="d8d44-255">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="d8d44-256">**Exportar**</span><span class="sxs-lookup"><span data-stu-id="d8d44-256">**Export**</span></span>  
     <span data-ttu-id="d8d44-257">Abra uma caixa de diálogo que permita exportar as informações mostradas na grade **Resumo do arquivo de log** para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d8d44-257">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="d8d44-258">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="d8d44-258">**Refresh**</span></span>  
     <span data-ttu-id="d8d44-259">Atualize a exibição dos logs selecionados.</span><span class="sxs-lookup"><span data-stu-id="d8d44-259">Refresh the view of the selected logs.</span></span> <span data-ttu-id="d8d44-260">O botão **Atualizar** relê os logs selecionados do servidor de destino ao aplicar qualquer configuração de filtro.</span><span class="sxs-lookup"><span data-stu-id="d8d44-260">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="d8d44-261">**Filter**</span><span class="sxs-lookup"><span data-stu-id="d8d44-261">**Filter**</span></span>  
     <span data-ttu-id="d8d44-262">Abra uma caixa de diálogo que permita especificar configurações usadas para filtrar o arquivo de log, como **Conexão**, **Data**ou outros critérios de filtragem **Gerais** .</span><span class="sxs-lookup"><span data-stu-id="d8d44-262">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="d8d44-263">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="d8d44-263">**Search**</span></span>  
     <span data-ttu-id="d8d44-264">Pesquise o texto específico no arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="d8d44-264">Search the log file for specific text.</span></span> <span data-ttu-id="d8d44-265">Não há suporte à pesquisa com caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="d8d44-265">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="d8d44-266">**Parar**</span><span class="sxs-lookup"><span data-stu-id="d8d44-266">**Stop**</span></span>  
     <span data-ttu-id="d8d44-267">Interrompe o carregamento das entradas do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="d8d44-267">Stops loading the log file entries.</span></span> <span data-ttu-id="d8d44-268">Por exemplo, você poderá usar essa opção se um arquivo de log remoto ou offline demorar muito tempo para ser carregado e você desejar exibir apenas as entradas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="d8d44-268">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="d8d44-269">**Resumo do arquivo de log**</span><span class="sxs-lookup"><span data-stu-id="d8d44-269">**Log file summary**</span></span>  
     <span data-ttu-id="d8d44-270">Esse painel de informações exibe um resumo da filtragem do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="d8d44-270">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="d8d44-271">Se o arquivo não for filtrado, você verá o seguinte texto, **Nenhum filtro aplicado**.</span><span class="sxs-lookup"><span data-stu-id="d8d44-271">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="d8d44-272">Se um filtro for aplicado ao log, você verá o seguinte texto **Filtrar entradas do log em que:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="d8d44-272">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="d8d44-273">**Data**</span><span class="sxs-lookup"><span data-stu-id="d8d44-273">**Date**</span></span>  
     <span data-ttu-id="d8d44-274">Exibe a data do evento.</span><span class="sxs-lookup"><span data-stu-id="d8d44-274">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="d8d44-275">**Origem**</span><span class="sxs-lookup"><span data-stu-id="d8d44-275">**Source**</span></span>  
     <span data-ttu-id="d8d44-276">Exibe o recurso de origem do qual o evento é criado, como o nome do serviço (MSSQLSERVER, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="d8d44-276">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="d8d44-277">Isso não é exibido para todos os tipos de log.</span><span class="sxs-lookup"><span data-stu-id="d8d44-277">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="d8d44-278">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="d8d44-278">**Message**</span></span>  
     <span data-ttu-id="d8d44-279">Exibe todas as mensagens associadas ao evento.</span><span class="sxs-lookup"><span data-stu-id="d8d44-279">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="d8d44-280">**Tipo de Log**</span><span class="sxs-lookup"><span data-stu-id="d8d44-280">**Log Type**</span></span>  
     <span data-ttu-id="d8d44-281">Exibe o tipo de log ao qual o evento pertence.</span><span class="sxs-lookup"><span data-stu-id="d8d44-281">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="d8d44-282">Todos os logs selecionados são exibidos na janela de resumo de arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="d8d44-282">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="d8d44-283">**Origem do Log**</span><span class="sxs-lookup"><span data-stu-id="d8d44-283">**Log Source**</span></span>  
     <span data-ttu-id="d8d44-284">Exibe uma descrição do log de origem no qual o evento é capturado.</span><span class="sxs-lookup"><span data-stu-id="d8d44-284">Displays a description of the source log in which the event is captured.</span></span>  
  
     <span data-ttu-id="d8d44-285">**Detalhes da linha selecionada**</span><span class="sxs-lookup"><span data-stu-id="d8d44-285">**Selected row details**</span></span>  
     <span data-ttu-id="d8d44-286">Selecione uma linha para exibir detalhes adicionais sobre a linha de evento selecionada na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="d8d44-286">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="d8d44-287">As colunas podem ser reordenadas arrastando-as para locais novos na grade.</span><span class="sxs-lookup"><span data-stu-id="d8d44-287">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="d8d44-288">As colunas podem ser redimensionadas arrastando para a esquerda ou direta as barras separadoras de coluna no cabeçalho de grade.</span><span class="sxs-lookup"><span data-stu-id="d8d44-288">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="d8d44-289">Clique duas vezes nas barras separadoras de coluna no cabeçalho da grade para dimensionar automaticamente a coluna para a largura do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d8d44-289">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="d8d44-290">**Instância**</span><span class="sxs-lookup"><span data-stu-id="d8d44-290">**Instance**</span></span>  
     <span data-ttu-id="d8d44-291">O nome da instância do na qual ocorreu o evento.</span><span class="sxs-lookup"><span data-stu-id="d8d44-291">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="d8d44-292">Esse nome é exibido como *nome do computador*\\*nome da instância*.</span><span class="sxs-lookup"><span data-stu-id="d8d44-292">This is displayed as *computer name*\\*instance name*.</span></span>  
  
  
