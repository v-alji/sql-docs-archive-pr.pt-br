---
title: Correspondência de qualidade de dados no Suplemento MDS para Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: be78d051-0d56-46d3-bb89-327e218dadd6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 037e535452e7f19644837e0cbcfd02efec5422b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581983"
---
# <a name="data-quality-matching-in-the-mds-add-in-for-excel"></a><span data-ttu-id="0595d-102">Correspondência de qualidade de dados no Suplemento do MDS para Excel</span><span class="sxs-lookup"><span data-stu-id="0595d-102">Data Quality Matching in the MDS Add-in for Excel</span></span>
  <span data-ttu-id="0595d-103">Com o tempo, você desejará adicionar mais dados ao repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="0595d-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="0595d-104">Antes de adicionar dados, talvez seja útil comparar os novos dados aos dados que já são gerenciados no MDS, para assegurar que você não está adicionando dados duplicados ou inexatos.</span><span class="sxs-lookup"><span data-stu-id="0595d-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure you are not adding duplicate or inaccurate data.</span></span>  
  
 <span data-ttu-id="0595d-105">O [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] MDS usa o recurso DQS (Data Quality Services) do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para associar a dados semelhantes.</span><span class="sxs-lookup"><span data-stu-id="0595d-105">The MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] uses the Data Quality Services (DQS) feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to match data that's similar.</span></span> <span data-ttu-id="0595d-106">Quando você usar a funcionalidade correspondente no suplemento, serão agrupados registros semelhantes e uma pontuação que representa a exatidão do resultado exibido.</span><span class="sxs-lookup"><span data-stu-id="0595d-106">When you use the matching functionality in the Add-in, similar records are grouped together and a score that represents the accuracy of the result is displayed.</span></span> <span data-ttu-id="0595d-107">Para obter mais informações sobre a funcionalidade de correspondência fornecida pelo DQS, consulte [Correspondência de dados](../../data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="0595d-107">For more information about the matching functionality provided by DQS, see [Data Matching](../../data-quality-services/data-matching.md).</span></span>  
  
## <a name="workflow-for-data-quality-matching"></a><span data-ttu-id="0595d-108">Fluxo de trabalho para correspondência de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="0595d-108">Workflow for Data Quality Matching</span></span>  
 <span data-ttu-id="0595d-109">Ao usar o DQS com o MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use o fluxo de trabalho seguinte:</span><span class="sxs-lookup"><span data-stu-id="0595d-109">When using DQS with the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use the following workflow:</span></span>  
  
1.  <span data-ttu-id="0595d-110">Recupere uma lista de dados gerenciados no MDS e combine-a com uma lista não gerenciada no MDS.</span><span class="sxs-lookup"><span data-stu-id="0595d-110">Retrieve a list of MDS-managed data and combine it with a list that is not managed in MDS.</span></span> <span data-ttu-id="0595d-111">Para obter mais informações, consulte [Combinar dados &#40;Suplemento MDS para Excel&#41;](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="0595d-111">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="0595d-112">Use o conhecimento do DQS para comparar os dados na lista combinada.</span><span class="sxs-lookup"><span data-stu-id="0595d-112">Use DQS knowledge to compare the data in the combined list.</span></span> <span data-ttu-id="0595d-113">Para obter mais informações, consulte [Corresponder dados semelhantes &#40;Suplemento MDS para Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="0595d-113">For more information, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
3.  <span data-ttu-id="0595d-114">Para exibir mais detalhes sobre as semelhanças encontradas pelo DQS, mostre as colunas de detalhe.</span><span class="sxs-lookup"><span data-stu-id="0595d-114">To view more details about the similarities found by DQS, show the detail columns.</span></span>  
  
4.  <span data-ttu-id="0595d-115">Analise os resultados e determine quais dados devem ser adicionados ao repositório do MDS e quais dados são duplicados.</span><span class="sxs-lookup"><span data-stu-id="0595d-115">Go through the results and determine which data should be added to the MDS repository and which data is duplicated.</span></span>  
  
5.  <span data-ttu-id="0595d-116">Publique os dados novos e/ou atualizados no repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="0595d-116">Publish the new and/or updated data to the MDS repository.</span></span>  
  
## <a name="knowledge-bases"></a><span data-ttu-id="0595d-117">Bases de Dados de Conhecimento</span><span class="sxs-lookup"><span data-stu-id="0595d-117">Knowledge Bases</span></span>  
 <span data-ttu-id="0595d-118">Os resultados correspondentes fornecidos no suplemento se baseiam em uma base de dados de conhecimento do DQS.</span><span class="sxs-lookup"><span data-stu-id="0595d-118">The matching results provided in the Add-in are based on a DQS knowledge base.</span></span>  
  
-   <span data-ttu-id="0595d-119">A base de dados de conhecimento padrão (Dados do DQS) é criada quando o DQS é instalado.</span><span class="sxs-lookup"><span data-stu-id="0595d-119">The default knowledge base (DQS Data) is created when DQS is installed.</span></span> <span data-ttu-id="0595d-120">Se você escolher usar a base de conhecimento padrão (sem adicionar uma política de correspondência à base de conhecimento padrão no Cliente Data Quality), você deverá mapear colunas na planilha para domínios na base de dados de conhecimento e, em seguida, atribuir um valor de peso aos domínios que você escolher.</span><span class="sxs-lookup"><span data-stu-id="0595d-120">If you choose to use the default knowledge base (without adding a matching policy to the default knowledge base in the Data Quality Client), you must map columns in the worksheet to domains in the knowledge base, and then assign a weight value to the domains you choose.</span></span>  
  
-   <span data-ttu-id="0595d-121">Você pode usar o Cliente Data Quality para criar uma nova base de dados de conhecimento com uma política de correspondência ou adicionar uma política de correspondência à base de dados de conhecimento padrão.</span><span class="sxs-lookup"><span data-stu-id="0595d-121">You can use the Data Quality Client to create a new knowledge base with a matching policy, or to add a matching policy to the default knowledge base.</span></span> <span data-ttu-id="0595d-122">Nesse caso, os valores de peso são determinados pela política correspondente que você já criou e só é necessário mapear as colunas para os domínios.</span><span class="sxs-lookup"><span data-stu-id="0595d-122">In this case, the weight values are determined by the matching policy you already created and you need only to map the columns to the domains.</span></span> <span data-ttu-id="0595d-123">Para obter mais informações, consulte [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="0595d-123">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
 <span data-ttu-id="0595d-124">Para obter mais informações sobre bases de dados de conhecimento, consulte [Bases de Dados de Conhecimento DQS e domínios](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="0595d-124">For more information about knowledge bases, see [DQS Knowledge Bases and Domains](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0595d-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0595d-125">Related Tasks</span></span>  
  
|<span data-ttu-id="0595d-126">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="0595d-126">Task Description</span></span>|<span data-ttu-id="0595d-127">Tópico</span><span class="sxs-lookup"><span data-stu-id="0595d-127">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="0595d-128">Combine dados externos com dados gerenciados no MDS na preparação para compará-los.</span><span class="sxs-lookup"><span data-stu-id="0595d-128">Combine external data with MDS-managed data in preparation to compare it.</span></span>|[<span data-ttu-id="0595d-129">Combinar dados &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0595d-129">Combine Data &#40;MDS Add-in for Excel&#41;</span></span>](combine-data-mds-add-in-for-excel.md)|  
|<span data-ttu-id="0595d-130">Use o conhecimento do DQS para localizar semelhanças em seus dados.</span><span class="sxs-lookup"><span data-stu-id="0595d-130">Use DQS knowledge to find similarities in your data.</span></span>|[<span data-ttu-id="0595d-131">Corresponder dados semelhantes &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0595d-131">Match Similar Data &#40;MDS Add-in for Excel&#41;</span></span>](match-similar-data-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="0595d-132">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="0595d-132">Related Content</span></span>  
  
-   [<span data-ttu-id="0595d-133">Publicando dados &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0595d-133">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="0595d-134">Correspondência de dados</span><span class="sxs-lookup"><span data-stu-id="0595d-134">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
