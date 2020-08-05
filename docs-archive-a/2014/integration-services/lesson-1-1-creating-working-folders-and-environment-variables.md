---
title: 'Etapa 1: criando pastas de trabalho e variáveis de ambiente | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 45091ba2-ea3d-4399-9814-489d812b42cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 63308d406e230538e5ca8b90dbb55bb802759bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574151"
---
# <a name="step-1-creating-working-folders-and-environment-variables"></a><span data-ttu-id="2280f-102">Etapa 1: Criar pastas de trabalho e variáveis de ambiente</span><span class="sxs-lookup"><span data-stu-id="2280f-102">Step 1: Creating Working Folders and Environment Variables</span></span>
  <span data-ttu-id="2280f-103">Nesta tarefa, você criará a pasta de trabalho (C:\DeploymentTutorial) e as novas variáveis de ambiente do sistema (`DataTransfer` e `LoadXMLData`), que serão usadas em tarefas posteriores do tutorial.</span><span class="sxs-lookup"><span data-stu-id="2280f-103">In this task, you will create the working folder (C:\DeploymentTutorial) and the new system environment variables (`DataTransfer` and `LoadXMLData`) that you will use in later tutorial tasks.</span></span>  
  
 <span data-ttu-id="2280f-104">A pasta de trabalho está na raiz da unidade C.</span><span class="sxs-lookup"><span data-stu-id="2280f-104">The working folder is at the root of the C drive.</span></span> <span data-ttu-id="2280f-105">Se você precisar usar uma unidade ou um local diferente, poderá fazer isso.</span><span class="sxs-lookup"><span data-stu-id="2280f-105">If you must use a different drive or location, you can do that.</span></span> <span data-ttu-id="2280f-106">Porém, será necessário anotar esse local e usá-lo sempre que o tutorial se referir ao local da pasta de trabalho DeploymentTutorial.</span><span class="sxs-lookup"><span data-stu-id="2280f-106">However, you need to note this location and then use it wherever the tutorial refers to the location of the DeploymentTutorial working folder.</span></span>  
  
 <span data-ttu-id="2280f-107">Em uma lição posterior, você implantará os pacotes salvos no sistema de arquivos na tabela sysssispackages no banco de dados msdb do[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2280f-107">In a later lesson, you will deploy packages that are saved to the file system to the sysssispackages table in the msdb[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="2280f-108">O ideal seria implantar os pacotes [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] em um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="2280f-108">Ideally you will deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to a different computer.</span></span> <span data-ttu-id="2280f-109">Se isso não for possível, você ainda poderá aprender muito fazendo esse tutorial para implantar os pacotes em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que estiver no computador local.</span><span class="sxs-lookup"><span data-stu-id="2280f-109">If that is not possible, you can still learn a lot from doing this tutorial by deploying the packages to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is on the local computer.</span></span> <span data-ttu-id="2280f-110">As variáveis de ambiente usadas nos computadores local e de destino têm os mesmos nomes de variável, mas são armazenados valores diferentes nas variáveis.</span><span class="sxs-lookup"><span data-stu-id="2280f-110">The environment variables that are used on the local and destination computers have the same variable names, but different values are stored in the variables.</span></span> <span data-ttu-id="2280f-111">Por exemplo, no computador local, o valor da variável do ambiente `DataTransfer` se refere à pasta C:\DeploymentTutorial, enquanto que no computador de destino a variável do ambiente `DataTransfer` se refere à pasta C:\DeploymentTutorialInstall.</span><span class="sxs-lookup"><span data-stu-id="2280f-111">For example, on the local computer, the value of the environment variable `DataTransfer` references the C:\DeploymentTutorial folder, whereas on the target computer the environment variable `DataTransfer` references the C:\DeploymentTutorialInstall folder.</span></span>  
  
 <span data-ttu-id="2280f-112">Se você planejar fazer a implantação no computador local, precisará criar apenas um conjunto de variáveis de ambiente; porém, precisará atualizar o valor das variáveis de ambiente para um valor apropriado antes de fazer a implantação local.</span><span class="sxs-lookup"><span data-stu-id="2280f-112">If you plan to deploy to the local computer, you need to create only one set of environment variables; however, you will need to update the value of the environment variables to an appropriate value before you do the local deployment.</span></span>  
  
 <span data-ttu-id="2280f-113">Se você planeja implantar os pacotes em um computador diferente, deverá criar dois conjuntos de variáveis de ambiente: um conjunto para o computador local e outro para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="2280f-113">If you plan to deploy the packages to a different computer, you must create two sets of environment variables: one set for the local computer, and one set for the destination computer.</span></span> <span data-ttu-id="2280f-114">Você pode criar agora apenas as variáveis para o computador original, e criar as variáveis para o computador de destino mais tarde, mas deve ter tanto a pasta, quanto as variáveis de ambiente disponíveis no computador de destino antes de instalar os pacotes nesse computador.</span><span class="sxs-lookup"><span data-stu-id="2280f-114">You can create only the variables for the source computer now, and create the variables for the destination computer later, but you must have both the folder and environment variables available on the destination computer before you can install the packages on that computer.</span></span>  
  
### <a name="to-create-the-local-working-folder"></a><span data-ttu-id="2280f-115">Para criar a pasta de trabalho local</span><span class="sxs-lookup"><span data-stu-id="2280f-115">To create the local working folder</span></span>  
  
1.  <span data-ttu-id="2280f-116">Clique com o botão direito do mouse no menu Iniciar e clique em Explorar.</span><span class="sxs-lookup"><span data-stu-id="2280f-116">Right-click the Start menu, and click Explore.</span></span>  
  
2.  <span data-ttu-id="2280f-117">Clique em **Disco Local (C:)** .</span><span class="sxs-lookup"><span data-stu-id="2280f-117">Click **Local Disk (C:)**.</span></span>  
  
3.  <span data-ttu-id="2280f-118">No menu **Arquivo** , aponte para **Novo**e clique em **Pasta**.</span><span class="sxs-lookup"><span data-stu-id="2280f-118">On the **File** menu, point to **New**, and then click **Folder**.</span></span>  
  
4.  <span data-ttu-id="2280f-119">Renomear nova pasta para `DeploymentTutorial` .</span><span class="sxs-lookup"><span data-stu-id="2280f-119">Rename New Folder to `DeploymentTutorial`.</span></span>  
  
### <a name="to-create-local-environment-variables"></a><span data-ttu-id="2280f-120">Para criar variáveis locais do ambiente</span><span class="sxs-lookup"><span data-stu-id="2280f-120">To create local environment variables</span></span>  
  
1.  <span data-ttu-id="2280f-121">No menu **Iniciar** , clique em **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="2280f-121">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="2280f-122">No Painel de Controle, clique duas vezes em **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="2280f-122">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="2280f-123">Na caixa de diálogo **Propriedades do Sistema** , clique na guia **Avançado** e clique em **Variáveis de Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="2280f-123">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="2280f-124">Na caixa de diálogo **Variáveis de Ambiente** , no quadro **Variáveis do sistema** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2280f-124">In the **Environment Variables** dialog box, in the **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="2280f-125">Na caixa de diálogo **nova variável do sistema** , digite `DataTransfer` a caixa **nome da variável** e, `C:\DeploymentTutorial\datatransferconfig.dtsconfig` na caixa **valor da variável** .</span><span class="sxs-lookup"><span data-stu-id="2280f-125">In the **New System Variable** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorial\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="2280f-126">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2280f-126">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="2280f-127">Clique em **novo** novamente e digite `LoadXMLData` a caixa **nome da variável** e, `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` na caixa **valor da variável** .</span><span class="sxs-lookup"><span data-stu-id="2280f-127">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="2280f-128">Clique em **OK** para sair da caixa de diálogo **Variáveis de Ambiente** .</span><span class="sxs-lookup"><span data-stu-id="2280f-128">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="2280f-129">Clique em **OK** para sair da caixa de diálogo **Propriedades do Sistema** .</span><span class="sxs-lookup"><span data-stu-id="2280f-129">Click **OK** to exit the **System Properties** dialog box.\</span></span>  
  
10. <span data-ttu-id="2280f-130">Opcionalmente, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="2280f-130">Optionally, restart your computer.</span></span> <span data-ttu-id="2280f-131">Se você não reiniciar o seu computador, o nome da nova variável não será exibido no Assistente de Configuração de Pacotes, mas você ainda poderá usá-lo.</span><span class="sxs-lookup"><span data-stu-id="2280f-131">If you do not restart the computer, the name of the new variable will not be displayed in the Package Configuration Wizard, but you can still use it.</span></span>  
  
### <a name="to-create-destination-environment-variables"></a><span data-ttu-id="2280f-132">Para criar variáveis de ambiente de destino</span><span class="sxs-lookup"><span data-stu-id="2280f-132">To create destination environment variables</span></span>  
  
1.  <span data-ttu-id="2280f-133">No menu **Iniciar** , clique em **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="2280f-133">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="2280f-134">No Painel de Controle, clique duas vezes em **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="2280f-134">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="2280f-135">Na caixa de diálogo **Propriedades do Sistema** , clique na guia **Avançado** e clique em **Variáveis de Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="2280f-135">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="2280f-136">Na caixa de diálogo **Variáveis de Ambiente** , no quadro **Variáveis do sistema** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2280f-136">In the **Environment Variables** dialog box, in **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="2280f-137">Na caixa de diálogo **novas variáveis do sistema** , digite `DataTransfer` a caixa **nome da variável** e, `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` na caixa **valor da variável** .</span><span class="sxs-lookup"><span data-stu-id="2280f-137">In the **New System Variables** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="2280f-138">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2280f-138">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="2280f-139">Clique em **novo** novamente e digite `LoadXMLData` a caixa **nome da variável** e, `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` na caixa **valor da variável** .</span><span class="sxs-lookup"><span data-stu-id="2280f-139">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="2280f-140">Clique em **OK** para sair da caixa de diálogo **Variáveis de Ambiente** .</span><span class="sxs-lookup"><span data-stu-id="2280f-140">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="2280f-141">Clique em **OK** para sair da caixa de diálogo **Propriedades do Sistema** .</span><span class="sxs-lookup"><span data-stu-id="2280f-141">Click **OK** to exit the **System Properties** dialog box.\</span></span>  
  
10. <span data-ttu-id="2280f-142">Opcionalmente, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="2280f-142">Optionally, restart your computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2280f-143">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="2280f-143">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2280f-144">Etapa 2: Criando o projeto de implantação</span><span class="sxs-lookup"><span data-stu-id="2280f-144">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
<span data-ttu-id="2280f-145">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2280f-145">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2280f-146">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="2280f-146">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2280f-147">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="2280f-147">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2280f-148">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="2280f-148">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
