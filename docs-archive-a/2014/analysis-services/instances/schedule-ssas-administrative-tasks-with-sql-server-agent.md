---
title: Agendar tarefas administrativas do SSAS com o SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d1484b3-51d9-48a0-93d2-0c3e4ed22b87
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c78fa5fcebc0589ba863163b93ad2d10731b75a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681240"
---
# <a name="schedule-ssas-administrative-tasks-with-sql-server-agent"></a><span data-ttu-id="f4d91-102">Agendar tarefas administrativas do SSAS com o SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f4d91-102">Schedule SSAS Administrative Tasks with SQL Server Agent</span></span>
  <span data-ttu-id="f4d91-103">Usando o serviço SQL Server Agent, você pode agendar tarefas administrativas do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para executar na ordem e nos horários em que você precisa.</span><span class="sxs-lookup"><span data-stu-id="f4d91-103">Using the SQL Server Agent service, you can schedule [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrative tasks to run in the order and times that you need.</span></span> <span data-ttu-id="f4d91-104">As tarefas agendadas ajudam a automatizar os processos que são executados em ciclos regulares ou previsíveis.</span><span class="sxs-lookup"><span data-stu-id="f4d91-104">Scheduled tasks help you automate processes that run on regular or predictable cycles.</span></span> <span data-ttu-id="f4d91-105">Você pode agendar a execução de tarefas administrativas, como o processamento de cubos, nas horas de menor atividade comercial.</span><span class="sxs-lookup"><span data-stu-id="f4d91-105">You can schedule administrative tasks, such as cube processing, to run during times of slow business activity.</span></span> <span data-ttu-id="f4d91-106">Pode também estabelecer a ordem em que essas tarefas devem ser executadas criando etapas em um trabalho do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="f4d91-106">You can also determine the order in which tasks run by creating job steps within a SQL Server Agent job.</span></span> <span data-ttu-id="f4d91-107">Por exemplo, é possível processar um cubo e, em seguida, fazer o backup do cubo.</span><span class="sxs-lookup"><span data-stu-id="f4d91-107">For example, you can process a cube and then perform a backup of the cube.</span></span>  
  
 <span data-ttu-id="f4d91-108">Com etapas de trabalho, você tem controle sobre o fluxo de execução.</span><span class="sxs-lookup"><span data-stu-id="f4d91-108">Job steps give you control over flow of execution.</span></span> <span data-ttu-id="f4d91-109">Em caso de falha de um trabalho, é possível configurar o SQL Server Agent para continuar executando as demais tarefas ou interromper a execução.</span><span class="sxs-lookup"><span data-stu-id="f4d91-109">If one job fails, you can configure SQL Server Agent to continue to run the remaining tasks or to stop execution.</span></span> <span data-ttu-id="f4d91-110">Você também pode configurar o SQL Server Agent para enviar notificações sobre o sucesso ou a falha da execução do trabalho.</span><span class="sxs-lookup"><span data-stu-id="f4d91-110">You can also configure SQL Server Agent to send notifications about the success or failure of job execution.</span></span>  
  
 <span data-ttu-id="f4d91-111">Este tópico é um passo a passo que mostra dois modos de usar o SQL Server Agent para executar um script XMLA.</span><span class="sxs-lookup"><span data-stu-id="f4d91-111">This topic is a walkthrough that shows two ways of using SQL Server Agent to run XMLA script.</span></span> <span data-ttu-id="f4d91-112">O primeiro exemplo demonstra como agendar o processamento de uma única dimensão.</span><span class="sxs-lookup"><span data-stu-id="f4d91-112">The first example demonstrates how to schedule processing of a single dimension.</span></span> <span data-ttu-id="f4d91-113">O segundo exemplo mostra como combinar tarefas de processamento em um único script executado com base em uma agenda.</span><span class="sxs-lookup"><span data-stu-id="f4d91-113">Example two shows how to combine processing tasks into a single script that runs on a schedule.</span></span> <span data-ttu-id="f4d91-114">Para concluir essas etapas, você precisará atender aos pré-requisitos a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4d91-114">To complete this walkthrough, you will need to meet the following prerequisites.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f4d91-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f4d91-115">Prerequisites</span></span>  
 <span data-ttu-id="f4d91-116">O serviço SQL Server Agent deve ser instalado.</span><span class="sxs-lookup"><span data-stu-id="f4d91-116">SQL Server Agent service must be installed.</span></span>  
  
 <span data-ttu-id="f4d91-117">Por padrão, os trabalhos são executados na conta de serviço.</span><span class="sxs-lookup"><span data-stu-id="f4d91-117">By default, jobs run under the service account.</span></span> <span data-ttu-id="f4d91-118">No [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , a conta padrão para SQL Server Agent é NT Service\SQLAgent $ \<instancename> .</span><span class="sxs-lookup"><span data-stu-id="f4d91-118">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the default account for SQL Server Agent is NT Service\SQLAgent$\<instancename>.</span></span> <span data-ttu-id="f4d91-119">Para executar um backup ou uma tarefa de processamento, essa conta deve ser um administrador do sistema na instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f4d91-119">To perform a backup or processing task, this account must be a system administrator on the Analysis Services instance.</span></span> <span data-ttu-id="f4d91-120">Para obter mais informações, consulte [conceder permissões de administrador do servidor &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span><span class="sxs-lookup"><span data-stu-id="f4d91-120">For more information, see [Grant Server Administrator Permissions &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span></span>  
  
 <span data-ttu-id="f4d91-121">Você também deveria ter um banco de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="f4d91-121">You should also have a test database to work with.</span></span> <span data-ttu-id="f4d91-122">Você pode implantar o banco de dados de exemplo multidimensional do AdventureWorks ou um projeto do tutorial multidimensional do Analysis Services para usar neste passo a passo.</span><span class="sxs-lookup"><span data-stu-id="f4d91-122">You can deploy the AdventureWorks multidimensional sample database or a project from the Analysis Services multidimensional tutorial to use in this walkthrough.</span></span> <span data-ttu-id="f4d91-123">Para obter mais informações, consulte [instalar dados de exemplo e projetos para o tutorial de modelagem multidimensional Analysis Services](../install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="f4d91-123">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](../install-sample-data-and-projects.md).</span></span>  
  
## <a name="example-1-processing-a-dimension-in-a-scheduled-task"></a><span data-ttu-id="f4d91-124">Exemplo 1: Processando uma dimensão em uma tarefa agendada</span><span class="sxs-lookup"><span data-stu-id="f4d91-124">Example 1: Processing a dimension in a scheduled task</span></span>  
 <span data-ttu-id="f4d91-125">Este exemplo demonstra como criar e agendar um trabalho que processa uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="f4d91-125">This example demonstrates how to create and schedule a job that processes a dimension.</span></span>  
  
 <span data-ttu-id="f4d91-126">Uma tarefa agendada do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] é um script XMLA inserido em um trabalho do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="f4d91-126">An [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] scheduled task is an XMLA script that is embedded into a SQL Server Agent job.</span></span> <span data-ttu-id="f4d91-127">A execução desse trabalho é agendada para as horas e com a frequência desejadas.</span><span class="sxs-lookup"><span data-stu-id="f4d91-127">This job is scheduled to run at desired times and frequency.</span></span> <span data-ttu-id="f4d91-128">Como o SQL Server Agent faz parte do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você trabalha com o Mecanismo de Banco de Dados e o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para criar e agendar uma tarefa administrativa.</span><span class="sxs-lookup"><span data-stu-id="f4d91-128">Because the SQL Server Agent is part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you work with both the Database Engine and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to create and schedule an administrative task.</span></span>  
  
###  <a name="create-a-script-for-processing-a-dimension-in-a-sql-server-agent-job"></a><a name="bkmk_CreateScript"></a><span data-ttu-id="f4d91-129">Criar um script para processar uma dimensão em um trabalho SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f4d91-129">Create a script for processing a dimension in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="f4d91-130">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4d91-130">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="f4d91-131">Abra uma pasta de banco de dados e localize uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="f4d91-131">Open a database folder and find a dimension.</span></span> <span data-ttu-id="f4d91-132">Clique com o botão direito do mouse na dimensão e selecione **Processar**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-132">Right-click the dimension and select **Process**.</span></span>  
  
2.  <span data-ttu-id="f4d91-133">Na caixa de diálogo **Processar Dimensão** , na coluna **Opções de Processo** na **Lista de objetos**, verifique se a opção dessa coluna é **Processar Completo**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-133">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="f4d91-134">Se essa opção não estiver selecionada, em **Opções de Processo**, clique na opção e selecione **Processar Completo** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="f4d91-134">If it is not, under **Process Options**, click the option, and then select **Process Full** from the drop-down list.</span></span>  
  
3.  <span data-ttu-id="f4d91-135">Clique em **Script**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-135">Click **Script**.</span></span>  
  
     <span data-ttu-id="f4d91-136">Essa etapa abre a janela **Consulta XML** que contém o script XMLA que processa a dimensão.</span><span class="sxs-lookup"><span data-stu-id="f4d91-136">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="f4d91-137">Na caixa de diálogo **Processar Dimensão** , clique em **Cancelar** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f4d91-137">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="f4d91-138">Na janela **Consulta XMLA** , realce o script XMLA, clique com o botão direito do mouse no script realçado e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-138">In the **XMLA Query** window, highlight the XMLA script, right-click the highlighted script, and select **Copy**.</span></span>  
  
     <span data-ttu-id="f4d91-139">Essa etapa copia o script XMLA para a Área de Transferência do Windows.</span><span class="sxs-lookup"><span data-stu-id="f4d91-139">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="f4d91-140">Você pode deixar o script XMLA na Área de Transferência ou colá-lo no Bloco de Notas ou em outro editor de texto.</span><span class="sxs-lookup"><span data-stu-id="f4d91-140">You can leave the XMLA script in the Clipboard or paste it into Notepad or another text editor.</span></span> <span data-ttu-id="f4d91-141">Este é um exemplo de script XMLA:</span><span class="sxs-lookup"><span data-stu-id="f4d91-141">The following is an example of the XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Account</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
###  <a name="create-and-schedule-the-dimension-processing-job"></a><a name="bkmk_ProcessJob"></a><span data-ttu-id="f4d91-142">Criar e agendar o trabalho de processamento de dimensões</span><span class="sxs-lookup"><span data-stu-id="f4d91-142">Create and schedule the dimension processing job</span></span>  
  
1.  <span data-ttu-id="f4d91-143">Conecte-se a uma instância do Mecanismo de Banco de Dados e abra o Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="f4d91-143">Connect to an instance of the Database Engine and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="f4d91-144">Expanda o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-144">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="f4d91-145">Clique com o botão direito do mouse em **Trabalho** e selecione **Novo Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-145">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="f4d91-146">Na caixa de diálogo **Novo Trabalho** , digite um nome de trabalho em **Nome**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-146">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="f4d91-147">Em **Selecionar uma página**, selecione **Etapas**e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-147">Under **Select a page**, select **Steps**, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="f4d91-148">Na caixa de diálogo **Nova Etapa do Trabalho** , digite um nome de etapa em **Nome da Etapa**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-148">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="f4d91-149">Em **servidor**, digite **localhost** para uma instância padrão do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e \*\*localhost \\ \*\* \<*instance name*> para uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="f4d91-149">In **Server**, type **localhost** for a default instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and **localhost\\**\<*instance name*> for a named instance.</span></span>  
  
     <span data-ttu-id="f4d91-150">Se você pretende executar o trabalho de um computador remoto, use o nome de servidor e nome de instância onde o trabalho será executado.</span><span class="sxs-lookup"><span data-stu-id="f4d91-150">If you will be running the job from a remote computer, use the server name and instance name where the job will run.</span></span> <span data-ttu-id="f4d91-151">Use o formato \<*server name*> para uma instância padrão e o \<*server name*> \\ < *nome da instância*> para uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="f4d91-151">Use the format \<*server name*> for a default instance, and \<*server name*>\\<*instance name*> for a named instance.</span></span>  
  
8.  <span data-ttu-id="f4d91-152">Em **Tipo**, selecione **Comando do SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-152">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
9. <span data-ttu-id="f4d91-153">Em **Comando**, clique com o botão direito do mouse e selecione **Colar**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-153">In **Command**, right-click and select **Paste**.</span></span> <span data-ttu-id="f4d91-154">O script XMLA gerado na etapa anterior deve aparecer na janela de comando.</span><span class="sxs-lookup"><span data-stu-id="f4d91-154">The XMLA script that you generated in the previous step should appear in the command window.</span></span>  
  
10. <span data-ttu-id="f4d91-155">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-155">Click **OK**.</span></span>  
  
11. <span data-ttu-id="f4d91-156">Em **Selecionar uma página**, clique em **Agendas**e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-156">Under **Select a page**, click **Schedules**, and then click **New**.</span></span>  
  
12. <span data-ttu-id="f4d91-157">Na caixa de diálogo **Nova Agenda de Trabalho** , digite um nome de agenda em **Nome**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-157">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f4d91-158">Essa etapa cria uma agenda para Domingo às 12:00 AM.</span><span class="sxs-lookup"><span data-stu-id="f4d91-158">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="f4d91-159">A próxima etapa mostra como executar o trabalho manualmente.</span><span class="sxs-lookup"><span data-stu-id="f4d91-159">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="f4d91-160">Você também pode especificar uma agenda que executará o trabalho durante o seu monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f4d91-160">You can also specify a schedule that executes the job when you are monitoring it.</span></span>  
  
13. <span data-ttu-id="f4d91-161">Na caixa de diálogo **Novo Trabalho** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-161">In the **New Job** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="f4d91-162">No **Pesquisador de Objetos**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho criado e selecione **Iniciar Trabalho na Etapa**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-162">In **Object Explorer**, expand **Jobs**, right-click the job you created, and then select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="f4d91-163">Como o trabalho tem apenas uma etapa, ele será executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f4d91-163">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="f4d91-164">Se o trabalho contiver mais de uma etapa, você poderá selecionar a etapa em que o trabalho deve iniciar.</span><span class="sxs-lookup"><span data-stu-id="f4d91-164">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
15. <span data-ttu-id="f4d91-165">Quando o trabalho for concluído, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-165">When the job finishes, click **Close**.</span></span>  
  
## <a name="example-2-batch-processing-a-dimension-and-a-partition-in-a-scheduled-task"></a><span data-ttu-id="f4d91-166">Exemplo 2: Processando uma dimensão e uma partição em lote em uma tarefa agendada</span><span class="sxs-lookup"><span data-stu-id="f4d91-166">Example 2: Batch processing a dimension and a partition in a scheduled task</span></span>  
 <span data-ttu-id="f4d91-167">Os procedimentos deste exemplo demonstram como criar e agendar um trabalho que processa uma dimensão de banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] em lote e, ao mesmo tempo, processa uma partição de cubo que depende da dimensão para agregação.</span><span class="sxs-lookup"><span data-stu-id="f4d91-167">The procedures in this example demonstrate how to create and schedule a job that batch processes an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database dimension, and at the same time to process a  cube partition that depends on the dimension for aggregation.</span></span> <span data-ttu-id="f4d91-168">Para obter mais informações sobre processamento em lote de objetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consulte [Processamento em lote &#40;Analysis Services&#41;](../multidimensional-models/batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="f4d91-168">For more information about batch processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Batch Processing &#40;Analysis Services&#41;](../multidimensional-models/batch-processing-analysis-services.md).</span></span>  
  
###  <a name="create-a-script-for-batch-processing-a-dimension-and-partition-in-a-sql-server-agent-job"></a><a name="bkmk_BatchProcess"></a><span data-ttu-id="f4d91-169">Criar um script para processamento em lotes de uma dimensão e uma partição em um trabalho SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f4d91-169">Create a script for batch processing a dimension and partition in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="f4d91-170">Usando o mesmo banco de dados, expanda **Dimensões**, clique com o botão direito do mouse na dimensão **Cliente** e selecione **Processo**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-170">Using the same database, expand **Dimensions**, right-click the **Customer** dimension, and select **Process**.</span></span>  
  
2.  <span data-ttu-id="f4d91-171">Na caixa de diálogo **Processar Dimensão** , na coluna **Opções de Processo** da **Lista de objetos**, verifique se a opção dessa coluna é **Processar Completo**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-171">In the **Process Dimension** dialog box, in **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
3.  <span data-ttu-id="f4d91-172">Clique em **Script**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-172">Click **Script**.</span></span>  
  
     <span data-ttu-id="f4d91-173">Essa etapa abre a janela **Consulta XML** que contém o script XMLA que processa a dimensão.</span><span class="sxs-lookup"><span data-stu-id="f4d91-173">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="f4d91-174">Na caixa de diálogo **Processar Dimensão** , clique em **Cancelar** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f4d91-174">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="f4d91-175">Expanda **Cubos**, **Adventure Works**, **Grupos de Medidas**, **Vendas pela Internet**, **Partições**, e clique com o botão direito do mouse na última partição da lista e selecione **Processar**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-175">Expand **Cubes**, expand **Adventure Works**, expand **Measure Groups**, expand **Internet Sales**, expand **Partitions**, right-click the last partition in the list, and then select **Process**.</span></span>  
  
6.  <span data-ttu-id="f4d91-176">Na caixa de diálogo **Processar Partição** , na coluna **Opções de Processo** da **Lista de objetos**, verifique se a opção dessa coluna é **Processar Completo**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-176">In the **Process Partition** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
7.  <span data-ttu-id="f4d91-177">Clique em **Script**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-177">Click **Script**.</span></span>  
  
     <span data-ttu-id="f4d91-178">Essa etapa abre uma segunda janela **Consulta XML** que contém o script XMLA que processa a partição.</span><span class="sxs-lookup"><span data-stu-id="f4d91-178">This step opens a second **XML Query** window that contains the XMLA script that processes the partition.</span></span>  
  
8.  <span data-ttu-id="f4d91-179">Na caixa de diálogo **Processar Partição** , clique em **Cancelar** para fechar o editor.</span><span class="sxs-lookup"><span data-stu-id="f4d91-179">In the **Process Partition** dialog box, click **Cancel** to close the editor.</span></span>  
  
     <span data-ttu-id="f4d91-180">Neste ponto, você deve mesclar os dois scripts e assegurar que a dimensão seja processada primeiro.</span><span class="sxs-lookup"><span data-stu-id="f4d91-180">At this point you must merge the two scripts, and ensure that the dimension is processed first.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="f4d91-181">Se a partição for processada primeiro, o processamento da dimensão subsequente fará com que a partição se torne não processada.</span><span class="sxs-lookup"><span data-stu-id="f4d91-181">If the partition is processed first, the subsequent dimension processing causes the partition to become unprocessed.</span></span> <span data-ttu-id="f4d91-182">A partição exigiria um segundo processamento para atingir um estado processado.</span><span class="sxs-lookup"><span data-stu-id="f4d91-182">The partition would then require a second processing to reach a processed state.</span></span>  
  
9. <span data-ttu-id="f4d91-183">Na janela **Consulta XMLA** que contém o script XMLA que processa a partição, realce o código dentro das tags `Batch` e `Parallel` , clique com o botão direito do mouse no script e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-183">In the **XMLA Query** window that contains the XMLA script that processes the partition, highlight the code inside the `Batch` and `Parallel` tags, right-click the highlighted script, and select **Copy**.</span></span>  
  
    ```  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID> Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID> Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
    ```  
  
10. <span data-ttu-id="f4d91-184">Abra a janela **Consulta XMLA** que contém o script XMLA que processa a dimensão.</span><span class="sxs-lookup"><span data-stu-id="f4d91-184">Open the **XMLA Query** window that contains the XMLA script that processes the dimension.</span></span> <span data-ttu-id="f4d91-185">Clique com o botão direito do mouse no script à esquerda da marca `</Process>` e selecione **Colar**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-185">Right-click within the script to the left of the `</Process>` tag and select **Paste**.</span></span>  
  
     <span data-ttu-id="f4d91-186">O exemplo a seguir mostra o script XMLA revisado.</span><span class="sxs-lookup"><span data-stu-id="f4d91-186">The following example shows the revised XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Customer</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID>Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
11. <span data-ttu-id="f4d91-187">Realce o script XMLA revisado, clique com o botão direito do mouse no script realçado e selecione **Copiar.**</span><span class="sxs-lookup"><span data-stu-id="f4d91-187">Highlight the revised XMLA script, right-click the highlighted script, and select **Copy.**</span></span>  
  
12. <span data-ttu-id="f4d91-188">Essa etapa copia o script XMLA para a Área de Transferência do Windows.</span><span class="sxs-lookup"><span data-stu-id="f4d91-188">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="f4d91-189">Você pode deixar o script XMLA na Área de Transferência, salvá-lo em um arquivo ou colá-lo no Bloco de Notas ou em outro editor de texto.</span><span class="sxs-lookup"><span data-stu-id="f4d91-189">You can leave the XMLA script in the Clipboard, save it to a file, or paste it into Notepad or another text editor.</span></span>  
  
###  <a name="create-and-schedule-the-batch-processing-job"></a><a name="bkmk_Scheduling"></a><span data-ttu-id="f4d91-190">Criar e agendar o trabalho de processamento em lotes</span><span class="sxs-lookup"><span data-stu-id="f4d91-190">Create and schedule the batch processing job</span></span>  
  
1.  <span data-ttu-id="f4d91-191">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e abra o Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="f4d91-191">Connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="f4d91-192">Expanda o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-192">Expand **SQL Server Agent**.</span></span> <span data-ttu-id="f4d91-193">Inicie o serviço caso ele ainda não esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="f4d91-193">Start the service if is not running.</span></span>  
  
3.  <span data-ttu-id="f4d91-194">Clique com o botão direito do mouse em **Trabalho** e selecione **Novo Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-194">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="f4d91-195">Na caixa de diálogo **Novo Trabalho** , digite um nome de trabalho em **Nome**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-195">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="f4d91-196">Em **Etapas**, clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-196">In **Steps**, click **New**.</span></span>  
  
6.  <span data-ttu-id="f4d91-197">Na caixa de diálogo **Nova Etapa do Trabalho** , digite um nome de etapa em **Nome da Etapa**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-197">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="f4d91-198">Em **Tipo**, selecione **Comando do SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-198">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
8.  <span data-ttu-id="f4d91-199">Em **Executar como**, selecione a **Conta de Serviço do SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-199">In **Run as**, select the **SQL Server Agent Service Account**.</span></span> <span data-ttu-id="f4d91-200">Lembre-se, a partir da seção Pré-requisitos, de que essa conta deve ter permissões administrativas no Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f4d91-200">Recall from the Prerequisites section that this account must have administrative permissions on Analysis Services.</span></span>  
  
9. <span data-ttu-id="f4d91-201">Em **Servidor**, especifique o nome do servidor da instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f4d91-201">In **Server**, specify the server name of the Analysis Services instance.</span></span>  
  
10. <span data-ttu-id="f4d91-202">Em **Comando**, clique com o botão direito do mouse e selecione **Colar**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-202">In **Command**, right-click and select **Paste**.</span></span>  
  
11. <span data-ttu-id="f4d91-203">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-203">Click **OK**.</span></span>  
  
12. <span data-ttu-id="f4d91-204">Na página **Agendas** , clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-204">In the **Schedules** page, click **New**.</span></span>  
  
13. <span data-ttu-id="f4d91-205">Na caixa de diálogo **Nova Agenda de Trabalho** , digite um nome de agenda em **Nome**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-205">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f4d91-206">Essa etapa cria uma agenda para Domingo às 12:00 AM.</span><span class="sxs-lookup"><span data-stu-id="f4d91-206">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="f4d91-207">A próxima etapa mostra como executar o trabalho manualmente.</span><span class="sxs-lookup"><span data-stu-id="f4d91-207">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="f4d91-208">Você também pode selecionar uma agenda que executará o trabalho durante o seu monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f4d91-208">You can also select a schedule which will execute the job when you are monitoring it.</span></span>  
  
14. <span data-ttu-id="f4d91-209">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f4d91-209">Click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="f4d91-210">No **Pesquisador de Objetos**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho criado e selecione **Iniciar Trabalho na Etapa**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-210">In **Object Explorer**, expand **Jobs**, right-click the job you created, and select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="f4d91-211">Como o trabalho tem apenas uma etapa, ele será executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f4d91-211">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="f4d91-212">Se o trabalho contiver mais de uma etapa, você poderá selecionar a etapa em que o trabalho deve iniciar.</span><span class="sxs-lookup"><span data-stu-id="f4d91-212">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
16. <span data-ttu-id="f4d91-213">Quando o trabalho for concluído, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="f4d91-213">When the job finishes, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d91-214">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4d91-214">See Also</span></span>  
 <span data-ttu-id="f4d91-215">[Opções de processamento e configurações &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="f4d91-215">[Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span></span>  
 [<span data-ttu-id="f4d91-216">Script de tarefas administrativas no Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f4d91-216">Script Administrative Tasks in Analysis Services</span></span>](../script-administrative-tasks-in-analysis-services.md)  
  
  
