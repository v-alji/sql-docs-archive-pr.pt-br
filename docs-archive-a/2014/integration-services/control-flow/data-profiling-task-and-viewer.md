---
title: Visualizador e tarefa criação de perfil de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], about data profiling
- data profiling
- profiling data
ms.assetid: 756840e3-aa09-45cd-9951-1a17af4b5925
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ae15d1cc75f8db04c36a830e44d07800c5aecf75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572634"
---
# <a name="data-profiling-task-and-viewer"></a><span data-ttu-id="cd214-102">Tarefa e visualizador da tarefa Criação de Perfil de Dados</span><span class="sxs-lookup"><span data-stu-id="cd214-102">Data Profiling Task and Viewer</span></span>
  <span data-ttu-id="cd214-103">A tarefa Criação de Perfil de Dados fornece a funcionalidade de criação de perfil de dados dentro do processo de extração, transformação e carga de dados.</span><span class="sxs-lookup"><span data-stu-id="cd214-103">The Data Profiling task provides data profiling functionality inside the process of extracting, transforming, and loading data.</span></span> <span data-ttu-id="cd214-104">Usando a tarefa Criação de Perfil de Dados, você pode alcançar os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="cd214-104">By using the Data Profiling task, you can achieve the following benefits:</span></span>  
  
-   <span data-ttu-id="cd214-105">Analisar os dados de origem mais efetivamente</span><span class="sxs-lookup"><span data-stu-id="cd214-105">Analyze the source data more effectively</span></span>  
  
-   <span data-ttu-id="cd214-106">Entender melhor os dados de origem</span><span class="sxs-lookup"><span data-stu-id="cd214-106">Understand the source data better</span></span>  
  
-   <span data-ttu-id="cd214-107">Prevenir problemas de qualidade dos dados antes que eles sejam introduzidos no data warehouse.</span><span class="sxs-lookup"><span data-stu-id="cd214-107">Prevent data quality problems before they are introduced into the data warehouse.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd214-108">A tarefa Criação de Perfil de Dados funciona apenas com dados armazenados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd214-108">The Data Profiling task works only with data that is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cd214-109">Ela não funciona com fontes de dados de terceiros ou baseadas em arquivos.</span><span class="sxs-lookup"><span data-stu-id="cd214-109">It does not work with third-party or file-based data sources.</span></span>  
  
## <a name="data-profiling-overview"></a><span data-ttu-id="cd214-110">Visão geral da Criação de Perfil de Dados</span><span class="sxs-lookup"><span data-stu-id="cd214-110">Data Profiling Overview</span></span>  
 <span data-ttu-id="cd214-111">A qualidade dos dados é importante para todo negócio.</span><span class="sxs-lookup"><span data-stu-id="cd214-111">Data quality is important to every business.</span></span> <span data-ttu-id="cd214-112">Como as empresas constroem sistemas analíticos e de business intelligence no topo de seus sistemas transacionais, a confiabilidade dos indicadores chave de desempenho e das previsões da mineração de dados, depende completamente da validade dos dados onde eles são baseados.</span><span class="sxs-lookup"><span data-stu-id="cd214-112">As enterprises build analytical and business intelligence systems on top of their transactional systems, the reliability of key performance indicators and of data mining predictions depends completely on the validity of the data on which they are based.</span></span> <span data-ttu-id="cd214-113">Mas, embora a importância da validade dos dados para a realização das decisões de negócios esteja crescendo, o desafio de certificar-se da validade dos dados também está aumentando.</span><span class="sxs-lookup"><span data-stu-id="cd214-113">But although the importance of valid data for business decision-making is increasing, the challenge of making sure of this data's validity is also increasing.</span></span> <span data-ttu-id="cd214-114">Dentro da empresa os dados estão fluindo constantemente de diversos sistemas e fontes e de um grande número de usuários.</span><span class="sxs-lookup"><span data-stu-id="cd214-114">Data is streaming into the enterprise constantly from diverse systems and sources, and a large numbers of users.</span></span>  
  
 <span data-ttu-id="cd214-115">Métrica para qualidade de dados pode ser difícil de definir porque eles são específicos ao domínio ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cd214-115">Metrics for data quality can be difficult to define because they are specific to the domain or the application.</span></span> <span data-ttu-id="cd214-116">Uma abordagem comum para definir qualidade de dados é a criação de perfil de dados.</span><span class="sxs-lookup"><span data-stu-id="cd214-116">One common approach to defining data quality is data profiling.</span></span>  
  
 <span data-ttu-id="cd214-117">Um perfil de dados é uma coleção de estatísticas de agregação sobre os dados que podem incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cd214-117">A data profile is a collection of aggregate statistics about data that might include the following:</span></span>  
  
-   <span data-ttu-id="cd214-118">O número de linhas na tabela Cliente.</span><span class="sxs-lookup"><span data-stu-id="cd214-118">The number of rows in the Customer table.</span></span>  
  
-   <span data-ttu-id="cd214-119">O número de valores distintos na coluna Estado.</span><span class="sxs-lookup"><span data-stu-id="cd214-119">The number of distinct values in the State column.</span></span>  
  
-   <span data-ttu-id="cd214-120">O número de valores ausentes ou nulos na coluna Zip.</span><span class="sxs-lookup"><span data-stu-id="cd214-120">The number of null or missing values in the Zip column.</span></span>  
  
-   <span data-ttu-id="cd214-121">A distribuição de valores na coluna Cidade.</span><span class="sxs-lookup"><span data-stu-id="cd214-121">The distribution of values in the City column.</span></span>  
  
-   <span data-ttu-id="cd214-122">A intensidade da dependência funcional da coluna Estado na coluna Zip, ou seja, o Estado deve sempre ser o mesmo para determinado valor de Zip.</span><span class="sxs-lookup"><span data-stu-id="cd214-122">The strength of the functional dependency of the State column on the Zip column-that is, the state should always be the same for a given zip value.</span></span>  
  
 <span data-ttu-id="cd214-123">As estatísticas que a criação de perfil de dados provê, fornecem a informação necessária para efetivamente minimizar as perdas de qualidade que podem ocorrer do uso da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="cd214-123">The statistics that a data profile provides gives you the information that you need in order to effectively minimize the quality issues that might occur from using the source data.</span></span>  
  
## <a name="integration-services-and-data-profiling"></a><span data-ttu-id="cd214-124">Integration Services e criação de perfil de dados</span><span class="sxs-lookup"><span data-stu-id="cd214-124">Integration Services and Data Profiling</span></span>  
 <span data-ttu-id="cd214-125">Em [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], o processo de criação de perfil de dados consiste nas seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="cd214-125">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the data profiling process consist of the following steps:</span></span>  
  
 <span data-ttu-id="cd214-126">**Etapa 1: configurar a tarefa de criação de perfil de dados**</span><span class="sxs-lookup"><span data-stu-id="cd214-126">**Step 1: Setting up the Data Profiling Task**</span></span>  
 <span data-ttu-id="cd214-127">A tarefa Criação de Perfil de Dados é uma tarefa que você usa para configurar os perfis que deseja calcular.</span><span class="sxs-lookup"><span data-stu-id="cd214-127">The Data Profiling task is a task that you use to configure the profiles that you want to compute.</span></span> <span data-ttu-id="cd214-128">Você executa o pacote que contém a tarefa de Criação de Perfil de Dados para computar os perfis.</span><span class="sxs-lookup"><span data-stu-id="cd214-128">You then run the package that contains the Data Profiling task to compute the profiles.</span></span> <span data-ttu-id="cd214-129">A tarefa salva o perfil produzido em formato de XML em um arquivo ou uma variável de pacote.</span><span class="sxs-lookup"><span data-stu-id="cd214-129">The task saves the profile output in XML format to a file or a package variable.</span></span>  
  
 <span data-ttu-id="cd214-130">**Para obter mais informações, consulte:** [Configuração da tarefa Criação de Perfil de Dados](data-profiling-task.md)</span><span class="sxs-lookup"><span data-stu-id="cd214-130">**For more information:** [Setup of the Data Profiling Task](data-profiling-task.md)</span></span>  
  
 <span data-ttu-id="cd214-131">**Etapa 2: revisar os perfis que a tarefa Criação de Perfis de Dados computa**</span><span class="sxs-lookup"><span data-stu-id="cd214-131">**Step 2: Reviewing the Profiles that the Data Profiling Task Computes**</span></span>  
 <span data-ttu-id="cd214-132">Para exibir os perfis de dados que a tarefa Criação de Perfil de Dados computa, envie a saída para um arquivo e utilize o Visualizador de Perfil de dados</span><span class="sxs-lookup"><span data-stu-id="cd214-132">To view the data profiles that the Data Profiling task computes, you send the output to a file, and then you use the Data Profile Viewer.</span></span> <span data-ttu-id="cd214-133">Esse visualizador é um utilitário autônomo que mostra a saída do perfil em formato resumido e detalhado com uma capacidade opcional de busca.</span><span class="sxs-lookup"><span data-stu-id="cd214-133">This viewer is a stand-alone utility that displays the profile output in both summary and detail format with optional drilldown capability.</span></span>  
  
 <span data-ttu-id="cd214-134">**Para obter mais informações, consulte:** [Visualizador de Perfil de Dados](data-profile-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="cd214-134">**For more information:** [Data Profile Viewer](data-profile-viewer.md)</span></span>  
  
### <a name="addition-of-conditional-logic-to-the-data-profiling-workflow"></a><span data-ttu-id="cd214-135">Adição de lógica condicional ao fluxo de trabalho de criação de perfil de dados.</span><span class="sxs-lookup"><span data-stu-id="cd214-135">Addition of Conditional Logic to the Data Profiling Workflow</span></span>  
 <span data-ttu-id="cd214-136">A tarefa Criação de Perfil de Dados não tem recursos internos que lhe permitam usar lógica condicional para conectar essa tarefa a tarefas de downstream com base na saída do perfil.</span><span class="sxs-lookup"><span data-stu-id="cd214-136">The Data Profiling task does not have built-in features that allow you to use conditional logic to connect this task to downstream tasks based on the profile output.</span></span> <span data-ttu-id="cd214-137">Porém, você pode adicionar facilmente esta lógica, com uma quantidade pequena de programação, em uma tarefa de Script.</span><span class="sxs-lookup"><span data-stu-id="cd214-137">However, you can easily add this logic, with a small amount of programming, in a Script task.</span></span> <span data-ttu-id="cd214-138">Por exemplo, a tarefa Script poderia executar uma consulta XPath contra o arquivo de saída da tarefa de Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="cd214-138">For example, the Script task could perform an XPath query against the output file of the Data Profiling task.</span></span> <span data-ttu-id="cd214-139">A consulta poderia determinar se a porcentagem de valores nulos em uma coluna particular excede certo limite.</span><span class="sxs-lookup"><span data-stu-id="cd214-139">The query could determine whether the percentage of null values in a particular column exceeds a certain threshold.</span></span> <span data-ttu-id="cd214-140">Se a porcentagem exceder o limite, você pode interromper o pacote e resolver o problema na fonte de dados antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="cd214-140">If the percentage exceeds the threshold, you could interrupt the package and resolve the problem in the source data before continuing.</span></span> <span data-ttu-id="cd214-141">Para obter informações, consulte [Incorporar uma tarefa Criação de Perfil de Dados no fluxo de trabalho do pacote](incorporate-a-data-profiling-task-in-package-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="cd214-141">For more information, see [Incorporate a Data Profiling Task in Package Workflow](incorporate-a-data-profiling-task-in-package-workflow.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="cd214-142">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="cd214-142">Related Content</span></span>  
 [<span data-ttu-id="cd214-143">Esquema do criador de perfil de dados</span><span class="sxs-lookup"><span data-stu-id="cd214-143">Data Profiler Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=251524)  
  
  
