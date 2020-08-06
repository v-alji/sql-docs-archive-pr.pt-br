---
title: Configurar atributos de dimensão (Assistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.selectattributes.f1
ms.assetid: 3d046e63-bcb1-4ab1-9c37-652463fa68c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1d2e9bc83b7a6d83b6d2808b472d67169266ff07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571048"
---
# <a name="configure-dimension-attributes-business-intelligence-wizard"></a><span data-ttu-id="34926-102">Configurar Atributos de Dimensão (Assistente de Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="34926-102">Configure Dimension Attributes (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="34926-103">Use a página **Configurar Atributos de Dimensão** para mapear atributos de dimensão para os tipos atributos usados pelo [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para identificar atributos para dimensões de conta.</span><span class="sxs-lookup"><span data-stu-id="34926-103">Use the **Configure Dimension Attributes** page to map the dimension attributes to the attribute types that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to identify attributes for account dimensions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="34926-104">Opções</span><span class="sxs-lookup"><span data-stu-id="34926-104">Options</span></span>  
 <span data-ttu-id="34926-105">**Tipo de dimensão**</span><span class="sxs-lookup"><span data-stu-id="34926-105">**Dimension type**</span></span>  
 <span data-ttu-id="34926-106">Exibe o tipo de dimensão selecionado.</span><span class="sxs-lookup"><span data-stu-id="34926-106">Displays the selected dimension type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34926-107">Esta opção não está disponível porque a `Type` propriedade da dimensão não pode ser alterada para um valor diferente de *conta* para dimensões de conta.</span><span class="sxs-lookup"><span data-stu-id="34926-107">This option is not available because the `Type` property of the dimension cannot be changed to a value other than *Account* for account dimensions.</span></span>  
  
 <span data-ttu-id="34926-108">**Atributos de dimensão**</span><span class="sxs-lookup"><span data-stu-id="34926-108">**Dimension attributes**</span></span>  
 <span data-ttu-id="34926-109">Exibe os tipos de atributos válidos que podem ser mapeados para os atributos de dimensão existentes na dimensão.</span><span class="sxs-lookup"><span data-stu-id="34926-109">Displays the valid attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="34926-110">**Incluir**</span><span class="sxs-lookup"><span data-stu-id="34926-110">**Include**</span></span>  
 <span data-ttu-id="34926-111">Selecione uma caixa de seleção para incluir o tipo de atributo correspondente na dimensão.</span><span class="sxs-lookup"><span data-stu-id="34926-111">Select a check box to include the corresponding attribute type in the dimension.</span></span>  
  
 <span data-ttu-id="34926-112">**Tipo de Atributo**</span><span class="sxs-lookup"><span data-stu-id="34926-112">**Attribute Type**</span></span>  
 <span data-ttu-id="34926-113">Lista os tipos de atributos que podem ser mapeados para os atributos de dimensão existentes na dimensão.</span><span class="sxs-lookup"><span data-stu-id="34926-113">Lists the attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="34926-114">**Atributo de Dimensão**</span><span class="sxs-lookup"><span data-stu-id="34926-114">**Dimension Attribute**</span></span>  
 <span data-ttu-id="34926-115">Selecione o atributo de dimensão que deve ser mapeado para o tipo de atributo correspondente.</span><span class="sxs-lookup"><span data-stu-id="34926-115">Select the dimension attribute that should be mapped to the corresponding attribute type.</span></span>  
  
 <span data-ttu-id="34926-116">**Definir medidas como semiaditivas com base no tipo de conta**</span><span class="sxs-lookup"><span data-stu-id="34926-116">**Set measures to be semiadditive based on account type**</span></span>  
 <span data-ttu-id="34926-117">Selecione para alterar cada medida associada a essa dimensão a ser agregada por tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="34926-117">Select to change every measure associated with this dimension to be aggregated by account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34926-118">Essa opção não será exibida se o Assistente de Business Intelligence tiver sido iniciado no Designer de Dimensão ou clicando com o botão direito do mouse em uma dimensão no Gerenciador de Soluções no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34926-118">This option does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34926-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34926-119">See Also</span></span>  
 <span data-ttu-id="34926-120">[Ajuda F1 do assistente de Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="34926-120">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="34926-121">[O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="34926-121">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="34926-122">O designer de dimensão &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="34926-122">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
