---
title: 'Lição 1: criando o projeto e o pacote básico | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 84d0b877-603f-4f8e-bb6b-671558ade5c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a9ddc36ef242cc4e4b146e90dfa9de470e68d83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574125"
---
# <a name="lesson-1-creating-the-project-and-basic-package"></a><span data-ttu-id="605c8-102">Lição 1: Como criar o projeto e o pacote básico</span><span class="sxs-lookup"><span data-stu-id="605c8-102">Lesson 1: Creating the Project and Basic Package</span></span>
  <span data-ttu-id="605c8-103">Nessa lição, você criará um pacote ETL simples que extrai dados de uma fonte exclusiva de arquivo simples, transforma os dados usando dois componentes de transformação pesquisa e grava esses dados na tabela de fatos **FactCurrency** no **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="605c8-103">In this lesson, you will create a simple ETL package that extracts data from a single flat file source, transforms the data using two lookup transformation components, and writes that data to the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span> <span data-ttu-id="605c8-104">Como parte dessa lição, você irá aprender como criar novos pacotes, adicionar e configurar fonte de dados, e conexões de destino, e trabalhar com novos fluxos de controle e componentes de fluxo.</span><span class="sxs-lookup"><span data-stu-id="605c8-104">As part of this lesson, you will learn how to create new packages, add and configure data source and destination connections, and work with new control flow and data flow components.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="605c8-105">Este tutorial requer o banco de dados de exemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="605c8-105">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="605c8-106">Para obter mais informações sobre como instalar e implantar o **AdventureWorksDW2012**, consulte [Microsoft SQL Server exemplos de produtos: Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span><span class="sxs-lookup"><span data-stu-id="605c8-106">For more information on installing and deploying **AdventureWorksDW2012**, see [Microsoft SQL Server Product Samples: Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span></span>  
  
## <a name="understanding-the-package-requirements"></a><span data-ttu-id="605c8-107">Compreendendo os requisitos de pacote</span><span class="sxs-lookup"><span data-stu-id="605c8-107">Understanding the Package Requirements</span></span>  
 <span data-ttu-id="605c8-108">Este tutorial requer o Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="605c8-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
  
 <span data-ttu-id="605c8-109">Para obter mais informações sobre como instalar o SQL Server Data Tools, consulte [Download do SQL Server Data Tools](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span><span class="sxs-lookup"><span data-stu-id="605c8-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span></span>  
  
 <span data-ttu-id="605c8-110">Antes de criar um pacote, você precisa ter um bom conhecimento da formatação usada tanto na fonte de dados quanto no destino.</span><span class="sxs-lookup"><span data-stu-id="605c8-110">Before creating a package, you need a good understanding of the formatting used in both the source data and the destination.</span></span> <span data-ttu-id="605c8-111">Depois de entender estes dois formatos de dados, você estará pronto para definir as transformações necessárias para mapear a fonte de dados ao destino.</span><span class="sxs-lookup"><span data-stu-id="605c8-111">Once you understand both of these data formats, you will be ready to define the transformations necessary to map the source data to the destination.</span></span>  
  
### <a name="looking-at-the-source"></a><span data-ttu-id="605c8-112">Olhando para a Fonte</span><span class="sxs-lookup"><span data-stu-id="605c8-112">Looking at the Source</span></span>  
 <span data-ttu-id="605c8-113">Nesse tutorial, os dados de origem são um conjunto de dados de moeda corrente históricos contidos no arquivo simples, SampleCurrencyData.txt.</span><span class="sxs-lookup"><span data-stu-id="605c8-113">For this tutorial, the source data is a set of historical currency data contained in the flat file, SampleCurrencyData.txt.</span></span> <span data-ttu-id="605c8-114">A fonte de dados tem as seguintes quatro colunas: a taxa média de moeda, uma chave de moeda, uma chave de data e a taxa de final do dia.</span><span class="sxs-lookup"><span data-stu-id="605c8-114">The source data has the following four columns: the average rate of the currency, a currency key, a date key, and the end-of-day rate.</span></span>  
  
 <span data-ttu-id="605c8-115">Aqui está um exemplo dos dados de origem contidos no arquivo SampleCurrencyData.txt:</span><span class="sxs-lookup"><span data-stu-id="605c8-115">Here is an example of the source data contained in the SampleCurrencyData.txt file:</span></span>  
  
 `1.00070049USD9/3/05 0:001.001201442`  
  
 `1.00020004USD9/4/05 0:001`  
  
 `1.00020004USD9/5/05 0:001.001201442`  
  
 `1.00020004USD9/6/05 0:001`  
  
 `1.00020004USD9/7/05 0:001.00070049`  
  
 `1.00070049USD9/8/05 0:000.99980004`  
  
 `1.00070049USD9/9/05 0:001.001502253`  
  
 `1.00070049USD9/10/05 0:000.99990001`  
  
 `1.00020004USD9/11/05 0:001.001101211`  
  
 `1.00020004USD9/12/05 0:000.99970009`  
  
 <span data-ttu-id="605c8-116">Quando estiver trabalhando com dados de fonte de arquivo simples, é importante entender como o gerenciador de conexões de Arquivo Simples interpreta os dados de arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="605c8-116">When working with flat file source data, it is important to understand how the Flat File connection manager interprets the flat file data.</span></span> <span data-ttu-id="605c8-117">Se a fonte do arquivo simples for Unicode, o gerenciador de conexões de Arquivo Simples definirá todas as colunas como [DT_WSTR] com uma largura padrão de coluna de 50.</span><span class="sxs-lookup"><span data-stu-id="605c8-117">If the flat file source is Unicode, the Flat File connection manager defines all columns as [DT_WSTR] with a default column width of 50.</span></span> <span data-ttu-id="605c8-118">Se a fonte de arquivo simples for codificada por ANSI, as colunas estarão definidas como [DT_STR] com uma largura de coluna de 50.</span><span class="sxs-lookup"><span data-stu-id="605c8-118">If the flat file source is ANSI-encoded, the columns are defined as [DT_STR] with a column width of 50.</span></span> <span data-ttu-id="605c8-119">Você provavelmente terá que alterar esses padrões para tornar os tipos de coluna de cadeia de caracteres mais apropriados para seus dados.</span><span class="sxs-lookup"><span data-stu-id="605c8-119">You will probably have to change these defaults to make the string column types more appropriate for your data.</span></span> <span data-ttu-id="605c8-120">Para fazer isso, você precisará olhar o tipo de dados do destino onde os dados serão gravados, e, então, escolher o tipo correto dentro do gerenciador de conexões de Arquivo Simples.</span><span class="sxs-lookup"><span data-stu-id="605c8-120">To do this, you will need to look at the data type of the destination where the data will be written to and then choose the correct type within the Flat File connection manager.</span></span>  
  
### <a name="looking-at-the-destination"></a><span data-ttu-id="605c8-121">Olhando o destino</span><span class="sxs-lookup"><span data-stu-id="605c8-121">Looking at the Destination</span></span>  
 <span data-ttu-id="605c8-122">O destino final dos dados de origem é a tabela de fatos **FactCurrency** no **AdventureWorksDW**.</span><span class="sxs-lookup"><span data-stu-id="605c8-122">The ultimate destination for the source data is the **FactCurrency** fact table in **AdventureWorksDW**.</span></span> <span data-ttu-id="605c8-123">A tabela de fatos **FactCurrency** tem quatro colunas e relacionamentos com duas tabelas de dimensões, como mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="605c8-123">The **FactCurrency** fact table has four columns, and has relationships to two dimension tables, as shown in the following table.</span></span>  
  
|<span data-ttu-id="605c8-124">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="605c8-124">Column Name</span></span>|<span data-ttu-id="605c8-125">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="605c8-125">Data Type</span></span>|<span data-ttu-id="605c8-126">Tabela de pesquisa</span><span class="sxs-lookup"><span data-stu-id="605c8-126">Lookup Table</span></span>|<span data-ttu-id="605c8-127">coluna de pesquisa</span><span class="sxs-lookup"><span data-stu-id="605c8-127">Lookup Column</span></span>|  
|-----------------|---------------|------------------|-------------------|  
|<span data-ttu-id="605c8-128">AverageRate</span><span class="sxs-lookup"><span data-stu-id="605c8-128">AverageRate</span></span>|<span data-ttu-id="605c8-129">FLOAT</span><span class="sxs-lookup"><span data-stu-id="605c8-129">float</span></span>|<span data-ttu-id="605c8-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="605c8-130">None</span></span>|<span data-ttu-id="605c8-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="605c8-131">None</span></span>|  
|<span data-ttu-id="605c8-132">CurrencyKey</span><span class="sxs-lookup"><span data-stu-id="605c8-132">CurrencyKey</span></span>|<span data-ttu-id="605c8-133">int (FK)</span><span class="sxs-lookup"><span data-stu-id="605c8-133">int (FK)</span></span>|<span data-ttu-id="605c8-134">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="605c8-134">DimCurrency</span></span>|<span data-ttu-id="605c8-135">CurrencyKey (PK)</span><span class="sxs-lookup"><span data-stu-id="605c8-135">CurrencyKey (PK)</span></span>|  
|<span data-ttu-id="605c8-136">DateKey</span><span class="sxs-lookup"><span data-stu-id="605c8-136">DateKey</span></span>|<span data-ttu-id="605c8-137">int (FK)</span><span class="sxs-lookup"><span data-stu-id="605c8-137">Int (FK)</span></span>|<span data-ttu-id="605c8-138">DimDate</span><span class="sxs-lookup"><span data-stu-id="605c8-138">DimDate</span></span>|<span data-ttu-id="605c8-139">DateKey (PK)</span><span class="sxs-lookup"><span data-stu-id="605c8-139">DateKey (PK)</span></span>|  
|<span data-ttu-id="605c8-140">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="605c8-140">EndOfDayRate</span></span>|<span data-ttu-id="605c8-141">FLOAT</span><span class="sxs-lookup"><span data-stu-id="605c8-141">float</span></span>|<span data-ttu-id="605c8-142">Nenhum</span><span class="sxs-lookup"><span data-stu-id="605c8-142">None</span></span>|<span data-ttu-id="605c8-143">Nenhum</span><span class="sxs-lookup"><span data-stu-id="605c8-143">None</span></span>|  
  
### <a name="mapping-source-data-to-be-compatible-with-the-destination"></a><span data-ttu-id="605c8-144">Mapeando fontes de dados compatíveis com o destino</span><span class="sxs-lookup"><span data-stu-id="605c8-144">Mapping Source Data to be Compatible with the Destination</span></span>  
 <span data-ttu-id="605c8-145">Uma análise dos formatos de dados de origem e destino indicam que as pesquisas serão necessárias para os valores **CurrencyKey** e **DateKey** .</span><span class="sxs-lookup"><span data-stu-id="605c8-145">Analysis of the source and destination data formats indicates that lookups will be necessary for the **CurrencyKey** and **DateKey** values.</span></span> <span data-ttu-id="605c8-146">As transformações que executarão essas pesquisas obterão os valores **CurrencyKey** e **DateKey** usando as chaves alternativas das tabelas de dimensões **DimCurrency** e **DimDate** .</span><span class="sxs-lookup"><span data-stu-id="605c8-146">The transformations that will perform these lookups will obtain the **CurrencyKey** and **DateKey** values by using the alternate keys from **DimCurrency** and **DimDate** dimension tables.</span></span>  
  
|<span data-ttu-id="605c8-147">Coluna de Arquivos Simples</span><span class="sxs-lookup"><span data-stu-id="605c8-147">Flat File Column</span></span>|<span data-ttu-id="605c8-148">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="605c8-148">Table Name</span></span>|<span data-ttu-id="605c8-149">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="605c8-149">Column Name</span></span>|<span data-ttu-id="605c8-150">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="605c8-150">Data Type</span></span>|  
|----------------------|----------------|-----------------|---------------|  
|<span data-ttu-id="605c8-151">0</span><span class="sxs-lookup"><span data-stu-id="605c8-151">0</span></span>|<span data-ttu-id="605c8-152">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="605c8-152">FactCurrency</span></span>|<span data-ttu-id="605c8-153">AverageRate</span><span class="sxs-lookup"><span data-stu-id="605c8-153">AverageRate</span></span>|<span data-ttu-id="605c8-154">FLOAT</span><span class="sxs-lookup"><span data-stu-id="605c8-154">float</span></span>|  
|<span data-ttu-id="605c8-155">1</span><span class="sxs-lookup"><span data-stu-id="605c8-155">1</span></span>|<span data-ttu-id="605c8-156">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="605c8-156">DimCurrency</span></span>|<span data-ttu-id="605c8-157">CurrencyAlternateKey</span><span class="sxs-lookup"><span data-stu-id="605c8-157">CurrencyAlternateKey</span></span>|<span data-ttu-id="605c8-158">nchar (3)</span><span class="sxs-lookup"><span data-stu-id="605c8-158">nchar (3)</span></span>|  
|<span data-ttu-id="605c8-159">2</span><span class="sxs-lookup"><span data-stu-id="605c8-159">2</span></span>|<span data-ttu-id="605c8-160">DimDate</span><span class="sxs-lookup"><span data-stu-id="605c8-160">DimDate</span></span>|<span data-ttu-id="605c8-161">FullDateAlternateKey</span><span class="sxs-lookup"><span data-stu-id="605c8-161">FullDateAlternateKey</span></span>|<span data-ttu-id="605c8-162">date</span><span class="sxs-lookup"><span data-stu-id="605c8-162">date</span></span>|  
|<span data-ttu-id="605c8-163">3</span><span class="sxs-lookup"><span data-stu-id="605c8-163">3</span></span>|<span data-ttu-id="605c8-164">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="605c8-164">FactCurrency</span></span>|<span data-ttu-id="605c8-165">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="605c8-165">EndOfDayRate</span></span>|<span data-ttu-id="605c8-166">FLOAT</span><span class="sxs-lookup"><span data-stu-id="605c8-166">float</span></span>|  
  
## <a name="lesson-tasks"></a><span data-ttu-id="605c8-167">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="605c8-167">Lesson Tasks</span></span>  
 <span data-ttu-id="605c8-168">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="605c8-168">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="605c8-169">Etapa 1: Criar um novo projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="605c8-169">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="605c8-170">Etapa 2: Adicionar e configurar um gerenciador de conexões de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="605c8-170">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="605c8-171">Etapa 3: Adicionar e configurar um gerenciador de conexões OLE DB</span><span class="sxs-lookup"><span data-stu-id="605c8-171">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>](lesson-1-3-adding-and-configuring-an-ole-db-connection-manager.md)  
  
-   [<span data-ttu-id="605c8-172">Etapa 4: Adicionar uma tarefa de fluxo de dados ao pacote</span><span class="sxs-lookup"><span data-stu-id="605c8-172">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
-   [<span data-ttu-id="605c8-173">Etapa 5: Adicionar e configurar a fonte de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="605c8-173">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
-   [<span data-ttu-id="605c8-174">Etapa 6: Adicionar e configurar a transformação Pesquisa</span><span class="sxs-lookup"><span data-stu-id="605c8-174">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
-   [<span data-ttu-id="605c8-175">Etapa 7: Adicionar e configurar o destino OLE DB</span><span class="sxs-lookup"><span data-stu-id="605c8-175">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
-   [<span data-ttu-id="605c8-176">Etapa 8: Tornar o pacote da Lição 1 mais fácil de compreender</span><span class="sxs-lookup"><span data-stu-id="605c8-176">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
-   [<span data-ttu-id="605c8-177">Etapa 9: Testar o pacote de tutorial da Lição 1</span><span class="sxs-lookup"><span data-stu-id="605c8-177">Step 9: Testing the Lesson 1 Tutorial Package</span></span>](lesson-1-9-testing-the-lesson-1-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="605c8-178">Iniciar a lição</span><span class="sxs-lookup"><span data-stu-id="605c8-178">Start the Lesson</span></span>  
 [<span data-ttu-id="605c8-179">Etapa 1: Criar um novo projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="605c8-179">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
  
