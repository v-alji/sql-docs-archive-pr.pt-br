---
title: Atualizando dados (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 58dbe99a-288d-4f1c-9cd5-704d6836c945
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 49b6e7bc19c41911c626965b9d1de132796367f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685202"
---
# <a name="refreshing-data-mds-add-in-for-excel"></a><span data-ttu-id="fa7d8-102">Atualizando dados (suplemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="fa7d8-102">Refreshing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="fa7d8-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], atualize os dados quando desejar obter as informações mais recentes do repositório do MDS sem abrir uma nova planilha.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], refresh data when you want to get the latest information from the MDS repository without opening a new worksheet.</span></span> <span data-ttu-id="fa7d8-104">Você pode atualizar todas as células ou uma seleção de células.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-104">You can refresh either all cells or a selection of cells.</span></span> <span data-ttu-id="fa7d8-105">Isso pode ser útil quando você insere colunas com fórmulas personalizadas ou outros dados que não são gerenciados no MDS e deseja preservá-los.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-105">This can be useful when you have inserted columns with custom formulas or other data that is not managed in MDS and you want to preserve it.</span></span>  
  
## <a name="when-you-can-refresh-mds-managed-data"></a><span data-ttu-id="fa7d8-106">Quando é possível atualizar dados gerenciados no MDS</span><span class="sxs-lookup"><span data-stu-id="fa7d8-106">When You Can Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="fa7d8-107">Você pode atualizar dados gerenciados no MDS em uma planilha ativa quando a planilha ativa já contém dados gerenciados no MDS.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-107">You can refresh MDS-managed data in an active worksheet if the active worksheet already contains MDS-managed data.</span></span> <span data-ttu-id="fa7d8-108">Se você tiver alterado os valores dos atributos ou adicionado membros à planilha, será preciso publicar suas alterações antes de poder atualizar.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-108">If you have changed attribute values or added members to the worksheet, you must publish your changes before you can refresh.</span></span>  
  
## <a name="refreshing-a-selection"></a><span data-ttu-id="fa7d8-109">Atualizando uma seleção</span><span class="sxs-lookup"><span data-stu-id="fa7d8-109">Refreshing a Selection</span></span>  
 <span data-ttu-id="fa7d8-110">Você tem a opção de atualizar todas as células ou apenas as células selecionadas.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-110">You have the choice of refreshing all cells or refreshing only selected cells.</span></span> <span data-ttu-id="fa7d8-111">As células selecionadas devem ser contíguas.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-111">The selected cells must be contiguous.</span></span> <span data-ttu-id="fa7d8-112">Se um conjunto de células contíguas for selecionado, todas as células gerenciadas pelo MDS nesse conjunto serão atualizadas para exibir os valores atualmente armazenados no servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-112">If a set of contiguous cells is selected, all MDS managed cells in that set will be updated to display the values currently stored on the server.</span></span> <span data-ttu-id="fa7d8-113">As linhas e colunas inalteradas que não forem gerenciadas pelo MDS não serão afetadas de nenhuma forma.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-113">Unchanged rows and columns that are not managed by MDS are not affected in any way.</span></span>  
  
## <a name="what-happens-when-you-refresh-mds-managed-data"></a><span data-ttu-id="fa7d8-114">O que acontece ao atualizar dados gerenciados no MDS</span><span class="sxs-lookup"><span data-stu-id="fa7d8-114">What Happens When You Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="fa7d8-115">Ao atualizar dados no [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], o que acontece aos dados gerenciados no MDS da planilha depende do que mudou no repositório do MDS desde a última vez que você carregou os dados.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-115">When you refresh data in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], what happens to the MDS-managed data in the sheet depends on what has changed in the MDS repository since you last loaded the data.</span></span>  
  
-   <span data-ttu-id="fa7d8-116">Se novos membros tiverem sido adicionados ao repositório, eles serão adicionados ao final da planilha e realçados em verde.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-116">If new members have been added to repository, they are added to the end of the worksheet and are highlighted in green.</span></span>  
  
-   <span data-ttu-id="fa7d8-117">Se membros forem excluídos do repositório, eles serão excluídos da planilha.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-117">If members were deleted from the repository, they are deleted from the worksheet.</span></span>  
  
-   <span data-ttu-id="fa7d8-118">Se um valor de atributo tiver sido alterado no repositório do MDS, o valor será atualizado na planilha com o valor do repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-118">If an attribute value has changed in the MDS repository, the value in the worksheet is updated with value from the MDS repository.</span></span> <span data-ttu-id="fa7d8-119">A cor de célula não mudará.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-119">The cell color does not change.</span></span>  
  
> [!WARNING]
>  -   <span data-ttu-id="fa7d8-120">Na planilha ativa, se houver dados não gerenciados nas linhas abaixo dos dados gerenciados no MDS, os dados não gerenciados poderão ser substituídos.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-120">In the active worksheet, if non-managed data exists in rows beneath the MDS-managed data, the non-managed data may be overwritten.</span></span> <span data-ttu-id="fa7d8-121">Isso ocorre quando você atualiza a planilha e novas linhas de dados gerenciados no MDS, que substituem os dados não gerenciados, são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-121">This occurs when you refresh the sheet and new rows of MDS-managed data, which overlap with the non-managed data, are added.</span></span>  
> -   <span data-ttu-id="fa7d8-122">Ao atualizar, os comentários das células gerenciadas no MDS são excluídos.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-122">When you refresh, comments on MDS-managed cells are deleted.</span></span>  
  
## <a name="how-to-refresh-mds-managed-data"></a><span data-ttu-id="fa7d8-123">Como atualizar dados gerenciados no MDS</span><span class="sxs-lookup"><span data-stu-id="fa7d8-123">How to Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="fa7d8-124">No grupo **Conectar e Carregar** na faixa de opções, o botão **Atualizar** tem duas opções: **Atualizar Tudo** e **Atualizar Seleção**.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-124">In the **Connect and Load** group on the ribbon, the **Refresh** button has two options, **Refresh All** and **Refresh Selection**.</span></span> <span data-ttu-id="fa7d8-125">A ação padrão do botão de faixa de opções é **Atualizar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-125">The default action of the ribbon button is **Refresh All**.</span></span> <span data-ttu-id="fa7d8-126">Para atualizar a planilha inteira com os valores do servidor, clique no botão **Atualizar** ou escolha a opção **Atualizar Tudo** .</span><span class="sxs-lookup"><span data-stu-id="fa7d8-126">To refresh the entire sheet with values from the server, click the **Refresh** button or choose the **Refresh All** option.</span></span> <span data-ttu-id="fa7d8-127">Para atualizar somente algumas células de uma planilha, selecione as células (deve ser uma seleção contígua) e escolha a opção **Atualizar Seleção** .</span><span class="sxs-lookup"><span data-stu-id="fa7d8-127">To refresh only some of the cells in a sheet, select the cells (must be one contiguous selection) and choose the **Refresh Selection** option.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="fa7d8-128">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="fa7d8-128">Related Tasks</span></span>  
  
|<span data-ttu-id="fa7d8-129">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="fa7d8-129">Task Description</span></span>|<span data-ttu-id="fa7d8-130">Tópico</span><span class="sxs-lookup"><span data-stu-id="fa7d8-130">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="fa7d8-131">Crie uma conexão com um banco de dados do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa7d8-131">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="fa7d8-132">Conectar-se a um repositório do MDS &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="fa7d8-132">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="fa7d8-133">Carregue os dados do MDS no Excel.</span><span class="sxs-lookup"><span data-stu-id="fa7d8-133">Load MDS data into Excel.</span></span>|[<span data-ttu-id="fa7d8-134">Carregar dados do MDS no Excel</span><span class="sxs-lookup"><span data-stu-id="fa7d8-134">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="fa7d8-135">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="fa7d8-135">Related Content</span></span>  
  
-   [<span data-ttu-id="fa7d8-136">Conexões &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="fa7d8-136">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="fa7d8-137">Carregando dados &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="fa7d8-137">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="fa7d8-138">Suplemento do Master Data Services para Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="fa7d8-138">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
