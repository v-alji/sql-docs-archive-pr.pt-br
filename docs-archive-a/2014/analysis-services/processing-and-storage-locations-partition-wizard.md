---
title: Locais de processamento e armazenamento (Assistente para partições) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifyprocessingandstorage.f1
ms.assetid: dda2dc57-923d-4db9-93a7-38e95770f3df
author: minewiskan
ms.author: owend
ms.openlocfilehash: 00ab88bac184f57bd2b4dcfdb8d00909a85ece4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685322"
---
# <a name="processing-and-storage-locations-partition-wizard"></a><span data-ttu-id="049ad-102">Locais de Processamento e Armazenamento (Assistente para Partições)</span><span class="sxs-lookup"><span data-stu-id="049ad-102">Processing and Storage Locations (Partition Wizard)</span></span>
  <span data-ttu-id="049ad-103">Use a página **Locais de Processamento e Armazenamento** para especificar a instância do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubo que contém a partição, bem como a instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que armazena os dados da partição.</span><span class="sxs-lookup"><span data-stu-id="049ad-103">Use the **Processing and Storage Locations** page to specify the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance of the cube that owns the partition, as well as the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that stores the data for the partition.</span></span> <span data-ttu-id="049ad-104">É possível definir uma partição como uma partição remota especificando uma instância remota do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou um local de armazenamento diferente do local de armazenamento padrão.</span><span class="sxs-lookup"><span data-stu-id="049ad-104">You can define a partition as a remote partition by specifying either a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a storage location other than the default storage location.</span></span> <span data-ttu-id="049ad-105">Para obter mais informações sobre partições remotas, consulte [Partições remotas](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="049ad-105">For more information about remote partitions, see [Remote Partitions](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span></span>  
  
## <a name="processing-location-options"></a><span data-ttu-id="049ad-106">Processando Opções de local</span><span class="sxs-lookup"><span data-stu-id="049ad-106">Processing location Options</span></span>  
 <span data-ttu-id="049ad-107">**Instância do servidor atual**</span><span class="sxs-lookup"><span data-stu-id="049ad-107">**Current server instance**</span></span>  
 <span data-ttu-id="049ad-108">Torna a instância atual do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] responsável por processar a partição.</span><span class="sxs-lookup"><span data-stu-id="049ad-108">Makes the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
 <span data-ttu-id="049ad-109">**Fonte de dados remota do Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="049ad-109">**Remote Analysis Services data source**</span></span>  
 <span data-ttu-id="049ad-110">Torna a instância remota do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] responsável por processar esta partição.</span><span class="sxs-lookup"><span data-stu-id="049ad-110">Makes a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing this partition.</span></span>  
  
 <span data-ttu-id="049ad-111">Na lista suspensa, selecione a fonte de dados que representa a instância remota do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que será responsável por processar a partição.</span><span class="sxs-lookup"><span data-stu-id="049ad-111">From the dropdown list, select the data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that will be responsible for processing the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="049ad-112">Ocorrerá um erro se você selecionar uma fonte de dados na qual a propriedade `Initial Catalog` da cadeia de conexão não está definida como um banco de dados correto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou se o banco de dados especificado na propriedade `Initial Catalog` da cadeia de conexão não oferecer suporte a partições remotas (ou seja, a propriedade `MasterDatasourceID` do banco de dados especificado não está definida como um valor válido).</span><span class="sxs-lookup"><span data-stu-id="049ad-112">An error occurs if you select a data source in which the `Initial Catalog` connection string property is not set to a valid [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, or if the database specified in the `Initial Catalog` connection string property does not support remote partitions (in other words, the `MasterDatasourceID` property of the specified database is not set to a valid value).</span></span>  
  
 <span data-ttu-id="049ad-113">**Novo**</span><span class="sxs-lookup"><span data-stu-id="049ad-113">**New**</span></span>  
 <span data-ttu-id="049ad-114">Cria uma nova fonte de dados que representa a instância remota do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] responsável por processar a partição.</span><span class="sxs-lookup"><span data-stu-id="049ad-114">Creates a new data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
## <a name="storage-location-options"></a><span data-ttu-id="049ad-115">Opções do local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="049ad-115">Storage location Options</span></span>  
 <span data-ttu-id="049ad-116">**Local do servidor padrão**</span><span class="sxs-lookup"><span data-stu-id="049ad-116">**Default server location**</span></span>  
 <span data-ttu-id="049ad-117">Torna a pasta de dados da instância atual do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o local de armazenamento dos dados de agregação e de indexação da partição.</span><span class="sxs-lookup"><span data-stu-id="049ad-117">Makes the data folder of the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="049ad-118">**Pasta especificada**</span><span class="sxs-lookup"><span data-stu-id="049ad-118">**Specified folder**</span></span>  
 <span data-ttu-id="049ad-119">Especifica o local de armazenamento dos dados de agregação e indexação da partição.</span><span class="sxs-lookup"><span data-stu-id="049ad-119">Specifies the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="049ad-120">**...**</span><span class="sxs-lookup"><span data-stu-id="049ad-120">**...**</span></span>  
 <span data-ttu-id="049ad-121">Exibe a caixa de diálogo **Procurar Pasta Remota** na qual é possível selecionar uma pasta para a opção **Pasta especificada**.</span><span class="sxs-lookup"><span data-stu-id="049ad-121">Displays the **Browse for Remote Folder** dialog box in which you can select a folder for **Specified folder**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="049ad-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="049ad-122">See Also</span></span>  
 <span data-ttu-id="049ad-123">[Ajuda F1 do assistente para partições &#40;Analysis Services de dados multidimensionais&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="049ad-123">[Partition Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="049ad-124">[Partições &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="049ad-124">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="049ad-125">Caixa de diálogo Procurar pasta remota &#40;Analysis Services-dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="049ad-125">Browse for Remote Folder Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browse-for-remote-folder-dialog-box-analysis-services-multidimensional-data.md)  
  
  
