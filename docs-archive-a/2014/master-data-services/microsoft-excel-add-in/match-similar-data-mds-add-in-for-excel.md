---
title: Corresponder dados semelhantes (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f6fd6fc1-3569-42a5-b6cb-87a921c88f3b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 70dea36de557c6fda909d06ee19ff8fa2ed6908d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680513"
---
# <a name="match-similar-data-mds-add-in-for-excel"></a><span data-ttu-id="055df-102">Corresponder dados semelhantes (Suplemento do MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="055df-102">Match Similar Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="055df-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use a funcionalidade do DQS (Data Quality Services) para localizar semelhanças em seus dados.</span><span class="sxs-lookup"><span data-stu-id="055df-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use Data Quality Services (DQS) functionality to find similarities in your data.</span></span>  
  
 <span data-ttu-id="055df-104">Para executar esse procedimento, você pode:</span><span class="sxs-lookup"><span data-stu-id="055df-104">To perform this procedure, you can:</span></span>  
  
-   <span data-ttu-id="055df-105">Usar a base de dados de conhecimento do Data Quality Services ou</span><span class="sxs-lookup"><span data-stu-id="055df-105">Use the default Data Quality Services knowledge base, or</span></span>  
  
-   <span data-ttu-id="055df-106">Criar sua própria base de dados de conhecimento do DQS personalizada e a política correspondente.</span><span class="sxs-lookup"><span data-stu-id="055df-106">Create your own custom DQS knowledge base and matching policy.</span></span> <span data-ttu-id="055df-107">Para obter mais informações, consulte [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="055df-107">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="055df-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="055df-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="055df-109">Você deve ter uma planilha que contenha dados gerenciados no MDS.</span><span class="sxs-lookup"><span data-stu-id="055df-109">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="055df-110">Para obter mais informações, consulte [carregar dados do MDS para o Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="055df-110">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="055df-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="055df-111">Optional.</span></span> <span data-ttu-id="055df-112">Você pode combinar outros dados com os dados gerenciados no MDS antes de verificar semelhanças.</span><span class="sxs-lookup"><span data-stu-id="055df-112">You can combine other data with the MDS-managed data before checking for similarities.</span></span> <span data-ttu-id="055df-113">Para obter mais informações, consulte [Combinar dados &#40;Suplemento MDS para Excel&#41;](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="055df-113">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
### <a name="to-find-similarities-by-using-the-default-knowledge-base"></a><span data-ttu-id="055df-114">Para localizar semelhanças usando a base de dados de conhecimento padrão</span><span class="sxs-lookup"><span data-stu-id="055df-114">To find similarities by using the default knowledge base</span></span>  
  
1.  <span data-ttu-id="055df-115">Na planilha que contém dados gerenciados no MDS, no grupo **Qualidade de Dados** , clique em **Corresponder Dados**.</span><span class="sxs-lookup"><span data-stu-id="055df-115">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="055df-116">Na caixa de diálogo **Corresponder Dados** , na lista **Base de Dados de Conhecimento do DQS** , selecione **Dados do DQS (padrão)**.</span><span class="sxs-lookup"><span data-stu-id="055df-116">In the **Match Data** dialog box, from the **DQS Knowledge Base** list, select **DQS Data (default)**.</span></span>  
  
3.  <span data-ttu-id="055df-117">Para cada coluna que contém dados que você queira corresponder, adicione uma linha na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="055df-117">For each column that contains data you want to match, add a row in the dialog box.</span></span> <span data-ttu-id="055df-118">Para obter informações sobre os campos desta caixa de diálogo, consulte [Como definir parâmetros de regra de correspondência](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span><span class="sxs-lookup"><span data-stu-id="055df-118">For information about the fields in this dialog box, see [How to Set Matching Rule Parameters](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span></span>  
  
4.  <span data-ttu-id="055df-119">Quando o total de todos os valores de peso for igual a 100%, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="055df-119">When the total of all weight values equals 100 percent, click **OK**.</span></span>  
  
### <a name="to-find-similarities-by-using-a-custom-knowledge-base"></a><span data-ttu-id="055df-120">Para localizar semelhanças usando a base de dados de conhecimento personalizada</span><span class="sxs-lookup"><span data-stu-id="055df-120">To find similarities by using a custom knowledge base</span></span>  
  
1.  <span data-ttu-id="055df-121">Na planilha que contém dados gerenciados no MDS, no grupo **Qualidade de Dados** , clique em **Corresponder Dados**.</span><span class="sxs-lookup"><span data-stu-id="055df-121">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="055df-122">Na lista **Base de Dados de Conhecimento do DQS** , selecione o nome da base de dados de conhecimento personalizada.</span><span class="sxs-lookup"><span data-stu-id="055df-122">From the **DQS Knowledge Base** list, select the name of your custom knowledge base.</span></span>  
  
3.  <span data-ttu-id="055df-123">Para cada coluna na planilha, selecione um domínio do DQS.</span><span class="sxs-lookup"><span data-stu-id="055df-123">For each column in the worksheet, select a DQS domain.</span></span>  
  
4.  <span data-ttu-id="055df-124">Quando todos os domínios do DQS estiverem mapeados para colunas na planilha, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="055df-124">When all DQS domains are mapped to columns in the worksheet, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="055df-125">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="055df-125">Next Steps</span></span>  
  
-   <span data-ttu-id="055df-126">Exiba informações adicionais para determinar quais dados são semelhantes.</span><span class="sxs-lookup"><span data-stu-id="055df-126">View additional information to determine which data is similar.</span></span> <span data-ttu-id="055df-127">Para obter mais informações, consulte [Colunas de correspondência de qualidade de dados &#40;Suplemento MDS para Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="055df-127">For more information, see [Data Quality Matching Columns &#40;MDS Add-in for Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="055df-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="055df-128">See Also</span></span>  
 <span data-ttu-id="055df-129">[Correspondência de qualidade de dados no Suplemento MDS para Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="055df-129">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="055df-130">Correspondência de dados</span><span class="sxs-lookup"><span data-stu-id="055df-130">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
