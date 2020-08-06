---
title: 'Etapa 2: configurar e habilitar configurações de pacote | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 005218ab-8dd5-48e9-a185-6bc60cd43a7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a804efcd84ebe563a13f61443fe19096788ca809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571440"
---
# <a name="step-2-enabling-and-configuring-package-configurations"></a><span data-ttu-id="7e3b3-102">Etapa 2: Habilitar e configurar configurações de pacote</span><span class="sxs-lookup"><span data-stu-id="7e3b3-102">Step 2: Enabling and Configuring Package Configurations</span></span>
  <span data-ttu-id="7e3b3-103">Nesta tarefa, você converterá o projeto no Modelo de Implantação de Pacote e habilitará configurações de pacote usando o Assistente de Configuração de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-103">In this task, you will convert the project to the Package Deployment Model and enable package configurations using the Package Configuration Wizard.</span></span> <span data-ttu-id="7e3b3-104">Você usará esse assistente para gerar um arquivo de configuração XML que contenha definições de configuração para a propriedade `Directory` do contêiner Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-104">You will use this wizard to generate an XML configuration file that contains configuration settings for the `Directory` property of the Foreach Loop container.</span></span> <span data-ttu-id="7e3b3-105">O valor da propriedade de diretório é fornecido por uma nova variável de nível de pacote que você pode atualizar no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-105">The value of the Directory property is supplied by a new package-level variable that you can update at run time.</span></span> <span data-ttu-id="7e3b3-106">Adicionalmente, você populará uma pasta de dados de exemplo para usar durante o teste.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-106">Additionally, you will populate a new sample data folder to use during testing.</span></span>  
  
### <a name="to-create-a-new-package-level-variable-mapped-to-the-directory-property"></a><span data-ttu-id="7e3b3-107">Para criar uma nova variável de nível de pacote mapeada para a propriedade de diretório</span><span class="sxs-lookup"><span data-stu-id="7e3b3-107">To create a new package-level variable mapped to the Directory property</span></span>  
  
1.  <span data-ttu-id="7e3b3-108">Clique na tela de fundo da guia **Fluxo de Controle** no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7e3b3-108">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="7e3b3-109">Isso define o escopo da variável que você criará para o pacote.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-109">This sets the scope for the variable you will create to the package.</span></span>  
  
2.  <span data-ttu-id="7e3b3-110">No menu [!INCLUDE[ssIS](../includes/ssis-md.md)] , selecione **Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-110">On the [!INCLUDE[ssIS](../includes/ssis-md.md)] menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="7e3b3-111">Na janela **Variáveis** , clique no ícone Adicionar Variável.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-111">In the **Variables** window, click the Add Variable icon.</span></span>  
  
4.  <span data-ttu-id="7e3b3-112">Na caixa **Nome** , digite **varFolderName**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-112">In the **Name** box, type **varFolderName**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="7e3b3-113">Nomes de variáveis fazem diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-113">Variable names are case sensitive.</span></span>  
  
5.  <span data-ttu-id="7e3b3-114">Verifique se a caixa **escopo** mostra o nome do pacote, lição 5.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-114">Verify that the **Scope** box shows the name of the package, Lesson 5.</span></span>  
  
6.  <span data-ttu-id="7e3b3-115">Defina o valor da caixa **Tipo de Dados** da variável `varFolderName` como **Cadeia de Caracteres**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-115">Set the value of the **Data Type** box of the `varFolderName` variable to **String**.</span></span>  
  
7.  <span data-ttu-id="7e3b3-116">Retorne à guia **Fluxo de Controle** e clique duas vezes no contêiner **Arquivo Foreach na Pasta** .</span><span class="sxs-lookup"><span data-stu-id="7e3b3-116">Return to the **Control Flow** tab and double-click the **Foreach File in Folder** container.</span></span>  
  
8.  <span data-ttu-id="7e3b3-117">Na página **coleção** do editor de **loop foreach**, clique em **expressões**e, em seguida, clique no botão de reticências **(...)**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-117">On the **Collection** page of the **Foreach Loop Editor**, click **Expressions**, and then click the ellipsis button **(...)**.</span></span>  
  
9. <span data-ttu-id="7e3b3-118">No **Editor de expressões de propriedade**, clique na lista de **Propriedades** e selecione `Directory` .</span><span class="sxs-lookup"><span data-stu-id="7e3b3-118">In the **Property Expressions Editor**, click in the **Property** list, and select `Directory`.</span></span>  
  
10. <span data-ttu-id="7e3b3-119">Na caixa **expressão** , clique no botão de reticências **(...)**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-119">In the **Expression** box, click the ellipsis button **(...)**.</span></span>  
  
11. <span data-ttu-id="7e3b3-120">No **Construtor de Expressões**, expanda a pasta Variáveis e arraste a variável **User::varFolderName** até a caixa **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="7e3b3-120">In the **Expression Builder**, expand the Variables folder, and drag the variable **User::varFolderName** to the **Expression** box.</span></span>  
  
12. <span data-ttu-id="7e3b3-121">Clique em **OK** para sair do **Construtor de Expressões**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-121">Click **OK** to exit the **Expression Builder**.</span></span>  
  
13. <span data-ttu-id="7e3b3-122">Clique em **OK** para sair do **Editor de Expressões de Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-122">Click **OK** to exit the **Property Expressions Editor**.</span></span>  
  
14. <span data-ttu-id="7e3b3-123">Clique em **OK** para sair do **Editor do Loop Foreach**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-123">Click **OK** to exit the **Foreach Loop Editor**.</span></span>  
  
### <a name="to-enable-package-configurations"></a><span data-ttu-id="7e3b3-124">Para habilitar configurações de pacote</span><span class="sxs-lookup"><span data-stu-id="7e3b3-124">To enable package configurations</span></span>  
  
1.  <span data-ttu-id="7e3b3-125">No **menu Projeto**, clique em **converter em modelo de implantação de pacote**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-125">On the **Project Menu**, click **Convert to Package Deployment Model**.</span></span>  
  
2.  <span data-ttu-id="7e3b3-126">Clique em **OK** no aviso e, assim que a conversão for concluída, clique em **OK** na caixa de diálogo **Converter em Modelo de Implantação de Pacote** .</span><span class="sxs-lookup"><span data-stu-id="7e3b3-126">Click **OK** on the warning prompt and, once the conversion is complete, click **OK** on the **Convert to Package Deployment Model** dialog.</span></span>  
  
3.  <span data-ttu-id="7e3b3-127">Clique na tela de fundo da guia **Fluxo de Controle** no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7e3b3-127">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
4.  <span data-ttu-id="7e3b3-128">No menu **SSIS** , clique em **Configurações do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-128">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
5.  <span data-ttu-id="7e3b3-129">Na caixa de diálogo **Organizador de Configurações do Pacote** , selecione **Habilitar Configurações do Pacote**e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-129">In the **Package Configurations Organizer** dialog box, select **Enable Package Configurations**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="7e3b3-130">Na página inicial do assistente de configuração de pacotes, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-130">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
7.  <span data-ttu-id="7e3b3-131">Na página **Selecionar Tipo de Configuração** , verifique se o **Tipo de configuração** está definido como **Arquivo de configuração XML**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-131">On the **Select Configuration Type** page, verify that the **Configuration type** is set to **XML configuration file**.</span></span>  
  
8.  <span data-ttu-id="7e3b3-132">Na página **Selecionar Tipo de Configuração** , clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-132">On the **Select Configuration Type** page, click **Browse**.</span></span>  
  
9. <span data-ttu-id="7e3b3-133">Por padrão, a caixa de diálogo **Selecionar Local do Arquivo de Configuração** abrirá a pasta do projeto.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-133">By default, the **Select Configuration File Location** dialog box will open to the project folder.</span></span>  
  
10. <span data-ttu-id="7e3b3-134">Na caixa de diálogo **Selecionar Local do Arquivo de Configuração** , em **Nome do arquivo** , digite **SSISTutorial**e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-134">In the **Select Configuration File Location** dialog box, for **File name** type **SSISTutorial**, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="7e3b3-135">Na página **Selecionar Tipo de Configuração** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-135">On the **Select Configuration Type** page, click **Next.**</span></span>  
  
12. <span data-ttu-id="7e3b3-136">Na página **selecionar propriedades a serem exportadas** , no painel **objetos** , expanda **variáveis**, expanda **varFolderName**, **Propriedades**e selecione **valor**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-136">On the **Select Properties to Export** page, in the **Objects** pane, expand **Variables**, expand **varFolderName**, expand **Properties**, and then select **Value**.</span></span>  
  
13. <span data-ttu-id="7e3b3-137">Na página **Selecionar Propriedades para Exportar** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-137">On the **Select Properties to Export** page, click **Next**.</span></span>  
  
14. <span data-ttu-id="7e3b3-138">Na página **Concluindo o Assistente** , digite um nome de configuração para a configuração, como **Configuração do Diretório de Tutoriais do SSIS**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-138">On the **Completing the Wizard** page, type a configuration name for the configuration, such as **SSIS Tutorial Directory configuration**.</span></span> <span data-ttu-id="7e3b3-139">Esse é o nome de configuração exibido na caixa de diálogo **Organizador de Configurações do Pacote** .</span><span class="sxs-lookup"><span data-stu-id="7e3b3-139">This is the configuration name that is displayed in the **Package Configuration Organizer** dialog box.</span></span>  
  
15. <span data-ttu-id="7e3b3-140">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="7e3b3-141">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-141">Click **Close**.</span></span>  
  
17. <span data-ttu-id="7e3b3-142">O assistente cria um arquivo de configuração, chamado SSISTutorial.dtsConfig, que contém as definições de configuração de `value` da variável que define a propriedade `Directory` do enumerador.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-142">The wizard creates a configuration file, named SSISTutorial.dtsConfig, that contains configuration settings for the `value` of the variable that in turn sets the `Directory` property of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e3b3-143">Um arquivo de configuração geralmente contém informações complexas sobre as propriedades do pacote, mas, para este tutorial, a única informação de configuração deveria ser</span><span class="sxs-lookup"><span data-stu-id="7e3b3-143">A configuration file typically contains complex information about the package properties, but for this tutorial the only configuration information should be</span></span>  
    > <span data-ttu-id="7e3b3-144"><Configuration ConfiguredType="Property"</span><span class="sxs-lookup"><span data-stu-id="7e3b3-144"><Configuration ConfiguredType="Property"</span></span>  
    > <span data-ttu-id="7e3b3-145">Path = "\Package.Variables [User:: varFolderName]. Properties [valor] "ValueType =" cadeia de caracteres "\></span><span class="sxs-lookup"><span data-stu-id="7e3b3-145">Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"\></span></span>  
    >  \<ConfiguredValue>\</ConfiguredValue>  
    > <span data-ttu-id="7e3b3-146">\</Configuration>.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-146">\</Configuration>.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="7e3b3-147">Para criar e popular uma nova pasta de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="7e3b3-147">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="7e3b3-148">No Windows Explorer, no nível raiz da unidade (por exemplo, C: \\ ), crie uma nova pasta chamada `New Sample Data` .</span><span class="sxs-lookup"><span data-stu-id="7e3b3-148">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named `New Sample Data`.</span></span>  
  
2.  <span data-ttu-id="7e3b3-149">Localize os arquivos de exemplo no computador e copie três dos arquivos da pasta.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-149">Locate the sample files on your computer and copy three of the files from the folder.</span></span>  
  
3.  <span data-ttu-id="7e3b3-150">Na `New Sample Data` pasta, Cole os arquivos copiados.</span><span class="sxs-lookup"><span data-stu-id="7e3b3-150">In the `New Sample Data` folder, paste the copied files.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7e3b3-151">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="7e3b3-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7e3b3-152">Etapa 3: Modificar o valor de configuração da propriedade de diretório</span><span class="sxs-lookup"><span data-stu-id="7e3b3-152">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
  
