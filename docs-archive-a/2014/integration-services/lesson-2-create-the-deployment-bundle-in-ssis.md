---
title: 'Lição 2: criando o pacote de implantação | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab17289d-c3d4-4a5e-b7f5-4fea8ae21707
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 927bcd393e4b54e92971c197d93dcc1e2804dcd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575908"
---
# <a name="lesson-2-creating-the-deployment-bundle"></a><span data-ttu-id="17610-102">Lição 2: Como criar o pacote de implantação</span><span class="sxs-lookup"><span data-stu-id="17610-102">Lesson 2: Creating the Deployment Bundle</span></span>
  <span data-ttu-id="17610-103">Na [Lição 1: Preparando-se para criar o pacote de implantação](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md), você criou o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] chamado Tutorial de Implantação, adicionou os pacotes e os arquivos de suporte ao projeto e implementou configurações em pacotes.</span><span class="sxs-lookup"><span data-stu-id="17610-103">In [Lesson 1: Preparing to Create the Deployment Bundle](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md), you created the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project named Deployment Tutorial, added the packages and supporting files to the project, and implemented configurations in packages.</span></span>  
  
 <span data-ttu-id="17610-104">Nesta lição, você criará um pacote de implantação, que é uma pasta que contém os itens que você precisa para instalar os pacotes em outro computador.</span><span class="sxs-lookup"><span data-stu-id="17610-104">In this lesson, you will create the deployment bundle, which is a folder that contains the items that you need to install packages on another computer.</span></span> <span data-ttu-id="17610-105">O pacote de implantação incluirá um manifesto de implantação, cópias dos pacotes e cópias dos arquivos de suporte do projeto do Tutorial de Implantação.</span><span class="sxs-lookup"><span data-stu-id="17610-105">The deployment bundle will include a deployment manifest, copies of the packages, and copies of the supporting files from the Deployment Tutorial project.</span></span> <span data-ttu-id="17610-106">O manifesto de implantação lista os pacotes, os diversos arquivos e as configurações do pacote de implantação.</span><span class="sxs-lookup"><span data-stu-id="17610-106">The deployment manifest lists the packages, miscellaneous files, and configurations in the deployment bundle.</span></span>  
  
 <span data-ttu-id="17610-107">Você também verificará a lista de arquivos no pacote de implantação e examinará o conteúdo do manifesto.</span><span class="sxs-lookup"><span data-stu-id="17610-107">You will also verify the file list in the deployment bundle and examine the contents of the manifest.</span></span>  
  
 <span data-ttu-id="17610-108">**Tempo estimado para concluir esta lição:** 30 minutos</span><span class="sxs-lookup"><span data-stu-id="17610-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="17610-109">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="17610-109">Lesson Tasks</span></span>  
 <span data-ttu-id="17610-110">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="17610-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="17610-111">Etapa 1: Compilando o utilitário de implantação</span><span class="sxs-lookup"><span data-stu-id="17610-111">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
-   [<span data-ttu-id="17610-112">Etapa 2: Verificando o pacote de implantação</span><span class="sxs-lookup"><span data-stu-id="17610-112">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="17610-113">Iniciar a lição</span><span class="sxs-lookup"><span data-stu-id="17610-113">Start the Lesson</span></span>  
 [<span data-ttu-id="17610-114">Etapa 1: Compilando o utilitário de implantação</span><span class="sxs-lookup"><span data-stu-id="17610-114">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
<span data-ttu-id="17610-115">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="17610-115">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="17610-116">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="17610-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="17610-117">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="17610-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="17610-118">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="17610-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
