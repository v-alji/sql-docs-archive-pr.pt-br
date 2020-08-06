---
title: Resultados de opções de consulta (página de texto) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.text.f1
ms.assetid: fd2fb409-58f9-4ede-8349-ce007126b68d
author: rothja
ms.author: jroth
ms.openlocfilehash: 45019450c8fc959b440aac5bf1e9098e59cecefc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582109"
---
# <a name="query-options-results-text-page"></a><span data-ttu-id="a33bd-102">Resultados das opções de consulta (página de texto)</span><span class="sxs-lookup"><span data-stu-id="a33bd-102">Query Options Results (Text Page)</span></span>
  <span data-ttu-id="a33bd-103">Use esta página para especificar as opções de exibição de um conjunto de resultados da consulta em formato de texto.</span><span class="sxs-lookup"><span data-stu-id="a33bd-103">Use this page to specify the options for displaying a query result set in text format.</span></span> <span data-ttu-id="a33bd-104">As configurações desta página também se aplicam quando **Resultados em Arquivo** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="a33bd-104">The settings on this page also apply when **Results to File** is selected.</span></span>  
  
 <span data-ttu-id="a33bd-105">**Formato da saída**</span><span class="sxs-lookup"><span data-stu-id="a33bd-105">**Output format**</span></span>  
 <span data-ttu-id="a33bd-106">Por padrão, a saída é exibida em colunas criadas preenchendo os resultados com espaços.</span><span class="sxs-lookup"><span data-stu-id="a33bd-106">By default the output is displayed in columns created by padding the results with spaces.</span></span> <span data-ttu-id="a33bd-107">Outras opções são o uso de vírgulas, tabulações ou espaços para separar as colunas.</span><span class="sxs-lookup"><span data-stu-id="a33bd-107">Other options are using commas, tabs, or spaces to separate columns.</span></span> <span data-ttu-id="a33bd-108">Marque a caixa de seleção **Delimitador personalizado** para especificar um caractere delimitador diferente na caixa **Delimitador personalizado** .</span><span class="sxs-lookup"><span data-stu-id="a33bd-108">Select the **Custom delimiter** check box to specify a different delimiting character in the **Custom delimiter** box.</span></span>  
  
 <span data-ttu-id="a33bd-109">**Delimitador personalizado**</span><span class="sxs-lookup"><span data-stu-id="a33bd-109">**Custom delimiter**</span></span>  
 <span data-ttu-id="a33bd-110">Especifique o caractere de sua escolha para separar colunas.</span><span class="sxs-lookup"><span data-stu-id="a33bd-110">Specify the character of your choice to separate columns.</span></span> <span data-ttu-id="a33bd-111">Esta opção só está disponível se a caixa de seleção **Delimitador personalizado** for marcada na caixa **Formato de saída** .</span><span class="sxs-lookup"><span data-stu-id="a33bd-111">This option is only available if the **Custom delimiter** check box is selected in the **Output format** box.</span></span>  
  
 <span data-ttu-id="a33bd-112">**Incluir cabeçalhos de coluna no conjunto de resultados**</span><span class="sxs-lookup"><span data-stu-id="a33bd-112">**Include column headers in the result set**</span></span>  
 <span data-ttu-id="a33bd-113">Desmarque esta caixa de seleção se não quiser cada coluna rotulada com um título de coluna.</span><span class="sxs-lookup"><span data-stu-id="a33bd-113">Clear this check box if you do not want each column labeled with a column title.</span></span>  
  
 <span data-ttu-id="a33bd-114">**Rolar à medida que os resultados forem recebidos**</span><span class="sxs-lookup"><span data-stu-id="a33bd-114">**Scroll as results are received**</span></span>  
 <span data-ttu-id="a33bd-115">Marque esta caixa de seleção para manter o foco de exibição nos registros retornados mais recentemente na parte inferior.</span><span class="sxs-lookup"><span data-stu-id="a33bd-115">Select this check box to keep the display focus on the most recently returned records at the bottom.</span></span> <span data-ttu-id="a33bd-116">Desmarque esta caixa de seleção para manter o foco de exibição nas primeiras linhas recebidas.</span><span class="sxs-lookup"><span data-stu-id="a33bd-116">Clear this check box to keep the display focus on the first rows received.</span></span>  
  
 <span data-ttu-id="a33bd-117">**Alinhar valores numéricos à direita**</span><span class="sxs-lookup"><span data-stu-id="a33bd-117">**Right align numeric values**</span></span>  
 <span data-ttu-id="a33bd-118">Marque esta caixa de seleção para alinhar valores numéricos à direita da coluna.</span><span class="sxs-lookup"><span data-stu-id="a33bd-118">Select this check box to align numeric values to the right of the column.</span></span> <span data-ttu-id="a33bd-119">Isso pode tornar mais fácil a revisão de números com um número fixo de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="a33bd-119">This can make it easier to review numbers with a fixed number of decimal places.</span></span>  
  
 <span data-ttu-id="a33bd-120">**Descartar resultado após a execução da consulta**</span><span class="sxs-lookup"><span data-stu-id="a33bd-120">**Discard result after query executes**</span></span>  
 <span data-ttu-id="a33bd-121">Libera memória descartando os resultados da consulta depois de serem recebidos pelo monitor.</span><span class="sxs-lookup"><span data-stu-id="a33bd-121">Frees memory by discarding the query results after the screen display has received them.</span></span>  
  
 <span data-ttu-id="a33bd-122">**Exibir resultados em uma guia separada**</span><span class="sxs-lookup"><span data-stu-id="a33bd-122">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="a33bd-123">Marque essa caixa de seleção para exibir o conjunto de resultados em uma nova janela de documento, em vez de na parte inferior da janela de documentos de consulta.</span><span class="sxs-lookup"><span data-stu-id="a33bd-123">Select this check box to display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="a33bd-124">**Alternar para a guia Resultados após a execução da consulta**</span><span class="sxs-lookup"><span data-stu-id="a33bd-124">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="a33bd-125">Clique para definir automaticamente o foco da tela no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="a33bd-125">Click to automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="a33bd-126">**Número máximo de caracteres exibidos em cada coluna**</span><span class="sxs-lookup"><span data-stu-id="a33bd-126">**Maximum number of characters displayed in each column**</span></span>  
 <span data-ttu-id="a33bd-127">Esse valor padrão é 256.</span><span class="sxs-lookup"><span data-stu-id="a33bd-127">This value defaults to 256.</span></span> <span data-ttu-id="a33bd-128">Aumente o valor para exibir conjuntos de resultados maiores sem truncar.</span><span class="sxs-lookup"><span data-stu-id="a33bd-128">Increase this value to display larger result sets without truncation.</span></span>  
  
 <span data-ttu-id="a33bd-129">**Restaurar Padrões**</span><span class="sxs-lookup"><span data-stu-id="a33bd-129">**Reset to Default**</span></span>  
 <span data-ttu-id="a33bd-130">Redefine todos os valores dessa página com os valores padrão originais.</span><span class="sxs-lookup"><span data-stu-id="a33bd-130">Resets all values on this page to the original default values.</span></span>  
  
## <a name="saving-a-text-result-set-with-headers"></a><span data-ttu-id="a33bd-131">Salvar um conjunto de resultados de texto com cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="a33bd-131">Saving a text result set with headers</span></span>  
 <span data-ttu-id="a33bd-132">Para salvar resultados de consulta como um arquivo de texto com cabeçalhos, marque a caixa de seleção **Incluir cabeçalhos de colunas no conjunto de resultados** e um formato de saída delimitado.</span><span class="sxs-lookup"><span data-stu-id="a33bd-132">To save query results as a text file with headers, select the **Include column headers in the result set** check box and a delimited output format.</span></span> <span data-ttu-id="a33bd-133">Agora, o arquivo do relatório conterá cabeçalhos quando você clicar em **Resultados em Arquivo** na barra de ferramenta ou quando você clicar com o botão direito do mouse em qualquer um dos resultados da consulta, clicar em **Salvar Resultados Como**, digitar um nome de arquivo e clicar em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a33bd-133">Now the report file will contain headers when you click **Results to File** on the toolbar, or when you right-click any query results, click **Save Results As**, type a file name, and then click **Save**.</span></span>  
  
  
