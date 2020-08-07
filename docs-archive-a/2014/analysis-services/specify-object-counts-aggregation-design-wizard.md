---
title: Especificar contagens de objetos (Assistente de design de agregação) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 305d9d79-d1ab-4704-a7b5-3283842b3996
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66b972395f86746b2d08df234db8aa0c71d03fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575387"
---
# <a name="specify-object-counts-aggregation-design-wizard"></a><span data-ttu-id="64b3f-102">Especificar Contagens de Objetos (Assistente de Design de Agregação)</span><span class="sxs-lookup"><span data-stu-id="64b3f-102">Specify Object Counts (Aggregation Design Wizard)</span></span>
  <span data-ttu-id="64b3f-103">Use a página **Especificar Contagens de Objetos** para calcular a contagem de objetos no cubo automaticamente ou para inserir contagens estimadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="64b3f-103">Use the **Specify Object Counts** page to automatically calculate the count of objects in the cube or to manually enter estimated counts.</span></span> <span data-ttu-id="64b3f-104">O Assistente de Design de Agregação usa a contagem de objetos para estimar requisitos de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="64b3f-104">The Aggregation Design Wizard uses the object counts to estimate storage requirements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="64b3f-105">Opções</span><span class="sxs-lookup"><span data-stu-id="64b3f-105">Options</span></span>  
 <span data-ttu-id="64b3f-106">**Objetos de Cubo**</span><span class="sxs-lookup"><span data-stu-id="64b3f-106">**Cube Objects**</span></span>  
 <span data-ttu-id="64b3f-107">Exibe as dimensões e os atributos do cubo.</span><span class="sxs-lookup"><span data-stu-id="64b3f-107">Displays the dimensions and attributes in the cube.</span></span> <span data-ttu-id="64b3f-108">Somente os atributos que não têm sua `AggregationUsage` propriedade definida como `None` na página **revisar uso de agregação** do assistente são mostrados, pois esses são os únicos atributos que exigem que as contagens sejam especificadas.</span><span class="sxs-lookup"><span data-stu-id="64b3f-108">Only the attributes that do not have their `AggregationUsage` property set to `None` in the **Review Aggregation Usage** page of the wizard are shown, because those are the only attributes that require the counts to be specified.</span></span>  
  
 <span data-ttu-id="64b3f-109">**Contagem estimada**</span><span class="sxs-lookup"><span data-stu-id="64b3f-109">**Estimated count**</span></span>  
 <span data-ttu-id="64b3f-110">Exibe o número estimado de linhas no grupo de medidas e as contagens de membros de atributo estimadas nas dimensões do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="64b3f-110">Displays the estimated number of rows in the measure group and the estimated attribute member counts in the database dimensions.</span></span> <span data-ttu-id="64b3f-111">Você pode digitar um valor a ser usado como a contagem estimada ou calcular os valores da contagem estimada.</span><span class="sxs-lookup"><span data-stu-id="64b3f-111">You can type a value to use as the estimated count or you can calculate the estimated count values.</span></span> <span data-ttu-id="64b3f-112">Para calcular os valores de contagem, digite `0` no campo e, em seguida, clique em **contagem**.</span><span class="sxs-lookup"><span data-stu-id="64b3f-112">To calculate the count values, type `0` in the field and then click **Count**.</span></span> <span data-ttu-id="64b3f-113">Os campos que já exibem uma contagem não são atualizados.</span><span class="sxs-lookup"><span data-stu-id="64b3f-113">Fields that already display a count are not updated.</span></span>  
  
 <span data-ttu-id="64b3f-114">**Contagem de partição**</span><span class="sxs-lookup"><span data-stu-id="64b3f-114">**Partition count**</span></span>  
 <span data-ttu-id="64b3f-115">(Opcional) Digite o número estimado de linhas no grupo de medidas e digite as contagens de membros de atributo estimadas nas partições.</span><span class="sxs-lookup"><span data-stu-id="64b3f-115">(Optional) Type the estimated number of rows in the measure group and type the estimated attribute member counts in the partitions.</span></span>  
  
 <span data-ttu-id="64b3f-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="64b3f-116">**Count**</span></span>  
 <span data-ttu-id="64b3f-117">Calcula e popula novamente os valores na coluna **Contagem estimada** para todos os campos vazios.</span><span class="sxs-lookup"><span data-stu-id="64b3f-117">Calculates and repopulates the values in the **Estimated count** column for all empty fields.</span></span> <span data-ttu-id="64b3f-118">Os campos que já exibem uma contagem não são atualizados.</span><span class="sxs-lookup"><span data-stu-id="64b3f-118">Fields that already display a count are not updated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b3f-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="64b3f-119">See Also</span></span>  
 <span data-ttu-id="64b3f-120">[Ajuda F1 do assistente de design de agregação](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="64b3f-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="64b3f-121">Analysis Services assistentes &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="64b3f-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
