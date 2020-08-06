---
title: Caixa de diálogo análise de impacto (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.impactanalysisdialog.f1
ms.assetid: 208268eb-4e14-44db-9c64-6f74b776adb6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e47ab806b9bd10afc812113b69fe0849437068b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679080"
---
# <a name="impact-analysis-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="dfdf4-102">Caixa de diálogo Análise de Impacto (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="dfdf4-102">Impact Analysis Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="dfdf4-103">Use a caixa de diálogo **Análise de Impacto** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para identificar e opcionalmente processar objetos dependentes que sejam afetados se os objetos listados na caixa de diálogo **Processo** forem processados.</span><span class="sxs-lookup"><span data-stu-id="dfdf4-103">Use the **Impact Analysis** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to identify and optionally process dependent objects that are affected if the objects listed in the **Process** dialog box are processed.</span></span> <span data-ttu-id="dfdf4-104">É possível exibir a caixa de diálogo **Análise de Impacto** clicando em **Análise de Impacto** na caixa de diálogo **Processar** .</span><span class="sxs-lookup"><span data-stu-id="dfdf4-104">You can display the **Impact Analysis** dialog box by clicking **Impact Analysis** from the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfdf4-105">Um objeto aparecerá mais de uma vez se for afetado de mais de uma maneira.</span><span class="sxs-lookup"><span data-stu-id="dfdf4-105">An object appears more than once if it is affected in more than one way.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dfdf4-106">Opções</span><span class="sxs-lookup"><span data-stu-id="dfdf4-106">Options</span></span>  
 <span data-ttu-id="dfdf4-107">**Lista de objetos**</span><span class="sxs-lookup"><span data-stu-id="dfdf4-107">**Object list**</span></span>  
 <span data-ttu-id="dfdf4-108">Exibe uma lista de objetos dependentes em uma grade.</span><span class="sxs-lookup"><span data-stu-id="dfdf4-108">Displays a list of dependent objects in a grid.</span></span> <span data-ttu-id="dfdf4-109">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="dfdf4-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="dfdf4-110">**Object Name**</span><span class="sxs-lookup"><span data-stu-id="dfdf4-110">**Object Name**</span></span>  
 <span data-ttu-id="dfdf4-111">Exibe o nome do objeto dependente que pode precisar ser processado.</span><span class="sxs-lookup"><span data-stu-id="dfdf4-111">Displays the name of the dependent object that may need to be processed.</span></span> <span data-ttu-id="dfdf4-112">O ícone à esquerda do nome indica o tipo do objeto.</span><span class="sxs-lookup"><span data-stu-id="dfdf4-112">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="dfdf4-113">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dfdf4-113">**Type**</span></span>  
 <span data-ttu-id="dfdf4-114">Exibe o tipo do objeto dependente que pode precisar ser processado.</span><span class="sxs-lookup"><span data-stu-id="dfdf4-114">Displays the type of dependent object that may need to be processed.</span></span>  
  
 <span data-ttu-id="dfdf4-115">**Tipo de Impacto**</span><span class="sxs-lookup"><span data-stu-id="dfdf4-115">**Impact Type**</span></span>  
 <span data-ttu-id="dfdf4-116">Exibe o efeito que o processamento dos objetos na caixa de diálogo **Processar** tem sobre o objeto dependente.</span><span class="sxs-lookup"><span data-stu-id="dfdf4-116">Displays the effect that processing the objects in the **Process** dialog box has on the dependent object.</span></span> <span data-ttu-id="dfdf4-117">A tabela a seguir lista os efeitos possíveis do processamento e indica se cada um deles resulta em um aviso ou erro.</span><span class="sxs-lookup"><span data-stu-id="dfdf4-117">The following table lists the possible effects of processing and notes whether each one results in a warning or an error.</span></span>  
  
|<span data-ttu-id="dfdf4-118">Impacto</span><span class="sxs-lookup"><span data-stu-id="dfdf4-118">Impact</span></span>|<span data-ttu-id="dfdf4-119">Mensagem</span><span class="sxs-lookup"><span data-stu-id="dfdf4-119">Message</span></span>|  
|------------|-------------|  
|<span data-ttu-id="dfdf4-120">O objeto será limpo (não processado)</span><span class="sxs-lookup"><span data-stu-id="dfdf4-120">Object will be cleared (unprocessed)</span></span>|<span data-ttu-id="dfdf4-121">Aviso</span><span class="sxs-lookup"><span data-stu-id="dfdf4-121">Warning</span></span>|  
|<span data-ttu-id="dfdf4-122">O objeto será inválido</span><span class="sxs-lookup"><span data-stu-id="dfdf4-122">Object would be invalid</span></span>|<span data-ttu-id="dfdf4-123">Erro</span><span class="sxs-lookup"><span data-stu-id="dfdf4-123">Error</span></span>|  
|<span data-ttu-id="dfdf4-124">A agregação será cancelada</span><span class="sxs-lookup"><span data-stu-id="dfdf4-124">Aggregation would be dropped</span></span>|<span data-ttu-id="dfdf4-125">Aviso</span><span class="sxs-lookup"><span data-stu-id="dfdf4-125">Warning</span></span>|  
|<span data-ttu-id="dfdf4-126">A agregação flexível será cancelada</span><span class="sxs-lookup"><span data-stu-id="dfdf4-126">Flexible aggregation would be dropped</span></span>|<span data-ttu-id="dfdf4-127">Aviso</span><span class="sxs-lookup"><span data-stu-id="dfdf4-127">Warning</span></span>|  
|<span data-ttu-id="dfdf4-128">Os índices serão cancelados</span><span class="sxs-lookup"><span data-stu-id="dfdf4-128">Indexes will be dropped</span></span>|<span data-ttu-id="dfdf4-129">Aviso</span><span class="sxs-lookup"><span data-stu-id="dfdf4-129">Warning</span></span>|  
|<span data-ttu-id="dfdf4-130">O objeto não filho será processado</span><span class="sxs-lookup"><span data-stu-id="dfdf4-130">Non-child object will be processed</span></span>|<span data-ttu-id="dfdf4-131">Aviso</span><span class="sxs-lookup"><span data-stu-id="dfdf4-131">Warning</span></span>|  
  
 <span data-ttu-id="dfdf4-132">**Objeto de Processo**</span><span class="sxs-lookup"><span data-stu-id="dfdf4-132">**Process Object**</span></span>  
 <span data-ttu-id="dfdf4-133">Selecione os objetos dependentes que você quer processar com a operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="dfdf4-133">Select the dependent objects that you want to process with the processing operation.</span></span> <span data-ttu-id="dfdf4-134">Objetos dependentes que não estão selecionados devem ser processados após a conclusão da operação de processamento.</span><span class="sxs-lookup"><span data-stu-id="dfdf4-134">Dependent objects that are not selected must be processed after the processing operation is finished.</span></span> <span data-ttu-id="dfdf4-135">Caso contrário, eles não podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="dfdf4-135">Otherwise, they cannot be used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfdf4-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dfdf4-136">See Also</span></span>  
 <span data-ttu-id="dfdf4-137">[Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="dfdf4-137">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="dfdf4-138">Caixa de diálogo processo &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="dfdf4-138">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
