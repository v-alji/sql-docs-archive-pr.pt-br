---
title: Criar um atributo de data (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating date attributes [Master Data Services]
- attributes [Master Data Services], creating date attributes
ms.assetid: 22a8f1a3-b4f2-4cfa-8495-7daad5ce9d12
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 93797b90ff03c6a2b60ce8e015897a46a7448aad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568684"
---
# <a name="create-a-date-attribute-master-data-services"></a><span data-ttu-id="2ec08-102">Criar um atributo de data (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2ec08-102">Create a Date Attribute (Master Data Services)</span></span>
  <span data-ttu-id="2ec08-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie um atributo de data quando desejar que os usuários insiram uma data como um valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="2ec08-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a date attribute when you want users to enter a date as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ec08-104">O atributo é chamado DateTime, mas valores de tempo não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="2ec08-104">The attribute is called DateTime, but time values are not supported.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2ec08-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2ec08-105">Prerequisites</span></span>  
 <span data-ttu-id="2ec08-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="2ec08-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="2ec08-107">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="2ec08-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="2ec08-108">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="2ec08-108">You must be a model administrator.</span></span> <span data-ttu-id="2ec08-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2ec08-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="2ec08-110">Você deve ter uma entidade para a qual possa criar o atributo.</span><span class="sxs-lookup"><span data-stu-id="2ec08-110">You must have an entity to create the attribute for.</span></span> <span data-ttu-id="2ec08-111">Para obter mais informações, consulte [criar uma entidade &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2ec08-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-date-attribute"></a><span data-ttu-id="2ec08-112">Para criar um atributo de data</span><span class="sxs-lookup"><span data-stu-id="2ec08-112">To create a date attribute</span></span>  
  
1.  <span data-ttu-id="2ec08-113">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="2ec08-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="2ec08-114">Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="2ec08-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="2ec08-115">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="2ec08-115">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="2ec08-116">Selecione a linha correspondente à entidade para a qual você deseja criar um atributo.</span><span class="sxs-lookup"><span data-stu-id="2ec08-116">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="2ec08-117">Clique em **Editar entidade selecionada**.</span><span class="sxs-lookup"><span data-stu-id="2ec08-117">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="2ec08-118">Na página **Editar Entidade** :</span><span class="sxs-lookup"><span data-stu-id="2ec08-118">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="2ec08-119">Se o atributo for para membros folha, no painel **Atributos de membro folha** , clique em **Adicionar atributo folha**.</span><span class="sxs-lookup"><span data-stu-id="2ec08-119">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="2ec08-120">Se o atributo for para membros consolidados, no painel **Atributo de membro consolidado** , clique em **Adicionar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="2ec08-120">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="2ec08-121">Se o atributo for para coleções, no painel **Atributos da coleção** , clique em **Adicionar atributo de coleção**.</span><span class="sxs-lookup"><span data-stu-id="2ec08-121">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="2ec08-122">Na página **Adicionar Atributo** , selecione a opção **Forma livre** .</span><span class="sxs-lookup"><span data-stu-id="2ec08-122">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="2ec08-123">Na caixa **Nome** , digite um nome para o atributo.</span><span class="sxs-lookup"><span data-stu-id="2ec08-123">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="2ec08-124">Para obter uma lista de palavras que não devem ser usadas como nomes de atributos, consulte [palavras reservadas &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2ec08-124">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="2ec08-125">Na caixa **Exibir largura em pixels** , digite a largura da coluna de atributo a ser exibida na grade do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="2ec08-125">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="2ec08-126">Na lista **Tipo de dados** , selecione **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="2ec08-126">From the **Data type** list, select **DateTime**.</span></span>  
  
11. <span data-ttu-id="2ec08-127">Na lista **Máscara de entrada** , selecione um formato para datas.</span><span class="sxs-lookup"><span data-stu-id="2ec08-127">From the **Input mask** list, select a format for dates.</span></span>  
  
12. <span data-ttu-id="2ec08-128">Opcionalmente, selecione **Habilitar controle de alterações** para controlar alterações de grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="2ec08-128">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="2ec08-129">Para obter mais informações, consulte [Adicionar atributos a um grupo de controle de alterações &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2ec08-129">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="2ec08-130">Clique em **Salvar atributo**.</span><span class="sxs-lookup"><span data-stu-id="2ec08-130">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="2ec08-131">Na página **Manutenção da Entidade** , clique em **Salvar entidade**.</span><span class="sxs-lookup"><span data-stu-id="2ec08-131">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="to-display-the-time-portion-of-a-datetime-value"></a><span data-ttu-id="2ec08-132">Para exibir a porção de tempo de um valor datetime</span><span class="sxs-lookup"><span data-stu-id="2ec08-132">To display the time portion of a datetime value</span></span>  
 <span data-ttu-id="2ec08-133">Para que a interface de usuário exiba a porção de hora de um valor datetime, você deve selecionar uma máscara de entrada apropriada para o atributo.</span><span class="sxs-lookup"><span data-stu-id="2ec08-133">To have the user interface display the time portion of a datetime value, you must select an appropriate input mask for the attribute.</span></span> <span data-ttu-id="2ec08-134">Nenhuma das máscaras internas para os atributos Datetime faz isso, mas você pode adicionar uma nova máscara que permitirá que você exiba a hora.</span><span class="sxs-lookup"><span data-stu-id="2ec08-134">None of the built-in masks for Datetime attributes do this, but you can add a new mask that will allow you to display time.</span></span> <span data-ttu-id="2ec08-135">Para fazer isso, adicione uma linha na tabela mdm.tblList do banco de dados MDS, onde as máscaras internas estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="2ec08-135">To do so, add a row in the mdm.tblList table of the MDS database, where the built-in masks are stored.</span></span> <span data-ttu-id="2ec08-136">A linha deve ter os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="2ec08-136">The row should have the following values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ec08-137">ListCode</span><span class="sxs-lookup"><span data-stu-id="2ec08-137">ListCode</span></span>|<span data-ttu-id="2ec08-138">lstInputMask</span><span class="sxs-lookup"><span data-stu-id="2ec08-138">lstInputMask</span></span>|  
|<span data-ttu-id="2ec08-139">ListName</span><span class="sxs-lookup"><span data-stu-id="2ec08-139">ListName</span></span>|<span data-ttu-id="2ec08-140">Máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="2ec08-140">Input Mask</span></span>|  
|<span data-ttu-id="2ec08-141">Seq</span><span class="sxs-lookup"><span data-stu-id="2ec08-141">Seq</span></span>|<span data-ttu-id="2ec08-142">19</span><span class="sxs-lookup"><span data-stu-id="2ec08-142">19</span></span>|  
|<span data-ttu-id="2ec08-143">Opção de Lista</span><span class="sxs-lookup"><span data-stu-id="2ec08-143">List Option</span></span>|<span data-ttu-id="2ec08-144">dd/MM/aaaa hh:mm:ss tt</span><span class="sxs-lookup"><span data-stu-id="2ec08-144">dd/MM/yyyy hh:mm:ss tt</span></span>|  
|<span data-ttu-id="2ec08-145">ID de opção</span><span class="sxs-lookup"><span data-stu-id="2ec08-145">Option ID</span></span>|<span data-ttu-id="2ec08-146">19</span><span class="sxs-lookup"><span data-stu-id="2ec08-146">19</span></span>|  
|<span data-ttu-id="2ec08-147">IsVisible</span><span class="sxs-lookup"><span data-stu-id="2ec08-147">IsVisible</span></span>|<span data-ttu-id="2ec08-148">1</span><span class="sxs-lookup"><span data-stu-id="2ec08-148">1</span></span>|  
|<span data-ttu-id="2ec08-149">ID do grupo</span><span class="sxs-lookup"><span data-stu-id="2ec08-149">Group_ID</span></span>|<span data-ttu-id="2ec08-150">3</span><span class="sxs-lookup"><span data-stu-id="2ec08-150">3</span></span>|  
  
 <span data-ttu-id="2ec08-151">Depois de inserir uma linha com os valores acima na tabela mdm.tblList, a máscara "dd/MM/aaaa hh:mm:ss tt" estará disponível na caixa de listagem de máscaras de entrada.</span><span class="sxs-lookup"><span data-stu-id="2ec08-151">After you enter a row with the above values in the mdm.tblList table, the "dd/MM/yyyy hh:mm:ss tt" mask will be available in the Input mask list box.</span></span> <span data-ttu-id="2ec08-152">Você pode então selecionar essa máscara para exibir a data e a hora em uma coluna de atributo de datetime de uma entidade no MDS Explorer.</span><span class="sxs-lookup"><span data-stu-id="2ec08-152">You can then select that mask to display the date and time in a datetime attribute column of an entity in the MDS Explorer.</span></span>  
  
 <span data-ttu-id="2ec08-153">A máscara de entrada é uma cadeia de caracteres de formato DateTime .NET personalizada.</span><span class="sxs-lookup"><span data-stu-id="2ec08-153">The Input Mask is a custom .NET DateTime format string.</span></span> <span data-ttu-id="2ec08-154">Para obter mais informações, consulte [Cadeias de caracteres personalizadas de formato data e hora](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="2ec08-154">For more information, see [Custom Date and Time Format Strings](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec08-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2ec08-155">See Also</span></span>  
 <span data-ttu-id="2ec08-156">[Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2ec08-156">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="2ec08-157">[Alterar um nome de atributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2ec08-157">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="2ec08-158">[Criar um atributo baseado em domínio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2ec08-158">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="2ec08-159">Criar um atributo de arquivo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2ec08-159">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
