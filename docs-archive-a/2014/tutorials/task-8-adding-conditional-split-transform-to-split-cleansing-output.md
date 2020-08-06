---
title: 'Tarefa 8: adicionando transformação de divisão condicional à saída de limpeza de divisão | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d4ebe420-a4a9-4076-89d3-41abe726fc5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9be7ea6f5330382ad0417df99e18bcba5b59a4e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568934"
---
# <a name="task-8-adding-conditional-split-transform-to-split-cleansing-output"></a><span data-ttu-id="b44dc-102">Tarefa 8: Adicionando a Transformação Divisão Condicional para dividir a saída da limpeza</span><span class="sxs-lookup"><span data-stu-id="b44dc-102">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>
  <span data-ttu-id="b44dc-103">Nesta transformação, você adiciona uma Transformação Divisão Condicional ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="b44dc-103">In this transform, you add a Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="b44dc-104">A transformação Divisão Condicional pode rotear linhas para saídas diferentes com base no conteúdo dos dados.</span><span class="sxs-lookup"><span data-stu-id="b44dc-104">The Conditional Split transformation can route rows to different outputs based on the content of the data.</span></span> <span data-ttu-id="b44dc-105">Para este tutorial, você usa a coluna saída de **status do registro** da transformação limpeza DQS.</span><span class="sxs-lookup"><span data-stu-id="b44dc-105">For this tutorial, you use the **Record Status** output column from the DQS Cleansing transform.</span></span> <span data-ttu-id="b44dc-106">Apenas os registros corretos ou corrigidos serão carregados no servidor MDS neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="b44dc-106">You will upload only correct or corrected records to MDS server in this tutorial.</span></span> <span data-ttu-id="b44dc-107">Portanto, você verifica se o **status do registro** está **correto** ou **corrigido**e combina os registros antes de carregar os registros para o MDS.</span><span class="sxs-lookup"><span data-stu-id="b44dc-107">Therefore you check if the **Record Status** is **Correct** or **Corrected**, and combine the records before uploading the records to MDS.</span></span>  
  
1.  <span data-ttu-id="b44dc-108">Arraste e solte **a transformação de divisão condicional** da seção **comum** na caixa de **Ferramentas do SSIS** para a guia fluxo de **dados** em **limpar dados do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="b44dc-108">Drag-drop **Conditional Split Transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab under **Cleanse Supplier Data**.</span></span>  
  
2.  <span data-ttu-id="b44dc-109">Clique com o botão direito do mouse em **divisão condicional**e clique em **renomear**.</span><span class="sxs-lookup"><span data-stu-id="b44dc-109">Right-click **Conditional Split**, and click **Rename**.</span></span> <span data-ttu-id="b44dc-110">Digite **escolher os registros corretos e corrigidos** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="b44dc-110">Type **Pick Correct and Corrected Records** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="b44dc-111">Conecte os **dados do fornecedor de limpeza** e escolha os **registros corretos e corrigidos** usando o conector azul.</span><span class="sxs-lookup"><span data-stu-id="b44dc-111">Connect **Cleanse Supplier Data** and **Pick Correct and Corrected Records** using the blue connector.</span></span>  
  
     <span data-ttu-id="b44dc-112">![Limpar dados do fornecedor-> escolha corrigir & corrigido](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Limpar Dados de Fornecedor -> Escolher Correto & Corrigido")</span><span class="sxs-lookup"><span data-stu-id="b44dc-112">![Cleanse Supplier Data -> Pick Correct & Corrected](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Cleanse Supplier Data -> Pick Correct & Corrected")</span></span>  
  
4.  <span data-ttu-id="b44dc-113">Clique duas vezes em **escolher os registros corretos e corrigidos** na guia **fluxo de dados** .</span><span class="sxs-lookup"><span data-stu-id="b44dc-113">Double-click **Pick Correct and Corrected Records** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="b44dc-114">Altere o **nome de saída padrão** na parte inferior da tela para **corrigir**.</span><span class="sxs-lookup"><span data-stu-id="b44dc-114">Change the **Default Output Name** at the bottom of the screen to **Correct**.</span></span>  
  
6.  <span data-ttu-id="b44dc-115">Expanda **colunas** no **painel superior esquerdo**.</span><span class="sxs-lookup"><span data-stu-id="b44dc-115">Expand **Columns** in the **top-left pane**.</span></span>  
  
     <span data-ttu-id="b44dc-116">![Editor de Transformação Divisão Condicional](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "Editor de Transformação Divisão Condicional")</span><span class="sxs-lookup"><span data-stu-id="b44dc-116">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "Conditional Split Transformation Editor")</span></span>  
  
7.  <span data-ttu-id="b44dc-117">Arraste e solte o **status do registro** para a coluna **condição** .</span><span class="sxs-lookup"><span data-stu-id="b44dc-117">Drag-drop **Record Status** to the **Condition** column.</span></span>  
  
8.  <span data-ttu-id="b44dc-118">Digite **= = "corrigido"** ao lado de **[status do registro]** para a coluna **condição** .</span><span class="sxs-lookup"><span data-stu-id="b44dc-118">Type **=="Corrected"** next to **[Record Status]** for the **Condition** column.</span></span>  
  
9. <span data-ttu-id="b44dc-119">Clique no **caso 1** na **coluna nome de saída**e altere o nome para **corrigido**.</span><span class="sxs-lookup"><span data-stu-id="b44dc-119">Click **Case 1** in the **Output Name Column**, and change the name to **Corrected**.</span></span>  
  
10. <span data-ttu-id="b44dc-120">Clique em **OK** para fechar a caixa de diálogo **Editor de transformação Divisão condicional** .</span><span class="sxs-lookup"><span data-stu-id="b44dc-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="b44dc-121">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b44dc-121">Next Step</span></span>  
 [<span data-ttu-id="b44dc-122">Tarefa 9: Adicionando a Transformação Unir Tudo para combinar registros corretos e corrigidos</span><span class="sxs-lookup"><span data-stu-id="b44dc-122">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>](../../2014/tutorials/task-9-adding-union-all-transform-to-combine-correct-and-corrected-records.md)  
  
  
