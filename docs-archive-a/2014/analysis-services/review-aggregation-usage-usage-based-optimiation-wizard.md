---
title: Examinar o uso de agregação (Assistente de otimização com base no uso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.reviewaggregationusage.f1
ms.assetid: 49ce2094-c4dc-4e46-8cef-c17c5db084ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ef9f900e64858515db226d1f9b864874a4ba827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570933"
---
# <a name="review-aggregation-usage-usage-based-optimiation-wizard"></a><span data-ttu-id="b678c-102">Verificar Uso de Agregação (Assistente de Otimização com Base no Uso)</span><span class="sxs-lookup"><span data-stu-id="b678c-102">Review Aggregation Usage (Usage-Based Optimiation Wizard)</span></span>
  <span data-ttu-id="b678c-103">Use a página **Revisar Uso de Agregação** para efetuar configurações do uso de agregação.</span><span class="sxs-lookup"><span data-stu-id="b678c-103">Use the **Review Aggregation Usage** page to configure aggregation usage settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b678c-104">Opções</span><span class="sxs-lookup"><span data-stu-id="b678c-104">Options</span></span>  
 <span data-ttu-id="b678c-105">**Default**</span><span class="sxs-lookup"><span data-stu-id="b678c-105">**Default**</span></span>  
 <span data-ttu-id="b678c-106">Selecione para definir a configuração do uso de agregação do atributo como Padrão.</span><span class="sxs-lookup"><span data-stu-id="b678c-106">Select to set the aggregation usage setting for the attribute to Default.</span></span> <span data-ttu-id="b678c-107">Quando essa configuração é utilizada, o designer aplica uma regra padrão com base no tipo de atributo e dimensão.</span><span class="sxs-lookup"><span data-stu-id="b678c-107">By using this setting, the designer applies a default rule based on the type of attribute and dimension.</span></span>  
  
 <span data-ttu-id="b678c-108">**Full**</span><span class="sxs-lookup"><span data-stu-id="b678c-108">**Full**</span></span>  
 <span data-ttu-id="b678c-109">Selecione para definir a configuração do uso de agregação do atributo como Completo.</span><span class="sxs-lookup"><span data-stu-id="b678c-109">Select to set the aggregation usage setting for the attribute to Full.</span></span> <span data-ttu-id="b678c-110">Quando essa configuração é utilizada, cada agregação para o cubo deve incluir esse atributo ou um atributo relacionado inferior na cadeia de atributos.</span><span class="sxs-lookup"><span data-stu-id="b678c-110">By using this setting, every aggregation for the cube must include this attribute or a related attribute that is lower in the attribute chain.</span></span> <span data-ttu-id="b678c-111">A configuração do uso de agregação Completo deverá ser evitada quando um atributo contiver muitos membros.</span><span class="sxs-lookup"><span data-stu-id="b678c-111">The Full aggregation usage setting should be avoided when an attribute contains many members.</span></span> <span data-ttu-id="b678c-112">Se for especificada para vários atributos ou atributos que têm muitos membros, essa configuração poderá impedir a criação de agregações por causa do seu tamanho excessivo.</span><span class="sxs-lookup"><span data-stu-id="b678c-112">If specified for multiple attributes or attributes that have many members, this setting might prevent aggregations from being designed because of excessive size.</span></span>  
  
 <span data-ttu-id="b678c-113">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="b678c-113">**None**</span></span>  
 <span data-ttu-id="b678c-114">Selecione para definir a configuração do uso de agregação do atributo como Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b678c-114">Select to set the aggregation usage setting for the attribute to None.</span></span> <span data-ttu-id="b678c-115">Quando essa configuração é utilizada, nenhuma agregação para o cubo pode incluir esse atributo.</span><span class="sxs-lookup"><span data-stu-id="b678c-115">By using this setting, no aggregation for the cube can include this attribute.</span></span>  
  
 <span data-ttu-id="b678c-116">**Irrestrito**</span><span class="sxs-lookup"><span data-stu-id="b678c-116">**Unrestricted**</span></span>  
 <span data-ttu-id="b678c-117">Selecione para definir a configuração do uso de agregação do atributo como Irrestrito.</span><span class="sxs-lookup"><span data-stu-id="b678c-117">Select to set the aggregation usage setting for the attribute to Unrestricted.</span></span> <span data-ttu-id="b678c-118">Quando essa configuração é utilizada, nenhuma restrição é colocada no designer de agregação.</span><span class="sxs-lookup"><span data-stu-id="b678c-118">By using this setting, no restrictions are put on the aggregation designer.</span></span> <span data-ttu-id="b678c-119">O atributo, porém, ainda deverá ser avaliado para determinar se é um candidato de agregação valioso.</span><span class="sxs-lookup"><span data-stu-id="b678c-119">However, the attribute must still be evaluated to determine whether it is a valuable aggregation candidate.</span></span>  
  
 <span data-ttu-id="b678c-120">**Definir Tudo como Padrão**</span><span class="sxs-lookup"><span data-stu-id="b678c-120">**Set All to Default**</span></span>  
 <span data-ttu-id="b678c-121">Selecione para definir a configuração do uso de agregação de todos os atributos como Padrão.</span><span class="sxs-lookup"><span data-stu-id="b678c-121">Select to set the aggregation usage settings for all attributes to Default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b678c-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b678c-122">See Also</span></span>  
 <span data-ttu-id="b678c-123">[Ajuda F1 do assistente de design de agregação](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="b678c-123">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="b678c-124">Analysis Services assistentes &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="b678c-124">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
