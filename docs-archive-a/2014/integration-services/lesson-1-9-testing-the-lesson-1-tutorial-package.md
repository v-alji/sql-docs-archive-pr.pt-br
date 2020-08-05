---
title: 'Etapa 9: testar o pacote de tutoriais da Lição 1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9aee7acf-797b-46f2-830d-80ab64a9f0b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dff1132489c1683430b1003e88f5037664b11983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574123"
---
# <a name="step-9-testing-the-lesson-1-tutorial-package"></a><span data-ttu-id="1447d-102">Etapa 9: Testar o pacote de tutorial da Lição 1</span><span class="sxs-lookup"><span data-stu-id="1447d-102">Step 9: Testing the Lesson 1 Tutorial Package</span></span>
  <span data-ttu-id="1447d-103">Nesta lição, você executou as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="1447d-103">In this lesson, you have done the following tasks:</span></span>  
  
-   <span data-ttu-id="1447d-104">Criou um novo projeto do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1447d-104">Created a new [!INCLUDE[ssIS](../includes/ssis-md.md)] project.</span></span>  
  
-   <span data-ttu-id="1447d-105">Configurou os gerenciadores de conexões que o pacote precisa para estabelecer conexão com os dados de origem e de destino.</span><span class="sxs-lookup"><span data-stu-id="1447d-105">Configured the connection managers that the package needs to connect to the source and destination data.</span></span>  
  
-   <span data-ttu-id="1447d-106">Adicionou um fluxo de dados que usa os dados de uma origem de arquivo simples, desenvolve as transformações Pesquisa necessárias sobre os dados e configura os dados para o destino.</span><span class="sxs-lookup"><span data-stu-id="1447d-106">Added a data flow that takes the data from a flat file source, performs the necessary Lookup transformations on the data, and configures the data for the destination.</span></span>  
  
 <span data-ttu-id="1447d-107">Seu pacote está completo agora!</span><span class="sxs-lookup"><span data-stu-id="1447d-107">Your package is now complete!</span></span> <span data-ttu-id="1447d-108">Está na hora de testá-lo.</span><span class="sxs-lookup"><span data-stu-id="1447d-108">It is time to test your package.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="1447d-109">Verificando o layout do pacote</span><span class="sxs-lookup"><span data-stu-id="1447d-109">Checking the Package Layout</span></span>  
 <span data-ttu-id="1447d-110">Antes de testar o pacote, é recomendável verificar se os fluxos de controle e de dados do pacote da Lição 1 contêm os objetos mostrados nos diagramas a seguir.</span><span class="sxs-lookup"><span data-stu-id="1447d-110">Before you test the package you should verify that the control and data flows in the Lesson 1 package contain the objects shown in the following diagrams.</span></span>  
  
 <span data-ttu-id="1447d-111">**Fluxo de Controle**</span><span class="sxs-lookup"><span data-stu-id="1447d-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="1447d-112">![Fluxo de controle no pacote](../../2014/tutorials/media/task9lesson1control.gif "Fluxo de controle no pacote")</span><span class="sxs-lookup"><span data-stu-id="1447d-112">![Control flow in package](../../2014/tutorials/media/task9lesson1control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="1447d-113">**Fluxo de Dados**</span><span class="sxs-lookup"><span data-stu-id="1447d-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="1447d-114">![Fluxo de dados no pacote](../../2014/tutorials/media/task9lesson1data.gif "Fluxo de dados no pacote")</span><span class="sxs-lookup"><span data-stu-id="1447d-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-1-tutorial-package"></a><span data-ttu-id="1447d-115">Para executar o pacote de tutorial da Lição 1</span><span class="sxs-lookup"><span data-stu-id="1447d-115">To run the Lesson 1 tutorial package</span></span>  
  
1.  <span data-ttu-id="1447d-116">No menu **Depurar**, clique em **Iniciar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="1447d-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="1447d-117">O pacote será executado, resultando em 1097 linhas adicionadas à tabela de fatos **FactCurrency** no **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="1447d-117">The package will run, resulting in 1097 rows successfully added into the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span>  
  
2.  <span data-ttu-id="1447d-118">Terminada a execução do pacote, no menu **Depurar** , clique em **Parar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="1447d-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="1447d-119">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="1447d-119">Next Lesson</span></span>  
 [<span data-ttu-id="1447d-120">Lição 2: Como adicionar um loop</span><span class="sxs-lookup"><span data-stu-id="1447d-120">Lesson 2: Adding Looping</span></span>](../integration-services/lesson-2-adding-looping-with-ssis.md)  
  
## <a name="see-also"></a><span data-ttu-id="1447d-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1447d-121">See Also</span></span>  
 [<span data-ttu-id="1447d-122">Execução de projetos e pacotes</span><span class="sxs-lookup"><span data-stu-id="1447d-122">Execution of Projects and Packages</span></span>](packages/run-integration-services-ssis-packages.md)  
  
  
