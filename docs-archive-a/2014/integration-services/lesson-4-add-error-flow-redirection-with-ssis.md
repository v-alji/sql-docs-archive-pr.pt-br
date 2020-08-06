---
title: 'Lição 4: adicionando o redirecionamento de fluxo de erro | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c8dbda2-75e3-4278-9b4e-dcd220c92522
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5b1d1ff9abf59a6288d1b693fce5a6fb707a129b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685207"
---
# <a name="lesson-4-adding-error-flow-redirection"></a><span data-ttu-id="0f74a-102">Lição 4: Adicionar redirecionamento de fluxo de erro</span><span class="sxs-lookup"><span data-stu-id="0f74a-102">Lesson 4: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="0f74a-103">Para lidar com erros que podem ocorrer no processo de transformação, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o oferece a capacidade de decidir por componente e por coluna como manipular dados que não podem ser transformados.</span><span class="sxs-lookup"><span data-stu-id="0f74a-103">To handle errors that may occur in the transformation process, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gives you the ability to decide on a per component and per column basis how to handle data that cannot be transformed.</span></span> <span data-ttu-id="0f74a-104">Você pode escolher ignorar uma falha em determinadas colunas, redirecionar toda a linha com falha ou apenas causar falha no componente.</span><span class="sxs-lookup"><span data-stu-id="0f74a-104">You can choose to ignore a failure in certain columns, redirect the entire failed row, or just fail the component.</span></span> <span data-ttu-id="0f74a-105">Por padrão, todos os componentes no [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] são configurados para falhar quando ocorrerem erros.</span><span class="sxs-lookup"><span data-stu-id="0f74a-105">By default, all components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are configured to fail when errors occur.</span></span> <span data-ttu-id="0f74a-106">Causar falha em um componente, por sua vez, faz com que o pacote falhe e todo o processamento subsequente pare.</span><span class="sxs-lookup"><span data-stu-id="0f74a-106">Failing a component, in turn, causes the package to fail and all subsequent processing to stop.</span></span>  
  
 <span data-ttu-id="0f74a-107">Em vez de permitir que as falhas interrompam a execução do pacote, é bom configurar e tratar erros de processamento em potencial conforme ocorrem dentro da transformação.</span><span class="sxs-lookup"><span data-stu-id="0f74a-107">Instead of letting failures stop package execution, it is good practice to configure and handle potential processing errors as they occur within the transformation.</span></span> <span data-ttu-id="0f74a-108">Como você pode escolher ignorar as falhas para garantir que seu pacote seja executado com êxito, frequentemente é melhor redirecionar a linha com falhas para outro caminho de processamento, em que os dados e o erro podem ser persistentes, examinados e reprocessados posteriormente.</span><span class="sxs-lookup"><span data-stu-id="0f74a-108">While you might choose to ignore failures to ensure your package runs successfully, it is often better to redirect the failed row to another processing path where the data and the error can be persisted, examined and reprocessed at a later time.</span></span>  
  
 <span data-ttu-id="0f74a-109">Nesta lição, você criará uma cópia do pacote desenvolvido em [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="0f74a-109">In this lesson, you will create a copy of the package that you developed in [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md).</span></span> <span data-ttu-id="0f74a-110">Ao trabalhar com este pacote novo, você criará uma versão corrompida de um dos arquivos de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="0f74a-110">Working with this new package, you will create a corrupted version of one of the sample data files.</span></span> <span data-ttu-id="0f74a-111">O arquivo corrompido forçará a ocorrência de um erro de processamento quando você executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="0f74a-111">The corrupted file will force a processing error to occur when you run the package.</span></span>  
  
 <span data-ttu-id="0f74a-112">Para tratar os dados de erro, você adicionará e configurará um destino de Arquivo Simples que gravará qualquer linha que não localize um valor de pesquisa na transformação Pesquisa de Códigos de Moeda em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0f74a-112">To handle the error data, you will add and configure a Flat File destination that will write any rows that fail to locate a lookup value in the Lookup Currency Key transformation to a file.</span></span>  
  
 <span data-ttu-id="0f74a-113">Antes que os dados de erro sejam gravados em um arquivo, você incluirá um componente Script que utiliza script para obter as descrições de erro.</span><span class="sxs-lookup"><span data-stu-id="0f74a-113">Before the error data is written to the file, you will include a Script component that uses script to get error descriptions.</span></span> <span data-ttu-id="0f74a-114">Você reconfigurará, então, a transformação Pesquisa de Códigos de Moeda para redirecionar qualquer dado que não possa ser processado para a transformação Script.</span><span class="sxs-lookup"><span data-stu-id="0f74a-114">You will then reconfigure the Lookup Currency Key transformation to redirect any data that could not be processed to the Script transformation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0f74a-115">Este tutorial requer o banco de dados de exemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="0f74a-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="0f74a-116">Para obter mais informações sobre como instalar e implantar o **AdventureWorksDW2012**, consulte [Reporting Services Product Samples on CodePlex (Amostras de produto do Reporting Services no CodePlex)](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span><span class="sxs-lookup"><span data-stu-id="0f74a-116">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples Project on CodePlex](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span></span>  
  
## <a name="tasks-in-lesson"></a><span data-ttu-id="0f74a-117">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="0f74a-117">Tasks in Lesson</span></span>  
 <span data-ttu-id="0f74a-118">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="0f74a-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="0f74a-119">Etapa 1: Copiar o pacote da Lição 3</span><span class="sxs-lookup"><span data-stu-id="0f74a-119">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
-   [<span data-ttu-id="0f74a-120">Etapa 2: Criar um arquivo corrompido</span><span class="sxs-lookup"><span data-stu-id="0f74a-120">Step 2: Creating a Corrupted File</span></span>](lesson-4-2-creating-a-corrupted-file.md)  
  
-   [<span data-ttu-id="0f74a-121">Etapa 3: Adicionar redirecionamento de fluxo de erro</span><span class="sxs-lookup"><span data-stu-id="0f74a-121">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
-   [<span data-ttu-id="0f74a-122">Etapa 4: Adicionar um destino de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="0f74a-122">Step 4: Adding a Flat File Destination</span></span>](lesson-4-4-adding-a-flat-file-destination.md)  
  
-   [<span data-ttu-id="0f74a-123">Etapa 5: Testar o pacote de tutorial da Lição 4</span><span class="sxs-lookup"><span data-stu-id="0f74a-123">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="0f74a-124">Iniciar a lição</span><span class="sxs-lookup"><span data-stu-id="0f74a-124">Start the Lesson</span></span>  
 [<span data-ttu-id="0f74a-125">Etapa 1: Copiar o pacote da Lição 3</span><span class="sxs-lookup"><span data-stu-id="0f74a-125">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
  
