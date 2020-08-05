---
title: Opções de Atributo Fixo e de Alteração (Assistente para Dimensões de Alteração Lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.attriboption.f1
ms.assetid: c841345c-7d03-452f-9379-1c8c464f029c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df654cd97b343179828ebd94dea40eacc90e003d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570780"
---
# <a name="fixed-and-changing-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="ea0db-102">Opções de Atributo Fixo e de Alteração (Assistente para Dimensões de Alteração Lenta)</span><span class="sxs-lookup"><span data-stu-id="ea0db-102">Fixed and Changing Attribute Options (Slowly Changing Dimension Wizard</span></span>
  <span data-ttu-id="ea0db-103">Use a caixa de diálogo **Opções de Atributo Fixo e de Alteração** para especificar como responder a mudanças nos atributos fixos e de alteração.</span><span class="sxs-lookup"><span data-stu-id="ea0db-103">Use the **Fixed and Changing Attribute Options** dialog box to specify how to respond to changes in fixed and changing attributes.</span></span>  
  
 <span data-ttu-id="ea0db-104">Para obter mais informações sobre este assistente, consulte [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="ea0db-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ea0db-105">Opções</span><span class="sxs-lookup"><span data-stu-id="ea0db-105">Options</span></span>  
 <span data-ttu-id="ea0db-106">**Atributos fixos**</span><span class="sxs-lookup"><span data-stu-id="ea0db-106">**Fixed attributes**</span></span>  
 <span data-ttu-id="ea0db-107">Para os atributos fixos, indique se a tarefa falhará se uma mudança for detectada em um atributo fixo.</span><span class="sxs-lookup"><span data-stu-id="ea0db-107">For fixed attributes, indicate whether the task should fail if a change is detected in a fixed attribute.</span></span>  
  
 <span data-ttu-id="ea0db-108">**Atributos de alteração**</span><span class="sxs-lookup"><span data-stu-id="ea0db-108">**Changing attributes**</span></span>  
 <span data-ttu-id="ea0db-109">Para alterar atributos, indique se a tarefa alterará registros antigos ou expirados, além de registros atuais, quando uma mudança for detectada em um atributo de alteração.</span><span class="sxs-lookup"><span data-stu-id="ea0db-109">For changing attributes, indicate whether the task should change outdated or expired records, in addition to current records, when a change is detected in a changing attribute.</span></span> <span data-ttu-id="ea0db-110">Um registro expirado é um registro que foi substituído por um registro mais novo por uma alteração em um atributo histórico (uma alteração Tipo 2).</span><span class="sxs-lookup"><span data-stu-id="ea0db-110">An expired record is a record that has been replaced with a newer record by a change in a historical attribute (a Type 2 change).</span></span> <span data-ttu-id="ea0db-111">A seleção desta opção pode impor requisitos de processamento adicionais em um objeto multidimensional construído no data warehouse relacional.</span><span class="sxs-lookup"><span data-stu-id="ea0db-111">Selecting this option may impose additional processing requirements on a multidimensional object constructed on the relational data warehouse.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea0db-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ea0db-112">See Also</span></span>  
 [<span data-ttu-id="ea0db-113">Configurar saídas por meio do Assistente para Dimensões de Alteração Lenta</span><span class="sxs-lookup"><span data-stu-id="ea0db-113">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
