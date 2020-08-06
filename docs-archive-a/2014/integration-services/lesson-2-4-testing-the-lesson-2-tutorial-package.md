---
title: 'Etapa 4: testar o pacote de tutoriais da Lição 2 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0e8c0a25-8f79-41df-8ed2-f82a74b129cd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c055f80cbe9e6748b82569204e3a2d82e2f437e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570113"
---
# <a name="step-4-testing-the-lesson-2-tutorial-package"></a><span data-ttu-id="046d1-102">Etapa 4: Testar o pacote de tutorial da Lição 2</span><span class="sxs-lookup"><span data-stu-id="046d1-102">Step 4: Testing the Lesson 2 Tutorial Package</span></span>
  <span data-ttu-id="046d1-103">Com o contêiner Loop Foreach e o gerenciador de conexões de Arquivo Simples agora configurado, o pacote da Lição 2 pode iterar através da coleção de 14 arquivos simples na pasta Dados de Exemplo.</span><span class="sxs-lookup"><span data-stu-id="046d1-103">With the Foreach Loop container and the Flat File connection manager now configured, the Lesson 2 package can iterate through the collection of 14 flat files in the Sample Data folder.</span></span> <span data-ttu-id="046d1-104">Cada vez que um nome de arquivo é encontrado e corresponde aos critérios de nome de arquivo especificado, o contêiner Loop Foreach popula a variável definida pelo usuário com o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="046d1-104">Each time a file name is found that matches the specified file name criteria, the Foreach Loop container populates the user-defined variable with the file name.</span></span> <span data-ttu-id="046d1-105">Essa variável, por sua vez, atualiza a propriedade ConnectionString do gerenciador de conexões de Arquivo Simples, e uma conexão é criada para o novo arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="046d1-105">This variable, in turn, updates the ConnectionString property of the Flat File connection manager, and a connection to the new flat file is made.</span></span> <span data-ttu-id="046d1-106">O contêiner Loop Foreach, então, executa a tarefa de fluxo de dados não modificados em relação aos dados no novo arquivo simples, antes de se conectar ao próximo arquivo na pasta.</span><span class="sxs-lookup"><span data-stu-id="046d1-106">The Foreach Loop container then runs the unmodified data flow task against the data in the new flat file before connecting to the next file in the folder.</span></span>  
  
 <span data-ttu-id="046d1-107">Use o procedimento a seguir para testar a nova funcionalidade de loop que você adicionou ao seu pacote.</span><span class="sxs-lookup"><span data-stu-id="046d1-107">Use the following procedure to test the new looping functionality that you have added to your package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="046d1-108">Se você tiver executado o pacote da lição 1, precisará excluir os registros de dbo.FactCurrency no AdventureWorksDW2012 antes de executar o pacote dessa lição, ou o pacote falhará com erros que indicam uma violação de restrição de chave primária.</span><span class="sxs-lookup"><span data-stu-id="046d1-108">If you ran the package from Lesson 1, you will need to delete the records from dbo.FactCurrency in AdventureWorksDW2012 before you run the package from this lesson or the package will fail with errors indicating a Violation of Primary Key constraint.</span></span> <span data-ttu-id="046d1-109">Você receberá os mesmos erros se executar o pacote selecionando Depurar/Iniciar Depuração (ou pressione F5) porque as lições 1 e 2 serão executadas.</span><span class="sxs-lookup"><span data-stu-id="046d1-109">You will receive the same errors if you run the package by selecting Debug/Start Debugging (or press F5) because both Lesson 1 and Lesson 2 will run.</span></span> <span data-ttu-id="046d1-110">A lição 2 tentará inserir os registros já inseridos na lição 1.</span><span class="sxs-lookup"><span data-stu-id="046d1-110">Lesson 2 will attempt to insert records already inserted in Lesson 1.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="046d1-111">Verificando o layout do pacote</span><span class="sxs-lookup"><span data-stu-id="046d1-111">Checking the Package Layout</span></span>  
 <span data-ttu-id="046d1-112">Antes de testar o pacote, deve-se verificar se os fluxos de controle e de dados do pacote da Lição 2 contêm os objetos mostrados nos diagramas a seguir.</span><span class="sxs-lookup"><span data-stu-id="046d1-112">Before you test the package you should verify that the control and data flows in the Lesson 2 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="046d1-113">O fluxo de dados deve ser idêntico ao fluxo de dados na Lição 1.</span><span class="sxs-lookup"><span data-stu-id="046d1-113">The data flow should be identical to the data flow in lesson 1.</span></span>  
  
 <span data-ttu-id="046d1-114">**Fluxo de Controle**</span><span class="sxs-lookup"><span data-stu-id="046d1-114">**Control Flow**</span></span>  
  
 <span data-ttu-id="046d1-115">![Fluxo de controle no pacote](../../2014/tutorials/media/task4lesson2control.gif "Fluxo de controle no pacote")</span><span class="sxs-lookup"><span data-stu-id="046d1-115">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="046d1-116">**Fluxo de Dados**</span><span class="sxs-lookup"><span data-stu-id="046d1-116">**Data Flow**</span></span>  
  
 <span data-ttu-id="046d1-117">![Fluxo de dados no pacote](../../2014/tutorials/media/task9lesson1data.gif "Fluxo de dados no pacote")</span><span class="sxs-lookup"><span data-stu-id="046d1-117">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-2-tutorial-package"></a><span data-ttu-id="046d1-118">Para testar o pacote de tutorial da Lição 2</span><span class="sxs-lookup"><span data-stu-id="046d1-118">To test the Lesson 2 tutorial package</span></span>  
  
1.  <span data-ttu-id="046d1-119">No **Gerenciador de Soluções**, clique com o botão direito do mouse em **Lesson 2.dtsx** e clique em **Executar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="046d1-119">In **Solution Explorer**, right-click **Lesson 2.dtsx** and click **Execute Package**.</span></span>  
  
     <span data-ttu-id="046d1-120">O pacote será executado.</span><span class="sxs-lookup"><span data-stu-id="046d1-120">The package will run.</span></span> <span data-ttu-id="046d1-121">Você pode verificar o status de cada loop na janela de saída ou clicando na guia **progresso** . Por exemplo, você pode ver que 1097 linhas foram adicionadas à tabela de destino do arquivo Currency_VEB.txt.</span><span class="sxs-lookup"><span data-stu-id="046d1-121">You can verify the status of each loop in the Output window, or by clicking on the **Progress** tab. For example, you can see that 1097 lines were added to the destination table from the file Currency_VEB.txt.</span></span>  
  
2.  <span data-ttu-id="046d1-122">Terminada a execução do pacote, no menu **Depurar** , clique em **Parar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="046d1-122">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="046d1-123">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="046d1-123">Next Lesson</span></span>  
 [<span data-ttu-id="046d1-124">Lição 5: Como adicionar configurações de pacote para o modelo de implantação de pacote</span><span class="sxs-lookup"><span data-stu-id="046d1-124">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>](../integration-services/lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="046d1-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="046d1-125">See Also</span></span>  
 [<span data-ttu-id="046d1-126">Execução de projetos e pacotes</span><span class="sxs-lookup"><span data-stu-id="046d1-126">Execution of Projects and Packages</span></span>](packages/run-integration-services-ssis-packages.md)  
  
  
