---
title: Exportando dados (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- exporting data [Master Data Services]
- subscription views [Master Data Services]
- subscription views [Master Data Services], about subscription views
ms.assetid: 8b74409a-ea70-45f8-84c7-da6905e4901a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: edae5b996c25a1b6053231ed2f69ef511b9fbfa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574080"
---
# <a name="exporting-data-master-data-services"></a><span data-ttu-id="6eb10-102">Exportando dados (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6eb10-102">Exporting Data (Master Data Services)</span></span>
  <span data-ttu-id="6eb10-103">Você pode exportar dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] para sistemas de assinatura por meio da criação de exibições de assinaturas.</span><span class="sxs-lookup"><span data-stu-id="6eb10-103">You can export [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] data to subscribing systems by creating subscriptions views.</span></span> <span data-ttu-id="6eb10-104">Qualquer sistema assinante pode exibir os dados publicados no banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6eb10-104">Any subscribing system can then view the published data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="6eb10-105">Para obter mais informações sobre modos de exibição, consulte [Modos de exibição](../relational-databases/views/views.md).</span><span class="sxs-lookup"><span data-stu-id="6eb10-105">For more information about views, see [Views](../relational-databases/views/views.md).</span></span>  
  
## <a name="subscription-view-formats"></a><span data-ttu-id="6eb10-106">Formatos de exibição da assinatura</span><span class="sxs-lookup"><span data-stu-id="6eb10-106">Subscription View Formats</span></span>  
 <span data-ttu-id="6eb10-107">Ao criar uma exibição do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], você faz escolhas em um conjunto de formatos de exibição padrão fornecido pelo [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6eb10-107">When you create a view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you choose from a set of standard view formats that [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] provides.</span></span> <span data-ttu-id="6eb10-108">Esses formatos podem ser usados para criar exibições que mostram:</span><span class="sxs-lookup"><span data-stu-id="6eb10-108">You can use these formats to create views that show:</span></span>  
  
-   <span data-ttu-id="6eb10-109">Todos os membros da folha e seus atributos.</span><span class="sxs-lookup"><span data-stu-id="6eb10-109">All leaf members and their attributes.</span></span>  
  
-   <span data-ttu-id="6eb10-110">Todos os membros da folha consolidados e seus atributos.</span><span class="sxs-lookup"><span data-stu-id="6eb10-110">All consolidated members and their attributes.</span></span>  
  
-   <span data-ttu-id="6eb10-111">Todas as coleções e seus atributos.</span><span class="sxs-lookup"><span data-stu-id="6eb10-111">All collections and their attributes.</span></span>  
  
-   <span data-ttu-id="6eb10-112">Os membros explicitamente adicionados a uma coleção.</span><span class="sxs-lookup"><span data-stu-id="6eb10-112">The members explicitly added to a collection.</span></span>  
  
-   <span data-ttu-id="6eb10-113">Os membros de uma hierarquia derivada, em formato pai-filho ou de nível.</span><span class="sxs-lookup"><span data-stu-id="6eb10-113">The members in a derived hierarchy, in either a parent child or level format.</span></span>  
  
-   <span data-ttu-id="6eb10-114">Os membros de todas as hierarquias explícitas de uma entidade, em formato pai-filho ou de nível.</span><span class="sxs-lookup"><span data-stu-id="6eb10-114">The members in all explicit hierarchies for an entity, in either a parent child or level format.</span></span>  
  
## <a name="subscription-views-can-become-out-of-date"></a><span data-ttu-id="6eb10-115">Exibições de assinatura podem se tornar desatualizadas</span><span class="sxs-lookup"><span data-stu-id="6eb10-115">Subscription Views Can Become Out-of-Date</span></span>  
 <span data-ttu-id="6eb10-116">Depois de criar uma exibição de assinatura para uma entidade ou hierarquia, as alterações nos objetos modelo associados não são refletidas automaticamente na exibição.</span><span class="sxs-lookup"><span data-stu-id="6eb10-116">After you create a subscription view for an entity or hierarchy, changes to the associated model objects are not automatically reflected in the view.</span></span> <span data-ttu-id="6eb10-117">Talvez seja necessário gerar novamente uma exibição de assinatura no [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para refletir as alterações nos objetos modelo.</span><span class="sxs-lookup"><span data-stu-id="6eb10-117">You might need to regenerate a subscription view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to reflect changes to model objects.</span></span> <span data-ttu-id="6eb10-118">A coluna **Alterado** na página **Exportação** é atualizada para **True** quando objetos do modelo forem alterados.</span><span class="sxs-lookup"><span data-stu-id="6eb10-118">The **Changed** column on the **Export** page is updated to **True** when model objects change.</span></span> <span data-ttu-id="6eb10-119">**True** indica que você deve editar e salvar a exibição de assinatura, o que gera novamente a exibição.</span><span class="sxs-lookup"><span data-stu-id="6eb10-119">**True** indicates that you should edit the subscription view and save it, which regenerates the view.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6eb10-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6eb10-120">Related Tasks</span></span>  
  
|<span data-ttu-id="6eb10-121">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="6eb10-121">Task Description</span></span>|<span data-ttu-id="6eb10-122">Tópico</span><span class="sxs-lookup"><span data-stu-id="6eb10-122">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="6eb10-123">Criar uma exibição de assinatura de seus dados mestre.</span><span class="sxs-lookup"><span data-stu-id="6eb10-123">Create a subscription view of your master data.</span></span>|[<span data-ttu-id="6eb10-124">Criar uma exibição de assinatura &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6eb10-124">Create a Subscription View &#40;Master Data Services&#41;</span></span>](create-a-subscription-view-to-export-data-master-data-services.md)|  
|<span data-ttu-id="6eb10-125">Excluir uma exibição de assinatura existente.</span><span class="sxs-lookup"><span data-stu-id="6eb10-125">Delete an existing subscription view.</span></span>|[<span data-ttu-id="6eb10-126">Excluir uma exibição de assinatura &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6eb10-126">Delete a Subscription View &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-subscription-view-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="6eb10-127">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="6eb10-127">Related Content</span></span>  
  
-   [<span data-ttu-id="6eb10-128">Formatos de exibição de assinatura &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6eb10-128">Subscription View Formats &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/subscription-view-formats-master-data-services.md)  
  
-   [<span data-ttu-id="6eb10-129">Exibições</span><span class="sxs-lookup"><span data-stu-id="6eb10-129">Views</span></span>](../relational-databases/views/views.md)  
  
  
