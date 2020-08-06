---
title: Editor de transformação pesquisa difusa (guia tabela de referência) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.referencetable.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 451f4e7d-1c8e-4784-b540-df0806509bf1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ce51dd64c9c5807ab23ac645694cfec29a36d52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570134"
---
# <a name="fuzzy-lookup-transformation-editor-reference-table-tab"></a><span data-ttu-id="63946-102">Editor de Transformação Pesquisa Difusa (guia Tabela de Referência)</span><span class="sxs-lookup"><span data-stu-id="63946-102">Fuzzy Lookup Transformation Editor (Reference Table Tab)</span></span>
  <span data-ttu-id="63946-103">Use a guia **Tabela de Referência** da caixa de diálogo **Editor de Transformação Pesquisa Difusa** para especificar a tabela de origem e o índice a ser usado na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63946-103">Use the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor** dialog box to specify the source table and the index to use for the lookup.</span></span> <span data-ttu-id="63946-104">A fonte de dados de referência deve ser uma tabela em um banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63946-104">The reference data source must be a table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63946-105">A transformação Pesquisa Difusa cria uma cópia de trabalho da tabela de referência.</span><span class="sxs-lookup"><span data-stu-id="63946-105">The Fuzzy Lookup transformation creates a working copy of the reference table.</span></span> <span data-ttu-id="63946-106">Os índices descritos abaixo são criados nesta tabela de trabalho usando uma tabela especial, não um índice do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] comum.</span><span class="sxs-lookup"><span data-stu-id="63946-106">The indexes described below are created on this working table by using a special table, not an ordinary [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] index.</span></span> <span data-ttu-id="63946-107">A transformação não modifica as tabelas de origem existentes a menos que você selecione **Manter índice armazenado**.</span><span class="sxs-lookup"><span data-stu-id="63946-107">The transformation does not modify the existing source tables unless you select **Maintain stored index**.</span></span> <span data-ttu-id="63946-108">Nesse caso, ela cria um gatilho na tabela de referência que atualiza a tabela de trabalho e a tabela de índices de pesquisa baseada em alterações na tabela de referência.</span><span class="sxs-lookup"><span data-stu-id="63946-108">In this case, it creates a trigger on the reference table that updates the working table and the lookup index table based on changes to the reference table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63946-109">As `Exhaustive` Propriedades e `MaxMemoryUsage` da transformação pesquisa difusa não estão disponíveis no **Editor de transformação pesquisa difusa**, mas podem ser definidas usando o **Editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="63946-109">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Lookup transformation are not available in the **Fuzzy Lookup Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="63946-110">Além disso, um valor maior que 100 para `MaxOutputMatchesPerInput` pode ser especificado somente no **Editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="63946-110">In addition, a value greater than 100 for `MaxOutputMatchesPerInput` can be specified only in the **Advanced Editor**.</span></span> <span data-ttu-id="63946-111">Para obter mais informações sobre estas propriedades, consulte a seção Transformação de Pesquisa Difusa em [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="63946-111">For more information on these properties, see the Fuzzy Lookup Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="63946-112">Para saber mais sobre a transformação Pesquisa Difusa, consulte [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="63946-112">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="63946-113">Opções</span><span class="sxs-lookup"><span data-stu-id="63946-113">Options</span></span>  
 <span data-ttu-id="63946-114">**Gerenciador de conexões OLE DB**</span><span class="sxs-lookup"><span data-stu-id="63946-114">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="63946-115">Selecione um gerenciador de conexões OLE DB existente na lista ou crie uma nova conexão clicando em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="63946-115">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="63946-116">**Novo**</span><span class="sxs-lookup"><span data-stu-id="63946-116">**New**</span></span>  
 <span data-ttu-id="63946-117">Crie uma nova conexão usando a caixa de diálogo **Configurar Gerenciador de Conexões OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="63946-117">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="63946-118">**Gerar novo índice**</span><span class="sxs-lookup"><span data-stu-id="63946-118">**Generate new index**</span></span>  
 <span data-ttu-id="63946-119">Especifique que a transformação deve criar um índice novo para ser utilizado na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63946-119">Specify that the transformation should create a new index to use for the lookup.</span></span>  
  
 <span data-ttu-id="63946-120">**Nome da tabela de referência**</span><span class="sxs-lookup"><span data-stu-id="63946-120">**Reference table name**</span></span>  
 <span data-ttu-id="63946-121">Selecione a tabela existente para usar como tabela de referência (pesquisa).</span><span class="sxs-lookup"><span data-stu-id="63946-121">Select the existing table to use as the reference (lookup) table.</span></span>  
  
 <span data-ttu-id="63946-122">**Armazenar novo índice**</span><span class="sxs-lookup"><span data-stu-id="63946-122">**Store new index**</span></span>  
 <span data-ttu-id="63946-123">Selecione esta opção para salvar o novo índice de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63946-123">Select this option if you want to save the new lookup index.</span></span>  
  
 <span data-ttu-id="63946-124">**Novo nome de índice**</span><span class="sxs-lookup"><span data-stu-id="63946-124">**New index name**</span></span>  
 <span data-ttu-id="63946-125">Se você optou por salvar o novo índice de pesquisa, digite um nome descritivo para o índice.</span><span class="sxs-lookup"><span data-stu-id="63946-125">If you have chosen to save the new lookup index, type a descriptive name for the index.</span></span>  
  
 <span data-ttu-id="63946-126">**Manter índice armazenado**</span><span class="sxs-lookup"><span data-stu-id="63946-126">**Maintain stored index**</span></span>  
 <span data-ttu-id="63946-127">Se você optou por salvar o novo índice de pesquisa, especifique se deseja que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] mantenha o índice.</span><span class="sxs-lookup"><span data-stu-id="63946-127">If you have chosen to save the new lookup index, specify whether you also want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to maintain the index.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63946-128">Quando você seleciona **Manter índice armazenado** na guia **Tabela de Referência** de **Editor de Transformação Pesquisa Difusa**, a transformação usa procedimentos armazenados gerenciados para manter o índice.</span><span class="sxs-lookup"><span data-stu-id="63946-128">When you select **Maintain stored index** on the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor**, the transformation uses managed stored procedures to maintain the index.</span></span> <span data-ttu-id="63946-129">Esses procedimentos armazenados gerenciados usam o recurso de integração de CLR (Common Language Runtime) no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63946-129">These managed stored procedures use the common language runtime (CLR) integration feature in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="63946-130">Por padrão, a integração de CLR no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não está habilitada.</span><span class="sxs-lookup"><span data-stu-id="63946-130">By default, CLR integration in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is not enabled.</span></span> <span data-ttu-id="63946-131">Para usar a funcionalidade **Manter índice armazenado** , você deve habilitar a integração de CLR.</span><span class="sxs-lookup"><span data-stu-id="63946-131">To use the **Maintain stored index** functionality, you must enable CLR integration.</span></span> <span data-ttu-id="63946-132">Para obter mais informações, consulte [Enabling CLR Integration](../relational-databases/clr-integration/clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="63946-132">For more information, see [Enabling CLR Integration](../relational-databases/clr-integration/clr-integration-enabling.md).</span></span>  
>   
>  <span data-ttu-id="63946-133">Como a opção **Manter índice armazenado** requer a integração CLR, esse recurso funciona apenas quando você seleciona uma tabela de referência em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] em que a integração CLR está habilitada.</span><span class="sxs-lookup"><span data-stu-id="63946-133">Because the **Maintain stored index** option requires CLR integration, this feature works only when you select a reference table on an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where CLR integration is enabled.</span></span>  
  
 <span data-ttu-id="63946-134">**Usar índice já existente**</span><span class="sxs-lookup"><span data-stu-id="63946-134">**Use existing index**</span></span>  
 <span data-ttu-id="63946-135">Especifique que a transformação deve usar um índice existente na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63946-135">Specify that the transformation should use an existing index for the lookup.</span></span>  
  
 <span data-ttu-id="63946-136">**Nome de um índice já existente**</span><span class="sxs-lookup"><span data-stu-id="63946-136">**Name of an existing index**</span></span>  
 <span data-ttu-id="63946-137">Selecione um índice de pesquisa criado anteriormente na lista.</span><span class="sxs-lookup"><span data-stu-id="63946-137">Select a previously created lookup index from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63946-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="63946-138">See Also</span></span>  
 <span data-ttu-id="63946-139">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="63946-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="63946-140">[Editor de transformação pesquisa difusa &#40;guia colunas&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="63946-140">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 [<span data-ttu-id="63946-141">Editor de Transformação Pesquisa Difusa &#40;Guia Avançado&#41;</span><span class="sxs-lookup"><span data-stu-id="63946-141">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
