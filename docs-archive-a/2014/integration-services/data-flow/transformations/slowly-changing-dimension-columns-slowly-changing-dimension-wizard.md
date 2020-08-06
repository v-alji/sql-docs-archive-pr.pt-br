---
title: Colunas da Dimensão de Alteração Lenta (Assistente para Dimensões de Alteração Lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.scdsupport.f1
ms.assetid: 36de99d5-5368-48e0-b876-17e9c6862c6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6283887cbddb9844e0ac769281184f588dc2a94d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678870"
---
# <a name="slowly-changing-dimension-columns-slowly-changing-dimension-wizard"></a><span data-ttu-id="c25f9-102">Colunas da Dimensão de Alteração Lenta (Assistente para Dimensões de Alteração Lenta)</span><span class="sxs-lookup"><span data-stu-id="c25f9-102">Slowly Changing Dimension Columns (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="c25f9-103">Use a caixa de diálogo **Colunas de Dimensão de Alteração Lenta** para selecionar um tipo de alteração para cada coluna de dimensão de alteração lenta.</span><span class="sxs-lookup"><span data-stu-id="c25f9-103">Use the **Slowly Changing Dimensions Columns** dialog box to select a change type for each slowly changing dimension column.</span></span>  
  
 <span data-ttu-id="c25f9-104">Para obter mais informações sobre este assistente, consulte [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c25f9-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c25f9-105">Opções</span><span class="sxs-lookup"><span data-stu-id="c25f9-105">Options</span></span>  
 <span data-ttu-id="c25f9-106">**Colunas de Dimensão**</span><span class="sxs-lookup"><span data-stu-id="c25f9-106">**Dimension Columns**</span></span>  
 <span data-ttu-id="c25f9-107">Selecione uma coluna de dimensão na lista.</span><span class="sxs-lookup"><span data-stu-id="c25f9-107">Select a dimension column from the list.</span></span>  
  
 <span data-ttu-id="c25f9-108">**Alterar Tipo**</span><span class="sxs-lookup"><span data-stu-id="c25f9-108">**Change Type**</span></span>  
 <span data-ttu-id="c25f9-109">Selecione um **Atributo Fixo**ou um dos dois tipos de atributos de alteração.</span><span class="sxs-lookup"><span data-stu-id="c25f9-109">Select a **Fixed Attribute**, or select one of the two types of changing attributes.</span></span> <span data-ttu-id="c25f9-110">Use **Atributo Fixo** caso o valor em uma coluna não deva ser alterado; assim o [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] tratará as alterações como erros.</span><span class="sxs-lookup"><span data-stu-id="c25f9-110">Use **Fixed Attribute** when the value in a column should not change; [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] then treats changes as errors.</span></span> <span data-ttu-id="c25f9-111">Use **Atributo de alteração** para substituir os valores existentes por com valores alterados.</span><span class="sxs-lookup"><span data-stu-id="c25f9-111">Use **Changing Attribute** to overwrite existing values with changed values.</span></span> <span data-ttu-id="c25f9-112">Use **Atributo Histórico** para salvar valores alterados em novos registros, marcando os registros anteriores como desatualizados.</span><span class="sxs-lookup"><span data-stu-id="c25f9-112">Use **Historical Attribute** to save changed values in new records, while marking previous records as outdated.</span></span>  
  
 <span data-ttu-id="c25f9-113">**Remover**</span><span class="sxs-lookup"><span data-stu-id="c25f9-113">**Remove**</span></span>  
 <span data-ttu-id="c25f9-114">Selecione uma coluna de dimensão e a remova da lista de colunas mapeadas clicando em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c25f9-114">Select a dimension column, and remove it from the list of mapped columns by clicking **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c25f9-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c25f9-115">See Also</span></span>  
 [<span data-ttu-id="c25f9-116">Configurar saídas por meio do Assistente para Dimensões de Alteração Lenta</span><span class="sxs-lookup"><span data-stu-id="c25f9-116">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
