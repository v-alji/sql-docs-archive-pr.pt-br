---
title: Membros de dimensão deduzidos (Assistente para Dimensões de Alteração Lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.inferrdim.f1
ms.assetid: 809e395f-2e10-48ff-8860-56403f130628
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dda4345b91c69b134516baab2e5ba9b9990bd6af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582045"
---
# <a name="inferred-dimension-members-slowly-changing-dimension-wizard"></a><span data-ttu-id="047c2-102">Membros de Dimensão Deduzidos (Assistente para Dimensões de Alteração Lenta)</span><span class="sxs-lookup"><span data-stu-id="047c2-102">Inferred Dimension Members (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="047c2-103">Use a caixa de diálogo **Membros de Dimensão Deduzidos** para especificar opções para a utilização dos membros deduzidos.</span><span class="sxs-lookup"><span data-stu-id="047c2-103">Use the **Inferred Dimension Members** dialog box to specify options for using inferred members.</span></span> <span data-ttu-id="047c2-104">Membros deduzidos existem quando uma tabela de fatos faz referência a membros de dimensão que ainda não foram carregados.</span><span class="sxs-lookup"><span data-stu-id="047c2-104">Inferred members exist when a fact table references dimension members that are not yet loaded.</span></span> <span data-ttu-id="047c2-105">Quando os dados do membro deduzido são carregados, você pode atualizar o registro existente em vez de criar um novo.</span><span class="sxs-lookup"><span data-stu-id="047c2-105">When data for the inferred member is loaded, you can update the existing record rather than create a new one.</span></span>  
  
 <span data-ttu-id="047c2-106">Para obter mais informações sobre este assistente, consulte [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="047c2-106">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="047c2-107">Opções</span><span class="sxs-lookup"><span data-stu-id="047c2-107">Options</span></span>  
 <span data-ttu-id="047c2-108">**Habilitar suporte a membro deduzido**</span><span class="sxs-lookup"><span data-stu-id="047c2-108">**Enable inferred member support**</span></span>  
 <span data-ttu-id="047c2-109">Se optar por habilitar membros deduzidos, você deve selecionar uma das duas opções abaixo.</span><span class="sxs-lookup"><span data-stu-id="047c2-109">If you choose to enable inferred members, you must select one of the two options that follow.</span></span>  
  
 <span data-ttu-id="047c2-110">**Todas as colunas com um tipo de alteração são nulas**</span><span class="sxs-lookup"><span data-stu-id="047c2-110">**All columns with a change type are null**</span></span>  
 <span data-ttu-id="047c2-111">Especifique se deseja inserir valores nulos em todas as colunas com um tipo de alteração no novo registro de membro deduzido.</span><span class="sxs-lookup"><span data-stu-id="047c2-111">Specify whether to enter null values in all columns with a change type in the new inferred member record.</span></span>  
  
 <span data-ttu-id="047c2-112">**Use uma coluna Booleana para indicar se o registro atual é um membro deduzido**</span><span class="sxs-lookup"><span data-stu-id="047c2-112">**Use a Boolean column to indicate whether the current record is an inferred member**</span></span>  
 <span data-ttu-id="047c2-113">Especifique se deve ser usada uma coluna Booleana para indicar se o registro atual é um membro deduzido.</span><span class="sxs-lookup"><span data-stu-id="047c2-113">Specify whether to use an existing Boolean column to indicate whether the current record is an inferred member.</span></span>  
  
 <span data-ttu-id="047c2-114">**Indicador de membro deduzido**</span><span class="sxs-lookup"><span data-stu-id="047c2-114">**Inferred member indicator**</span></span>  
 <span data-ttu-id="047c2-115">Se você optou por usar uma coluna Booleana para indicar membros deduzidos como descrito acima, selecione a coluna na lista.</span><span class="sxs-lookup"><span data-stu-id="047c2-115">If you have chosen to use a Boolean column to indicate inferred members as described above, select the column from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047c2-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="047c2-116">See Also</span></span>  
 [<span data-ttu-id="047c2-117">Configurar saídas por meio do Assistente para Dimensões de Alteração Lenta</span><span class="sxs-lookup"><span data-stu-id="047c2-117">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
