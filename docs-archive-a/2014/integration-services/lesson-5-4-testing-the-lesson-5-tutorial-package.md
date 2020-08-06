---
title: 'Etapa 4: testar o pacote de tutoriais da Lição 5 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5215b77d-c2ec-4b25-a3de-ca49ea197d74
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 76e4692de4daa9ddd6ed0e418bed5cda74ec7650
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571438"
---
# <a name="step-4-testing-the-lesson-5-tutorial-package"></a><span data-ttu-id="376fb-102">Etapa 4: Testar o pacote de tutorial da Lição 5</span><span class="sxs-lookup"><span data-stu-id="376fb-102">Step 4: Testing the Lesson 5 Tutorial Package</span></span>
  <span data-ttu-id="376fb-103">Em tempo de execução, o pacote irá obter o valor da propriedade `Directory` de uma variável atualizada em tempo de execução, ao invés de utilizar o nome original de diretório que foi especificado quando você criou o pacote.</span><span class="sxs-lookup"><span data-stu-id="376fb-103">At run time, your package will obtain the value for the `Directory` property from a variable updated at run time, rather than using the original directory name that you specified when you created the package.</span></span> <span data-ttu-id="376fb-104">O valor da variável é populado pelo arquivo SSISTutorial.dtsConfig.</span><span class="sxs-lookup"><span data-stu-id="376fb-104">The value of the variable is populated by the SSISTutorial.dtsConfig file.</span></span>  
  
 <span data-ttu-id="376fb-105">Para verificar se, em tempo de execução, o pacote atualizou corretamente o Diretório com o novo valor, simplesmente execute o pacote.</span><span class="sxs-lookup"><span data-stu-id="376fb-105">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="376fb-106">Devido a serem copiados apenas três arquivos de dados de exemplo para o novo diretório, o fluxo de dados irá executar apenas três vezes ao invés de interagir com 14 arquivos da pasta original.</span><span class="sxs-lookup"><span data-stu-id="376fb-106">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="376fb-107">Verificando o layout do pacote</span><span class="sxs-lookup"><span data-stu-id="376fb-107">Checking the Package Layout</span></span>  
 <span data-ttu-id="376fb-108">Antes de testar o pacote, deve-se verificar se os fluxos de controle e de dados do pacote da Lição 5 contêm os objetos mostrados nos diagramas a seguir.</span><span class="sxs-lookup"><span data-stu-id="376fb-108">Before you test the package you should verify that the control and data flows in the Lesson 5 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="376fb-109">O fluxo de controle deve ser idêntico ao fluxo de controle da Lição 4.</span><span class="sxs-lookup"><span data-stu-id="376fb-109">The control flow should be identical to the control flow in lesson 4.</span></span> <span data-ttu-id="376fb-110">O fluxo de dados deve ser idêntico ao fluxo de dados da lição 4.</span><span class="sxs-lookup"><span data-stu-id="376fb-110">The data flow should be identical to the data flow in lessons 4.</span></span>  
  
 <span data-ttu-id="376fb-111">**Fluxo de Controle**</span><span class="sxs-lookup"><span data-stu-id="376fb-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="376fb-112">![Fluxo de controle no pacote](../../2014/tutorials/media/task4lesson2control.gif "Fluxo de controle no pacote")</span><span class="sxs-lookup"><span data-stu-id="376fb-112">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="376fb-113">**Fluxo de Dados**</span><span class="sxs-lookup"><span data-stu-id="376fb-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="376fb-114">![Fluxo de dados no pacote](../../2014/tutorials/media/task9lesson1data.gif "Fluxo de dados no pacote")</span><span class="sxs-lookup"><span data-stu-id="376fb-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-5-tutorial-package"></a><span data-ttu-id="376fb-115">Para testar o pacote de tutorial da Lição 5</span><span class="sxs-lookup"><span data-stu-id="376fb-115">To test the Lesson 5 tutorial package</span></span>  
  
1.  <span data-ttu-id="376fb-116">No menu **Depurar**, clique em **Iniciar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="376fb-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="376fb-117">Após a conclusão da execução do pacote, no menu **depurar** , clique em **parar depuração**.</span><span class="sxs-lookup"><span data-stu-id="376fb-117">After the package has completed running, on the **Debug** menu, and then click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="376fb-118">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="376fb-118">Next Lesson</span></span>  
 [<span data-ttu-id="376fb-119">Lição 6: Como usar parâmetros com o modelo de implantação de projeto</span><span class="sxs-lookup"><span data-stu-id="376fb-119">Lesson 6: Using Parameters with the Project Deployment Model</span></span>](../integration-services/lesson-6-using-parameters-with-the-project-deployment-model-in-ssis.md)  
  
  
