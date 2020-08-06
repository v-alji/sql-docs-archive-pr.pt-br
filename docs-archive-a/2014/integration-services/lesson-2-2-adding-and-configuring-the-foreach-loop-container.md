---
title: 'Etapa 2: adicionar e configurar o contêiner Loop Foreach | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 88a973cc-0f23-4ecf-adb6-5b06279c2df6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de5e8875c43edda618ccef4839c88c3b84a003cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570121"
---
# <a name="step-2-adding-and-configuring-the-foreach-loop-container"></a><span data-ttu-id="b6fa7-102">Etapa 2: Adicionar e configurar o contêiner Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="b6fa7-102">Step 2: Adding and Configuring the Foreach Loop Container</span></span>
  <span data-ttu-id="b6fa7-103">Nessa tarefa, você adicionará a capacidade de executar loop através de uma pasta de arquivos simples e aplicará a mesma transformação Fluxo de Dados usada na Lição 1 para cada um desses arquivos simples.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-103">In this task, you will add the ability to loop through a folder of flat files and apply the same data flow transformation used in Lesson 1 to each of those flat files.</span></span> <span data-ttu-id="b6fa7-104">Você faz isto adicionando e configurando um contêiner Loop Foreach ao fluxo de controle.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-104">You do this by adding and configuring a Foreach Loop container to the control flow.</span></span>  
  
 <span data-ttu-id="b6fa7-105">O contêiner Loop Foreach que você adicionar deve ser capaz de se conectar a cada arquivo simples na pasta.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-105">The Foreach Loop container that you add must be able to connect to each flat file in the folder.</span></span> <span data-ttu-id="b6fa7-106">Como todos os arquivos da pasta têm o mesmo formato, o contêiner Loop Foreach pode usar o mesmo gerenciador de conexões de Arquivo Simples para conectar-se a cada um desses arquivos.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-106">Because all the files in the folder have the same format, the Foreach Loop container can use the same Flat File connection manager to connect to each of these files.</span></span> <span data-ttu-id="b6fa7-107">O gerenciador de conexões de Arquivo Simples que o contêiner usará é o mesmo gerenciador de conexões de Arquivo Simples que você criou na Lição 1.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-107">The Flat File connection manager that the container will use is the same Flat File connection manager that you created in Lesson 1.</span></span>  
  
 <span data-ttu-id="b6fa7-108">Atualmente, o gerenciador de conexões de Arquivo Simples da Lição 1 se conecta a um único arquivo simples específico.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-108">Currently, the Flat File connection manager from Lesson 1 connects to only one, specific flat file.</span></span> <span data-ttu-id="b6fa7-109">Para conectar-se iterativamente a cada arquivo simples da pasta, você terá que configurar o contêiner Loop Foreach e o gerenciador de conexões de Arquivo Simples da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b6fa7-109">To iteratively connect to each flat file in the folder, you will have to configure both the Foreach Loop container and the Flat File connection manager as follows:</span></span>  
  
-   <span data-ttu-id="b6fa7-110">**Contêiner Loop Foreach:** você mapeará o valor enumerado do contêiner para uma variável de pacote definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-110">**Foreach Loop container:** You will map the enumerated value of the container to a user-defined package variable.</span></span> <span data-ttu-id="b6fa7-111">O contêiner usará a variável definida pelo usuário para modificar dinamicamente a propriedade `ConnectionString` do gerenciador de conexões de Arquivo Simples, e conectar-se iterativamente a cada um dos arquivos simples da pasta.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-111">The container will then use this user-defined variable to dynamically modify the `ConnectionString` property of the Flat File connection manager and iteratively connect to each flat file in the folder.</span></span>  
  
-   <span data-ttu-id="b6fa7-112">**Gerenciador de conexões de arquivos simples:** Você modificará o Gerenciador de conexões criado na lição 1 usando uma variável definida pelo usuário para popular a propriedade do Gerenciador de conexões `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="b6fa7-112">**Flat File connection manager:** You will modify the connection manager that was created in Lesson 1 by using a user-defined variable to populate the connection manager's `ConnectionString` property.</span></span>  
  
 <span data-ttu-id="b6fa7-113">Os procedimentos nessa tarefa mostram como você pode criar e modificar o contêiner Loop Foreach para usar uma variável definida pelo usuário e adicionar a tarefa de fluxo de dados ao loop.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-113">The procedures in this task show you how to create and modify the Foreach Loop container to use a user-defined package variable and to add the data flow task to the loop.</span></span> <span data-ttu-id="b6fa7-114">Você aprenderá como modificar o gerenciador de conexões de Arquivo Simples para usar uma variável definida pelo usuário na próxima tarefa.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-114">You will learn how to modify the Flat File connection manager to use a user-defined variable in the next task.</span></span>  
  
 <span data-ttu-id="b6fa7-115">Após essas modificações no pacote, quando ele for executado, o contêiner Loop Foreach iterará através dessa coleção de arquivos na pasta Dados de Exemplo.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-115">After you have made these modifications to the package, when the package is run, the Foreach Loop Container will iterate through the collection of files in the Sample Data folder.</span></span> <span data-ttu-id="b6fa7-116">Toda vez que um arquivo é encontrado e corresponde ao critério, o contêiner Loop Foreach irá popular a variável definida pelo usuário com o nome do arquivo, mapeará a variável definida pelo usuário para a propriedade `ConnectionString` do gerenciador de conexões do Arquivo Simples de Dados Moeda de exemplo e, então, executará o fluxo de dados naquele arquivo.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-116">Each time a file is found that matches the criteria, the Foreach Loop Container will populate the user-defined variable with the file name, map the user-defined variable to the `ConnectionString` property of the Sample Currency Data Flat File connection manager, and then run the data flow against that file.</span></span> <span data-ttu-id="b6fa7-117">Portanto, em cada iteração do Loop Foreach a tarefa de Fluxo de Dados consumirá um arquivo simples diferente.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-117">Therefore, in each iteration of the Foreach Loop the Data Flow task will consume a different flat file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6fa7-118">Como o [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separa o fluxo de controle do fluxo de dados, qualquer loop que você adicionar ao fluxo de controle não exigirá modificações no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-118">Because [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates control flow from data flow, any looping that you add to the control flow will not require modification to the data flow.</span></span> <span data-ttu-id="b6fa7-119">Portanto, o fluxo de dados que você criou na Lição 1 não tem que ser alterado.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-119">Therefore, the data flow that you created in Lesson 1 does not have to be changed.</span></span>  
  
### <a name="to-add-a-foreach-loop-container"></a><span data-ttu-id="b6fa7-120">Para adicionar um contêiner Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="b6fa7-120">To add a Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="b6fa7-121">Em **SQL Server Data Tools**, clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="b6fa7-121">In **SQL Server Data Tools**, click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="b6fa7-122">Na **Caixa de Ferramentas do SSIS**, expanda **Contêineres**e arraste um **Contêiner Loop Foreach** até a superfície de design da guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="b6fa7-122">In the **SSIS Toolbox**, expand **Containers**, and then drag a **Foreach Loop Container** onto the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="b6fa7-123">Clique com o botão direito do mouse no **Contêiner Loop Foreach** recém-adicionado e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-123">Right-click the newly added **Foreach Loop Container** and select **Edit**.</span></span>  
  
4.  <span data-ttu-id="b6fa7-124">Na caixa de diálogo **Editor de loop foreach** , na página **geral** , em **nome**, digite `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="b6fa7-124">In the **Foreach Loop Editor** dialog box, on the **General** page, for **Name**, enter `Foreach File in Folder`.</span></span> <span data-ttu-id="b6fa7-125">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-125">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="b6fa7-126">Clique com o botão direito do mouse no contêiner Loop Foreach, clique em **Propriedades**e, na janela Propriedades, verifique se a `LocaleID` propriedade está definida como **Inglês (Estados Unidos)**.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-126">Right-click the Foreach Loop container, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
### <a name="to-configure-the-enumerator-for-the-foreach-loop-container"></a><span data-ttu-id="b6fa7-127">Para configurar o enumerador para o contêiner Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="b6fa7-127">To configure the enumerator for the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="b6fa7-128">Clique duas vezes em Arquivo Foreach na Pasta para abrir novamente o **Editor de Loop Foreach**.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-128">Double-click Foreach File in Folder to reopen the **Foreach Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="b6fa7-129">Clique em **Coleção**.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-129">Click **Collection**.</span></span>  
  
3.  <span data-ttu-id="b6fa7-130">Na página **Coleção** , selecione **Enumerador de Arquivo Foreach**.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-130">On the **Collection** page, select **Foreach File Enumerator**.</span></span>  
  
4.  <span data-ttu-id="b6fa7-131">No grupo **Configuração do enumerador** , clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-131">In the **Enumerator configuration** group, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="b6fa7-132">Na caixa de diálogo **Procurar pasta** , localize a pasta no computador que contém os arquivos Currency_\*.txt.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-132">In the **Browse for Folder** dialog box, locate the folder on your machine that contains the Currency_\*.txt files.</span></span>  
  
     <span data-ttu-id="b6fa7-133">Estes dados de exemplo estão incluídos com os pacotes de lição do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6fa7-133">This sample data is included with the [!INCLUDE[ssIS](../includes/ssis-md.md)] lesson packages.</span></span> <span data-ttu-id="b6fa7-134">Para baixar os dados de exemplo e os pacotes de lição, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-134">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="b6fa7-135">Navegue para os [Exemplos de Produtos do Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="b6fa7-135">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="b6fa7-136">Clique na guia **downloads** .</span><span class="sxs-lookup"><span data-stu-id="b6fa7-136">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="b6fa7-137">Clique no hiperlink " https://msftisprodsamples.codeplex.com/downloads/get/578097 " SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip arquivo.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-137">Click the  HYPERLINK "https://msftisprodsamples.codeplex.com/downloads/get/578097" SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
6.  <span data-ttu-id="b6fa7-138">Na caixa **Arquivos**, digite **Currency_\*.txt**.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-138">In the **Files** box, type **Currency_\*.txt**.</span></span>  
  
### <a name="to-map-the-enumerator-to-a-user-defined-variable"></a><span data-ttu-id="b6fa7-139">Para mapear o enumerador para uma variável definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="b6fa7-139">To map the enumerator to a user-defined variable</span></span>  
  
1.  <span data-ttu-id="b6fa7-140">Clique em **Mapeamentos de Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-140">Click **Variable Mappings**.</span></span>  
  
2.  <span data-ttu-id="b6fa7-141">Na página **mapeamentos de variáveis** , na coluna **variável** , clique na célula vazia e selecione **\<New Variable...>** .</span><span class="sxs-lookup"><span data-stu-id="b6fa7-141">On the **Variable Mappings** page, in the **Variable** column, click the empty cell and select **\<New Variable...>**.</span></span>  
  
3.  <span data-ttu-id="b6fa7-142">Na caixa de diálogo **Adicionar variável** , em **nome**, digite `varFileName` .</span><span class="sxs-lookup"><span data-stu-id="b6fa7-142">In the **Add Variable** dialog box, for **Name**, type `varFileName`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b6fa7-143">Nomes de variáveis fazem diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-143">Variable names are case sensitive.</span></span>  
  
4.  <span data-ttu-id="b6fa7-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6fa7-144">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="b6fa7-145">Clique em **OK** novamente para sair da caixa de diálogo **Editor de Loop Foreach** .</span><span class="sxs-lookup"><span data-stu-id="b6fa7-145">Click **OK** again to exit the **Foreach Loop Editor** dialog box.</span></span>  
  
### <a name="to-add-the-data-flow-task-to-the-loop"></a><span data-ttu-id="b6fa7-146">Para adicionar a tarefa de fluxo de dados ao loop</span><span class="sxs-lookup"><span data-stu-id="b6fa7-146">To add the data flow task to the loop</span></span>  
  
-   <span data-ttu-id="b6fa7-147">Arraste a tarefa extrair fluxo de dados de **dados de moeda de exemplo** para o contêiner Loop Foreach agora renomeado `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="b6fa7-147">Drag the **Extract Sample Currency Data** data flow task onto the Foreach Loop container now renamed `Foreach File in Folder`.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="b6fa7-148">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="b6fa7-148">Next Lesson Task</span></span>  
 [<span data-ttu-id="b6fa7-149">Etapa 3: Modificar o gerenciador de conexões de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="b6fa7-149">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
## <a name="see-also"></a><span data-ttu-id="b6fa7-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b6fa7-150">See Also</span></span>  
 <span data-ttu-id="b6fa7-151">[Configurar um contêiner Loop Foreach](control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="b6fa7-151">[Configure a Foreach Loop Container](control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="b6fa7-152">Usar variáveis em pacotes</span><span class="sxs-lookup"><span data-stu-id="b6fa7-152">Use Variables in Packages</span></span>](use-variables-in-packages.md)  
  
