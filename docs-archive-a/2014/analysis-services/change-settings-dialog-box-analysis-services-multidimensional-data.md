---
title: Caixa de diálogo Alterar configurações (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.batchsettingsdialog.f1
ms.assetid: 0041e042-d7ce-48f9-a690-a6dc65471ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2649195e3aff4e17d378e54c4b1d656361dfe3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571710"
---
# <a name="change-settings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="7721e-102">Caixa de diálogo Alterar Configurações (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="7721e-102">Change Settings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="7721e-103">Use a caixa de diálogo **Alterar Configurações** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para alterar as configurações que governam o processamento de objetos listados na caixa de diálogo **Processo** .</span><span class="sxs-lookup"><span data-stu-id="7721e-103">Use the **Change Settings** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to change the settings that govern the processing of objects listed in the **Process** dialog box.</span></span> <span data-ttu-id="7721e-104">É possível exibir a caixa de diálogo **Alterar Configurações** clicando em **Alterar Configurações** na caixa de diálogo **Processar** .</span><span class="sxs-lookup"><span data-stu-id="7721e-104">You can display the **Change Settings** dialog box by clicking **Change Settings** on the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7721e-105"> As configurações especificadas nessa caixa de diálogo substituem as configurações herdadas do banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dos objetos listados na caixa de diálogo **Processar** .</span><span class="sxs-lookup"><span data-stu-id="7721e-105">Settings specified in this dialog box override default settings inherited from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database for the objects listed in the **Process** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7721e-106">Opções</span><span class="sxs-lookup"><span data-stu-id="7721e-106">Options</span></span>  
 <span data-ttu-id="7721e-107">**Opções de processamento**</span><span class="sxs-lookup"><span data-stu-id="7721e-107">**Processing options**</span></span>  
 <span data-ttu-id="7721e-108">Use essa guia para modificar configurações relacionadas à ordem de processamento, à tabela de write-back e aos objetos afetados para a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-108">Use this tab to modify settings related to the processing order, writeback table, and affected objects for the processing operation.</span></span> <span data-ttu-id="7721e-109">A guia contém as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7721e-109">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="7721e-110">**Parallel**</span><span class="sxs-lookup"><span data-stu-id="7721e-110">**Parallel**</span></span>  
 <span data-ttu-id="7721e-111">Clique para processar os objetos em paralelo.</span><span class="sxs-lookup"><span data-stu-id="7721e-111">Click to process the objects in parallel.</span></span>  
  
 <span data-ttu-id="7721e-112">**Máximo de tarefas paralelas**</span><span class="sxs-lookup"><span data-stu-id="7721e-112">**Maximum parallel tasks**</span></span>  
 <span data-ttu-id="7721e-113">Selecione o número máximo de tarefas a serem executadas em paralelo pela operação de processamento ou escolha **Deixar o servidor decidir** para permitir que o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] selecione um número ideal de tarefas paralelas.</span><span class="sxs-lookup"><span data-stu-id="7721e-113">Select the maximum number of tasks to execute in parallel by the processing operation, or choose **Let the server decide** to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to select an optimal number of parallel tasks.</span></span>  
  
 <span data-ttu-id="7721e-114">**Sequencial**</span><span class="sxs-lookup"><span data-stu-id="7721e-114">**Sequential**</span></span>  
 <span data-ttu-id="7721e-115">Clique para processar os objetos sequencialmente.</span><span class="sxs-lookup"><span data-stu-id="7721e-115">Click to process the objects sequentially.</span></span>  
  
 <span data-ttu-id="7721e-116">**Modo de transação**</span><span class="sxs-lookup"><span data-stu-id="7721e-116">**Transaction mode**</span></span>  
 <span data-ttu-id="7721e-117">Escolha o modo de transação usado quando os objetos são processados em ordem sequencial:</span><span class="sxs-lookup"><span data-stu-id="7721e-117">Choose the transaction mode that is used when objects are processed in sequential order:</span></span>  
  
-   <span data-ttu-id="7721e-118">**Uma Transação** processa todos os objetos na mesma transação.</span><span class="sxs-lookup"><span data-stu-id="7721e-118">**One Transaction** processes all objects in the same transaction.</span></span>  
  
-   <span data-ttu-id="7721e-119">**Separar Transações** processa todos os objetos, inclusive objetos dependentes, em transações separadas.</span><span class="sxs-lookup"><span data-stu-id="7721e-119">**Separate Transactions** processes all objects, including dependent objects, in separate transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7721e-120"> Essa opção estará habilitada apenas se a opção **Sequencial** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="7721e-120">This option is enabled only if **Sequential** is selected.</span></span>  
  
 <span data-ttu-id="7721e-121">**Opção de tabela de write-back**</span><span class="sxs-lookup"><span data-stu-id="7721e-121">**Writeback table option**</span></span>  
 <span data-ttu-id="7721e-122">Escolha a opção usada para gerenciar uma tabela de write-back:</span><span class="sxs-lookup"><span data-stu-id="7721e-122">Choose the option used to manage a writeback table:</span></span>  
  
-   <span data-ttu-id="7721e-123">**Criar** criará uma tabela de write-back se ela não existir.</span><span class="sxs-lookup"><span data-stu-id="7721e-123">**Create** creates a writeback table if it does not exist.</span></span> <span data-ttu-id="7721e-124">Ocorrerá um erro se uma tabela write-back já existir.</span><span class="sxs-lookup"><span data-stu-id="7721e-124">An error occurs if a writeback table already exists.</span></span>  
  
-   <span data-ttu-id="7721e-125">**Criar sempre** cria uma tabela write-back se ela não existir ou substitui a tabela write-back existente se ela já existir.</span><span class="sxs-lookup"><span data-stu-id="7721e-125">**Create always** creates a writeback table if it does not exist, or overwrites the existing writeback table if it does exist.</span></span>  
  
-   <span data-ttu-id="7721e-126">**Usar existente** usará a tabela de write-back existente se ela já existir.</span><span class="sxs-lookup"><span data-stu-id="7721e-126">**Use existing** uses the existing writeback table if it exists.</span></span> <span data-ttu-id="7721e-127">Ocorrerá um erro se uma tabela write-back não existir.</span><span class="sxs-lookup"><span data-stu-id="7721e-127">An error occurs if a writeback table does not exist.</span></span>  
  
 <span data-ttu-id="7721e-128">**Objetos afetados pelo processo**</span><span class="sxs-lookup"><span data-stu-id="7721e-128">**Process affected objects**</span></span>  
 <span data-ttu-id="7721e-129">Selecione para incluir e processar objetos que dependem de objetos incluídos na operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-129">Select to include and process objects that depend on objects included in the processing operation.</span></span>  
  
 <span data-ttu-id="7721e-130">**Erros de chave de dimensão**</span><span class="sxs-lookup"><span data-stu-id="7721e-130">**Dimension key errors**</span></span>  
 <span data-ttu-id="7721e-131">Use essa guia para modificar configurações relacionadas à configuração de erros da operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-131">Use this tab to modify settings related to the error configuration for the processing operation.</span></span> <span data-ttu-id="7721e-132">A guia contém as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7721e-132">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="7721e-133">**Usar configuração de erro padrão**</span><span class="sxs-lookup"><span data-stu-id="7721e-133">**Use default error configuration**</span></span>  
 <span data-ttu-id="7721e-134">Selecione para usar a configuração de erro padrão para objetos na operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-134">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="7721e-135">**Usar configuração de erro personalizada**</span><span class="sxs-lookup"><span data-stu-id="7721e-135">**Use custom error configuration**</span></span>  
 <span data-ttu-id="7721e-136">Selecione para definir a configuração de erro para objetos na operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-136">Select to define the error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="7721e-137">**Ação de erro de chave**</span><span class="sxs-lookup"><span data-stu-id="7721e-137">**Key error action**</span></span>  
 <span data-ttu-id="7721e-138">Escolha uma das seguintes ações que ocorrem quando uma nova chave é encontrada durante processamento que não pode ser pesquisado:</span><span class="sxs-lookup"><span data-stu-id="7721e-138">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="7721e-139">**Converter em desconhecido** agrega as informações do registro ao membro desconhecido.</span><span class="sxs-lookup"><span data-stu-id="7721e-139">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="7721e-140">**Descartar registro** exclui a informações do registro para que não sejam processadas com o objeto.</span><span class="sxs-lookup"><span data-stu-id="7721e-140">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="7721e-141">**Ignorar contagem de erros**</span><span class="sxs-lookup"><span data-stu-id="7721e-141">**Ignore errors count**</span></span>  
 <span data-ttu-id="7721e-142">Clique para ignorar quaisquer erros ocorridos durante o processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-142">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="7721e-143">**Parar se houver erro**</span><span class="sxs-lookup"><span data-stu-id="7721e-143">**Stop on error**</span></span>  
 <span data-ttu-id="7721e-144">Clique para interromper o processamento quando ocorrerem erros.</span><span class="sxs-lookup"><span data-stu-id="7721e-144">Click to stop processing when errors occur.</span></span> <span data-ttu-id="7721e-145">Essa opção habilita as opções **Número de erros** e **Ação se houver erro** .</span><span class="sxs-lookup"><span data-stu-id="7721e-145">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="7721e-146">**Número de erros**</span><span class="sxs-lookup"><span data-stu-id="7721e-146">**Number of errors**</span></span>  
 <span data-ttu-id="7721e-147">Digite o número de erros que são ignorados antes do processamento ser encerrado.</span><span class="sxs-lookup"><span data-stu-id="7721e-147">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="7721e-148">**Ação se houver erro**</span><span class="sxs-lookup"><span data-stu-id="7721e-148">**On error action**</span></span>  
 <span data-ttu-id="7721e-149">Escolha uma das seguintes ações a serem executadas quando o número de erros exceder o valor em **Número de erros**:</span><span class="sxs-lookup"><span data-stu-id="7721e-149">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="7721e-150">**Parar processamento** encerra a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-150">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="7721e-151">**Parar log** para o log de erros, mas continua a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-151">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="7721e-152">**Chave não encontrada**</span><span class="sxs-lookup"><span data-stu-id="7721e-152">**Key not found**</span></span>  
 <span data-ttu-id="7721e-153">Especifique uma das seguintes ações a ser executada quando uma chave não for localizada quando um objeto for processado:</span><span class="sxs-lookup"><span data-stu-id="7721e-153">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="7721e-154">**Ignorar erro** ignora o erro.</span><span class="sxs-lookup"><span data-stu-id="7721e-154">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="7721e-155">**Relatar e continuar** relata o erro e continua a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-155">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="7721e-156">**Relatar e parar** relata o erro e para a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-156">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="7721e-157">**Chave duplicada**</span><span class="sxs-lookup"><span data-stu-id="7721e-157">**Duplicate key**</span></span>  
 <span data-ttu-id="7721e-158">Especifique uma das seguintes ações a ser executada se uma chave duplicada for localizada quando um objeto for processado:</span><span class="sxs-lookup"><span data-stu-id="7721e-158">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="7721e-159">**Ignorar erro** ignora o erro.</span><span class="sxs-lookup"><span data-stu-id="7721e-159">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="7721e-160">**Relatar e continuar** relata o erro e continua a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-160">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="7721e-161">**Relatar e parar** relata o erro e para a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-161">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="7721e-162">**Chave nula convertida em desconhecida**</span><span class="sxs-lookup"><span data-stu-id="7721e-162">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="7721e-163">Especifique uma das seguintes ações a ser executada quando uma chave de membro nula for adicionada ao membro desconhecido quando um objeto for processado:</span><span class="sxs-lookup"><span data-stu-id="7721e-163">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed:</span></span>  
  
-   <span data-ttu-id="7721e-164">**Ignorar erro** ignora o erro.</span><span class="sxs-lookup"><span data-stu-id="7721e-164">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="7721e-165">**Relatar e continuar** relata o erro e continua a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-165">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="7721e-166">**Relatar e parar** relata o erro e para a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-166">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="7721e-167">**Chave nula não permitida**</span><span class="sxs-lookup"><span data-stu-id="7721e-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="7721e-168">Especifique uma das seguintes ações a ser executada quando uma chave nula for localizada, mas não for permitida, quando um objeto for processado:</span><span class="sxs-lookup"><span data-stu-id="7721e-168">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed:</span></span>  
  
-   <span data-ttu-id="7721e-169">**Ignorar erro** ignora o erro.</span><span class="sxs-lookup"><span data-stu-id="7721e-169">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="7721e-170">**Relatar e continuar** relata o erro e continua a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-170">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="7721e-171">**Relatar e parar** relata o erro e para a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="7721e-171">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="7721e-172">**Caminho do log de erros**</span><span class="sxs-lookup"><span data-stu-id="7721e-172">**Error log path**</span></span>  
 <span data-ttu-id="7721e-173">Digite o caminho completo e nome do arquivo de log de erros.</span><span class="sxs-lookup"><span data-stu-id="7721e-173">Type the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="7721e-174">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="7721e-174">**Browse**</span></span>  
 <span data-ttu-id="7721e-175">Clique para abrir a caixa de diálogo **Abrir** e selecionar o caminho completo e o nome do arquivo de log de erros.</span><span class="sxs-lookup"><span data-stu-id="7721e-175">Click to open the **Open** dialog box and select the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="7721e-176">**Objetos afetados pelo processo**</span><span class="sxs-lookup"><span data-stu-id="7721e-176">**Process affected objects**</span></span>  
 <span data-ttu-id="7721e-177">Clique para processar os objetos que têm uma dependência dos objetos selecionados na caixa de diálogo **Processar** .</span><span class="sxs-lookup"><span data-stu-id="7721e-177">Click to process the objects that have a dependency on the objects selected in the **Process** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7721e-178">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7721e-178">See Also</span></span>  
 <span data-ttu-id="7721e-179">[Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7721e-179">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="7721e-180">Caixa de diálogo processo &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="7721e-180">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
