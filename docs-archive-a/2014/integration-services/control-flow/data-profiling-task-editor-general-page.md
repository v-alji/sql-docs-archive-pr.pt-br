---
title: Editor da tarefa Criação de Perfil de Dados (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataprofilingtask.general.f1
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: eec15906-d757-4079-b2f6-aca4e52b3b4c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cfcdf472f817d3dd688a5f867ac74d46835ab91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575268"
---
# <a name="data-profiling-task-editor-general-page"></a><span data-ttu-id="07b91-102">Editor da tarefa Criação de Perfil de Dados (página Geral)</span><span class="sxs-lookup"><span data-stu-id="07b91-102">Data Profiling Task Editor (General Page)</span></span>
  <span data-ttu-id="07b91-103">Use a página **Geral** do **Editor da Tarefa Criação de Perfil de Dados** para configurar as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="07b91-103">Use the **General** page of the **Data Profiling Task Editor** to configure the following options:</span></span>  
  
-   <span data-ttu-id="07b91-104">Especifique o destino do perfil de saída.</span><span class="sxs-lookup"><span data-stu-id="07b91-104">Specify the destination for the profile output.</span></span>  
  
-   <span data-ttu-id="07b91-105">Use as configurações padrão para simplificar a tarefa de criar um perfil para uma única tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="07b91-105">Use the default settings to simplify the task of profiling a single table or view.</span></span>  
  
 <span data-ttu-id="07b91-106">Para obter mais informações sobre como usar a Tarefa Criação de Perfil de Dados, consulte [Configuração da Tarefa Criação de Perfil de Dados](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="07b91-106">For more information about how to use the Data Profiling task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="07b91-107">Para obter mais informações sobre como usar o Visualizador de Perfil de Dados para analisar a saída da Tarefa Criação de Perfil de Dados, consulte [Visualizador de Perfil de Dados](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="07b91-107">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
 <span data-ttu-id="07b91-108">**Para abrir a página Geral do Editor da Tarefa de Criação de Perfil de Dados**</span><span class="sxs-lookup"><span data-stu-id="07b91-108">**To open the General page of the Data Profiling Task Editor**</span></span>  
  
1.  <span data-ttu-id="07b91-109">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="07b91-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that has the Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="07b91-110">Na guia **Fluxo de Controle** , clique duas vezes na tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="07b91-110">On the **Control Flow** tab, double-click the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="07b91-111">No **Editor da Tarefa Criação de Perfil de Dados**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="07b91-111">In the **Data Profiling Task Editor**, click **General**.</span></span>  
  
## <a name="data-profiling-options"></a><span data-ttu-id="07b91-112">Opções de Criação de Perfil de Dados</span><span class="sxs-lookup"><span data-stu-id="07b91-112">Data Profiling Options</span></span>  
 <span data-ttu-id="07b91-113">**Tempo Limite**</span><span class="sxs-lookup"><span data-stu-id="07b91-113">**Timeout**</span></span>  
 <span data-ttu-id="07b91-114">Especifique o número de segundos após o qual a tarefa Criação de Perfil de Dados deve alcançar o tempo limite e interromper a execução.</span><span class="sxs-lookup"><span data-stu-id="07b91-114">Specify the number of seconds after which the Data Profiling task should timeout and stop running.</span></span> <span data-ttu-id="07b91-115">O valor padrão é 0, que não indica nenhum tempo limite.</span><span class="sxs-lookup"><span data-stu-id="07b91-115">The default value is 0, which indicates no timeout.</span></span>  
  
## <a name="destination-options"></a><span data-ttu-id="07b91-116">Opções de destino</span><span class="sxs-lookup"><span data-stu-id="07b91-116">Destination Options</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="07b91-117">O arquivo de saída pode conter dados confidenciais sobre seu banco de dados e os dados contidos no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="07b91-117">The output file might contain sensitive data about your database and the data that database contains.</span></span> <span data-ttu-id="07b91-118">Para obter sugestões sobre como tornar esse arquivo mais seguro, consulte [Acesso aos arquivos usados por pacotes](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="07b91-118">For suggestions about how to make this file more secure, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="07b91-119">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="07b91-119">**DestinationType**</span></span>  
 <span data-ttu-id="07b91-120">Especifique se deseja salvar a saída do perfil de dados para um arquivo ou uma variável:</span><span class="sxs-lookup"><span data-stu-id="07b91-120">Specify whether to save the data profile output to a file or a variable:</span></span>  
  
|<span data-ttu-id="07b91-121">Valor</span><span class="sxs-lookup"><span data-stu-id="07b91-121">Value</span></span>|<span data-ttu-id="07b91-122">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="07b91-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="07b91-123">**FileConnection**</span><span class="sxs-lookup"><span data-stu-id="07b91-123">**FileConnection**</span></span>|<span data-ttu-id="07b91-124">Salve o perfil produzido em um arquivo no local especificado em um gerenciador de conexões do Arquivo.</span><span class="sxs-lookup"><span data-stu-id="07b91-124">Save the profile output to a file in the location that is specified in a File connection manager.</span></span><br /><br /> <span data-ttu-id="07b91-125">Observação: especifique qual gerenciador de conexões do Arquivo deve ser usado na opção **Destino** .</span><span class="sxs-lookup"><span data-stu-id="07b91-125">Note: You specify which File connection manager to use in the **Destination** option.</span></span>|  
|<span data-ttu-id="07b91-126">**Variável**</span><span class="sxs-lookup"><span data-stu-id="07b91-126">**Variable**</span></span>|<span data-ttu-id="07b91-127">Salve a saída do perfil em uma variável de pacote.</span><span class="sxs-lookup"><span data-stu-id="07b91-127">Save the profile output to a package variable.</span></span><br /><br /> <span data-ttu-id="07b91-128">Observação: especifique qual variável de pacote deve ser usada na opção **Destino** .</span><span class="sxs-lookup"><span data-stu-id="07b91-128">Note: You specify which package variable to use in the **Destination** option.</span></span>|  
  
 <span data-ttu-id="07b91-129">**Destino**</span><span class="sxs-lookup"><span data-stu-id="07b91-129">**Destination**</span></span>  
 <span data-ttu-id="07b91-130">Especifique qual gerenciador de conexões do Arquivo ou variável de pacote contém a saída do perfil de dados:</span><span class="sxs-lookup"><span data-stu-id="07b91-130">Specify which File connection manager or package variable contains the data profile output:</span></span>  
  
-   <span data-ttu-id="07b91-131">Se a opção **DestinationType** for definida como **FileConnection**, a opção **Destino** exibirá os gerenciadores de conexões do Arquivo disponíveis.</span><span class="sxs-lookup"><span data-stu-id="07b91-131">If the **DestinationType** option is set to **FileConnection**, the **Destination** option displays the available File connection managers.</span></span> <span data-ttu-id="07b91-132">Selecione um desses gerenciadores de conexões ou selecione \<New File connection> para criar um gerenciador de conexões de Arquivo.</span><span class="sxs-lookup"><span data-stu-id="07b91-132">Select one of these connection managers, or select \<New File connection> to create a new File connection manager.</span></span>  
  
-   <span data-ttu-id="07b91-133">Se a opção **DestinationType** for definida como **Variável**, a opção **Destino** exibirá as variáveis de pacote disponíveis na lista **Destino** .</span><span class="sxs-lookup"><span data-stu-id="07b91-133">If the **DestinationType** option is set to **Variable**, the **Destination** option displays the available package variables in the **Destination** list.</span></span> <span data-ttu-id="07b91-134">Selecione uma dessas variáveis ou selecione \<New Variable> para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="07b91-134">Select one of these variables, or select \<New Variable> to create a new variable.</span></span>  
  
 <span data-ttu-id="07b91-135">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="07b91-135">**OverwriteDestination**</span></span>  
 <span data-ttu-id="07b91-136">Especifique se deseja substituir o arquivo de saída, se este já existir.</span><span class="sxs-lookup"><span data-stu-id="07b91-136">Specify whether to overwrite the output file if it already exists.</span></span> <span data-ttu-id="07b91-137">O valor padrão é **Falso**.</span><span class="sxs-lookup"><span data-stu-id="07b91-137">The default value is **False**.</span></span> <span data-ttu-id="07b91-138">O valor desta propriedade é usado somente quando a opção DestinationType for definida como FileConnection.</span><span class="sxs-lookup"><span data-stu-id="07b91-138">The value of this property is used only when the DestinationType option is set to FileConnection.</span></span> <span data-ttu-id="07b91-139">Quando a opção DestinationType é definida como Variável, a tarefa sempre substitui o valor anterior da variável.</span><span class="sxs-lookup"><span data-stu-id="07b91-139">When the DestinationType option is set to Variable, the task always overwrites the previous value of the variable.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="07b91-140">Se tentar executar a tarefa Criação de Perfil de Dados mais de uma vez sem alterar o nome do arquivo de saída ou alterar o valor da propriedade **OverwriteDestination** para **True**, a tarefa falhará, exibindo uma mensagem que informa que o arquivo de saída já existe.</span><span class="sxs-lookup"><span data-stu-id="07b91-140">If you try to run the Data Profiling task more than once without changing the output file name or changing the value of the **OverwriteDestination** property to **True**, the task fails with the message that the output file already exists.</span></span>  
  
## <a name="other-options"></a><span data-ttu-id="07b91-141">Outras opções</span><span class="sxs-lookup"><span data-stu-id="07b91-141">Other Options</span></span>  
 <span data-ttu-id="07b91-142">**Perfil Rápido**</span><span class="sxs-lookup"><span data-stu-id="07b91-142">**Quick Profile**</span></span>  
 <span data-ttu-id="07b91-143">Exibe o **Formulário de Perfil Rápido de Tabela Única**.</span><span class="sxs-lookup"><span data-stu-id="07b91-143">Display the **Single Table Quick Profile Form**.</span></span> <span data-ttu-id="07b91-144">Este formulário simplifica a tarefa de criação de perfil de uma tabela ou exibição única usando configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="07b91-144">This form simplifies the task of profiling a single table or view by using default settings.</span></span> <span data-ttu-id="07b91-145">Para obter mais informações, consulte [Formulário de Perfil Rápido de Tabela Única &#40;Tarefa Criação de Perfil de Dados&#41;](single-table-quick-profile-form-data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="07b91-145">For more information, see [Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md).</span></span>  
  
 <span data-ttu-id="07b91-146">**Abrir o Visualizador de Perfil**</span><span class="sxs-lookup"><span data-stu-id="07b91-146">**Open Profile Viewer**</span></span>  
 <span data-ttu-id="07b91-147">Abra o Visualizador de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="07b91-147">Opens the Data Profile Viewer.</span></span> <span data-ttu-id="07b91-148">O visualizador de Perfil de Dados autônomo exibe a saída de perfil de dados da tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="07b91-148">The stand-alone Data Profile Viewer displays data profile output from the Data Profiling task.</span></span> <span data-ttu-id="07b91-149">A saída do perfil de dados pode ser exibida após a execução da tarefa Criação de Perfil de Dados no pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] e a computação de perfis de dados.</span><span class="sxs-lookup"><span data-stu-id="07b91-149">You can view the data profile output after you have run the Data Profiling task inside the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package and computed the data profiles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07b91-150">Você também pode abrir o Visualizador de Perfil de Dados executando o DataProfileViewer.exe na pasta *\<drive>* :\Arquivos de Programas (x86) | Arquivos de Programas\Microsoft SQL Server\110\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="07b91-150">You can also open the Data Profile Viewer by running the DataProfileViewer.exe in the folder, *\<drive>*:\Program Files (x86) | Program Files\Microsoft SQL Server\110\DTS\Binn.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07b91-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="07b91-151">See Also</span></span>  
 <span data-ttu-id="07b91-152">[Formulário de Perfil Rápido de Tabela Única &#40;Tarefa Criação de Perfil de Dados&#41;](single-table-quick-profile-form-data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="07b91-152">[Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md) </span></span>  
 [<span data-ttu-id="07b91-153">Editor da tarefa Criação de Perfil de Dados &#40;Página Solicitações de Perfil&#41;</span><span class="sxs-lookup"><span data-stu-id="07b91-153">Data Profiling Task Editor &#40;Profile Requests Page&#41;</span></span>](data-profiling-task-editor-profile-requests-page.md)  
  
  
