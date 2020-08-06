---
title: 'Lição 2: adicionando looping | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 01f2ed61-1e5a-4ec6-b6a6-2bd070c64077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65efb84b4e50b470470e396bbe5681ce4b5dfac3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571441"
---
# <a name="lesson-2-adding-looping"></a><span data-ttu-id="ef0d8-102">Lição 2: Como adicionar um loop</span><span class="sxs-lookup"><span data-stu-id="ef0d8-102">Lesson 2: Adding Looping</span></span>
  <span data-ttu-id="ef0d8-103">Na [lição 1: criando o projeto e o pacote básico](lesson-1-create-a-project-and-basic-package-with-ssis.md), você criou um pacote que extraiu dados de uma única fonte de arquivo simples, transformou os dados usando transformações de pesquisa e, por fim, carregou os dados na tabela de fatos **FactCurrency** do banco de dados de exemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="ef0d8-103">In [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md), you created a package that extracted data from a single flat file source, transformed the data using Lookup transformations, and finally loaded the data into the **FactCurrency** fact table of the **AdventureWorksDW2012** sample database.</span></span>  
  
 <span data-ttu-id="ef0d8-104">Porém, é raro para um processo de extração, transformação e carregamento (ETL) usar um único arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-104">However, it is rare for an extract, transform, and load (ETL) process to use a single flat file.</span></span> <span data-ttu-id="ef0d8-105">Um típico processo ETL extrairia dados de várias fontes de arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-105">A typical ETL process would extract data from multiple flat file sources.</span></span> <span data-ttu-id="ef0d8-106">Extrair dados de várias fontes requer um fluxo de controle iterativo.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-106">Extracting data from multiple sources requires an iterative control flow.</span></span> <span data-ttu-id="ef0d8-107">Um dos recursos mais previstos do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] é a capacidade de adicionar iterações ou looping facilmente a pacotes.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-107">One of the most anticipated features of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is the ability to easily add iteration or looping to packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="ef0d8-108">fornece dois tipos de contêineres para efetuar loop por meio de pacotes: Foreach Loop e Loop For.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-108">provides two types of containers for looping through packages: the Foreach Loop container and the For Loop container.</span></span> <span data-ttu-id="ef0d8-109">O contêiner Foreach Loop usa um enumerador para executar o loop, enquanto que o contêiner For Loop geralmente usa uma expressão de variável.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-109">The Foreach Loop container uses an enumerator to perform the looping, whereas the For Loop container typically uses a variable expression.</span></span> <span data-ttu-id="ef0d8-110">Esta lição usa o contêiner Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-110">This lesson uses the Foreach Loop container.</span></span>  
  
 <span data-ttu-id="ef0d8-111">O contêiner Loop Foreach habilita um pacote a repetir o fluxo de controle para cada membro de um enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-111">The Foreach Loop container enables a package to repeat the control flow for each member of a specified enumerator.</span></span> <span data-ttu-id="ef0d8-112">Com o contêiner Loop Foreach, você pode enumerar:</span><span class="sxs-lookup"><span data-stu-id="ef0d8-112">With the Foreach Loop container, you can enumerate:</span></span>  
  
-   <span data-ttu-id="ef0d8-113">Linhas do conjunto de registros ADO</span><span class="sxs-lookup"><span data-stu-id="ef0d8-113">ADO recordset rows</span></span>  
  
-   <span data-ttu-id="ef0d8-114">Informações de esquema do ADO .Net</span><span class="sxs-lookup"><span data-stu-id="ef0d8-114">ADO .Net schema information</span></span>  
  
-   <span data-ttu-id="ef0d8-115">Estruturas de arquivo e diretório</span><span class="sxs-lookup"><span data-stu-id="ef0d8-115">File and directory structures</span></span>  
  
-   <span data-ttu-id="ef0d8-116">Variáveis de sistema, pacote e usuário</span><span class="sxs-lookup"><span data-stu-id="ef0d8-116">System, package and user variables</span></span>  
  
-   <span data-ttu-id="ef0d8-117">Objetos enumeráveis contidos em uma variável</span><span class="sxs-lookup"><span data-stu-id="ef0d8-117">Enumerable objects contained in a variable</span></span>  
  
-   <span data-ttu-id="ef0d8-118">Itens de uma coleção</span><span class="sxs-lookup"><span data-stu-id="ef0d8-118">Items in a collection</span></span>  
  
-   <span data-ttu-id="ef0d8-119">Nós em uma expressão XML Path Language (XPath)</span><span class="sxs-lookup"><span data-stu-id="ef0d8-119">Nodes in an XML Path Language (XPath) expression</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="ef0d8-120">SMO (Management Objects)</span><span class="sxs-lookup"><span data-stu-id="ef0d8-120">Management Objects (SMO)</span></span>  
  
 <span data-ttu-id="ef0d8-121">Nesta lição, você modificará o pacote ETL simples criado na lição 1 para aproveitar o contêiner Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-121">In this lesson, you will modify the simple ETL package created in Lesson 1 to take advantage of the Foreach Loop container.</span></span> <span data-ttu-id="ef0d8-122">Você também ajustará as variáveis do pacote definidas pelo usuário para habilitar o pacote do tutorial a ser iterado por todos os arquivos simples na pasta.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-122">You will also set user-defined package variables to enable the tutorial package to iterate through all the flat files in the folder.</span></span> <span data-ttu-id="ef0d8-123">Se você não tiver completado a lição anterior, também poderá copiar o pacote da Lição 1 terminada, que está incluído no tutorial.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-123">If you have not completed the previous lesson, you can also copy the completed Lesson 1 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="ef0d8-124">Nesta lição, você não modificará o fluxo de dados, apenas o fluxo de controle.</span><span class="sxs-lookup"><span data-stu-id="ef0d8-124">In this lesson, you will not modify the data flow, only the control flow.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ef0d8-125">Este tutorial requer o banco de dados de exemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="ef0d8-125">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="ef0d8-126">Para obter mais informações sobre como instalar e implantar o **AdventureWorksDW2012**, consulte [Amostras de produto do Reporting Services no CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="ef0d8-126">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="ef0d8-127">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="ef0d8-127">Lesson Tasks</span></span>  
 <span data-ttu-id="ef0d8-128">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="ef0d8-128">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="ef0d8-129">Etapa 1: Copiar o pacote da Lição 1</span><span class="sxs-lookup"><span data-stu-id="ef0d8-129">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
-   [<span data-ttu-id="ef0d8-130">Etapa 2: Adicionar e configurar o contêiner Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="ef0d8-130">Step 2: Adding and Configuring the Foreach Loop Container</span></span>](lesson-2-2-adding-and-configuring-the-foreach-loop-container.md)  
  
-   [<span data-ttu-id="ef0d8-131">Etapa 3: Modificar o gerenciador de conexões de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="ef0d8-131">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="ef0d8-132">Etapa 4: Testar o pacote de tutorial da Lição 2</span><span class="sxs-lookup"><span data-stu-id="ef0d8-132">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="ef0d8-133">Iniciar a lição</span><span class="sxs-lookup"><span data-stu-id="ef0d8-133">Start the Lesson</span></span>  
 [<span data-ttu-id="ef0d8-134">Etapa 1: Copiar o pacote da Lição 1</span><span class="sxs-lookup"><span data-stu-id="ef0d8-134">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="ef0d8-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ef0d8-135">See Also</span></span>  
 [<span data-ttu-id="ef0d8-136">Contêiner Loop For</span><span class="sxs-lookup"><span data-stu-id="ef0d8-136">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  
