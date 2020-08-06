---
title: Excluir uma regra de negócios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting business rules [Master Data Services]
- business rules [Master Data Services], deleting
ms.assetid: b97aa4f9-569f-451d-ad62-65b81f980299
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8e6db486f71634cf025c57eabbedeeb9efdbc437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678823"
---
# <a name="delete-a-business-rule-master-data-services"></a><span data-ttu-id="50efb-102">Excluir uma regra de negócio (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="50efb-102">Delete a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="50efb-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclua uma regra de negócio quando ela não for mais necessária.</span><span class="sxs-lookup"><span data-stu-id="50efb-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a business rule when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50efb-104">Você pode evitar a validação de dados em relação a uma regra de negócio excluindo-a.</span><span class="sxs-lookup"><span data-stu-id="50efb-104">You can prevent data from being validated against a business rule by excluding it, rather than deleting it.</span></span> <span data-ttu-id="50efb-105">Para obter mais informações, consulte [Excluir uma regra de negócio &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="50efb-105">For more information, see [Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="50efb-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="50efb-106">Prerequisites</span></span>  
 <span data-ttu-id="50efb-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="50efb-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="50efb-108">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="50efb-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="50efb-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="50efb-109">You must be a model administrator.</span></span> <span data-ttu-id="50efb-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="50efb-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-business-rule"></a><span data-ttu-id="50efb-111">Para excluir uma regra de negócio</span><span class="sxs-lookup"><span data-stu-id="50efb-111">To delete a business rule</span></span>  
  
1.  <span data-ttu-id="50efb-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="50efb-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="50efb-113">Na barra de menus, aponte para **Gerenciar** e clique em **Regras de Negócios**.</span><span class="sxs-lookup"><span data-stu-id="50efb-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="50efb-114">Na página **Manutenção de Regra de Negócio** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="50efb-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="50efb-115">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="50efb-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="50efb-116">Na lista **Tipo de Membro** , selecione um tipo de membro ao qual a regra de negócio será aplicada.</span><span class="sxs-lookup"><span data-stu-id="50efb-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="50efb-117">Na lista **Atributo** , selecione um atributo ou deixe o valor padrão **Todos**.</span><span class="sxs-lookup"><span data-stu-id="50efb-117">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="50efb-118">Na grade, clique na linha da regra de negócios que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="50efb-118">In the grid, click the row for the business rule you want to delete.</span></span>  
  
8.  <span data-ttu-id="50efb-119">Clique em **excluir regra de negócio selecionada**.</span><span class="sxs-lookup"><span data-stu-id="50efb-119">Click **Delete selected business rule**.</span></span>  
  
9. <span data-ttu-id="50efb-120">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="50efb-120">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="50efb-121">O valor na coluna **status** é **exclusão pendente**.</span><span class="sxs-lookup"><span data-stu-id="50efb-121">The value in the **Status** column is **Deletion pending**.</span></span>  
  
10. <span data-ttu-id="50efb-122">Clique em **Publicar regras de negócio**.</span><span class="sxs-lookup"><span data-stu-id="50efb-122">Click **Publish business rules**.</span></span>  
  
11. <span data-ttu-id="50efb-123">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="50efb-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50efb-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="50efb-124">See Also</span></span>  
 <span data-ttu-id="50efb-125">[Excluir uma regra de negócio &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="50efb-125">[Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="50efb-126">[Criar e publicar uma regra de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="50efb-126">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="50efb-127">Regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="50efb-127">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
