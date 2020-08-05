---
title: Tarefa de Upload do DW no SQL Azure | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPDWUPTASK.F1
- SQL11.DTS.DESIGNER.AFPDWUPTASK.F1
ms.assetid: 112cf764-f85a-4c1a-b732-d299d717c0d4
author: yualan
ms.author: chugu
ms.openlocfilehash: d90cc36b5e8beb35313b76ecef2ed95f065dcb89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570824"
---
# <a name="azure-sql-dw-upload-task"></a><span data-ttu-id="a45b3-102">Tarefa de Upload do SQL DW do Azure</span><span class="sxs-lookup"><span data-stu-id="a45b3-102">Azure SQL DW Upload Task</span></span>
<span data-ttu-id="a45b3-103">A **Tarefa de Upload do SQL DW do Azure** permite que um pacote do SSIS carregue dados locais em uma tabela no SQL Data Warehouse (DW) do Azure.</span><span class="sxs-lookup"><span data-stu-id="a45b3-103">The **Azure SQL DW Upload Task** enables an SSIS package to upload local data to a table in Azure SQL Data Warehouse (DW).</span></span> <span data-ttu-id="a45b3-104">O formato de arquivo de dados de origem com suporte atualmente é texto delimitado em codificação UTF8.</span><span class="sxs-lookup"><span data-stu-id="a45b3-104">The currently supported source data file format is delimited text in UTF8 encoding.</span></span> <span data-ttu-id="a45b3-105">O processo de carregamento segue a abordagem de polybase eficiente.</span><span class="sxs-lookup"><span data-stu-id="a45b3-105">The uploading process follows the efficient PolyBase approach.</span></span> <span data-ttu-id="a45b3-106">Especificamente, os dados serão primeiro carregados no Armazenamento de Blobs do Azure e, em seguida, no SQL DW do Azure.</span><span class="sxs-lookup"><span data-stu-id="a45b3-106">Specifically, data will first be uploaded to Azure Blob Storage, and then to Azure SQL DW.</span></span> <span data-ttu-id="a45b3-107">Portanto, é necessário uma conta de Armazenamento de Blobs do Azure para usar essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="a45b3-107">Therefore, an Azure Blob Storage account is needed to use this task.</span></span>

<span data-ttu-id="a45b3-108">Para adicionar uma **Tarefa de Upload do SQL DW do Azure**, arraste-a da Caixa de Ferramentas do SSIS e solte-a na tela do designer, e clique duas vezes ou clique com o botão direito do mouse em **Editar** para ver a caixa de diálogo editor da tarefa.</span><span class="sxs-lookup"><span data-stu-id="a45b3-108">To add an **Azure SQL DW Upload Task**, drag-drop it from SSIS Toolbox to the designer canvas, and double-click or right-click and click **Edit** to see the task editor dialog box.</span></span>

<span data-ttu-id="a45b3-109">Na página **Geral** , defina as propriedades a seguir.</span><span class="sxs-lookup"><span data-stu-id="a45b3-109">On the **General** page, configure the following properties.</span></span>

<span data-ttu-id="a45b3-110">Campo</span><span class="sxs-lookup"><span data-stu-id="a45b3-110">Field</span></span>|<span data-ttu-id="a45b3-111">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a45b3-111">Description</span></span>
-----|-----------
<span data-ttu-id="a45b3-112">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="a45b3-112">LocalDirectory</span></span>|<span data-ttu-id="a45b3-113">Especifica o diretório local que contém os arquivos de dados a serem carregados.</span><span class="sxs-lookup"><span data-stu-id="a45b3-113">Specifies the local directory that contains the data files to be uploaded.</span></span>
<span data-ttu-id="a45b3-114">Recursivamente</span><span class="sxs-lookup"><span data-stu-id="a45b3-114">Recursively</span></span>|<span data-ttu-id="a45b3-115">Especifica se os subdiretórios devem ser pesquisados recursivamente.</span><span class="sxs-lookup"><span data-stu-id="a45b3-115">Specifies whether to recursively search sub-directories.</span></span>
<span data-ttu-id="a45b3-116">FileName</span><span class="sxs-lookup"><span data-stu-id="a45b3-116">FileName</span></span>|<span data-ttu-id="a45b3-117">Especifica um filtro de nome para selecionar arquivos com o padrão de nome determinado.</span><span class="sxs-lookup"><span data-stu-id="a45b3-117">Specifies a name filter to select files with certain name pattern.</span></span> <span data-ttu-id="a45b3-118">Por ex.:</span><span class="sxs-lookup"><span data-stu-id="a45b3-118">E.g.</span></span> <span data-ttu-id="a45b3-119">MySheet\*.xsl\* incluirá arquivos como MySheet001.xsl e MySheetABC.xslx.</span><span class="sxs-lookup"><span data-stu-id="a45b3-119">MySheet\*.xsl\* will include files such as MySheet001.xsl and MySheetABC.xslx.</span></span>
<span data-ttu-id="a45b3-120">RowDelimiter</span><span class="sxs-lookup"><span data-stu-id="a45b3-120">RowDelimiter</span></span>|<span data-ttu-id="a45b3-121">Especifica os caracteres que marcam o final de cada linha.</span><span class="sxs-lookup"><span data-stu-id="a45b3-121">Specifies the character(s) that marks the end of each row.</span></span>
<span data-ttu-id="a45b3-122">ColumnDelimiter</span><span class="sxs-lookup"><span data-stu-id="a45b3-122">ColumnDelimiter</span></span>|<span data-ttu-id="a45b3-123">Especifica um ou mais caracteres que marcam o final de cada coluna.</span><span class="sxs-lookup"><span data-stu-id="a45b3-123">Specifies one or more characters that mark the end of each column.</span></span> <span data-ttu-id="a45b3-124">Por ex.:</span><span class="sxs-lookup"><span data-stu-id="a45b3-124">E.g.</span></span> <span data-ttu-id="a45b3-125">&#124; (barra vertical) \t (tabulação), ' (aspa simples), "(aspas duplas) e 0x5c (barra invertida).</span><span class="sxs-lookup"><span data-stu-id="a45b3-125">&#124; (pipe), \t (tab), ' (single quote), " (double quote), and 0x5c (backslash).</span></span>
<span data-ttu-id="a45b3-126">IsFirstRowHeader</span><span class="sxs-lookup"><span data-stu-id="a45b3-126">IsFirstRowHeader</span></span>|<span data-ttu-id="a45b3-127">Especifica se a primeira linha em cada arquivo de dados contém nomes de coluna em vez de dados reais.</span><span class="sxs-lookup"><span data-stu-id="a45b3-127">Specifies whether the first row in each data file contains column names instead of actual data.</span></span>
<span data-ttu-id="a45b3-128">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="a45b3-128">AzureStorageConnection</span></span>|<span data-ttu-id="a45b3-129">Especifica um gerenciador de conexões do Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="a45b3-129">Specifies an Azure Storage connection manager.</span></span>
<span data-ttu-id="a45b3-130">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="a45b3-130">BlobContainer</span></span>|<span data-ttu-id="a45b3-131">Especifica o nome do contêiner de blob no qual os dados locais serão carregados e retransmitidos ao DW do Azure através do PolyBase.</span><span class="sxs-lookup"><span data-stu-id="a45b3-131">Specifies the name of blob container to which local data will be uploaded and relayed to Azure DW via PolyBase.</span></span> <span data-ttu-id="a45b3-132">Um novo contêiner será criado, caso não exista.</span><span class="sxs-lookup"><span data-stu-id="a45b3-132">A new container will be created if it does not exist.</span></span>
<span data-ttu-id="a45b3-133">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="a45b3-133">BlobDirectory</span></span>|<span data-ttu-id="a45b3-134">Especifica o diretório de blob (estrutura hierárquica virtual) no qual os dados locais serão carregados e retransmitidos ao DW do Azure através do PolyBase.</span><span class="sxs-lookup"><span data-stu-id="a45b3-134">Specifies the blob directory (virtual hierarchical structure) to which local data will be uploaded and relayed to Azure DW via PolyBase.</span></span>
<span data-ttu-id="a45b3-135">RetainFiles</span><span class="sxs-lookup"><span data-stu-id="a45b3-135">RetainFiles</span></span>|<span data-ttu-id="a45b3-136">Especifica se os arquivos carregados no Armazenamento do Azure serão mantidos.</span><span class="sxs-lookup"><span data-stu-id="a45b3-136">Specifies whether to retain the files uploaded to Azure Storage.</span></span>
<span data-ttu-id="a45b3-137">CompressionType</span><span class="sxs-lookup"><span data-stu-id="a45b3-137">CompressionType</span></span>|<span data-ttu-id="a45b3-138">Especifica o formato de compactação a ser usado ao carregar arquivos no Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="a45b3-138">Specifies the compression format to use upon uploading files to Azure Storage.</span></span> <span data-ttu-id="a45b3-139">A origem local não é afetada.</span><span class="sxs-lookup"><span data-stu-id="a45b3-139">Local source is not affected.</span></span>
<span data-ttu-id="a45b3-140">CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="a45b3-140">CompressionLevel</span></span>|<span data-ttu-id="a45b3-141">Especifica o nível de compactação a ser usado para o formato de compactação.</span><span class="sxs-lookup"><span data-stu-id="a45b3-141">Specifies the compression level to use for the compression format.</span></span>
<span data-ttu-id="a45b3-142">AzureDwConnection</span><span class="sxs-lookup"><span data-stu-id="a45b3-142">AzureDwConnection</span></span>|<span data-ttu-id="a45b3-143">Especifica um Gerenciador de conexões ADO.NET para o SQL DW do Azure.</span><span class="sxs-lookup"><span data-stu-id="a45b3-143">Specifies an ADO.NET connection manager for Azure SQL DW.</span></span>
<span data-ttu-id="a45b3-144">TableName</span><span class="sxs-lookup"><span data-stu-id="a45b3-144">TableName</span></span>|<span data-ttu-id="a45b3-145">Especifica o nome da tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="a45b3-145">Specifies name of the destination table.</span></span> <span data-ttu-id="a45b3-146">Escolha o nome de uma tabela existente ou crie uma selecionando **\<New Table ...>** .</span><span class="sxs-lookup"><span data-stu-id="a45b3-146">Either choose an existing table name, or create a new one by choosing **\<New Table ...>**.</span></span>
<span data-ttu-id="a45b3-147">TableDistribution</span><span class="sxs-lookup"><span data-stu-id="a45b3-147">TableDistribution</span></span>|<span data-ttu-id="a45b3-148">Especifica o método de distribuição para a nova tabela.</span><span class="sxs-lookup"><span data-stu-id="a45b3-148">Specifies the distribution method for new table.</span></span> <span data-ttu-id="a45b3-149">Aplica-se caso um novo nome de tabela para **TableName**seja especificado.</span><span class="sxs-lookup"><span data-stu-id="a45b3-149">Applies if a new table name is specified for **TableName**.</span></span>
<span data-ttu-id="a45b3-150">HashColumnName</span><span class="sxs-lookup"><span data-stu-id="a45b3-150">HashColumnName</span></span>|<span data-ttu-id="a45b3-151">Especifica a coluna usada para a distribuição da tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="a45b3-151">Specifies the column used for hash table distribution.</span></span> <span data-ttu-id="a45b3-152">Aplica-se caso **HASH** for especificado para **TableDistribution**.</span><span class="sxs-lookup"><span data-stu-id="a45b3-152">Applies if **HASH** is specified for **TableDistribution**.</span></span>

<span data-ttu-id="a45b3-153">Você verá uma página **Mapeamentos** diferente caso esteja carregando para uma tabela nova ou para uma tabela existente.</span><span class="sxs-lookup"><span data-stu-id="a45b3-153">You will see a different **Mappings** page depending on whether you are uploading to a new table or to an existing one.</span></span> <span data-ttu-id="a45b3-154">No primeiro caso, configure quais colunas de origem serão mapeadas e os nomes correspondentes na tabela de destino a ser criada.</span><span class="sxs-lookup"><span data-stu-id="a45b3-154">In the former case, configure which source columns are to be mapped and their corresponding names in the to-be-created destination table.</span></span> <span data-ttu-id="a45b3-155">No último caso, configure as relações de mapeamento entre colunas de origem e de destino.</span><span class="sxs-lookup"><span data-stu-id="a45b3-155">In the latter case, configure the mapping relationships between source and destination columns.</span></span>

<span data-ttu-id="a45b3-156">Na página **Colunas** , configure as propriedades de tipo de dados para cada coluna de origem.</span><span class="sxs-lookup"><span data-stu-id="a45b3-156">On the **Columns** page, configure the data type properties for each source column.</span></span>

<span data-ttu-id="a45b3-157">A página **T-SQL** mostra o T-SQL usado para carregar os dados do Armazenamento de Blobs do Azure para o SQL DW do Azure.</span><span class="sxs-lookup"><span data-stu-id="a45b3-157">The **T-SQL** page shows the T-SQL used to load data from Azure Blob Storage to Azure SQL DW.</span></span> <span data-ttu-id="a45b3-158">O T-SQL é gerado automaticamente de configurações nas outras páginas e será executado como parte da execução da tarefa.</span><span class="sxs-lookup"><span data-stu-id="a45b3-158">The T-SQL is automatically generated from configurations on the other pages, and will be executed as part of the task execution.</span></span> <span data-ttu-id="a45b3-159">Você pode optar por editar manualmente o T-SQL gerado para atender às suas necessidades específicas clicando no botão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="a45b3-159">You may choose to manually edit the generated T-SQL to meet your particular needs by clicking the **Edit** button.</span></span> <span data-ttu-id="a45b3-160">Depois, você pode reverter para aquele que foi gerado automaticamente, clicando no botão **Redefinir** .</span><span class="sxs-lookup"><span data-stu-id="a45b3-160">You can revert to the automatically generated one later on by clicking the **Reset** button.</span></span>