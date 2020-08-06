---
title: Exportando para um arquivo CSV (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 68ec746e-8c82-47f5-8c3d-dbe403a441e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 635d5904acf6e616378f5423bfbaf4cf5390fa9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569165"
---
# <a name="exporting-to-a-csv-file-report-builder-and-ssrs"></a><span data-ttu-id="2e2bc-102">Exportando para um arquivo CSV (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2e2bc-102">Exporting to a CSV File (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2e2bc-103">A extensão de renderização CSV (Comma-Separated Value) renderiza relatórios como uma representação mesclada dos dados de um relatório padronizado, em formato de texto simples que pode ser facilmente lido e que também permite a troca com vários aplicativos.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-103">The Comma-Separated Value (CSV) rendering extension renders reports as a flattened representation of data from a report in a standardized, plain-text format that is easily readable and exchangeable with many applications.</span></span>  
  
 <span data-ttu-id="2e2bc-104">A extensão de renderização do CSV usa um delimitador de caracteres da cadeia de caracteres para separar campos e linhas, um delimitador configurável para ser um caractere diferente de uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-104">The CSV rendering extension uses a string character delimiter to separate fields and rows, with the string character delimiter configurable to be a character other than a comma.</span></span> <span data-ttu-id="2e2bc-105">O arquivo resultante pode ser aberto em um programa de planilha como o [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] ou pode ser utilizado como um formato de importação para outros programas.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-105">The resulting file can be opened in a spreadsheet program like [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] or used as an import format for other programs.</span></span> <span data-ttu-id="2e2bc-106">O relatório exportado torna-se um arquivo .csv e retorna um tipo MIME de `text/csv`.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-106">The exported report becomes a .csv file, and returns a MIME type of `text/csv`.</span></span>  
  
 <span data-ttu-id="2e2bc-107">Se você quiser trabalhar com dados relacionados a gráficos, barras de dados, minigráficos, medidores e indicadores no [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)], exporte o relatório para um arquivo CSV e abra o arquivo no [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-107">If you want to work with data related to charts, data bars, sparklines, gauges, and indicators in [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)], export the report to a CSV file, and then open the file in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="csv-rendering"></a><a name="CSVRendering"></a> <span data-ttu-id="2e2bc-108">Renderização de CSV</span><span class="sxs-lookup"><span data-stu-id="2e2bc-108">CSV Rendering</span></span>  
 <span data-ttu-id="2e2bc-109">Quando renderizado usando as configurações padrão, um relatório de CSV tem as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="2e2bc-109">When rendered using the default settings, a CSV report has the following characteristics:</span></span>  
  
-   <span data-ttu-id="2e2bc-110">A cadeia de caracteres delimitadora de campo padrão é uma vírgula (,).</span><span class="sxs-lookup"><span data-stu-id="2e2bc-110">The default field delimiter string is a comma (,).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e2bc-111">Você pode alterar o delimitador de campo para qualquer caractere que desejar, inclusive o TAB, alterando as configurações de informações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-111">You can change the field delimiter to any character that you want, including TAB, by changing the device information settings.</span></span> <span data-ttu-id="2e2bc-112">Para obter mais informações, consulte [CSV Device Information Settings](../csv-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2e2bc-112">For more information, see [CSV Device Information Settings](../csv-device-information-settings.md).</span></span>  
  
-   <span data-ttu-id="2e2bc-113">A cadeia de caracteres do delimitador de registro é o retorno de carro e o feed de linha ( \<cr> \<lf> ).</span><span class="sxs-lookup"><span data-stu-id="2e2bc-113">The record delimiter string is the carriage return and line feed (\<cr>\<lf>).</span></span>  
  
-   <span data-ttu-id="2e2bc-114">A cadeia de caracteres qualificadora de texto é formada por aspas (").</span><span class="sxs-lookup"><span data-stu-id="2e2bc-114">The text qualifier string is a quotation mark (").</span></span>  
  
     <span data-ttu-id="2e2bc-115">O renderizador de CSV não adiciona qualificadores ao redor de todas as cadeias de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-115">The CSV renderer does not add qualifiers around all text strings.</span></span> <span data-ttu-id="2e2bc-116">Os qualificadores de texto são adicionados apenas quando o valor contém o caractere delimitador ou uma quebra de linha.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-116">Text qualifiers are added only when the value contains the delimiter character or when the value has a line break.</span></span>  
  
-   <span data-ttu-id="2e2bc-117">Se o texto contiver uma cadeia de caracteres delimitadora inserida ou uma cadeia de caracteres qualificadora, o qualificador de texto será posicionado ao redor do texto e as cadeias de caracteres qualificadoras inseridas serão duplicadas.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-117">If the text contains an embedded delimiter string or qualifier string, the text qualifier is placed around the text, and the embedded qualifier strings are doubled.</span></span>  
  
-   <span data-ttu-id="2e2bc-118">A formatação e o layout são ignorados.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-118">Formatting and layout are ignored.</span></span>  
  
 <span data-ttu-id="2e2bc-119">Os seguintes itens são ignorados durante a renderização:</span><span class="sxs-lookup"><span data-stu-id="2e2bc-119">The following items are ignored during rendering:</span></span>  
  
-   <span data-ttu-id="2e2bc-120">Cabeçalho da página</span><span class="sxs-lookup"><span data-stu-id="2e2bc-120">Page header</span></span>  
  
-   <span data-ttu-id="2e2bc-121">Rodapé</span><span class="sxs-lookup"><span data-stu-id="2e2bc-121">Page footer</span></span>  
  
-   <span data-ttu-id="2e2bc-122">Itens de relatório personalizados</span><span class="sxs-lookup"><span data-stu-id="2e2bc-122">Custom report items</span></span>  
  
-   <span data-ttu-id="2e2bc-123">Linha</span><span class="sxs-lookup"><span data-stu-id="2e2bc-123">Line</span></span>  
  
-   <span data-ttu-id="2e2bc-124">Imagem</span><span class="sxs-lookup"><span data-stu-id="2e2bc-124">Image</span></span>  
  
-   <span data-ttu-id="2e2bc-125">Retângulo</span><span class="sxs-lookup"><span data-stu-id="2e2bc-125">Rectangle</span></span>  
  
-   <span data-ttu-id="2e2bc-126">Subtotais automáticos</span><span class="sxs-lookup"><span data-stu-id="2e2bc-126">Automatic subtotals</span></span>  
  
 <span data-ttu-id="2e2bc-127">Os demais itens do relatório são classificados de cima para baixo e da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-127">The remaining report items are sorted, from top to bottom, then left to right.</span></span> <span data-ttu-id="2e2bc-128">Cada item é renderizado em uma coluna.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-128">Each item is then rendered to a column.</span></span> <span data-ttu-id="2e2bc-129">Se o relatório aninhou itens de dados como listas ou tabelas, os itens pai serão repetidos em cada registro.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-129">If the report has nested data items like lists or tables, the parent items are repeated in each record.</span></span>  
  
 <span data-ttu-id="2e2bc-130">A tabela a seguir indica a aparência de itens de relatório quando renderizados:</span><span class="sxs-lookup"><span data-stu-id="2e2bc-130">The following table indicates the appearance of report items when rendered:</span></span>  
  
|<span data-ttu-id="2e2bc-131">Item</span><span class="sxs-lookup"><span data-stu-id="2e2bc-131">Item</span></span>|<span data-ttu-id="2e2bc-132">Comportamento da renderização</span><span class="sxs-lookup"><span data-stu-id="2e2bc-132">Rendering behavior</span></span>|  
|----------|------------------------|  
|<span data-ttu-id="2e2bc-133">Caixa de texto</span><span class="sxs-lookup"><span data-stu-id="2e2bc-133">Text box</span></span>|<span data-ttu-id="2e2bc-134">Renderiza o conteúdo da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-134">Renders the contents of the text box.</span></span> <span data-ttu-id="2e2bc-135">No modo padrão, os itens são formatados com base nas propriedades de formatação do item.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-135">In default mode, items are formatted based on the item's formatting properties.</span></span> <span data-ttu-id="2e2bc-136">No modo compatível, a formatação pode ser alterada pelas configurações das informações do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-136">In compliant mode, formatting can be changed by device information settings.</span></span> <span data-ttu-id="2e2bc-137">Para obter mais informações sobre os modos de renderização de CSV, consulte as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-137">For more information about CSV rendering modes, see below.</span></span>|  
|<span data-ttu-id="2e2bc-138">Table</span><span class="sxs-lookup"><span data-stu-id="2e2bc-138">Table</span></span>|<span data-ttu-id="2e2bc-139">Renderiza expandindo a tabela e criando uma linha e uma coluna para cada linha e coluna no nível mais baixo de detalhe.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-139">Renders by expanding the table and creating a row and column for each row and column at the lowest level of detail.</span></span> <span data-ttu-id="2e2bc-140">As linhas e colunas de subtotal não têm cabeçalhos de coluna ou de linha.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-140">Subtotal rows and columns do not have column or row headings.</span></span> <span data-ttu-id="2e2bc-141">Não há suporte para relatórios detalhados.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-141">Drillthrough reports are not supported.</span></span>|  
|<span data-ttu-id="2e2bc-142">Matriz</span><span class="sxs-lookup"><span data-stu-id="2e2bc-142">Matrix</span></span>|<span data-ttu-id="2e2bc-143">Renderiza expandindo a matriz e criando uma linha e uma coluna para cada linha e coluna no nível mais baixo de detalhe.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-143">Renders by expanding the matrix and creating a row and column for each row and column at the lowest level of detail.</span></span> <span data-ttu-id="2e2bc-144">As linhas e colunas de subtotal não têm cabeçalhos de coluna ou de linha.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-144">Subtotal rows and columns do not have column or row headings.</span></span>|  
|<span data-ttu-id="2e2bc-145">Lista</span><span class="sxs-lookup"><span data-stu-id="2e2bc-145">List</span></span>|<span data-ttu-id="2e2bc-146">Renderiza um registro para cada linha de detalhes ou instância na lista.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-146">Renders a record for each detail row or instance in the list.</span></span>|  
|<span data-ttu-id="2e2bc-147">Sub-relatório</span><span class="sxs-lookup"><span data-stu-id="2e2bc-147">Subreport</span></span>|<span data-ttu-id="2e2bc-148">O item pai é repetido para cada instância de conteúdos.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-148">The parent item is repeated for each instance of the contents.</span></span>|  
|<span data-ttu-id="2e2bc-149">Gráfico</span><span class="sxs-lookup"><span data-stu-id="2e2bc-149">Chart</span></span>|<span data-ttu-id="2e2bc-150">Renderiza criando uma linha para cada valor de gráfico e rótulos de membro.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-150">Renders by creating a row for each chart value and member labels.</span></span> <span data-ttu-id="2e2bc-151">Os rótulos de séries e categorias em hierarquias são mesclados e incluídos na linha para obter um valor de gráfico.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-151">Labels from series and categories in hierarchies are flattened and included in the row for a chart value.</span></span>|  
|<span data-ttu-id="2e2bc-152">Barra de dados</span><span class="sxs-lookup"><span data-stu-id="2e2bc-152">Data bar</span></span>|<span data-ttu-id="2e2bc-153">Renderiza como um gráfico.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-153">Renders like a chart.</span></span> <span data-ttu-id="2e2bc-154">Normalmente, uma barra de dados não inclui hierarquias ou rótulos.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-154">Typically, a data bar does not include hierarchies or labels.</span></span>|  
|<span data-ttu-id="2e2bc-155">Minigráficos</span><span class="sxs-lookup"><span data-stu-id="2e2bc-155">Sparkline</span></span>|<span data-ttu-id="2e2bc-156">Renderiza como um gráfico.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-156">Renders like a chart.</span></span> <span data-ttu-id="2e2bc-157">Normalmente, um minigráfico não inclui hierarquias ou rótulos.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-157">Typically, a sparkline does not  do not include hierarchies or labels.</span></span>|  
|<span data-ttu-id="2e2bc-158">Medidor</span><span class="sxs-lookup"><span data-stu-id="2e2bc-158">Gauge</span></span>|<span data-ttu-id="2e2bc-159">Renderiza como um único registro com os valores mínimo e máximo da escala linear, valores de início e fim do intervalo e valor do ponteiro.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-159">Renders as a single record with the minimum and maximum values of the linear scale, start and end values of the range, and the value of the pointer.</span></span>|  
|<span data-ttu-id="2e2bc-160">Indicador</span><span class="sxs-lookup"><span data-stu-id="2e2bc-160">Indicator</span></span>|<span data-ttu-id="2e2bc-161">Renderiza como um único registro com o nome do estado ativo, estados disponíveis e o valor de dados.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-161">Renders as a single record with the active state name, available states, and the data value.</span></span>|  
|<span data-ttu-id="2e2bc-162">Mapeamento</span><span class="sxs-lookup"><span data-stu-id="2e2bc-162">Map</span></span>|<span data-ttu-id="2e2bc-163">Renderiza uma linha com os rótulos e os valores para cada membro do mapa de uma camada do mapa.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-163">Renders a row with the labels and values for each map member of a map layer.</span></span><br /><br /> <span data-ttu-id="2e2bc-164">Se o mapa tiver várias camadas, os valores nas linhas variarão, dependendo do fato de as camadas do mapa usarem as mesmas regiões de dados do mapa ou regiões de dados do mapa diferentes.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-164">If the map has multiple layers the values in the rows varies depending on whether the map layers use the same or different map data regions.</span></span> <span data-ttu-id="2e2bc-165">Se várias camadas do mapa usarem a mesma região de dados, as linhas conterão dados de todas as camadas.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-165">If multiple map layers use the same data region, the rows contain data from all layers.</span></span>|  
  
### <a name="hierarchical-and-grouped-data"></a><span data-ttu-id="2e2bc-166">Dados hierárquicos e agrupados</span><span class="sxs-lookup"><span data-stu-id="2e2bc-166">Hierarchical and Grouped Data</span></span>  
 <span data-ttu-id="2e2bc-167">Os dados hierárquicos e agrupados devem ser para ser mesclados para que possam ser representados no formato CSV.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-167">Hierarchical and grouped data must be flattened in order to be represented in the CSV format.</span></span>  
  
 <span data-ttu-id="2e2bc-168">A extensão de renderização mescla o relatório em uma estrutura de árvores que representa os grupos aninhados dentro da região de dados.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-168">The rendering extension flattens the report into a tree structure that represents the nested groups within the data region.</span></span> <span data-ttu-id="2e2bc-169">Para mesclar o relatório:</span><span class="sxs-lookup"><span data-stu-id="2e2bc-169">To flatten the report:</span></span>  
  
-   <span data-ttu-id="2e2bc-170">Uma hierarquia de linha é mesclada antes de uma hierarquia de coluna.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-170">A row hierarchy is flattened before a column hierarchy.</span></span>  
  
-   <span data-ttu-id="2e2bc-171">As colunas são ordenadas da seguinte forma: caixas de texto ordenadas da esquerda para a direita, de cima para baixo, seguida pelas regiões de dados ordenadas da esquerda para a direita, de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-171">Columns are ordered as follows: text boxes in body order left-to-right, top-to-bottom followed by data regions ordered left-to-right, top-to-bottom.</span></span>  
  
-   <span data-ttu-id="2e2bc-172">Dentro da região de dados, as colunas são ordenadas da seguinte maneira: membros do canto, membros da hierarquia de linha, membros da hierarquia de coluna e, em seguida, as células.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-172">Within a data region, the columns are ordered as follows: corner members, row hierarchy members, column hierarchy members, and then cells.</span></span>  
  
-   <span data-ttu-id="2e2bc-173">As regiões de dados semelhantes são grupos de regiões de dados ou grupos dinâmicos que compartilham uma região de dados comum ou o ancestral dinâmico.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-173">Peer data regions are data regions or dynamic groups that share a common data region or dynamic ancestor.</span></span> <span data-ttu-id="2e2bc-174">Os dados pares são identificados pela ramificação da árvore mesclada.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-174">Peer data is identified by branching of the flattened tree.</span></span>  
  
 <span data-ttu-id="2e2bc-175">Para obter mais informações, consulte [Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2e2bc-175">For more information, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="renderer-modes"></a><a name="RenderingModes"></a> <span data-ttu-id="2e2bc-176">Modos do renderizador</span><span class="sxs-lookup"><span data-stu-id="2e2bc-176">Renderer Modes</span></span>  
 <span data-ttu-id="2e2bc-177">A extensão de renderização CSV pode operar em dois modos: um otimizado para o Excel e o outro otimizado para aplicativos de terceiros que requerem total compatibilidade com a especificação CSV no RFC 4180.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-177">The CSV rendering extension can operate in two modes: one is optimized for Excel and the other is optimized for third-party applications that require strict CSV compliance to the CSV specification in RFC 4180.</span></span> <span data-ttu-id="2e2bc-178">Dependendo do modo usado, as regiões de dados semelhantes são controladas de maneira diferente.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-178">Depending on which mode you use, peer data regions are handled differently.</span></span>  
  
### <a name="default-mode"></a><span data-ttu-id="2e2bc-179">Modo Padrão</span><span class="sxs-lookup"><span data-stu-id="2e2bc-179">Default Mode</span></span>  
 <span data-ttu-id="2e2bc-180">O modo Padrão é otimizado para Excel.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-180">The default mode is optimized for Excel.</span></span> <span data-ttu-id="2e2bc-181">Quando renderizado no modo padrão, o relatório é renderizado como um arquivo CSV com várias seções de dados renderizados por CSV.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-181">When rendered in default mode, the report is rendered as a CSV file with multiple sections of CSV-rendered data.</span></span> <span data-ttu-id="2e2bc-182">Cada região de dados semelhante é delimitada por uma linha vazia.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-182">Each peer data region is delimited by an empty line.</span></span> <span data-ttu-id="2e2bc-183">As regiões de dados semelhantes dentro do corpo do relatório são renderizadas como blocos de dados separados dentro do arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-183">Peer data regions within the report body are rendered as separate blocks of data within the CSV file.</span></span> <span data-ttu-id="2e2bc-184">O resultado é um arquivo CSV em que:</span><span class="sxs-lookup"><span data-stu-id="2e2bc-184">The result is a CSV file in which:</span></span>  
  
-   <span data-ttu-id="2e2bc-185">As caixas de texto individuais do relatório são renderizadas como o primeiro bloco de dados dentro do arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-185">Individual text boxes within the report body are rendered once as the first block of data within the CSV file.</span></span>  
  
-   <span data-ttu-id="2e2bc-186">Cada região de dados semelhante de nível superior no corpo do relatório é renderizada em seu próprio bloco de dados.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-186">Each top-level peer data region in the report body is rendered in its own data block.</span></span>  
  
-   <span data-ttu-id="2e2bc-187">As regiões de dados aninhadas são renderizadas diagonalmente no mesmo bloco de dados.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-187">Nested data regions are rendered diagonally into the same data block.</span></span>  
  
#### <a name="formatting"></a><span data-ttu-id="2e2bc-188">Formatação</span><span class="sxs-lookup"><span data-stu-id="2e2bc-188">Formatting</span></span>  
 <span data-ttu-id="2e2bc-189">Os valores numéricos são renderizados em seus estados de formatação.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-189">Numeric values are rendered in their formatted state.</span></span> <span data-ttu-id="2e2bc-190">O Excel pode reconhecer os valores numéricos formatados, como moeda, porcentagem e data, e formatar as células de maneira adequada quando importar o arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-190">Excel can recognize formatted numeric values, such as currency, percentage and date, and format the cells appropriately when importing the CSV file.</span></span>  
  
### <a name="compliant-mode"></a><span data-ttu-id="2e2bc-191">Modo Compatível</span><span class="sxs-lookup"><span data-stu-id="2e2bc-191">Compliant Mode</span></span>  
 <span data-ttu-id="2e2bc-192">O modo Compatível é otimizado para aplicativos de terceiros.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-192">Compliant mode is optimized for third-party applications.</span></span>  
  
#### <a name="data-regions"></a><span data-ttu-id="2e2bc-193">Regiões de Dados</span><span class="sxs-lookup"><span data-stu-id="2e2bc-193">Data Regions</span></span>  
 <span data-ttu-id="2e2bc-194">Apenas a primeira linha do arquivo contém os cabeçalhos de coluna e cada linha tem o mesmo número de colunas.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-194">Only the first row of the file contains the column headers and each row has the same number of columns.</span></span>  
  
#### <a name="formatting"></a><span data-ttu-id="2e2bc-195">Formatação</span><span class="sxs-lookup"><span data-stu-id="2e2bc-195">Formatting</span></span>  
 <span data-ttu-id="2e2bc-196">Os valores não são formatados.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-196">Values are unformatted.</span></span>  
  
##  <a name="interactivity"></a><a name="Interactivity"></a><span data-ttu-id="2e2bc-197">Interatividade</span><span class="sxs-lookup"><span data-stu-id="2e2bc-197">Interactivity</span></span>  
 <span data-ttu-id="2e2bc-198">A interatividade não é suportada por formatos de CSV gerados por este renderizador.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-198">Interactivity is not supported by either CSV formats generated by this renderer.</span></span> <span data-ttu-id="2e2bc-199">Os elementos interativos a seguir não são renderizados:</span><span class="sxs-lookup"><span data-stu-id="2e2bc-199">The following interactive elements are not rendered:</span></span>  
  
-   <span data-ttu-id="2e2bc-200">Hiperlinks</span><span class="sxs-lookup"><span data-stu-id="2e2bc-200">Hyperlinks</span></span>  
  
-   <span data-ttu-id="2e2bc-201">Mostrar ou ocultar</span><span class="sxs-lookup"><span data-stu-id="2e2bc-201">Show or Hide</span></span>  
  
-   <span data-ttu-id="2e2bc-202">Mapa do documento</span><span class="sxs-lookup"><span data-stu-id="2e2bc-202">Document Map</span></span>  
  
-   <span data-ttu-id="2e2bc-203">Links de detalhamento ou de clique</span><span class="sxs-lookup"><span data-stu-id="2e2bc-203">Drillthrough or clickthrough links</span></span>  
  
-   <span data-ttu-id="2e2bc-204">Classificação de usuário final</span><span class="sxs-lookup"><span data-stu-id="2e2bc-204">End user sort</span></span>  
  
-   <span data-ttu-id="2e2bc-205">Cabeçalhos fixos</span><span class="sxs-lookup"><span data-stu-id="2e2bc-205">Fixes headers</span></span>  
  
-   <span data-ttu-id="2e2bc-206">Indicadores</span><span class="sxs-lookup"><span data-stu-id="2e2bc-206">Bookmarks</span></span>  
  

  
##  <a name="device-information-settings"></a><a name="DeviceInfo"></a><span data-ttu-id="2e2bc-207">Configurações de informações do dispositivo</span><span class="sxs-lookup"><span data-stu-id="2e2bc-207">Device Information Settings</span></span>  
 <span data-ttu-id="2e2bc-208">Você pode alterar algumas configurações padrão deste renderizador, incluindo qual o modo de processamento, quais caracteres serão usados como delimitadores e quais caracteres serão usados como a cadeia de caracteres padrão do qualificador de texto, alterando as configurações de informações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2e2bc-208">You can change some default settings for this renderer, including which mode to render in, which characters to use as delimiters and which characters to use as the text qualifier default string, by changing the device information settings.</span></span> <span data-ttu-id="2e2bc-209">Para obter mais informações, consulte [CSV Device Information Settings](../csv-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2e2bc-209">For more information, see [CSV Device Information Settings](../csv-device-information-settings.md).</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="2e2bc-210">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2e2bc-210">See Also</span></span>  
 <span data-ttu-id="2e2bc-211">[Paginação em Reporting Services &#40;Construtor de Relatórios e SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e2bc-211">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2e2bc-212">[Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e2bc-212">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2e2bc-213">[Funcionalidade interativa para extensões de renderização de relatório diferentes &#40;Construtor de Relatórios e SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="2e2bc-213">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 <span data-ttu-id="2e2bc-214">[Renderizando itens de relatório &#40;Construtor de Relatórios e SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e2bc-214">[Rendering Report Items &#40;Report Builder and SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2e2bc-215">Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2e2bc-215">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)  
  
  
