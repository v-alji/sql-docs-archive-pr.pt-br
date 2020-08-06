---
title: Combinar dados (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: a867dc15-5a0d-457c-8304-ac323bcf9377
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bc2d5bffb6d7a12164a8643e9a790b32538f8979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680015"
---
# <a name="combine-data-mds-add-in-for-excel"></a><span data-ttu-id="e339d-102">Combinar dados (Suplemento do MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="e339d-102">Combine Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="e339d-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], combine dados de duas planilhas quando você desejar comparar dados antes de publicar.</span><span class="sxs-lookup"><span data-stu-id="e339d-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], combine data from two worksheets when you want to compare data before publishing.</span></span> <span data-ttu-id="e339d-104">Nesse procedimento, você combina dados de duas planilhas em uma.</span><span class="sxs-lookup"><span data-stu-id="e339d-104">In this procedure, you combine data from a two worksheets into one.</span></span> <span data-ttu-id="e339d-105">Assim, você pode executar mais comparações e determinar quais dados, se houver, publicar no repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="e339d-105">Then you can perform further comparisons and determine which data, if any, to publish to the MDS repository.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e339d-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e339d-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="e339d-107">Você deve ter uma planilha que contenha dados gerenciados no MDS.</span><span class="sxs-lookup"><span data-stu-id="e339d-107">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="e339d-108">Para obter mais informações, consulte [carregar dados do MDS para o Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e339d-108">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="e339d-109">Você deve ter uma planilha que contenha dados que queira combinar com os dados gerenciados no MDS.</span><span class="sxs-lookup"><span data-stu-id="e339d-109">You must have a worksheet that contains data you want to combine with MDS-managed data.</span></span> <span data-ttu-id="e339d-110">Essa planilha deve ter uma linha de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="e339d-110">This sheet must have a header row.</span></span>  
  
### <a name="to-combine-non-managed-data-into-an-mds-managed-sheet"></a><span data-ttu-id="e339d-111">Para combinar dados não gerenciados em uma planilha gerenciada no MDS</span><span class="sxs-lookup"><span data-stu-id="e339d-111">To combine non-managed data into an MDS-managed sheet</span></span>  
  
1.  <span data-ttu-id="e339d-112">Na planilha que contém dados gerenciados no MDS, no grupo **Publicar e Validar** , clique em **Combinar Dados**.</span><span class="sxs-lookup"><span data-stu-id="e339d-112">On the sheet that contains MDS-managed data, in the **Publish and Validate** group, click **Combine Data**.</span></span>  
  
2.  <span data-ttu-id="e339d-113">Na caixa de diálogo **Combinar Dados** , ao lado da caixa de texto **Intervalo a ser combinado com dados do MDS** , clique no ícone.</span><span class="sxs-lookup"><span data-stu-id="e339d-113">In the **Combine Data** dialog box, next to the **Range to combine with MDS data** text box, click the icon.</span></span> <span data-ttu-id="e339d-114">A caixa de diálogo é recolhida.</span><span class="sxs-lookup"><span data-stu-id="e339d-114">The dialog box contracts.</span></span>  
  
3.  <span data-ttu-id="e339d-115">Clique na planilha que contém os dados que você deseja combinar.</span><span class="sxs-lookup"><span data-stu-id="e339d-115">Click the sheet that contains the data you want to combine.</span></span>  
  
4.  <span data-ttu-id="e339d-116">Realce todas as células na planilha que você deseja combinar, inclusive a linha de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="e339d-116">Highlight all cells on the sheet that you want to combine, including the header row.</span></span>  
  
5.  <span data-ttu-id="e339d-117">Na caixa de diálogo **Combinar Dados** , clique no ícone.</span><span class="sxs-lookup"><span data-stu-id="e339d-117">In the **Combine Data** dialog box, click the icon.</span></span> <span data-ttu-id="e339d-118">A caixa de diálogo é expandida.</span><span class="sxs-lookup"><span data-stu-id="e339d-118">The dialog box expands.</span></span>  
  
6.  <span data-ttu-id="e339d-119">Para uma coluna listada para a entidade do MDS, selecione uma coluna em **Coluna Correspondente**.</span><span class="sxs-lookup"><span data-stu-id="e339d-119">For a column listed for the MDS entity, select a column under **Corresponding Column**.</span></span> <span data-ttu-id="e339d-120">Nem todas as colunas do MDS precisam de colunas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="e339d-120">All MDS columns do not need corresponding columns.</span></span>  
  
7.  <span data-ttu-id="e339d-121">Clique em **Combinar**.</span><span class="sxs-lookup"><span data-stu-id="e339d-121">Click **Combine**.</span></span> <span data-ttu-id="e339d-122">Uma coluna de **SOURCE** é exibida, indicando se os dados são do MDS ou de uma origem externa.</span><span class="sxs-lookup"><span data-stu-id="e339d-122">A **SOURCE** column is displayed, indicating whether the data is from MDS or an external source.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e339d-123">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e339d-123">Next Steps</span></span>  
  
-   <span data-ttu-id="e339d-124">Para localizar semelhanças entre os dados gerenciados no MDS e dados externos, consulte [Corresponder dados semelhantes &#40;Suplemento MDS para Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="e339d-124">To find similarities between the MDS-managed and external data, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e339d-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e339d-125">See Also</span></span>  
 <span data-ttu-id="e339d-126">[Carregando dados &#40;Suplemento MDS para Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="e339d-126">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="e339d-127">Correspondência de qualidade de dados no Suplemento do MDS para Excel</span><span class="sxs-lookup"><span data-stu-id="e339d-127">Data Quality Matching in the MDS Add-in for Excel</span></span>](data-quality-matching-in-the-mds-add-in-for-excel.md)  
  
  
