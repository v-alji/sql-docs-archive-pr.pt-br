---
title: Destino do Arquivo Bruto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledest.f1
helpviewer_keywords:
- append options [Integration Services]
- destinations [Integration Services], Raw File
- raw data [Integration Services]
- writing raw data
- Raw File destination
ms.assetid: d311b458-aefc-4b4d-b1a1-4c0ebbb34214
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fc5ce99be6e467ba323137ef885cbb13bfb328ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571467"
---
# <a name="raw-file-destination"></a><span data-ttu-id="4ea1e-102">Destino do Arquivo Bruto</span><span class="sxs-lookup"><span data-stu-id="4ea1e-102">Raw File Destination</span></span>
  <span data-ttu-id="4ea1e-103">O destino Arquivo Bruto grava dados brutos em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-103">The Raw File destination writes raw data to a file.</span></span> <span data-ttu-id="4ea1e-104">Devido ao formato dos dados ser nativo para o destino, os dados não requerem nenhuma tradução e pouca análise.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-104">Because the format of the data is native to the destination, the data requires no translation and little parsing.</span></span> <span data-ttu-id="4ea1e-105">Isso significa que o destino do Arquivo Bruto pode gravar dados mais rápido que outros destinos, tais como o Arquivo Plano e os destinos de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-105">This means that the Raw File destination can write data more quickly than other destinations such as the Flat File and the OLE DB destinations.</span></span>  
  
 <span data-ttu-id="4ea1e-106">Além de gravar dados brutos em um arquivo, você também pode usar o destino Arquivo Bruto para gerar um arquivo bruto vazio que contém somente as colunas (arquivo somente de metadados), sem ter que executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-106">In addition to writing raw data to a file, you can also use the Raw File destination to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="4ea1e-107">Use a fonte Arquivo Bruto para recuperar dados brutos que foram escritos previamente pelo destino.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-107">You use the Raw File source to retrieve raw data that was previously written by the destination.</span></span> <span data-ttu-id="4ea1e-108">Você também pode apontar a fonte Arquivo Bruto para o arquivo somente de metadados.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-108">You can also point the Raw File source to the metadata-only file.</span></span>  
  
 <span data-ttu-id="4ea1e-109">O formato de arquivo bruto contém informações de classificação.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-109">The raw file format contains sort information.</span></span> <span data-ttu-id="4ea1e-110">O destino Arquivo Bruto salva todas as informações de classificação incluindo os sinalizadores de comparação para as colunas de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-110">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="4ea1e-111">A fonte Arquivo Bruto lê e segue as informações de classificação.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-111">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="4ea1e-112">Você tem a opção de configurar fonte Arquivo Bruto para ignorar os sinalizadores de classificação no arquivo, usando o Editor Avançado.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-112">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="4ea1e-113">Para obter mais informações sobre os sinalizadores de comparação, consulte [Comparando dados de cadeia de caracteres](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="4ea1e-113">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="4ea1e-114">Você pode configurar o destino de Arquivo Bruto das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="4ea1e-114">You can configure the Raw File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="4ea1e-115">Especifique um modo de acesso que seja o nome do arquivo ou uma variável que contenha o nome do arquivo para qual o destino do Arquivo Bruto grava.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-115">Specify an access mode which is either the name of the file or a variable that contains the name of the file to which the Raw File destination writes.</span></span>  
  
-   <span data-ttu-id="4ea1e-116">Indique se o destino do Arquivo Bruto anexa dados a um arquivo existente que tenha o mesmo nome ou cria um arquivo novo.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-116">Indicate whether the Raw File destination appends data to an existing file that has the same name or creates a new file.</span></span>  
  
 <span data-ttu-id="4ea1e-117">O destino do Arquivo Bruto frequentemente é usado para gravar resultados intermediários de dados parcialmente processados entre as execuções de pacotes.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-117">The Raw File destination is frequently used to write intermediary results of partly processed data between package executions.</span></span> <span data-ttu-id="4ea1e-118">Armazenar dados brutos significa que os dados podem ser lidos rapidamente por uma fonte de Arquivo Bruto e posteriormente ser transformados antes que ele seja carregado em seu destino final.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-118">Storing raw data means that the data can be read quickly by a Raw File source and then further transformed before it is loaded into its final destination.</span></span> <span data-ttu-id="4ea1e-119">Por exemplo, um pacote poderia ser executado várias vezes e cada vez gravar dados brutos em arquivos.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-119">For example, a package might run several times, and each time write raw data to files.</span></span> <span data-ttu-id="4ea1e-120">Depois, um pacote diferente pode usar a fonte do Arquivo Bruto para ler a partir de cada arquivo, utilizar uma transformação do Union All para intercalar os dados em um conjunto de dados e então aplicar transformações adicionais que resumam os dados antes de carregá-los em seu destino final, tais como uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4ea1e-120">Later, a different package can use the Raw File source to read from each file, use a Union All transformation to merge the data into one data set, and then apply additional transformations that summarize the data before loading the data into its final destination such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ea1e-121">O destino do Arquivo Bruto aceita dados nulos, mas não dados de objeto binário grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="4ea1e-121">The Raw File destination supports null data but not binary large object (BLOB) data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ea1e-122">O destino do Arquivo Bruto não usa um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-122">The Raw File destination does not use a connection manager.</span></span>  
  
 <span data-ttu-id="4ea1e-123">Esta fonte tem uma entrada normal.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-123">This source has one regular input.</span></span> <span data-ttu-id="4ea1e-124">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-124">It does not support an error output.</span></span>  
  
## <a name="append-and-new-file-options"></a><span data-ttu-id="4ea1e-125">Opções de acréscimo e arquivo novo</span><span class="sxs-lookup"><span data-stu-id="4ea1e-125">Append and New File Options</span></span>  
 <span data-ttu-id="4ea1e-126">A propriedade WriteOption inclui opções para acrescentar dados a um arquivo existente ou criar um arquivo novo.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-126">The WriteOption property includes options to append data to an existing file or create a new file.</span></span>  
  
 <span data-ttu-id="4ea1e-127">A tabela seguinte descreve as opções disponíveis para a propriedade WriteOption.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-127">The following table describes the available options for the WriteOption property.</span></span>  
  
|<span data-ttu-id="4ea1e-128">Opção</span><span class="sxs-lookup"><span data-stu-id="4ea1e-128">Option</span></span>|<span data-ttu-id="4ea1e-129">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4ea1e-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4ea1e-130">Acrescentar</span><span class="sxs-lookup"><span data-stu-id="4ea1e-130">Append</span></span>|<span data-ttu-id="4ea1e-131">Acrescenta dados a um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-131">Appends data to an existing file.</span></span> <span data-ttu-id="4ea1e-132">Os metadados dos dados adicionados devem corresponder ao formato do arquivo.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-132">The metadata of the appended data must match the file format.</span></span>|  
|<span data-ttu-id="4ea1e-133">Criar sempre</span><span class="sxs-lookup"><span data-stu-id="4ea1e-133">Create always</span></span>|<span data-ttu-id="4ea1e-134">Sempre cria um arquivo novo.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-134">Always creates a new file.</span></span>|  
|<span data-ttu-id="4ea1e-135">Criar uma vez</span><span class="sxs-lookup"><span data-stu-id="4ea1e-135">Create once</span></span>|<span data-ttu-id="4ea1e-136">Cria um arquivo novo.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-136">Creates a new file.</span></span> <span data-ttu-id="4ea1e-137">Se o arquivo já existir, o componente falha.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-137">If the file exists, the component fails.</span></span>|  
|<span data-ttu-id="4ea1e-138">Truncar e acrescentar</span><span class="sxs-lookup"><span data-stu-id="4ea1e-138">Truncate and append</span></span>|<span data-ttu-id="4ea1e-139">Trunca um arquivo existente e depois grava os dados no arquivo.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-139">Truncates an existing file and then writes the data to the file.</span></span> <span data-ttu-id="4ea1e-140">Os metadados dos dados adicionados devem corresponder ao formato do arquivo.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-140">The metadata of the appended data must match the file format.</span></span>|  
  
 <span data-ttu-id="4ea1e-141">Os itens a seguir são importantes sobre como adicionar dados:</span><span class="sxs-lookup"><span data-stu-id="4ea1e-141">The following are important items about appending data:</span></span>  
  
-   <span data-ttu-id="4ea1e-142">Adicionar dados a um arquivo bruto existente não reclassifica os dados.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-142">Appending data to an existing raw file does not re-sort the data.</span></span>  
  
     <span data-ttu-id="4ea1e-143">Você precisa verificar se as chaves classificadas permanecem na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-143">You need to make certain that the sorted keys remain in the correct order.</span></span>  
  
-   <span data-ttu-id="4ea1e-144">Adicionar dados a um arquivo bruto existente não altera os metadados do arquivo (informações de classificação).</span><span class="sxs-lookup"><span data-stu-id="4ea1e-144">Appending data to an existing raw file does not change the file metadata (sort information).</span></span>  
  
 <span data-ttu-id="4ea1e-145">Por exemplo, um pacote lê os dados classificados no PK (ProductKey).</span><span class="sxs-lookup"><span data-stu-id="4ea1e-145">For example, a package reads data sorted on the ProductKey (PK).</span></span> <span data-ttu-id="4ea1e-146">O fluxo de dados de pacote adiciona os dados a um arquivo bruto existente.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-146">The package data flow appends the data to an existing raw file.</span></span> <span data-ttu-id="4ea1e-147">Na primeira vez que o pacote é executado, três linhas são recebidas (PK 1000, 1100, 1200).</span><span class="sxs-lookup"><span data-stu-id="4ea1e-147">The first time the package runs, three rows are received (PK 1000, 1100, 1200).</span></span> <span data-ttu-id="4ea1e-148">O arquivo bruto agora contém os seguintes dados.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-148">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="4ea1e-149">1000, produtoA</span><span class="sxs-lookup"><span data-stu-id="4ea1e-149">1000, productA</span></span>  
  
-   <span data-ttu-id="4ea1e-150">1100, produtoB</span><span class="sxs-lookup"><span data-stu-id="4ea1e-150">1100, productB</span></span>  
  
-   <span data-ttu-id="4ea1e-151">1200, produtoC</span><span class="sxs-lookup"><span data-stu-id="4ea1e-151">1200, productC</span></span>  
  
 <span data-ttu-id="4ea1e-152">Na segunda vez que o pacote é executado, duas novas linhas são recebidas (PK 1001, 1300).</span><span class="sxs-lookup"><span data-stu-id="4ea1e-152">The second time the package runs, two new rows are received (PK 1001, 1300).</span></span> <span data-ttu-id="4ea1e-153">O arquivo bruto agora contém os seguintes dados.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-153">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="4ea1e-154">1000, produtoA</span><span class="sxs-lookup"><span data-stu-id="4ea1e-154">1000, productA</span></span>  
  
-   <span data-ttu-id="4ea1e-155">1100, produtoB</span><span class="sxs-lookup"><span data-stu-id="4ea1e-155">1100, productB</span></span>  
  
-   <span data-ttu-id="4ea1e-156">1200, produtoC</span><span class="sxs-lookup"><span data-stu-id="4ea1e-156">1200, productC</span></span>  
  
-   <span data-ttu-id="4ea1e-157">1001, produtoD</span><span class="sxs-lookup"><span data-stu-id="4ea1e-157">1001, productD</span></span>  
  
-   <span data-ttu-id="4ea1e-158">1300, produtoE</span><span class="sxs-lookup"><span data-stu-id="4ea1e-158">1300, productE</span></span>  
  
 <span data-ttu-id="4ea1e-159">Os novos dados são adicionados no final do arquivo bruto e as chaves classificadas (PK) estão fora de ordem.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-159">The new data is appended to the end of the raw file, and the sorted keys (PK) are out of order.</span></span> <span data-ttu-id="4ea1e-160">Além disso, a operação de acrescentar não alterou os metadados do arquivo (informações de classificação).</span><span class="sxs-lookup"><span data-stu-id="4ea1e-160">In addition, the append operation didn't change the file metadata (sort information).</span></span> <span data-ttu-id="4ea1e-161">Se você ler o arquivo usando a fonte Arquivo Bruto, o componente indicará que o arquivo ainda está classificado em PK, embora os dados no arquivo não estejam mais na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-161">If you read the file by using the Raw File source, the component indicates that the file is still sorted on PK even though the data in the file is no longer in the correct order.</span></span>  
  
 <span data-ttu-id="4ea1e-162">Para manter as chaves classificadas na ordem correta enquanto adiciona dados, você pode criar o fluxo de dados de pacote da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4ea1e-162">To keep the sorted keys in the correct order while appending data, you can design the package data flow as follows:</span></span>  
  
1.  <span data-ttu-id="4ea1e-163">Recupere novas linhas usando a Origem A.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-163">Retrieve new rows by using Source A.</span></span>  
  
2.  <span data-ttu-id="4ea1e-164">Recupere linhas existentes de RawFile1 usando a Origem B.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-164">Retrieve existing rows from RawFile1 using Source B.</span></span>  
  
3.  <span data-ttu-id="4ea1e-165">Combine as entradas de Origem A e Origem B usando a transformação Union All.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-165">Combine the inputs from Source A and Source B by using the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="4ea1e-166">Classifique em PK.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-166">Sort on PK.</span></span>  
  
5.  <span data-ttu-id="4ea1e-167">Grave no RawFile2 usando o destino Arquivo Bruto.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-167">Write to RawFile2 by using the Raw File destination.</span></span>  
  
     <span data-ttu-id="4ea1e-168">RawFile1 está bloqueado porque está sendo lido no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-168">RawFile1 is locked because it's being read from, in the data flow.</span></span>  
  
6.  <span data-ttu-id="4ea1e-169">Substitua RawFile1 por RawFile2.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-169">Replace RawFile1 with RawFile2.</span></span>  
  
### <a name="using-the-raw-file-destination-in-a-loop"></a><span data-ttu-id="4ea1e-170">Usando o destino do Arquivo Bruto em um loop</span><span class="sxs-lookup"><span data-stu-id="4ea1e-170">Using the Raw File Destination in a Loop</span></span>  
 <span data-ttu-id="4ea1e-171">Se o fluxo de dados que usa o destino do Arquivo Bruto estiver em um loop, talvez você precise criar o arquivo uma vez e, em seguida, acrescentar dados ao arquivo quando o loop se repetir.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-171">If the data flow that uses the Raw File destination is in a loop, you may want to create the file once and then append data to the file when the loop repeats.</span></span> <span data-ttu-id="4ea1e-172">Para acrescentar dados ao arquivo, os dados que são acrescentados devem corresponder ao formato do arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-172">To append data to the file, the data that is appended must match the format of the existing file.</span></span>  
  
 <span data-ttu-id="4ea1e-173">Para criar o arquivo na primeira iteração do loop e então acrescentar filas nas iterações subsequentes do loop, você precisa fazer o seguinte na hora do design:</span><span class="sxs-lookup"><span data-stu-id="4ea1e-173">To create the file in the first iteration of the loop, and then append rows in the subsequent iterations of the loop, you need to do the following at design time:</span></span>  
  
1.  <span data-ttu-id="4ea1e-174">Defina a propriedade WriteOption como **CreateOnce** ou **CreateAlways**e execute uma iteração do loop.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-174">Set the WriteOption property to **CreateOnce** or **CreateAlways**and run one iteration of the loop.</span></span> <span data-ttu-id="4ea1e-175">O arquivo é criado.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-175">The file is created.</span></span> <span data-ttu-id="4ea1e-176">Isto assegura que os metadados de dados acrescentados e o arquivo correspondam.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-176">This ensures that the metadata of appended data and the file matches.</span></span>  
  
2.  <span data-ttu-id="4ea1e-177">Redefina a propriedade WriteOption como **Append** e defina a propriedade ValidateExternalMetadata como `False` .</span><span class="sxs-lookup"><span data-stu-id="4ea1e-177">Reset the WriteOption property to **Append** and set the ValidateExternalMetadata property to `False`.</span></span>  
  
 <span data-ttu-id="4ea1e-178">Se você usar a opção **TruncateAppend** em vez da opção **Append** , truncará filas que foram adicionadas a qualquer iteração anterior e então acrescentará novas filas.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-178">If you use the **TruncateAppend** option instead of the **Append** option, it will truncate rows that were added in any previous iteration, and then append new rows.</span></span> <span data-ttu-id="4ea1e-179">Usar a opção **TruncateAppend** também requer que os dados correspondam ao formato do arquivo.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-179">Using the **TruncateAppend** option also requires that the data matches the file format.</span></span>  
  
## <a name="configuration-of-the-raw-file-destination"></a><span data-ttu-id="4ea1e-180">Configuração do destino Arquivo Bruto</span><span class="sxs-lookup"><span data-stu-id="4ea1e-180">Configuration of the Raw File Destination</span></span>  
 <span data-ttu-id="4ea1e-181">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-181">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4ea1e-182">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-182">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="4ea1e-183">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="4ea1e-183">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="4ea1e-184">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="4ea1e-184">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="4ea1e-185">Propriedades personalizadas de arquivo bruto</span><span class="sxs-lookup"><span data-stu-id="4ea1e-185">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="4ea1e-186">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4ea1e-186">Related Tasks</span></span>  
 <span data-ttu-id="4ea1e-187">Para obter informações sobre como definir as propriedades do componente, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="4ea1e-187">For information about how to set properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="4ea1e-188">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="4ea1e-188">Related Content</span></span>  
 <span data-ttu-id="4ea1e-189">Entrada de blog, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131)(Arquivos brutos são incríveis), em sqlservercentral.com.</span><span class="sxs-lookup"><span data-stu-id="4ea1e-189">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea1e-190">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4ea1e-190">See Also</span></span>  
 <span data-ttu-id="4ea1e-191">[Fonte de arquivo bruto](raw-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="4ea1e-191">[Raw File Source](raw-file-source.md) </span></span>  
 [<span data-ttu-id="4ea1e-192">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="4ea1e-192">Data Flow</span></span>](data-flow.md)  
  
  
