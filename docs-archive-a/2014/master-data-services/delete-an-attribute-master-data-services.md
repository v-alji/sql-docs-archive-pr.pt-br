---
title: Excluir um atributo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], deleting
- deleting attributes [Master Data Services]
ms.assetid: ec3e66f7-0e35-43d7-a80d-64899948ebfe
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 96db56dac9356b1131e722fc7f6b779c93305bb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678825"
---
# <a name="delete-an-attribute-master-data-services"></a><span data-ttu-id="cff39-102">Excluir um atributo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="cff39-102">Delete an Attribute (Master Data Services)</span></span>
  <span data-ttu-id="cff39-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclua um atributo quando você quiser excluir permanentemente esse atributo e todos os valores associados a ele.</span><span class="sxs-lookup"><span data-stu-id="cff39-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute when you want to permanently delete the attribute and all associated attribute values.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cff39-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="cff39-104">Prerequisites</span></span>  
 <span data-ttu-id="cff39-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="cff39-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="cff39-106">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="cff39-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="cff39-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="cff39-107">You must be a model administrator.</span></span> <span data-ttu-id="cff39-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cff39-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute"></a><span data-ttu-id="cff39-109">Para excluir um atributo</span><span class="sxs-lookup"><span data-stu-id="cff39-109">To delete an attribute</span></span>  
  
1.  <span data-ttu-id="cff39-110">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="cff39-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="cff39-111">Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="cff39-111">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="cff39-112">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="cff39-112">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="cff39-113">Selecione a linha da entidade que contém o atributo que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="cff39-113">Select the row for the entity that contains the attribute you want to delete.</span></span>  
  
5.  <span data-ttu-id="cff39-114">Clique em **Editar entidade selecionada**.</span><span class="sxs-lookup"><span data-stu-id="cff39-114">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="cff39-115">Na página **Editar entidade** , clique no atributo que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="cff39-115">On the **Edit Entity** page, click the attribute you want to delete.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cff39-116">Não é possível excluir os atributos Name e Code.</span><span class="sxs-lookup"><span data-stu-id="cff39-116">You cannot delete the Name or Code attributes.</span></span>  
  
7.  <span data-ttu-id="cff39-117">Clique em **excluir atributo selecionado**.</span><span class="sxs-lookup"><span data-stu-id="cff39-117">Click **Delete selected attribute**.</span></span>  
  
8.  <span data-ttu-id="cff39-118">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cff39-118">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="cff39-119">Na caixa de diálogo de confirmação adicional, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cff39-119">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff39-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cff39-120">See Also</span></span>  
 <span data-ttu-id="cff39-121">[Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="cff39-121">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="cff39-122">[Atributos baseados em domínio &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="cff39-122">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="cff39-123">[Criar um atributo de texto &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="cff39-123">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="cff39-124">Criar um atributo baseado em domínio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="cff39-124">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
