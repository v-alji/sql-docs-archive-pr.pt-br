---
title: Mapear colunas para domínios de composição | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9422412-8a3d-45ae-af7f-072c902a09ba
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a665b2096579c9da35a1b69be46c4ba6103610f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582040"
---
# <a name="map-columns-to-composite-domains"></a><span data-ttu-id="e6fc1-102">Mapear colunas para domínios compostos</span><span class="sxs-lookup"><span data-stu-id="e6fc1-102">Map Columns to Composite Domains</span></span>
  <span data-ttu-id="e6fc1-103">Um domínio composto consiste em dois ou mais domínios únicos.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-103">A composite domain consists of two or more single domains.</span></span> <span data-ttu-id="e6fc1-104">Você pode mapear várias colunas para o domínio, ou pode mapear uma única coluna com valores limitados para o domínio.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-104">You can map multiple columns to the domain, or you can map a single column with delimited values to the domain.</span></span>  
  
 <span data-ttu-id="e6fc1-105">Quando você tiver várias colunas, deverá mapear uma coluna para cada domínio único no domínio composto para aplicar as regras do domínio composto para a limpeza de dados.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-105">When you have multiple columns, you must map a column to each single domain in the composite domain to apply the composite domain rules to data cleansing.</span></span> <span data-ttu-id="e6fc1-106">Selecione os domínios únicos contidos no domínio composto, no Cliente Data Quality.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-106">You select the single domains contained in the composite domain, in the Data Quality Client.</span></span> <span data-ttu-id="e6fc1-107">Para obter mais informações, consulte [Criar um domínio composto](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="e6fc1-107">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
 <span data-ttu-id="e6fc1-108">Quando você tiver uma única coluna com valores limitados, deverá mapear a única coluna para o domínio composto.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-108">When you have a single column with delimited values, you must map the single column to the composite domain.</span></span> <span data-ttu-id="e6fc1-109">Os valores devem aparecer na mesma ordem que os domínios únicos aparecem no domínio composto.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-109">The values must appear in the same order as the single domains appear in the composite domain.</span></span> <span data-ttu-id="e6fc1-110">O delimitador na fonte de dados deve corresponder ao delimitador usado para analisar os valores do domínio composto.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-110">The delimiter in the data source must match the delimiter that is used to parse the composite domain values.</span></span> <span data-ttu-id="e6fc1-111">Você seleciona o delimitador para o domínio composto, bem como define outras propriedades, no Cliente Data Quality.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-111">You select the delimiter for the composite domain, as well as set other properties, in the Data Quality Client.</span></span> <span data-ttu-id="e6fc1-112">Para obter mais informações, consulte [Criar um domínio composto](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="e6fc1-112">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
### <a name="to-map-multiple-columns-to-a-composite-domain"></a><span data-ttu-id="e6fc1-113">Para mapear várias colunas para um domínio composto</span><span class="sxs-lookup"><span data-stu-id="e6fc1-113">To map multiple columns to a composite domain</span></span>  
  
1.  <span data-ttu-id="e6fc1-114">Clique com o botão direito do mouse na transformação Limpeza DQS e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-114">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="e6fc1-115">Na guia **Gerenciador de Conexões** , confirme se o domínio composto é exibido na lista de domínios disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-115">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="e6fc1-116">Na guia **Mapeamento** , selecione as colunas na área **Colunas de Entrada Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="e6fc1-116">On the **Mapping** tab, select the columns in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="e6fc1-117">Para cada coluna listada no campo **Coluna de Entrada** , selecione um domínio único no campo **Domínio** .</span><span class="sxs-lookup"><span data-stu-id="e6fc1-117">For each column listed in the **Input Column** field, select a single domain in the **Domain** field.</span></span> <span data-ttu-id="e6fc1-118">Selecione somente domínios únicos que estão no domínio composto.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-118">Select only single domains that are in the composite domain.</span></span>  
  
5.  <span data-ttu-id="e6fc1-119">Quando necessário, modifique os nomes que aparecem nos campos **Alias de Origem**, **Alias de Saída**e **Alias de Status** .</span><span class="sxs-lookup"><span data-stu-id="e6fc1-119">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="e6fc1-120">Conforme o necessário, defina as propriedades na guia **Avançado** . Para obter mais informações sobre as propriedades, consulte [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="e6fc1-120">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
### <a name="to-map-a-column-with-delimited-values-to-a-composite-domain"></a><span data-ttu-id="e6fc1-121">Para mapear uma coluna com valores delimitados para um domínio composto</span><span class="sxs-lookup"><span data-stu-id="e6fc1-121">To map a column with delimited values to a composite domain</span></span>  
  
1.  <span data-ttu-id="e6fc1-122">Clique com o botão direito do mouse na transformação Limpeza DQS e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-122">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="e6fc1-123">Na guia **Gerenciador de Conexões** , confirme se o domínio composto é exibido na lista de domínios disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e6fc1-123">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="e6fc1-124">Na guia **Mapeamento** , selecione a coluna na área **Colunas de Entrada Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="e6fc1-124">On the **Mapping** tab, select the column in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="e6fc1-125">Para a coluna listada no campo **Coluna de Entrada** , selecione o domínio composto no campo **Domínio** .</span><span class="sxs-lookup"><span data-stu-id="e6fc1-125">For the column listed in the **Input Column** field, select the composite domain in the **Domain** field.</span></span>  
  
5.  <span data-ttu-id="e6fc1-126">Quando necessário, modifique os nomes que aparecem nos campos **Alias de Origem**, **Alias de Saída**e **Alias de Status** .</span><span class="sxs-lookup"><span data-stu-id="e6fc1-126">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="e6fc1-127">Conforme o necessário, defina as propriedades na guia **Avançado** . Para obter mais informações sobre as propriedades, consulte [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="e6fc1-127">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6fc1-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e6fc1-128">See Also</span></span>  
 [<span data-ttu-id="e6fc1-129">Transformação Limpeza DQS</span><span class="sxs-lookup"><span data-stu-id="e6fc1-129">DQS Cleansing Transformation</span></span>](dqs-cleansing-transformation.md)  
  
  
