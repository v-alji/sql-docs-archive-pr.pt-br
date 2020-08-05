---
title: 'Lição 3: Instalando pacotes | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 87bc4d82-39d8-424f-886f-98cf1e4bb07a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f8b58cee7bd8e16cd0ca2e726dc8e5eff2cfec5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573182"
---
# <a name="lesson-3-installing-packages"></a><span data-ttu-id="89b7e-102">Lição 3: Instalando pacotes</span><span class="sxs-lookup"><span data-stu-id="89b7e-102">Lesson 3: Installing Packages</span></span>
  <span data-ttu-id="89b7e-103">Na [lição 2: criando o pacote de implantação](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md), você construiu um utilitário de implantação e criou o pacote de implantação que contém os itens que você deve instalar pacotes em outro computador.</span><span class="sxs-lookup"><span data-stu-id="89b7e-103">In [Lesson 2: Creating the Deployment Bundle](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md), you built a deployment utility and created the deployment bundle that contains the items that you must install packages on another computer.</span></span> <span data-ttu-id="89b7e-104">Você também verificou a lista de arquivos no pacote de implantação e examinou o conteúdo do arquivo de manifesto criado quando você compilou o utilitário de implantação.</span><span class="sxs-lookup"><span data-stu-id="89b7e-104">You also verified the file list in the deployment bundle and examined the contents of the manifest file that was created when you built the deployment utility.</span></span>  
  
 <span data-ttu-id="89b7e-105">Nesta lição, você copiará o pacote de implantação para o computador de destino e executará o Assistente de Instalação de Pacotes para instalar os pacotes, as dependências dos pacotes e os arquivos auxiliares no computador.</span><span class="sxs-lookup"><span data-stu-id="89b7e-105">In this lesson, you will copy the deployment bundle to the destination computer and then run the Package Installation Wizard to install the packages, package dependencies, and ancillary files on that computer.</span></span> <span data-ttu-id="89b7e-106">Os pacotes serão instalados no banco de dados **msdb** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e os outros itens serão instalados no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="89b7e-106">The packages will be installed in the **msdb**[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database and the other items will be installed in the file system.</span></span> <span data-ttu-id="89b7e-107">Depois de concluir a instalação de pacote, você testará a implantação executando os pacotes do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] usando o Execute o Utilitário de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="89b7e-107">After you complete the package installation, you will test the deployment by running the packages from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] using the Execute Package Utility.</span></span>  
  
 <span data-ttu-id="89b7e-108">**Tempo estimado para concluir esta lição:** 30 minutos</span><span class="sxs-lookup"><span data-stu-id="89b7e-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="89b7e-109">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="89b7e-109">Lesson Tasks</span></span>  
 <span data-ttu-id="89b7e-110">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="89b7e-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="89b7e-111">Etapa 1: Copiar o pacote de implantação</span><span class="sxs-lookup"><span data-stu-id="89b7e-111">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
-   [<span data-ttu-id="89b7e-112">Etapa 2: Executar o Assistente de Instalação de Pacotes</span><span class="sxs-lookup"><span data-stu-id="89b7e-112">Step 2: Running the Package Installation Wizard</span></span>](../integration-services/lesson-3-2-running-the-package-installation-wizard.md)  
  
-   [<span data-ttu-id="89b7e-113">Etapa 3: Testar os pacotes implantados</span><span class="sxs-lookup"><span data-stu-id="89b7e-113">Step 3: Testing the Deployed Packages</span></span>](../integration-services/lesson-3-3-testing-the-deployed-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="89b7e-114">Iniciar a lição</span><span class="sxs-lookup"><span data-stu-id="89b7e-114">Start the Lesson</span></span>  
 [<span data-ttu-id="89b7e-115">Etapa 1: Copiar o pacote de implantação</span><span class="sxs-lookup"><span data-stu-id="89b7e-115">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
<span data-ttu-id="89b7e-116">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="89b7e-116">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="89b7e-117">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="89b7e-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="89b7e-118">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="89b7e-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="89b7e-119">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="89b7e-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
