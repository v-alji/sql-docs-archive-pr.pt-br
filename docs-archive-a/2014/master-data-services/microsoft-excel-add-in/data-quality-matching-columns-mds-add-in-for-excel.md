---
title: Colunas de correspondência de qualidade de dados (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f683fdc6-0d4c-4793-8143-567616cb2094
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 939ec9727cc81ce3b206b8bc7ca3ed8dd62c3877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568666"
---
# <a name="data-quality-matching-columns-mds-add-in-for-excel"></a><span data-ttu-id="7554c-102">Colunas de correspondência de qualidade de dados (Suplemento do MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="7554c-102">Data Quality Matching Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="7554c-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], após a correspondência de dados, no grupo **Qualidade de Dados** na faixa de opções, você pode clicar em **Mostrar Detalhes** para exibir colunas que fornecem detalhes correspondentes.</span><span class="sxs-lookup"><span data-stu-id="7554c-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], after you match data, in the **Data Quality** group on the ribbon, you can click **Show Details** to display columns that provide matching details.</span></span>  
  
 <span data-ttu-id="7554c-104">A tabela a seguir mostra as colunas que são exibidas durante a correspondência de dados.</span><span class="sxs-lookup"><span data-stu-id="7554c-104">The following table shows the columns that are displayed when matching data.</span></span>  
  
|<span data-ttu-id="7554c-105">Nome</span><span class="sxs-lookup"><span data-stu-id="7554c-105">Name</span></span>|<span data-ttu-id="7554c-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="7554c-106">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="7554c-107">**CLUSTER_ID**</span><span class="sxs-lookup"><span data-stu-id="7554c-107">**CLUSTER_ID**</span></span>|<span data-ttu-id="7554c-108">Um identificador exclusivo usado para agrupar registros semelhantes.</span><span class="sxs-lookup"><span data-stu-id="7554c-108">A unique identifier used to group similar records.</span></span> <span data-ttu-id="7554c-109">Todas as linhas semelhantes têm a mesma **CLUSTER_ID**.</span><span class="sxs-lookup"><span data-stu-id="7554c-109">All rows that are similar have the same **CLUSTER_ID**.</span></span> <span data-ttu-id="7554c-110">Se nenhum **CLUSTER_ID** é exibido para uma linha, nenhum registro semelhante foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="7554c-110">If no **CLUSTER_ID** is displayed for a row, then no similar records were found.</span></span>|  
|<span data-ttu-id="7554c-111">**RECORD_ID**</span><span class="sxs-lookup"><span data-stu-id="7554c-111">**RECORD_ID**</span></span>|<span data-ttu-id="7554c-112">Um identificador exclusivo usado para identificar registros.</span><span class="sxs-lookup"><span data-stu-id="7554c-112">A unique identifier used to identify records.</span></span> <span data-ttu-id="7554c-113">Semelhante ao valor de Código armazenado no repositório do MDS é um valor usado para identificar um registro.</span><span class="sxs-lookup"><span data-stu-id="7554c-113">Similar to the Code value stored in the MDS repository, it is a value used to identify a record.</span></span> <span data-ttu-id="7554c-114">É gerado automaticamente a cada correspondência de hora.</span><span class="sxs-lookup"><span data-stu-id="7554c-114">It is generated automatically each time matching takes place.</span></span>|  
|<span data-ttu-id="7554c-115">**PIVOT_MARK**</span><span class="sxs-lookup"><span data-stu-id="7554c-115">**PIVOT_MARK**</span></span>|<span data-ttu-id="7554c-116">Um registro arbitrário com o qual outros registros são comparados; não tem um valor de pontuação.</span><span class="sxs-lookup"><span data-stu-id="7554c-116">An arbitrary record that other records are compared to; it does not have a score value.</span></span>|  
|<span data-ttu-id="7554c-117">**PLACAR**</span><span class="sxs-lookup"><span data-stu-id="7554c-117">**SCORE**</span></span>|<span data-ttu-id="7554c-118">Representa o grau de similaridade dos registros no grupo com o registro dinâmico.</span><span class="sxs-lookup"><span data-stu-id="7554c-118">Represents how similar the records in the group are to the pivot record.</span></span> <span data-ttu-id="7554c-119">Essa pontuação é determinada pelo DQS.</span><span class="sxs-lookup"><span data-stu-id="7554c-119">This score is determined by DQS.</span></span> <span data-ttu-id="7554c-120">Se nenhuma pontuação for exibida, o registro será dinâmico para outros registros ou nenhuma correspondência será encontrada.</span><span class="sxs-lookup"><span data-stu-id="7554c-120">If no score is displayed, either the record is the pivot for other records, or no matches were found.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7554c-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7554c-121">See Also</span></span>  
 <span data-ttu-id="7554c-122">[Correspondência de qualidade de dados no Suplemento MDS para Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="7554c-122">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="7554c-123">[Corresponder dados semelhantes &#40;Suplemento MDS para Excel&#41;](match-similar-data-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="7554c-123">[Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="7554c-124">Correspondência de dados</span><span class="sxs-lookup"><span data-stu-id="7554c-124">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
