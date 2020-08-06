---
title: 'Tarefa 5: Configurando relações baseadas em termos | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6569d512-637d-4f7b-82e1-1e8582278b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1589ec5843053baa6c42a0b9b0dec019c887da9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683171"
---
# <a name="task-5-setting-term-based-relationships"></a><span data-ttu-id="382be-102">Tarefa 5: Definindo relações baseadas em termos</span><span class="sxs-lookup"><span data-stu-id="382be-102">Task 5: Setting Term Based Relationships</span></span>
  <span data-ttu-id="382be-103">Nesta tarefa, você define algumas relações baseadas em termos para valores para o domínio **nome do fornecedor** .</span><span class="sxs-lookup"><span data-stu-id="382be-103">In this task, you define a few term-based relations for values for the **Supplier Name** domain.</span></span> <span data-ttu-id="382be-104">Uma relação baseada em termos permite que você faça uma correção em um termo que faz parte de um valor em um domínio.</span><span class="sxs-lookup"><span data-stu-id="382be-104">A term-based relation enables you to make a correction to a term that is part of a value in a domain.</span></span> <span data-ttu-id="382be-105">Elas permitem que diversos valores idênticos, exceto pela ortografia de uma parte comum deles, sejam considerados como sinônimos idênticos.</span><span class="sxs-lookup"><span data-stu-id="382be-105">It enables multiple values that are identical except for the spelling of a common part of them to be considered identical synonyms.</span></span> <span data-ttu-id="382be-106">Por exemplo, **Inc.** pode ser corrigido para **incorporado**.</span><span class="sxs-lookup"><span data-stu-id="382be-106">For example, **Inc.** can be corrected to **Incorporated**.</span></span> <span data-ttu-id="382be-107">O DQS usa essas relações nos processos de descoberta de conhecimento, limpeza ou correspondência.</span><span class="sxs-lookup"><span data-stu-id="382be-107">DQS uses these relations in the knowledge discovery, cleansing, or matching processes.</span></span> <span data-ttu-id="382be-108">Consulte [criar relações baseadas em termos](https://msdn.microsoft.com/library/hh510404.aspx) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="382be-108">See [Create Term-based Relations](https://msdn.microsoft.com/library/hh510404.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="382be-109">Selecione **nome do fornecedor** na **lista de domínios**.</span><span class="sxs-lookup"><span data-stu-id="382be-109">Select **Supplier Name** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="382be-110">Alterne para a guia **relações baseadas em termos** no painel direito.</span><span class="sxs-lookup"><span data-stu-id="382be-110">Switch to the **Term-Based Relationships** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="382be-111">Clique no botão **Adicionar nova relação** na barra de ferramentas para adicionar uma relação à tabela.</span><span class="sxs-lookup"><span data-stu-id="382be-111">Click **Add new relation** button on the toolbar to add a relation to the table.</span></span>  
  
4.  <span data-ttu-id="382be-112">Digite **co.** para o campo de **valor** e a **empresa** para o campo **corrigir para** .</span><span class="sxs-lookup"><span data-stu-id="382be-112">Type **Co.** for the **Value** field and **Company** for the **Correct To** field.</span></span>  
  
5.  <span data-ttu-id="382be-113">Repita as duas etapas anteriores para os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="382be-113">Repeat the previous two steps for the following values:</span></span>  
  
    |<span data-ttu-id="382be-114">Valor</span><span class="sxs-lookup"><span data-stu-id="382be-114">Value</span></span>|<span data-ttu-id="382be-115">Corrigir para</span><span class="sxs-lookup"><span data-stu-id="382be-115">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="382be-116">Corp.</span><span class="sxs-lookup"><span data-stu-id="382be-116">Corp.</span></span>|<span data-ttu-id="382be-117">Corporation</span><span class="sxs-lookup"><span data-stu-id="382be-117">Corporation</span></span>|  
    |<span data-ttu-id="382be-118">Inc.</span><span class="sxs-lookup"><span data-stu-id="382be-118">Inc.</span></span>|<span data-ttu-id="382be-119">Incorporated</span><span class="sxs-lookup"><span data-stu-id="382be-119">Incorporated</span></span>|  
  
     <span data-ttu-id="382be-120">![Relações baseadas em termos](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Relações baseadas em termos")</span><span class="sxs-lookup"><span data-stu-id="382be-120">![Term Based Relations](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Term Based Relations")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="382be-121">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="382be-121">Next Step</span></span>  
 [<span data-ttu-id="382be-122">Tarefa 6: Definindo sinônimos</span><span class="sxs-lookup"><span data-stu-id="382be-122">Task 6: Setting Synonyms</span></span>](../../2014/tutorials/task-6-setting-synonyms.md)  
  
  
