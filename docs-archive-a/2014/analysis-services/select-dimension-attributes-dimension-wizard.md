---
title: Selecionar atributos de dimensão (Assistente para dimensões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionattributes.f1
ms.assetid: f58a3e14-ab27-44d3-8c26-f5c9ee7583b0
author: minewiskan
ms.author: owend
ms.openlocfilehash: a4961092517ce1d38cfd4086ec083a939242652d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571645"
---
# <a name="select-dimension-attributes-dimension-wizard"></a><span data-ttu-id="70f7f-102">Selecionar atributos de dimensão (Assistente para Dimensões)</span><span class="sxs-lookup"><span data-stu-id="70f7f-102">Select Dimension Attributes (Dimension Wizard)</span></span>
  <span data-ttu-id="70f7f-103">Use a página **Selecionar Atributos de Dimensão** para selecionar e modificar os atributos para a dimensão a ser criada.</span><span class="sxs-lookup"><span data-stu-id="70f7f-103">Use the **Select Dimension Attributes** page to select and modify the attributes for the dimension to be created.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70f7f-104">Se você não consegue ler os valores de alguma coluna, maximize a janela do assistente e altere a largura de cada cabeçalho de coluna até que consiga ler os valores.</span><span class="sxs-lookup"><span data-stu-id="70f7f-104">If you cannot read the values for any column, maximize the wizard window and change the width of each column heading until you can read the values.</span></span>  
  
 <span data-ttu-id="70f7f-105">**Para abrir o Assistente para Dimensões**</span><span class="sxs-lookup"><span data-stu-id="70f7f-105">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="70f7f-106">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], no **Gerenciador de Soluções**, clique com o botão direito do mouse na pasta **Dimensões** de um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e clique em **Nova Dimensão**.</span><span class="sxs-lookup"><span data-stu-id="70f7f-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="70f7f-107">Opções</span><span class="sxs-lookup"><span data-stu-id="70f7f-107">Options</span></span>  
 <span data-ttu-id="70f7f-108">(Coluna com caixas de seleção)</span><span class="sxs-lookup"><span data-stu-id="70f7f-108">(Column with check boxes)</span></span>  
 <span data-ttu-id="70f7f-109">Selecione para incluir um atributo na dimensão.</span><span class="sxs-lookup"><span data-stu-id="70f7f-109">Select to include an attribute in the dimension.</span></span>  
  
 <span data-ttu-id="70f7f-110">Para incluir um atributo específico, marque a caixa de seleção para esse atributo.</span><span class="sxs-lookup"><span data-stu-id="70f7f-110">To include a specific attribute, select the check box for that attribute.</span></span>  
  
 <span data-ttu-id="70f7f-111">Para incluir todos os atributos, marque a caixa de seleção no cabeçalho de coluna.</span><span class="sxs-lookup"><span data-stu-id="70f7f-111">To include all attributes, select the check box in the column header.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70f7f-112">A caixa de seleção para o atributo de chave não pode ser desmarcada.</span><span class="sxs-lookup"><span data-stu-id="70f7f-112">The check box for the key attribute cannot be cleared.</span></span>  
  
 <span data-ttu-id="70f7f-113">**Nome do atributo**</span><span class="sxs-lookup"><span data-stu-id="70f7f-113">**Attribute Name**</span></span>  
 <span data-ttu-id="70f7f-114">Lista os atributos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="70f7f-114">Lists the available attributes.</span></span>  
  
 <span data-ttu-id="70f7f-115">Para alterar o nome de um atributo, clique no nome do atributo e digite um nome novo para o atributo.</span><span class="sxs-lookup"><span data-stu-id="70f7f-115">To change the name of an attribute, click the attribute name and type a new name for the attribute.</span></span>  
  
 <span data-ttu-id="70f7f-116">**Habilitar Navegação**</span><span class="sxs-lookup"><span data-stu-id="70f7f-116">**Enable Browsing**</span></span>  
 <span data-ttu-id="70f7f-117">Selecione para tornar o atributo disponível ao usuário final para navegação e filtragem.</span><span class="sxs-lookup"><span data-stu-id="70f7f-117">Select to make the attribute available to the end user for browsing and filtering.</span></span> <span data-ttu-id="70f7f-118">**Habilitar Navegação** deve ser selecionado para o atributo de chave.</span><span class="sxs-lookup"><span data-stu-id="70f7f-118">**Enable Browsing** must be selected for the key attribute.</span></span> <span data-ttu-id="70f7f-119">Para atributos não chave, o padrão é que **Habilitar Navegação** não esteja selecionado, o que faz com que os atributos não chave só sejam mostrados como propriedades do membro.</span><span class="sxs-lookup"><span data-stu-id="70f7f-119">For non-key attributes, the default is not to have **Enable Browsing** selected, which causes the non-key attributes to be shown only as member properties.</span></span>  
  
 <span data-ttu-id="70f7f-120">Na maioria dos casos, o atributo se torna disponível ou não disponível para navegação definindo-se a propriedade `AttributeHierarchyEnabled` como `True` ou `False`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="70f7f-120">In most cases, the attribute is made available or not available for browsing by setting the `AttributeHierarchyEnabled` property to `True` or `False`, respectively.</span></span> <span data-ttu-id="70f7f-121">No entanto, nas três caixas a seguir, o assistente usa configurações diferentes.</span><span class="sxs-lookup"><span data-stu-id="70f7f-121">However, in the following three cases, the wizard uses different settings.</span></span>  
  
|<span data-ttu-id="70f7f-122">Caixa</span><span class="sxs-lookup"><span data-stu-id="70f7f-122">Case</span></span>|<span data-ttu-id="70f7f-123">Configurações</span><span class="sxs-lookup"><span data-stu-id="70f7f-123">Settings</span></span>|  
|----------|--------------|  
|<span data-ttu-id="70f7f-124">Uma dimensão contém uma hierarquia pai-filho e **Habilitar Navegação** não é selecionado</span><span class="sxs-lookup"><span data-stu-id="70f7f-124">A dimension contains a parent-child hierarchy and **Enable Browsing** is not selected</span></span>|<span data-ttu-id="70f7f-125">O assistente deixa a propriedade `AttributeHierarchyEnabled` definida como `True` e define o atributo `AttributeHierarchyVisible` como `False` para o atributo de chave.</span><span class="sxs-lookup"><span data-stu-id="70f7f-125">The wizard leaves the `AttributeHierarchyEnabled` property set to `True`, and sets the `AttributeHierarchyVisible` attribute to `False` for the key attribute.</span></span>|  
|<span data-ttu-id="70f7f-126">Uma tabela em uma dimensão contém uma chave estrangeira para uma tabela que não está na dimensão</span><span class="sxs-lookup"><span data-stu-id="70f7f-126">A table in a dimension contains a foreign key to a table that is not in the dimension</span></span>|<span data-ttu-id="70f7f-127">O assistente seleciona a chave estrangeira como um atributo a ser incluído, mas não selecionará **Habilitar Navegação**.</span><span class="sxs-lookup"><span data-stu-id="70f7f-127">The wizard selects the foreign key as an attribute to be included, but will not select **Enable Browsing**.</span></span> <span data-ttu-id="70f7f-128">Se você mantiver estas configurações, a propriedade `AttributeHiearchyEnabled` do atributo será definida como `True` e a propriedade `AttributeHierarchyVisible` será definida como `False`.</span><span class="sxs-lookup"><span data-stu-id="70f7f-128">If you keep these settings, the `AttributeHiearchyEnabled` property of the attribute will be set to `True`, and the `AttributeHierarchyVisible` property will be set to `False`.</span></span>|  
|<span data-ttu-id="70f7f-129">Uma dimensão contém tabelas floco de neve que são alcançadas por meio de colunas de chave estrangeira anuláveis</span><span class="sxs-lookup"><span data-stu-id="70f7f-129">A dimension contains snowflake tables that are reached through nullable foreign key columns</span></span><br /><br /> <span data-ttu-id="70f7f-130">-e-</span><span class="sxs-lookup"><span data-stu-id="70f7f-130">-and-</span></span><br /><br /> <span data-ttu-id="70f7f-131">Habilitar Navegação não está selecionado para o atributo que está baseado na chave da tabela floco de neve</span><span class="sxs-lookup"><span data-stu-id="70f7f-131">Enable Browsing for the attribute that is based on the key of the snowflake table is not selected</span></span>|<span data-ttu-id="70f7f-132">O assistente criará o novo atributo que tem a propriedade `AttributeHiearchyEnabled` definida como `True` e a propriedade `AttributeHierarchyVisible` definida como `False`.</span><span class="sxs-lookup"><span data-stu-id="70f7f-132">The wizard will create the new attribute that has the `AttributeHiearchyEnabled` property set to `True`, and the `AttributeHierarchyVisible` property set to `False`.</span></span>|  
  
 <span data-ttu-id="70f7f-133">**Tipo de Atributo**</span><span class="sxs-lookup"><span data-stu-id="70f7f-133">**Attribute Type**</span></span>  
 <span data-ttu-id="70f7f-134">(Opcional) Defina o tipo para o atributo.</span><span class="sxs-lookup"><span data-stu-id="70f7f-134">(Optional) Set the type for the attribute.</span></span> <span data-ttu-id="70f7f-135">O valor padrão é **Regular**.</span><span class="sxs-lookup"><span data-stu-id="70f7f-135">The default value is **Regular**.</span></span> <span data-ttu-id="70f7f-136">O tipo de atributo fornece orientação a aplicativos clientes quanto a quais informações o atributo poderia conter.</span><span class="sxs-lookup"><span data-stu-id="70f7f-136">The attribute type provides guidance to client applications on what information the attribute might contain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f7f-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="70f7f-137">See Also</span></span>  
 <span data-ttu-id="70f7f-138">[Ajuda F1 do assistente para dimensões](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="70f7f-138">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="70f7f-139">[Dimensões &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="70f7f-139">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="70f7f-140">Dimensões em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="70f7f-140">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
