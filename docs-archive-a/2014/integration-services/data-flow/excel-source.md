---
title: Origem do Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsource.f1
helpviewer_keywords:
- Excel [Integration Services]
- sources [Integration Services], Excel
ms.assetid: e66349f3-b1b8-4763-89b7-7803541a4d62
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1324ca9e9b9535b8598e3e2de22f6c06c350b7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685870"
---
# <a name="excel-source"></a><span data-ttu-id="79d6f-102">Origem do Excel</span><span class="sxs-lookup"><span data-stu-id="79d6f-102">Excel Source</span></span>
  <span data-ttu-id="79d6f-103">A origem do Excel extrai dados de planilhas ou intervalos em pastas de trabalho do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="79d6f-103">The Excel source extracts data from worksheets or ranges in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbooks.</span></span>  
  
 <span data-ttu-id="79d6f-104">A origem do Excel fornece quatro modos de acesso a dados diferentes para extrair dados:</span><span class="sxs-lookup"><span data-stu-id="79d6f-104">The Excel source provides four different data access modes for extracting data:</span></span>  
  
-   <span data-ttu-id="79d6f-105">Uma tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="79d6f-105">A table or view.</span></span>  
  
-   <span data-ttu-id="79d6f-106">Uma tabela ou exibição especificada em uma variável.</span><span class="sxs-lookup"><span data-stu-id="79d6f-106">A table or view specified in a variable.</span></span>  
  
-   <span data-ttu-id="79d6f-107">Os resultados de uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="79d6f-107">The results of an SQL statement.</span></span> <span data-ttu-id="79d6f-108">A consulta pode ser uma consulta parametrizada.</span><span class="sxs-lookup"><span data-stu-id="79d6f-108">The query can be a parameterized query.</span></span>  
  
-   <span data-ttu-id="79d6f-109">Os resultados de uma instrução SQL armazenados em uma variável.</span><span class="sxs-lookup"><span data-stu-id="79d6f-109">The results of an SQL statement stored in a variable.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="79d6f-110">No Excel, uma planilha de trabalho ou intervalo é equivalente a uma tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="79d6f-110">In Excel, a worksheet or range is the equivalent of a table or view.</span></span> <span data-ttu-id="79d6f-111">A lista de tabelas disponíveis nos Editores de Origem e Destino do Excel exibe planilhas de trabalho existentes (identificadas pelo sinal $ anexado ao nome da planilha, por exemplo, Planilha1$) e os intervalos nomeados (identificados pela ausência desse sinal $, como Meu Intervalo).</span><span class="sxs-lookup"><span data-stu-id="79d6f-111">The list of available tables in the Excel Source and Destination editors displays existing worksheets (identified by the $ sign appended to the worksheet name, such as Sheet1$) and named ranges (identified by the absence of the $ sign, such as MyRange).</span></span> <span data-ttu-id="79d6f-112">Para obter mais informações, consulte a seção de Considerações de uso.</span><span class="sxs-lookup"><span data-stu-id="79d6f-112">For more information, see the Usage Considerations section.</span></span>  
  
 <span data-ttu-id="79d6f-113">A origem do Excel usa um gerenciador de conexões do Excel para se conectar a uma fonte de dados e o gerenciador de conexões especifica o arquivo da planilha de trabalho a ser usado.</span><span class="sxs-lookup"><span data-stu-id="79d6f-113">The Excel source uses an Excel connection manager to connect to a data source, and the connection manager specifies the workbook file to use.</span></span> <span data-ttu-id="79d6f-114">Para obter mais informações, consulte [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="79d6f-114">For more information, see [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span></span>  
  
 <span data-ttu-id="79d6f-115">A origem do Excel tem uma saída comum e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="79d6f-115">The Excel source has one regular output and one error output.</span></span>  
  
## <a name="usage-considerations"></a><span data-ttu-id="79d6f-116">Considerações de uso</span><span class="sxs-lookup"><span data-stu-id="79d6f-116">Usage Considerations</span></span>  
 <span data-ttu-id="79d6f-117">O Gerenciador de Conexões do Excel usa o Provedor [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB para Jet 4.0 e driver ISAM do Excel com suporte para se conectar, além de ler e gravar dados nas fontes de dados do Excel.</span><span class="sxs-lookup"><span data-stu-id="79d6f-117">The Excel Connection Manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span>  
  
 <span data-ttu-id="79d6f-118">Muitos artigos da Base de Dados de Conhecimento da [!INCLUDE[msCoName](../../includes/msconame-md.md)] documentam o comportamento desse provedor e driver e, embora esses artigos não sejam específicos do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ou de seus serviços de transformação de dados anteriores, talvez você queira obter mais informações sobre determinados comportamentos que podem levar a resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="79d6f-118">Many existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base articles document the behavior of this provider and driver, and although these articles are not specific to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] or its predecessor Data Transformation Services, you may want to know about certain behaviors that can lead to unexpected results.</span></span> <span data-ttu-id="79d6f-119">Para obter informações gerais sobre o uso e comportamento do driver do Excel, consulte [Como usar ADO com dados do Excel do Visual Basic ou do VBA](https://support.microsoft.com/kb/257819).</span><span class="sxs-lookup"><span data-stu-id="79d6f-119">For general information on the use and behavior of the Excel driver, see [HOWTO: Use ADO with Excel Data from Visual Basic or VBA](https://support.microsoft.com/kb/257819).</span></span>  
  
 <span data-ttu-id="79d6f-120">Os seguintes comportamentos do provedor Jet com o driver do Excel podem levar a resultados inesperados ao ler dados de uma fonte de dados do Excel.</span><span class="sxs-lookup"><span data-stu-id="79d6f-120">The following behaviors of the Jet provider with the Excel driver can lead to unexpected results when reading data from an Excel data source.</span></span>  
  
-   <span data-ttu-id="79d6f-121">**Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="79d6f-121">**Data sources**.</span></span> <span data-ttu-id="79d6f-122">A fonte de dados em uma pasta de trabalho do Excel pode ser uma planilha de trabalho, à qual o sinal $ deve ser anexado (por exemplo, Planilha1$), ou um intervalo nomeado (por exemplo, MeuIntervalo).</span><span class="sxs-lookup"><span data-stu-id="79d6f-122">The source of data in an Excel workbook can be a worksheet, to which the $ sign must be appended (for example, Sheet1$), or a named range (for example, MyRange).</span></span> <span data-ttu-id="79d6f-123">Em uma instrução SQL, o nome de uma planilha de trabalho deve ser delimitado (por exemplo, [Planilha1$]) para evitar um erro de sintaxe causado pelo sinal $.</span><span class="sxs-lookup"><span data-stu-id="79d6f-123">In a SQL statement, the name of a worksheet must be delimited (for example, [Sheet1$]) to avoid a syntax error caused by the $ sign.</span></span> <span data-ttu-id="79d6f-124">O Construtor de Consultas adiciona automaticamente esses delimitadores.</span><span class="sxs-lookup"><span data-stu-id="79d6f-124">The Query Builder automatically adds these delimiters.</span></span> <span data-ttu-id="79d6f-125">Quando você especifica uma planilha de trabalho ou um intervalo, o driver lê o bloco contínuo de células começando com a primeira célula não vazia no canto superior esquerdo da planilha de trabalho ou do intervalo.</span><span class="sxs-lookup"><span data-stu-id="79d6f-125">When you specify a worksheet or range, the driver reads the contiguous block of cells starting with the first non-empty cell in the upper-left corner of the worksheet or range.</span></span> <span data-ttu-id="79d6f-126">Dessa forma, você não pode ter linhas vazias nos dados de origem ou uma linha vazia entre o título ou as linhas de cabeçalho e de dados.</span><span class="sxs-lookup"><span data-stu-id="79d6f-126">Therefore you cannot have empty rows in the source data, or an empty row between title or header rows and the data rows.</span></span>  
  
-   <span data-ttu-id="79d6f-127">**Valores ausentes**.</span><span class="sxs-lookup"><span data-stu-id="79d6f-127">**Missing values**.</span></span> <span data-ttu-id="79d6f-128">O driver do Excel lê um determinado número de linhas (por padrão, 8 linhas) na fonte especificada para determinar o tipo de dados de cada coluna.</span><span class="sxs-lookup"><span data-stu-id="79d6f-128">The Excel driver reads a certain number of rows (by default, 8 rows) in the specified source to guess at the data type of each column.</span></span> <span data-ttu-id="79d6f-129">Quando uma coluna parece conter tipos de dados mistos, especialmente dados numéricos combinados com dados de texto, o driver decide em favor do tipo de dados majoritário e retorna valores nulos para as células que contêm dados de outro tipo.</span><span class="sxs-lookup"><span data-stu-id="79d6f-129">When a column appears to contain mixed data types, especially numeric data mixed with text data, the driver decides in favor of the majority data type, and returns null values for cells that contain data of the other type.</span></span> <span data-ttu-id="79d6f-130">(Em uma ligação, o tipo numérico vence.) A maioria das opções de formatação de células na planilha de trabalho do Excel não parece afetar a determinação desse tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="79d6f-130">(In a tie, the numeric type wins.) Most cell formatting options in the Excel worksheet do not seem to affect this data type determination.</span></span> <span data-ttu-id="79d6f-131">Você pode modificar esse comportamento de driver do Excel especificando Modo de Importação.</span><span class="sxs-lookup"><span data-stu-id="79d6f-131">You can modify this behavior of the Excel driver by specifying Import Mode.</span></span> <span data-ttu-id="79d6f-132">Para especificar o modo de importação, adicione `IMEX=1` ao valor de propriedades estendidas na cadeia de conexão do Gerenciador de conexões do Excel na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="79d6f-132">To specify Import Mode, add `IMEX=1` to the value of Extended Properties in the connection string of the Excel connection manager in the **Properties** window.</span></span> <span data-ttu-id="79d6f-133">Para obter mais informações, consulte [PRB: valores do Excel retornados como NULOS usando DAO OpenRecordset](https://support.microsoft.com/kb/194124).</span><span class="sxs-lookup"><span data-stu-id="79d6f-133">For more information, see [PRB: Excel Values Returned as NULL Using DAO OpenRecordset](https://support.microsoft.com/kb/194124).</span></span>  
  
-   <span data-ttu-id="79d6f-134">**Texto truncado**.</span><span class="sxs-lookup"><span data-stu-id="79d6f-134">**Truncated text**.</span></span> <span data-ttu-id="79d6f-135">Quando o driver determina que uma coluna do Excel contém dados de texto, ele seleciona o tipo de dados (cadeia ou memorando) com base no valor mais longo que ele obtém.</span><span class="sxs-lookup"><span data-stu-id="79d6f-135">When the driver determines that an Excel column contains text data, the driver selects the data type (string or memo) based on the longest value that it samples.</span></span> <span data-ttu-id="79d6f-136">Se o driver não descobre nenhum valor maior que 255 caracteres nas linhas que ele verifica, ele trata a coluna como uma coluna de cadeia de 255 caracteres, não como uma coluna de memorando.</span><span class="sxs-lookup"><span data-stu-id="79d6f-136">If the driver does not discover any values longer than 255 characters in the rows that it samples, it treats the column as a 255-character string column instead of a memo column.</span></span> <span data-ttu-id="79d6f-137">Assim, valores com mais de 255 caracteres podem estar truncados.</span><span class="sxs-lookup"><span data-stu-id="79d6f-137">Therefore, values longer than 255 characters may be truncated.</span></span> <span data-ttu-id="79d6f-138">Para importar dados de uma coluna de memorando sem que haja truncamento, você deve certificar-se de que essa coluna, em pelo menos uma das linhas de amostra, contenha um valor com mais 255 caracteres ou deve aumentar o número de linhas de amostra pelo driver para incluir esse tipo de linha.</span><span class="sxs-lookup"><span data-stu-id="79d6f-138">To import data from a memo column without truncation, you must make sure that the memo column in at least one of the sampled rows contains a value longer than 255 characters, or you must increase the number of rows sampled by the driver to include such a row.</span></span> <span data-ttu-id="79d6f-139">Você pode aumentar o número de linhas de amostra aumentando o valor de **TypeGuessRows** na chave do Registro **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Jet\4.0\Engines\Excel** .</span><span class="sxs-lookup"><span data-stu-id="79d6f-139">You can increase the number of rows sampled by increasing the value of **TypeGuessRows** under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Jet\4.0\Engines\Excel** registry key.</span></span> <span data-ttu-id="79d6f-140">Para obter mais informações, consulte [PRB: a transferência de dados da fonte Jet 4.0 OLEDB falha com erro](https://support.microsoft.com/kb/281517).</span><span class="sxs-lookup"><span data-stu-id="79d6f-140">For more information, see [PRB: Transfer of Data from Jet 4.0 OLEDB Source Fails w/ Error](https://support.microsoft.com/kb/281517).</span></span>  
  
-   <span data-ttu-id="79d6f-141">**Tipos de dados**.</span><span class="sxs-lookup"><span data-stu-id="79d6f-141">**Data types**.</span></span> <span data-ttu-id="79d6f-142">O driver do Excel reconhece apenas um conjunto limitado de tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="79d6f-142">The Excel driver recognizes only a limited set of data types.</span></span> <span data-ttu-id="79d6f-143">Por exemplo, todas as colunas numéricas são interpretadas como duplas (DT_R8) e todas as colunas de cadeia de caracteres (que não sejam colunas de memorando) são interpretadas como cadeias Unicode de 255 caracteres (DT_WSTR).</span><span class="sxs-lookup"><span data-stu-id="79d6f-143">For example, all numeric columns are interpreted as doubles (DT_R8), and all string columns (other than memo columns) are interpreted as 255-character Unicode strings (DT_WSTR).</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="79d6f-144">mapeia os tipos de dados do Excel da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="79d6f-144">maps the Excel data types as follows:</span></span>  
  
    -   <span data-ttu-id="79d6f-145">Numérico – flutuante de precisão dupla (DT_R8)</span><span class="sxs-lookup"><span data-stu-id="79d6f-145">Numeric - double-precision float (DT_R8)</span></span>  
  
    -   <span data-ttu-id="79d6f-146">Moeda – moeda (DT_CY)</span><span class="sxs-lookup"><span data-stu-id="79d6f-146">Currency - currency (DT_CY)</span></span>  
  
    -   <span data-ttu-id="79d6f-147">Booliano – booliano (DT_BOOL)</span><span class="sxs-lookup"><span data-stu-id="79d6f-147">Boolean - Boolean (DT_BOOL)</span></span>  
  
    -   <span data-ttu-id="79d6f-148">Data/hora- `datetime` (DT_DATE)</span><span class="sxs-lookup"><span data-stu-id="79d6f-148">Date/time - `datetime` (DT_DATE)</span></span>  
  
    -   <span data-ttu-id="79d6f-149">Cadeia de caracteres – cadeia Unicode, 255 de comprimento (DT_WSTR)</span><span class="sxs-lookup"><span data-stu-id="79d6f-149">String - Unicode string, length 255 (DT_WSTR)</span></span>  
  
    -   <span data-ttu-id="79d6f-150">Memorando – fluxo de texto Unicode (DT_NTEXT)</span><span class="sxs-lookup"><span data-stu-id="79d6f-150">Memo - Unicode text stream (DT_NTEXT)</span></span>  
  
-   <span data-ttu-id="79d6f-151">**Tipos de dados e conversões de comprimento**.</span><span class="sxs-lookup"><span data-stu-id="79d6f-151">**Data type and length conversions**.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="79d6f-152">não converte tipos de dados implicitamente.</span><span class="sxs-lookup"><span data-stu-id="79d6f-152">does not implicitly convert data types.</span></span> <span data-ttu-id="79d6f-153">Como resultado, você pode precisar usar as transformações Coluna Derivada ou Conversão de Dados para converter explicitamente dados do Excel antes de carregá-los em um destino que não seja Excel ou para converter dados que não sejam do Excel antes de carregá-los em um destino Excel.</span><span class="sxs-lookup"><span data-stu-id="79d6f-153">As a result, you may need to use Derived Column or Data Conversion transformations to convert Excel data explicitly before loading it into a non-Excel destination, or to convert non-Excel data before loading it into an Excel destination.</span></span> <span data-ttu-id="79d6f-154">Nesse caso, pode ser útil criar o pacote inicial usando o Assistente de Importação e Exportação, que configura as conversões necessárias.</span><span class="sxs-lookup"><span data-stu-id="79d6f-154">In this case, it may be useful to create the initial package by using the Import and Export Wizard, which configures the necessary conversions for you.</span></span> <span data-ttu-id="79d6f-155">Alguns exemplos de conversões que podem ser necessárias incluem:</span><span class="sxs-lookup"><span data-stu-id="79d6f-155">Some examples of the conversions that may be required include the following:</span></span>  
  
    -   <span data-ttu-id="79d6f-156">Conversão entre colunas de cadeias Unicode e não Unicode do Excel com páginas de código específicas</span><span class="sxs-lookup"><span data-stu-id="79d6f-156">Conversion between Unicode Excel string columns and non-Unicode string columns with specific codepages</span></span>  
  
    -   <span data-ttu-id="79d6f-157">Conversão entre colunas de cadeias de 255 caracteres e de comprimentos diferentes do Excel</span><span class="sxs-lookup"><span data-stu-id="79d6f-157">Conversion between 255-character Excel string columns and string columns of different lengths</span></span>  
  
    -   <span data-ttu-id="79d6f-158">Conversão entre colunas numéricas de precisão dupla e de outros tipos de colunas numéricas do Excel</span><span class="sxs-lookup"><span data-stu-id="79d6f-158">Conversion between double-precision Excel numeric columns and numeric columns of other types</span></span>  
  
## <a name="excel-source-configuration"></a><span data-ttu-id="79d6f-159">Configuração da origem do Excel</span><span class="sxs-lookup"><span data-stu-id="79d6f-159">Excel Source Configuration</span></span>  
 <span data-ttu-id="79d6f-160">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="79d6f-160">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="79d6f-161">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Origem do Excel** clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="79d6f-161">For more information about the properties that you can set in the **Excel Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="79d6f-162">Editor de Origem do Excel &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="79d6f-162">Excel Source Editor &#40;Connection Manager Page&#41;</span></span>](../excel-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="79d6f-163">Editor de Fonte do Excel &#40;Página Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="79d6f-163">Excel Source Editor &#40;Columns Page&#41;</span></span>](../excel-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="79d6f-164">Editor de Origem do Excel &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="79d6f-164">Excel Source Editor &#40;Error Output Page&#41;</span></span>](../excel-source-editor-error-output-page.md)  
  
 <span data-ttu-id="79d6f-165">A caixa de diálogo **Editor Avançado** reflete todas as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="79d6f-165">The **Advanced Editor** dialog box reflects all the properties that can be set programmatically.</span></span> <span data-ttu-id="79d6f-166">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="79d6f-166">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="79d6f-167">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="79d6f-167">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="79d6f-168">Propriedades personalizadas do Excel</span><span class="sxs-lookup"><span data-stu-id="79d6f-168">Excel Custom Properties</span></span>](excel-custom-properties.md)  
  
 <span data-ttu-id="79d6f-169">Para obter informações sobre loop através de um grupo de arquivos do Excel, consulte [Loop por meio de arquivos do Excel e tabelas usando um contêiner de Loop Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="79d6f-169">For information about looping through a group of Excel files, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="79d6f-170">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="79d6f-170">Related Tasks</span></span>  

-   [<span data-ttu-id="79d6f-171">Importar dados do Excel ou exportar dados para o Excel com o SSIS (SQL Server Integration Services)</span><span class="sxs-lookup"><span data-stu-id="79d6f-171">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)

-   [<span data-ttu-id="79d6f-172">Mapear parâmetros de consulta para variáveis em um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="79d6f-172">Map Query Parameters to Variables in a Data Flow Component</span></span>](map-query-parameters-to-variables-in-a-data-flow-component.md)  
  
-   [<span data-ttu-id="79d6f-173">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="79d6f-173">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="79d6f-174">Classificar dados para as transformações Mesclagem e Junção de Mesclagem</span><span class="sxs-lookup"><span data-stu-id="79d6f-174">Sort Data for the Merge and Merge Join Transformations</span></span>](transformations/sort-data-for-the-merge-and-merge-join-transformations.md)  
  
-   [<span data-ttu-id="79d6f-175">Loop através de arquivos e tabelas do Excel por meio de um contêiner do Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="79d6f-175">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
## <a name="related-content"></a><span data-ttu-id="79d6f-176">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="79d6f-176">Related Content</span></span>  
  
-   <span data-ttu-id="79d6f-177">Entrada de blog, [Importando dados do Excel de 64 bits no SSIS](https://go.microsoft.com/fwlink/?LinkId=217673), em hrvoje.piasevoli.com</span><span class="sxs-lookup"><span data-stu-id="79d6f-177">Blog entry, [Importing data from 64-bit Excel in SSIS](https://go.microsoft.com/fwlink/?LinkId=217673), on hrvoje.piasevoli.com</span></span>  
  
-   <span data-ttu-id="79d6f-178">Entrada de blog, [conectando ao Excel (xlsx) no SSIS](https://microsoft-ssis.blogspot.com/2014/02/connecting-to-excel-xlsx-in-ssis.html).</span><span class="sxs-lookup"><span data-stu-id="79d6f-178">Blog entry, [Connecting to Excel (XLSX) in SSIS](https://microsoft-ssis.blogspot.com/2014/02/connecting-to-excel-xlsx-in-ssis.html).</span></span>  
  
  