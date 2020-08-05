---
title: Examinar o uso de agregação (Assistente de design de agregação) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.aggregationdesignwizard.reviewusage.f1
ms.assetid: 107ee872-3df2-4931-b56c-af11e38f6745
author: minewiskan
ms.author: owend
ms.openlocfilehash: afbb02dae64f3f7ebd57065c3ff8a7d1e202dcf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570934"
---
# <a name="review-aggregation-usage-aggregation-design-wizard"></a><span data-ttu-id="e533e-102">Revisar Uso de Agregação (Assistente de Design de Agregação)</span><span class="sxs-lookup"><span data-stu-id="e533e-102">Review Aggregation Usage (Aggregation Design Wizard)</span></span>
  <span data-ttu-id="e533e-103">Use a página **Revisar Uso de Agregação** para efetuar configurações do uso de agregação.</span><span class="sxs-lookup"><span data-stu-id="e533e-103">Use the **Review Aggregation Usage** page to configure aggregation usage settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e533e-104">Opções</span><span class="sxs-lookup"><span data-stu-id="e533e-104">Options</span></span>  
 <span data-ttu-id="e533e-105">**Default**</span><span class="sxs-lookup"><span data-stu-id="e533e-105">**Default**</span></span>  
 <span data-ttu-id="e533e-106">Selecione para definir a configuração do uso de agregação do atributo como Padrão.</span><span class="sxs-lookup"><span data-stu-id="e533e-106">Select to set the aggregation usage setting for the attribute to Default.</span></span> <span data-ttu-id="e533e-107">Quando essa configuração é utilizada, o designer aplica uma regra padrão com base no tipo de atributo e dimensão.</span><span class="sxs-lookup"><span data-stu-id="e533e-107">By using this setting, the designer applies a default rule based on the type of attribute and dimension.</span></span>  
  
 `Full`  
 <span data-ttu-id="e533e-108">Selecione para definir a configuração de uso de agregação para o atributo como `Full`.</span><span class="sxs-lookup"><span data-stu-id="e533e-108">Select to set the aggregation usage setting for the attribute to `Full`.</span></span> <span data-ttu-id="e533e-109">Quando essa configuração é utilizada, cada agregação para o cubo deve incluir esse atributo ou um atributo relacionado inferior na cadeia de atributos.</span><span class="sxs-lookup"><span data-stu-id="e533e-109">By using this setting, every aggregation for the cube must include this attribute or a related attribute that is lower in the attribute chain.</span></span> <span data-ttu-id="e533e-110">A configuração de uso de agregação `Full` deverá ser evitada quando um atributo contiver muitos membros.</span><span class="sxs-lookup"><span data-stu-id="e533e-110">The `Full` aggregation usage setting should be avoided when an attribute contains many members.</span></span> <span data-ttu-id="e533e-111">Se for especificada para vários atributos ou atributos que têm muitos membros, essa configuração poderá impedir a criação de agregações por causa do seu tamanho excessivo.</span><span class="sxs-lookup"><span data-stu-id="e533e-111">If specified for multiple attributes or attributes that have many members, this setting might prevent aggregations from being designed because of excessive size.</span></span>  
  
 <span data-ttu-id="e533e-112">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="e533e-112">**None**</span></span>  
 <span data-ttu-id="e533e-113">Selecione para definir a configuração do uso de agregação do atributo como Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e533e-113">Select to set the aggregation usage setting for the attribute to None.</span></span> <span data-ttu-id="e533e-114">Quando essa configuração é utilizada, nenhuma agregação para o cubo pode incluir esse atributo.</span><span class="sxs-lookup"><span data-stu-id="e533e-114">By using this setting, no aggregation for the cube can include this attribute.</span></span>  
  
 `Unrestricted`  
 <span data-ttu-id="e533e-115">Selecione para definir a configuração de uso de agregação para o atributo como `Unrestricted`.</span><span class="sxs-lookup"><span data-stu-id="e533e-115">Select to set the aggregation usage setting for the attribute to `Unrestricted`.</span></span> <span data-ttu-id="e533e-116">Quando essa configuração é utilizada , não são impostas restrições sobre o designer de agregação; porém, o atributo ainda deve ser avaliado para determinar se é um candidato de agregação valioso.</span><span class="sxs-lookup"><span data-stu-id="e533e-116">By using this setting, no restrictions are put on the aggregation designer; however, the attribute must still be evaluated to determine whether it is a valuable aggregation candidate.</span></span>  
  
 <span data-ttu-id="e533e-117">**Definir Tudo como Padrão**</span><span class="sxs-lookup"><span data-stu-id="e533e-117">**Set All to Default**</span></span>  
 <span data-ttu-id="e533e-118">Selecione para definir a configuração do uso de agregação de todos os atributos como Padrão.</span><span class="sxs-lookup"><span data-stu-id="e533e-118">Select to set the aggregation usage settings for all attributes to Default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e533e-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e533e-119">See Also</span></span>  
 <span data-ttu-id="e533e-120">[Ajuda F1 do assistente de design de agregação](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e533e-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="e533e-121">Analysis Services assistentes &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="e533e-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
