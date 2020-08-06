---
title: Exibir ou alterar sinalizadores de modelagem (mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d1169735-fb18-417b-b8d6-9a161e444020
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf0edd827321685a2d6a9041759328a7ac6e7cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681278"
---
# <a name="view-or-change-modeling-flags-data-mining"></a><span data-ttu-id="16597-102">Exibir ou alterar sinalizadores de modelagem (mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="16597-102">View or Change Modeling Flags (Data Mining)</span></span>
  <span data-ttu-id="16597-103">Sinalizadores de modelagem são propriedades que você define em uma coluna da estrutura de mineração ou em colunas do modelo de mineração para controlar como o algoritmo processa os dados durante a análise.</span><span class="sxs-lookup"><span data-stu-id="16597-103">Modeling flags are properties that you set on a mining structure column or mining model columns to control how the algorithm processes the data during analysis.</span></span>  
  
 <span data-ttu-id="16597-104">No Designer de Mineração de Dados, é possível exibir e modificar os sinalizadores de modelagem associados a uma estrutura ou a uma coluna de mineração ao exibir as propriedades do modelo ou da estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="16597-104">In Data Mining Designer, you can view and modify the modeling flags associated with a mining structure or mining column by viewing the properties of the structure or model.</span></span> <span data-ttu-id="16597-105">Você também pode definir sinalizadores de modelagem usando DMX, AMO ou XMLA.</span><span class="sxs-lookup"><span data-stu-id="16597-105">You can also set modeling flags by using DMX, AMO, or XMLA.</span></span>  
  
 <span data-ttu-id="16597-106">Este procedimento descreve como alterar os sinalizadores de modelagem no designer.</span><span class="sxs-lookup"><span data-stu-id="16597-106">This procedure describes how to change the modeling flags in the designer.</span></span>  
  
### <a name="view-or-change-the-modeling-flag-for-a-structure-column-or-model-column"></a><span data-ttu-id="16597-107">Exibir ou alterar o sinalizador de modelagem de uma coluna de estrutura ou de modelo</span><span class="sxs-lookup"><span data-stu-id="16597-107">View or change the modeling flag for a structure column or model column</span></span>  
  
1.  <span data-ttu-id="16597-108">No SQL Server Design Estúdio, abra o Gerenciador de Soluções e clique duas vezes na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="16597-108">In SQL Server Design Studio, open Solution Explorer, and then double-click the mining structure.</span></span>  
  
2.  <span data-ttu-id="16597-109">Para definir o sinalizador de modelagem NOT NULL, clique na guia **estrutura de mineração** . Para definir os sinalizadores de REGRESSOr ou de MODEL_EXISTENCE_ONLY, clique na guia **modelo de mineração** .</span><span class="sxs-lookup"><span data-stu-id="16597-109">To set the NOT NULL modeling flag, click the **Mining Structure** tab. To set the REGRESSOR or MODEL_EXISTENCE_ONLY flags, click the **Mining Model** tab.</span></span>  
  
3.  <span data-ttu-id="16597-110">Clique com o botão direito do mouse na coluna que você deseja exibir ou alterar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="16597-110">Right-click the column you want to view or change, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="16597-111">Para adicionar um novo sinalizador de modelagem, clique na caixa de texto próxima de propriedade **ModelingFlags** e marque as caixas de seleção referentes aos sinalizadores de modelagem que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="16597-111">To add a new modeling flag, click the text box next to the **ModelingFlags** property, and select the check box or check boxes for the modeling flags you want to use.</span></span>  
  
     <span data-ttu-id="16597-112">Serão exibidos apenas os sinalizadores de modelagem apropriados para o tipo de dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="16597-112">Modeling flags are displayed only if they are appropriate for the column data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="16597-113">Depois de alterar um sinalizador de modelagem, processe novamente o modelo.</span><span class="sxs-lookup"><span data-stu-id="16597-113">After you change a modeling flag, you must reprocess the model.</span></span>  
  
### <a name="get-the-modeling-flags-used-in-the-model"></a><span data-ttu-id="16597-114">Obter os sinalizadores de modelagem usados no modelo</span><span class="sxs-lookup"><span data-stu-id="16597-114">Get the modeling flags used in the model</span></span>  
  
-   <span data-ttu-id="16597-115">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra uma janela da Consulta DMX e digite uma consulta como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="16597-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window, and type a query like the following:</span></span>  
  
    ```  
    SELECT COLUMN_NAME, CONTENT_TYPE, MODELING_FLAG  
    FROM $system.DMSCHEMA_MINING_COLUMNS  
    WHERE MODEL_NAME = 'Forecasting'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="16597-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16597-116">See Also</span></span>  
 <span data-ttu-id="16597-117">[Tarefas e instruções do modelo de mineração](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="16597-117">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="16597-118">Sinalizadores de modelagem &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="16597-118">Modeling Flags &#40;Data Mining&#41;</span></span>](modeling-flags-data-mining.md)  
  
  
