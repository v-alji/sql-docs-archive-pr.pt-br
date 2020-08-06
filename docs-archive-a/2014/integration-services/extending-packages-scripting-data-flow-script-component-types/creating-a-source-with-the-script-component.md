---
title: Criando uma fonte com o componente Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], source components
- output columns [Integration Services]
- sources [Integration Services], components
ms.assetid: 547c4179-ea82-4265-8c6f-04a2aa77a3c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a352348f7f47157c5f2ec6d3ff01cea47de0ffb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574780"
---
# <a name="creating-a-source-with-the-script-component"></a><span data-ttu-id="051c5-102">Criando uma fonte com o componente Script</span><span class="sxs-lookup"><span data-stu-id="051c5-102">Creating a Source with the Script Component</span></span>
  <span data-ttu-id="051c5-103">Você usa um componente de origem no fluxo de dados de um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para carregar dados de uma fonte de dados a serem passados para transformações e destinos downstream.</span><span class="sxs-lookup"><span data-stu-id="051c5-103">You use a source component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to load data from a data source to pass on to downstream transformations and destinations.</span></span> <span data-ttu-id="051c5-104">Normalmente, você se conecta à fonte de dados por um gerenciador de conexões existente.</span><span class="sxs-lookup"><span data-stu-id="051c5-104">Ordinarily you connect to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="051c5-105">Para obter uma visão geral do componente Script, consulte [estendendo o fluxo de dados com o componente Script] (.. /extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="051c5-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="051c5-106">O componente Script e o código de infraestrutura gerado para você simplificam significativamente o processo de desenvolvimento de um componente de fluxo de dados personalizado.</span><span class="sxs-lookup"><span data-stu-id="051c5-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="051c5-107">Contudo, para compreender o funcionamento do componente Script, talvez seja útil ler as etapas envolvidas no desenvolvimento de um componente de fluxo de dados personalizado.</span><span class="sxs-lookup"><span data-stu-id="051c5-107">However, to understand how the Script component works, you may find it useful to read through the steps that are involved in developing a custom data flow component.</span></span> <span data-ttu-id="051c5-108">Consulte a seção [Desenvolvendo um componente de fluxo de dados personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md), especialmente o tópico [Desenvolvendo um componente de origem personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-108">See the section [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md), especially the topic [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="getting-started-with-a-source-component"></a><span data-ttu-id="051c5-109">Guia de introdução com um componente de origem</span><span class="sxs-lookup"><span data-stu-id="051c5-109">Getting Started with a Source Component</span></span>
 <span data-ttu-id="051c5-110">Quando você adiciona um componente Script ao painel Fluxo de Dados do Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)], a caixa de diálogo **Selecionar Tipo de Componente Script** é aberta e solicita a seleção de um script de Origem, Destino ou Transformação.</span><span class="sxs-lookup"><span data-stu-id="051c5-110">When you add a Script component to the Data Flow pane of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a Source, Destination, or Transformation script.</span></span> <span data-ttu-id="051c5-111">Nessa caixa de diálogo, selecione **Origem**.</span><span class="sxs-lookup"><span data-stu-id="051c5-111">In this dialog box, select **Source**.</span></span>

## <a name="configuring-a-source-component-in-metadata-design-mode"></a><span data-ttu-id="051c5-112">Configurando um componente de origem em modo do design de metadados</span><span class="sxs-lookup"><span data-stu-id="051c5-112">Configuring a Source Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="051c5-113">Depois de selecionar que deseja criar um componente de origem, configure o componente usando o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="051c5-113">After selecting to create a source component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="051c5-114">Para obter mais informações, consulte [Configurando o componente Script no Editor de Componente Script](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-114">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="051c5-115">Um componente de origem de fluxo de dados não tem entradas e dá suporte a uma ou mais saídas.</span><span class="sxs-lookup"><span data-stu-id="051c5-115">A data flow source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="051c5-116">A configuração das saídas do componente é uma das etapas que devem ser concluídas no modo de design de metadados, usando o **Editor de Transformação Scripts**, antes de escrever o script personalizado.</span><span class="sxs-lookup"><span data-stu-id="051c5-116">Configuring the outputs for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

 <span data-ttu-id="051c5-117">Você também pode especificar a linguagem de script configurando a propriedade **ScriptLanguage** na página **Script** do **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="051c5-117">You can also specify the script language by setting the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor**.</span></span>

> [!NOTE]
>  <span data-ttu-id="051c5-118">Para definir a linguagem de scripts padrão para componentes de Script e Tarefas de Script, use a opção **Linguagem de scripts** na página **Geral** da caixa de diálogo **Opções**.</span><span class="sxs-lookup"><span data-stu-id="051c5-118">To set the default script language for Script components and Script Tasks, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="051c5-119">Para obter mais informações, consulte [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-119">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="051c5-120">Adicionando gerenciadores de conexões</span><span class="sxs-lookup"><span data-stu-id="051c5-120">Adding Connection Managers</span></span>
 <span data-ttu-id="051c5-121">Em geral, um componente de origem usa um gerenciador de conexões existente para se conectar à fonte de dados da qual ele carrega dados para o fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="051c5-121">Ordinarily a source component uses an existing connection manager to connect to the data source from which it loads data into the data flow.</span></span> <span data-ttu-id="051c5-122">Na página **Gerenciadores de Conexões** do **Editor de Transformação Scripts**, clique em **Adicionar** para adicionar o gerenciador de conexões apropriado.</span><span class="sxs-lookup"><span data-stu-id="051c5-122">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="051c5-123">Contudo, um gerenciador de conexões é apenas uma unidade conveniente que encapsula e armazena as informações necessárias para a conexão a uma fonte de dados de um tipo específico.</span><span class="sxs-lookup"><span data-stu-id="051c5-123">However, a connection manager is only a convenient unit that encapsulates and stores the information that it must have to connect to a data source of a particular type.</span></span> <span data-ttu-id="051c5-124">Escreva seu próprio código personalizado para carregar ou salvar seus dados e, possivelmente, para também abrir e fechar a conexão à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="051c5-124">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source also.</span></span>

 <span data-ttu-id="051c5-125">Para obter informações gerais sobre como usar gerenciadores de conexões com o componente Script, consulte [Conectando-se a fontes de dados no componente Script](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-125">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="051c5-126">Para obter mais informações sobre a página **Gerenciadores de Conexões** do **Editor de Transformação Scripts**, consulte [Editor de Transformação Scripts &#40;Página Gerenciadores de Conexões&#41;](../script-transformation-editor-connection-managers-page.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-126">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-outputs-and-output-columns"></a><span data-ttu-id="051c5-127">Configurando saídas e colunas de saída</span><span class="sxs-lookup"><span data-stu-id="051c5-127">Configuring Outputs and Output Columns</span></span>
 <span data-ttu-id="051c5-128">Um componente de origem não tem nenhuma entrada e dá suporte a uma ou mais saídas.</span><span class="sxs-lookup"><span data-stu-id="051c5-128">A source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="051c5-129">Na página **Entradas e Saídas** do **Editor de Transformação Scripts**, uma única saída foi criada por padrão, mas nenhuma coluna de saída foi criada.</span><span class="sxs-lookup"><span data-stu-id="051c5-129">On the **Inputs and Outputs** page of the **Script Transformation Editor**, a single output has been created by default, but no output columns have been created.</span></span> <span data-ttu-id="051c5-130">Nessa página do editor, você pode precisar ou querer configurar os itens a seguir.</span><span class="sxs-lookup"><span data-stu-id="051c5-130">On this page of the editor, you may need or want to configure the following items.</span></span>

-   <span data-ttu-id="051c5-131">Adicione e configure colunas de saída manualmente para cada saída.</span><span class="sxs-lookup"><span data-stu-id="051c5-131">You must add and configure output columns manually for each output.</span></span> <span data-ttu-id="051c5-132">Selecione a pasta Colunas de Saída para cada saída e, em seguida, use os botões **Adicionar Coluna** e **Remover Coluna** para gerenciar as colunas de saída para cada saída do componente de origem.</span><span class="sxs-lookup"><span data-stu-id="051c5-132">Select the Output Columns folder for each output, and then use the **Add Column** and **Remove Column** buttons to manage the output columns for each output of the source component.</span></span> <span data-ttu-id="051c5-133">Posteriormente, você fará referência às colunas de saída do seu script pelos nomes atribuídos aqui, usando as propriedades de acessador digitadas criadas para você no código gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="051c5-133">Later, you will refer to the output columns in your script by the names that you assign here, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="051c5-134">Talvez você queira criar uma ou mais saídas adicionais, tais como uma saída de erro simulada para linhas que contêm valores inesperados.</span><span class="sxs-lookup"><span data-stu-id="051c5-134">You may want to create one or more additional outputs, such as a simulated error output for rows that contain unexpected values.</span></span> <span data-ttu-id="051c5-135">Use os botões **Adicionar Saída** e **Remover Saída** para gerenciar as saídas do componente de origem.</span><span class="sxs-lookup"><span data-stu-id="051c5-135">Use the **Add Output** and **Remove Output** buttons to manage the outputs of the source component.</span></span> <span data-ttu-id="051c5-136">Todas as linhas de entrada são direcionadas a todas as saídas disponíveis, a menos que você também especifique um valor idêntico diferente de zero para a propriedade `ExclusionGroup` das saídas onde você pretende direcionar cada linha a apenas uma das saídas que compartilham o mesmo valor `ExclusionGroup`.</span><span class="sxs-lookup"><span data-stu-id="051c5-136">All input rows are directed to all available outputs unless you also specify an identical non-zero value for the `ExclusionGroup` property of those outputs where you intend to direct each row to only one of the outputs that share the same `ExclusionGroup` value.</span></span> <span data-ttu-id="051c5-137">O valor de inteiro específico selecionado para identificar o `ExclusionGroup` não é significante.</span><span class="sxs-lookup"><span data-stu-id="051c5-137">The particular integer value selected to identify the `ExclusionGroup` is not significant.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="051c5-138">Você também poderá usar um valor de propriedade `ExclusionGroup` diferente de zero com uma única saída quando não quiser gerar todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="051c5-138">You can also use a non-zero `ExclusionGroup` property value with a single output when you do not want to output all rows.</span></span> <span data-ttu-id="051c5-139">Nesse caso, entretanto, você precisa chamar explicitamente o método **DirectRowTo\<outputbuffer>** para cada linha que deseja enviar à saída.</span><span class="sxs-lookup"><span data-stu-id="051c5-139">In this case, however, you must explicitly call the **DirectRowTo\<outputbuffer>** method for each row that you want to send to the output.</span></span>

-   <span data-ttu-id="051c5-140">Talvez você queira atribuir um nome amigável às saídas.</span><span class="sxs-lookup"><span data-stu-id="051c5-140">You may want to assign a friendly name to the outputs.</span></span> <span data-ttu-id="051c5-141">Posteriormente, você fará referência às saídas pelos nomes no seu script, usando as propriedades de acessador digitadas, criadas para você no código gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="051c5-141">Later, you will refer to the outputs by their names in your script, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="051c5-142">Em geral, várias saídas no mesmo `ExclusionGroup` têm as mesmas colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="051c5-142">Ordinarily multiple outputs in the same `ExclusionGroup` have the same output columns.</span></span> <span data-ttu-id="051c5-143">Porém, se você estiver criando uma saída de erro simulada, talvez queira adicionar mais colunas para armazenar informações de erro.</span><span class="sxs-lookup"><span data-stu-id="051c5-143">However, if you are creating a simulated error output, you may want to add more columns to store error information.</span></span> <span data-ttu-id="051c5-144">Para obter informações sobre como o mecanismo de fluxo de dados processa linhas de erro, consulte [Usando saídas de erro em um componente de fluxo de dados](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-144">For information about how the data flow engine processes error rows, see [Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md).</span></span> <span data-ttu-id="051c5-145">No componente Script, contudo, escreva seu próprio código para preencher as colunas adicionais com informações de erro apropriadas.</span><span class="sxs-lookup"><span data-stu-id="051c5-145">In the Script component, however, you must write your own code to fill the additional columns with appropriate error information.</span></span> <span data-ttu-id="051c5-146">Para obter mais informações, consulte [Simulando uma saída de erro para o componente Script](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-146">For more information, see [Simulating an Error Output for the Script Component](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md).</span></span>

 <span data-ttu-id="051c5-147">Para obter mais informações sobre a página **Entradas e Saídas** do **Editor de Transformação Scripts**, consulte [Editor de Transformação Scripts &#40;página Entradas e Saídas&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-147">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="051c5-148">Adicionando variáveis</span><span class="sxs-lookup"><span data-stu-id="051c5-148">Adding Variables</span></span>
 <span data-ttu-id="051c5-149">Se houver qualquer variável existente cujos valores você deseja usar em seu script, você poderá adicioná-las nos campos de `ReadOnlyVariables` `ReadWriteVariables` propriedade e na página **script** do **Editor de transformação scripts**.</span><span class="sxs-lookup"><span data-stu-id="051c5-149">If there are any existing variables whose values you want to use in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="051c5-150">Ao inserir diversas variáveis nos campos de propriedade, separe os nomes delas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="051c5-150">When you enter multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="051c5-151">Você também pode inserir várias variáveis clicando no botão de reticências (**...**) ao lado `ReadOnlyVariables` dos `ReadWriteVariables` campos de propriedade e e selecionando variáveis na caixa de diálogo **Selecionar variáveis** .</span><span class="sxs-lookup"><span data-stu-id="051c5-151">You can also enter multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields and selecting variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="051c5-152">Para obter informações gerais sobre como usar variáveis com o componente Script, consulte [Usando variáveis no componente Script](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-152">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="051c5-153">Para obter mais informações sobre a página **Script** do **Editor de Transformação Scripts**, consulte [Editor de Transformação Scripts &#40;Página Script&#41;](../script-transformation-editor-script-page.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-153">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-source-component-in-code-design-mode"></a><span data-ttu-id="051c5-154">Gerando scripts de um componente de origem em modo do design de código</span><span class="sxs-lookup"><span data-stu-id="051c5-154">Scripting a Source Component in Code-Design Mode</span></span>
 <span data-ttu-id="051c5-155">Depois de configurar os metadados para o componente, abra o IDE do VSTA ([!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications) para codificar o script personalizado.</span><span class="sxs-lookup"><span data-stu-id="051c5-155">After you have configured the metadata for your component, open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE to code your custom script.</span></span> <span data-ttu-id="051c5-156">Para abrir o VSTA, clique em **Editar Script** na página **Script** do **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="051c5-156">To open VSTA, click **Edit Script** on the **Script** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="051c5-157">Escreva seu script usando o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic ou o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#, dependendo da linguagem de script selecionada para a propriedade **ScriptLanguage**.</span><span class="sxs-lookup"><span data-stu-id="051c5-157">You can write your script by using either [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#, depending on the script language selected for the **ScriptLanguage** property.</span></span>

 <span data-ttu-id="051c5-158">Para obter informações importantes que se aplicam a todos os tipos de componentes criados por meio do componente Script, consulte [Codificando e depurando o componente Script](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-158">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="051c5-159">Compreendendo o código gerado automaticamente</span><span class="sxs-lookup"><span data-stu-id="051c5-159">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="051c5-160">Quando você abrir o VSTA IDE depois de criar e configurar um componente de origem, a classe editável `ScriptMain` aparecerá no editor de códigos.</span><span class="sxs-lookup"><span data-stu-id="051c5-160">When you open the VSTA IDE after creating and configuring a source component, the editable `ScriptMain` class appears in the code editor.</span></span> <span data-ttu-id="051c5-161">Você escreve seu código personalizado na classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="051c5-161">You write your custom code in the `ScriptMain` class.</span></span>

 <span data-ttu-id="051c5-162">A classe `ScriptMain` inclui um stub para o método `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="051c5-162">The `ScriptMain` class includes a stub for the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="051c5-163">O `CreateNewOutputRows` é o método mais importante em um componente de origem.</span><span class="sxs-lookup"><span data-stu-id="051c5-163">The `CreateNewOutputRows` is the most important method in a source component.</span></span>

 <span data-ttu-id="051c5-164">Se você abrir a janela **Explorador de projeto** no VSTA, poderá ver que o componente script também gerou itens de `BufferWrapper` projeto e somente leitura `ComponentWrapper` .</span><span class="sxs-lookup"><span data-stu-id="051c5-164">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="051c5-165">A classe `ScriptMain` herda da classe `UserComponent` no item de projeto `ComponentWrapper`.</span><span class="sxs-lookup"><span data-stu-id="051c5-165">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="051c5-166">Em tempo de execução, o mecanismo de fluxo de dados invoca o método `PrimeOutput` na classe `UserComponent`, que substitui o método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A> da classe pai <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="051c5-166">At run time, the data flow engine invokes the `PrimeOutput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="051c5-167">O método `PrimeOutput`, por sua vez, chama os seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="051c5-167">The `PrimeOutput` method in turn calls the following methods:</span></span>

1.  <span data-ttu-id="051c5-168">O método `CreateNewOutputRows`, que você substitui em `ScriptMain` para adicionar linhas da fonte de dados aos buffers de saída, que estão vazios no início.</span><span class="sxs-lookup"><span data-stu-id="051c5-168">The `CreateNewOutputRows` method, which you override in `ScriptMain` to add rows from the data source to the output buffers, which are empty at first.</span></span>

2.  <span data-ttu-id="051c5-169">O método `FinishOutputs` que está vazio por padrão.</span><span class="sxs-lookup"><span data-stu-id="051c5-169">The `FinishOutputs` method, which is empty by default.</span></span> <span data-ttu-id="051c5-170">Substitua esse método em `ScriptMain` para executar qualquer processamento requerido para concluir a saída.</span><span class="sxs-lookup"><span data-stu-id="051c5-170">Override this method in `ScriptMain` to perform any processing that is required to complete the output.</span></span>

3.  <span data-ttu-id="051c5-171">O método `MarkOutputsAsFinished` particular, que chama o método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A> da classe pai <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> para indicar ao mecanismo de fluxo de dados que a saída está concluída.</span><span class="sxs-lookup"><span data-stu-id="051c5-171">The private `MarkOutputsAsFinished` method, which calls the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> parent class to indicate to the data flow engine that the output is finished.</span></span> <span data-ttu-id="051c5-172">Você não precisa chamar o `SetEndOfRowset` explicitamente em seu próprio código.</span><span class="sxs-lookup"><span data-stu-id="051c5-172">You do not have to call `SetEndOfRowset` explicitly in your own code.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="051c5-173">Escrevendo seu código personalizado</span><span class="sxs-lookup"><span data-stu-id="051c5-173">Writing Your Custom Code</span></span>
 <span data-ttu-id="051c5-174">Para terminar de criar um componente de origem personalizado, você pode escrever um script nos métodos a seguir disponíveis na classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="051c5-174">To finish creating a custom source component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="051c5-175">Substitua o método `AcquireConnections` para se conectar à fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="051c5-175">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="051c5-176">Extraia o objeto de conexão, ou as informações de conexão requeridas, do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="051c5-176">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="051c5-177">Substitua o método `PreExecute` para carregar dados, caso possa carregar todos os dados de origem ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="051c5-177">Override the `PreExecute` method to load data, if you can load all the source data at the same time.</span></span> <span data-ttu-id="051c5-178">Por exemplo, você pode executar um `SqlCommand` em relação à conexão [!INCLUDE[vstecado](../../includes/vstecado-md.md)] para um banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e carregar todos os dados de origem ao mesmo tempo em um `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="051c5-178">For example, you can execute a `SqlCommand` against an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and load all the source data at the same time into a `SqlDataReader`.</span></span> <span data-ttu-id="051c5-179">Se você precisar carregar os dados de origem em uma linha de cada vez (por exemplo, ao ler um arquivo de texto), poderá carregar os dados ao executar um loop nas linhas de `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="051c5-179">If you must load the source data one row at a time (for example, when reading a text file), you can load the data as you loop through rows in `CreateNewOutputRows`.</span></span>

3.  <span data-ttu-id="051c5-180">Use o método `CreateNewOutputRows` substituído para adicionar novas linhas nos buffers de saída vazios e preencher os valores de cada coluna nas novas linhas de saída.</span><span class="sxs-lookup"><span data-stu-id="051c5-180">Use the overridden `CreateNewOutputRows` method to add new rows to the empty output buffers and to fill in the values of each column in the new output rows.</span></span> <span data-ttu-id="051c5-181">Use o método `AddRow` de cada buffer de saída para adicionar uma linha nova vazia e, depois, defina os valores de cada coluna.</span><span class="sxs-lookup"><span data-stu-id="051c5-181">Use the `AddRow` method of each output buffer to add an empty new row, and then set the values of each column.</span></span> <span data-ttu-id="051c5-182">Em geral, você copia valores das colunas carregadas a partir da origem externa.</span><span class="sxs-lookup"><span data-stu-id="051c5-182">Typically you copy values from the columns loaded from the external source.</span></span>

4.  <span data-ttu-id="051c5-183">Substitua o método `PostExecute` para concluir o processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="051c5-183">Override the `PostExecute` method to finish processing the data.</span></span> <span data-ttu-id="051c5-184">Por exemplo, você pode fechar o `SqlDataReader` usado para carregar dados.</span><span class="sxs-lookup"><span data-stu-id="051c5-184">For example, you can close the `SqlDataReader` that you used to load data.</span></span>

5.  <span data-ttu-id="051c5-185">Substitua o método `ReleaseConnections` para desconectar-se da fonte de dados externa, caso necessário.</span><span class="sxs-lookup"><span data-stu-id="051c5-185">Override the `ReleaseConnections` method to disconnect from the external data source, if required.</span></span>

## <a name="examples"></a><span data-ttu-id="051c5-186">Exemplos</span><span class="sxs-lookup"><span data-stu-id="051c5-186">Examples</span></span>
 <span data-ttu-id="051c5-187">Os exemplos a seguir demonstram o código personalizado que é requerido na classe `ScriptMain` para criar um componente de origem.</span><span class="sxs-lookup"><span data-stu-id="051c5-187">The following examples demonstrate the custom code that is required in the `ScriptMain` class to create a source component.</span></span>

> [!NOTE]
>  <span data-ttu-id="051c5-188">Esses exemplos usam a tabela **Person. Address** no `AdventureWorks` banco de dados de exemplo e passam sua primeira e quarta colunas, as colunas City **intAddressID** e **nvarchar (30)** , por meio do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="051c5-188">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **intAddressID** and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="051c5-189">Os mesmos dados são usados nos exemplos de origem, transformação e destino nessa seção.</span><span class="sxs-lookup"><span data-stu-id="051c5-189">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="051c5-190">Pré-requisitos e suposições adicionais são documentados para cada exemplo.</span><span class="sxs-lookup"><span data-stu-id="051c5-190">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-source-example"></a><span data-ttu-id="051c5-191">Exemplo de origem do ADO.NET</span><span class="sxs-lookup"><span data-stu-id="051c5-191">ADO.NET Source Example</span></span>
 <span data-ttu-id="051c5-192">Esse exemplo demonstra um componente de origem que usa um gerenciador de conexões do [!INCLUDE[vstecado](../../includes/vstecado-md.md)] existente para carregar dados de uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="051c5-192">This example demonstrates a source component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to load data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into the data flow.</span></span>

 <span data-ttu-id="051c5-193">Se você quiser executar esse código de exemplo, configure o pacote e o componente desta forma:</span><span class="sxs-lookup"><span data-stu-id="051c5-193">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="051c5-194">Crie um [!INCLUDE[vstecado](../../includes/vstecado-md.md)] Gerenciador de conexões que use o `SqlClient` provedor para se conectar ao `AdventureWorks` banco de dados.</span><span class="sxs-lookup"><span data-stu-id="051c5-194">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="051c5-195">Adicione um novo componente Script à superfície do designer Fluxo de Dados e configure-o como uma origem.</span><span class="sxs-lookup"><span data-stu-id="051c5-195">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

3.  <span data-ttu-id="051c5-196">Abra o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="051c5-196">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="051c5-197">Na página **Entradas e Saídas**, renomeie a saída padrão com um nome mais descritivo, como **MyAddressOutput** e adicione e configure as duas colunas de saída, **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="051c5-197">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**, and add and configure the two output columns, **AddressID** and **City**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="051c5-198">Altere o tipo de dados da coluna de saída **City** para DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="051c5-198">Be sure to change the data type of the **City** output column to DT_WSTR.</span></span>

4.  <span data-ttu-id="051c5-199">Na página **Gerenciadores de Conexões**, adicione ou crie o gerenciador de conexões do [!INCLUDE[vstecado](../../includes/vstecado-md.md)] e dê a ele um nome como **MyADONETConnection**.</span><span class="sxs-lookup"><span data-stu-id="051c5-199">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager and give it a name such as **MyADONETConnection**.</span></span>

5.  <span data-ttu-id="051c5-200">Na página **Script**, clique em **Editar Script** e insira o script a seguir.</span><span class="sxs-lookup"><span data-stu-id="051c5-200">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="051c5-201">Em seguida, feche o ambiente de desenvolvimento de script e o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="051c5-201">Then close the script development environment and the **Script Transformation Editor**.</span></span>

6.  <span data-ttu-id="051c5-202">Crie e configure um componente de destino, como um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou o componente de destino de exemplo demonstrado em [Criando um destino com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md), que espera as colunas **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="051c5-202">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md), that expects the **AddressID** and **City** columns.</span></span> <span data-ttu-id="051c5-203">Depois, conecte o componente de origem ao destino.</span><span class="sxs-lookup"><span data-stu-id="051c5-203">Then connect the source component to the destination.</span></span> <span data-ttu-id="051c5-204">(Você pode conectar uma fonte diretamente a um destino sem nenhuma transformação.) Você pode criar uma tabela de destino executando o seguinte [!INCLUDE[tsql](../../includes/tsql-md.md)] comando no `AdventureWorks` banco de dados:</span><span class="sxs-lookup"><span data-stu-id="051c5-204">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

7.  <span data-ttu-id="051c5-205">Execute o exemplo.</span><span class="sxs-lookup"><span data-stu-id="051c5-205">Run the sample.</span></span>

    ```vb
    Imports System.Data.SqlClient
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Dim connMgr As IDTSConnectionManager100
        Dim sqlConn As SqlConnection
        Dim sqlReader As SqlDataReader

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            connMgr = Me.Connections.MyADONETConnection
            sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

        End Sub

        Public Overrides Sub PreExecute()

            Dim cmd As New SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn)
            sqlReader = cmd.ExecuteReader

        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Do While sqlReader.Read
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = sqlReader.GetInt32(0)
                    .City = sqlReader.GetString(1)
                End With
            Loop

        End Sub

        Public Overrides Sub PostExecute()

            sqlReader.Close()

        End Sub

        Public Overrides Sub ReleaseConnections()

            connMgr.ReleaseConnection(sqlConn)

        End Sub

    End Class
    ```

    ```csharp
    using System.Data.SqlClient;
    public class ScriptMain:
        UserComponent

    {
        IDTSConnectionManager100 connMgr;
        SqlConnection sqlConn;
        SqlDataReader sqlReader;

        public override void AcquireConnections(object Transaction)
        {
            connMgr = this.Connections.MyADONETConnection;
            sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {

            SqlCommand cmd = new SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn);
            sqlReader = cmd.ExecuteReader();

        }

        public override void CreateNewOutputRows()
        {

            while (sqlReader.Read())
            {
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = sqlReader.GetInt32(0);
                    MyAddressOutputBuffer.City = sqlReader.GetString(1);
                }
            }

        }

        public override void PostExecute()
        {

            sqlReader.Close();

        }

        public override void ReleaseConnections()
        {

            connMgr.ReleaseConnection(sqlConn);

        }

    }
    ```

### <a name="flat-file-source-example"></a><span data-ttu-id="051c5-206">Exemplo de fonte de arquivos simples</span><span class="sxs-lookup"><span data-stu-id="051c5-206">Flat File Source Example</span></span>
 <span data-ttu-id="051c5-207">Esse exemplo demonstra um componente de origem que usa um gerenciador de conexões de arquivos simples existente para carregar dados de um arquivo simples no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="051c5-207">This example demonstrates a source component that uses an existing Flat File connection manager to load data from a flat file into the data flow.</span></span> <span data-ttu-id="051c5-208">Os dados de fonte de arquivo simples são criados através de sua exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="051c5-208">The flat file source data is created by exporting it from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

 <span data-ttu-id="051c5-209">Se você quiser executar esse código de exemplo, configure o pacote e o componente desta forma:</span><span class="sxs-lookup"><span data-stu-id="051c5-209">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="051c5-210">Use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Assistente de importação e exportação do para exportar a tabela **Person. Address** do `AdventureWorks` banco de dados de exemplo para um arquivo simples delimitado por vírgula.</span><span class="sxs-lookup"><span data-stu-id="051c5-210">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard to export the **Person.Address** table from the `AdventureWorks` sample database to a comma-delimited flat file.</span></span> <span data-ttu-id="051c5-211">Esse exemplo usa o nome de arquivo ExportedAddresses.txt.</span><span class="sxs-lookup"><span data-stu-id="051c5-211">This sample uses the file name ExportedAddresses.txt.</span></span>

2.  <span data-ttu-id="051c5-212">Crie um gerenciador de conexões de arquivos simples que se conecta ao arquivo de dados exportado.</span><span class="sxs-lookup"><span data-stu-id="051c5-212">Create a Flat File connection manager that connects to the exported data file.</span></span>

3.  <span data-ttu-id="051c5-213">Adicione um novo componente Script à superfície do designer Fluxo de Dados e configure-o como uma origem.</span><span class="sxs-lookup"><span data-stu-id="051c5-213">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

4.  <span data-ttu-id="051c5-214">Abra o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="051c5-214">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="051c5-215">Na página **Entradas e Saídas**, renomeie a saída padrão com um nome mais descritivo, como **MyAddressOutput**.</span><span class="sxs-lookup"><span data-stu-id="051c5-215">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**.</span></span> <span data-ttu-id="051c5-216">Adicione e configure as duas colunas de saída, **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="051c5-216">Add and configure the two output columns, **AddressID** and **City**.</span></span>

5.  <span data-ttu-id="051c5-217">Na página **Gerenciadores de Conexões**, adicione ou crie o gerenciador de conexões de Arquivos Simples usando um nome descritivo como **MyFlatFileSrcConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="051c5-217">On the **Connection Managers** page, add or create the Flat File connection manager, using a descriptive name such as **MyFlatFileSrcConnectionManager**.</span></span>

6.  <span data-ttu-id="051c5-218">Na página **Script**, clique em **Editar Script** e insira o script a seguir.</span><span class="sxs-lookup"><span data-stu-id="051c5-218">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="051c5-219">Em seguida, feche o ambiente de desenvolvimento de script e o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="051c5-219">Then close the script development environment and the **Script Transformation Editor**.</span></span>

7.  <span data-ttu-id="051c5-220">Crie e configure um componente de destino, como um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou o componente de destino de exemplo demonstrado em [Criando um destino com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="051c5-220">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="051c5-221">Depois, conecte o componente de origem ao destino.</span><span class="sxs-lookup"><span data-stu-id="051c5-221">Then connect the source component to the destination.</span></span> <span data-ttu-id="051c5-222">(Você pode conectar uma fonte diretamente a um destino sem nenhuma transformação.) Você pode criar uma tabela de destino executando o seguinte [!INCLUDE[tsql](../../includes/tsql-md.md)] comando no `AdventureWorks` banco de dados:</span><span class="sxs-lookup"><span data-stu-id="051c5-222">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

8.  <span data-ttu-id="051c5-223">Execute o exemplo.</span><span class="sxs-lookup"><span data-stu-id="051c5-223">Run the sample.</span></span>

    ```vb
    Imports System.IO
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Private textReader As StreamReader
        Private exportedAddressFile As String

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            Dim connMgr As IDTSConnectionManager100 = _
                Me.Connections.MyFlatFileSrcConnectionManager
            exportedAddressFile = _
                CType(connMgr.AcquireConnection(Nothing), String)

        End Sub

        Public Overrides Sub PreExecute()
            MyBase.PreExecute()
            textReader = New StreamReader(exportedAddressFile)
        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Dim nextLine As String
            Dim columns As String()

            Dim delimiters As Char()
            delimiters = ",".ToCharArray

            nextLine = textReader.ReadLine
            Do While nextLine IsNot Nothing
                columns = nextLine.Split(delimiters)
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = columns(0)
                    .City = columns(3)
                End With
                nextLine = textReader.ReadLine
            Loop

        End Sub

        Public Overrides Sub PostExecute()
            MyBase.PostExecute()
            textReader.Close()

        End Sub

    End Class
    ```

    ```csharp
    using System.IO;
    public class ScriptMain:
        UserComponent

    {
        private StreamReader textReader;
        private string exportedAddressFile;

        public override void AcquireConnections(object Transaction)
        {

            IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileSrcConnectionManager;
            exportedAddressFile = (string)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {
            base.PreExecute();
            textReader = new StreamReader(exportedAddressFile);
        }

        public override void CreateNewOutputRows()
        {

            string nextLine;
            string[] columns;

            char[] delimiters;
            delimiters = ",".ToCharArray();

            nextLine = textReader.ReadLine();
            while (nextLine != null)
            {
                columns = nextLine.Split(delimiters);
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = columns[0];
                    MyAddressOutputBuffer.City = columns[3];
                }
                nextLine = textReader.ReadLine();
            }

        }

        public override void PostExecute()
        {

            base.PostExecute();
            textReader.Close();

        }

    }
    ```

<span data-ttu-id="051c5-224">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="051c5-224">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="051c5-225">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="051c5-225">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="051c5-226">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="051c5-226">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="051c5-227">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="051c5-227">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="051c5-228">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="051c5-228">See Also</span></span>
 <span data-ttu-id="051c5-229">[Criando um destino com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [desenvolvendo um componente de origem personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span><span class="sxs-lookup"><span data-stu-id="051c5-229">[Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span></span>


