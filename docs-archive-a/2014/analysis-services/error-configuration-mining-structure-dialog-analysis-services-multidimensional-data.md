---
title: Configuração de erro (caixa de diálogo estrutura de mineração) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.miningstructuredialog.general.f1
ms.assetid: d9aa028b-bad9-49c7-a81c-c2150e4dd481
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5eb41da36400271a9b058ecf275d26bd22d3ee53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583873"
---
# <a name="error-configuration-mining-structure-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="d072c-102">Configuração de Erros (Caixa de diálogo Estrutura de Mineração) (Analysis Services – Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="d072c-102">Error Configuration (Mining Structure Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d072c-103">Utilize a página **Configuração de Erros** da caixa de diálogo **Propriedades da Estrutura de Mineração** no **SQL Server Management Studio** para definir as propriedades de configuração de erros de uma estrutura de mineração em um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d072c-103">Use the **Error Configuration** page of the **Mining Structure Properties** dialog box in **SQL Server Management Studio** to set the error configuration properties of a mining structure in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d072c-104">Opções</span><span class="sxs-lookup"><span data-stu-id="d072c-104">Options</span></span>  
 <span data-ttu-id="d072c-105">**Usar configuração de erro padrão**</span><span class="sxs-lookup"><span data-stu-id="d072c-105">**Use default error configuration**</span></span>  
 <span data-ttu-id="d072c-106">Selecione para usar a configuração de erro padrão para objetos na operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-106">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="d072c-107">**Ação de erro de chave**</span><span class="sxs-lookup"><span data-stu-id="d072c-107">**Key error action**</span></span>  
 <span data-ttu-id="d072c-108">Escolha uma das seguintes ações que ocorrem quando uma nova chave é encontrada durante processamento que não pode ser pesquisado:</span><span class="sxs-lookup"><span data-stu-id="d072c-108">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="d072c-109">**Converter em desconhecido** agrega as informações do registro ao membro desconhecido.</span><span class="sxs-lookup"><span data-stu-id="d072c-109">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="d072c-110">**Descartar registro** exclui a informações do registro para que não sejam processadas com o objeto.</span><span class="sxs-lookup"><span data-stu-id="d072c-110">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="d072c-111">**Ignorar contagem de erros**</span><span class="sxs-lookup"><span data-stu-id="d072c-111">**Ignore errors count**</span></span>  
 <span data-ttu-id="d072c-112">Clique para ignorar quaisquer erros ocorridos durante o processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-112">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="d072c-113">**Parar se houver erro**</span><span class="sxs-lookup"><span data-stu-id="d072c-113">**Stop on error**</span></span>  
 <span data-ttu-id="d072c-114">Clique para interromper o processamento quando ocorrerem erros.</span><span class="sxs-lookup"><span data-stu-id="d072c-114">Click to stop processing when errors occur.</span></span> <span data-ttu-id="d072c-115">Essa opção habilita as opções **Número de erros** e **Ação se houver erro** .</span><span class="sxs-lookup"><span data-stu-id="d072c-115">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="d072c-116">**Número de erros**</span><span class="sxs-lookup"><span data-stu-id="d072c-116">**Number of errors**</span></span>  
 <span data-ttu-id="d072c-117">Digite o número de erros que são ignorados antes do processamento ser encerrado.</span><span class="sxs-lookup"><span data-stu-id="d072c-117">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="d072c-118">**Ação se houver erro**</span><span class="sxs-lookup"><span data-stu-id="d072c-118">**On error action**</span></span>  
 <span data-ttu-id="d072c-119">Escolha uma das seguintes ações a serem executadas quando o número de erros exceder o valor em **Número de erros**:</span><span class="sxs-lookup"><span data-stu-id="d072c-119">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="d072c-120">**Parar processamento** encerra a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-120">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="d072c-121">**Parar log** para o log de erros, mas continua a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-121">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="d072c-122">**Chave não encontrada**</span><span class="sxs-lookup"><span data-stu-id="d072c-122">**Key not found**</span></span>  
 <span data-ttu-id="d072c-123">Especifique uma das seguintes ações a ser executada quando uma chave não for localizada quando um objeto for processado:</span><span class="sxs-lookup"><span data-stu-id="d072c-123">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="d072c-124">**Ignorar erro** ignora o erro</span><span class="sxs-lookup"><span data-stu-id="d072c-124">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="d072c-125">**Relatar e continuar** relata o erro e continua a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-125">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="d072c-126">**Relatar e parar** relata o erro e para a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-126">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="d072c-127">**Chave duplicada**</span><span class="sxs-lookup"><span data-stu-id="d072c-127">**Duplicate key**</span></span>  
 <span data-ttu-id="d072c-128">Especifique uma das seguintes ações a ser executada se uma chave duplicada for localizada quando um objeto for processado:</span><span class="sxs-lookup"><span data-stu-id="d072c-128">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="d072c-129">**Ignorar erro** ignora o erro</span><span class="sxs-lookup"><span data-stu-id="d072c-129">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="d072c-130">**Relatar e continuar** relata o erro e continua a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-130">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="d072c-131">**Relatar e parar** relata o erro e para a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-131">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="d072c-132">**Chave nula convertida em desconhecida**</span><span class="sxs-lookup"><span data-stu-id="d072c-132">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="d072c-133">Especifique uma das seguintes ações a ser executada quando uma chave de membro nula for adicionada ao membro desconhecido durante o processamento de um objeto.</span><span class="sxs-lookup"><span data-stu-id="d072c-133">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed.</span></span>  
  
-   <span data-ttu-id="d072c-134">**Ignorar erro** ignora o erro</span><span class="sxs-lookup"><span data-stu-id="d072c-134">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="d072c-135">**Relatar e continuar** relata o erro e continua a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-135">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="d072c-136">**Relatar e parar** relata o erro e para a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-136">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="d072c-137">**Chave nula não permitida**</span><span class="sxs-lookup"><span data-stu-id="d072c-137">**Null key not allowed**</span></span>  
 <span data-ttu-id="d072c-138">Especifique uma das seguintes ações a ser executada quando uma chave nula for localizada, mas não for permitida, quando um objeto for processado.</span><span class="sxs-lookup"><span data-stu-id="d072c-138">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed.</span></span>  
  
-   <span data-ttu-id="d072c-139">**Ignorar erro** ignora o erro</span><span class="sxs-lookup"><span data-stu-id="d072c-139">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="d072c-140">**Relatar e continuar** relata o erro e continua a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-140">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="d072c-141">**Relatar e parar** relata o erro e para a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="d072c-141">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="d072c-142">**Caminho do log de erros**</span><span class="sxs-lookup"><span data-stu-id="d072c-142">**Error log path**</span></span>  
 <span data-ttu-id="d072c-143">Digite o caminho completo e nome do arquivo de log de erros.</span><span class="sxs-lookup"><span data-stu-id="d072c-143">Type the full path and file name for the error log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d072c-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d072c-144">See Also</span></span>  
 <span data-ttu-id="d072c-145">[Caixa de diálogo Propriedades da estrutura de mineração &#40;Analysis Services-Mineração de dados&#41;](mining-structure-properties-dialog-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="d072c-145">[Mining Structure Properties Dialog &#40;Analysis Services - Data Mining&#41;](mining-structure-properties-dialog-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="d072c-146">Caixa de diálogo &#40;geral de estrutura de mineração&#41; &#40;Analysis Services-Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="d072c-146">General &#40;Mining Structure Dialog Box&#41; &#40;Analysis Services - Data Mining&#41;</span></span>](general-mining-structure-dialog-box-analysis-services-data-mining.md)  
  
  
