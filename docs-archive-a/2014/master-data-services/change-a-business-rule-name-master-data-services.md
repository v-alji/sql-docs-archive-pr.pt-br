---
title: Alterar o nome de uma regra de negócios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], changing name
ms.assetid: cffcae43-a208-443f-9f43-a0ec9e05f79c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0e99047ffe27332aaed4514394ca2357942a1297
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583710"
---
# <a name="change-a-business-rule-name-master-data-services"></a><span data-ttu-id="67e52-102">Alterar o nome de uma regra de negócio (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="67e52-102">Change a Business Rule Name (Master Data Services)</span></span>
  <span data-ttu-id="67e52-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], altere o nome de uma regra de negócio quando o nome atribuído não atender às suas necessidades comerciais.</span><span class="sxs-lookup"><span data-stu-id="67e52-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], change a business rule name when the name assigned does not meet your business needs.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="67e52-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="67e52-104">Prerequisites</span></span>  
 <span data-ttu-id="67e52-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="67e52-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="67e52-106">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="67e52-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="67e52-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="67e52-107">You must be a model administrator.</span></span> <span data-ttu-id="67e52-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="67e52-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="67e52-109">Uma regra de negócios deve existir.</span><span class="sxs-lookup"><span data-stu-id="67e52-109">A business rule must exist.</span></span> <span data-ttu-id="67e52-110">Para obter mais informações, consulte [Criar e publicar uma regra de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="67e52-110">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
### <a name="to-change-the-name-of-a-business-rule"></a><span data-ttu-id="67e52-111">Para alterar o nome de uma regra de negócios</span><span class="sxs-lookup"><span data-stu-id="67e52-111">To change the name of a business rule</span></span>  
  
1.  <span data-ttu-id="67e52-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="67e52-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="67e52-113">Na barra de menus, aponte para **Gerenciar** e clique em **Regras de Negócios**.</span><span class="sxs-lookup"><span data-stu-id="67e52-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="67e52-114">Na página **Manutenção de Regra de Negócio** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="67e52-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="67e52-115">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="67e52-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="67e52-116">Na lista **tipo de membro** , selecione um tipo de membro.</span><span class="sxs-lookup"><span data-stu-id="67e52-116">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="67e52-117">Na lista **Atributo** , selecione um atributo ou deixe o valor padrão **Todos**.</span><span class="sxs-lookup"><span data-stu-id="67e52-117">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="67e52-118">Na grade, na linha da regra de negócio, clique duas vezes no campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="67e52-118">In the grid, in the row for the business rule, double-click the **Name** field.</span></span>  
  
8.  <span data-ttu-id="67e52-119">Digite um nome para a regra de negócios.</span><span class="sxs-lookup"><span data-stu-id="67e52-119">Type a name for the business rule.</span></span>  
  
9. <span data-ttu-id="67e52-120">Pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="67e52-120">Press ENTER.</span></span>  
  
10. <span data-ttu-id="67e52-121">Clique em **Publicar regras de negócio**.</span><span class="sxs-lookup"><span data-stu-id="67e52-121">Click **Publish business rules**.</span></span>  
  
11. <span data-ttu-id="67e52-122">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="67e52-122">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="67e52-123">O status da regra mudará para **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="67e52-123">The rule's status changes to **Active**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e52-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67e52-124">See Also</span></span>  
 [<span data-ttu-id="67e52-125">Regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="67e52-125">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
