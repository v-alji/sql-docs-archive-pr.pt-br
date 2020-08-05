---
title: 'Etapa 5: testar os pacotes atualizados | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 683e52e5-1c7e-49ab-9ffe-6a450a1c5776
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a075af2e030c8257d01abf5eba7d330b1cc8efe7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574131"
---
# <a name="step-5-testing-the-updated-packages"></a><span data-ttu-id="78ca3-102">Etapa 5: Testar os pacotes atualizados</span><span class="sxs-lookup"><span data-stu-id="78ca3-102">Step 5: Testing the Updated Packages</span></span>
  <span data-ttu-id="78ca3-103">Antes de ir para a próxima lição, na qual você criará o pacote de implantação a ser usado para instalar os pacotes de tutorial no computador de destino, você deverá testar os pacotes.</span><span class="sxs-lookup"><span data-stu-id="78ca3-103">Before you go on to the next lesson, in which you will create the deployment bundle to use to install the tutorial packages on the destination computer, you should test the packages.</span></span> <span data-ttu-id="78ca3-104">Nesta tarefa, você executará os pacotes, DataTransfer.dtsx e LoadXMLData que você adicionou ao projeto Tutorial de Implantação e então estendeu com configurações.</span><span class="sxs-lookup"><span data-stu-id="78ca3-104">In this task, you will run the packages, DataTransfer.dtsx and LoadXMLData, that you added to the Deployment Tutorial project and then extended with configurations.</span></span>  
  
 <span data-ttu-id="78ca3-105">Quando os pacotes são executados, cada executável do pacote fica com uma cor verde quando concluído com sucesso.</span><span class="sxs-lookup"><span data-stu-id="78ca3-105">When the packages run, each executable in the package becomes a green color as it completes successfully.</span></span> <span data-ttu-id="78ca3-106">Quando todos os executáveis estão verdes, o pacote foi concluído com sucesso.</span><span class="sxs-lookup"><span data-stu-id="78ca3-106">When all executables are green, the package has completed successfully.</span></span> <span data-ttu-id="78ca3-107">Você também pode visualizar o progresso da execução do pacote na guia **Progresso** .</span><span class="sxs-lookup"><span data-stu-id="78ca3-107">You can also view the package execution progress on the **Progress** tab.</span></span>  
  
 <span data-ttu-id="78ca3-108">Se os pacotes não forem executados com sucesso, você precisará corrigi-los antes de ir para a próxima lição.</span><span class="sxs-lookup"><span data-stu-id="78ca3-108">If the packages do not run successfully, you must fix them before you go on to the next lesson.</span></span>  
  
### <a name="to-run-the-datatransfer-package"></a><span data-ttu-id="78ca3-109">Para executar o pacote DataTransfer</span><span class="sxs-lookup"><span data-stu-id="78ca3-109">To run the DataTransfer package</span></span>  
  
1.  <span data-ttu-id="78ca3-110">No Gerenciador de Soluções, clique em DataTransfer.dtsx.</span><span class="sxs-lookup"><span data-stu-id="78ca3-110">In Solution Explorer, click DataTransfer.dtsx.</span></span>  
  
2.  <span data-ttu-id="78ca3-111">No menu **Depurar** , clique em **Iniciar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="78ca3-111">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="78ca3-112">Terminada a execução do pacote, no menu **Depurar** , clique em **Parar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="78ca3-112">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-run-the-loadxmldata-package"></a><span data-ttu-id="78ca3-113">Para executar o pacote LoadXMLData</span><span class="sxs-lookup"><span data-stu-id="78ca3-113">To run the LoadXMLData package</span></span>  
  
1.  <span data-ttu-id="78ca3-114">No Gerenciador de Soluções, clique em LoadXMLData.dtsx.</span><span class="sxs-lookup"><span data-stu-id="78ca3-114">In Solution Explorer, click LoadXMLData.dtsx.</span></span>  
  
2.  <span data-ttu-id="78ca3-115">No menu **Depurar** , clique em **Iniciar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="78ca3-115">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="78ca3-116">Terminada a execução do pacote, no menu **Depurar** , clique em **Parar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="78ca3-116">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="78ca3-117">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="78ca3-117">Next Lesson</span></span>  
 [<span data-ttu-id="78ca3-118">Lição 2: Como criar o pacote de implantação</span><span class="sxs-lookup"><span data-stu-id="78ca3-118">Lesson 2: Creating the Deployment Bundle</span></span>](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md)  
  
<span data-ttu-id="78ca3-119">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="78ca3-119">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="78ca3-120">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="78ca3-120">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="78ca3-121">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="78ca3-121">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="78ca3-122">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="78ca3-122">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
