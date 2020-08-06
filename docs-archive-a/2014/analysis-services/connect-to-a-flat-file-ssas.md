---
title: Conectar-se a um arquivo simples (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connflatfile.f1
ms.assetid: a365991e-eded-4cd8-89c0-0daf6d658d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6bee3c8f7f4b255e6985e8d783365bc8a47599e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571028"
---
# <a name="connect-to-a-flat-file-ssas"></a><span data-ttu-id="bd3a7-102">Conectar a um arquivo simples (SSAS)</span><span class="sxs-lookup"><span data-stu-id="bd3a7-102">Connect to a Flat File (SSAS)</span></span>
  <span data-ttu-id="bd3a7-103">Esta página do **Assistente de Importação de Tabela** o habilita a se conectar a um arquivo simples (.txt), um arquivo separado por tabulações (.tab) ou um arquivo separado por vírgulas (.csv).</span><span class="sxs-lookup"><span data-stu-id="bd3a7-103">This page of the **Table Import Wizard** enables you to connect to a flat file (.txt), tab-separated file (.tab), or a comma-separated file (.csv).</span></span> <span data-ttu-id="bd3a7-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="bd3a7-105">Para conectar um arquivo simples, você deve ter o provedor ACE instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-105">To connect to a flat file, you must have the ACE provider installed on your computer.</span></span> <span data-ttu-id="bd3a7-106">Para obter mais informações, consulte [Fontes de dados com suporte &#40;SSAS tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="bd3a7-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd3a7-107">As credenciais do usuário atual são usadas na seleção de um arquivo nesta página.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="bd3a7-108">Porém, a importação não terá êxito se o usuário especificado na página Informações sobre Representação não tiver privilégios suficientes para ler do arquivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="bd3a7-109">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="bd3a7-109">UI element list</span></span>  
 <span data-ttu-id="bd3a7-110">**Nome de conexão amigável**</span><span class="sxs-lookup"><span data-stu-id="bd3a7-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="bd3a7-111">Digite um nome exclusivo para esta conexão de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="bd3a7-112">Esse é um campo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-112">This is a required field.</span></span>  
  
 <span data-ttu-id="bd3a7-113">**Caminho do arquivo**</span><span class="sxs-lookup"><span data-stu-id="bd3a7-113">**File Path**</span></span>  
 <span data-ttu-id="bd3a7-114">Especifique o caminho completo para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-114">Specify a full path for the file.</span></span>  
  
 <span data-ttu-id="bd3a7-115">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="bd3a7-115">**Browse**</span></span>  
 <span data-ttu-id="bd3a7-116">Navegue até um local onde um arquivo está disponível.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-116">Navigate to a location where a file is available.</span></span>  
  
 <span data-ttu-id="bd3a7-117">**Separador de coluna**</span><span class="sxs-lookup"><span data-stu-id="bd3a7-117">**Column Separator**</span></span>  
 <span data-ttu-id="bd3a7-118">Selecione de uma lista de separadores de colunas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-118">Select from a list of available column separators.</span></span> <span data-ttu-id="bd3a7-119">Escolha um separador com pouca probabilidade de ocorrer no texto.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-119">Choose a separator that is not likely to occur in the text.</span></span>  
  
|<span data-ttu-id="bd3a7-120">Valor</span><span class="sxs-lookup"><span data-stu-id="bd3a7-120">Value</span></span>|<span data-ttu-id="bd3a7-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="bd3a7-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd3a7-122">Tabulação (t)</span><span class="sxs-lookup"><span data-stu-id="bd3a7-122">Tab (t)</span></span>|<span data-ttu-id="bd3a7-123">As colunas são separadas por uma tabulação (t).</span><span class="sxs-lookup"><span data-stu-id="bd3a7-123">Columns are separated by a tab (t).</span></span>|  
|<span data-ttu-id="bd3a7-124">Vírgula (,)</span><span class="sxs-lookup"><span data-stu-id="bd3a7-124">Comma (,)</span></span>|<span data-ttu-id="bd3a7-125">As colunas são separadas por uma vírgula (,).</span><span class="sxs-lookup"><span data-stu-id="bd3a7-125">Columns are separated by a comma (,).</span></span>|  
|<span data-ttu-id="bd3a7-126">Ponto-e-vírgula (;)</span><span class="sxs-lookup"><span data-stu-id="bd3a7-126">Semicolon (;)</span></span>|<span data-ttu-id="bd3a7-127">As colunas são separadas por um ponto-e-vírgula (;).</span><span class="sxs-lookup"><span data-stu-id="bd3a7-127">Columns are separated by a semicolon (;).</span></span>|  
|<span data-ttu-id="bd3a7-128">Espaço ( )</span><span class="sxs-lookup"><span data-stu-id="bd3a7-128">Space ( )</span></span>|<span data-ttu-id="bd3a7-129">As colunas são separadas por um espaço ( ).</span><span class="sxs-lookup"><span data-stu-id="bd3a7-129">Columns are separated by a space ( ).</span></span>|  
|<span data-ttu-id="bd3a7-130">Dois-pontos (:)</span><span class="sxs-lookup"><span data-stu-id="bd3a7-130">Colon (:)</span></span>|<span data-ttu-id="bd3a7-131">As colunas são separadas por dois-pontos (:).</span><span class="sxs-lookup"><span data-stu-id="bd3a7-131">Columns are separated by a colon (:).</span></span>|  
|<span data-ttu-id="bd3a7-132">Barra vertical (&#124;)</span><span class="sxs-lookup"><span data-stu-id="bd3a7-132">Vertical Bar (&#124;)</span></span>|<span data-ttu-id="bd3a7-133">As colunas são separadas por uma barra vertical (&#124;).</span><span class="sxs-lookup"><span data-stu-id="bd3a7-133">Columns are separated by a vertical bar (&#124;).</span></span>|  
  
 <span data-ttu-id="bd3a7-134">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="bd3a7-134">**Advanced**</span></span>  
 <span data-ttu-id="bd3a7-135">Especifique a codificação e as opções de localidade para o arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-135">Specify the encoding and locale options for the flat file.</span></span>  
  
 <span data-ttu-id="bd3a7-136">**Usar primeira linha como cabeçalhos de coluna**</span><span class="sxs-lookup"><span data-stu-id="bd3a7-136">**Use first row as column headers**</span></span>  
 <span data-ttu-id="bd3a7-137">Especifique se deseja usar a primeira linha de dados como o cabeçalho de coluna da tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-137">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="bd3a7-138">**Visualização de dados**</span><span class="sxs-lookup"><span data-stu-id="bd3a7-138">**Data preview**</span></span>  
 <span data-ttu-id="bd3a7-139">Visualize os dados na tabela selecionada e use as opções a seguir para modificar a importação de dados.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-139">Preview the data in the selected file, and use the following options to modify the data import.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd3a7-140">São exibidas somente as primeiras 50 linhas do arquivo nesta visualização.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-140">Only the first 50 rows in the file are displayed in this preview.</span></span>  
  
|<span data-ttu-id="bd3a7-141">Opção</span><span class="sxs-lookup"><span data-stu-id="bd3a7-141">Option</span></span>|<span data-ttu-id="bd3a7-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="bd3a7-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bd3a7-143">**Caixa de seleção no cabeçalho da coluna**</span><span class="sxs-lookup"><span data-stu-id="bd3a7-143">**Checkbox in the column header**</span></span>|<span data-ttu-id="bd3a7-144">Marque a caixa de seleção para incluir a coluna na importação de dados.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-144">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="bd3a7-145">Desmarque a caixa de seleção para remover a coluna da importação de dados.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-145">Clear the checkbox to remove the column from the data import.</span></span>|  
|<span data-ttu-id="bd3a7-146">**Botão de seta para baixo no cabeçalho da coluna**</span><span class="sxs-lookup"><span data-stu-id="bd3a7-146">**Down-arrow button in the column header**</span></span>|<span data-ttu-id="bd3a7-147">Classifique e filtre dados na coluna.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-147">Sort and filter data in the column.</span></span>|  
  
 <span data-ttu-id="bd3a7-148">**Limpar Filtros de Linha**</span><span class="sxs-lookup"><span data-stu-id="bd3a7-148">**Clear Row Filters**</span></span>  
 <span data-ttu-id="bd3a7-149">Remova todos os filtros aplicados aos dados nas colunas.</span><span class="sxs-lookup"><span data-stu-id="bd3a7-149">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
