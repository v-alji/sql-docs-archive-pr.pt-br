---
title: Opções de Atributo Histórico (Assistente para Dimensões de Alteração Lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.histattriboption.f1
ms.assetid: a176ec66-ec39-4c99-99d1-c1afa8450e1e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fad005d6b8f80973abeb47dd881ef02b669d7b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582055"
---
# <a name="historical-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="b30e5-102">Opções de Atributo Histórico (Assistente para Dimensões de Alteração Lenta)</span><span class="sxs-lookup"><span data-stu-id="b30e5-102">Historical Attribute Options (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="b30e5-103">Use a caixa de diálogo **Opções de Atributo Histórico** para mostrar atributos históricos por datas de início e de término ou para registrar atributos históricos em uma coluna criada especialmente para este propósito.</span><span class="sxs-lookup"><span data-stu-id="b30e5-103">Use the **Historical Attributes Options** dialog box to show historical attributes by start and end dates, or to record historical attributes in a column specially created for this purpose.</span></span>  
  
 <span data-ttu-id="b30e5-104">Para obter mais informações sobre este assistente, consulte [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="b30e5-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b30e5-105">Opções</span><span class="sxs-lookup"><span data-stu-id="b30e5-105">Options</span></span>  
 <span data-ttu-id="b30e5-106">**Use uma única coluna para mostrar os registros atual e expirado**</span><span class="sxs-lookup"><span data-stu-id="b30e5-106">**Use a single column to show current and expired records**</span></span>  
 <span data-ttu-id="b30e5-107">Se você optar por usar uma única coluna para registrar o status de atributos históricos, estarão disponíveis as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b30e5-107">If you choose to use a single column to record the status of historical attributes, the following options are available:</span></span>  
  
|<span data-ttu-id="b30e5-108">Opção</span><span class="sxs-lookup"><span data-stu-id="b30e5-108">Option</span></span>|<span data-ttu-id="b30e5-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b30e5-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b30e5-110">**Coluna para indicar o registro atual**</span><span class="sxs-lookup"><span data-stu-id="b30e5-110">**Column to indicate current record**</span></span>|<span data-ttu-id="b30e5-111">Selecione uma coluna na qual indicar o registro atual.</span><span class="sxs-lookup"><span data-stu-id="b30e5-111">Select a column in which to indicate the current record.</span></span>|  
|<span data-ttu-id="b30e5-112">**Valor atual**</span><span class="sxs-lookup"><span data-stu-id="b30e5-112">**Value when current**</span></span>|<span data-ttu-id="b30e5-113">Use **Verdadeiro** ou **Atual** para mostrar se o registro é atual.</span><span class="sxs-lookup"><span data-stu-id="b30e5-113">Use either **True** or **Current** to show whether the record is current.</span></span>|  
|<span data-ttu-id="b30e5-114">**Valor de expiração**</span><span class="sxs-lookup"><span data-stu-id="b30e5-114">**Expiration value**</span></span>|<span data-ttu-id="b30e5-115">Use **Falso** ou **Expirado** para mostrar se o registro é um valor histórico.</span><span class="sxs-lookup"><span data-stu-id="b30e5-115">Use either **False** or **Expired** to show whether the record is a historical value.</span></span>|  
  
 <span data-ttu-id="b30e5-116">**Use as datas de início e de término para identificar os registros atual e expirado**</span><span class="sxs-lookup"><span data-stu-id="b30e5-116">**Use start and end dates to identify current and expired records**</span></span>  
 <span data-ttu-id="b30e5-117">A tabela de dimensão desta opção deve incluir uma coluna de data.</span><span class="sxs-lookup"><span data-stu-id="b30e5-117">The dimension table for this option must include a date column.</span></span> <span data-ttu-id="b30e5-118">Se você optar por mostrar atributos históricos por datas de início e de término, estarão disponíveis as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b30e5-118">If you choose to show historical attributes by start and end dates, the following options are available:</span></span>  
  
|<span data-ttu-id="b30e5-119">Opção</span><span class="sxs-lookup"><span data-stu-id="b30e5-119">Option</span></span>|<span data-ttu-id="b30e5-120">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b30e5-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b30e5-121">**Coluna da data de início**</span><span class="sxs-lookup"><span data-stu-id="b30e5-121">**Start date column**</span></span>|<span data-ttu-id="b30e5-122">Selecione a coluna na tabela de dimensões que conterá a data de início.</span><span class="sxs-lookup"><span data-stu-id="b30e5-122">Select the column in the dimension table to contain the start date.</span></span>|  
|<span data-ttu-id="b30e5-123">**Coluna da data de término**</span><span class="sxs-lookup"><span data-stu-id="b30e5-123">**End date column**</span></span>|<span data-ttu-id="b30e5-124">Selecione a coluna na tabela de dimensões que conterá a data de término.</span><span class="sxs-lookup"><span data-stu-id="b30e5-124">Select the column in the dimension table to contain the end date.</span></span>|  
|<span data-ttu-id="b30e5-125">**Variável para definir valores de data**</span><span class="sxs-lookup"><span data-stu-id="b30e5-125">**Variable to set date values**</span></span>|<span data-ttu-id="b30e5-126">Selecione uma variável de data na lista.</span><span class="sxs-lookup"><span data-stu-id="b30e5-126">Select a date variable from the list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b30e5-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b30e5-127">See Also</span></span>  
 [<span data-ttu-id="b30e5-128">Configurar saídas por meio do Assistente para Dimensões de Alteração Lenta</span><span class="sxs-lookup"><span data-stu-id="b30e5-128">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
