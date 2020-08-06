---
title: Executar uma avaliação sob demanda usando o pesquisador de objetos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: ee6d3b79-18bc-49d3-8a1d-0c0905b990f0
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e32876978ac462af361986d84e11ef3dc0f278e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568961"
---
# <a name="perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="c4537-102">Realize uma avaliação sob demanda usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="c4537-102">Perform an On-Demand Evaluation by Using Object Explorer</span></span>
  <span data-ttu-id="c4537-103">Nesta tarefa, você usará o Pesquisador de Objetos para realizar uma avaliação sob demanda das políticas de práticas recomendadas para o [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] em uma única instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4537-103">In this task, you will use Object Explorer to perform an on-demand evaluation of best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4537-104">Você também pode avaliar políticas em uma única instância através de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="c4537-104">You can also evaluate policies on a single instance through Registered Servers.</span></span> <span data-ttu-id="c4537-105">Para obter mais informações, consulte [executar uma avaliação sob demanda usando servidores registrados](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span><span class="sxs-lookup"><span data-stu-id="c4537-105">For more information, see [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c4537-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c4537-106">Prerequisites</span></span>  
 <span data-ttu-id="c4537-107">Esta lição baseia-se na versão do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4537-107">This lesson is based on the version of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4537-108">Para executar uma avaliação sob demanda das políticas de práticas recomendadas em relação a instâncias que estão em execução [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] , você deve usar o procedimento no tópico [executar uma avaliação sob demanda usando servidores registrados](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span><span class="sxs-lookup"><span data-stu-id="c4537-108">To perform an on-demand evaluation of best practices policies against instances that are running [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you must use the procedure in the topic [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
### <a name="to-perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="c4537-109">Para realizar uma avaliação sob demanda usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="c4537-109">To perform an on-demand evaluation by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="c4537-110">Inicie o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]e conecte-se ao [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4537-110">Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c4537-111">No Pesquisador de objetos, expanda **Gerenciamento**, **Gerenciamento de políticas**, clique com o botão direito do mouse em **políticas**e clique em **avaliar**.</span><span class="sxs-lookup"><span data-stu-id="c4537-111">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Policies**, and then click **Evaluate**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4537-112">Por padrão, a instância local é usada como a origem das políticas.</span><span class="sxs-lookup"><span data-stu-id="c4537-112">By default, the local instance is used as the source of the policies.</span></span> <span data-ttu-id="c4537-113">Se você importou políticas de práticas recomendadas previamente, elas serão listadas, junto com qualquer outra política que você criou.</span><span class="sxs-lookup"><span data-stu-id="c4537-113">If you have previously imported best practices policies, they will be listed, together with any other policies that you have created.</span></span> <span data-ttu-id="c4537-114">Você pode selecionar qualquer uma das políticas de práticas recomendadas importadas e, em seguida, clicar em **avaliar**.</span><span class="sxs-lookup"><span data-stu-id="c4537-114">You can select any of the imported best practices policies, and then click **Evaluate**.</span></span> <span data-ttu-id="c4537-115">Se você não importou as políticas de práticas recomendadas, continue com este procedimento.</span><span class="sxs-lookup"><span data-stu-id="c4537-115">If you have not imported the best practices policies, continue with this procedure.</span></span>  
  
3.  <span data-ttu-id="c4537-116">Na caixa de diálogo **avaliar políticas** , ao lado da caixa **origem** , clique no botão de reticências (**...**).</span><span class="sxs-lookup"><span data-stu-id="c4537-116">In the **Evaluate Policies** dialog box, next to the **Source** box, click the ellipsis (**...**) button.</span></span>  
  
4.  <span data-ttu-id="c4537-117">Na caixa de diálogo **selecionar origem** , você pode selecionar **arquivos** ou **servidor** como a origem dos arquivos de política a serem avaliados.</span><span class="sxs-lookup"><span data-stu-id="c4537-117">In the **Select Source** dialog box, you can select either **Files** or **Server** as the source of the policy files to evaluate.</span></span> <span data-ttu-id="c4537-118">Se você clicar em **servidor**, poderá executar uma avaliação sob demanda de todas as políticas de práticas recomendadas que foram importadas anteriormente para o gerenciamento baseado em políticas em um servidor local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="c4537-118">If you click **Server**, you can perform an on-demand evaluation of any best practices policies that were previously imported into Policy-Based Management on a local or remote server.</span></span> <span data-ttu-id="c4537-119">Neste tutorial, você clicará em **arquivos**e, em seguida, selecionará os arquivos de política individuais que deseja avaliar.</span><span class="sxs-lookup"><span data-stu-id="c4537-119">In this tutorial, you will click **Files**, and then select the individual policy files that you want to evaluate.</span></span> <span data-ttu-id="c4537-120">Para fazer isso, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c4537-120">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="c4537-121">Clique em **arquivos**.</span><span class="sxs-lookup"><span data-stu-id="c4537-121">Click **Files**.</span></span>  
  
    2.  <span data-ttu-id="c4537-122">Ao lado de **arquivos**, clique no botão de reticências (**...**).</span><span class="sxs-lookup"><span data-stu-id="c4537-122">Next to **Files**, click the ellipsis (**...**) button.</span></span>  
  
    3.  <span data-ttu-id="c4537-123">Na caixa de diálogo **selecionar política** , navegue até a seguinte pasta, que contém as políticas de práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="c4537-123">In the **Select Policy** dialog box, browse to the following folder, which contains the best practices policies:</span></span>  
  
         <span data-ttu-id="c4537-124">**C:\Arquivos de Programas (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="c4537-124">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c4537-125">O caminho do arquivo pode variar, dependendo de onde você instalou os arquivos de programa do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , do sistema operacional em execução (32 bits ou 64 bits) e do identificador de idioma.</span><span class="sxs-lookup"><span data-stu-id="c4537-125">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
    4.  <span data-ttu-id="c4537-126">Selecione um ou mais arquivos de política. XML a serem avaliados e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="c4537-126">Select one or more .xml policy files to evaluate, and then click **Open**.</span></span>  
  
         <span data-ttu-id="c4537-127">A lista de arquivos selecionados aparece na caixa **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="c4537-127">The list of selected files appears in the **Files** box.</span></span>  
  
    5.  <span data-ttu-id="c4537-128">Na caixa de diálogo **selecionar origem** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4537-128">In the **Select Source** dialog box, click **OK**.</span></span>  
  
    6.  <span data-ttu-id="c4537-129">Se a caixa de diálogo **carregando políticas** for exibida, clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="c4537-129">If the **Loading Policies** dialog box appears, click **Close**.</span></span>  
  
     <span data-ttu-id="c4537-130">As políticas que você selecionou são listadas na página **seleção de política** .</span><span class="sxs-lookup"><span data-stu-id="c4537-130">The policies that you selected are listed on the **Policy Selection** page.</span></span> <span data-ttu-id="c4537-131">Observe que um ícone de aviso ao lado de uma política indica que a política contém scripts.</span><span class="sxs-lookup"><span data-stu-id="c4537-131">Be aware that a warning icon next to a policy indicates that the policy contains scripts.</span></span>  
  
5.  <span data-ttu-id="c4537-132">Clique em **avaliar** para avaliar as políticas.</span><span class="sxs-lookup"><span data-stu-id="c4537-132">Click **Evaluate** to evaluate the policies.</span></span>  
  
     <span data-ttu-id="c4537-133">Na tabela de **resultados** , os resultados de cada política são listados.</span><span class="sxs-lookup"><span data-stu-id="c4537-133">In the **Results** table, the results for each policy are listed.</span></span> <span data-ttu-id="c4537-134">Um ícone "x" vermelho indica falha na conformidade com a política.</span><span class="sxs-lookup"><span data-stu-id="c4537-134">A red "x" icon indicates that policy compliance failed.</span></span>  
  
6.  <span data-ttu-id="c4537-135">Para algumas falhas de política, o Gerenciamento Baseado em Políticas permite aplicar ações de conformidade com políticas no destino imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c4537-135">For some policy failures, Policy-Based Management enables you to immediately enforce policy compliance on the target.</span></span> <span data-ttu-id="c4537-136">Para esse tipo de falha, uma caixa de seleção será exibida ao lado da política com falha.</span><span class="sxs-lookup"><span data-stu-id="c4537-136">For such failures, a check box will appear next to the failed policy.</span></span> <span data-ttu-id="c4537-137">Se você marcar a caixa de seleção, o botão **aplicar** ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="c4537-137">If you select the check box, the **Apply** button becomes available.</span></span> <span data-ttu-id="c4537-138">Quando você clica em **aplicar**, a configuração não compatível será atualizada automaticamente na instância de destino.</span><span class="sxs-lookup"><span data-stu-id="c4537-138">When you click **Apply**, the noncompliant setting will be automatically updated on the target instance.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="c4537-139">Tenha certeza de que você entende a configuração de política perfeitamente antes de atualizar uma instância de destino automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c4537-139">Make sure that you fully understand the policy setting before automatically updating a target instance.</span></span> <span data-ttu-id="c4537-140">Recomendamos que, depois de selecionar uma ou mais caixas de seleção, você clique em **script**e escolha um local de saída para poder examinar o [!INCLUDE[tsql](../includes/tsql-md.md)] código subjacente antes de aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c4537-140">We recommend that after you select one or more check boxes, you click **Script**, and choose an output location so that you can review the underlying [!INCLUDE[tsql](../includes/tsql-md.md)] code before you apply the changes.</span></span>  
  
7.  <span data-ttu-id="c4537-141">Para exibir resultados detalhados de uma política, clique na política na tabela de **resultados** .</span><span class="sxs-lookup"><span data-stu-id="c4537-141">To view detailed results for a policy, click the policy in the **Results** table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c4537-142">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="c4537-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c4537-143">Realize uma avaliação sob demanda usando servidores registrados</span><span class="sxs-lookup"><span data-stu-id="c4537-143">Perform an On-Demand Evaluation by Using Registered Servers</span></span>](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md)  
  
  
