---
title: Propriedades de nível | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- user hierarchies [Analysis Services]
- hierarchies [Analysis Services], user
ms.assetid: dabb7335-887b-442a-b67c-4901ba1242b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 553503b9d35142bcc998b4ec12ad2e29d4c66318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570309"
---
# <a name="level-properties"></a><span data-ttu-id="7eb49-102">Propriedades de nível</span><span class="sxs-lookup"><span data-stu-id="7eb49-102">Level Properties</span></span> 
  <span data-ttu-id="7eb49-103">A tabela a seguir lista e descreve as propriedades de um nível em uma hierarquia definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7eb49-103">The following table lists and describes the properties of a level in a user-defined hierarchy.</span></span>  
  
|<span data-ttu-id="7eb49-104">Propriedade</span><span class="sxs-lookup"><span data-stu-id="7eb49-104">Property</span></span>|<span data-ttu-id="7eb49-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="7eb49-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="7eb49-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="7eb49-106">Description</span></span>|<span data-ttu-id="7eb49-107">Contém a descrição do nível.</span><span class="sxs-lookup"><span data-stu-id="7eb49-107">Contains the description of the level.</span></span>|  
|<span data-ttu-id="7eb49-108">HideMemberIf</span><span class="sxs-lookup"><span data-stu-id="7eb49-108">HideMemberIf</span></span>|<span data-ttu-id="7eb49-109">Indica se, e quando, um membro em um nível ficará oculto pelos aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="7eb49-109">Indicates whether and when a member in a level should be hidden from client applications.</span></span> <span data-ttu-id="7eb49-110">Essa propriedade pode ter os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7eb49-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="7eb49-111">Nunca</span><span class="sxs-lookup"><span data-stu-id="7eb49-111">Never</span></span><br /> <span data-ttu-id="7eb49-112">Membros nunca são ocultados.</span><span class="sxs-lookup"><span data-stu-id="7eb49-112">Members are never hidden.</span></span> <span data-ttu-id="7eb49-113">Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="7eb49-113">This is the default value.</span></span><br /><br /> <span data-ttu-id="7eb49-114">OnlyChildWithNoName</span><span class="sxs-lookup"><span data-stu-id="7eb49-114">OnlyChildWithNoName</span></span><br /> <span data-ttu-id="7eb49-115">Um membro é ocultado quando o membro for o único filho de seu pai e seu nome estiver vazio.</span><span class="sxs-lookup"><span data-stu-id="7eb49-115">A member is hidden when the member is the only child of its parent and the member's name is empty.</span></span><br /><br /> <span data-ttu-id="7eb49-116">OnlyChildWithParentName</span><span class="sxs-lookup"><span data-stu-id="7eb49-116">OnlyChildWithParentName</span></span><br /> <span data-ttu-id="7eb49-117">Um membro é ocultado quando o membro for o único filho de seu pai e seu nome for idêntico ao de seu pai.</span><span class="sxs-lookup"><span data-stu-id="7eb49-117">A member is hidden when the member is the only child of its parent and the member's name is identical to that of its parent.</span></span><br /><br /> <span data-ttu-id="7eb49-118">NoName</span><span class="sxs-lookup"><span data-stu-id="7eb49-118">NoName</span></span><br /> <span data-ttu-id="7eb49-119">Um membro é ocultado quando o nome do membro estiver vazio.</span><span class="sxs-lookup"><span data-stu-id="7eb49-119">A member is hidden when the member's name is empty.</span></span><br /><br /> <span data-ttu-id="7eb49-120">ParentName</span><span class="sxs-lookup"><span data-stu-id="7eb49-120">ParentName</span></span><br /> <span data-ttu-id="7eb49-121">Um membro é ocultado quando o nome do membro for idêntico ao de seu pai.</span><span class="sxs-lookup"><span data-stu-id="7eb49-121">A member is hidden when the member's name is identical to that of its parent.</span></span>|  
|<span data-ttu-id="7eb49-122">ID</span><span class="sxs-lookup"><span data-stu-id="7eb49-122">ID</span></span>|<span data-ttu-id="7eb49-123">Contém o identificador exclusivo (ID) do nível.</span><span class="sxs-lookup"><span data-stu-id="7eb49-123">Contains the unique identifier (ID) of the level.</span></span>|  
|<span data-ttu-id="7eb49-124">Nome</span><span class="sxs-lookup"><span data-stu-id="7eb49-124">Name</span></span>|<span data-ttu-id="7eb49-125">Contém o nome amigável do nível.</span><span class="sxs-lookup"><span data-stu-id="7eb49-125">Contains the friendly name of the level.</span></span> <span data-ttu-id="7eb49-126">Por padrão, o nome de um nível é igual ao nome do atributo de origem.</span><span class="sxs-lookup"><span data-stu-id="7eb49-126">By default, the name of a level is the same as the name of the source attribute.</span></span>|  
|<span data-ttu-id="7eb49-127">SourceAttribute</span><span class="sxs-lookup"><span data-stu-id="7eb49-127">SourceAttribute</span></span>|<span data-ttu-id="7eb49-128">Contém o nome do atributo de origem no qual o nível tem como base.</span><span class="sxs-lookup"><span data-stu-id="7eb49-128">Contains the name of the source attribute on which the level is based.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7eb49-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7eb49-129">See Also</span></span>  
 [<span data-ttu-id="7eb49-130">Propriedades de hierarquia do usuário</span><span class="sxs-lookup"><span data-stu-id="7eb49-130">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
