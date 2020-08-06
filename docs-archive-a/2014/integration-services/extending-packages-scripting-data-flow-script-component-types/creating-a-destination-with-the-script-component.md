---
title: Criando um destino com o componente Script | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], destination components
- destinations [Integration Services], components
- input columns [Integration Services]
ms.assetid: 214e22e8-7e7d-4876-b690-c138e5721b81
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1245dde111b24d1c37e2c5550d236c97126ee725
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575962"
---
# <a name="creating-a-destination-with-the-script-component"></a><span data-ttu-id="a8607-102">Criando um destino com o componente Script</span><span class="sxs-lookup"><span data-stu-id="a8607-102">Creating a Destination with the Script Component</span></span>
  <span data-ttu-id="a8607-103">Você usa um componente de destino no fluxo de dados de um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para salvar dados recebidos de fontes upstream e transformações em uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="a8607-103">You use a destination component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to save data received from upstream sources and transformations to a data source.</span></span> <span data-ttu-id="a8607-104">Em geral, o componente de destino se conecta à fonte de dados através de um gerenciador de conexões existente.</span><span class="sxs-lookup"><span data-stu-id="a8607-104">Ordinarily the destination component connects to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="a8607-105">Para obter uma visão geral do componente Script, consulte [estendendo o fluxo de dados com o componente Script] (.. /extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="a8607-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="a8607-106">O componente Script e o código de infraestrutura gerado para você simplificam significativamente o processo de desenvolvimento de um componente de fluxo de dados personalizado.</span><span class="sxs-lookup"><span data-stu-id="a8607-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="a8607-107">No entanto, para entender como funciona o componente Script, talvez seja útil ler as etapas de como desenvolver componentes de fluxo de dados personalizados na seção [Desenvolvendo um componente de fluxo de dados personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) e, especialmente, [Desenvolvendo um componente de destino personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md).</span><span class="sxs-lookup"><span data-stu-id="a8607-107">However, to understand how the Script component works, you may find it useful to read through the steps for developing a custom data flow components in the [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) section, and especially [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md).</span></span>

## <a name="getting-started-with-a-destination-component"></a><span data-ttu-id="a8607-108">Guia de Introdução com um componente Destino</span><span class="sxs-lookup"><span data-stu-id="a8607-108">Getting Started with a Destination Component</span></span>
 <span data-ttu-id="a8607-109">Quando você adiciona um componente Script à guia Fluxo de Dados do Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)], a caixa de diálogo **Selecionar Tipo de Componente Script** é aberta e solicita a seleção de um script **Origem**, **Destino** ou **Transformação**.</span><span class="sxs-lookup"><span data-stu-id="a8607-109">When you add a Script component to the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a **Source**, **Destination**, or **Transformation** script.</span></span> <span data-ttu-id="a8607-110">Nessa caixa de diálogo, selecione **Destino**.</span><span class="sxs-lookup"><span data-stu-id="a8607-110">In this dialog box, select **Destination**.</span></span>

 <span data-ttu-id="a8607-111">Depois, conecte a saída de uma transformação ao componente de destino no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8607-111">Next, connect the output of a transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="a8607-112">Como teste, você pode conectar uma origem diretamente a um destino, sem qualquer transformação.</span><span class="sxs-lookup"><span data-stu-id="a8607-112">For testing, you can connect a source directly to a destination without any transformations.</span></span>

## <a name="configuring-a-destination-component-in-metadata-design-mode"></a><span data-ttu-id="a8607-113">Configurando um componente Destino no modo do design de metadados</span><span class="sxs-lookup"><span data-stu-id="a8607-113">Configuring a Destination Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="a8607-114">Depois de selecionar a opção para criar um componente de destino, configure o componente usando o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="a8607-114">After you select the option to create a destination component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="a8607-115">Para obter mais informações, consulte [Configurando o componente Script no Editor de Componente Script](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a8607-115">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="a8607-116">Para selecionar a linguagem de script que será usada pelo destino Script, defina a propriedade **ScriptLanguage** na página **Script** da caixa de diálogo **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="a8607-116">To select the script language that the Script destination will use, you set the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor** dialog box.</span></span>

> [!NOTE]
>  <span data-ttu-id="a8607-117">Para definir a linguagem de scripts padrão para o componente Script, use a opção **Linguagem de scripts** na página **Geral** da caixa de diálogo **Opções**.</span><span class="sxs-lookup"><span data-stu-id="a8607-117">To set the default scripting language for the Script component, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="a8607-118">Para obter mais informações, consulte [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="a8607-118">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

 <span data-ttu-id="a8607-119">Um componente de destino de fluxo de dados tem uma entrada e nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="a8607-119">A data flow destination component has one input and no outputs.</span></span> <span data-ttu-id="a8607-120">A configuração da entrada do componente é uma das etapas que devem ser concluídas no modo de design de metadados, usando o **Editor de Transformação Scripts**, antes de escrever o script personalizado.</span><span class="sxs-lookup"><span data-stu-id="a8607-120">Configuring the input for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="a8607-121">Adicionando gerenciadores de conexões</span><span class="sxs-lookup"><span data-stu-id="a8607-121">Adding Connection Managers</span></span>
 <span data-ttu-id="a8607-122">Em geral, um componente de destino usa um gerenciador de conexões existente para se conectar à fonte de dados na qual ele salva dados do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="a8607-122">Ordinarily a destination component uses an existing connection manager to connect to the data source to which it saves data from the data flow.</span></span> <span data-ttu-id="a8607-123">Na página **Gerenciadores de Conexões** do **Editor de Transformação Scripts**, clique em **Adicionar** para adicionar o gerenciador de conexões apropriado.</span><span class="sxs-lookup"><span data-stu-id="a8607-123">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="a8607-124">Contudo, um gerenciador de conexões é apenas uma unidade conveniente que encapsula e armazena as informações necessárias para a conexão a uma fonte de dados de um tipo específico.</span><span class="sxs-lookup"><span data-stu-id="a8607-124">However, a connection manager is just a convenient unit that encapsulates and stores the information that is required to connect to a data source of a particular type.</span></span> <span data-ttu-id="a8607-125">Escreva seu próprio código personalizado para carregar ou salvar seus dados e, possivelmente, para abrir e fechar a conexão à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="a8607-125">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source.</span></span>

 <span data-ttu-id="a8607-126">Para obter informações gerais sobre como usar gerenciadores de conexões com o componente Script, consulte [Conectando-se a fontes de dados no componente Script](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="a8607-126">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="a8607-127">Para obter mais informações sobre a página **Gerenciadores de Conexões** do **Editor de Transformação Scripts**, consulte [Editor de Transformação Scripts &#40;Página Gerenciadores de Conexões&#41;](../script-transformation-editor-connection-managers-page.md).</span><span class="sxs-lookup"><span data-stu-id="a8607-127">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-inputs-and-input-columns"></a><span data-ttu-id="a8607-128">Configurando entradas e colunas de entrada</span><span class="sxs-lookup"><span data-stu-id="a8607-128">Configuring Inputs and Input Columns</span></span>
 <span data-ttu-id="a8607-129">Um componente de destino tem uma entrada e nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="a8607-129">A destination component has one input and no outputs.</span></span>

 <span data-ttu-id="a8607-130">Na página **Colunas de Entrada** do **Editor de Transformação Scripts**, a lista de colunas mostra as colunas disponíveis da saída do componente upstream no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="a8607-130">On the **Input Columns** page of the **Script Transformation Editor**, the column list shows the available columns from the output of the upstream component in the data flow.</span></span> <span data-ttu-id="a8607-131">Selecione as colunas a serem salvas.</span><span class="sxs-lookup"><span data-stu-id="a8607-131">Select the columns that you want to save.</span></span>

 <span data-ttu-id="a8607-132">Para obter mais informações sobre a página **Colunas de Entrada** do **Editor de Transformação Scripts**, consulte [Editor de Transformação Scripts &#40;página Colunas de Entrada&#41;](../script-transformation-editor-input-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="a8607-132">For more information about the **Input Columns** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Input Columns Page&#41;](../script-transformation-editor-input-columns-page.md).</span></span>

 <span data-ttu-id="a8607-133">A página **Entradas e Saídas** do **Editor de Transformação Scripts** mostra uma única entrada, que pode ser renomeada.</span><span class="sxs-lookup"><span data-stu-id="a8607-133">The **Inputs and Outputs** page of the **Script Transformation Editor** shows a single input, which you can rename.</span></span> <span data-ttu-id="a8607-134">Você fará referência à entrada pelo nome em seu script usando a propriedade de acessador criada no código gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a8607-134">You will refer to the input by its name in your script by using the accessor property created in the auto-generated code.</span></span>

 <span data-ttu-id="a8607-135">Para obter mais informações sobre a página **Entradas e Saídas** do **Editor de Transformação Scripts**, consulte [Editor de Transformação Scripts &#40;página Entradas e Saídas&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span><span class="sxs-lookup"><span data-stu-id="a8607-135">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="a8607-136">Adicionando variáveis</span><span class="sxs-lookup"><span data-stu-id="a8607-136">Adding Variables</span></span>
 <span data-ttu-id="a8607-137">Se você quiser usar variáveis existentes em seu script, poderá adicioná-las nos campos de `ReadOnlyVariables` `ReadWriteVariables` propriedade e na página **script** do **Editor de transformação scripts**.</span><span class="sxs-lookup"><span data-stu-id="a8607-137">If you want to use existing variables in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="a8607-138">Ao adicionar diversas variáveis aos campos de propriedade, separe os nomes das variáveis com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="a8607-138">When you add multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="a8607-139">Você também pode selecionar várias variáveis clicando no botão de reticências (**...**) ao lado dos `ReadOnlyVariables` campos de propriedade e e `ReadWriteVariables` selecionando as variáveis na caixa de diálogo **Selecionar variáveis** .</span><span class="sxs-lookup"><span data-stu-id="a8607-139">You can also select multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields, and then selecting the variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="a8607-140">Para obter informações gerais sobre como usar variáveis com o componente Script, consulte [Usando variáveis no componente Script](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="a8607-140">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="a8607-141">Para obter mais informações sobre a página **Script** do **Editor de Transformação Scripts**, consulte [Editor de Transformação Scripts &#40;Página Script&#41;](../script-transformation-editor-script-page.md).</span><span class="sxs-lookup"><span data-stu-id="a8607-141">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-destination-component-in-code-design-mode"></a><span data-ttu-id="a8607-142">Gerando scripts de um componente de destino em modo do design de código</span><span class="sxs-lookup"><span data-stu-id="a8607-142">Scripting a Destination Component in Code-Design Mode</span></span>
 <span data-ttu-id="a8607-143">Depois de configurar os metadados do seu componente, você poderá escrever seu script personalizado.</span><span class="sxs-lookup"><span data-stu-id="a8607-143">After you have configured the metadata for your component, you can write your custom script.</span></span> <span data-ttu-id="a8607-144">No **Editor de Transformação Scripts**, na página **Script**, clique em **Editar Script** para abrir o IDE do VSTA ([!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications), no qual você pode adicionar o script personalizado.</span><span class="sxs-lookup"><span data-stu-id="a8607-144">In the **Script Transformation Editor**, on the **Script** page, click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE where you can add your custom script.</span></span> <span data-ttu-id="a8607-145">A linguagem de scripts usada depende se você selecionou o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic ou o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# como a linguagem de scripts para a propriedade **ScriptLanguage** na página **Script**.</span><span class="sxs-lookup"><span data-stu-id="a8607-145">The scripting language that you use depends on whether you selected [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# as the script language for the **ScriptLanguage** property on the **Script** page.</span></span>

 <span data-ttu-id="a8607-146">Para obter informações importantes que se aplicam a todos os tipos de componentes criados por meio do componente Script, consulte [Codificando e depurando o componente Script](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="a8607-146">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="a8607-147">Compreendendo o código gerado automaticamente</span><span class="sxs-lookup"><span data-stu-id="a8607-147">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="a8607-148">Quando você abre o VSTA IDE depois de criar e configurar um componente de destino, a classe `ScriptMain` editável aparece no editor de códigos com um stub para o método `ProcessInputRow`.</span><span class="sxs-lookup"><span data-stu-id="a8607-148">When you open the VSTA IDE after you create and configuring a destination component, the editable `ScriptMain` class appears in the code editor with a stub for the `ProcessInputRow` method.</span></span> <span data-ttu-id="a8607-149">A classe `ScriptMain` é onde você escreverá seu código personalizado, e `ProcessInputRow` é o método mais importante em um componente de destino.</span><span class="sxs-lookup"><span data-stu-id="a8607-149">The `ScriptMain` class is where you will write your custom code, and `ProcessInputRow` is the most important method in a destination component.</span></span>

 <span data-ttu-id="a8607-150">Se você abrir a janela **Explorador de projeto** no VSTA, poderá ver que o componente script também gerou itens de `BufferWrapper` projeto e somente leitura `ComponentWrapper` .</span><span class="sxs-lookup"><span data-stu-id="a8607-150">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="a8607-151">A classe `ScriptMain` herda da classe `UserComponent` no item de projeto `ComponentWrapper`.</span><span class="sxs-lookup"><span data-stu-id="a8607-151">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="a8607-152">Em tempo de execução, o mecanismo de fluxo de dados invoca o método `ProcessInput` na classe `UserComponent`, que substitui o método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A> da classe pai <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="a8607-152">At run time, the data flow engine invokes the `ProcessInput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="a8607-153">O método `ProcessInput`, por sua vez, executa um loop nas linhas do buffer de entrada e chama o método `ProcessInputRow` uma vez para cada linha.</span><span class="sxs-lookup"><span data-stu-id="a8607-153">The `ProcessInput` method in turn loops through the rows in the input buffer and calls the `ProcessInputRow` method one time for each row.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="a8607-154">Escrevendo seu código personalizado</span><span class="sxs-lookup"><span data-stu-id="a8607-154">Writing Your Custom Code</span></span>
 <span data-ttu-id="a8607-155">Para terminar de criar um componente de destino personalizado, você pode escrever um script nos métodos a seguir disponíveis na classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="a8607-155">To finish creating a custom destination component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="a8607-156">Substitua o método `AcquireConnections` para se conectar à fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="a8607-156">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="a8607-157">Extraia o objeto de conexão, ou as informações de conexão requeridas, do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="a8607-157">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="a8607-158">Substitua o método `PreExecute` como preparo para salvar os dados.</span><span class="sxs-lookup"><span data-stu-id="a8607-158">Override the `PreExecute` method to prepare to save the data.</span></span> <span data-ttu-id="a8607-159">Por exemplo, talvez você queira criar e configurar um `SqlCommand` e seus parâmetros nesse método.</span><span class="sxs-lookup"><span data-stu-id="a8607-159">For example, you may want to create and configure a `SqlCommand` and its parameters in this method.</span></span>

3.  <span data-ttu-id="a8607-160">Use o método `ProcessInputRow` substituído para copiar cada linha de entrada para a fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="a8607-160">Use the overridden `ProcessInputRow` method to copy each input row to the external data source.</span></span> <span data-ttu-id="a8607-161">Por exemplo, para um destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você pode copiar os valores de coluna nos parâmetros de um `SqlCommand` e executar o comando uma vez para cada linha.</span><span class="sxs-lookup"><span data-stu-id="a8607-161">For example, for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, you can copy the column values into the parameters of a `SqlCommand` and execute the command one time for each row.</span></span> <span data-ttu-id="a8607-162">Para um destino de arquivo simples, você pode escrever os valores de cada coluna para um `StreamWriter`, separando-os com o delimitador de colunas.</span><span class="sxs-lookup"><span data-stu-id="a8607-162">For a flat file destination, you can write the values for each column to a `StreamWriter`, separating the values by the column delimiter.</span></span>

4.  <span data-ttu-id="a8607-163">Substitua o método `PostExecute` para desconectar-se da fonte de dados externa, caso necessário, e executar qualquer outra limpeza exigeida.</span><span class="sxs-lookup"><span data-stu-id="a8607-163">Override the `PostExecute` method to disconnect from the external data source, if required, and to perform any other required cleanup.</span></span>

## <a name="examples"></a><span data-ttu-id="a8607-164">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a8607-164">Examples</span></span>
 <span data-ttu-id="a8607-165">Os exemplos a seguir demonstram o código que é exigido na classe `ScriptMain` para criar um componente de destino.</span><span class="sxs-lookup"><span data-stu-id="a8607-165">The examples that follow demonstrate code that is required in the `ScriptMain` class to create a destination component.</span></span>

> [!NOTE]
>  <span data-ttu-id="a8607-166">Esses exemplos usam a tabela **Person. Address** no `AdventureWorks` banco de dados de exemplo e passam sua primeira e quarta colunas, as colunas **int \* AddressID**\* e **nvarchar (30) City** , por meio do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="a8607-166">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="a8607-167">Os mesmos dados são usados nos exemplos de origem, transformação e destino nessa seção.</span><span class="sxs-lookup"><span data-stu-id="a8607-167">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="a8607-168">Pré-requisitos e suposições adicionais são documentados para cada exemplo.</span><span class="sxs-lookup"><span data-stu-id="a8607-168">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-destination-example"></a><span data-ttu-id="a8607-169">Exemplo de destino ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8607-169">ADO.NET Destination Example</span></span>
 <span data-ttu-id="a8607-170">Esse exemplo demonstra um componente de destino que usa um gerenciador de conexões existente do [!INCLUDE[vstecado](../../includes/vstecado-md.md)] para salvar dados do fluxo de dados em uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8607-170">This example demonstrates a destination component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to save data from the data flow into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="a8607-171">Se você quiser executar esse código de exemplo, configure o pacote e o componente desta forma:</span><span class="sxs-lookup"><span data-stu-id="a8607-171">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="a8607-172">Crie um [!INCLUDE[vstecado](../../includes/vstecado-md.md)] Gerenciador de conexões que use o `SqlClient` provedor para se conectar ao `AdventureWorks` banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a8607-172">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="a8607-173">Crie uma tabela de destino executando o seguinte comando [!INCLUDE[tsql](../../includes/tsql-md.md)] no banco de dados `AdventureWorks`:</span><span class="sxs-lookup"><span data-stu-id="a8607-173">Create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

3.  <span data-ttu-id="a8607-174">Adicione um novo componente Script à superfície do designer de Fluxo de Dados e configure-o como um destino.</span><span class="sxs-lookup"><span data-stu-id="a8607-174">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

4.  <span data-ttu-id="a8607-175">Conecte a saída de uma origem ou transformação upstream para o componente de destino no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8607-175">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="a8607-176">(Você pode conectar uma fonte diretamente a um destino sem nenhuma transformação.) Essa saída deve fornecer dados da tabela **Person. Address** do banco de `AdventureWorks` dados de exemplo que contém pelo menos as colunas **AddressID** e **City** .</span><span class="sxs-lookup"><span data-stu-id="a8607-176">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database that contains at least the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="a8607-177">Abra o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="a8607-177">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="a8607-178">Na página **Colunas de Entrada**, selecione as colunas de entrada **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="a8607-178">On the **Input Columns** page, select the **AddressID** and **City** input columns.</span></span>

6.  <span data-ttu-id="a8607-179">Na página **Entradas e Saídas**, renomeie a entrada com um nome mais descritivo, como **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="a8607-179">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>

7.  <span data-ttu-id="a8607-180">Na página **Gerenciadores de Conexões**, adicione ou crie o gerenciador de conexões do [!INCLUDE[vstecado](../../includes/vstecado-md.md)] com um nome como **MyADONETConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="a8607-180">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager with a name such as **MyADONETConnectionManager**.</span></span>

8.  <span data-ttu-id="a8607-181">Na página **Script**, clique em **Editar Script** e insira o script a seguir.</span><span class="sxs-lookup"><span data-stu-id="a8607-181">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="a8607-182">Em seguida, feche o ambiente de desenvolvimento de script.</span><span class="sxs-lookup"><span data-stu-id="a8607-182">Then close the script development environment.</span></span>

9. <span data-ttu-id="a8607-183">Feche o **Editor de Transformação Scripts** e execute a amostra.</span><span class="sxs-lookup"><span data-stu-id="a8607-183">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.Data.SqlClient
...
Public Class ScriptMain
    Inherits UserComponent

    Dim connMgr As IDTSConnectionManager100
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        connMgr = Me.Connections.MyADONETConnectionManager
        sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

    End Sub

    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)
        With sqlCmd
            .Parameters("@addressid").Value = Row.AddressID
            .Parameters("@city").Value = Row.City
            .ExecuteNonQuery()
        End With
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
    SqlCommand sqlCmd;
    SqlParameter sqlParam;

    public override void AcquireConnections(object Transaction)
    {

        connMgr = this.Connections.MyADONETConnectionManager;
        sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " +
            "VALUES(@addressid, @city)", sqlConn);
        sqlParam = new SqlParameter("@addressid", SqlDbType.Int);
        sqlCmd.Parameters.Add(sqlParam);
        sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30);
        sqlCmd.Parameters.Add(sqlParam);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {
        {
            sqlCmd.Parameters["@addressid"].Value = Row.AddressID;
            sqlCmd.Parameters["@city"].Value = Row.City;
            sqlCmd.ExecuteNonQuery();
        }
    }

    public override void ReleaseConnections()
    {

        connMgr.ReleaseConnection(sqlConn);

    }

}
```

### <a name="flat-file-destination-example"></a><span data-ttu-id="a8607-184">Exemplo de Destino de Arquivos Simples</span><span class="sxs-lookup"><span data-stu-id="a8607-184">Flat File Destination Example</span></span>
 <span data-ttu-id="a8607-185">Esse exemplo demonstra um componente de destino que usa um gerenciador de conexões de arquivos simples existente para salvar dados do fluxo de dados em um arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="a8607-185">This example demonstrates a destination component that uses an existing Flat File connection manager to save data from the data flow to a flat file.</span></span>

 <span data-ttu-id="a8607-186">Se você quiser executar esse código de exemplo, configure o pacote e o componente desta forma:</span><span class="sxs-lookup"><span data-stu-id="a8607-186">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="a8607-187">Crie um gerenciador de conexões de arquivos simples que se conecte a um arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="a8607-187">Create a Flat File connection manager that connects to a destination file.</span></span> <span data-ttu-id="a8607-188">Não é necessário que o arquivo já exista; o componente de destino irá criá-lo.</span><span class="sxs-lookup"><span data-stu-id="a8607-188">The file does not have to exist; the destination component will create it.</span></span> <span data-ttu-id="a8607-189">Configure o arquivo de destino como um arquivo delimitado por vírgula que contém as colunas **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="a8607-189">Configure the destination file as a comma-delimited file that contains the **AddressID** and **City** columns.</span></span>

2.  <span data-ttu-id="a8607-190">Adicione um novo componente Script à superfície do designer de Fluxo de Dados e configure-o como um destino.</span><span class="sxs-lookup"><span data-stu-id="a8607-190">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

3.  <span data-ttu-id="a8607-191">Conecte a saída de uma origem ou transformação upstream para o componente de destino no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8607-191">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="a8607-192">(Você pode conectar uma fonte diretamente a um destino sem nenhuma transformação.) Essa saída deve fornecer dados da tabela **Person. Address** do banco de `AdventureWorks` dados de exemplo e deve conter pelo menos as colunas **AddressID** e **City** .</span><span class="sxs-lookup"><span data-stu-id="a8607-192">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database, and should contain at least the **AddressID** and **City** columns.</span></span>

4.  <span data-ttu-id="a8607-193">Abra o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="a8607-193">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="a8607-194">Na página **Colunas de Entrada**, selecione as colunas **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="a8607-194">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="a8607-195">Na página **Entradas e Saídas**, renomeie a entrada com um nome mais descritivo, como **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="a8607-195">On the **Inputs and Outputs** page, rename the input with a more descriptive name, such as **MyAddressInput**.</span></span>

6.  <span data-ttu-id="a8607-196">Na página **Gerenciadores de Conexões**, adicione ou crie o gerenciador de conexões de Arquivos Simples com um nome descritivo como **MyFlatFileDestConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="a8607-196">On the **Connection Managers** page, add or create the Flat File connection manager with a descriptive name such as **MyFlatFileDestConnectionManager**.</span></span>

7.  <span data-ttu-id="a8607-197">Na página **Script**, clique em **Editar Script** e insira o script a seguir.</span><span class="sxs-lookup"><span data-stu-id="a8607-197">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="a8607-198">Em seguida, feche o ambiente de desenvolvimento de script.</span><span class="sxs-lookup"><span data-stu-id="a8607-198">Then close the script development environment.</span></span>

8.  <span data-ttu-id="a8607-199">Feche o **Editor de Transformação Scripts** e execute a amostra.</span><span class="sxs-lookup"><span data-stu-id="a8607-199">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.IO
...
Public Class ScriptMain
    Inherits UserComponent

    Dim copiedAddressFile As String
    Private textWriter As StreamWriter
    Private columnDelimiter As String = ","

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        Dim connMgr As IDTSConnectionManager100 = _
            Me.Connections.MyFlatFileDestConnectionManager
        copiedAddressFile = CType(connMgr.AcquireConnection(Nothing), String)

    End Sub

    Public Overrides Sub PreExecute()

        textWriter = New StreamWriter(copiedAddressFile, False)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)

        With textWriter
            If Not Row.AddressID_IsNull Then
                .Write(Row.AddressID)
            End If
            .Write(columnDelimiter)
            If Not Row.City_IsNull Then
                .Write(Row.City)
            End If
            .WriteLine()
        End With

    End Sub

    Public Overrides Sub PostExecute()

        textWriter.Close()

    End Sub

End Class
```

```csharp
using System.IO;
public class ScriptMain:
    UserComponent

{
    string copiedAddressFile;
    private StreamWriter textWriter;
    private string columnDelimiter = ",";

    public override void AcquireConnections(object Transaction)
    {

        IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileDestConnectionManager;
        copiedAddressFile = (string) connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        textWriter = new StreamWriter(copiedAddressFile, false);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {

        {
            if (!Row.AddressID_IsNull)
            {
                textWriter.Write(Row.AddressID);
            }
            textWriter.Write(columnDelimiter);
            if (!Row.City_IsNull)
            {
                textWriter.Write(Row.City);
            }
            textWriter.WriteLine();
        }

    }

    public override void PostExecute()
    {

        textWriter.Close();

    }

}
```

<span data-ttu-id="a8607-200">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a8607-200">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a8607-201">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="a8607-201">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a8607-202">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="a8607-202">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a8607-203">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="a8607-203">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8607-204">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a8607-204">See Also</span></span>
 <span data-ttu-id="a8607-205">[Criando uma fonte com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [desenvolvendo um componente de destino personalizado](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span><span class="sxs-lookup"><span data-stu-id="a8607-205">[Creating a Source with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span></span>


