---
title: Criar uma entidade (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d354abb3-88fe-4b40-a374-f6256b84ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 87ad67f7347da87c67afc11590df6775af4cf3d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568675"
---
# <a name="create-an-entity-mds-add-in-for-excel"></a><span data-ttu-id="5d3df-102">Criar uma entidade (Suplemento do MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="5d3df-102">Create an Entity (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="5d3df-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], os administradores podem criar novas entidades para armazenar dados.</span><span class="sxs-lookup"><span data-stu-id="5d3df-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create new entities to store data.</span></span> <span data-ttu-id="5d3df-104">Quando você cria uma entidade, deve carregar pelo menos uma amostragem dos dados que deseja armazenar.</span><span class="sxs-lookup"><span data-stu-id="5d3df-104">When you create an entity you should load at least a sampling of the data you want to store.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5d3df-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5d3df-105">Prerequisites</span></span>  
 <span data-ttu-id="5d3df-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="5d3df-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5d3df-107">Você precisa ter permissão para acessar as áreas funcionais **Administração do Sistema** e **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="5d3df-107">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="5d3df-108">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="5d3df-108">You must be a model administrator.</span></span> <span data-ttu-id="5d3df-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5d3df-109">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="5d3df-110">Você deve ter um modelo existente no qual criar a entidade.</span><span class="sxs-lookup"><span data-stu-id="5d3df-110">You must have an existing model to create the entity in.</span></span> <span data-ttu-id="5d3df-111">Para obter mais informações, consulte [Criar um modelo &#40;Master Data Services&#41;](../create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5d3df-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../create-a-model-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="5d3df-112">Verifique se seus dados atendem aos requisitos seguintes:</span><span class="sxs-lookup"><span data-stu-id="5d3df-112">Ensure that your data meets the following requirements:</span></span>  
  
    -   <span data-ttu-id="5d3df-113">Os dados devem ter uma linha de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="5d3df-113">The data should have a header row.</span></span>  
  
    -   <span data-ttu-id="5d3df-114">É útil ter colunas **Nome** e **Código** .</span><span class="sxs-lookup"><span data-stu-id="5d3df-114">It is helpful to have **Name** and **Code** columns.</span></span> <span data-ttu-id="5d3df-115">**Código** é um identificador exclusivo de cada linha.</span><span class="sxs-lookup"><span data-stu-id="5d3df-115">**Code** is a unique identifier for each row.</span></span>  
  
    -   <span data-ttu-id="5d3df-116">Você deve ter pelo menos uma linha de dados diferente do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="5d3df-116">You should have at least one row of data other than the header.</span></span> <span data-ttu-id="5d3df-117">Nem todas as colunas precisam de valores, mas os dados devem ser representativos dos dados que estarão na entidade.</span><span class="sxs-lookup"><span data-stu-id="5d3df-117">All columns do not need values, but the data should be representative of the data that will be in the entity.</span></span>  
  
    -   <span data-ttu-id="5d3df-118">Se houver uma coluna que contém um identificador exclusivo (conhecido no MDS como **Código**), verifique se os valores são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="5d3df-118">If you have a column that contains a unique identifier (known in MDS as **Code**), ensure that the values are unique.</span></span> <span data-ttu-id="5d3df-119">Se nenhuma coluna contiver identificadores, você poderá tê-los gerado automaticamente ao criar a entidade.</span><span class="sxs-lookup"><span data-stu-id="5d3df-119">If no column contains identifiers, you can have them generated automatically when you create the entity.</span></span>  
  
    -   <span data-ttu-id="5d3df-120">Verifique se nenhuma célula contém fórmulas.</span><span class="sxs-lookup"><span data-stu-id="5d3df-120">Ensure that no cells contain formulas.</span></span>  
  
    -   <span data-ttu-id="5d3df-121">Verifique se nenhuma célula valores de hora.</span><span class="sxs-lookup"><span data-stu-id="5d3df-121">Ensure that no cells contain time values.</span></span> <span data-ttu-id="5d3df-122">Valores de data podem ser salvos no MDS, mas valores de hora não podem.</span><span class="sxs-lookup"><span data-stu-id="5d3df-122">Date values can be saved in MDS but time values cannot.</span></span>  
  
### <a name="to-create-an-entity-and-load-data"></a><span data-ttu-id="5d3df-123">Para criar uma entidade e carregar dados</span><span class="sxs-lookup"><span data-stu-id="5d3df-123">To create an entity and load data</span></span>  
  
1.  <span data-ttu-id="5d3df-124">Abra ou crie uma planilha do Excel que contenha os dados que você deseja carregar.</span><span class="sxs-lookup"><span data-stu-id="5d3df-124">Open or create an Excel worksheet that contains data you want to load.</span></span>  
  
2.  <span data-ttu-id="5d3df-125">Selecione as células que você deseja carregar na nova entidade.</span><span class="sxs-lookup"><span data-stu-id="5d3df-125">Select the cells you want to load into the new entity.</span></span>  
  
3.  <span data-ttu-id="5d3df-126">Na guia **Dados Mestre** , no grupo **Compilar Modelo** , clique em **Criar Entidade**.</span><span class="sxs-lookup"><span data-stu-id="5d3df-126">On the **Master Data** tab, in the **Build Model** group, click **Create Entity**.</span></span>  
  
4.  <span data-ttu-id="5d3df-127">Se você for solicitado a se conectar a um repositório do MDS, faça isso.</span><span class="sxs-lookup"><span data-stu-id="5d3df-127">If you are prompted to connect to an MDS repository, connect.</span></span>  
  
5.  <span data-ttu-id="5d3df-128">Na caixa de diálogo **Criar Entidade** , deixe o intervalo padrão ou altere-o para aplicar aos dados que você deseja carregar.</span><span class="sxs-lookup"><span data-stu-id="5d3df-128">In the **Create Entity** dialog box, leave the default range or change it to apply to the data you want to load.</span></span>  
  
6.  <span data-ttu-id="5d3df-129">Não desmarque a caixa de seleção **Meus dados têm cabeçalhos** .</span><span class="sxs-lookup"><span data-stu-id="5d3df-129">Do not clear the **My data has headers** check box.</span></span>  
  
7.  <span data-ttu-id="5d3df-130">Na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="5d3df-130">From the **Model** list, select a model.</span></span>  
  
8.  <span data-ttu-id="5d3df-131">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="5d3df-131">From the **Version** list, select a version.</span></span>  
  
9. <span data-ttu-id="5d3df-132">Na caixa **Nome da nova entidade** , digite um nome para a entidade.</span><span class="sxs-lookup"><span data-stu-id="5d3df-132">In the **New entity name** box, type a name for the entity.</span></span>  
  
10. <span data-ttu-id="5d3df-133">Na lista **Código** , selecione a coluna que contém identificadores exclusivos ou que tem códigos gerados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5d3df-133">From the **Code** list, select the column that contains unique identifiers or have codes generated automatically.</span></span>  
  
11. <span data-ttu-id="5d3df-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5d3df-134">Optional.</span></span> <span data-ttu-id="5d3df-135">Na lista **Nome** , selecione uma coluna que contém nomes para cada membro.</span><span class="sxs-lookup"><span data-stu-id="5d3df-135">From the **Name** list, select a column that contains names for each member.</span></span>  
  
12. <span data-ttu-id="5d3df-136">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d3df-136">Click **OK**.</span></span> <span data-ttu-id="5d3df-137">Após a criação com êxito da entidade, uma nova linha de cabeçalho é exibida, as células são realçadas e o nome da planilha é atualizado para corresponder ao nome da entidade.</span><span class="sxs-lookup"><span data-stu-id="5d3df-137">When the entity has been created successfully, a new header row is displayed, the cells are highlighted, and the sheet name is updated to match the entity name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5d3df-138">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5d3df-138">Next Steps</span></span>  
  
-   <span data-ttu-id="5d3df-139">Para exibir os erros que ocorreram, no grupo **Publicar e Validar** , clique em **Mostrar Status**.</span><span class="sxs-lookup"><span data-stu-id="5d3df-139">To view errors that occurred, in the **Publish and Validate** group, click **Show Status**.</span></span> <span data-ttu-id="5d3df-140">As colunas ValidationStatus e InputStatus são exibidas.</span><span class="sxs-lookup"><span data-stu-id="5d3df-140">ValidationStatus and InputStatus columns are displayed.</span></span> <span data-ttu-id="5d3df-141">Para obter mais informações, consulte [Validando dados &#40;Suplemento MDS para Excel&#41;](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="5d3df-141">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
-   <span data-ttu-id="5d3df-142">Confirme se os atributos foram criados como o tipo de dados esperado.</span><span class="sxs-lookup"><span data-stu-id="5d3df-142">Confirm that the attributes were created as the data type you expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d3df-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5d3df-143">See Also</span></span>  
 [<span data-ttu-id="5d3df-144">Criar um atributo baseado em domínio &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5d3df-144">Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;</span></span>](create-a-domain-based-attribute-mds-add-in-for-excel.md)  
  
  
