---
title: 'Etapa 5: testar o pacote de tutoriais da Lição 4 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5f18df92-0248-4858-836b-c8b02f0e0439
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a897f99bf68805e4e66c3b6bbe818b312077fb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683114"
---
# <a name="step-5-testing-the-lesson-4-tutorial-package"></a><span data-ttu-id="67c83-102">Etapa 5: Testar o pacote de tutorial da Lição 4</span><span class="sxs-lookup"><span data-stu-id="67c83-102">Step 5: Testing the Lesson 4 Tutorial Package</span></span>
  <span data-ttu-id="67c83-103">No tempo de execução, o arquivo corrompido, Currency_BAD.txt, não gerará uma correspondência dentro da transformação Pesquisa de Códigos de Moeda.</span><span class="sxs-lookup"><span data-stu-id="67c83-103">At run time, the corrupted file, Currency_BAD.txt, will fail to generate a match within the Currency Key Lookup transformation.</span></span> <span data-ttu-id="67c83-104">Como a saída de erro de Pesquisa de Códigos de Moeda foi configurada para redirecionar linhas com falhas para o novo destino de linhas com falha, o componente não falha e o pacote é executado com êxito.</span><span class="sxs-lookup"><span data-stu-id="67c83-104">Because the error output of Currency Key Lookup has now been configured to redirect failed rows to the new Failed Rows destination, the component does not fail, and the package runs successfully.</span></span> <span data-ttu-id="67c83-105">Todas as linhas com erro são gravadas em ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="67c83-105">All failed error rows are written to ErrorOutput.txt.</span></span>  
  
 <span data-ttu-id="67c83-106">Nesta tarefa, você testará a configuração de saída do erro revisado executando o pacote.</span><span class="sxs-lookup"><span data-stu-id="67c83-106">In this task, you will test the revised error output configuration by running the package.</span></span> <span data-ttu-id="67c83-107">Com a execução bem-sucedida do pacote, você verá o conteúdo do arquivo ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="67c83-107">Upon successful package execution, you will then view the contents of the ErrorOutput.txt file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67c83-108">Se você não quiser acumular linhas de erro no arquivo ErrorOutput.txt, exclua manualmente o conteúdo do arquivo entre execuções de pacotes.</span><span class="sxs-lookup"><span data-stu-id="67c83-108">If you do not want to accumulate error rows in the ErrorOutput.txt file, you should manually delete the file content between package runs.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="67c83-109">Verificando o layout do pacote</span><span class="sxs-lookup"><span data-stu-id="67c83-109">Checking the Package layout</span></span>  
 <span data-ttu-id="67c83-110">Antes de você testar o pacote, é recomendável verificar se o fluxo de controle e o fluxo de dados do pacote da lição 4 contêm os objetos mostrados nos diagramas seguintes.</span><span class="sxs-lookup"><span data-stu-id="67c83-110">Before you test the package you should verify that the control flow and the data flow in the Lesson 4 package contain the objects shown in the following diagrams.</span></span> <span data-ttu-id="67c83-111">O fluxo de controle deve ser idêntico ao fluxo de controle das lições 2 - 4.</span><span class="sxs-lookup"><span data-stu-id="67c83-111">The control flow should be identical to the control flow in lessons 2 - 4.</span></span>  
  
 <span data-ttu-id="67c83-112">**Fluxo de Controle**</span><span class="sxs-lookup"><span data-stu-id="67c83-112">**Control Flow**</span></span>  
  
 <span data-ttu-id="67c83-113">![Fluxo de controle no pacote](../../2014/tutorials/media/task4lesson2control.gif "Fluxo de controle no pacote")</span><span class="sxs-lookup"><span data-stu-id="67c83-113">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="67c83-114">**Fluxo de Dados**</span><span class="sxs-lookup"><span data-stu-id="67c83-114">**Data Flow**</span></span>  
  
 <span data-ttu-id="67c83-115">![Fluxo de dados no pacote](../../2014/tutorials/media/task5lesson5data.gif "Fluxo de dados no pacote")</span><span class="sxs-lookup"><span data-stu-id="67c83-115">![Data flow in package](../../2014/tutorials/media/task5lesson5data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-4-tutorial-package"></a><span data-ttu-id="67c83-116">Para executar o pacote de tutorial da lição 4</span><span class="sxs-lookup"><span data-stu-id="67c83-116">To run the Lesson 4 tutorial package</span></span>  
  
1.  <span data-ttu-id="67c83-117">No menu **Depurar**, clique em **Iniciar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="67c83-117">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="67c83-118">Terminada a execução do pacote, no menu **Depurar** , clique em **Parar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="67c83-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-verify-the-contents-of-the-erroroutputtxt-file"></a><span data-ttu-id="67c83-119">Para verificar o conteúdo do arquivo ErrorOutput.txt</span><span class="sxs-lookup"><span data-stu-id="67c83-119">To verify the contents of the ErrorOutput.txt file</span></span>  
  
-   <span data-ttu-id="67c83-120">No Bloco de Notas ou qualquer outro editor de texto, abra o arquivo ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="67c83-120">In Notepad or any other text editor, open the ErrorOutput.txt file.</span></span> <span data-ttu-id="67c83-121">A ordem de colunas padrão é: AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="67c83-121">The default column order is: AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.</span></span>  
  
     <span data-ttu-id="67c83-122">Observe que todas as linhas do arquivo contêm o valor CurrencyID de BAD, o valor ErrorCode de -1071607778, o valor ErrorColumn de 0 e o valor ErrorDescription de "Row yielded no match during lookup."</span><span class="sxs-lookup"><span data-stu-id="67c83-122">Notice that all the rows in the file contain the unmatched CurrencyID value of BAD, the ErrorCode value of -1071607778, the ErrorColumn value of 0, and the ErrorDescription value "Row yielded no match during lookup".</span></span> <span data-ttu-id="67c83-123">O valor de ErrorColumn é definido como 0 porque o erro não é específico da coluna.</span><span class="sxs-lookup"><span data-stu-id="67c83-123">The value of the ErrorColumn is set to 0 because the error is not column specific.</span></span> <span data-ttu-id="67c83-124">A operação de pesquisa que falhou.</span><span class="sxs-lookup"><span data-stu-id="67c83-124">It is the lookup operation that failed.</span></span> <span data-ttu-id="67c83-125">.</span><span class="sxs-lookup"><span data-stu-id="67c83-125">.</span></span>  
  
  
