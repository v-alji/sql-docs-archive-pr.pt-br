---
title: 'Etapa 3: testar o pacote da Lição 6 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c184c92d-948f-4037-a502-5fabd909c84c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3c7ab82e9b04fe0752252102374f745e311d830d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683607"
---
# <a name="step-3-testing-the-lesson-6-package"></a><span data-ttu-id="27ad0-102">Etapa 3: Testar o pacote da Lição 6</span><span class="sxs-lookup"><span data-stu-id="27ad0-102">Step 3: Testing the Lesson 6 Package</span></span>
  <span data-ttu-id="27ad0-103">Em tempo de execução, seu pacote irá obter o valor para a propriedade Diretório a partir do parâmetro VarFolderName.</span><span class="sxs-lookup"><span data-stu-id="27ad0-103">At run time, your package will obtain the value for the Directory property from the VarFolderName parameter.</span></span>  
  
 <span data-ttu-id="27ad0-104">Para verificar se, em tempo de execução, o pacote atualizou corretamente o Diretório com o novo valor, simplesmente execute o pacote.</span><span class="sxs-lookup"><span data-stu-id="27ad0-104">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="27ad0-105">Devido a serem copiados apenas três arquivos de dados de exemplo para o novo diretório, o fluxo de dados irá executar apenas três vezes ao invés de interagir com 14 arquivos da pasta original.</span><span class="sxs-lookup"><span data-stu-id="27ad0-105">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="27ad0-106">Verificando o layout do pacote</span><span class="sxs-lookup"><span data-stu-id="27ad0-106">Checking the Package Layout</span></span>  
 <span data-ttu-id="27ad0-107">Antes de testar o pacote deve-se verificar se os fluxos de controle e de dados do pacote da Lição 6 contêm os objetos mostrados nos diagramas a seguir.</span><span class="sxs-lookup"><span data-stu-id="27ad0-107">Before you test the package you should verify that the control and data flows in the Lesson 6 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="27ad0-108">O fluxo de controle deve ser idêntico ao fluxo de controle da lição 5.</span><span class="sxs-lookup"><span data-stu-id="27ad0-108">The control flow should be identical to the control flow in lesson 5.</span></span> <span data-ttu-id="27ad0-109">O fluxo de dados deve ser idêntico ao fluxo de dados na lição 5.</span><span class="sxs-lookup"><span data-stu-id="27ad0-109">The data flow should be identical to the data flow in lesson 5.</span></span>  
  
 <span data-ttu-id="27ad0-110">**Fluxo de Controle**</span><span class="sxs-lookup"><span data-stu-id="27ad0-110">**Control Flow**</span></span>  
  
 <span data-ttu-id="27ad0-111">![Fluxo de Controle](../../2014/tutorials/media/task3lesson6control.jpg "Fluxo de Controle")</span><span class="sxs-lookup"><span data-stu-id="27ad0-111">![Control Flow](../../2014/tutorials/media/task3lesson6control.jpg "Control Flow")</span></span>  
  
 <span data-ttu-id="27ad0-112">**Fluxo de Dados**</span><span class="sxs-lookup"><span data-stu-id="27ad0-112">**Data Flow**</span></span>  
  
 <span data-ttu-id="27ad0-113">![Fluxo de Dados](../../2014/tutorials/media/task3lesson6data.jpg "Fluxo de Dados")</span><span class="sxs-lookup"><span data-stu-id="27ad0-113">![Data Flow](../../2014/tutorials/media/task3lesson6data.jpg "Data Flow")</span></span>  
  
### <a name="to-test-the-lesson-6-tutorial-package"></a><span data-ttu-id="27ad0-114">Para testar o pacote de tutorial da Lição 6</span><span class="sxs-lookup"><span data-stu-id="27ad0-114">TO test the Lesson 6 tutorial package</span></span>  
  
1.  <span data-ttu-id="27ad0-115">No menu Depurar, clique em Iniciar Depuração.</span><span class="sxs-lookup"><span data-stu-id="27ad0-115">On the Debug menu, click Start Debugging.</span></span>  
  
2.  <span data-ttu-id="27ad0-116">Terminada a execução do pacote, no menu Depurar, clique em Parar Depuração.</span><span class="sxs-lookup"><span data-stu-id="27ad0-116">After the package has completed running, on the Debug menu, and then click Stop Debugging.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="27ad0-117">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="27ad0-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="27ad0-118">Etapa 4: Implantar o pacote da Lição 6</span><span class="sxs-lookup"><span data-stu-id="27ad0-118">Step 4: Deploying the Lesson 6 Package</span></span>](../integration-services/lesson-6-4-deploying-the-lesson-6-package.md)  
  
  
