---
title: Validar membros específicos em relação a regras de negócio (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- applying business rules [Master Data Services]
- business rules [Master Data Services], applying to select members
ms.assetid: 2288ef43-5392-47ea-b651-ec25e5692a14
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 18af83146679eb77638dfbc98b31f198dc8e07b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573161"
---
# <a name="validate-specific-members-against-business-rules-master-data-services"></a><span data-ttu-id="03a35-102">Validar membros específicos em relação a regras de negócio (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="03a35-102">Validate Specific Members against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="03a35-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], aplique regras de negócio seletivamente quando desejar atualizar ou validar subconjuntos de membros com base em regras de negócio.</span><span class="sxs-lookup"><span data-stu-id="03a35-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], apply business rules selectively when you want to update or validate subsets of members against business rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="03a35-104">Se você deseja aplicar regras de negócio a todos os membros em uma versão de um modelo, consulte [Validar uma versão em relação a regras de negócio &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="03a35-104">If you want to apply business rules to all members in a version of a model, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="03a35-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="03a35-105">Prerequisites</span></span>  
 <span data-ttu-id="03a35-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="03a35-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="03a35-107">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="03a35-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="03a35-108">Você deve ter, no mínimo, a permissão **Atualizar** para o objeto de modelo ao qual está aplicando regras de negócio.</span><span class="sxs-lookup"><span data-stu-id="03a35-108">You must have a minimum of **Update** permission to the model object you are applying business rules to.</span></span>  
  
### <a name="to-apply-business-rules-selectively"></a><span data-ttu-id="03a35-109">Para aplicar regras de negócio seletivamente.</span><span class="sxs-lookup"><span data-stu-id="03a35-109">To apply business rules selectively</span></span>  
  
1.  <span data-ttu-id="03a35-110">Na home page do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="03a35-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="03a35-111">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="03a35-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="03a35-112">Clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="03a35-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="03a35-113">Na barra de menus, aponte para **Entidades** e clique no nome da entidade que contém os membros aos quais você deseja aplicar regras.</span><span class="sxs-lookup"><span data-stu-id="03a35-113">From the menu bar, point to **Entities** and click the name of the entity that contains members you want to apply rules to.</span></span>  
  
5.  <span data-ttu-id="03a35-114">Clique em **Aplicar regras de negócio**.</span><span class="sxs-lookup"><span data-stu-id="03a35-114">Click **Apply business rules**.</span></span> <span data-ttu-id="03a35-115">As regras de negócio são aplicadas apenas aos membros exibidos na grade.</span><span class="sxs-lookup"><span data-stu-id="03a35-115">Business rules are applied only to the members displayed in the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a35-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="03a35-116">See Also</span></span>  
 <span data-ttu-id="03a35-117">[Validar uma versão em relação às regras de negócio &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="03a35-117">[Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="03a35-118">Regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="03a35-118">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
