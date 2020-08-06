---
title: Palavras reservadas (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- reserved words [Master Data Services]
- Master Data Services, reserved words
ms.assetid: 88afd0d0-4362-4394-8357-4e65388fc0fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c54bb371cd8f797cfb36f015387e0e21339c0426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574756"
---
# <a name="reserved-words-master-data-services"></a><span data-ttu-id="0569f-102">Palavras reservadas (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0569f-102">Reserved Words (Master Data Services)</span></span>
  <span data-ttu-id="0569f-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], quando você cria objetos ou membros de modelo, algumas palavras não podem ser usadas.</span><span class="sxs-lookup"><span data-stu-id="0569f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when you create model objects or members, some words cannot be used.</span></span> <span data-ttu-id="0569f-104">Usar essas palavras pode causar erros.</span><span class="sxs-lookup"><span data-stu-id="0569f-104">Using these words may cause errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0569f-105">Você também deve limitar o uso de caracteres especiais (símbolos, hifenização, etc.)</span><span class="sxs-lookup"><span data-stu-id="0569f-105">You should also limit your use of special characters (symbols, hyphenation, etc.).</span></span>  
  
-   [<span data-ttu-id="0569f-106">Modelos</span><span class="sxs-lookup"><span data-stu-id="0569f-106">Models</span></span>](#models)  
  
-   [<span data-ttu-id="0569f-107">Entidades</span><span class="sxs-lookup"><span data-stu-id="0569f-107">Entities</span></span>](#entities)  
  
-   [<span data-ttu-id="0569f-108">Hierarquias explícitas</span><span class="sxs-lookup"><span data-stu-id="0569f-108">Explicit Hierarchies</span></span>](#exhierarchies)  
  
-   [<span data-ttu-id="0569f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0569f-109">Attributes</span></span>](#attributes)  
  
-   [<span data-ttu-id="0569f-110">Membros</span><span class="sxs-lookup"><span data-stu-id="0569f-110">Members</span></span>](#members)  
  
##  <a name="models"></a><a name="models"></a><span data-ttu-id="0569f-111">Modelos</span><span class="sxs-lookup"><span data-stu-id="0569f-111">Models</span></span>  
 <span data-ttu-id="0569f-112">Se você criar um modelo com o nome definido como **nome**, não selecione **criar entidade com o mesmo nome que o modelo** porque o **nome** não pode ser usado para o nome de uma entidade.</span><span class="sxs-lookup"><span data-stu-id="0569f-112">If you create a model with the name set to **Name**, do not select **Create entity with same name as model** because **Name** cannot be used for the name of an entity.</span></span>  
  
##  <a name="entities"></a><a name="entities"></a><span data-ttu-id="0569f-113">Contabilidade</span><span class="sxs-lookup"><span data-stu-id="0569f-113">Entities</span></span>  
 <span data-ttu-id="0569f-114">Para nomes de entidade, você não pode usar **Name** nem **Code**.</span><span class="sxs-lookup"><span data-stu-id="0569f-114">For entity names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="explicit-hierarchies"></a><a name="exhierarchies"></a><span data-ttu-id="0569f-115">Hierarquias explícitas</span><span class="sxs-lookup"><span data-stu-id="0569f-115">Explicit Hierarchies</span></span>  
 <span data-ttu-id="0569f-116">Para nomes de hierarquia explícita, você não pode usar **Name** nem **Code**.</span><span class="sxs-lookup"><span data-stu-id="0569f-116">For explicit hierarchy names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="attributes"></a><a name="attributes"></a><span data-ttu-id="0569f-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="0569f-117">Attributes</span></span>  
  
-   <span data-ttu-id="0569f-118">**ID**</span><span class="sxs-lookup"><span data-stu-id="0569f-118">**ID**</span></span>  
  
-   <span data-ttu-id="0569f-119">**Código**</span><span class="sxs-lookup"><span data-stu-id="0569f-119">**Code**</span></span>  
  
-   <span data-ttu-id="0569f-120">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0569f-120">**Name**</span></span>  
  
-   <span data-ttu-id="0569f-121">**EnterDTM**</span><span class="sxs-lookup"><span data-stu-id="0569f-121">**EnterDTM**</span></span>  
  
-   <span data-ttu-id="0569f-122">**EnterUserID**</span><span class="sxs-lookup"><span data-stu-id="0569f-122">**EnterUserID**</span></span>  
  
-   <span data-ttu-id="0569f-123">**EnterUserName**</span><span class="sxs-lookup"><span data-stu-id="0569f-123">**EnterUserName**</span></span>  
  
-   <span data-ttu-id="0569f-124">**LastChgDTM**</span><span class="sxs-lookup"><span data-stu-id="0569f-124">**LastChgDTM**</span></span>  
  
-   <span data-ttu-id="0569f-125">**LastChgUserID**</span><span class="sxs-lookup"><span data-stu-id="0569f-125">**LastChgUserID**</span></span>  
  
-   <span data-ttu-id="0569f-126">**Status_ID**</span><span class="sxs-lookup"><span data-stu-id="0569f-126">**Status_ID**</span></span>  
  
-   <span data-ttu-id="0569f-127">**ValidationStatus_ID**</span><span class="sxs-lookup"><span data-stu-id="0569f-127">**ValidationStatus_ID**</span></span>  
  
-   <span data-ttu-id="0569f-128">**Version_ID**</span><span class="sxs-lookup"><span data-stu-id="0569f-128">**Version_ID**</span></span>  
  
##  <a name="members"></a><a name="members"></a><span data-ttu-id="0569f-129">Os</span><span class="sxs-lookup"><span data-stu-id="0569f-129">Members</span></span>  
 <span data-ttu-id="0569f-130">Para membros, você não pode usar **MDMMemberStatus** ou **root** para o valor do atributo **Code** .</span><span class="sxs-lookup"><span data-stu-id="0569f-130">For members, you cannot use **MDMMemberStatus** or **ROOT** for the **Code** attribute value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0569f-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0569f-131">See Also</span></span>  
 [<span data-ttu-id="0569f-132">Visão geral de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="0569f-132">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
  
