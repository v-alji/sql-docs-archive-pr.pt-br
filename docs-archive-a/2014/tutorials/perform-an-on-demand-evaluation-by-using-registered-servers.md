---
title: Executar uma avaliação sob demanda usando servidores registrados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: c14034ef-6e0b-4df5-8072-bfb8d90b3172
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a3a06efaabff7e94e5b560744f0e1c739831042a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568962"
---
# <a name="perform-an-on-demand-evaluation-by-using-registered-servers"></a><span data-ttu-id="02f51-102">Realize uma avaliação sob demanda usando servidores registrados</span><span class="sxs-lookup"><span data-stu-id="02f51-102">Perform an On-Demand Evaluation by Using Registered Servers</span></span>

  <span data-ttu-id="02f51-103">Você pode realizar uma avaliação sob demanda de políticas de práticas recomendadas em relação a uma ou mais instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usando Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="02f51-103">You can perform an on-demand evaluation of best practices policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by using Registered Servers.</span></span> <span data-ttu-id="02f51-104">Você pode usar grupos de servidores locais ou um servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="02f51-104">You can use either local server groups or a central management server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02f51-105">Você pode realizar uma avaliação sob demanda de políticas de práticas recomendadas em relação a membros de grupo de servidores que estão executando o [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] ou uma versão posterior do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02f51-105">You can perform an on-demand evaluation of best practices policies against server group members that are running [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] or a later version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="02f51-106">No entanto, você pode receber um erro de exceção se houver algumas propriedades referidas por uma política que não tem suporte no [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] ou [!INCLUDE[ssVersion2000](../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02f51-106">However, you may receive an exception error if there are some properties that are referred to by a policy that are not supported in [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] or [!INCLUDE[ssVersion2000](../includes/ssversion2000-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="02f51-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="02f51-107">Prerequisites</span></span>  
 <span data-ttu-id="02f51-108">Para realizar essa tarefa, você deve configurar um ou mais registros de servidor em Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="02f51-108">To perform this task, you must have configured one or more server registrations in Registered Servers.</span></span> <span data-ttu-id="02f51-109">Para obter mais informações, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="02f51-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="02f51-110">Criar ou editar um grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="02f51-110">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
-   <span data-ttu-id="02f51-111">[Registre um servidor conectado &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="02f51-111">[Register a Connected Server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span></span>  
  
-   [<span data-ttu-id="02f51-112">Criar um servidor de gerenciamento central e um grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="02f51-112">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
### <a name="to-evaluate-best-practices-policies-against-a-server-group"></a><span data-ttu-id="02f51-113">Para avaliar políticas de práticas recomendadas em relação a um grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="02f51-113">To evaluate best practices policies against a server group</span></span>  
  
1.  <span data-ttu-id="02f51-114">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], no menu **Exibir** , clique em **Servidores Registrados**.</span><span class="sxs-lookup"><span data-stu-id="02f51-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="02f51-115">Expanda **mecanismo de banco de dados**e, em seguida, expanda **grupos de servidores locais**ou **servidores de gerenciamento central**, dependendo de sua configuração.</span><span class="sxs-lookup"><span data-stu-id="02f51-115">Expand **Database Engine**, and then expand either **Local Server Groups**, or **Central Management Servers**, depending on your configuration.</span></span>  
  
3.  <span data-ttu-id="02f51-116">Execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="02f51-116">Do either of the following:</span></span>  
  
    -   <span data-ttu-id="02f51-117">Para avaliar as políticas em relação a todos os servidores gerenciados pelo grupo de servidores local ou do servidor de gerenciamento central, clique com o botão direito do mouse no nome do grupo de servidores locais ou no nome do servidor de gerenciamento central e clique em **avaliar políticas**.</span><span class="sxs-lookup"><span data-stu-id="02f51-117">To evaluate the policies against all servers that are managed by the local server group or the central management server, right-click the local server group name or the central management server name, and then click **Evaluate Policies**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="02f51-118">Quando você avaliar políticas através de um servidor de gerenciamento central, as políticas não serão avaliadas em relação ao próprio servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="02f51-118">When you evaluate policies through a central management server, the policies are not evaluated against the central management server itself.</span></span>  
  
    -   <span data-ttu-id="02f51-119">Para avaliar as políticas em relação a um servidor ou grupo de servidores específico, expanda **grupos de servidores locais** ou o nome do servidor de gerenciamento central, clique com o botão direito do mouse no servidor ou grupo de servidores do qual você deseja avaliar políticas e clique em **avaliar políticas**.</span><span class="sxs-lookup"><span data-stu-id="02f51-119">To evaluate the policies against a specific server or server group, expand **Local Server Groups** or the central management server name, right-click the server or server group that you want to evaluate policies against, and then click **Evaluate Policies**.</span></span>  
  
4.  <span data-ttu-id="02f51-120">Na caixa de diálogo **avaliar políticas** , ao lado da caixa **origem** , clique no botão de reticências (**...**).</span><span class="sxs-lookup"><span data-stu-id="02f51-120">In the **Evaluate Policies** dialog box, next to the **Source** box, click the ellipsis (**...**) button.</span></span>  
  
5.  <span data-ttu-id="02f51-121">Na caixa de diálogo **selecionar origem** , você pode selecionar **arquivos** ou **servidor** como a origem dos arquivos de política a serem avaliados.</span><span class="sxs-lookup"><span data-stu-id="02f51-121">In the **Select Source** dialog box, you can select either **Files** or **Server** as the source of the policy files to evaluate.</span></span> <span data-ttu-id="02f51-122">Se você clicar em **servidor**, poderá executar uma avaliação sob demanda de todas as políticas de práticas recomendadas que foram importadas anteriormente para o gerenciamento baseado em políticas em um servidor local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="02f51-122">If you click **Server**, you can perform an on-demand evaluation of any best practices policies that were previously imported into Policy-Based Management on a local or remote server.</span></span> <span data-ttu-id="02f51-123">Neste tutorial, você clicará em **arquivos**e, em seguida, selecionará os arquivos de política individuais que deseja avaliar.</span><span class="sxs-lookup"><span data-stu-id="02f51-123">In this tutorial, you will click **Files**, and then select the individual policy files that you want to evaluate.</span></span> <span data-ttu-id="02f51-124">Para fazer isso, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="02f51-124">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="02f51-125">Clique em **arquivos**.</span><span class="sxs-lookup"><span data-stu-id="02f51-125">Click **Files**.</span></span>  
  
    2.  <span data-ttu-id="02f51-126">Ao lado de **arquivos**, clique no botão de reticências (**...**).</span><span class="sxs-lookup"><span data-stu-id="02f51-126">Next to **Files**, click the ellipsis (**...**) button.</span></span>  
  
    3.  <span data-ttu-id="02f51-127">Selecione um ou mais arquivos de política. XML a serem avaliados e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="02f51-127">Select one or more .xml policy files to evaluate, and then click **Open**.</span></span>  
  
         <span data-ttu-id="02f51-128">A lista de arquivos selecionados aparece na caixa **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="02f51-128">The list of selected files appears in the **Files** box.</span></span>  
  
    4.  <span data-ttu-id="02f51-129">Na caixa de diálogo **selecionar origem** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="02f51-129">In the **Select Source** dialog box, click **OK**.</span></span>  
  
    5.  <span data-ttu-id="02f51-130">Se a caixa de diálogo **carregando políticas** for exibida, clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="02f51-130">If the **Loading Policies** dialog box appears, click **Close**.</span></span>  
  
     <span data-ttu-id="02f51-131">As políticas que você selecionou são listadas na página **seleção de política** .</span><span class="sxs-lookup"><span data-stu-id="02f51-131">The policies that you selected are listed on the **Policy Selection** page.</span></span> <span data-ttu-id="02f51-132">Observe que um ícone de aviso ao lado de uma política indica que a política contém scripts.</span><span class="sxs-lookup"><span data-stu-id="02f51-132">Be aware that a warning icon next to a policy indicates that the policy contains scripts.</span></span>  
  
6.  <span data-ttu-id="02f51-133">Clique em **avaliar** para avaliar as políticas.</span><span class="sxs-lookup"><span data-stu-id="02f51-133">Click **Evaluate** to evaluate the policies.</span></span>  
  
7.  <span data-ttu-id="02f51-134">Para algumas falhas de política, o Gerenciamento Baseado em Políticas permite aplicar ações de conformidade com políticas no destino imediatamente.</span><span class="sxs-lookup"><span data-stu-id="02f51-134">For some policy failures, Policy-Based Management enables you to immediately enforce policy compliance on the target.</span></span> <span data-ttu-id="02f51-135">Para esse tipo de falha, uma caixa de seleção será exibida ao lado da política com falha.</span><span class="sxs-lookup"><span data-stu-id="02f51-135">For such failures, a check box will appear next to the failed policy.</span></span> <span data-ttu-id="02f51-136">Se você marcar a caixa de seleção ou clicar na linha com a política com falha, as caixas de seleção aparecerão no painel **detalhes de destino** ao lado das instâncias de destino que falharam na avaliação.</span><span class="sxs-lookup"><span data-stu-id="02f51-136">If you select the check box, or click the row with the failed policy, check boxes appear in the **Target details** pane next to the target instances that failed the evaluation.</span></span> <span data-ttu-id="02f51-137">Se qualquer uma das caixas de seleção estiver selecionada, o botão **aplicar** ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="02f51-137">If any of the check boxes are selected, the **Apply** button becomes available.</span></span> <span data-ttu-id="02f51-138">Quando você clica em **aplicar**, a configuração não compatível será atualizada automaticamente nas instâncias de destino que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="02f51-138">When you click **Apply**, the noncompliant setting will be automatically updated on the target instances that you selected.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="02f51-139">Tenha certeza de que você entende a configuração de política perfeitamente antes de atualizar uma instância de destino automaticamente.</span><span class="sxs-lookup"><span data-stu-id="02f51-139">Make sure that you fully understand the policy setting before automatically updating a target instance.</span></span> <span data-ttu-id="02f51-140">Recomendamos que, depois de selecionar uma ou mais caixas de seleção, você clique em **script**e escolha um local de saída para poder examinar o [!INCLUDE[tsql](../includes/tsql-md.md)] código subjacente antes de aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="02f51-140">We recommend that after you select one or more check boxes, you click **Script**, and choose an output location so that you can review the underlying [!INCLUDE[tsql](../includes/tsql-md.md)] code before you apply the changes.</span></span>  
  
8.  <span data-ttu-id="02f51-141">Para exibir resultados detalhados de uma política, clique na política na tabela de **resultados** .</span><span class="sxs-lookup"><span data-stu-id="02f51-141">To view detailed results for a policy, click the policy in the **Results** table.</span></span> <span data-ttu-id="02f51-142">A tabela **detalhes de destino** mostra os detalhes de cada instância.</span><span class="sxs-lookup"><span data-stu-id="02f51-142">The **Target details** table shows the details for each instance.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="02f51-143">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="02f51-143">Next Lesson</span></span>  
 [<span data-ttu-id="02f51-144">Lição 2: Avaliar políticas de melhores práticas de forma agendada</span><span class="sxs-lookup"><span data-stu-id="02f51-144">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>](../../2014/tutorials/lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis.md)  
  
## <a name="see-also"></a><span data-ttu-id="02f51-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="02f51-145">See Also</span></span>  
 <span data-ttu-id="02f51-146">[Monitorar e impor práticas recomendadas usando o gerenciamento baseado em políticas](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="02f51-146">[Monitor and Enforce Best Practices by Using Policy-Based Management](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md) </span></span>  
 [<span data-ttu-id="02f51-147">Administrar vários servidores usando servidores de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="02f51-147">Administer Multiple Servers Using Central Management Servers</span></span>](../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
