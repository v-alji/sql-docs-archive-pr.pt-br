---
title: Criar um atributo de texto (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating text attributes
- creating text attributes [Master Data Services]
ms.assetid: cd8b57de-364d-42a3-9273-c1c6b992bb40
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c0f44e0e6c6e3df49b6a3746648ee46a23a7a3ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584184"
---
# <a name="create-a-text-attribute-master-data-services"></a><span data-ttu-id="27cde-102">Criar um atributo de texto (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="27cde-102">Create a Text Attribute (Master Data Services)</span></span>
  <span data-ttu-id="27cde-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie um atributo de texto quando desejar que os usuários insiram uma cadeia de caracteres de texto como um valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="27cde-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a text attribute when you want users to enter a text string as an attribute value.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="27cde-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="27cde-104">Prerequisites</span></span>  
 <span data-ttu-id="27cde-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="27cde-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="27cde-106">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="27cde-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="27cde-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="27cde-107">You must be a model administrator.</span></span> <span data-ttu-id="27cde-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="27cde-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="27cde-109">Uma entidade deve existir para que se possa criar o atributo para ela.</span><span class="sxs-lookup"><span data-stu-id="27cde-109">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="27cde-110">Para obter mais informações, consulte [criar uma entidade &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="27cde-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-text-attribute"></a><span data-ttu-id="27cde-111">Para criar um atributo de texto</span><span class="sxs-lookup"><span data-stu-id="27cde-111">To create a text attribute</span></span>  
  
1.  <span data-ttu-id="27cde-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="27cde-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="27cde-113">Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="27cde-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="27cde-114">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="27cde-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="27cde-115">Selecione a linha correspondente à entidade para a qual você deseja criar um atributo.</span><span class="sxs-lookup"><span data-stu-id="27cde-115">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="27cde-116">Clique em **Editar entidade selecionada**.</span><span class="sxs-lookup"><span data-stu-id="27cde-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="27cde-117">Na página **Editar Entidade** :</span><span class="sxs-lookup"><span data-stu-id="27cde-117">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="27cde-118">Se o atributo for para membros folha, no painel **Atributos de membro folha** , clique em **Adicionar atributo folha**.</span><span class="sxs-lookup"><span data-stu-id="27cde-118">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="27cde-119">Se o atributo for para membros consolidados, no painel **Atributo de membro consolidado** , clique em **Adicionar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="27cde-119">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="27cde-120">Se o atributo for para coleções, no painel **Atributos da coleção** , clique em **Adicionar atributo de coleção**.</span><span class="sxs-lookup"><span data-stu-id="27cde-120">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="27cde-121">Na página **Adicionar Atributo** , selecione a opção **Forma livre** .</span><span class="sxs-lookup"><span data-stu-id="27cde-121">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="27cde-122">Na caixa **Nome** , digite um nome para o atributo.</span><span class="sxs-lookup"><span data-stu-id="27cde-122">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="27cde-123">Para obter uma lista de palavras que não devem ser usadas como nomes de atributos, consulte [palavras reservadas &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="27cde-123">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="27cde-124">Na caixa **Exibir largura em pixels** , digite a largura da coluna de atributo a ser exibida na grade do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="27cde-124">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="27cde-125">Na lista **Tipo de dados** , selecione **Texto**.</span><span class="sxs-lookup"><span data-stu-id="27cde-125">From the **Data type** list, select **Text**.</span></span>  
  
11. <span data-ttu-id="27cde-126">Na caixa **Tamanho** , digite o número máximo de caracteres permitidos.</span><span class="sxs-lookup"><span data-stu-id="27cde-126">In the **Length** box, type the maximum number of characters allowed.</span></span>  
  
12. <span data-ttu-id="27cde-127">Opcionalmente, selecione **Habilitar controle de alterações** para controlar alterações de grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="27cde-127">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="27cde-128">Para obter mais informações, consulte [Adicionar atributos a um grupo de controle de alterações &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="27cde-128">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="27cde-129">Clique em **Salvar atributo**.</span><span class="sxs-lookup"><span data-stu-id="27cde-129">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="27cde-130">Na página **Manutenção da Entidade** , clique em **Salvar entidade**.</span><span class="sxs-lookup"><span data-stu-id="27cde-130">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27cde-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="27cde-131">See Also</span></span>  
 <span data-ttu-id="27cde-132">[Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="27cde-132">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="27cde-133">[Alterar um nome de atributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="27cde-133">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="27cde-134">[Criar um atributo baseado em domínio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="27cde-134">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="27cde-135">Criar um atributo de arquivo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="27cde-135">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
