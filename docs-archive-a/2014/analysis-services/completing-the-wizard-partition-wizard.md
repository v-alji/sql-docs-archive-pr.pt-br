---
title: Concluindo o assistente (Assistente para partições) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.finish.f1
ms.assetid: 68a4dd5d-94d9-4a02-be31-949a6da0ef51
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60be28170e8f8ec156d1c37149ddbc04b64bf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571050"
---
# <a name="completing-the-wizard-partition-wizard"></a><span data-ttu-id="66368-102">Concluindo o Assistente (Assistente para Partições)</span><span class="sxs-lookup"><span data-stu-id="66368-102">Completing the Wizard (Partition Wizard)</span></span>
  <span data-ttu-id="66368-103">Use a página **Concluindo o Assistente** para nomear a partição, definir o design de agregação da partição e, opcionalmente, implantar e processar a partição após concluir o Assistente para Partições.</span><span class="sxs-lookup"><span data-stu-id="66368-103">Use the **Completing the Wizard** page to name the partition, define the aggregation design for your partition, and optionally deploy and process the partition after completing the Partition Wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="66368-104">Opções</span><span class="sxs-lookup"><span data-stu-id="66368-104">Options</span></span>  
 <span data-ttu-id="66368-105">**Nome**</span><span class="sxs-lookup"><span data-stu-id="66368-105">**Name**</span></span>  
 <span data-ttu-id="66368-106">Digite o nome da nova partição.</span><span class="sxs-lookup"><span data-stu-id="66368-106">Type the name for the new partition.</span></span> <span data-ttu-id="66368-107">Se estiver trabalhando com várias tabelas, digite o prefixo que será combinado com o nome da tabela para criar cada nome de partição.</span><span class="sxs-lookup"><span data-stu-id="66368-107">If you are working with multiple tables, enter the prefix that will be combined with the table name to create each partition name.</span></span>  
  
 <span data-ttu-id="66368-108">**Opções de agregação**</span><span class="sxs-lookup"><span data-stu-id="66368-108">**Aggregation options**</span></span>  
 <span data-ttu-id="66368-109">Especifica a opção de agregação da partição.</span><span class="sxs-lookup"><span data-stu-id="66368-109">Specifies the aggregation option for the partition.</span></span>  
  
 <span data-ttu-id="66368-110">A tabela a seguir lista as opções de agregação disponíveis.</span><span class="sxs-lookup"><span data-stu-id="66368-110">The following table lists the aggregation options that are available.</span></span>  
  
|<span data-ttu-id="66368-111">Opção</span><span class="sxs-lookup"><span data-stu-id="66368-111">Option</span></span>|<span data-ttu-id="66368-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="66368-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="66368-113">**Criar agregações para a partição agora**</span><span class="sxs-lookup"><span data-stu-id="66368-113">**Design aggregations for the partition now**</span></span>|<span data-ttu-id="66368-114">Cria agregações para a nova partição depois que o Assistente para Partições cria a nova partição.</span><span class="sxs-lookup"><span data-stu-id="66368-114">Designs aggregations for the new partition after the Partition Wizard creates the new partition.</span></span> <span data-ttu-id="66368-115">A seleção dessa opção inicia o Assistente de Design de Agregação depois que você clica **em Concluir** no Assistente para Partições.</span><span class="sxs-lookup"><span data-stu-id="66368-115">Selecting this option starts the Aggregation Design Wizard after you click **Finish** in the Partition Wizard.</span></span> <span data-ttu-id="66368-116">Para obter mais informações sobre o Assistente de Design de Agregação, consulte a [Ajuda de F1 do Assistente de Design de Agregação](aggregation-design-wizard-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="66368-116">For more information about the Aggregation Design Wizard, see [Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md).</span></span>|  
|<span data-ttu-id="66368-117">**Criar as agregações mais tarde**</span><span class="sxs-lookup"><span data-stu-id="66368-117">**Design the aggregations later**</span></span>|<span data-ttu-id="66368-118">Cria a partição sem criar agregações neste momento.</span><span class="sxs-lookup"><span data-stu-id="66368-118">Creates the partition without designing aggregations at this time.</span></span>|  
|<span data-ttu-id="66368-119">**Copiar o design de agregação de uma partição existente**</span><span class="sxs-lookup"><span data-stu-id="66368-119">**Copy the aggregation design from an existing partition**</span></span>|<span data-ttu-id="66368-120">Copia o design de agregação de uma partição existente no grupo de medidas para a nova partição.</span><span class="sxs-lookup"><span data-stu-id="66368-120">Copies the aggregation design from an existing partition in the measure group to the new partition.</span></span> <span data-ttu-id="66368-121">Um clique nesta opção disponibiliza a opção **Copiar de** .</span><span class="sxs-lookup"><span data-stu-id="66368-121">Clicking this option makes the **Copy from** option available.</span></span> <span data-ttu-id="66368-122">Use a opção **Copiar de** para selecionar a partição da qual copiar o design de agregação.</span><span class="sxs-lookup"><span data-stu-id="66368-122">Use the **Copy from** option to select the partition from which to copy the aggregation design.</span></span><br /><br /> <span data-ttu-id="66368-123">Observe que as partições que podem ser mescladas no futuro devem ter a mesma estrutura de tabela e design de agregação.</span><span class="sxs-lookup"><span data-stu-id="66368-123">Note that partitions that may be merged in the future must have the same table structure and aggregation design.</span></span> <span data-ttu-id="66368-124">Se você mesclar a nova partição com uma partição existente no grupo de medidas, deverá copiar o design de agregação da partição existente na nova partição.</span><span class="sxs-lookup"><span data-stu-id="66368-124">If you might merge the new partition with an existing partition in the measure group, you should copy the aggregation design of the existing partition into the new partition.</span></span>|  
  
 <span data-ttu-id="66368-125">**Implantar e Processar Agora**</span><span class="sxs-lookup"><span data-stu-id="66368-125">**Deploy and Process Now**</span></span>  
 <span data-ttu-id="66368-126">Implanta e processa a partição para a instância do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] especificada na página **Locais de Processamento e Armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="66368-126">Deploys and processes the partition to the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance specified on the **Processing and Storage Locations** page.</span></span> <span data-ttu-id="66368-127">O assistente implanta e processa a partição depois que você clica em **Concluir** nessa página.</span><span class="sxs-lookup"><span data-stu-id="66368-127">The wizard deploys and processes the partition after you click **Finish** on this page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66368-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="66368-128">See Also</span></span>  
 [<span data-ttu-id="66368-129">Partições &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="66368-129">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
