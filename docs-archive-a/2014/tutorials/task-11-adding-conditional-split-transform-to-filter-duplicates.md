---
title: 'Tarefa 11: adicionando transformação de divisão condicional para filtrar duplicatas | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3094bd57-5cf4-4860-bf51-fadd1b309f94
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e8370563c4275df0d0513d5434a8b16efba728d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685989"
---
# <a name="task-11-adding-conditional-split-transform-to-filter-duplicates"></a><span data-ttu-id="86096-102">Tarefa 11: Adicionando a Transformação Divisão Condicional para filtrar duplicatas</span><span class="sxs-lookup"><span data-stu-id="86096-102">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>
  <span data-ttu-id="86096-103">Nesta tarefa, você adiciona a Transformação Divisão Condicional ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="86096-103">In this task, you add the Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="86096-104">Essa transformação ajuda o ajuda a filtrar duplicatas do conjunto de registros de entrada.</span><span class="sxs-lookup"><span data-stu-id="86096-104">This transform helps you filter duplicates from the incoming record set.</span></span> <span data-ttu-id="86096-105">A transformação Grupo Difuso agrupa os registros que considera correspondências e escolhe um dos registros como registro dinâmico.</span><span class="sxs-lookup"><span data-stu-id="86096-105">The Fuzzy Group transform groups the records that it finds to be matches and picks one of the records as a pivot record.</span></span> <span data-ttu-id="86096-106">Todos os registros em um grupo têm o mesmo valor _key_out.</span><span class="sxs-lookup"><span data-stu-id="86096-106">All the records in a group have the same _key_out value.</span></span> <span data-ttu-id="86096-107">O registro dinâmico no grupo tem o valor _key_in igual ao valor _key_out.</span><span class="sxs-lookup"><span data-stu-id="86096-107">The pivot record in the group has _key_in same as the _key_out value.</span></span> <span data-ttu-id="86096-108">Os outros registros no grupo têm valores diferentes para _key_in e _key_out.</span><span class="sxs-lookup"><span data-stu-id="86096-108">The other records in the group have different values for _key_in and _key_out.</span></span> <span data-ttu-id="86096-109">Assim, quando você filtrar usando a condição _key_in==_key_out, receberá apenas a linha dinâmica no grupo.</span><span class="sxs-lookup"><span data-stu-id="86096-109">Therefore, when you filter using the condition _key_in==_key_out, you only get the pivot row in the group.</span></span>  
  
1.  <span data-ttu-id="86096-110">Arraste e solte a transformação de **divisão condicional** da seção **comum** na **caixa de ferramentas do SSIS** para a guia fluxo de **dados** .</span><span class="sxs-lookup"><span data-stu-id="86096-110">Drag-drop **Conditional Split** Transform from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="86096-111">Clique com o botão direito do mouse em **transformação de divisão condicional** na guia **fluxo de dados** e clique em **renomear**.</span><span class="sxs-lookup"><span data-stu-id="86096-111">Right-click **Conditional Split Transform** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="86096-112">Digite **duplicatas de filtro** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="86096-112">Type **Filter Duplicates** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="86096-113">Conecte os **fornecedores do grupo com as IDs correspondentes** para **Filtrar duplicatas**.</span><span class="sxs-lookup"><span data-stu-id="86096-113">Connect **Group Suppliers with Matching IDs** to **Filter Duplicates**.</span></span>  
  
4.  <span data-ttu-id="86096-114">Clique duas vezes em **Filtrar duplicatas** para iniciar a caixa de diálogo **Editor de transformação de divisão condicional** .</span><span class="sxs-lookup"><span data-stu-id="86096-114">Double-click **Filter Duplicates** to launch the **Conditional Split Transform Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="86096-115">Expanda **colunas** no painel superior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="86096-115">Expand **Columns** in the top-left pane.</span></span>  
  
6.  <span data-ttu-id="86096-116">Arraste e solte **_key_in** para a coluna **condição** .</span><span class="sxs-lookup"><span data-stu-id="86096-116">Drag-drop **_key_in** to the **Condition** column.</span></span>  
  
7.  <span data-ttu-id="86096-117">Digite = = (igual a) ao lado de **_key_in** e arrastar e soltar **_key_out**.</span><span class="sxs-lookup"><span data-stu-id="86096-117">Type == (equals to) next to **_key_in** and drag-drop **_key_out**.</span></span>  
  
8.  <span data-ttu-id="86096-118">Clique em **caso 1** na coluna **nome de saída** , digite **registros exclusivos**e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="86096-118">Click **Case 1** in the **Output Name** column, type **Unique Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="86096-119">![Editor de Transformação Divisão Condicional](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "Editor de Transformação Divisão Condicional")</span><span class="sxs-lookup"><span data-stu-id="86096-119">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "Conditional Split Transformation Editor")</span></span>  
  
9. <span data-ttu-id="86096-120">Clique em **OK** para fechar a caixa de diálogo **Editor de transformação Divisão condicional** .</span><span class="sxs-lookup"><span data-stu-id="86096-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="86096-121">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="86096-121">Next Step</span></span>  
 [<span data-ttu-id="86096-122">Tarefa 12: Adicionando a Transformação Coluna Derivada para adicionar as colunas necessárias pelo MDS</span><span class="sxs-lookup"><span data-stu-id="86096-122">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>](../../2014/tutorials/task-12-adding-derived-column-transform-to-add-columns-required-by-mds.md)  
  
  
