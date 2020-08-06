---
title: Controle de alterações (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server]
ms.assetid: 5e879c65-0d38-454f-9a20-62a6e72c89f7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2d3b69057b02884f41a43aa9a009ab3db937ed25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680980"
---
# <a name="change-tracking-master-data-services"></a><span data-ttu-id="20ca9-102">Controle de alterações (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="20ca9-102">Change Tracking (Master Data Services)</span></span>
  <span data-ttu-id="20ca9-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], você pode usar grupos de controle de alterações para executar uma ação quando um valor de atributo muda.</span><span class="sxs-lookup"><span data-stu-id="20ca9-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can use change tracking groups to take action when an attribute value changes.</span></span> <span data-ttu-id="20ca9-104">Use o controle de alterações quando você não souber qual será o novo valor, mas desejar saber se houve alterações.</span><span class="sxs-lookup"><span data-stu-id="20ca9-104">Use change tracking when you don't know what the new value will be, but instead want to know if any change occurred.</span></span>  
  
## <a name="configuring-change-tracking"></a><span data-ttu-id="20ca9-105">Configurando o controle de alterações</span><span class="sxs-lookup"><span data-stu-id="20ca9-105">Configuring Change Tracking</span></span>  
 <span data-ttu-id="20ca9-106">Para configurar o controle de alterações, você adiciona um atributo a um grupo de controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="20ca9-106">To configure change tracking, you add an attribute to a change tracking group.</span></span> <span data-ttu-id="20ca9-107">O grupo pode conter um ou muitos atributos.</span><span class="sxs-lookup"><span data-stu-id="20ca9-107">The group can contain one or many attributes.</span></span> <span data-ttu-id="20ca9-108">Depois, você cria uma regra de negócios para definir a ação que é executada quando há mudanças em quaisquer dos atributos no grupo.</span><span class="sxs-lookup"><span data-stu-id="20ca9-108">Then, you create a business rule to define the action that is taken when any of the attributes in the group change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20ca9-109">Regras de negócio de controle de alterações consideram os dados preparados (importados) a serem alterados.</span><span class="sxs-lookup"><span data-stu-id="20ca9-109">Change tracking business rules consider staged (imported) data to be changed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="20ca9-110">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="20ca9-110">Related Tasks</span></span>  
  
|<span data-ttu-id="20ca9-111">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="20ca9-111">Task Description</span></span>|<span data-ttu-id="20ca9-112">Tópico</span><span class="sxs-lookup"><span data-stu-id="20ca9-112">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="20ca9-113">Adicionar atributos a um grupo de controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="20ca9-113">Add attributes to a change tracking group.</span></span>|[<span data-ttu-id="20ca9-114">Adicionar atributos a um grupo de controle de alterações &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="20ca9-114">Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;</span></span>](add-attributes-to-a-change-tracking-group-master-data-services.md)|  
|<span data-ttu-id="20ca9-115">Criar uma regra de negócios que inicie ações com base em alterações de atributos.</span><span class="sxs-lookup"><span data-stu-id="20ca9-115">Create a business rule that initiates actions based on attribute changes.</span></span>|[<span data-ttu-id="20ca9-116">Iniciar ações com base em alterações no valor do atributo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="20ca9-116">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="20ca9-117">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="20ca9-117">Related Content</span></span>  
  
-   [<span data-ttu-id="20ca9-118">Validação &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="20ca9-118">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
-   [<span data-ttu-id="20ca9-119">Regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="20ca9-119">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="20ca9-120">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="20ca9-120">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
