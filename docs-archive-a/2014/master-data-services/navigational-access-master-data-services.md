---
title: Acesso de navegação (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- navigational access [Master Data Services]
- security [Master Data Services], navigational access
ms.assetid: 3403b7b0-44e2-48c3-a1b7-9c4612b874b8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7af3c16d98320b6fea3d4611e9e4c6d37c6015bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568661"
---
# <a name="navigational-access-master-data-services"></a><span data-ttu-id="fa9f8-102">Acesso de navegação (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="fa9f8-102">Navigational Access (Master Data Services)</span></span>
  <span data-ttu-id="fa9f8-103">O acesso de navegação se aplica à segurança do objeto do modelo que é atribuída na guia **Modelos** .</span><span class="sxs-lookup"><span data-stu-id="fa9f8-103">Navigational access applies to model object security, which is assigned on the **Models** tab.</span></span>  
  
 <span data-ttu-id="fa9f8-104">O acesso de navegação é o acesso que você obtém a níveis mais altos do que o acesso ao qual você atribuiu segurança.</span><span class="sxs-lookup"><span data-stu-id="fa9f8-104">Navigational access is the access you get to levels higher than where you've assigned security.</span></span>  
  
 <span data-ttu-id="fa9f8-105">Neste exemplo, as permissões são atribuídas a uma entidade e, portanto, o acesso de navegação é concedido no nível do modelo.</span><span class="sxs-lookup"><span data-stu-id="fa9f8-105">In this example, permissions are assigned to an entity, and so navigational access is granted at the model level.</span></span>  
  
 <span data-ttu-id="fa9f8-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="fa9f8-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>  
  
 <span data-ttu-id="fa9f8-107">**Entidades**</span><span class="sxs-lookup"><span data-stu-id="fa9f8-107">**Entities**</span></span>  
  
 <span data-ttu-id="fa9f8-108">Quando você atribui permissão a uma entidade, seus membros folha ou seus membros consolidados, o acesso de navegação significa que você pode ler ou atualizar o nome e o código de todos os membros.</span><span class="sxs-lookup"><span data-stu-id="fa9f8-108">When you assign permission to an entity, its leaf members, or its consolidated members, navigational access means you can read or update the name and code for all members.</span></span> <span data-ttu-id="fa9f8-109">Você também pode ler o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="fa9f8-109">You can also read the model name.</span></span>  
  
 <span data-ttu-id="fa9f8-110">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="fa9f8-110">**Attributes**</span></span>  
  
 <span data-ttu-id="fa9f8-111">Quando você atribui permissão a um atributo, o acesso de navegação significa que você pode ler ou atualizar o nome e o código de todos os membros da entidade.</span><span class="sxs-lookup"><span data-stu-id="fa9f8-111">When you assign permission to an attribute, navigational access means you can read or update the name and code for all members in the entity.</span></span> <span data-ttu-id="fa9f8-112">Você também pode ler o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="fa9f8-112">You can also read the model name.</span></span>  
  
 <span data-ttu-id="fa9f8-113">**Coleções**</span><span class="sxs-lookup"><span data-stu-id="fa9f8-113">**Collections**</span></span>  
  
 <span data-ttu-id="fa9f8-114">Quando atribui permissões a coleções, você pode ler ou atualizar o nome, o código, a descrição e a ID do proprietário.</span><span class="sxs-lookup"><span data-stu-id="fa9f8-114">When you assign permissions to collections, you can read or update the name, code, description and owner ID.</span></span> <span data-ttu-id="fa9f8-115">Você também pode ler o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="fa9f8-115">You can also read the model name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa9f8-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fa9f8-116">See Also</span></span>  
 [<span data-ttu-id="fa9f8-117">Como as permissões são determinadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fa9f8-117">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](how-permissions-are-determined-master-data-services.md)  
  
  
