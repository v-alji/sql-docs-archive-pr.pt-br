---
title: Restringir linhas (Assistente para partições) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.typefilterexpression.f1
ms.assetid: eec8da8f-eab4-4ac4-a81d-995c814f88ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b0acc9ab24cfe92877d9abcd86353c85b4f8905
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570944"
---
# <a name="restrict-rows-partition-wizard"></a><span data-ttu-id="708dc-102">Restringir linhas (Assistente para Partições)</span><span class="sxs-lookup"><span data-stu-id="708dc-102">Restrict Rows (Partition Wizard)</span></span>
  <span data-ttu-id="708dc-103">Use a página **Restringir Linhas** para restringir as linhas que serão recuperadas da tabela especificada e agregadas e incluídas na partição.</span><span class="sxs-lookup"><span data-stu-id="708dc-103">Use the **Restrict Rows** page to restrict the rows that will be retrieved from the specified table and will be aggregated and included in the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="708dc-104"> Essa página será exibida apenas se você tiver selecionado uma única tabela na página **Especificar Informações sobre a Origem** .</span><span class="sxs-lookup"><span data-stu-id="708dc-104">This page is appears only if you selected a single table in the **Specify Source Information** page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="708dc-105"> Se você tiver especificado uma tabela em **Tabelas Disponíveis** na página **Especificar Informações sobre a Origem** que seja usada por outra partição, deverá fornecer uma consulta na página **Restringir Linhas** ou arriscar a duplicação de dados no cubo.</span><span class="sxs-lookup"><span data-stu-id="708dc-105">If you specified a table in **Available Tables** on the **Specify Source Information** page that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="708dc-106">Opções</span><span class="sxs-lookup"><span data-stu-id="708dc-106">Options</span></span>  
 <span data-ttu-id="708dc-107">**Especificar uma consulta para restringir linhas**</span><span class="sxs-lookup"><span data-stu-id="708dc-107">**Specify a query to restrict rows**</span></span>  
 <span data-ttu-id="708dc-108">Selecione para inserir uma consulta que restrinja linhas na caixa **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="708dc-108">Select to enter a query that restricts rows into the **Query** box.</span></span>  
  
 <span data-ttu-id="708dc-109">Se o campo **Fornecer uma cláusula WHERE** estiver vazio quando essa opção for selecionada, essa opção será preenchida com uma instrução SQL que recupera todas as linhas da tabela selecionada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="708dc-109">If **Supply a WHERE clause** is empty when this option is selected, that option is populated with an SQL statement that retrieves all columns and all rows from the previously selected table.</span></span>  
  
 <span data-ttu-id="708dc-110">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="708dc-110">**Query**</span></span>  
 <span data-ttu-id="708dc-111">Digite ou modifique a instrução SQL usada ao recuperar linhas da tabela quando a partição é processada.</span><span class="sxs-lookup"><span data-stu-id="708dc-111">Type or modify the SQL statement used when retrieving rows from the table when the partition is processed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="708dc-112">Ao especificar uma cláusula WHERE, um subconjunto de registros pode ser usado para esta partição.</span><span class="sxs-lookup"><span data-stu-id="708dc-112">By specifying a WHERE clause, a subset of records can be used for this partition.</span></span> <span data-ttu-id="708dc-113">Isso é essencial para evitar duplicação de dados quando várias partições estiverem baseadas em uma única tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="708dc-113">This is essential to prevent duplication of data when multiple partitions are based on a single fact table.</span></span>  
  
 <span data-ttu-id="708dc-114">**Verificação**</span><span class="sxs-lookup"><span data-stu-id="708dc-114">**Check**</span></span>  
 <span data-ttu-id="708dc-115">Verifica se a instrução em **Consulta** é uma instrução SQL válida.</span><span class="sxs-lookup"><span data-stu-id="708dc-115">Verifies that the statement in **Query** is a valid SQL statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="708dc-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="708dc-116">See Also</span></span>  
 [<span data-ttu-id="708dc-117">Partições &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="708dc-117">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
