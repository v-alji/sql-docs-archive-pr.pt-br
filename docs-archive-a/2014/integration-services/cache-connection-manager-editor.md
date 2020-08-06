---
title: Editor do Gerenciador de conexões de cache | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cacheconnection.f1
ms.assetid: 0d8f9324-0c35-4eea-b06d-da3cc2426d2c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 38a858217925496d8dd937d684368bdb2e061b14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582579"
---
# <a name="cache-connection-manager-editor"></a><span data-ttu-id="2d0f9-102">Editor do Gerenciador de Conexões de Cache</span><span class="sxs-lookup"><span data-stu-id="2d0f9-102">Cache Connection Manager Editor</span></span>
  <span data-ttu-id="2d0f9-103">O gerenciador de conexões de Cache lê um conjunto de dados de referência da transformação Cache ou de um arquivo cache (.caw) e salva os dados em um arquivo cache.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-103">The Cache connection manager reads a reference dataset from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="2d0f9-104">Os dados sempre são armazenados na memória.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-104">The data is always stored in memory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d0f9-105">O gerenciador de conexões do Cache não oferece suporte aos tipos de dados BLOB (objetos binários grandes) DT_TEXT, DT_NTEXT e DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-105">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="2d0f9-106">Se o conjunto de dados de referência contiver um tipo de dados BLOB, o componente irá falhar quando o pacote for executado.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-106">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="2d0f9-107">Você pode usar o **Editor do Gerenciador de Conexões de Cache** para modificar os tipos de dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-107">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span>  
  
 <span data-ttu-id="2d0f9-108">A transformação Pesquisa realiza as pesquisas no conjunto de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-108">The Lookup transformation performs lookups on the reference dataset.</span></span>  
  
 <span data-ttu-id="2d0f9-109">A caixa de diálogo **Editor do Gerenciador de Conexões de Cache** inclui as seguintes guias:</span><span class="sxs-lookup"><span data-stu-id="2d0f9-109">The **Cache Connection ManagerEditor** dialog box includes the following tabs:</span></span>  
  
-   [<span data-ttu-id="2d0f9-110">Guia geral</span><span class="sxs-lookup"><span data-stu-id="2d0f9-110">General tab</span></span>](#generaltab)  
  
-   [<span data-ttu-id="2d0f9-111">Guia colunas</span><span class="sxs-lookup"><span data-stu-id="2d0f9-111">Columns tab</span></span>](#columnstab)  
  
 <span data-ttu-id="2d0f9-112">Para obter mais informações sobre o Gerenciador de Conexões de Cache, consulte [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2d0f9-112">To learn more about the Cache Connection Manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
##  <a name="general-tab"></a><a name="generaltab"></a><span data-ttu-id="2d0f9-113">Guia geral</span><span class="sxs-lookup"><span data-stu-id="2d0f9-113">General Tab</span></span>  
 <span data-ttu-id="2d0f9-114">Use a guia **Geral** da caixa de diálogo **Editor do Gerenciador de Conexões de Cache** para indicar se é necessário ler o cache de um arquivo ou salvar o cache em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-114">Use the **General** tab of the **Cache Connection ManagerEditor** dialog box to indicate whether to read the cache from a file or save the cache to a file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2d0f9-115">Opções</span><span class="sxs-lookup"><span data-stu-id="2d0f9-115">Options</span></span>  
 <span data-ttu-id="2d0f9-116">**Nome do gerenciador de conexões**</span><span class="sxs-lookup"><span data-stu-id="2d0f9-116">**Connection manager name**</span></span>  
 <span data-ttu-id="2d0f9-117">Forneça um nome exclusivo para a conexão de cache no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-117">Provide a unique name for the cache connection in the workflow.</span></span> <span data-ttu-id="2d0f9-118">O nome fornecido será exibido no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d0f9-118">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="2d0f9-119">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2d0f9-119">**Description**</span></span>  
 <span data-ttu-id="2d0f9-120">Descreva a conexão.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-120">Describe the connection.</span></span> <span data-ttu-id="2d0f9-121">Como prática recomendável, descreva a conexão de acordo com a sua finalidade para tornar os pacotes autodocumentados e facilitar a sua manutenção.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-121">As a best practice, describe the connection according to its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="2d0f9-122">**Usar cache de arquivo.**</span><span class="sxs-lookup"><span data-stu-id="2d0f9-122">**Use file cache**</span></span>  
 <span data-ttu-id="2d0f9-123">Indique se precisa usar um arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-123">Indicate whether to use a cache file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d0f9-124">O nível de proteção do pacote não se aplica ao arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-124">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="2d0f9-125">Se o arquivo de cache tiver informações confidenciais, use uma lista de controle de acesso (ACL) para restringir o acesso ao local ou à pasta na qual você deseja armazenar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-125">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="2d0f9-126">Você deve habilitar o acesso apenas para determinadas contas.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-126">You should enable access only to certain accounts.</span></span> <span data-ttu-id="2d0f9-127">Para obter mais informações, consulte [Acesso aos arquivos usados por pacotes](../../2014/integration-services/access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="2d0f9-127">For more information, see [Access to Files Used by Packages](../../2014/integration-services/access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="2d0f9-128">Se você configurar o gerenciador de conexões de cache para usar um arquivo de cache, o gerenciador irá realizar uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="2d0f9-128">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
-   <span data-ttu-id="2d0f9-129">Salvar os dados no arquivo quando a transformação Cache estiver configurada para gravar dados de uma fonte de dados no fluxo de dados para o gerenciador de conexões de cache.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-129">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span> <span data-ttu-id="2d0f9-130">Para obter mais informações, consulte [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="2d0f9-130">For more information, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="2d0f9-131">Ler os dados do arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-131">Read data from the cache file.</span></span>  
  
 <span data-ttu-id="2d0f9-132">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="2d0f9-132">**File name**</span></span>  
 <span data-ttu-id="2d0f9-133">Digite o caminho e o nome do arquivo do arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-133">Type the path and file name of the cache file.</span></span>  
  
 <span data-ttu-id="2d0f9-134">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="2d0f9-134">**Browse**</span></span>  
 <span data-ttu-id="2d0f9-135">Localize o arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-135">Locate the cache file.</span></span>  
  
 <span data-ttu-id="2d0f9-136">**Atualizar metadados**</span><span class="sxs-lookup"><span data-stu-id="2d0f9-136">**Refresh Metadata**</span></span>  
 <span data-ttu-id="2d0f9-137">Exclua os metadados de colunas no gerenciador de conexões de Cache e popule novamente o gerenciador de conexões do Cache com matadados de colunas de um arquivo de cache selecionado.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-137">Delete the column metadata in the Cache connection manager and repopulate the Cache connection manager with column metadata from a selected cache file.</span></span>  
  
##  <a name="columns-tab"></a><a name="columnstab"></a><span data-ttu-id="2d0f9-138">Guia colunas</span><span class="sxs-lookup"><span data-stu-id="2d0f9-138">Columns Tab</span></span>  
 <span data-ttu-id="2d0f9-139">Use a guia **Colunas** da caixa de diálogo **Editor do Gerenciador de Conexões de Cache** para configurar as propriedades de cada coluna no cache.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-139">Use the **Columns** tab of the **Cache Connection Manager Editor** dialog box to configure the properties of each column in the cache.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2d0f9-140">Opções</span><span class="sxs-lookup"><span data-stu-id="2d0f9-140">Options</span></span>  
 <span data-ttu-id="2d0f9-141">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2d0f9-141">**Column**</span></span>  
 <span data-ttu-id="2d0f9-142">Especifique o nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-142">Specify the column name.</span></span>  
  
 <span data-ttu-id="2d0f9-143">**Posição de Índice**</span><span class="sxs-lookup"><span data-stu-id="2d0f9-143">**Index Position**</span></span>  
 <span data-ttu-id="2d0f9-144">Especifique quais colunas são colunas de índice indicando a posição de índice de cada coluna.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-144">Specify which columns are index columns by specifying the index position of each column.</span></span> <span data-ttu-id="2d0f9-145">O índice é uma coleção de uma ou mais colunas.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-145">The index is a collection of one or more columns.</span></span>  
  
 <span data-ttu-id="2d0f9-146">Para colunas sem-índice, a posição de índice é 0.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-146">For non-index columns, the index position is 0.</span></span>  
  
 <span data-ttu-id="2d0f9-147">Para colunas de índice, a posição de índice é um número sequencial positivo.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-147">For index columns, the index position is a sequential, positive number.</span></span> <span data-ttu-id="2d0f9-148">Este número indica a ordem na qual a transformação Pesquisa compara as linhas no conjunto de dados de referência às linhas na fonte de dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-148">This number indicates the order in which the Lookup transformation compares rows in the reference dataset to rows in the input data source.</span></span> <span data-ttu-id="2d0f9-149">A coluna com os valores mais exclusivos deve ter a posição de índice mais baixa.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-149">The column with the most unique values should have the lowest index position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d0f9-150">Quando a transformação Pesquisa é configurada para usar um gerenciador de conexões de Cache, somente as colunas de índice no conjunto de dados de referência podem ser mapeadas para as colunas de entrada.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-150">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="2d0f9-151">Além disso, todas as colunas de índice devem ser mapeadas.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-151">Also, all index columns must be mapped.</span></span>  
  
 <span data-ttu-id="2d0f9-152">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2d0f9-152">**Type**</span></span>  
 <span data-ttu-id="2d0f9-153">Especifique o tipo de dados da coluna</span><span class="sxs-lookup"><span data-stu-id="2d0f9-153">Specify the data type of the column.</span></span>  
  
 `Length`  
 <span data-ttu-id="2d0f9-154">Especifica o tipo de dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-154">Specifies the column data type.</span></span> <span data-ttu-id="2d0f9-155">Se aplicável ao tipo de dados, você pode atualizar a `Length`.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-155">If applicable to the data type, you can update `Length`.</span></span>  
  
 `Precision`  
 <span data-ttu-id="2d0f9-156">Especifica a precisão de alguns tipos de dados de coluna.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-156">Specifies the precision for certain column data types.</span></span> <span data-ttu-id="2d0f9-157">A precisão é o número de dígitos em um número.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-157">Precision is the number of digits in a number.</span></span> <span data-ttu-id="2d0f9-158">Se aplicável ao tipo de dados, você pode atualizar a `Precision`.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-158">If applicable to the data type, you can update `Precision`.</span></span>  
  
 `Scale`  
 <span data-ttu-id="2d0f9-159">Especifica a escala de alguns tipos de dados de coluna.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-159">Specifies the scale for certain column data types.</span></span> <span data-ttu-id="2d0f9-160">A escala é o número de dígitos à direita da casa decimal em um número.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-160">Scale is the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="2d0f9-161">Se aplicável ao tipo de dados, você pode atualizar a `Scale`.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-161">If applicable to the data type, you can update `Scale`.</span></span>  
  
 `Code Page`  
 <span data-ttu-id="2d0f9-162">Especifica a página de código para o tipo de coluna.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-162">Specifies the code page for the column type.</span></span> <span data-ttu-id="2d0f9-163">Se aplicável ao tipo de dados, você pode atualizar a `Code Page`.</span><span class="sxs-lookup"><span data-stu-id="2d0f9-163">If applicable to the data type, you can update `Code Page`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d0f9-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d0f9-164">See Also</span></span>  
 [<span data-ttu-id="2d0f9-165">Transformação Pesquisa</span><span class="sxs-lookup"><span data-stu-id="2d0f9-165">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
