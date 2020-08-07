---
title: Opções (página resultados da consulta-SQL Server-resultados em texto) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLResultsToText
ms.assetid: 2ccbdf17-e14f-42f1-a836-ca999a3432c9
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ece458e4bab9a57cb6692d4ac6dfdf2e8f4bd22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681817"
---
# <a name="options-query-results-sql-server-results-to-text-page"></a><span data-ttu-id="34875-102">Opções (página resultados da consulta-SQL Server-resultados em texto)</span><span class="sxs-lookup"><span data-stu-id="34875-102">Options (Query Results-SQL Server-Results to Text Page)</span></span>
  <span data-ttu-id="34875-103">Use esta página para especificar as opções de exibição de um conjunto de resultados da consulta em formato de texto.</span><span class="sxs-lookup"><span data-stu-id="34875-103">Use this page to specify the options for displaying a query result set in text format.</span></span> <span data-ttu-id="34875-104">As alterações feitas nessas opções são aplicadas apenas a novas consultas do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34875-104">Changes to these options are applied only to new [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="34875-105">Para alterar as opções das consultas atuais, clique em **Opções de consulta** no menu **consulta** ou clique com o botão direito do mouse na [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] janela de consulta e selecione **Opções de consulta**.</span><span class="sxs-lookup"><span data-stu-id="34875-105">To change the options for the current queries, click **Query Options** on the **Query** menu, or right-click in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window, and select **Query Options**.</span></span> <span data-ttu-id="34875-106">Na caixa de diálogo **Opções de Consulta**, em **Resultados**, clique em **Texto**.</span><span class="sxs-lookup"><span data-stu-id="34875-106">In the **Query Options** dialog box, under **Results**, click **Text**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="34875-107">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="34875-107">UI element list</span></span>  
 <span data-ttu-id="34875-108">**Formato da saída**</span><span class="sxs-lookup"><span data-stu-id="34875-108">**Output format**</span></span>  
 <span data-ttu-id="34875-109">Por padrão, a saída é exibida em colunas criadas preenchendo os resultados com espaços.</span><span class="sxs-lookup"><span data-stu-id="34875-109">By default the output is displayed in columns created by padding the results with spaces.</span></span> <span data-ttu-id="34875-110">Outras opções são o uso de vírgulas, tabulações ou espaços para separar as colunas.</span><span class="sxs-lookup"><span data-stu-id="34875-110">Other options are to use commas, tabs, or spaces to separate columns.</span></span> <span data-ttu-id="34875-111">Selecione **Delimitador personalizado** nessa lista suspensa, a fim de especificar um caractere de delimitação diferente na caixa de texto **Delimitador personalizado**.</span><span class="sxs-lookup"><span data-stu-id="34875-111">Select **Custom delimiter** from this drop-down list to specify a different delimiting character in the **Custom delimiter** text box.</span></span>  
  
 <span data-ttu-id="34875-112">**Delimitador personalizado**</span><span class="sxs-lookup"><span data-stu-id="34875-112">**Custom delimiter**</span></span>  
 <span data-ttu-id="34875-113">Especifique o caractere de sua escolha para separar colunas.</span><span class="sxs-lookup"><span data-stu-id="34875-113">Specify the character of your choice to separate columns.</span></span> <span data-ttu-id="34875-114">Essa caixa de texto está disponível apenas se você clicou em Delimitador personalizado na caixa de listagem suspensa **Formato de saída**.</span><span class="sxs-lookup"><span data-stu-id="34875-114">This text box is available only if you clicked Custom delimiter in the **Output format** drop-down list box.</span></span>  
  
 <span data-ttu-id="34875-115">**Incluir cabeçalhos de coluna no conjunto de resultados**</span><span class="sxs-lookup"><span data-stu-id="34875-115">**Include column headers in the result set**</span></span>  
 <span data-ttu-id="34875-116">Desmarque esta caixa de seleção se não quiser cada coluna rotulada com um título de coluna.</span><span class="sxs-lookup"><span data-stu-id="34875-116">Clear this check box if you do not want each column labeled with a column title.</span></span>  
  
 <span data-ttu-id="34875-117">**Incluir a consulta no conjunto de resultados**</span><span class="sxs-lookup"><span data-stu-id="34875-117">**Include the query in the result set**</span></span>  
 <span data-ttu-id="34875-118">Marque essa caixa de seleção para incluir o texto da consulta que está sendo executada no painel resultados antes dos resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="34875-118">Select this check box to include the text of the query that is running in the results pane before the results of the query.</span></span>  
  
 <span data-ttu-id="34875-119">**Rolar à medida que os resultados forem recebidos**</span><span class="sxs-lookup"><span data-stu-id="34875-119">**Scroll as results are received**</span></span>  
 <span data-ttu-id="34875-120">Marque essa caixa de seleção para manter o foco de exibição nos registros retornados, mais recentemente, no final do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="34875-120">Select this check box to keep the display focus on the most recently returned records at the end of the results set.</span></span> <span data-ttu-id="34875-121">Desmarque esta caixa de seleção para manter o foco de exibição nas primeiras linhas recebidas.</span><span class="sxs-lookup"><span data-stu-id="34875-121">Clear this check box to keep the display focus on the first rows received.</span></span>  
  
 <span data-ttu-id="34875-122">**Alinhar valores numéricos à direita**</span><span class="sxs-lookup"><span data-stu-id="34875-122">**Right align numeric values**</span></span>  
 <span data-ttu-id="34875-123">Marque esta caixa de seleção para alinhar valores numéricos à direita da coluna.</span><span class="sxs-lookup"><span data-stu-id="34875-123">Select this check box to align numeric values to the right of the column.</span></span> <span data-ttu-id="34875-124">Isso pode tornar mais fácil a revisão de números com um número fixo de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="34875-124">This can make it easier to review numbers with a fixed number of decimal places.</span></span>  
  
 <span data-ttu-id="34875-125">**Descartar resultado após a execução da consulta**</span><span class="sxs-lookup"><span data-stu-id="34875-125">**Discard result after query executes**</span></span>  
 <span data-ttu-id="34875-126">Marque essa caixa de seleção para descartar os resultados da consulta depois que forem exibidos no painel resultados da janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="34875-126">Select this check box to discard the query results after they are displayed in the results pane of the query window.</span></span>  
  
 <span data-ttu-id="34875-127">**Exibir resultados em uma guia separada**</span><span class="sxs-lookup"><span data-stu-id="34875-127">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="34875-128">Marque essa caixa de seleção para exibir o conjunto de resultados em uma nova janela de documento, em vez de na parte inferior da janela de documentos de consulta.</span><span class="sxs-lookup"><span data-stu-id="34875-128">Select this check box to display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="34875-129">**Alternar para a guia Resultados após a execução da consulta**</span><span class="sxs-lookup"><span data-stu-id="34875-129">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="34875-130">Marque essa caixa de seleção para definir o foco de tela automaticamente para o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="34875-130">Select this check box to automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="34875-131">**Número máximo de caracteres exibidos em cada coluna**</span><span class="sxs-lookup"><span data-stu-id="34875-131">**Maximum number of characters displayed in each column**</span></span>  
 <span data-ttu-id="34875-132">Esse valor padrão é 256.</span><span class="sxs-lookup"><span data-stu-id="34875-132">This value defaults to 256.</span></span> <span data-ttu-id="34875-133">Aumente o valor para exibir conjuntos de resultados maiores sem truncar.</span><span class="sxs-lookup"><span data-stu-id="34875-133">Increase this value to display larger result sets without truncation.</span></span> <span data-ttu-id="34875-134">O valor máximo é 8.192.</span><span class="sxs-lookup"><span data-stu-id="34875-134">The maximum value is 8,192.</span></span>  
  
 <span data-ttu-id="34875-135">**Restaurar Padrões**</span><span class="sxs-lookup"><span data-stu-id="34875-135">**Reset to Default**</span></span>  
 <span data-ttu-id="34875-136">Redefine todos os valores dessa página com os valores padrão originais.</span><span class="sxs-lookup"><span data-stu-id="34875-136">Resets all values on this page to the original default values.</span></span>  
  
  
