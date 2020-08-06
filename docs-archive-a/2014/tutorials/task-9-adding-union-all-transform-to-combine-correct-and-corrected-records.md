---
title: 'Tarefa 9: adicionando a transformação unir tudo para combinar registros corretos e corrigidos | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 24ba466d-a7d3-49e7-9111-b348399c9e58
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 83afb5ea9367660048fe36d00ab59d808da17b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685987"
---
# <a name="task-9-adding-union-all-transform-to-combine-correct-and-corrected-records"></a><span data-ttu-id="81cbe-102">Tarefa 9: Adicionando a Transformação Unir Tudo para combinar registros corretos e corrigidos</span><span class="sxs-lookup"><span data-stu-id="81cbe-102">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>
  <span data-ttu-id="81cbe-103">Nesta tarefa, você adiciona a Transformação Unir Tudo ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="81cbe-103">In this task, you add the Union All Transform to the data flow.</span></span> <span data-ttu-id="81cbe-104">A transformação Union All combina várias entradas em apenas uma saída.</span><span class="sxs-lookup"><span data-stu-id="81cbe-104">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="81cbe-105">No cenário, isso combina registros Corretos e Corrigidos em um fluxo.</span><span class="sxs-lookup"><span data-stu-id="81cbe-105">In your scenario, it combine both Correct and Corrected records into one stream.</span></span>  
  
1.  <span data-ttu-id="81cbe-106">Arraste e solte **unir todas as** transformações da seção **comum** da **caixa de ferramentas do SSIS** para a guia fluxo de **dados** e coloque-as em **escolher os registros corretos e corrigidos**.</span><span class="sxs-lookup"><span data-stu-id="81cbe-106">Drag-drop **Union All** Transform from **Common** section of the **SSIS Toolbox** to the **Data Flow** tab and place it under **Pick Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="81cbe-107">Clique com o botão direito do mouse em **Union All** Transform na guia **fluxo de dados** e clique em **renomear**.</span><span class="sxs-lookup"><span data-stu-id="81cbe-107">Right-click **Union All** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="81cbe-108">Digite **combinar registros corretos e corrigidos**e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="81cbe-108">Type **Combine Correct and Corrected Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="81cbe-109">![Combinar Registros Corretos e Corrigidos](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Combinar Registros Corretos e Corrigidos")</span><span class="sxs-lookup"><span data-stu-id="81cbe-109">![Combine Correct and Corrected Reocrds](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Combine Correct and Corrected Reocrds")</span></span>  
  
3.  <span data-ttu-id="81cbe-110">Conectar **selecione registros corretos e corrigidos** para **combinar os registros corretos e corrigidos** na guia **fluxo de dados** usando o conector azul.</span><span class="sxs-lookup"><span data-stu-id="81cbe-110">Connect **Pick Correct and Corrected Records** to **Combine Correct and Corrected Records** in the **Data Flow** tab by using the blue connector.</span></span> <span data-ttu-id="81cbe-111">Você deverá ver a caixa de diálogo **seleção de saída de entrada** .</span><span class="sxs-lookup"><span data-stu-id="81cbe-111">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="81cbe-112">Na caixa de diálogo **saída de entrada** , selecione **corrigir** para **saída** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="81cbe-112">In the **Input Output** dialog box, select **Correct** for **Output** and click **OK**.</span></span>  
  
     <span data-ttu-id="81cbe-113">![Caixa de diálogo Seleção de Saída e Entrada](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Caixa de diálogo Seleção de Saída e Entrada")</span><span class="sxs-lookup"><span data-stu-id="81cbe-113">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="81cbe-114">Mova o conector intitulado **correto** para a esquerda arrastando e soltando o ponto no final do conector para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="81cbe-114">Move the connector titled **Correct** to the left by dragging and dropping the dot at the end of the connector to left.</span></span>  
  
     <span data-ttu-id="81cbe-115">![Conectar Corrigir a Combinar Corretos e Corrigidos](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Conectar Corrigir a Combinar Corretos e Corrigidos")</span><span class="sxs-lookup"><span data-stu-id="81cbe-115">![Connect Correct to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Connect Correct to Combine Correct and Corrected")</span></span>  
  
6.  <span data-ttu-id="81cbe-116">Se você selecionar **escolher correção de registros corretos e corrigidos** , você verá outro conector azul.</span><span class="sxs-lookup"><span data-stu-id="81cbe-116">If you select **Pick Correct and Corrected Records** transform, you should see another blue connector.</span></span> <span data-ttu-id="81cbe-117">Arraste esse conector azul para **combinar os registros corretos e corrigidos**.</span><span class="sxs-lookup"><span data-stu-id="81cbe-117">Drag that blue connector to **Combine Correct and Corrected Records**.</span></span>  
  
     <span data-ttu-id="81cbe-118">![Conectar Corrigido a Combinar Corretos e Corrigidos](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Conectar Corrigido a Combinar Corretos e Corrigidos")</span><span class="sxs-lookup"><span data-stu-id="81cbe-118">![Connect Corrected to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Connect Corrected to Combine Correct and Corrected")</span></span>  
  
7.  <span data-ttu-id="81cbe-119">Esse **conector** deve ter o título **corrigido**.</span><span class="sxs-lookup"><span data-stu-id="81cbe-119">This **connector** should be titled **Corrected**.</span></span> <span data-ttu-id="81cbe-120">Como você tem apenas duas condições **corretas** e **corrigidas**, e uma condição já foi usada, a caixa de diálogo de **seleção de saída de entrada** não é exibida desta vez.</span><span class="sxs-lookup"><span data-stu-id="81cbe-120">Since you have only two conditions **Correct** and **Corrected**, and one condition was already used, the **Input Output Selection** dialog box is not displayed this time.</span></span> <span data-ttu-id="81cbe-121">Se os conectores se sobrepuserem, mova um deles para esquerda e o outro para direita arrastando o conector para a esquerda ou direita.</span><span class="sxs-lookup"><span data-stu-id="81cbe-121">If the connectors overlap, move one to left and the other one to right by dragging the connector to left or right.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="81cbe-122">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="81cbe-122">Next Step</span></span>  
 [<span data-ttu-id="81cbe-123">Tarefa 10: Adicionando a Transformação Grupo Difuso para identificar duplicatas</span><span class="sxs-lookup"><span data-stu-id="81cbe-123">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>](../../2014/tutorials/task-10-adding-fuzzy-group-transform-to-identify-duplicates.md)  
  
  
