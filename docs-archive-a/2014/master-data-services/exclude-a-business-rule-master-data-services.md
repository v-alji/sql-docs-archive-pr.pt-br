---
title: Excluir uma regra de negócios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], excluding
ms.assetid: bdbc9df0-23f7-40b9-8aba-4445c1482580
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 317964dcbc7b2cbe212c415b3aa4f9f1a0743301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680535"
---
# <a name="exclude-a-business-rule-master-data-services"></a><span data-ttu-id="e31c5-102">Apagar uma regra de negócio (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e31c5-102">Exclude a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="e31c5-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclua uma regra de negócio quando não desejar removê-la permanentemente, nem validar dados em relação a ela.</span><span class="sxs-lookup"><span data-stu-id="e31c5-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclude a business rule when you do not want to delete the rule permanently, but you do not want to validate data against it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e31c5-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e31c5-104">Prerequisites</span></span>  
 <span data-ttu-id="e31c5-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="e31c5-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="e31c5-106">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="e31c5-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="e31c5-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="e31c5-107">You must be a model administrator.</span></span> <span data-ttu-id="e31c5-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e31c5-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-exclude-a-business-rule"></a><span data-ttu-id="e31c5-109">Para excluir uma regra de negócios</span><span class="sxs-lookup"><span data-stu-id="e31c5-109">To exclude a business rule</span></span>  
  
1.  <span data-ttu-id="e31c5-110">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="e31c5-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="e31c5-111">Na barra de menus, aponte para **Gerenciar** e clique em **Regras de Negócios**.</span><span class="sxs-lookup"><span data-stu-id="e31c5-111">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="e31c5-112">Na página **Manutenção de Regra de Negócio** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="e31c5-112">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="e31c5-113">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="e31c5-113">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="e31c5-114">Na lista **tipo de membro** , selecione um tipo de membro.</span><span class="sxs-lookup"><span data-stu-id="e31c5-114">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="e31c5-115">Na lista **Atributo** , selecione um atributo ou deixe o valor padrão **Todos**.</span><span class="sxs-lookup"><span data-stu-id="e31c5-115">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="e31c5-116">Na grade, na linha da regra de negócio, marque a caixa de seleção na coluna **excluir** .</span><span class="sxs-lookup"><span data-stu-id="e31c5-116">In the grid, in the row for the business rule, select the check box in the **Exclude** column.</span></span> <span data-ttu-id="e31c5-117">O valor na coluna **status** é **exclusão pendente**.</span><span class="sxs-lookup"><span data-stu-id="e31c5-117">The value in the **Status** column is **Exclusion pending**.</span></span>  
  
8.  <span data-ttu-id="e31c5-118">Clique em **Publicar regras de negócio**.</span><span class="sxs-lookup"><span data-stu-id="e31c5-118">Click **Publish business rules**.</span></span>  
  
9. <span data-ttu-id="e31c5-119">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e31c5-119">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="e31c5-120">O valor na coluna **status** é **excluído**.</span><span class="sxs-lookup"><span data-stu-id="e31c5-120">The value in the **Status** column is **Excluded**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e31c5-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e31c5-121">See Also</span></span>  
 <span data-ttu-id="e31c5-122">[Excluir uma regra de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e31c5-122">[Delete a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="e31c5-123">[Criar e publicar uma regra de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e31c5-123">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="e31c5-124">Regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e31c5-124">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
