---
title: 'Etapa 2: adicionar e configurar o registro em log | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56105f3f-e500-4669-8c8e-acf434527727
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f2cdce6f34a19e22830d357d20f5d99cff8c14f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680557"
---
# <a name="step-2-adding-and-configuring-logging"></a><span data-ttu-id="725f7-102">Etapa 2: Adicionar e configurar registro em log</span><span class="sxs-lookup"><span data-stu-id="725f7-102">Step 2: Adding and Configuring Logging</span></span>
  <span data-ttu-id="725f7-103">Nesta tarefa, você habilitará o log do fluxo de dados no pacote Lesson 3.dtsx.</span><span class="sxs-lookup"><span data-stu-id="725f7-103">In this task, you will enable logging for the data flow in the Lesson 3.dtsx package.</span></span> <span data-ttu-id="725f7-104">Então, você configurará um provedor de log de arquivo de texto para armazenar os eventos PipelineExecutionPlan e PipelineExecuteTrees em log.</span><span class="sxs-lookup"><span data-stu-id="725f7-104">Then, you will configure a Text File log provider to log the PipelineExecutionPlan and PipelineExecuteTrees events.</span></span> <span data-ttu-id="725f7-105">O provedor de log de arquivos de texto cria logs que são fáceis exibir e transportar.</span><span class="sxs-lookup"><span data-stu-id="725f7-105">The Text Files log provider creates logs that are easy to view and easily transportable.</span></span> <span data-ttu-id="725f7-106">A simplicidade destes arquivos de log faz estes arquivos especialmente úteis durante a fase de teste básico de um pacote.</span><span class="sxs-lookup"><span data-stu-id="725f7-106">The simplicity of these log files makes these files especially useful during the basic testing phase of a package.</span></span> <span data-ttu-id="725f7-107">É possível também exibir as entradas de log na janela Eventos de Log do Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="725f7-107">You can also view the log entries in the Log Events window of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
### <a name="to-add-logging-to-the-package"></a><span data-ttu-id="725f7-108">Adicionar log ao pacote</span><span class="sxs-lookup"><span data-stu-id="725f7-108">To add logging to the package</span></span>  
  
1.  <span data-ttu-id="725f7-109">No menu **SSIS** , clique em **Registrar em Log**.</span><span class="sxs-lookup"><span data-stu-id="725f7-109">On the **SSIS** menu, click **Logging**.</span></span>  
  
2.  <span data-ttu-id="725f7-110">Na caixa de diálogo **Configurar SSIS Logs** , no painel **Contêineres** , certifique-se que o objeto mais alto, que representa o pacote Lição 3, está selecionado.</span><span class="sxs-lookup"><span data-stu-id="725f7-110">In the **Configure SSIS Logs** dialog box, in the **Containers** pane, make sure that the topmost object, which represents the Lesson 3 package, is selected.</span></span>  
  
3.  <span data-ttu-id="725f7-111">Na guia **Provedores e Logs** , na caixa **Tipo de provedor** , selecione **SSIS provedor de log para Arquivos de Texto**, e clique **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="725f7-111">On the **Providers and Logs** tab, in the **Provider type** box, select **SSIS log provider for Text files**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="725f7-112">Integration Services adiciona um novo provedor de log de arquivo de texto ao pacote com o **provedor de log SSIS de nome padrão para arquivos de texto**.</span><span class="sxs-lookup"><span data-stu-id="725f7-112">Integration Services adds a new Text File log provider to the package with the default name **SSIS log provider for text files**.</span></span> <span data-ttu-id="725f7-113">Agora é possível configurar o novo provedor de log.</span><span class="sxs-lookup"><span data-stu-id="725f7-113">You can now configure the new log provider.</span></span>  
  
4.  <span data-ttu-id="725f7-114">Na coluna **nome** , digite `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="725f7-114">In the **Name** column, type `Lesson 3 Log File`.</span></span>  
  
5.  <span data-ttu-id="725f7-115">Opcionalmente, modifique a **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="725f7-115">Optionally, modify the **Description**.</span></span>  
  
6.  <span data-ttu-id="725f7-116">Na coluna **Configuração** , clique em **\<New Connection>** para especificar o destino no qual as informações de log serão gravadas.</span><span class="sxs-lookup"><span data-stu-id="725f7-116">In the **Configuration** column, click **\<New Connection>** to specify the destination to which the log information is written.</span></span>  
  
     <span data-ttu-id="725f7-117">Na caixa de diálogo **Editor do Gerenciador de Conexões de Arquivos** , para **Tipo de uso**, selecione **Criar Arquivo**e clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="725f7-117">In the **File Connection Manager Editor** dialog box, for **Usage type**, select **Create file**, and then click **Browse**.</span></span> <span data-ttu-id="725f7-118">Por padrão, a caixa de diálogo **Selecione Arquivo** abrirá a pasta do projeto, mas você pode salvar o log em qualquer localização.</span><span class="sxs-lookup"><span data-stu-id="725f7-118">By default, the **Select File** dialog box opens the project folder, but you can save log information to any location.</span></span>  
  
7.  <span data-ttu-id="725f7-119">Na caixa de diálogo **Selecionar arquivo** , na caixa **nome do arquivo** `TutorialLog.log` , digite e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="725f7-119">In the **Select File** dialog box, in the **File name** box type `TutorialLog.log`, and click **Open**.</span></span>  
  
8.  <span data-ttu-id="725f7-120">Clique em **OK** para fechar a caixa de diálogo **Editor do Gerenciador de Conexões de Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="725f7-120">Click **OK** to close the **File Connection Manager Editor** dialog box.</span></span>  
  
9. <span data-ttu-id="725f7-121">No painel **Contêineres** , expandir todos os nós da hierarquia do contêiner do pacote, e limpe todas as caixas de seleção, inclusive a caixa de seleção **Extrair Dados de Exemplo de Moeda** .</span><span class="sxs-lookup"><span data-stu-id="725f7-121">In the **Containers** pane, expand all nodes of the package container hierarchy, and then clear all check boxes, including the **Extract Sample Currency Data** check box.</span></span> <span data-ttu-id="725f7-122">Agora marque a caixa de seleção **Extrair Dados de Exemplo de Moeda** para adquirir só os eventos para este nó.</span><span class="sxs-lookup"><span data-stu-id="725f7-122">Now select the check box for **Extract Sample Currency Data** to get only the events for this node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="725f7-123"> Se o estado da caixa de seleção **Extrair Dados de Exemplo de Moeda** estiver esmaecido ao invés de marcada, a tarefa usará as configurações de log do contêiner pai e não será possível ativar os eventos de log específicos para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="725f7-123">If the state of the **Extract Sample Currency Data** check box is dimmed instead of selected, the task uses the log settings of the parent container and you cannot enable the log events that are specific to the task.</span></span>  
  
10. <span data-ttu-id="725f7-124">Na guia **Detalhes** , na coluna **Eventos** , selecione os eventos **PipelineExecutionPlan** e **PipelineExecutionTrees** .</span><span class="sxs-lookup"><span data-stu-id="725f7-124">On the **Details** tab, in the **Events** column, select the **PipelineExecutionPlan** and **PipelineExecutionTrees** events.</span></span>  
  
11. <span data-ttu-id="725f7-125">Clique em **Avançado** para revisar os detalhes que o provedor de log escreverá no log para cada evento.</span><span class="sxs-lookup"><span data-stu-id="725f7-125">Click **Advanced** to review the details that the log provider will write to the log for each event.</span></span> <span data-ttu-id="725f7-126">Por padrão, todas as categorias de informações são selecionadas automaticamente para os eventos especificados por você.</span><span class="sxs-lookup"><span data-stu-id="725f7-126">By default, all information categories are automatically selected for the events you specify.</span></span>  
  
12. <span data-ttu-id="725f7-127">Clique em **Básico** para ocultar as categorias de informações.</span><span class="sxs-lookup"><span data-stu-id="725f7-127">Click **Basic** to hide the information categories.</span></span>  
  
13. <span data-ttu-id="725f7-128">Na guia **provedor e logs** , na coluna **nome** , selecione `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="725f7-128">On the **Provider and Logs** tab, in the **Name** column, select `Lesson 3 Log File`.</span></span> <span data-ttu-id="725f7-129">Assim que tiver criado um provedor de log para seu pacote, poderá, como opção, retirar a seleção para temporariamente desligar o registro em log, sem ter que excluir e recriar o provedor de log.</span><span class="sxs-lookup"><span data-stu-id="725f7-129">Once you have created a log provider for your package, you can optionally deselect it to temporarily turn off logging, without having to delete and re-create a log provider.</span></span>  
  
14. <span data-ttu-id="725f7-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="725f7-130">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="725f7-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="725f7-131">Next Steps</span></span>  
 [<span data-ttu-id="725f7-132">Etapa 3: Testar o pacote de tutorial da Lição 3</span><span class="sxs-lookup"><span data-stu-id="725f7-132">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
  
