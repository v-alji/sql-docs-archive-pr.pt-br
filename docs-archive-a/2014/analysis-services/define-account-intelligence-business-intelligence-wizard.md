---
title: Definir inteligência de conta (Assistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.mapaccounttype.f1
ms.assetid: fe4c204b-1031-4ac4-9916-8052ce2301cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17b8136e79097cd502d6b239ba6867c4e678c70f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679096"
---
# <a name="define-account-intelligence-business-intelligence-wizard"></a><span data-ttu-id="66134-102">Definir Inteligência de Conta (Assistente de Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="66134-102">Define Account Intelligence (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="66134-103">Use a página **Definir Inteligência de Conta** para mapear tipos de conta definidos na instância do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] como tipos de conta definidos por uma tabela de origem na fonte de dados que fornece os dados para a dimensão de conta.</span><span class="sxs-lookup"><span data-stu-id="66134-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined by a source table in the data source that supplies the data for the account dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66134-104"> Essa página será exibida se um atributo de dimensão tiver sido mapeado para o atributo **Tipo de Conta** na página **Configurar Atributos de Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="66134-104">This page will appear if a dimension attribute was mapped to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="66134-105">Opções</span><span class="sxs-lookup"><span data-stu-id="66134-105">Options</span></span>  
 <span data-ttu-id="66134-106">**Tipos de Conta de Tabela de Origem**</span><span class="sxs-lookup"><span data-stu-id="66134-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="66134-107">Exibe os valores contidos no atributo de dimensão atribuído ao atributo **Tipo de Conta** na página **Configurar Atributos de Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="66134-107">Displays the values that are contained in the dimension attribute assigned to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
 <span data-ttu-id="66134-108">**Tipos de Conta Interna**</span><span class="sxs-lookup"><span data-stu-id="66134-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="66134-109">Selecione o tipo de conta definido na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que mapeia para os tipos de conta na tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="66134-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="66134-110">A tabela a seguir lista os tipos de conta que estão definidos em uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66134-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="66134-111">Valor</span><span class="sxs-lookup"><span data-stu-id="66134-111">Value</span></span>|<span data-ttu-id="66134-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="66134-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="66134-113">**Ativo**</span><span class="sxs-lookup"><span data-stu-id="66134-113">**Asset**</span></span>|<span data-ttu-id="66134-114">Valor de itens possuídos em um momento específico.</span><span class="sxs-lookup"><span data-stu-id="66134-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="66134-115">**Saldo**</span><span class="sxs-lookup"><span data-stu-id="66134-115">**Balance**</span></span>|<span data-ttu-id="66134-116">Contagem de algo em um momento específico.</span><span class="sxs-lookup"><span data-stu-id="66134-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="66134-117">**Despesa**</span><span class="sxs-lookup"><span data-stu-id="66134-117">**Expense**</span></span>|<span data-ttu-id="66134-118">Valor de despesas efetuadas.</span><span class="sxs-lookup"><span data-stu-id="66134-118">Value of things spent.</span></span>|  
|<span data-ttu-id="66134-119">**Flow**</span><span class="sxs-lookup"><span data-stu-id="66134-119">**Flow**</span></span>|<span data-ttu-id="66134-120">Contagem incremental de itens.</span><span class="sxs-lookup"><span data-stu-id="66134-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="66134-121">**Líqui**</span><span class="sxs-lookup"><span data-stu-id="66134-121">**Income**</span></span>|<span data-ttu-id="66134-122">Valor de itens recebidos.</span><span class="sxs-lookup"><span data-stu-id="66134-122">Value of things received.</span></span>|  
|<span data-ttu-id="66134-123">**Dívida**</span><span class="sxs-lookup"><span data-stu-id="66134-123">**Liability**</span></span>|<span data-ttu-id="66134-124">Valor de itens devidos em um momento específico.</span><span class="sxs-lookup"><span data-stu-id="66134-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="66134-125">**Estatística**</span><span class="sxs-lookup"><span data-stu-id="66134-125">**Statistical**</span></span>|<span data-ttu-id="66134-126">Taxa calculada de algo ou contagem de algo que não agrega.</span><span class="sxs-lookup"><span data-stu-id="66134-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66134-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="66134-127">See Also</span></span>  
 <span data-ttu-id="66134-128">[Ajuda F1 do assistente de Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="66134-128">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="66134-129">[O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="66134-129">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="66134-130">O designer de dimensão &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="66134-130">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
