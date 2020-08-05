---
title: 'Etapa 1: compilar o utilitário de implantação | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1ff4dcff-89b3-4b99-a725-5f7963e98abf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3d32dcbf4bfcf9758dfe58803b75094d1807aa90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574116"
---
# <a name="step-1-building-the-deployment-utility"></a><span data-ttu-id="0ec6f-102">Etapa 1: Compilar o utilitário de implantação</span><span class="sxs-lookup"><span data-stu-id="0ec6f-102">Step 1: Building the Deployment Utility</span></span>
  <span data-ttu-id="0ec6f-103">Nesta tarefa, você configurará e compilará um utilitário de implantação para o projeto do Tutorial de Implantação.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-103">In this task, you will configure and build a deployment utility for the Deployment Tutorial project.</span></span>  
  
 <span data-ttu-id="0ec6f-104">Antes de compilar o utilitário de implantação, você deve modificar as propriedades do projeto do Tutorial de Implantação.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-104">Before you can build the deployment utility, you must modify the properties of the Deployment Tutorial project.</span></span> <span data-ttu-id="0ec6f-105">Você usará a caixa de diálogo **Páginas de Propriedades do Tutorial de Implantação** para configurar essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-105">You will use the **Deployment Tutorial Property Pages** dialog box to configure these properties.</span></span> <span data-ttu-id="0ec6f-106">Nesta caixa de diálogo, você deve habilitar o recurso para atualizar configurações durante a implantação e especificar que o processo de compilação gera um utilitário de implantação.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-106">In this dialog box, you must enable the ability to update configurations during deployment and specify that the build process generates a deployment utility.</span></span> <span data-ttu-id="0ec6f-107">Depois que você definir as propriedades, o projeto será compilado.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-107">After you set the properties, you will build the project.</span></span>  
  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="0ec6f-108">fornece um conjunto de janelas que você pode usar para depurar pacotes.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-108">provides a set of windows that you can use to debug packages.</span></span> <span data-ttu-id="0ec6f-109">Você pode visualizar mensagens de erro, de avisos e de informações, pode rastrear o status de pacotes em tempo de execução, ou pode visualizar o progresso e os resultados dos processos de compilação.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-109">You can view error, warning, and information messages, track about the status of packages at run time, or view the progress and results of build processes.</span></span> <span data-ttu-id="0ec6f-110">Nesta lição, você usará a janela Saída para visualizar o progresso e os resultados da compilação do utilitário de implantação.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-110">For this lesson, you will use the Output window to view the progress and results of building the deployment utility.</span></span>  
  
### <a name="to-set-the-deployment-utility-properties"></a><span data-ttu-id="0ec6f-111">Para definir as propriedades do utilitário de implantação</span><span class="sxs-lookup"><span data-stu-id="0ec6f-111">To set the deployment utility properties</span></span>  
  
1.  <span data-ttu-id="0ec6f-112">Se o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ainda não estiver aberto, clique em **Iniciar**, aponte para **Todos os Programas**, **Microsoft SQL Server**e clique em **Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-112">If [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="0ec6f-113">No menu **Arquivo** , clique em **Abrir**, em **Projeto/Solução**, clique na pasta **Tutorial de Implantação** , clique em **Abrir**e clique duas vezes em **Deployment Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-113">On the **File** menu, click **Open**, click **Project/Solution**, click the **Deployment Tutorial** folder and click **Open**, and then double-click **Deployment Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="0ec6f-114">No Gerenciador de Soluções, clique com o botão direito do mouse em Tutorial de Implantação e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-114">In Solution Explorer, right-click Deployment Tutorial and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="0ec6f-115">Na caixa de diálogo **Páginas de Propriedades do Tutorial de Implantação** , expanda Propriedades de Configurações e clique em Utilitário de Implantação.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-115">In the **Deployment Tutorial Property Pages** dialog box, expand Configuration Properties, and click Deployment Utility.</span></span>  
  
5.  <span data-ttu-id="0ec6f-116">No painel direito da caixa de diálogo **páginas de propriedades do tutorial de implantação** , verifique se `AllowConfigurationChanges` está definido como `true` , defina `CreateDeploymentUtility` como e, `true` opcionalmente, atualize o valor padrão de `DeploymentOutputPath` .</span><span class="sxs-lookup"><span data-stu-id="0ec6f-116">In the right pane of the **Deployment Tutorial Property Pages** dialog box, verify that `AllowConfigurationChanges` is set to `true`, set `CreateDeploymentUtility` to `true`, and optionally update the default value of `DeploymentOutputPath`.</span></span>  
  
6.  <span data-ttu-id="0ec6f-117">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-117">Click **OK**.</span></span>  
  
### <a name="to-build-the-deployment-utility"></a><span data-ttu-id="0ec6f-118">Para compilar o utilitário de implantação</span><span class="sxs-lookup"><span data-stu-id="0ec6f-118">To build the deployment utility</span></span>  
  
1.  <span data-ttu-id="0ec6f-119">No Gerenciador de Soluções, clique em **Tutorial de Implantação**.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-119">In Solution Explorer, click **Deployment Tutorial**.</span></span>  
  
2.  <span data-ttu-id="0ec6f-120">No menu **Exibir** , clique em **Saída**.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-120">On the **View** menu, click **Output**.</span></span> <span data-ttu-id="0ec6f-121">Por padrão, a janela Saída está localizada no canto esquerdo inferior do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ec6f-121">By default, the Output window is located in the bottom left corner of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="0ec6f-122">No menu **Criar** , clique em **Criar Tutorial de Implantação**.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-122">On the **Build** menu, click **Build Deployment Tutorial**.</span></span>  
  
4.  <span data-ttu-id="0ec6f-123">Na janela Saída, verifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="0ec6f-123">In the Output window, verify the following information:</span></span>  
  
     <span data-ttu-id="0ec6f-124">Compilação iniciada: Projeto do SQL Integration Services: Incremental ...</span><span class="sxs-lookup"><span data-stu-id="0ec6f-124">Build started: SQL Integration Services project: Incremental ...</span></span>  
  
     <span data-ttu-id="0ec6f-125">Criando utilitário de implantação...</span><span class="sxs-lookup"><span data-stu-id="0ec6f-125">Creating deployment utility...</span></span>  
  
     <span data-ttu-id="0ec6f-126">Utilitário de implantação criado.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-126">Deployment Utility created.</span></span>  
  
     <span data-ttu-id="0ec6f-127">Compilação concluída – 0 erros, 0 avisos</span><span class="sxs-lookup"><span data-stu-id="0ec6f-127">Build complete -- 0 errors, 0 warnings</span></span>  
  
     <span data-ttu-id="0ec6f-128">========== Compilação: 0 bem-sucedido, 0 com falha, 1 atualizado, 0 ignorado ==========</span><span class="sxs-lookup"><span data-stu-id="0ec6f-128">========== Build: 0 succeeded, 0 failed, 1 up-to-date, 0 skipped ==========</span></span>  
  
5.  <span data-ttu-id="0ec6f-129">No menu **Arquivo** , clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-129">On the **File** menu, click **Exit**.</span></span> <span data-ttu-id="0ec6f-130">Se for solicitado que você salve as alterações dos itens do Tutorial de Implantação, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-130">If prompted to save changes to Deployment Tutorial items, click **Yes**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0ec6f-131">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="0ec6f-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0ec6f-132">Etapa 2: Verificando o pacote de implantação</span><span class="sxs-lookup"><span data-stu-id="0ec6f-132">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
<span data-ttu-id="0ec6f-133">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="0ec6f-133">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="0ec6f-134">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="0ec6f-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="0ec6f-135">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="0ec6f-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="0ec6f-136">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="0ec6f-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec6f-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ec6f-137">See Also</span></span>  
 [<span data-ttu-id="0ec6f-138">Criar um utilitário de implantação</span><span class="sxs-lookup"><span data-stu-id="0ec6f-138">Create a Deployment Utility</span></span>](../../2014/integration-services/create-a-deployment-utility.md)  
  
  
