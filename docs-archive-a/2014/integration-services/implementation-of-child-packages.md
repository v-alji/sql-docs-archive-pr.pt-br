---
title: Implementação de pacotes filho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- child packages
ms.assetid: ab0c09d7-ce2e-487d-a1ed-a4b5adb6cc01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4fa4fa7c523c55c595341c7aee6a530c5918a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680037"
---
# <a name="implementation-of-child-packages"></a><span data-ttu-id="a1c33-102">Implementação de pacotes filho</span><span class="sxs-lookup"><span data-stu-id="a1c33-102">Implementation of Child Packages</span></span>
  <span data-ttu-id="a1c33-103">Quando você implementa balanceamento de carga usando o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], os pacotes filho são instalados em outros servidores para aproveitar a CPU disponível ou o tempo do servidor.</span><span class="sxs-lookup"><span data-stu-id="a1c33-103">When you implement load balancing using [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], child packages are installed on other servers to take advantage of the available CPU or server time.</span></span> <span data-ttu-id="a1c33-104">Para criar e executar os pacotes filho são necessárias as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a1c33-104">To create and run the child packages requires the following steps:</span></span>  
  
-   <span data-ttu-id="a1c33-105">Criar os pacotes filho.</span><span class="sxs-lookup"><span data-stu-id="a1c33-105">Designing the child packages.</span></span>  
  
-   <span data-ttu-id="a1c33-106">Mover os pacotes para o servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="a1c33-106">Moving the packages to the remote server.</span></span>  
  
-   <span data-ttu-id="a1c33-107">Criar um trabalho do SQL Server Agent no servidor remoto que contém uma etapa que executa o pacote filho.</span><span class="sxs-lookup"><span data-stu-id="a1c33-107">Creating a SQL Server Agent Job on the remote server that contains a step that runs the child package.</span></span>  
  
-   <span data-ttu-id="a1c33-108">Testar e depurar o trabalho do SQL Server Agent e os pacotes filho.</span><span class="sxs-lookup"><span data-stu-id="a1c33-108">Testing and debugging the SQL Server Agent Job and child packages.</span></span>  
  
 <span data-ttu-id="a1c33-109">Quando você cria pacotes filho, os pacotes não têm nenhuma limitação em sua criação e é possível inserir qualquer funcionalidade desejada.</span><span class="sxs-lookup"><span data-stu-id="a1c33-109">When you design the child packages, the packages have no limitations in their design, and you can put in any functionality you desire.</span></span> <span data-ttu-id="a1c33-110">Entretanto, se o pacote acessar dados, será necessário verificar se o servidor que executa o pacote tem acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="a1c33-110">However, if the package accesses data, you must ensure that the server that runs the package has access to the data.</span></span>  
  
 <span data-ttu-id="a1c33-111">Para identificar o pacote pai que executa pacotes filho, em [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , clique com o botão direito do mouse no pacote no Gerenciador de Soluções e clique em **Pacote de Ponto de Entrada**.</span><span class="sxs-lookup"><span data-stu-id="a1c33-111">To identify the parent package that executes child packages, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] right click the package in Solution Explorer and then click **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="a1c33-112">Depois que os pacotes filho são criados, a próxima etapa é implantá-los nos servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="a1c33-112">After the child packages have been designed, the next step is to deploy them on the remote servers.</span></span>  
  
## <a name="moving-the-child-package-to-the-remote-instance"></a><span data-ttu-id="a1c33-113">Mover o pacote filho para uma instância remota</span><span class="sxs-lookup"><span data-stu-id="a1c33-113">Moving the Child Package to the Remote Instance</span></span>  
 <span data-ttu-id="a1c33-114">Há várias maneiras de mover os pacotes para outros servidores.</span><span class="sxs-lookup"><span data-stu-id="a1c33-114">There are multiple ways to move packages to other servers.</span></span> <span data-ttu-id="a1c33-115">Os dois métodos sugeridos são:</span><span class="sxs-lookup"><span data-stu-id="a1c33-115">The two suggested methods are:</span></span>  
  
-   <span data-ttu-id="a1c33-116">Exportar os pacotes usando o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1c33-116">Exporting packages by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="a1c33-117">Implantar os pacotes compilando um utilitário de implantação para o projeto que contém os pacotes que você deseja implantar e, depois, executar o Assistente de Instalação de Pacotes para instalar os pacotes no sistema de arquivos ou em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1c33-117">Deploying packages by building a deployment utility for the project that contains the packages you want to deploy, and then running the Package Installation Wizard to install the packages to the file system or to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a1c33-118">Para obter mais informações, consulte [implantação de pacote &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="a1c33-118">For more information, see [Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md).</span></span>  
  
 <span data-ttu-id="a1c33-119">Você precisa repetir a implantação em cada servidor remoto que desejar usar.</span><span class="sxs-lookup"><span data-stu-id="a1c33-119">You must repeat the deployment to each remote server you want to use.</span></span>  
  
## <a name="creating-the-sql-server-agent-jobs"></a><span data-ttu-id="a1c33-120">Criar trabalhos do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="a1c33-120">Creating the SQL Server Agent Jobs</span></span>  
 <span data-ttu-id="a1c33-121">Depois que os pacotes filho forem implantados em vários servidores, crie um trabalho do SQL Server Agent em cada servidor que contém um pacote filho.</span><span class="sxs-lookup"><span data-stu-id="a1c33-121">After the child packages have been deployed to the various servers, create a SQL Server Agent job on each server that contains a child package.</span></span> <span data-ttu-id="a1c33-122">O trabalho do SQL Server Agent possui uma etapa que executa o pacote filho quando o agente de trabalhos é chamado.</span><span class="sxs-lookup"><span data-stu-id="a1c33-122">The SQL Server Agent job contains a step that runs the child package when the job agent is called.</span></span> <span data-ttu-id="a1c33-123">Os trabalhos do SQL Server Agent não são trabalhos agendados; eles executam os pacotes filho somente quando são chamados pelo pacote pai.</span><span class="sxs-lookup"><span data-stu-id="a1c33-123">The SQL Server Agent jobs are not scheduled jobs; they run the child packages only when they are called by the parent package.</span></span> <span data-ttu-id="a1c33-124">A notificação de êxito ou falha do trabalho no pacote pai reflete o sucesso ou a falha do trabalho do SQL Server Agent e se ele foi chamado com êxito, e não o êxito ou o fracasso do pacote filho ou se ele foi executado.</span><span class="sxs-lookup"><span data-stu-id="a1c33-124">Notification of success or failure of the job back to the parent package reflects the success or failure of the SQL Server Agent job and whether it was called successfully, not the success or failure of the child package or whether it was executed.</span></span>  
  
## <a name="debugging-the-sql-server-agent-jobs-and-child-packages"></a><span data-ttu-id="a1c33-125">Depurar os trabalhos do SQL Server Agent e os pacotes filho</span><span class="sxs-lookup"><span data-stu-id="a1c33-125">Debugging the SQL Server Agent Jobs and Child Packages</span></span>  
 <span data-ttu-id="a1c33-126">Você pode testar os trabalhos do SQL Server Agent e seus pacotes filho usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="a1c33-126">You can test the SQL Server Agent jobs and their child packages by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="a1c33-127">Executando cada pacote filho no Designer SSIS, clicando em **depurar**  /  **Iniciar sem depuração**.</span><span class="sxs-lookup"><span data-stu-id="a1c33-127">Running each child package in SSIS Designer, by clicking **Debug** / **Start Without Debugging**.</span></span>  
  
-   <span data-ttu-id="a1c33-128">Executar o trabalho individual do SQL Server Agent no computador remoto usando o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]para garantir que o pacote seja executado.</span><span class="sxs-lookup"><span data-stu-id="a1c33-128">Running the individual SQL Server Agent job on the remote computer by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to make sure that the package runs.</span></span>  
  
 <span data-ttu-id="a1c33-129">Para obter informações sobre como resolver problemas de pacotes executados nos trabalhos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, consulte [Um pacote SSIS não é executado quando você chama o pacote SSIS a partir de um trabalho do SQL Server Agent](https://support.microsoft.com/kb/918760) na Base de Dados de Conhecimento de Suporte da [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1c33-129">For information about how to troubleshoot packages that you run from [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs, see [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760) in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Support Knowledge Base.</span></span>  
  
 <span data-ttu-id="a1c33-130">O SQL Server Agent realiza verificações no acesso do subsistema para um proxy e fornece acesso ao proxy toda vez que a etapa do trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="a1c33-130">The SQL Server Agent checks subsystem access for a proxy and gives access to the proxy every time the job step runs.</span></span>  
  
 <span data-ttu-id="a1c33-131">Você pode criar um proxy no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1c33-131">You can create a proxy in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a1c33-132">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a1c33-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a1c33-133">Executar um pacote no servidor SSIS usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a1c33-133">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="a1c33-134">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="a1c33-134">Related Content</span></span>  
  
-   <span data-ttu-id="a1c33-135">Entrada de blog, [SSIS: acessando variáveis em um pacote pai](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/), em andyleonard. blog.</span><span class="sxs-lookup"><span data-stu-id="a1c33-135">Blog entry, [SSIS: Accessing variables in a parent package](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/), on andyleonard.blog.</span></span>  
  
-   <span data-ttu-id="a1c33-136">Artigo, [tarefa Executar Pacote](../integration-services/control-flow/execute-package-task.md).</span><span class="sxs-lookup"><span data-stu-id="a1c33-136">Article, [Execute Package Task](../integration-services/control-flow/execute-package-task.md).</span></span>  
  
  
