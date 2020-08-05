---
title: Tarefa Executar DDL do Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.f1
helpviewer_keywords:
- Analysis Services Execute DDL task
- DDL
ms.assetid: 7f25c8c6-b601-41f2-9553-be0a2ee0751a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a75bae174c816cdabd07ce688e068cbadb016b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574216"
---
# <a name="analysis-services-execute-ddl-task"></a><span data-ttu-id="8678d-102">Tarefa Executar DDL do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8678d-102">Analysis Services Execute DDL Task</span></span>
  <span data-ttu-id="8678d-103">A tarefa Executar DLL do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] executa instruções DDL (linguagem de definição de dados) que podem criar, descartar ou alterar modelos de mineração e objetos multidimensionais, como cubos e dimensões.</span><span class="sxs-lookup"><span data-stu-id="8678d-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task runs data definition language (DDL) statements that can create, drop, or alter mining models and multidimensional objects such as cubes and dimensions.</span></span> <span data-ttu-id="8678d-104">Por exemplo, uma instrução DDL pode criar uma partição no cubo **Adventure Works** ou excluir uma dimensão do [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], o exemplo de banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incluído no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8678d-104">For example, a DDL statement can create a partition in the **Adventure Works** cube, or delete a dimension in [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8678d-105">A tarefa Executar DDL do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usa um gerenciador de conexões do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para se conectar a uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou a um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8678d-105">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="8678d-106">Para obter mais informações, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8678d-106">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="8678d-107">inclui um número de tarefas que desempenham outras operações de business intelligence, como processamento de objetos analíticos e execução de consultas de previsão de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="8678d-107">includes a number of tasks that perform business intelligence operations, such as processing analytic objects and running data mining prediction queries.</span></span>  
  
 <span data-ttu-id="8678d-108">Para obter mais informações sobre tarefas de business intelligence relacionadas, clique em um dos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="8678d-108">For more information about related business intelligence tasks, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8678d-109">Tarefa Processamento do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8678d-109">Analysis Services Processing Task</span></span>](analysis-services-processing-task.md)  
  
-   [<span data-ttu-id="8678d-110">Tarefa Consulta de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="8678d-110">Data Mining Query Task</span></span>](data-mining-query-task.md)  
  
## <a name="ddl-statements"></a><span data-ttu-id="8678d-111">Instruções DDL</span><span class="sxs-lookup"><span data-stu-id="8678d-111">DDL Statements</span></span>  
 <span data-ttu-id="8678d-112">As instruções DDL são representadas como instruções no ASSL (Analysis Services Scripting Language) do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e são enquadradas em um comando XMLA (XML for Analysis).</span><span class="sxs-lookup"><span data-stu-id="8678d-112">The DDL statements are represented as statements in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language (ASSL), and framed in an XML for Analysis (XMLA) command.</span></span>  
  
-   <span data-ttu-id="8678d-113">O ASSL é usado para definir e descrever uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e os bancos de dados e objetos de banco de dados que ela contém.</span><span class="sxs-lookup"><span data-stu-id="8678d-113">ASSL is used to define and describe an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and the databases and database objects it contains.</span></span> <span data-ttu-id="8678d-114">Para obter mais informações, consulte [Analysis Services linguagem de script &#40;ASSL&#41; referência](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span><span class="sxs-lookup"><span data-stu-id="8678d-114">For more information, see [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span></span>  
  
-   <span data-ttu-id="8678d-115">O XMLA é uma linguagem de comandos usada para enviar comandos de ação, como Criar, Alterar ou Processar para uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8678d-115">XMLA is a command language that is used to send action commands, such as Create, Alter, or Process, to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="8678d-116">Para obter mais informações, consulte [Referência do XMLA &#40;XML for Analysis&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span><span class="sxs-lookup"><span data-stu-id="8678d-116">For more information, see [XML for Analysis  &#40;XMLA&#41; Reference](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span></span>  
  
 <span data-ttu-id="8678d-117">Se o código DDL for armazenado em um arquivo separado, a tarefa Executar DDL do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usará um gerenciador de conexões de arquivo para especificar o caminho do arquivo.</span><span class="sxs-lookup"><span data-stu-id="8678d-117">If the DDL code is stored in a separate file, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task uses a File connection manager to specify the path of the file.</span></span> <span data-ttu-id="8678d-118">Para obter mais informações, consulte [File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8678d-118">For more information, see [File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="8678d-119">Como as instruções DDL podem conter senhas e outras informações confidenciais, um pacote que contém uma ou mais tarefas Executar DDL do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deve usar o nível de proteção de pacote `EncryptAllWithUserKey` ou `EncryptAllWithPassword`.</span><span class="sxs-lookup"><span data-stu-id="8678d-119">Because DDL statements can contain passwords and other sensitive information, a package that contains one or more [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL tasks should use the package protection level `EncryptAllWithUserKey` or `EncryptAllWithPassword`.</span></span> <span data-ttu-id="8678d-120">Para obter mais informações, consulte [Integration Services &#40;SSIS&#41; Pacotes](../integration-services-ssis-packages.md).</span><span class="sxs-lookup"><span data-stu-id="8678d-120">For more information, see [Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md).</span></span>  
  
### <a name="ddl-examples"></a><span data-ttu-id="8678d-121">Exemplos de DDL</span><span class="sxs-lookup"><span data-stu-id="8678d-121">DDL Examples</span></span>  
 <span data-ttu-id="8678d-122">As três instruções de DDL a seguir foram geradas por script de objetos no [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], o banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incluído no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8678d-122">The following three DDL statements were generated by scripting objects in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8678d-123">A instrução DDL a seguir exclui a dimensão **Promoção** .</span><span class="sxs-lookup"><span data-stu-id="8678d-123">The following DDL statement deletes the **Promotion** dimension.</span></span>  
  
```  
<Delete xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 <span data-ttu-id="8678d-124">A instrução de DDL a seguir processa o cubo do [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8678d-124">The following DDL statement processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] cube.</span></span>  
  
```  
<Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 <span data-ttu-id="8678d-125">A instrução DDL a seguir cria o modelo de mineração **Previsão** .</span><span class="sxs-lookup"><span data-stu-id="8678d-125">The following DDL statement creates the **Forecasting** mining model.</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
 <span data-ttu-id="8678d-126">As três instruções de DDL a seguir foram geradas por script de objetos no [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], o banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incluído no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8678d-126">The following three DDL statements were generated by scripting objects in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8678d-127">A instrução DDL a seguir exclui a dimensão **Promoção** .</span><span class="sxs-lookup"><span data-stu-id="8678d-127">The following DDL statement deletes the **Promotion** dimension.</span></span>  
  
```  
<Delete xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 <span data-ttu-id="8678d-128">A instrução de DDL a seguir processa o cubo do [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8678d-128">The following DDL statement processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] cube.</span></span>  
  
```  
<Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 <span data-ttu-id="8678d-129">A instrução DDL a seguir cria o modelo de mineração **Previsão** .</span><span class="sxs-lookup"><span data-stu-id="8678d-129">The following DDL statement creates the **Forecasting** mining model.</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
## <a name="configuration-of-the-analysis-services-execute-ddl-task"></a><span data-ttu-id="8678d-130">Configuração da Tarefa Executar DDL do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8678d-130">Configuration of the Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="8678d-131">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="8678d-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="8678d-132">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="8678d-132">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8678d-133">Editor da Tarefa Executar DDL do Analysis Services &#40;Página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="8678d-133">Analysis Services Execute DDL Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="8678d-134">Editor da Tarefa Executar DDL do Analysis Services &#40;Página DDL&#41;</span><span class="sxs-lookup"><span data-stu-id="8678d-134">Analysis Services Execute DDL Task Editor &#40;DDL Page&#41;</span></span>](../analysis-services-execute-ddl-task-editor-ddl-page.md)  
  
-   [<span data-ttu-id="8678d-135">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="8678d-135">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="8678d-136">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="8678d-136">For more information about setting these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="8678d-137">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="8678d-137">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-analysis-services-execute-ddl-task"></a><span data-ttu-id="8678d-138">Configuração programática da Tarefa Executar DDL do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8678d-138">Programmatic Configuration of the Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="8678d-139">Para obter mais informações sobre como definir essas propriedades programaticamente, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="8678d-139">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.DataTransformationServices.Tasks.DTSProcessingTask.ASExecuteDDLTask>  
  
  
