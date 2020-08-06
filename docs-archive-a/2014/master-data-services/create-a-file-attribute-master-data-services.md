---
title: Criar um atributo de arquivo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating file attributes [Master Data Services]
- attributes [Master Data Services], creating file attributes
ms.assetid: d224886b-2ef1-4658-8b01-2213cc4b8df6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f4f6e2f10a830d089d1d217f7cf54d0b8557add9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570736"
---
# <a name="create-a-file-attribute-master-data-services"></a><span data-ttu-id="35d9e-102">Criar um atributo de arquivo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="35d9e-102">Create a File Attribute (Master Data Services)</span></span>
  <span data-ttu-id="35d9e-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie um atributo de arquivo para popular os valores de atributo com arquivos.</span><span class="sxs-lookup"><span data-stu-id="35d9e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a file attribute to populate attribute values with files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="35d9e-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="35d9e-104">Prerequisites</span></span>  
 <span data-ttu-id="35d9e-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="35d9e-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="35d9e-106">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="35d9e-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="35d9e-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="35d9e-107">You must be a model administrator.</span></span> <span data-ttu-id="35d9e-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="35d9e-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="35d9e-109">Uma entidade deve existir para que se possa criar o atributo para ela.</span><span class="sxs-lookup"><span data-stu-id="35d9e-109">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="35d9e-110">Para obter mais informações, consulte [criar uma entidade &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="35d9e-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-file-attribute"></a><span data-ttu-id="35d9e-111">Para criar um atributo de arquivo</span><span class="sxs-lookup"><span data-stu-id="35d9e-111">To create a file attribute</span></span>  
  
1.  <span data-ttu-id="35d9e-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="35d9e-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="35d9e-113">Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="35d9e-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="35d9e-114">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="35d9e-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="35d9e-115">Selecione a linha correspondente à entidade para a qual você deseja criar um atributo.</span><span class="sxs-lookup"><span data-stu-id="35d9e-115">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="35d9e-116">Clique em **Editar entidade selecionada**.</span><span class="sxs-lookup"><span data-stu-id="35d9e-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="35d9e-117">Na página **Editar Entidade** :</span><span class="sxs-lookup"><span data-stu-id="35d9e-117">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="35d9e-118">Se o atributo for para membros folha, no painel **Atributos de membro folha** , clique em **Adicionar atributo folha**.</span><span class="sxs-lookup"><span data-stu-id="35d9e-118">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="35d9e-119">Se o atributo for para membros consolidados, no painel **Atributo de membro consolidado** , clique em **Adicionar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="35d9e-119">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="35d9e-120">Se o atributo for para coleções, no painel **Atributos da coleção** , clique em **Adicionar atributo de coleção**.</span><span class="sxs-lookup"><span data-stu-id="35d9e-120">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="35d9e-121">Na página **Adicionar atributo** , selecione a opção **arquivo** .</span><span class="sxs-lookup"><span data-stu-id="35d9e-121">On the **Add Attribute** page, select the **File** option.</span></span>  
  
8.  <span data-ttu-id="35d9e-122">Na caixa **Nome** , digite um nome para o atributo.</span><span class="sxs-lookup"><span data-stu-id="35d9e-122">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="35d9e-123">Para obter uma lista de palavras que não devem ser usadas como nomes de atributos, consulte [palavras reservadas &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="35d9e-123">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="35d9e-124">Na caixa **Exibir largura em pixels** , digite a largura da coluna de atributo a ser exibida na grade do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="35d9e-124">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="35d9e-125">Na lista **extensão de arquivo** , selecione um ou mais tipos de arquivo que um usuário pode carregar ou deixe o padrão (\*. \* ) para permitir todos os tipos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="35d9e-125">From the **File extension** list, select one or more file types that a user can upload, or leave the default (\*.\*) to allow all file types.</span></span>  
  
11. <span data-ttu-id="35d9e-126">Opcionalmente, selecione **Habilitar controle de alterações** para controlar alterações de grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="35d9e-126">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="35d9e-127">Para obter mais informações, consulte [Adicionar atributos a um grupo de controle de alterações &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="35d9e-127">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
12. <span data-ttu-id="35d9e-128">Clique em **Salvar atributo**.</span><span class="sxs-lookup"><span data-stu-id="35d9e-128">Click **Save attribute**.</span></span>  
  
13. <span data-ttu-id="35d9e-129">Na página **Manutenção da Entidade** , clique em **Salvar entidade**.</span><span class="sxs-lookup"><span data-stu-id="35d9e-129">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d9e-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="35d9e-130">See Also</span></span>  
 <span data-ttu-id="35d9e-131">[Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="35d9e-131">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="35d9e-132">[Alterar um nome de atributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="35d9e-132">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="35d9e-133">[Criar um atributo baseado em domínio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="35d9e-133">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="35d9e-134">Criar um atributo de texto &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="35d9e-134">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)  
  
  
