---
title: Definir inteligência de conta (Assistente para dimensões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.accountintelligencetypemapping.f1
ms.assetid: cbcff072-3a7e-4e98-858f-1b4265461561
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90871e2299d1531db1b678b1f4b16ddd7f1db767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576056"
---
# <a name="define-account-intelligence-dimension-wizard"></a><span data-ttu-id="df305-102">Definir Inteligência de Conta (Assistente de Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="df305-102">Define Account Intelligence (Dimension Wizard)</span></span>
  <span data-ttu-id="df305-103">Use a página **Definir Inteligência de Conta** para mapear tipos de conta definidos na instância do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para tipos de conta definidos no atributo de dimensão associado ao atributo **Tipo de Conta** na dimensão.</span><span class="sxs-lookup"><span data-stu-id="df305-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined in the dimension attribute associated with the **Account Type** attribute type in the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df305-104"> Essa página é exibida apenas de você tiver selecionado **Dimensão padrão** na página **Selecionar o Tipo de Dimensão** e se tiver mapeado um atributo de dimensão para o tipo de atributo **Tipo de Conta** na página **Especificar Tipo de Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="df305-104">This page is displayed only if you selected **Standard dimension** on the **Select the Dimension Type** page and if you mapped a dimension attribute to the **Account Type** attribute type on the **Specify Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="df305-105">Opções</span><span class="sxs-lookup"><span data-stu-id="df305-105">Options</span></span>  
 <span data-ttu-id="df305-106">**Tipos de Conta de Tabela de Origem**</span><span class="sxs-lookup"><span data-stu-id="df305-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="df305-107">Exibe os valores contidos no atributo de dimensão atribuídos ao atributo **Tipo de Conta** na página **Especificar Chave e Tipo de Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="df305-107">Displays the values contained in the dimension attribute assigned to the **Account Type** attribute type in the **Specify Dimension Key and Type** page.</span></span>  
  
 <span data-ttu-id="df305-108">**Tipos de Conta Interna**</span><span class="sxs-lookup"><span data-stu-id="df305-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="df305-109">Selecione o tipo de conta definido na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que mapeia para os tipos de conta na tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="df305-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="df305-110">A tabela a seguir lista os tipos de conta que estão definidos em uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df305-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="df305-111">Valor</span><span class="sxs-lookup"><span data-stu-id="df305-111">Value</span></span>|<span data-ttu-id="df305-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="df305-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="df305-113">**Ativo**</span><span class="sxs-lookup"><span data-stu-id="df305-113">**Asset**</span></span>|<span data-ttu-id="df305-114">Valor de itens possuídos em um momento específico.</span><span class="sxs-lookup"><span data-stu-id="df305-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="df305-115">**Saldo**</span><span class="sxs-lookup"><span data-stu-id="df305-115">**Balance**</span></span>|<span data-ttu-id="df305-116">Contagem de algo em um momento específico.</span><span class="sxs-lookup"><span data-stu-id="df305-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="df305-117">**Despesa**</span><span class="sxs-lookup"><span data-stu-id="df305-117">**Expense**</span></span>|<span data-ttu-id="df305-118">Valor de despesas efetuadas.</span><span class="sxs-lookup"><span data-stu-id="df305-118">Value of things spent.</span></span>|  
|<span data-ttu-id="df305-119">**Flow**</span><span class="sxs-lookup"><span data-stu-id="df305-119">**Flow**</span></span>|<span data-ttu-id="df305-120">Contagem incremental de itens.</span><span class="sxs-lookup"><span data-stu-id="df305-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="df305-121">**Líqui**</span><span class="sxs-lookup"><span data-stu-id="df305-121">**Income**</span></span>|<span data-ttu-id="df305-122">Valor de itens recebidos.</span><span class="sxs-lookup"><span data-stu-id="df305-122">Value of things received.</span></span>|  
|<span data-ttu-id="df305-123">**Dívida**</span><span class="sxs-lookup"><span data-stu-id="df305-123">**Liability**</span></span>|<span data-ttu-id="df305-124">Valor de itens devidos em um momento específico.</span><span class="sxs-lookup"><span data-stu-id="df305-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="df305-125">**Estatística**</span><span class="sxs-lookup"><span data-stu-id="df305-125">**Statistical**</span></span>|<span data-ttu-id="df305-126">Taxa calculada de algo ou contagem de algo que não agrega.</span><span class="sxs-lookup"><span data-stu-id="df305-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df305-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="df305-127">See Also</span></span>  
 <span data-ttu-id="df305-128">[Ajuda F1 do assistente para dimensões](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="df305-128">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="df305-129">[Dimensões &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="df305-129">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="df305-130">Dimensões em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="df305-130">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
