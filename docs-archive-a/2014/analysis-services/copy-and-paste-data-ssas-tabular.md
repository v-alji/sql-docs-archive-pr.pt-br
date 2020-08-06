---
title: Copiar e colar dados (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.pastepreviewdb.f1
ms.assetid: 2f8d8b3d-810b-4c31-98f2-341015e13da8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30df733377f3cb6f7583d380fbb8e92a0ea69e88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570999"
---
# <a name="copy-and-paste-data-ssas-tabular"></a><span data-ttu-id="08f50-102">Copiar e colar dados (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="08f50-102">Copy and Paste Data (SSAS Tabular)</span></span>
  <span data-ttu-id="08f50-103">É possível copiar dados de tabelas de aplicativos externos e colá-los em uma nova tabela ou uma existente no designer de modelo.</span><span class="sxs-lookup"><span data-stu-id="08f50-103">You can copy table data from external applications and paste it into a new or existing table in the model designer.</span></span> <span data-ttu-id="08f50-104">Os dados colados da Área de Transferência devem estar em formato HTML, por exemplo, dados que são copiados de Excel ou Word.</span><span class="sxs-lookup"><span data-stu-id="08f50-104">The data that you paste from the Clipboard must be in HTML format, for example, data that is copied from Excel or Word.</span></span> <span data-ttu-id="08f50-105">O designer de modelo detectará e aplicará automaticamente os tipos de dados aos dados colados.</span><span class="sxs-lookup"><span data-stu-id="08f50-105">The model designer will automatically detect and apply data types to the pasted data.</span></span> <span data-ttu-id="08f50-106">Você também pode modificar manualmente o tipo de dados ou a formatação de exibição de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="08f50-106">You can also manually modify the data type or display formatting of a column.</span></span>  
  
 <span data-ttu-id="08f50-107">Ao contrário de tabelas com uma conexão da fonte de dados, as tabelas coladas não têm uma propriedade Nome de Conexão ou Dados de Origem.</span><span class="sxs-lookup"><span data-stu-id="08f50-107">Unlike tables with a data source connection, pasted tables do not have a Connection Name or Source Data property.</span></span> <span data-ttu-id="08f50-108">Dados colados são persistidos no arquivo Model.bim.</span><span class="sxs-lookup"><span data-stu-id="08f50-108">Pasted data is persisted in the Model.bim file.</span></span> <span data-ttu-id="08f50-109">Quando o projeto ou o arquivo Model.bim for salvo, os dados colados também serão salvos.</span><span class="sxs-lookup"><span data-stu-id="08f50-109">When the project or Model.bim file is saved, the pasted data is also saved.</span></span>  
  
 <span data-ttu-id="08f50-110">Quando um modelo é implantado, os dados colados também serão implantados com ele, mesmo que o modelo não seja processado com a implantação.</span><span class="sxs-lookup"><span data-stu-id="08f50-110">When a model is deployed, pasted data will also be deployed with it regardless if the model is processed with the deployment.</span></span>  
  
 <span data-ttu-id="08f50-111">Seções neste tópico:</span><span class="sxs-lookup"><span data-stu-id="08f50-111">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="08f50-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="08f50-112">Prerequisites</span></span>](#bkmk_prerequisites)  
  
-   [<span data-ttu-id="08f50-113">Colar dados</span><span class="sxs-lookup"><span data-stu-id="08f50-113">Paste Data</span></span>](#bkmk_paste_data)  
  
-   [<span data-ttu-id="08f50-114">Caixa de diálogo Colar Visualização</span><span class="sxs-lookup"><span data-stu-id="08f50-114">Paste Preview Dialog Box</span></span>](#bkmk_paste_preview)  
  
##  <a name="prerequisites"></a><a name="bkmk_prerequisites"></a> <span data-ttu-id="08f50-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="08f50-115">Prerequisites</span></span>  
 <span data-ttu-id="08f50-116">Há algumas restrições para colar dados:</span><span class="sxs-lookup"><span data-stu-id="08f50-116">There are some restrictions when pasting data:</span></span>  
  
-   <span data-ttu-id="08f50-117">As tabelas coladas não podem ter mais de 10.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="08f50-117">Pasted tables cannot have more than 10,000 rows.</span></span>  
  
-   <span data-ttu-id="08f50-118">Não é possível particionar tabelas coladas.</span><span class="sxs-lookup"><span data-stu-id="08f50-118">Pasted tables cannot be partitioned.</span></span>  
  
-   <span data-ttu-id="08f50-119">Tabelas coladas não têm suporte no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="08f50-119">Pasted tables are not supported in DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="08f50-120">As opções **Colar Acréscimo** e **Colar Substituição** estão disponível somente para trabalhar com uma tabela que tenha sido inicialmente através da colagem de dados da Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="08f50-120">The **Paste Append** and **Paste Replace** options are only available when working with a table that was initially created by pasting data from the Clipboard.</span></span> <span data-ttu-id="08f50-121">Não é possível usar **Colar Acréscimo** ou **Colar Substituição** para adicionar dados em uma tabela de dados importados de outro tipo de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="08f50-121">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data from another type of data source.</span></span>  
  
-   <span data-ttu-id="08f50-122">Quando você usar **Colar Acréscimo** ou **Colar Substituição**, os novos dados deverão conter exatamente o mesmo número de colunas dos dados originais.</span><span class="sxs-lookup"><span data-stu-id="08f50-122">When you use **Paste Append** or **Paste Replace**, the new data must contain exactly the same number of columns as the original data.</span></span> <span data-ttu-id="08f50-123">De preferência, as colunas de dados coladas ou anexadas também deverão ser dos mesmos tipos de dados ou compatíveis com os da tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="08f50-123">Preferably, the columns of data that you paste or append should also be of the same or compatible data type as those in the destination table.</span></span> <span data-ttu-id="08f50-124">Em alguns casos, você pode usar um tipo de dados diferente, mas um erro **Tipos incompatíveis** poderá ser exibido.</span><span class="sxs-lookup"><span data-stu-id="08f50-124">In some cases you can use a different data type, but a **Type mismatch** error may be displayed.</span></span>  
  
##  <a name="paste-data"></a><a name="bkmk_paste_data"></a> <span data-ttu-id="08f50-125">Colar dados</span><span class="sxs-lookup"><span data-stu-id="08f50-125">Paste Data</span></span>  
  
#### <a name="to-paste-data-into-the-designer"></a><span data-ttu-id="08f50-126">Para colar dados na janela do designer</span><span class="sxs-lookup"><span data-stu-id="08f50-126">To paste data into the designer</span></span>  
  
-   <span data-ttu-id="08f50-127">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], clique no menu **Editar** e clique em um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="08f50-127">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Edit** menu, and then clicke of the following:</span></span>  
  
    -   <span data-ttu-id="08f50-128">Clique em **Colar** para colar o conteúdo da Área de Transferência em uma nova tabela.</span><span class="sxs-lookup"><span data-stu-id="08f50-128">Click **Paste** to paste the contents of the Clipboard into a new table.</span></span>  
  
    -   <span data-ttu-id="08f50-129">Clique em **Colar Acréscimo** para colar o conteúdo da Área de Transferência como linhas adicionais na tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="08f50-129">Click **Paste Append** to paste the contents of the Clipboard as additional rows into the selected table.</span></span> <span data-ttu-id="08f50-130">As novas linhas serão adicionadas ao final da tabela.</span><span class="sxs-lookup"><span data-stu-id="08f50-130">The new rows will be added to the end of the table.</span></span>  
  
    -   <span data-ttu-id="08f50-131">Clique em **Colar Substituição** para substituir a tabela selecionada pelo conteúdo da Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="08f50-131">Click **Paste Replace** to replace the selected table with the contents of the Clipboard.</span></span> <span data-ttu-id="08f50-132">Todos os nomes de cabeçalho de coluna existentes permanecerão na tabela e as relações serão preservadas.</span><span class="sxs-lookup"><span data-stu-id="08f50-132">All existing column header names will remain in the table, and relationships are preserved.</span></span>  
  
##  <a name="paste-preview-dialog-box"></a><a name="bkmk_paste_preview"></a><span data-ttu-id="08f50-133">Caixa de diálogo colar visualização</span><span class="sxs-lookup"><span data-stu-id="08f50-133">Paste Preview Dialog Box</span></span>  
 <span data-ttu-id="08f50-134">A caixa de diálogo **Visualização de Colagem** o habilita a visualizar os dados copiados na janela do designer e a verificar se os dados foram copiados corretamente.</span><span class="sxs-lookup"><span data-stu-id="08f50-134">The **Paste Preview** dialog box enables you to see a preview of data that is copied into the designer window and to ensure that the data is copied correctly.</span></span> <span data-ttu-id="08f50-135">Para acessar essa caixa de diálogo, copie os dados baseados em tabela no formato HTML para a área de transferência e, no designer, clique no menu **Editar** , clique em **Colar**, **Colar Acréscimo**ou **Colar Substituição**.</span><span class="sxs-lookup"><span data-stu-id="08f50-135">To access this dialog box, copy table-based data in the HTML format to the clipboard, and then in the designer, click on the **Edit** menu, and then click **Paste**, **Paste Append**, or **Paste Replace**.</span></span> <span data-ttu-id="08f50-136">As opções **Colar Acréscimo** e **Colar Substituição** só estarão disponíveis quando você adicionar ou substituir dados em uma tabela criada por meio de cópia e colagem da Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="08f50-136">The **Paste Append** and **Paste Replace** options are only available when you add or replace data in a table that was created by copying and pasting from the Clipboard.</span></span> <span data-ttu-id="08f50-137">Não é possível usar **Colar Acréscimo** ou **Colar Substituição** para adicionar dados em uma tabela de dados importados.</span><span class="sxs-lookup"><span data-stu-id="08f50-137">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data.</span></span>  
  
 <span data-ttu-id="08f50-138">As opções desta caixa de diálogo são diferentes, dependendo de você colar os dados em uma tabela completamente nova, colar os dados em uma tabela existente e, em seguida, substituir os dados existentes pelos novos, ou anexar os dados a uma tabela existente.</span><span class="sxs-lookup"><span data-stu-id="08f50-138">The options for this dialog box are different depending on whether you paste data into a completely new table, paste data into an existing table and then replace the existing data with the new data, or whether you append data to an existing table.</span></span>  
  
### <a name="paste-to-new-table"></a><span data-ttu-id="08f50-139">Colar em Nova Tabela</span><span class="sxs-lookup"><span data-stu-id="08f50-139">Paste to New Table</span></span>  
 <span data-ttu-id="08f50-140">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="08f50-140">**Table name**</span></span>  
 <span data-ttu-id="08f50-141">Especifique o nome da tabela que será criada no designer.</span><span class="sxs-lookup"><span data-stu-id="08f50-141">Specify the name of the table that will be created in the designer.</span></span>  
  
 <span data-ttu-id="08f50-142">**Dados a Serem Colados**</span><span class="sxs-lookup"><span data-stu-id="08f50-142">**Data to be pasted**</span></span>  
 <span data-ttu-id="08f50-143">Mostra um exemplo do conteúdo da Área de Transferência que será adicionado à tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="08f50-143">Shows a sample of the Clipboard contents that will be added to the destination table.</span></span>  
  
### <a name="paste-append"></a><span data-ttu-id="08f50-144">Colar Acréscimo</span><span class="sxs-lookup"><span data-stu-id="08f50-144">Paste Append</span></span>  
 <span data-ttu-id="08f50-145">**Dados existentes na tabela**</span><span class="sxs-lookup"><span data-stu-id="08f50-145">**Existing data in the table**</span></span>  
 <span data-ttu-id="08f50-146">Mostra um exemplo dos dados existentes na tabela, para que você possa verificar as colunas, os tipos de dados etc.</span><span class="sxs-lookup"><span data-stu-id="08f50-146">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="08f50-147">**Dados a Serem Colados**</span><span class="sxs-lookup"><span data-stu-id="08f50-147">**Data to be pasted**</span></span>  
 <span data-ttu-id="08f50-148">Mostra um exemplo do conteúdo da Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="08f50-148">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="08f50-149">Os dados existentes serão adicionados por estes dados.</span><span class="sxs-lookup"><span data-stu-id="08f50-149">The existing data will be appended by this data.</span></span>  
  
### <a name="paste-replace"></a><span data-ttu-id="08f50-150">Colar Substituição</span><span class="sxs-lookup"><span data-stu-id="08f50-150">Paste Replace</span></span>  
 <span data-ttu-id="08f50-151">**Dados existentes na tabela**</span><span class="sxs-lookup"><span data-stu-id="08f50-151">**Existing data in the table**</span></span>  
 <span data-ttu-id="08f50-152">Mostra um exemplo dos dados existentes na tabela, para que você possa verificar as colunas, os tipos de dados etc.</span><span class="sxs-lookup"><span data-stu-id="08f50-152">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="08f50-153">**Dados a Serem Colados**</span><span class="sxs-lookup"><span data-stu-id="08f50-153">**Data to be pasted**</span></span>  
 <span data-ttu-id="08f50-154">Mostra um exemplo do conteúdo da Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="08f50-154">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="08f50-155">Os dados existentes na tabela de destino serão excluídos e as novas linhas serão inseridas na tabela.</span><span class="sxs-lookup"><span data-stu-id="08f50-155">The existing data in the destination table will be deleted and the new rows will be inserted into the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f50-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="08f50-156">See Also</span></span>  
 <span data-ttu-id="08f50-157">[Importar dados &#40;SSAS de tabela&#41;](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="08f50-157">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="08f50-158">[Fontes de dados com suporte &#40;SSAS de tabela&#41;](tabular-models/data-sources-supported-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="08f50-158">[Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="08f50-159">Definir o tipo de dados de uma coluna &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="08f50-159">Set the Data Type of a Column &#40;SSAS Tabular&#41;</span></span>](tabular-models/set-the-data-type-of-a-column-ssas-tabular.md)  
  
  
