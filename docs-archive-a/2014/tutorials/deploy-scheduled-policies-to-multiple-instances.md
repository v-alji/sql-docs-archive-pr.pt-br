---
title: Implantar políticas agendadas em várias instâncias | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: f551b8e8-3668-4ed4-852f-bae826254f4f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 30faf94c2033be43ac035517e58d5a18c0c68ab8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679108"
---
# <a name="deploy-scheduled-policies-to-multiple-instances"></a><span data-ttu-id="d9c8b-102">Implantar diretivas agendadas em várias instâncias</span><span class="sxs-lookup"><span data-stu-id="d9c8b-102">Deploy Scheduled Policies to Multiple Instances</span></span>
  <span data-ttu-id="d9c8b-103">Usando Servidores Registrados, você poderá implantar políticas agendadas em servidores gerenciados a partir de um local central.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-103">By using Registered Servers, you can deploy scheduled policies to managed servers from a central location.</span></span> <span data-ttu-id="d9c8b-104">Você poderá implantar diretivas agendadas a partir de um grupo de servidores local ou de um Servidor Central de Gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-104">You can deploy scheduled policies from either a local server group, or from a Central Management Server.</span></span>  
  
 <span data-ttu-id="d9c8b-105">Nesta tarefa, você fará o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d9c8b-105">In this task, you will do the following:</span></span>  
  
1.  <span data-ttu-id="d9c8b-106">Exportar as diretivas agendadas na tarefa anterior em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-106">Export the policies that you scheduled in the previous task to a folder.</span></span>  
  
2.  <span data-ttu-id="d9c8b-107">Implantar as diretivas agendadas nas instâncias de destino que são gerenciadas por meio de Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-107">Deploy the scheduled policies to target instances that are managed through Registered Servers.</span></span>  
  
 <span data-ttu-id="d9c8b-108">Você executará essas tarefas no computador em que concluiu as tarefas anteriores desta lição.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-108">You will perform these tasks on the computer where you completed the previous tasks in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d9c8b-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d9c8b-109">Prerequisites</span></span>  
 <span data-ttu-id="d9c8b-110">Esta tarefa tem os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="d9c8b-110">This task has the following prerequisites:</span></span>  
  
-   <span data-ttu-id="d9c8b-111">Você deve ter concluído as tarefas anteriores desta lição.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-111">You must have completed the previous tasks in this lesson.</span></span>  
  
-   <span data-ttu-id="d9c8b-112">As instâncias em que você implantará as diretivas agendadas deve estar executando o [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-112">The instances where you want to deploy the scheduled policies must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="d9c8b-113">A automação requer que as diretivas sejam armazenadas localmente, o que não tem suporte em versões do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] anteriores ao [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9c8b-113">Automation requires the policies to be stored locally, which is not supported on versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
-   <span data-ttu-id="d9c8b-114">Os servidores em que você deseja implantar as políticas agendadas devem ser registrados em servidores registrados no nó **grupos** de servidores locais ou **servidores de gerenciamento central** .</span><span class="sxs-lookup"><span data-stu-id="d9c8b-114">The servers where you want to deploy the scheduled policies must be registered in Registered Servers in either the **Local Server Groups** or the **Central Management Servers** node.</span></span> <span data-ttu-id="d9c8b-115">Para obter mais informações, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="d9c8b-115">For more information, see the following topics:</span></span>  
  
    -   [<span data-ttu-id="d9c8b-116">Criar ou editar um grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d9c8b-116">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
    -   <span data-ttu-id="d9c8b-117">[Registre um servidor conectado &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d9c8b-117">[Register a Connected Server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span></span>  
  
    -   [<span data-ttu-id="d9c8b-118">Criar um servidor de gerenciamento central e um grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d9c8b-118">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
### <a name="to-export-the-scheduled-policies-as-xml-files"></a><span data-ttu-id="d9c8b-119">Para exportar as diretivas agendadas como arquivos .xml</span><span class="sxs-lookup"><span data-stu-id="d9c8b-119">To export the scheduled policies as .xml files</span></span>  
  
1.  <span data-ttu-id="d9c8b-120">No servidor em que você configurou políticas agendadas na tarefa anterior, expanda **Gerenciamento**, **Gerenciamento de políticas**e, em seguida, clique em **políticas**.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-120">On the server where you configured scheduled policies in the previous task, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span>  
  
2.  <span data-ttu-id="d9c8b-121">No menu **Exibir** , clique em **Detalhes do Pesquisador de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-121">On the **View** menu, click **Object Explorer Details**.</span></span>  
  
3.  <span data-ttu-id="d9c8b-122">No painel **detalhes** do pesquisador de objetos, selecione todas as políticas de práticas recomendadas agendadas que você deseja implantar em outros servidores por meio de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-122">In the **Object Explorer Details** pane, select all the scheduled best practices policies that you want to deploy to other servers through Registered Servers.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d9c8b-123">Você pode clicar no título **categoria** para classificar as políticas por categoria.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-123">You can click the **Category** heading to sort the policies by category.</span></span>  
  
4.  <span data-ttu-id="d9c8b-124">Clique com o botão direito do mouse na seleção e clique em **Exportar política**.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-124">Right-click the selection, and then click **Export Policy**.</span></span>  
  
5.  <span data-ttu-id="d9c8b-125">Se você tiver selecionado várias políticas para exportar, na caixa de diálogo **Procurar pasta** , selecione uma pasta de destino ou crie uma nova pasta.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-125">If you selected multiple policies to export, in the **Browse For Folder** dialog box, select a destination folder, or create a new folder.</span></span> <span data-ttu-id="d9c8b-126">Nesta lição, crie uma nova pasta com o caminho **c:\ Scheduled_BP_Policies**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-126">For this lesson, create a new folder with the path **C:\Scheduled_BP_Policies**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d9c8b-127">Se você selecionou apenas uma política para exportar, na caixa de diálogo **Exportar política** , crie uma nova pasta com o caminho **c:\ Scheduled_BP_Policies**, clique em **abrir**e, em seguida, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-127">If you only selected one policy to export, in the **Export Policy** dialog box, create a new folder with the path **C:\Scheduled_BP_Policies**, click **Open**, and then click **Save**.</span></span>  
  
     <span data-ttu-id="d9c8b-128">Os arquivos de diretivas .xml são criados no local da pasta.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-128">The .xml policy files are created in the folder location.</span></span>  
  
### <a name="to-deploy-the-scheduled-policies-to-servers-that-are-managed-through-registered-servers"></a><span data-ttu-id="d9c8b-129">Para implantar as diretivas agendadas em servidores que são gerenciados por meio de Servidores Registrados</span><span class="sxs-lookup"><span data-stu-id="d9c8b-129">To deploy the scheduled policies to servers that are managed through Registered Servers</span></span>  
  
1.  <span data-ttu-id="d9c8b-130">No menu **Exibir** , clique em **Servidores Registrados**.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-130">On the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="d9c8b-131">Expanda **mecanismo de banco de dados**, expanda **grupos de servidores locais** ou **servidores de gerenciamento central**, clique com o botão direito do mouse no nó no qual você deseja implantar as políticas e clique em **importar políticas**.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-131">Expand **Database Engine**, expand either **Local Server Groups** or **Central Management Servers**, right-click the node that you want to deploy the policies to, and then click **Import Policies**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d9c8b-132">Se você clicar com o botão direito do mouse em **grupos de servidores locais** ou no próprio servidor de gerenciamento central, as políticas serão implantadas em todos os servidores gerenciados.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-132">If you right-click **Local Server Groups** or the Central Management Server itself, the policies will be deployed to all managed servers.</span></span> <span data-ttu-id="d9c8b-133">Se você clicar com o botão direito do mouse em um grupo específico de servidores, as diretivas serão implantadas somente nos servidores desse grupo.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-133">If you right-click a specific server group, the policies will only be deployed to servers in that group.</span></span> <span data-ttu-id="d9c8b-134">Se você clicar com o botão direito do mouse em um servidor registrado específico, as políticas serão implantadas nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-134">If you right-click a specific registered server, the policies will only be deployed to that server.</span></span>  
  
3.  <span data-ttu-id="d9c8b-135">Ao lado de **arquivos a serem importados**, clique no botão de reticências (**...**).</span><span class="sxs-lookup"><span data-stu-id="d9c8b-135">Next to **Files to import**, click the ellipsis button (**...**).</span></span>  
  
4.  <span data-ttu-id="d9c8b-136">Na caixa de diálogo **selecionar política** , navegue até o local da pasta onde você salvou as políticas agendadas.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-136">In the **Select Policy** dialog box, browse to the folder location where you saved the scheduled policies.</span></span> <span data-ttu-id="d9c8b-137">Para este exemplo, navegue até o local **c:\ Scheduled_BP_Policies**.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-137">For this example, browse to the location **C:\Scheduled_BP_Policies**.</span></span>  
  
5.  <span data-ttu-id="d9c8b-138">Selecione as políticas que você deseja importar para as instâncias de destino e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-138">Select the policies that you want to import to the target instances, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="d9c8b-139">Na caixa de diálogo **importar** , na lista **estado da política** , selecione o estado da política desejada.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-139">In the **Import** dialog box, in the **Policy state** list, select the desired policy state.</span></span> <span data-ttu-id="d9c8b-140">Você poderá optar por preservar o estado da diretiva, habilitar ou desabilitar as diretivas na importação.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-140">You can choose to preserve the policy state, enable, or disable the policies on import.</span></span> <span data-ttu-id="d9c8b-141">Lembre-se de que as diretivas devem ser habilitadas para execução em um agendamento.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-141">Be aware that the policies must be enabled to run on a schedule.</span></span>  
  
7.  <span data-ttu-id="d9c8b-142">Clique em **OK** para importar as políticas para todas as instâncias de destino.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-142">Click **OK** to import the policies to all the target instances.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d9c8b-143">Se houver erros, a caixa de diálogo **importar** não desaparecerá.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-143">If there are any errors, the **Import** dialog box does not disappear.</span></span> <span data-ttu-id="d9c8b-144">Clique na página **log** para examinar as mensagens.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-144">Click the **Log** page to review the messages.</span></span> <span data-ttu-id="d9c8b-145">Clique em **Cancelar** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-145">Click **Cancel** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="d9c8b-146">Para exibir as políticas de uma instância de destino, conecte-se à instância do, abra o pesquisador de objetos, expanda **Gerenciamento**e expanda **políticas**.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-146">To view the policies from a target instance, connect to the instance, open Object Explorer, expand **Management**, and then expand **Policies**.</span></span> <span data-ttu-id="d9c8b-147">Você deve ver as políticas importadas no nó **políticas** .</span><span class="sxs-lookup"><span data-stu-id="d9c8b-147">You should see the imported policies in the **Policies** node.</span></span> <span data-ttu-id="d9c8b-148">Se você clicar duas vezes em cada diretiva, poderá ver a agenda ou alterar as configurações.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-148">If you double-click each policy, you can view the schedule, or change the settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d9c8b-149">Para exibir os resultados da avaliação após a execução de uma diretiva agendada, abra o log Histórico da Diretiva na instância de destino.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-149">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="d9c8b-150">Para abrir o log, clique com o botão direito do mouse em **Gerenciamento de políticas**e clique em **Exibir histórico**.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-150">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="d9c8b-151">Resumo</span><span class="sxs-lookup"><span data-stu-id="d9c8b-151">Summary</span></span>  
 <span data-ttu-id="d9c8b-152">Este tutorial mostrou como executar avaliações sob demanda e planejadas das diretivas de práticas recomendadas em uma ou mais instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9c8b-152">This tutorial has shown you how to perform both on-demand and scheduled evaluations of the best practices policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="next"></a><span data-ttu-id="d9c8b-153">Avançar</span><span class="sxs-lookup"><span data-stu-id="d9c8b-153">Next</span></span>  
 <span data-ttu-id="d9c8b-154">Este tutorial está concluído.</span><span class="sxs-lookup"><span data-stu-id="d9c8b-154">This tutorial is finished.</span></span> <span data-ttu-id="d9c8b-155">Para retornar ao início, consulte [tutorial: avaliando práticas recomendadas usando o gerenciamento baseado em políticas](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="d9c8b-155">To return to the start, see [Tutorial: Evaluating Best Practices by Using Policy-Based Management](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="d9c8b-156">Para ver uma lista de [!INCLUDE[ssDE](../includes/ssde-md.md)] tutoriais, clique [mecanismo de banco de dados tutoriais](../relational-databases/database-engine-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="d9c8b-156">To see a list of [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorials, click [Database Engine Tutorials](../relational-databases/database-engine-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9c8b-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d9c8b-157">See Also</span></span>  
 [<span data-ttu-id="d9c8b-158">Administrar servidores com Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="d9c8b-158">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
