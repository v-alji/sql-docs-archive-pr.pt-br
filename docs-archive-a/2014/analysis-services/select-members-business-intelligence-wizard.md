---
title: Selecionar Membros (Assistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.memberconversion.f1
ms.assetid: 1a147461-d594-41e7-a41d-09d2d003e1e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd5f184e0d9670725609531b6d0a101f8e7f8647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571631"
---
# <a name="select-members-business-intelligence-wizard"></a><span data-ttu-id="c99fb-102">Selecionar Membros (Assistente de Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="c99fb-102">Select Members (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="c99fb-103">Use a página **Selecionar Membros** para determinar a quais membros o Assistente de Business Intelligence deve aplicar a funcionalidade de conversão de moeda especificada na página **Definir Opções de Conversão de Moeda** .</span><span class="sxs-lookup"><span data-stu-id="c99fb-103">Use the **Select Members** page to determine to which members the Business Intelligence Wizard should apply the currency conversion functionality specified on the **Set Currency Conversion Options** page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c99fb-104">Essa página não será exibida se o Assistente de Business Intelligence tiver sido iniciado no Designer de Dimensão ou clicando com o botão direito do mouse em uma dimensão no Gerenciador de Soluções no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c99fb-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="c99fb-105">Opções</span><span class="sxs-lookup"><span data-stu-id="c99fb-105">Options</span></span>  
 <span data-ttu-id="c99fb-106">**Dimensão de medidas**</span><span class="sxs-lookup"><span data-stu-id="c99fb-106">**Measures dimension**</span></span>  
 <span data-ttu-id="c99fb-107">Selecione para aplicar a funcionalidade de conversão de moeda a uma ou mais medidas no cubo.</span><span class="sxs-lookup"><span data-stu-id="c99fb-107">Select to apply the currency conversion functionality to one or more measures in the cube.</span></span>  
  
 <span data-ttu-id="c99fb-108">Se selecionada, a grade exibirá as opções listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c99fb-108">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="c99fb-109">Opção</span><span class="sxs-lookup"><span data-stu-id="c99fb-109">Option</span></span>|<span data-ttu-id="c99fb-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="c99fb-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c99fb-111">**Tipos de Medidas Internas**</span><span class="sxs-lookup"><span data-stu-id="c99fb-111">**Built-in Measure Types**</span></span>|<span data-ttu-id="c99fb-112">Selecione para incluir funcionalidade de conversão de moeda para a medida especificada.</span><span class="sxs-lookup"><span data-stu-id="c99fb-112">Select to include currency conversion functionality for the specified measure.</span></span>|  
|<span data-ttu-id="c99fb-113">**Determina**</span><span class="sxs-lookup"><span data-stu-id="c99fb-113">**Measures**</span></span>|<span data-ttu-id="c99fb-114">Selecione a medida do grupo de medidas de taxa que contém a taxa de câmbio a ser usada ao converter a medida selecionada em **Tipos de Medidas Internas** .</span><span class="sxs-lookup"><span data-stu-id="c99fb-114">Select the measure from the rate measure group that contains the exchange rate to use when the measure selected in **Built-in Measure Types** is converted.</span></span>|  
  
 <span data-ttu-id="c99fb-115">**Hierarquia de contas**</span><span class="sxs-lookup"><span data-stu-id="c99fb-115">**Account hierarchy**</span></span>  
 <span data-ttu-id="c99fb-116">Selecione para aplicar a funcionalidade de conversão de moeda a um ou mais membros da hierarquia de contas da dimensão de conta incluída no cubo.</span><span class="sxs-lookup"><span data-stu-id="c99fb-116">Select to apply the currency conversion functionality to one or more members in the account hierarchy of the account dimension included in the cube.</span></span> <span data-ttu-id="c99fb-117">A hierarquia de conta é a hierarquia dentro da dimensão de conta cuja `Type` propriedade está definida como *conta*.</span><span class="sxs-lookup"><span data-stu-id="c99fb-117">The account hierarchy is the hierarchy within the account dimension whose `Type` property is set to *Account*.</span></span>  
  
 <span data-ttu-id="c99fb-118">Se selecionada, a grade exibirá as opções listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c99fb-118">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="c99fb-119">Opção</span><span class="sxs-lookup"><span data-stu-id="c99fb-119">Option</span></span>|<span data-ttu-id="c99fb-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="c99fb-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c99fb-121">**Membro da Conta**</span><span class="sxs-lookup"><span data-stu-id="c99fb-121">**Account Member**</span></span>|<span data-ttu-id="c99fb-122">Selecione para incluir funcionalidade de conversão de moeda para o membro especificado da hierarquia de contas.</span><span class="sxs-lookup"><span data-stu-id="c99fb-122">Select to include currency conversion functionality for the specified member of the account hierarchy.</span></span>|  
|<span data-ttu-id="c99fb-123">**Determina**</span><span class="sxs-lookup"><span data-stu-id="c99fb-123">**Measures**</span></span>|<span data-ttu-id="c99fb-124">Selecione a medida do grupo de medidas de taxa que contém a taxa de câmbio a ser usada quando as medidas do membro selecionado em **Membro da Conta** forem convertidas.</span><span class="sxs-lookup"><span data-stu-id="c99fb-124">Select the measure from the rate measure group that contains the exchange rate to use when the measures for the member selected in **Account Member** are converted.</span></span>|  
  
 <span data-ttu-id="c99fb-125">**Hierarquia de contas baseada no tipo**</span><span class="sxs-lookup"><span data-stu-id="c99fb-125">**Account hierarchy based on type**</span></span>  
 <span data-ttu-id="c99fb-126">Selecione para aplicar a funcionalidade de conversão de moeda a todos os membros de atributos na hierarquia de contas cuja propriedade `Type` está definida como um tipo de conta especificado.</span><span class="sxs-lookup"><span data-stu-id="c99fb-126">Select to apply the currency conversion functionality to all members of attributes in the account hierarchy whose `Type` property is set to a specified account type.</span></span>  
  
 <span data-ttu-id="c99fb-127">Se selecionada, a grade exibirá as opções listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c99fb-127">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="c99fb-128">Opção</span><span class="sxs-lookup"><span data-stu-id="c99fb-128">Option</span></span>|<span data-ttu-id="c99fb-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="c99fb-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c99fb-130">**Tipo de conta**</span><span class="sxs-lookup"><span data-stu-id="c99fb-130">**Account Type**</span></span>|<span data-ttu-id="c99fb-131">Selecione para incluir funcionalidade de conversão de moeda para o tipo de conta especificado.</span><span class="sxs-lookup"><span data-stu-id="c99fb-131">Select to include currency conversion functionality for the specified account type.</span></span>|  
|<span data-ttu-id="c99fb-132">**Determina**</span><span class="sxs-lookup"><span data-stu-id="c99fb-132">**Measures**</span></span>|<span data-ttu-id="c99fb-133">Selecione a medida do grupo de medidas de taxa que contém a taxa de câmbio a ser usada ao converter medidas para os membros de atributos usando o tipo de conta selecionado em **Tipo de Conta** .</span><span class="sxs-lookup"><span data-stu-id="c99fb-133">Select the measure from the rate measure group that contains the exchange rate to use when measures for the members of attributes using the account type selected in **Account Type** are converted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c99fb-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c99fb-134">See Also</span></span>  
 <span data-ttu-id="c99fb-135">[Ajuda F1 do assistente de Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="c99fb-135">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="c99fb-136">[O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="c99fb-136">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="c99fb-137">O designer de dimensão &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="c99fb-137">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
