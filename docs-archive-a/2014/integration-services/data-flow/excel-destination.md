---
title: Destino do Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldest.f1
helpviewer_keywords:
- destinations [Integration Services], Excel
- Excel [Integration Services]
ms.assetid: 37c07446-1264-4814-b4f5-9c66d333bb24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e959f14e52fc045cb0cbc2ba0255d20bd0356d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685868"
---
# <a name="excel-destination"></a><span data-ttu-id="a08cb-102">Destino do Excel</span><span class="sxs-lookup"><span data-stu-id="a08cb-102">Excel Destination</span></span>
  <span data-ttu-id="a08cb-103">O destino do Excel carrega dados em planilhas ou intervalos em pastas de trabalho do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="a08cb-103">The Excel destination loads data into worksheets or ranges in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbooks.</span></span>  
  
## <a name="access-modes"></a><span data-ttu-id="a08cb-104">Modos de acesso</span><span class="sxs-lookup"><span data-stu-id="a08cb-104">Access Modes</span></span>  
 <span data-ttu-id="a08cb-105">O destino do Excel fornece três modos de acesso diferentes para carregar dados:</span><span class="sxs-lookup"><span data-stu-id="a08cb-105">The Excel destination provides three different data access modes for loading data:</span></span>  
  
-   <span data-ttu-id="a08cb-106">Uma tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="a08cb-106">A table or view.</span></span>  
  
-   <span data-ttu-id="a08cb-107">Uma tabela ou exibição especificada em uma variável.</span><span class="sxs-lookup"><span data-stu-id="a08cb-107">A table or view specified in a variable.</span></span>  
  
-   <span data-ttu-id="a08cb-108">Os resultados de uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="a08cb-108">The results of an SQL statement.</span></span> <span data-ttu-id="a08cb-109">A consulta pode ser uma consulta parametrizada.</span><span class="sxs-lookup"><span data-stu-id="a08cb-109">The query can be a parameterized query.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a08cb-110">No Excel, uma planilha de trabalho ou intervalo é equivalente a uma tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="a08cb-110">In Excel, a worksheet or range is the equivalent of a table or view.</span></span> <span data-ttu-id="a08cb-111">As listas de tabelas disponíveis nos Editores de Origem e Destino do Excel exibem somente planilhas existentes (identificadas pelo sinal $ anexado ao nome da planilha, por exemplo, Planilha1$) e os intervalos nomeados (identificados pela ausência desse sinal $, como MyRange).</span><span class="sxs-lookup"><span data-stu-id="a08cb-111">The lists of available tables in the Excel Source and Destination editors display only existing worksheets (identified by the $ sign appended to the worksheet name, such as Sheet1$) and named ranges (identified by the absence of the $ sign, such as MyRange).</span></span>  
  
## <a name="usage-considerations"></a><span data-ttu-id="a08cb-112">Considerações de uso</span><span class="sxs-lookup"><span data-stu-id="a08cb-112">Usage Considerations</span></span>  
 <span data-ttu-id="a08cb-113">O Gerenciador de Conexões do Excel usa o Provedor [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB para Jet 4.0 e driver ISAM do Excel com suporte para se conectar, além de ler e gravar dados nas fontes de dados do Excel.</span><span class="sxs-lookup"><span data-stu-id="a08cb-113">The Excel Connection Manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span>  
  
 <span data-ttu-id="a08cb-114">Muitos artigos da Base de Dados de Conhecimento da [!INCLUDE[msCoName](../../includes/msconame-md.md)] documentam o comportamento desse provedor e driver e, embora esses artigos não sejam específicos do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ou de seus serviços de transformação de dados anteriores, talvez você queira obter mais informações sobre determinados comportamentos que podem levar a resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="a08cb-114">Many existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base articles document the behavior of this provider and driver, and although these articles are not specific to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] or its predecessor Data Transformation Services, you may want to know about certain behaviors that can lead to unexpected results.</span></span> <span data-ttu-id="a08cb-115">Para obter informações gerais sobre o uso e comportamento do driver do Excel, consulte [Como usar ADO com dados do Excel do Visual Basic ou do VBA](https://support.microsoft.com/kb/257819).</span><span class="sxs-lookup"><span data-stu-id="a08cb-115">For general information on the use and behavior of the Excel driver, see [HOWTO: Use ADO with Excel Data from Visual Basic or VBA](https://support.microsoft.com/kb/257819).</span></span>  
  
 <span data-ttu-id="a08cb-116">Os seguintes comportamentos do provedor Jet que está incluído no driver do Excel podem levar a resultados inesperados ao salvar dados em um destino do Excel.</span><span class="sxs-lookup"><span data-stu-id="a08cb-116">The following behaviors of the Jet provider that is included with the Excel driver can lead to unexpected results when saving data to an Excel destination.</span></span>  
  
-   <span data-ttu-id="a08cb-117">**Salvando dados de texto**.</span><span class="sxs-lookup"><span data-stu-id="a08cb-117">**Saving text data**.</span></span> <span data-ttu-id="a08cb-118">Quando o driver do Excel salva valores de dados de texto em um destino do Excel, o driver coloca aspas simples (') antes do texto de cada célula para garantir que os valores salvos serão interpretados como texto.</span><span class="sxs-lookup"><span data-stu-id="a08cb-118">When the Excel driver saves text data values to an Excel destination, the driver precedes the text in each cell with the single quote character (') to ensure that the saved values will be interpreted as text values.</span></span> <span data-ttu-id="a08cb-119">Se você tem ou desenvolve outros aplicativos que leem ou processam os dados salvos, será necessário incluir um tratamento especial para as aspas simples que precedem cada texto.</span><span class="sxs-lookup"><span data-stu-id="a08cb-119">If you have or develop other applications that read or process the saved data, you may need to include special handling for the single quote character that precedes each text value.</span></span>  
  
     <span data-ttu-id="a08cb-120">Para obter informações sobre como evitar incluir aspas simples, consulte esta postagem no blog, [Aspas simples são acrescentadas a todas as cadeias de caracteres quando os dados são transformados para Excel ao usar o componente de fluxo de dados de destino do Excel no pacote SSIS](https://go.microsoft.com/fwlink/?LinkId=400876), no msdn.com.</span><span class="sxs-lookup"><span data-stu-id="a08cb-120">For information on how to avoid including the single quote, see this blog post, [Single quote is appended to all strings when data is transformed to excel when using Excel destination data flow component in SSIS package](https://go.microsoft.com/fwlink/?LinkId=400876), on msdn.com.</span></span>  
  
-   <span data-ttu-id="a08cb-121">**Salvando dados de memorando (ntext)**.</span><span class="sxs-lookup"><span data-stu-id="a08cb-121">**Saving memo (ntext) da**ta.</span></span> <span data-ttu-id="a08cb-122">Antes de salvar com sucesso cadeias de caracteres com mais de 255 caracteres em uma coluna do Excel, o driver deve reconhecer o tipo de dados da coluna de destino como **memorando** e não como **cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="a08cb-122">Before you can successfully save strings longer than 255 characters to an Excel column, the driver must recognize the data type of the destination column as **memo** and not **string**.</span></span> <span data-ttu-id="a08cb-123">Se a tabela de destino já contém linhas de dados, então as primeiras linhas que serão amostradas pelo driver devem conter pelo menos uma instância com um valor maior que 255 caracteres na coluna de memorando.</span><span class="sxs-lookup"><span data-stu-id="a08cb-123">If the destination table already contains rows of data, then the first few rows that are sampled by the driver must contain at least one instance of a value longer than 255 characters in the memo column.</span></span> <span data-ttu-id="a08cb-124">Se a tabela de destino for criada durante o design do pacote ou em tempo de execução, a instrução CREATE TABLE deverá usar LONGTEXT (ou um de seus sinônimos) como o tipo de dados da coluna de memorando.</span><span class="sxs-lookup"><span data-stu-id="a08cb-124">If the destination table is created during package design or at run time, then the CREATE TABLE statement must use LONGTEXT (or one of its synonyms) as the data type of the memo column.</span></span>  
  
-   <span data-ttu-id="a08cb-125">**Tipos de dados**.</span><span class="sxs-lookup"><span data-stu-id="a08cb-125">**Data types**.</span></span> <span data-ttu-id="a08cb-126">O driver do Excel reconhece apenas um conjunto limitado de tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="a08cb-126">The Excel driver recognizes only a limited set of data types.</span></span> <span data-ttu-id="a08cb-127">Por exemplo, todas as colunas numéricas são interpretadas como duplas (DT_R8) e todas as colunas de cadeia de caracteres (que não sejam colunas de memorando) são interpretadas como cadeias Unicode de 255 caracteres (DT_WSTR).</span><span class="sxs-lookup"><span data-stu-id="a08cb-127">For example, all numeric columns are interpreted as doubles (DT_R8), and all string columns (other than memo columns) are interpreted as 255-character Unicode strings (DT_WSTR).</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="a08cb-128">mapeia os tipos de dados do Excel da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a08cb-128">maps the Excel data types as follows:</span></span>  
  
    -   <span data-ttu-id="a08cb-129">Numérico    flutuante de precisão dupla (DT_R8)</span><span class="sxs-lookup"><span data-stu-id="a08cb-129">Numeric    double-precision float (DT_R8)</span></span>  
  
    -   <span data-ttu-id="a08cb-130">Moeda     moeda (DT_CY)</span><span class="sxs-lookup"><span data-stu-id="a08cb-130">Currency     currency (DT_CY)</span></span>  
  
    -   <span data-ttu-id="a08cb-131">Booliano     booliano (DT_BOOL)</span><span class="sxs-lookup"><span data-stu-id="a08cb-131">Boolean     Boolean (DT_BOOL)</span></span>  
  
    -   <span data-ttu-id="a08cb-132">Data/hora `datetime` (DT_DATE)</span><span class="sxs-lookup"><span data-stu-id="a08cb-132">Date/time     `datetime` (DT_DATE)</span></span>  
  
    -   <span data-ttu-id="a08cb-133">Cadeia de caracteres     cadeia de caracteres Unicode com 255 caracteres (DT_WSTR)</span><span class="sxs-lookup"><span data-stu-id="a08cb-133">String     Unicode string, length 255 (DT_WSTR)</span></span>  
  
    -   <span data-ttu-id="a08cb-134">Memorando     fluxo de texto Unicode (DT_NTEXT)</span><span class="sxs-lookup"><span data-stu-id="a08cb-134">Memo     Unicode text stream (DT_NTEXT)</span></span>  
  
-   <span data-ttu-id="a08cb-135">**Tipos de dados e conversões de comprimento**.</span><span class="sxs-lookup"><span data-stu-id="a08cb-135">**Data type and length conversions**.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="a08cb-136">não converte tipos de dados implicitamente.</span><span class="sxs-lookup"><span data-stu-id="a08cb-136">does not implicitly convert data types.</span></span> <span data-ttu-id="a08cb-137">Como resultado, talvez seja necessário usar as transformações Coluna Derivada ou Conversão de Dados para converter explicitamente os dados do Excel antes de carregá-los em um destino que não seja Excel ou para converter dados que não sejam do Excel antes de carregá-los em um destino do Excel.</span><span class="sxs-lookup"><span data-stu-id="a08cb-137">As a result, you may need to use the Derived Column or Data Conversion transformations to convert Excel data explicitly before loading it into a non-Excel destination, or to convert non-Excel data before loading it into an Excel destination.</span></span> <span data-ttu-id="a08cb-138">Nesse caso, pode ser útil criar o pacote inicial usando o Assistente de Importação e Exportação, que configura as conversões necessárias.</span><span class="sxs-lookup"><span data-stu-id="a08cb-138">In this case, it may be useful to create the initial package by using the Import and Export Wizard, which configures the necessary conversions for you.</span></span> <span data-ttu-id="a08cb-139">Alguns exemplos de conversões que podem ser necessárias incluem:</span><span class="sxs-lookup"><span data-stu-id="a08cb-139">Some examples of the conversions that may be required include the following:</span></span>  
  
    -   <span data-ttu-id="a08cb-140">Conversão entre colunas de cadeia de caracteres Unicode e não Unicode do Excel com páginas de código específicas.</span><span class="sxs-lookup"><span data-stu-id="a08cb-140">Conversion between Unicode Excel string columns and non-Unicode string columns with specific codepages.</span></span>  
  
    -   <span data-ttu-id="a08cb-141">Conversão entre colunas de cadeia de 255 caracteres e de comprimentos diferentes do Excel.</span><span class="sxs-lookup"><span data-stu-id="a08cb-141">Conversion between 255-character Excel string columns and string columns of different lengths.</span></span>  
  
    -   <span data-ttu-id="a08cb-142">Conversão entre colunas numéricas de precisão dupla e outros tipos de colunas numéricas do Excel.</span><span class="sxs-lookup"><span data-stu-id="a08cb-142">Conversion between double-precision Excel numeric columns and numeric columns of other types.</span></span>  
  
## <a name="configuration-of-the-excel-destination"></a><span data-ttu-id="a08cb-143">Configuração do destino do Excel</span><span class="sxs-lookup"><span data-stu-id="a08cb-143">Configuration of the Excel Destination</span></span>  
 <span data-ttu-id="a08cb-144">O destino do Excel usa um gerenciador de conexões do Excel para se conectar a uma fonte de dados e o gerenciador de conexões especifica o arquivo de pasta de trabalho a ser usado.</span><span class="sxs-lookup"><span data-stu-id="a08cb-144">The Excel destination uses an Excel connection manager to connect to a data source, and the connection manager specifies the workbook file to use.</span></span> <span data-ttu-id="a08cb-145">Para obter mais informações, consulte [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a08cb-145">For more information, see [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span></span>  
  
 <span data-ttu-id="a08cb-146">O destino do Excel tem uma entrada regular e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="a08cb-146">The Excel destination has one regular input and one error output.</span></span>  
  
 <span data-ttu-id="a08cb-147">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="a08cb-147">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="a08cb-148">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Destinos do Excel** , clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="a08cb-148">For more information about the properties that you can set in the **Excel Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a08cb-149">Editor de Destinos do Excel &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="a08cb-149">Excel Destination Editor &#40;Connection Manager Page&#41;</span></span>](../excel-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="a08cb-150">Editor de Destinos do Excel &#40;página Mapeamentos&#41;</span><span class="sxs-lookup"><span data-stu-id="a08cb-150">Excel Destination Editor &#40;Mappings Page&#41;</span></span>](../excel-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="a08cb-151">Editor de Destinos do Excel &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="a08cb-151">Excel Destination Editor &#40;Error Output Page&#41;</span></span>](../excel-destination-editor-error-output-page.md)  
  
 <span data-ttu-id="a08cb-152">A caixa de diálogo **Editor Avançado** reflete todas as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="a08cb-152">The **Advanced Editor** dialog box reflects all the properties that can be set programmatically.</span></span> <span data-ttu-id="a08cb-153">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="a08cb-153">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a08cb-154">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="a08cb-154">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="a08cb-155">Propriedades personalizadas do Excel</span><span class="sxs-lookup"><span data-stu-id="a08cb-155">Excel Custom Properties</span></span>](excel-custom-properties.md)  
  
 <span data-ttu-id="a08cb-156">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a08cb-156">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a08cb-157">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a08cb-157">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a08cb-158">Importar dados do Excel ou exportar dados para o Excel com o SSIS (SQL Server Integration Services)</span><span class="sxs-lookup"><span data-stu-id="a08cb-158">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)  
  
-   [<span data-ttu-id="a08cb-159">Loop através de arquivos e tabelas do Excel por meio de um contêiner do Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="a08cb-159">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="a08cb-160">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="a08cb-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="a08cb-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a08cb-161">See Also</span></span>  
 <span data-ttu-id="a08cb-162">[Origem do Excel](excel-source.md) </span><span class="sxs-lookup"><span data-stu-id="a08cb-162">[Excel Source](excel-source.md) </span></span>  
 <span data-ttu-id="a08cb-163">[Variáveis do SSIS &#40;Integration Services&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="a08cb-163">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="a08cb-164">[Fluxo de Dados](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="a08cb-164">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="a08cb-165">Trabalhar com arquivos do Excel com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="a08cb-165">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
  
  
