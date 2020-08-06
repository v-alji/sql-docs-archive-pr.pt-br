---
title: Especificar contagens de objetos (Assistente de otimização com base no uso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 306c7c25-ae24-4852-ab8c-c82f68a4bc1f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 862be19f12308def815a280dba04f42f0cbe6878
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581497"
---
# <a name="specify-object-counts-usage-based-optimization-wizard"></a><span data-ttu-id="4ec8f-102">Especificar Contagens de Objetos (Assistente de Otimização com Base no Uso)</span><span class="sxs-lookup"><span data-stu-id="4ec8f-102">Specify Object Counts (Usage-Based Optimization Wizard)</span></span>
  <span data-ttu-id="4ec8f-103">Use a página **Especificar Contagens de Objetos** para calcular a contagem de objetos no cubo automaticamente ou para inserir contagens estimadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="4ec8f-103">Use the **Specify Object Counts** page to automatically calculate the count of objects in the cube or to manually enter estimated counts.</span></span> <span data-ttu-id="4ec8f-104">O Assistente de Otimização com Base no Uso usa a contagem de objetos para estimar requisitos de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="4ec8f-104">The Usage-Based Optimization Wizard uses the object counts to estimate storage requirements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4ec8f-105">Opções</span><span class="sxs-lookup"><span data-stu-id="4ec8f-105">Options</span></span>  
 <span data-ttu-id="4ec8f-106">**Objetos de Cubo**</span><span class="sxs-lookup"><span data-stu-id="4ec8f-106">**Cube Objects**</span></span>  
 <span data-ttu-id="4ec8f-107">Exibe as dimensões e os atributos do cubo.</span><span class="sxs-lookup"><span data-stu-id="4ec8f-107">Displays the dimensions and attributes in the cube.</span></span> <span data-ttu-id="4ec8f-108">Somente os atributos que não têm sua `AggregationUsage` propriedade definida como nenhum na página **revisar uso de agregação** do assistente são mostrados porque esses são os únicos atributos que precisam de contagens especificadas.</span><span class="sxs-lookup"><span data-stu-id="4ec8f-108">Only the attributes that do not have their `AggregationUsage` property set to None in the **Review Aggregation Usage** page of the wizard are shown because those are the only attributes that need counts specified.</span></span>  
  
 <span data-ttu-id="4ec8f-109">**Contagem estimada**</span><span class="sxs-lookup"><span data-stu-id="4ec8f-109">**Estimated count**</span></span>  
 <span data-ttu-id="4ec8f-110">Exibe o número estimado de linhas no grupo de medidas e as contagens de membros de atributo estimadas nas dimensões do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ec8f-110">Displays the estimated number of rows in the measure group and the estimated attribute member counts in the database dimensions.</span></span> <span data-ttu-id="4ec8f-111">Você pode digitar um valor a ser usado como a contagem estimada ou calcular os valores da contagem estimada.</span><span class="sxs-lookup"><span data-stu-id="4ec8f-111">You can type a value to use as the estimated count or you can calculate the estimated count values.</span></span> <span data-ttu-id="4ec8f-112">Para calcular os valores da contagem, digite 0 no campo e clique em **Contagem**.</span><span class="sxs-lookup"><span data-stu-id="4ec8f-112">To calculate the count values, type 0 in the field and then click **Count**.</span></span> <span data-ttu-id="4ec8f-113">Os campos que já exibem uma contagem não são atualizados.</span><span class="sxs-lookup"><span data-stu-id="4ec8f-113">Fields that already display a count are not updated.</span></span>  
  
 <span data-ttu-id="4ec8f-114">**Contagem de partição**</span><span class="sxs-lookup"><span data-stu-id="4ec8f-114">**Partition count**</span></span>  
 <span data-ttu-id="4ec8f-115">(Opcional) Digite o número estimado de linhas no grupo de medidas e as contagens de membros de atributo estimadas nas partições.</span><span class="sxs-lookup"><span data-stu-id="4ec8f-115">(Optional) Type the estimated number of rows in the measure group and the estimated attribute member counts in the partitions.</span></span>  
  
 <span data-ttu-id="4ec8f-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="4ec8f-116">**Count**</span></span>  
 <span data-ttu-id="4ec8f-117">Calcula e popula novamente os valores na coluna **Contagem estimada** para todos os campos vazios.</span><span class="sxs-lookup"><span data-stu-id="4ec8f-117">Calculates and repopulates the values in the **Estimated count** column for all empty fields.</span></span> <span data-ttu-id="4ec8f-118">Os campos que já exibem uma contagem não são atualizados.</span><span class="sxs-lookup"><span data-stu-id="4ec8f-118">Fields that already display a count are not updated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec8f-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4ec8f-119">See Also</span></span>  
 <span data-ttu-id="4ec8f-120">[Ajuda F1 do assistente de design de agregação](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="4ec8f-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="4ec8f-121">Analysis Services assistentes &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="4ec8f-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
