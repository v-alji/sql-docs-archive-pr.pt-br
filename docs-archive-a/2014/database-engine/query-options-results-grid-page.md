---
title: Resultados de opções de consulta (página grade) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.grid.f1
ms.assetid: 764bf435-3aab-4c62-b4e0-64fe020a5a95
author: rothja
ms.author: jroth
ms.openlocfilehash: bf300dd5071128b0259230ae788a27595bd8d29e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582110"
---
# <a name="query-options-results-grid-page"></a><span data-ttu-id="91534-102">Resultados das opções de consultas (Página Grade)</span><span class="sxs-lookup"><span data-stu-id="91534-102">Query Options Results (Grid Page)</span></span>
  <span data-ttu-id="91534-103">Use esta página para especificar as opções de exibição de um conjunto de resultados da consulta em formato de grade.</span><span class="sxs-lookup"><span data-stu-id="91534-103">Use this page to specify the options for displaying a query result set in grid format.</span></span>  
  
## <a name="options"></a><span data-ttu-id="91534-104">Opções</span><span class="sxs-lookup"><span data-stu-id="91534-104">Options</span></span>  
 <span data-ttu-id="91534-105">**Incluir a consulta no conjunto de resultados**</span><span class="sxs-lookup"><span data-stu-id="91534-105">**Include the query in the result set**</span></span>  
 <span data-ttu-id="91534-106">Retorna o texto da consulta como parte do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="91534-106">Returns the text of the query as part of the result set.</span></span>  
  
 <span data-ttu-id="91534-107">**Inclua cabeçalhos de coluna ao copiar ou salvar resultados**</span><span class="sxs-lookup"><span data-stu-id="91534-107">**Include column headers when copying or saving the results**</span></span>  
 <span data-ttu-id="91534-108">Inclui os cabeçalhos de coluna (títulos) quando os resultados são copiados para a área de transferência ou quando são salvos em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="91534-108">Include column headers (titles) when results are copied to the clipboard, or saved in a file.</span></span> <span data-ttu-id="91534-109">Desmarque essa caixa de seleção se você não deseja que os dados de resultados copiados ou salvos contenham apenas os dados e não os cabeçalhos da coluna.</span><span class="sxs-lookup"><span data-stu-id="91534-109">Clear this check box if you do not want saved or copied result data to have only the data, and not the column headings.</span></span>  
  
 <span data-ttu-id="91534-110">**Descartar resultados após a execução**</span><span class="sxs-lookup"><span data-stu-id="91534-110">**Discard results after execution**</span></span>  
 <span data-ttu-id="91534-111">Libera memória descartando os resultados da consulta após a tela tê-los recebido.</span><span class="sxs-lookup"><span data-stu-id="91534-111">Free memory by discarding the query results after the screen display has received them.</span></span>  
  
 <span data-ttu-id="91534-112">**Exibir resultados em uma guia separada**</span><span class="sxs-lookup"><span data-stu-id="91534-112">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="91534-113">Exibe o conjunto de resultados em uma janela de documentos nova, em vez de na parte inferior da janela de documentos de consulta.</span><span class="sxs-lookup"><span data-stu-id="91534-113">Display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="91534-114">**Alternar para a guia Resultados após a execução da consulta**</span><span class="sxs-lookup"><span data-stu-id="91534-114">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="91534-115">Define automaticamente o foco da tela para o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="91534-115">Automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="91534-116">**Máximo de Caracteres Recuperados**</span><span class="sxs-lookup"><span data-stu-id="91534-116">**Maximum Characters Retrieved**</span></span>  
 <span data-ttu-id="91534-117">**Dados não XML**:</span><span class="sxs-lookup"><span data-stu-id="91534-117">**Non XML data**:</span></span>  
  
 <span data-ttu-id="91534-118">Digite um número de 1 a 65535 para especificar o número máximo de caracteres que serão exibidos em cada célula.</span><span class="sxs-lookup"><span data-stu-id="91534-118">Enter a number from 1 through 65535 to specify the maximum number of characters that will be displayed in each cell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91534-119">Especificar um número grande de caracteres pode fazer com que os dados no conjunto de resultados apareçam truncados.</span><span class="sxs-lookup"><span data-stu-id="91534-119">Specifying a large number of characters may cause data in the result set to appear truncated.</span></span> <span data-ttu-id="91534-120">O número máximo de caracteres exibido em cada célula depende do tamanho da fonte.</span><span class="sxs-lookup"><span data-stu-id="91534-120">The maximum number of characters displayed in each cell is dependent on the font size.</span></span> <span data-ttu-id="91534-121">Quando grandes conjuntos de resultados são retornados, um valor alto nessa caixa pode fazer com que o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] fique com pouca memória e atrapalhe o desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="91534-121">When large result sets are returned, a high value in this box can cause [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to run low on memory and hinder system performance.</span></span>  
  
 <span data-ttu-id="91534-122">**Dados XML**:</span><span class="sxs-lookup"><span data-stu-id="91534-122">**XML data**:</span></span>  
  
 <span data-ttu-id="91534-123">Selecione **1 MB**, **2 MB**ou **5 MB**.</span><span class="sxs-lookup"><span data-stu-id="91534-123">Select **1 MB**, **2 MB**, or **5 MB**.</span></span> <span data-ttu-id="91534-124">Selecione **Ilimitado** para recuperar todos os caracteres.</span><span class="sxs-lookup"><span data-stu-id="91534-124">Select **Unlimited** to retrieve all characters.</span></span>  
  
 <span data-ttu-id="91534-125">**Restaurar Padrões**</span><span class="sxs-lookup"><span data-stu-id="91534-125">**Reset to Default**</span></span>  
 <span data-ttu-id="91534-126">Redefine todos os valores dessa página com os valores padrão originais.</span><span class="sxs-lookup"><span data-stu-id="91534-126">Resets all values on this page to the original default values.</span></span>  
  
  
