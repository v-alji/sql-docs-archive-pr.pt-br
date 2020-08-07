---
title: Editor de transformação Extração de termos (guia Avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.advanced.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 87118281-6e3c-499e-bac4-fa4c24bb12c6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4be56f8ac2deeab49e43071a07894a466019287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681760"
---
# <a name="term-extraction-transformation-editor-advanced-tab"></a><span data-ttu-id="7f355-102">Editor de Transformação Extração de Termos (guia Avançado)</span><span class="sxs-lookup"><span data-stu-id="7f355-102">Term Extraction Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="7f355-103">Use a guia **Avançado** da caixa de diálogo **Editor de Transformação de Extração de Termos** para especificar propriedades de extração, como frequência, comprimento e se devem ser extraídas palavras ou frases.</span><span class="sxs-lookup"><span data-stu-id="7f355-103">Use the **Advanced** tab of the **Term Extraction Transformation Editor** dialog box to specify properties for the extraction such as frequency, length, and whether to extract words or phrases.</span></span>  
  
 <span data-ttu-id="7f355-104">Para saber mais sobre a transformação Extração de Termos, consulte [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="7f355-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f355-105">Opções</span><span class="sxs-lookup"><span data-stu-id="7f355-105">Options</span></span>  
 <span data-ttu-id="7f355-106">**Substantivo**</span><span class="sxs-lookup"><span data-stu-id="7f355-106">**Noun**</span></span>  
 <span data-ttu-id="7f355-107">Especifique que a transformação só extrai substantivos individuais.</span><span class="sxs-lookup"><span data-stu-id="7f355-107">Specify that the transformation extracts individual nouns only.</span></span>  
  
 <span data-ttu-id="7f355-108">**Frase substantivada**</span><span class="sxs-lookup"><span data-stu-id="7f355-108">**Noun phrase**</span></span>  
 <span data-ttu-id="7f355-109">Especifique que a transformação só extraia frases substantivadas.</span><span class="sxs-lookup"><span data-stu-id="7f355-109">Specify that the transformation extracts noun phrases only.</span></span>  
  
 <span data-ttu-id="7f355-110">**Substantivo e frase substantivada**</span><span class="sxs-lookup"><span data-stu-id="7f355-110">**Noun and noun phrase**</span></span>  
 <span data-ttu-id="7f355-111">Especifique que a transformação extraia tanto substantivos como frases substantivadas.</span><span class="sxs-lookup"><span data-stu-id="7f355-111">Specify that the transformation extracts both nouns and noun phrases.</span></span>  
  
 <span data-ttu-id="7f355-112">**Frequência**</span><span class="sxs-lookup"><span data-stu-id="7f355-112">**Frequency**</span></span>  
 <span data-ttu-id="7f355-113">Especifique que a pontuação é a frequência do termo.</span><span class="sxs-lookup"><span data-stu-id="7f355-113">Specify that the score is the frequency of the term.</span></span>  
  
 <span data-ttu-id="7f355-114">**TFIDF**</span><span class="sxs-lookup"><span data-stu-id="7f355-114">**TFIDF**</span></span>  
 <span data-ttu-id="7f355-115">Especifique que a pontuação é o valor TFIDF do termo.</span><span class="sxs-lookup"><span data-stu-id="7f355-115">Specify that the score is the TFIDF value of the term.</span></span> <span data-ttu-id="7f355-116">A pontuação TFIDF é o produto da Frequência do Termo e da Frequência de Documento Inversa, definido como: TFIDF de um termo T = (frequência de T) \* log ((nºs de linhas na Entrada) / (nº de linhas com T))</span><span class="sxs-lookup"><span data-stu-id="7f355-116">The TFIDF score is the product of Term Frequency and Inverse Document Frequency, defined as: TFIDF of a Term T = (frequency of T) \* log( (#rows in Input) / (#rows having T) )</span></span>  
  
 <span data-ttu-id="7f355-117">**Limite de frequência**</span><span class="sxs-lookup"><span data-stu-id="7f355-117">**Frequency threshold**</span></span>  
 <span data-ttu-id="7f355-118">Especifique o número de vezes que uma palavra ou frase deve aparecer antes de ser extraída.</span><span class="sxs-lookup"><span data-stu-id="7f355-118">Specify the number of times a word or phrase must occur before extracting it.</span></span> <span data-ttu-id="7f355-119">O valor padrão é 2.</span><span class="sxs-lookup"><span data-stu-id="7f355-119">The default value is 2.</span></span>  
  
 <span data-ttu-id="7f355-120">**Comprimento máximo do termo**</span><span class="sxs-lookup"><span data-stu-id="7f355-120">**Maximum length of term**</span></span>  
 <span data-ttu-id="7f355-121">Especifique o comprimento máximo de uma frase em palavras.</span><span class="sxs-lookup"><span data-stu-id="7f355-121">Specify the maximum length of a phrase in words.</span></span> <span data-ttu-id="7f355-122">Esta opção só afeta frases substantivadas.</span><span class="sxs-lookup"><span data-stu-id="7f355-122">This option affects noun phrases only.</span></span> <span data-ttu-id="7f355-123">O valor padrão é 12.</span><span class="sxs-lookup"><span data-stu-id="7f355-123">The default value is 12.</span></span>  
  
 <span data-ttu-id="7f355-124">**Usar extração de termos com diferenciação de maiúsculas e minúsculas**</span><span class="sxs-lookup"><span data-stu-id="7f355-124">**Use case-sensitive term extraction**</span></span>  
 <span data-ttu-id="7f355-125">Especifique se a extração deve ser feita diferenciando maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7f355-125">Specify whether to make the extraction case-sensitive.</span></span> <span data-ttu-id="7f355-126">O padrão é `False`.</span><span class="sxs-lookup"><span data-stu-id="7f355-126">The default is `False`.</span></span>  
  
 <span data-ttu-id="7f355-127">**Configurar Saída de Erro**</span><span class="sxs-lookup"><span data-stu-id="7f355-127">**Configure Error Output**</span></span>  
 <span data-ttu-id="7f355-128">Use a caixa de diálogo [Configurar Saída de Erro](../../2014/integration-services/configure-error-output.md) para especificar tratamento de erro em linhas que causam erros.</span><span class="sxs-lookup"><span data-stu-id="7f355-128">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f355-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7f355-129">See Also</span></span>  
 <span data-ttu-id="7f355-130">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7f355-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="7f355-131">[Editor de transformação Extração de termos &#40;guia extração de termos&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="7f355-131">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="7f355-132">[Editor de transformação Extração de termos &#40;guia exclusão&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span><span class="sxs-lookup"><span data-stu-id="7f355-132">[Term Extraction Transformation Editor &#40;Exclusion Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span></span>  
 [<span data-ttu-id="7f355-133">Transformação Pesquisa de Termos</span><span class="sxs-lookup"><span data-stu-id="7f355-133">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
