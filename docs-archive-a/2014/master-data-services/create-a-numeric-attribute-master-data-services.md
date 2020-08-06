---
title: Criar um atributo numérico (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating number attributes
- creating number attributes [Master Data Services]
ms.assetid: c0dbb6d8-ba78-485a-a40d-6d5cb7e75d0a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bb9302c0b585c21410a6a764dc2e6dac845c6299
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568681"
---
# <a name="create-a-numeric-attribute-master-data-services"></a><span data-ttu-id="e98c2-102">Criar um atributo numérico (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e98c2-102">Create a Numeric Attribute (Master Data Services)</span></span>
  <span data-ttu-id="e98c2-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie um atributo numérico quando desejar que os usuários insiram um número como valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="e98c2-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a numeric attribute when you want users to enter a number as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e98c2-104">Os atributos numéricos têm limitações.</span><span class="sxs-lookup"><span data-stu-id="e98c2-104">Numeric attributes have limitations.</span></span> <span data-ttu-id="e98c2-105">Para obter mais informações, consulte [Atributos &#40;Master Data Services&#41;](attributes-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e98c2-105">For more information, see [Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e98c2-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e98c2-106">Prerequisites</span></span>  
 <span data-ttu-id="e98c2-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="e98c2-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="e98c2-108">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="e98c2-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="e98c2-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="e98c2-109">You must be a model administrator.</span></span> <span data-ttu-id="e98c2-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e98c2-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="e98c2-111">Uma entidade deve existir para que se possa criar o atributo para ela.</span><span class="sxs-lookup"><span data-stu-id="e98c2-111">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="e98c2-112">Para obter mais informações, consulte [criar uma entidade &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e98c2-112">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-numeric-attribute"></a><span data-ttu-id="e98c2-113">Para criar um atributo numérico</span><span class="sxs-lookup"><span data-stu-id="e98c2-113">To create a numeric attribute</span></span>  
  
1.  <span data-ttu-id="e98c2-114">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="e98c2-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="e98c2-115">Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="e98c2-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="e98c2-116">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="e98c2-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="e98c2-117">Selecione a linha correspondente à entidade para a qual você deseja criar um atributo.</span><span class="sxs-lookup"><span data-stu-id="e98c2-117">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="e98c2-118">Clique em **Editar entidade selecionada**.</span><span class="sxs-lookup"><span data-stu-id="e98c2-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="e98c2-119">Na página **Editar Entidade** :</span><span class="sxs-lookup"><span data-stu-id="e98c2-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="e98c2-120">Se o atributo for para membros folha, no painel **Atributos de membro folha** , clique em **Adicionar atributo folha**.</span><span class="sxs-lookup"><span data-stu-id="e98c2-120">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="e98c2-121">Se o atributo for para membros consolidados, no painel **Atributo de membro consolidado** , clique em **Adicionar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="e98c2-121">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="e98c2-122">Se o atributo for para coleções, no painel **Atributos da coleção** , clique em **Adicionar atributo de coleção**.</span><span class="sxs-lookup"><span data-stu-id="e98c2-122">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="e98c2-123">Na página **Adicionar Atributo** , selecione a opção **Forma livre** .</span><span class="sxs-lookup"><span data-stu-id="e98c2-123">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="e98c2-124">Na caixa **Nome** , digite um nome para o atributo.</span><span class="sxs-lookup"><span data-stu-id="e98c2-124">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="e98c2-125">Para obter uma lista de palavras que não devem ser usadas como nomes de atributos, consulte [palavras reservadas &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e98c2-125">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="e98c2-126">Na caixa **Exibir largura em pixels** , digite a largura da coluna de atributo a ser exibida na grade do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="e98c2-126">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="e98c2-127">Na lista **Tipo de dados** , selecione **Número**.</span><span class="sxs-lookup"><span data-stu-id="e98c2-127">From the **Data type** list, select **Number**.</span></span>  
  
11. <span data-ttu-id="e98c2-128">Na caixa **Decimais** , digite a quantidade de números que podem ser inseridos depois de um decimal.</span><span class="sxs-lookup"><span data-stu-id="e98c2-128">In the **Decimals** box, type the number of numbers that can be entered after a decimal.</span></span>  
  
12. <span data-ttu-id="e98c2-129">Na lista **máscara de entrada** , selecione um formato para números negativos.</span><span class="sxs-lookup"><span data-stu-id="e98c2-129">From the **Input mask** list, select a format for negative numbers.</span></span>  
  
13. <span data-ttu-id="e98c2-130">Opcionalmente, selecione **Habilitar controle de alterações** para controlar alterações de grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="e98c2-130">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="e98c2-131">Consulte [Adicionar atributos a um grupo de controle de alterações &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e98c2-131">See [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) for more information.</span></span>  
  
14. <span data-ttu-id="e98c2-132">Clique em **Salvar atributo**.</span><span class="sxs-lookup"><span data-stu-id="e98c2-132">Click **Save attribute**.</span></span>  
  
15. <span data-ttu-id="e98c2-133">Na página **Manutenção da Entidade** , clique em **Salvar entidade**.</span><span class="sxs-lookup"><span data-stu-id="e98c2-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e98c2-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e98c2-134">See Also</span></span>  
 <span data-ttu-id="e98c2-135">[Atributos &#40;Master Data Services&#41;](attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e98c2-135">[Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="e98c2-136">[Alterar um nome de atributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e98c2-136">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="e98c2-137">[Criar um atributo baseado em domínio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e98c2-137">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="e98c2-138">Criar um atributo de arquivo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e98c2-138">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
