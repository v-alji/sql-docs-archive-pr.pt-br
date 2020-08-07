---
title: Origem ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.f1
ms.assetid: abcf34eb-9140-4100-82e6-b85bccd22abe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 792557839d60f34bdf944dab150959d4df7cb8cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571485"
---
# <a name="odbc-source"></a><span data-ttu-id="bfedd-102">Origem ODBC</span><span class="sxs-lookup"><span data-stu-id="bfedd-102">ODBC Source</span></span>
  <span data-ttu-id="bfedd-103">A origem ODBC extrai dados de um banco de dados com suporte do ODBC usando uma tabela de banco de dados, uma exibição ou uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="bfedd-103">The ODBC source extracts data from ODBC-supported database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="bfedd-104">A origem ODBC tem os seguintes modos de acesso a dados para extrair dados:</span><span class="sxs-lookup"><span data-stu-id="bfedd-104">The ODBC source has the following data access modes for extracting data:</span></span>  
  
-   <span data-ttu-id="bfedd-105">Uma tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="bfedd-105">A table or view.</span></span>  
  
-   <span data-ttu-id="bfedd-106">Os resultados de uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="bfedd-106">The results of an SQL statement.</span></span>  
  
 <span data-ttu-id="bfedd-107">A origem usa um gerenciador de conexões ODBC que especifica o provedor a ser usado.</span><span class="sxs-lookup"><span data-stu-id="bfedd-107">The source uses an ODBC connection manager, which specifies the provider to use.</span></span>  
  
 <span data-ttu-id="bfedd-108">Uma origem ODBC inclui as colunas de saída dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="bfedd-108">An ODBC source includes the source data output columns.</span></span> <span data-ttu-id="bfedd-109">Quando colunas de saída são mapeadas no destino ODBC para as colunas de destino, poderão ocorrer erros se nenhuma coluna de saída for mapeada para as colunas de destino.</span><span class="sxs-lookup"><span data-stu-id="bfedd-109">When output columns are mapped in the ODBC destination to the destination columns, errors may occur if no output columns are mapped to the destination columns.</span></span> <span data-ttu-id="bfedd-110">Colunas de tipos diferentes podem ser mapeadas, porém se os dados de saída não forem compatíveis com o destino, um erro ocorrerá em runtime.</span><span class="sxs-lookup"><span data-stu-id="bfedd-110">Columns of different types can be mapped, however if the output data is not compatible for the destination then an error occurs at runtime.</span></span> <span data-ttu-id="bfedd-111">Dependendo da configuração de comportamento do erro, o erro será ignorado, causará uma falha ou a linha será enviada à saída de erro.</span><span class="sxs-lookup"><span data-stu-id="bfedd-111">Depending on the error behavior, setting the error will be ignored, cause a failure, or the row is sent to the error output.</span></span>  
  
 <span data-ttu-id="bfedd-112">A origem ODBC tem uma saída regular e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="bfedd-112">The ODBC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="bfedd-113">Tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="bfedd-113">Error Handling</span></span>  
 <span data-ttu-id="bfedd-114">A origem ODBC tem uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="bfedd-114">The ODBC source has an error output.</span></span> <span data-ttu-id="bfedd-115">A saída de erro de componente inclui as colunas de saída seguintes:</span><span class="sxs-lookup"><span data-stu-id="bfedd-115">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="bfedd-116">**Código de Erro**: o número que corresponde ao erro atual.</span><span class="sxs-lookup"><span data-stu-id="bfedd-116">**Error Code**: The number that corresponds to the current error.</span></span> <span data-ttu-id="bfedd-117">Consulte a documentação do banco de dados com suporte do ODBC que você está usando para obter uma lista de erros.</span><span class="sxs-lookup"><span data-stu-id="bfedd-117">See the documentation for the ODBC-supported database you are using for a list of errors.</span></span> <span data-ttu-id="bfedd-118">Para obter uma lista dos códigos de erro SSIS, consulte a Referência de código e mensagem de erro SSIS.</span><span class="sxs-lookup"><span data-stu-id="bfedd-118">For a list of SSIS error codes, see the SSIS Error Code and Message Reference.</span></span>  
  
-   <span data-ttu-id="bfedd-119">**Coluna de Erro**: a coluna de origem que causa o erro (para erros de conversão).</span><span class="sxs-lookup"><span data-stu-id="bfedd-119">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="bfedd-120">As colunas de dados de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="bfedd-120">The standard output data columns.</span></span>  
  
 <span data-ttu-id="bfedd-121">Dependendo da configuração de comportamento de erro, a origem ODBC oferece suporte ao retorno de erros (conversão de dados, truncamento) que ocorre durante o processo de extração na saída de erro.</span><span class="sxs-lookup"><span data-stu-id="bfedd-121">Depending on the error behavior setting, the ODBC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="bfedd-122">Para obter mais informações, consulte [Editor do Destino ODBC &#40;Página Gerenciador de Conexões&#41;](../odbc-destination-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="bfedd-122">For more information, see [ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="bfedd-123">Suporte do tipo de dados</span><span class="sxs-lookup"><span data-stu-id="bfedd-123">Data Type Support</span></span>  
 <span data-ttu-id="bfedd-124">Para obter informações sobre os tipos de dados com suporte da origem ODBC, consulte Conector para ODBC da Attunity.</span><span class="sxs-lookup"><span data-stu-id="bfedd-124">For information about the data types supported by the ODBC source, see Connector for Open Database Connectivity (ODBC) by Attunity.</span></span>  
  
## <a name="extract-options"></a><span data-ttu-id="bfedd-125">Extrair opções</span><span class="sxs-lookup"><span data-stu-id="bfedd-125">Extract Options</span></span>  
 <span data-ttu-id="bfedd-126">A origem ODBC opera no modo **Lote** ou **Linha a Linha** .</span><span class="sxs-lookup"><span data-stu-id="bfedd-126">The ODBC source operates in either **Batch** or **Row-by-Row** mode.</span></span> <span data-ttu-id="bfedd-127">O modo usado é determinado pela propriedade **FetchMethod** .</span><span class="sxs-lookup"><span data-stu-id="bfedd-127">The mode used is determined by the **FetchMethod** property.</span></span> <span data-ttu-id="bfedd-128">A lista seguinte descreve os modos.</span><span class="sxs-lookup"><span data-stu-id="bfedd-128">The following list describes the modes.</span></span>  
  
-   <span data-ttu-id="bfedd-129">**Lote**: o componente tenta usar o método de busca mais eficiente com base no provedor ODBC percebido.</span><span class="sxs-lookup"><span data-stu-id="bfedd-129">**Batch**: The component attempts to use the most efficient fetch method based on the perceived ODBC provider capabilities.</span></span> <span data-ttu-id="bfedd-130">Para a maioria dos provedores ODBC modernos, esse é SQLFetchScroll com associação de matriz (em que o tamanho da matriz é determinado pela propriedade **BatchSize** ).</span><span class="sxs-lookup"><span data-stu-id="bfedd-130">For most modern ODBC providers, this is SQLFetchScroll with array binding (where the array size is determined by the **BatchSize** property).</span></span> <span data-ttu-id="bfedd-131">Se você selecionar **Lote** e o provedor não oferecer suporte a esse método, o destino ODBC alternará automaticamente para modo **Linha a linha** .</span><span class="sxs-lookup"><span data-stu-id="bfedd-131">If you select **Batch** and the provider does not support this method, the ODBC destination automatically switches to the **Row-by-row** mode.</span></span>  
  
-   <span data-ttu-id="bfedd-132">**Linha a linha**: o componente usa SQLFetch para recuperar as linhas uma de cada vez.</span><span class="sxs-lookup"><span data-stu-id="bfedd-132">**Row-by Row**: The component uses SQLFetch to retrieve the rows one at a time.</span></span>  
  
 <span data-ttu-id="bfedd-133">Para obter mais informações sobre a propriedade **FetchMethod** , consulte [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="bfedd-133">For more information about the **FetchMethod** property, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="parallelism"></a><span data-ttu-id="bfedd-134">Paralelismo</span><span class="sxs-lookup"><span data-stu-id="bfedd-134">Parallelism</span></span>  
 <span data-ttu-id="bfedd-135">Não há nenhuma limitação no número de componentes de origem ODBC que podem ser executados em paralelo na mesma tabela ou tabelas diferentes, na mesma máquina ou em máquinas diferentes (diferente de limites de sessão globais normais).</span><span class="sxs-lookup"><span data-stu-id="bfedd-135">There is no limitation on the number of ODBC source components that can run in parallel against the same table or different tables, on the same machine or on different machines (other than normal global session limits).</span></span>  
  
 <span data-ttu-id="bfedd-136">No entanto, as imitações do provedor ODBC sendo usado podem restringir o número de conexões simultâneas pelo provedor.</span><span class="sxs-lookup"><span data-stu-id="bfedd-136">However, limitations of the ODBC provider being used may restrict the number of concurrent connections through the provider.</span></span> <span data-ttu-id="bfedd-137">Essas limitações restringem o número de instâncias paralelas com suporte possível para a fonte ODBC.</span><span class="sxs-lookup"><span data-stu-id="bfedd-137">These limitations limit the number of supported parallel instances possible for the ODBC source.</span></span> <span data-ttu-id="bfedd-138">O desenvolvedor SSIS deve estar consciente das limitações de qualquer provedor ODBC usado e considerá-las ao compilar pacotes SSIS.</span><span class="sxs-lookup"><span data-stu-id="bfedd-138">The SSIS developer must be aware of the limitations of any ODBC provider being used and take them into consideration when building SSIS packages.</span></span>  
  
## <a name="troubleshooting-the-odbc-source"></a><span data-ttu-id="bfedd-139">Solucionando problemas da origem ODBC</span><span class="sxs-lookup"><span data-stu-id="bfedd-139">Troubleshooting the ODBC Source</span></span>  
 <span data-ttu-id="bfedd-140">Você pode registrar as chamadas que a origem ODBC faz para provedores de dados externos.</span><span class="sxs-lookup"><span data-stu-id="bfedd-140">You can log the calls that the ODBC source makes to external data providers.</span></span> <span data-ttu-id="bfedd-141">Você pode usar essa capacidade de registro para solucionar problemas de carregamento de dados de fontes de dados externas que a origem ODBC executa.</span><span class="sxs-lookup"><span data-stu-id="bfedd-141">You can use this logging capability to troubleshoot the loading of data from external data sources that the ODBC source performs.</span></span> <span data-ttu-id="bfedd-142">Para registrar em log as chamadas que a origem ODBC faz a provedores de dados externos, habilite o rastreamento do gerenciador de driver ODBC.</span><span class="sxs-lookup"><span data-stu-id="bfedd-142">To log the calls that the ODBC source makes to external data providers, enable the ODBC driver manager trace.</span></span> <span data-ttu-id="bfedd-143">Para obter mais informações, consulte a documentação da Microsoft em *Como gerar um rastreamento ODBC com o administrador de fonte de dados.*</span><span class="sxs-lookup"><span data-stu-id="bfedd-143">For more information, see the Microsoft documentation on *How To Generate an ODBC Trace with ODBC the Data Source Administrator.*</span></span>  
  
## <a name="configuring-the-odbc-source"></a><span data-ttu-id="bfedd-144">Configurando a origem ODBC</span><span class="sxs-lookup"><span data-stu-id="bfedd-144">Configuring the ODBC Source</span></span>  
 <span data-ttu-id="bfedd-145">Você pode configurar a origem ODBC programaticamente ou por meio do SSIS Designer.</span><span class="sxs-lookup"><span data-stu-id="bfedd-145">You can configure the ODBC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="bfedd-146">Para obter mais informações, consulte um dos tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="bfedd-146">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="bfedd-147">Editor de Fonte ODBC &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="bfedd-147">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="bfedd-148">Editor de Origem ODBC &#40;Página Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="bfedd-148">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="bfedd-149">Editor de Fonte ODBC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="bfedd-149">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="bfedd-150">A caixa de diálogo **Editor Avançado** contém as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="bfedd-150">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="bfedd-151">Para abrir a caixa de diálogo **Editor Avançado** :</span><span class="sxs-lookup"><span data-stu-id="bfedd-151">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="bfedd-152">Na tela **Fluxo de Dados** do seu projeto do [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , clique com o botão direito do mouse na origem ODBC e selecione **Mostrar Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="bfedd-152">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the ODBC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="bfedd-153">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo Editor Avançado, consulte [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="bfedd-153">For more information about the properties that you can set in the Advanced Editor dialog box, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bfedd-154">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bfedd-154">In This Section</span></span>  
  
-   [<span data-ttu-id="bfedd-155">Editor de Fonte ODBC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="bfedd-155">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="bfedd-156">Editor de Origem ODBC &#40;Página Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="bfedd-156">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="bfedd-157">Editor de Fonte ODBC &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="bfedd-157">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="bfedd-158">Extrair dados por meio da origem ODBC</span><span class="sxs-lookup"><span data-stu-id="bfedd-158">Extract Data by Using the ODBC Source</span></span>](odbc-source.md)  
  
-   [<span data-ttu-id="bfedd-159">ODBC Source Custom Properties</span><span class="sxs-lookup"><span data-stu-id="bfedd-159">ODBC Source Custom Properties</span></span>](odbc-source-custom-properties.md)  
  
  
