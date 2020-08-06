---
title: Especificar marcar como tabela de data para uso com inteligência de tempo (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 30841d1f-0c3b-4575-8f4a-27a1492e248c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 81038369b8cb8636a2aa216f1c26783a96d5f7ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678296"
---
# <a name="specify-mark-as-date-table-for-use-with-time-intelligence-ssas-tabular"></a><span data-ttu-id="190ce-102">Especifique Marcar como Tabela de Data para uso com Inteligência de Tempo (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="190ce-102">Specify Mark as Date Table for use with Time Intelligence (SSAS Tabular)</span></span>
  <span data-ttu-id="190ce-103">Para usar funções de inteligência de tempo em fórmulas DAX, você deverá especificar uma tabela de datas e uma coluna de identificador exclusivo (datetime) do tipo de dados de data.</span><span class="sxs-lookup"><span data-stu-id="190ce-103">In order to use time intelligence functions in DAX formulas, you must specify a date table and a unique identifier (datetime) column of the Date data type.</span></span> <span data-ttu-id="190ce-104">Quando uma coluna na tabela de datas é especificada como um identificador exclusivo, você pode criar relações entre colunas na tabela de datas e qualquer tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="190ce-104">Once a column in the date table is specified as a unique identifier, you can create relationships between columns in the date table and any fact tables.</span></span>  
  
 <span data-ttu-id="190ce-105">Ao usar as funções de inteligência de dados de tempo, as seguintes regras se aplicam:</span><span class="sxs-lookup"><span data-stu-id="190ce-105">When using time intelligence functions, the following rules apply:</span></span>  
  
-   <span data-ttu-id="190ce-106">Ao usar as funções de inteligência de dados de tempo DAX, nunca especifique uma coluna de datetime de uma tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="190ce-106">When using DAX time intelligence functions, never specify a datetime column from a fact table.</span></span> <span data-ttu-id="190ce-107">Sempre crie uma tabela de datas separada em seu modelo com pelo menos uma coluna de datetime de tipo de dados de data e com valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="190ce-107">Always create a separate date table in your model with at least one datetime column of Date data type and with unique values.</span></span>  
  
-   <span data-ttu-id="190ce-108">Tenha certeza de que sua tabela de datas tem um intervalo de datas contínuo.</span><span class="sxs-lookup"><span data-stu-id="190ce-108">Make sure your date table has a continuous date range.</span></span>  
  
-   <span data-ttu-id="190ce-109">A coluna de datetime na tabela de datas deve ter uma granularidade de dia (sem frações de um dia).</span><span class="sxs-lookup"><span data-stu-id="190ce-109">The datetime column in the date table should be at day granularity (without fractions of a day).</span></span>  
  
-   <span data-ttu-id="190ce-110">Você deve especificar uma tabela de data e uma coluna de identificador exclusivo usando a caixa de diálogo **Marcar como Tabela de Datas** .</span><span class="sxs-lookup"><span data-stu-id="190ce-110">You must specify a date table and a unique identifier column by using the **Mark the Date Table** dialog box.</span></span>  
  
-   <span data-ttu-id="190ce-111">Crie relações entre tabelas de fatos e colunas de tipo de dados de data na tabela de datas.</span><span class="sxs-lookup"><span data-stu-id="190ce-111">Create relationships between fact tables and columns of Date data type in the date table.</span></span>  
  
#### <a name="to-specify-a-date-table-and-unique-identifier"></a><span data-ttu-id="190ce-112">Para especificar uma tabela de datas e um identificador exclusivo</span><span class="sxs-lookup"><span data-stu-id="190ce-112">To specify a date table and unique identifier</span></span>  
  
1.  <span data-ttu-id="190ce-113">No designer de modelos, clique na tabela de datas.</span><span class="sxs-lookup"><span data-stu-id="190ce-113">In the model designer, click the date table.</span></span>  
  
2.  <span data-ttu-id="190ce-114">Clique no menu **Tabela** , clique em **Data**e em **Mark as Data Tabela**.</span><span class="sxs-lookup"><span data-stu-id="190ce-114">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**</span></span>  
  
3.  <span data-ttu-id="190ce-115">Na caixa de diálogo **Marcar como Tabela de Data** , na caixa de listagem **Data** , selecione uma coluna a ser usada como um identificador exclusivo.</span><span class="sxs-lookup"><span data-stu-id="190ce-115">In the **Mark as Date Table** dialog box, in the **Date** listbox, select a column to be used as a unique identifier.</span></span> <span data-ttu-id="190ce-116">Esta coluna deve conter valores exclusivos e deve ser do tipo de dados de data.</span><span class="sxs-lookup"><span data-stu-id="190ce-116">This column must contain unique values and should be of Date data type.</span></span> <span data-ttu-id="190ce-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="190ce-117">For example:</span></span>  
  
    |<span data-ttu-id="190ce-118">Data</span><span class="sxs-lookup"><span data-stu-id="190ce-118">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="190ce-119">7/1/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="190ce-119">7/1/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="190ce-120">7/2/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="190ce-120">7/2/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="190ce-121">7/3/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="190ce-121">7/3/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="190ce-122">7/4/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="190ce-122">7/4/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="190ce-123">7/5/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="190ce-123">7/5/2010 12:00:00 AM</span></span>|  
  
4.  <span data-ttu-id="190ce-124">Se necessário, crie qualquer relação entre tabelas de fatos e a tabela de datas.</span><span class="sxs-lookup"><span data-stu-id="190ce-124">If necessary, create any relationships between fact tables and the date table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="190ce-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="190ce-125">See Also</span></span>  
 <span data-ttu-id="190ce-126">[Cálculos &#40;SSAS de tabela&#41;](calculations-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="190ce-126">[Calculations &#40;SSAS Tabular&#41;](calculations-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="190ce-127">Funções de inteligência de tempo &#40;&#41;DAX</span><span class="sxs-lookup"><span data-stu-id="190ce-127">Time Intelligence Functions &#40;DAX&#41;</span></span>](/dax/time-intelligence-functions-dax)  
  
  
