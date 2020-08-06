---
title: Definir comportamento semiaditivo (Assistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.semiadditivememberdetection.f1
ms.assetid: e57080ba-ce96-40f8-bca7-6701d1725b3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5a3c46de038a7e45dcb39805e324260676a03228
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679092"
---
# <a name="define-semiadditive-behavior-business-intelligence-wizard"></a><span data-ttu-id="9b005-102">Definir Comportamento Semiaditivo (Assistente de Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="9b005-102">Define Semiadditive Behavior (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="9b005-103">Use a página **Definir Comportamento Semiaditivo** para habilitar ou desabilitar comportamento semiaditivo em medidas.</span><span class="sxs-lookup"><span data-stu-id="9b005-103">Use the **Define Semiadditive Behavior** page to enable or disable semi-additive behavior on measures.</span></span> <span data-ttu-id="9b005-104">O comportamento semiaditivo determina como medidas que são contidas por um cubo são agregadas sobre uma dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="9b005-104">Semi-additive behavior determines how measures that are contained by a cube are aggregated over a time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b005-105">Com exceção de LastChild que está disponível na edição standard, os comportamentos semiaditivos só estão disponíveis nas edições business intelligence ou enterprise.</span><span class="sxs-lookup"><span data-stu-id="9b005-105">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span> <span data-ttu-id="9b005-106">Além disso, como o comportamento semiaditivo é definido somente em medidas e não em dimensões, você não encontrará esta página no Assistente de Business Intelligence caso ele tenha sido iniciado do Designer de Dimensão ou por meio de um clique com o botão direito do mouse no Gerenciador de Soluções do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b005-106">Furthermore, because semiadditive behavior is defined only on measures and not dimensions, you will not find this page in the Business Intelligence Wizard if it was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="9b005-107">Opções</span><span class="sxs-lookup"><span data-stu-id="9b005-107">Options</span></span>  
 <span data-ttu-id="9b005-108">**Desativar comportamento semiaditivo**</span><span class="sxs-lookup"><span data-stu-id="9b005-108">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="9b005-109">Desabilita comportamento semiaditivo em todas as medidas contidas pelo cubo.</span><span class="sxs-lookup"><span data-stu-id="9b005-109">Disables semi-additive behavior in all measures contained by the cube.</span></span>  
  
 <span data-ttu-id="9b005-110">**O assistente detectou a \<dimension name> dimensão de conta, que contém membros semiaditivos. O servidor agregará membros dessa dimensão de acordo com o comportamento semiaditivo especificado para cada tipo de conta.**</span><span class="sxs-lookup"><span data-stu-id="9b005-110">**The wizard has detected the \<dimension name> account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="9b005-111">Habilita comportamento semiaditivo para dimensões de conta que contêm membros semiaditivos.</span><span class="sxs-lookup"><span data-stu-id="9b005-111">Enables semi-additive behavior for account dimensions that contain semi-additive members.</span></span> <span data-ttu-id="9b005-112">A seleção dessa opção configura a função de agregação de todas as medidas do grupo de medidas que faz referência à dimensão de conta para `ByAccount`.</span><span class="sxs-lookup"><span data-stu-id="9b005-112">Selecting this option sets the aggregation function of all measures in measure groups that reference the account dimension to `ByAccount`.</span></span>  
  
 <span data-ttu-id="9b005-113">Para obter mais informações sobre dimensões de conta, consulte [Criar uma Conta de Finanças de dimensão de tipo pai-filho](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span><span class="sxs-lookup"><span data-stu-id="9b005-113">For more information about account dimensions, see [Create a Finance Account of parent-child type Dimension](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span></span>  
  
 <span data-ttu-id="9b005-114">**Definir comportamento semiaditivo para membros individuais**</span><span class="sxs-lookup"><span data-stu-id="9b005-114">**Define semiadditive behavior for individual members**</span></span>  
 <span data-ttu-id="9b005-115">Habilita comportamento semiaditivo e especifica a função de agregação semiaditiva para medidas específicas.</span><span class="sxs-lookup"><span data-stu-id="9b005-115">Enables semi-additive behavior and specifies the semi-additive aggregation function for specific measures.</span></span> <span data-ttu-id="9b005-116">A função de agregação aplica-se a todas as dimensões que são referenciadas pelo grupo de medidas que contém a medida.</span><span class="sxs-lookup"><span data-stu-id="9b005-116">The aggregation function applies to all dimensions that are referenced by the measure group that contains the measure.</span></span>  
  
 <span data-ttu-id="9b005-117">**Determina**</span><span class="sxs-lookup"><span data-stu-id="9b005-117">**Measures**</span></span>  
 <span data-ttu-id="9b005-118">Exibe o nome de uma medida contida pelo cubo.</span><span class="sxs-lookup"><span data-stu-id="9b005-118">Displays the name of a measure contained by the cube.</span></span>  
  
 <span data-ttu-id="9b005-119">**Função Semiaditiva**</span><span class="sxs-lookup"><span data-stu-id="9b005-119">**Semiadditive Function**</span></span>  
 <span data-ttu-id="9b005-120">Selecione a função de agregação da medida selecionada.</span><span class="sxs-lookup"><span data-stu-id="9b005-120">Select the aggregation function for the selected measure.</span></span> <span data-ttu-id="9b005-121">A tabela a seguir lista as funções de agregação disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9b005-121">The following table lists the aggregation functions that are available.</span></span>  
  
|<span data-ttu-id="9b005-122">Valor</span><span class="sxs-lookup"><span data-stu-id="9b005-122">Value</span></span>|<span data-ttu-id="9b005-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b005-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9b005-124">**AverageOfChildren**</span><span class="sxs-lookup"><span data-stu-id="9b005-124">**AverageOfChildren**</span></span>|<span data-ttu-id="9b005-125">Agregada retornando a média dos filhos da medida.</span><span class="sxs-lookup"><span data-stu-id="9b005-125">Aggregated by returning the average of the measure's children.</span></span>|  
|`ByAccount`|<span data-ttu-id="9b005-126">Agregada pela função de agregação associada ao tipo de conta especificado de um atributo em uma dimensão de conta.</span><span class="sxs-lookup"><span data-stu-id="9b005-126">Aggregated by the aggregation function associated with the specified account type of an attribute in an account dimension.</span></span>|  
|`Count`|<span data-ttu-id="9b005-127">Agregada com a função `Count`.</span><span class="sxs-lookup"><span data-stu-id="9b005-127">Aggregated using the `Count` function.</span></span>|  
|`DistinctCount`|<span data-ttu-id="9b005-128">Agregada com a função `DistinctCount`.</span><span class="sxs-lookup"><span data-stu-id="9b005-128">Aggregated using the `DistinctCount` function.</span></span>|  
|<span data-ttu-id="9b005-129">**FirstChild**</span><span class="sxs-lookup"><span data-stu-id="9b005-129">**FirstChild**</span></span>|<span data-ttu-id="9b005-130">Agregado ao retornar o primeiro membro filho da medida em uma dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="9b005-130">Aggregated by returning the measure's first child member over a time dimension.</span></span>|  
|<span data-ttu-id="9b005-131">**FirstNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="9b005-131">**FirstNonEmpty**</span></span>|<span data-ttu-id="9b005-132">Agregado ao retornar o primeiro membro não vazio da medida em uma dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="9b005-132">Aggregated by returning the measure's first nonempty member over a time dimension.</span></span>|  
|<span data-ttu-id="9b005-133">**LastChild**</span><span class="sxs-lookup"><span data-stu-id="9b005-133">**LastChild**</span></span>|<span data-ttu-id="9b005-134">Agregado ao retornar o último membro filho da medida em uma dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="9b005-134">Aggregated by returning the measure's last child member over a time dimension.</span></span>|  
|<span data-ttu-id="9b005-135">**LastNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="9b005-135">**LastNonEmpty**</span></span>|<span data-ttu-id="9b005-136">Agregado ao retornar o último membro não vazio da medida em uma dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="9b005-136">Aggregated by returning the measure's last nonempty member over a time dimension.</span></span>|  
|`Max`|<span data-ttu-id="9b005-137">Agregada com a função `Max`.</span><span class="sxs-lookup"><span data-stu-id="9b005-137">Aggregated using the `Max` function.</span></span>|  
|`Min`|<span data-ttu-id="9b005-138">Agregada com a função `Min`.</span><span class="sxs-lookup"><span data-stu-id="9b005-138">Aggregated using the `Min` function.</span></span>|  
|<span data-ttu-id="9b005-139">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="9b005-139">**None**</span></span>|<span data-ttu-id="9b005-140">Nenhuma agregação executada.</span><span class="sxs-lookup"><span data-stu-id="9b005-140">No aggregation performed.</span></span>|  
|`Sum`|<span data-ttu-id="9b005-141">Agregada com a função `Sum`.</span><span class="sxs-lookup"><span data-stu-id="9b005-141">Aggregated using the `Sum` function.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="9b005-142">Seleções feitas para essa opção serão aplicadas apenas se **Definir comportamento semiaditivo para membros individuais** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="9b005-142">Selections made for this option apply only if **Define semiadditive behavior for individual members** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b005-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b005-143">See Also</span></span>  
 <span data-ttu-id="9b005-144">[Ajuda F1 do assistente de Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="9b005-144">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="9b005-145">[O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="9b005-145">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="9b005-146">O designer de dimensão &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="9b005-146">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
