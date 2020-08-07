---
title: Caixa de diálogo Executar Pacote | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageexecute.f1
- sql12.ssis.ssms.executepackage.f1
ms.assetid: 4f7a806d-4867-4d1f-bc65-b00c1caee7b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b60381054c781cd59f0a9d434710663b72d616c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574802"
---
# <a name="execute-package-dialog-box"></a><span data-ttu-id="0adfc-102">Execute Package Dialog Box</span><span class="sxs-lookup"><span data-stu-id="0adfc-102">Execute Package Dialog Box</span></span>
  <span data-ttu-id="0adfc-103">Use a caixa de diálogo **Executar Pacote** para executar um pacote armazenado no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0adfc-103">Use the **Execute Package** dialog box to run a package that is stored on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="0adfc-104">Um pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] pode conter parâmetros com valores armazenados em variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="0adfc-104">An [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package may contain parameters that values stored in environment variables.</span></span> <span data-ttu-id="0adfc-105">Antes de executar esse tipo de pacote, você deve especificar qual ambiente será usado para fornecer os valores de variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="0adfc-105">Before executing such a package, you must specify which environment will be used to provide the environment variable values.</span></span> <span data-ttu-id="0adfc-106">Um projeto pode conter vários ambientes, mas só um ambiente pode ser usado para associar valores de variável de ambiente no momento da execução.</span><span class="sxs-lookup"><span data-stu-id="0adfc-106">A project may contain multiple environments, but only one environment can be used for binding environment variable values at the time of execution.</span></span> <span data-ttu-id="0adfc-107">Se nenhuma variável de ambiente for usada no pacote, nenhum ambiente será necessário.</span><span class="sxs-lookup"><span data-stu-id="0adfc-107">If no environment variables are used in the package, an environment is not required.</span></span>  
  
 <span data-ttu-id="0adfc-108">O que você deseja fazer?</span><span class="sxs-lookup"><span data-stu-id="0adfc-108">What do you want to do?</span></span>  
  
-   [<span data-ttu-id="0adfc-109">Abrir a caixa de diálogo Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="0adfc-109">Open the Execute Package dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="0adfc-110">Definir as opções na página Geral</span><span class="sxs-lookup"><span data-stu-id="0adfc-110">Set the Options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="0adfc-111">Definir as opções na guia Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0adfc-111">Set the Options on the Parameters tab</span></span>](#parameters)  
  
-   [<span data-ttu-id="0adfc-112">Definir as opções na guia de Gerenciadores de Conexões</span><span class="sxs-lookup"><span data-stu-id="0adfc-112">Set the Options on the Connection Managers tab</span></span>](#connection)  
  
-   [<span data-ttu-id="0adfc-113">Definir as opções na guia Avançado</span><span class="sxs-lookup"><span data-stu-id="0adfc-113">Set the Options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="0adfc-114">Criando scripts para as opções na caixa de diálogo Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="0adfc-114">Scripting the Options in the Execute Package Dialog Box</span></span>](#script)  
  
##  <a name="open-the-execute-package-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="0adfc-115">Abrir a caixa de diálogo Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="0adfc-115">Open the Execute Package dialog box</span></span>  
  
1.  <span data-ttu-id="0adfc-116">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], conecte-se ao servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0adfc-116">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="0adfc-117">Você está se conectando à instância do [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] que hospeda o banco de dados SSISDB.</span><span class="sxs-lookup"><span data-stu-id="0adfc-117">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="0adfc-118">Em Pesquisador de Objetos, expanda a árvore para exibir o nó **Catálogos do Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="0adfc-118">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="0adfc-119">Expanda o nó **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="0adfc-119">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="0adfc-120">Expanda a pasta que contém o pacote que você deseja executar.</span><span class="sxs-lookup"><span data-stu-id="0adfc-120">Expand the folder that contains the package you want to run.</span></span>  
  
5.  <span data-ttu-id="0adfc-121">Clique com o botão direito do mouse no pacote e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="0adfc-121">Right-click the package, and then click **Execute**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="0adfc-122">Definir as opções na página Geral</span><span class="sxs-lookup"><span data-stu-id="0adfc-122">Set the Options on the General page</span></span>  
 <span data-ttu-id="0adfc-123">Selecione **Ambiente** para especificar o ambiente aplicado com o pacote executado.</span><span class="sxs-lookup"><span data-stu-id="0adfc-123">Select **Environment** to specify the environment that is applied with the package is run.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-tab"></a><a name="parameters"></a> <span data-ttu-id="0adfc-124">Definir as opções na guia Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0adfc-124">Set the Options on the Parameters tab</span></span>  
 <span data-ttu-id="0adfc-125">Use a guia **Parâmetros** para modificar os valores de parâmetros usados quando o pacote for executado.</span><span class="sxs-lookup"><span data-stu-id="0adfc-125">Use the **Parameters** tab to modify the parameter values that are used when the package runs.</span></span>  
  
##  <a name="set-the-options-on-the-connection-managers-tab"></a><a name="connection"></a> <span data-ttu-id="0adfc-126">Definir as opções na guia de Gerenciadores de Conexões</span><span class="sxs-lookup"><span data-stu-id="0adfc-126">Set the Options on the Connection Managers tab</span></span>  
 <span data-ttu-id="0adfc-127">Use a guia Gerenciadores de Conexões para definir as propriedades dos gerenciadores de conexões do pacote.</span><span class="sxs-lookup"><span data-stu-id="0adfc-127">Use the Connection Managers tab to set the properties of the package connection manager(s).</span></span>  
  
##  <a name="set-the-options-on-the-advanced-tab"></a><a name="advanced"></a> <span data-ttu-id="0adfc-128">Definir as opções na guia Avançado</span><span class="sxs-lookup"><span data-stu-id="0adfc-128">Set the Options on the Advanced tab</span></span>  
 <span data-ttu-id="0adfc-129">Use a guia Avançado para gerenciar propriedades e outras configurações de pacote.</span><span class="sxs-lookup"><span data-stu-id="0adfc-129">Use the Advanced tab to manage properties and other package settings.</span></span>  
  
 <span data-ttu-id="0adfc-130">**Adicionar**, **Editar**, **Remover**</span><span class="sxs-lookup"><span data-stu-id="0adfc-130">**Add**, **Edit**, **Remove**</span></span>  
 <span data-ttu-id="0adfc-131">Clique para adicionar, editar ou remover uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="0adfc-131">Click to add, edit, or remove a property.</span></span>  
  
 <span data-ttu-id="0adfc-132">**Nível de log**</span><span class="sxs-lookup"><span data-stu-id="0adfc-132">**Logging level**</span></span>  
 <span data-ttu-id="0adfc-133">Selecione o nível de log para a execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="0adfc-133">Select the logging level for the package execution.</span></span> <span data-ttu-id="0adfc-134">Para obter mais informações, consulte [catalog.set_execution_parameter_value &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="0adfc-134">For more information, see [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span></span>  
  
 <span data-ttu-id="0adfc-135">**Despejar quando ocorrerem erros**</span><span class="sxs-lookup"><span data-stu-id="0adfc-135">**Dump on errors**</span></span>  
 <span data-ttu-id="0adfc-136">Especifique se um arquivo de despejo será criado quando ocorrerem erros durante a execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="0adfc-136">Specify whether a dump file is created when errors occur during the package execution.</span></span> <span data-ttu-id="0adfc-137">Para obter mais informações, consulte [Generating Dump Files for Package Execution](troubleshooting/generating-dump-files-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="0adfc-137">For more information, see [Generating Dump Files for Package Execution](troubleshooting/generating-dump-files-for-package-execution.md).</span></span>  
  
 <span data-ttu-id="0adfc-138">**runtime de 32 bits**</span><span class="sxs-lookup"><span data-stu-id="0adfc-138">**32-bit runtime**</span></span>  
 <span data-ttu-id="0adfc-139">Especifique se o pacote será executado em um sistema de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="0adfc-139">Specify that the package will execute on a 32-bit system.</span></span>  
  
##  <a name="scripting-the-options-in-the-execute-package-dialog-box"></a><a name="script"></a> <span data-ttu-id="0adfc-140">Criando scripts para as opções na caixa de diálogo Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="0adfc-140">Scripting the Options in the Execute Package Dialog Box</span></span>  
 <span data-ttu-id="0adfc-141">Enquanto estiver na caixa de diálogo **Executar Pacote** , você também poderá usar o botão **Script** na barra de ferramentas para gravar o código [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0adfc-141">While you are in the **Execute Package** dialog box, you can also use the **Script** button on the toolbar to write [!INCLUDE[tsql](../includes/tsql-md.md)] code for you.</span></span> <span data-ttu-id="0adfc-142">O script gerado chama os procedimentos armazenados [catalog.start_execution &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) com as mesmas opções selecionadas na caixa de diálogo **Executar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="0adfc-142">The generated script calls the stored procedures [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) with the same options that you have selected in the **Execute Package** dialog box.</span></span> <span data-ttu-id="0adfc-143">O script aparece em uma nova janela de script no [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0adfc-143">The script appears in a new script window in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
  
