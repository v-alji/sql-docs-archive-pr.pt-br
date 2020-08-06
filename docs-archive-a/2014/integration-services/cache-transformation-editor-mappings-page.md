---
title: Editor de transformação cache (página Mapeamentos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetransmap.f1
ms.assetid: ffd53f18-9646-458a-a84a-f2467d601ea5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bb31e479ea98133da34dcbf257d59e70f4ffe8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582098"
---
# <a name="cache-transformation-editor-mappings-page"></a><span data-ttu-id="a2f01-102">Editor da Transformação Cache (página Mapeamentos)</span><span class="sxs-lookup"><span data-stu-id="a2f01-102">Cache Transformation Editor (Mappings Page)</span></span>
  <span data-ttu-id="a2f01-103">Use a página **Mapeamentos** do **Editor da Transformação Cache** para mapear as colunas de entrada na Transformação Cache para as colunas de destino no Gerenciador de conexões de cache.</span><span class="sxs-lookup"><span data-stu-id="a2f01-103">Use the **Mappings** page of the **Cache Transformation Editor** to map the input columns in the Cache Transform transformation to destination columns in the Cache connection manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2f01-104">Cada coluna de entrada deve ser mapeada para uma coluna de destino e os tipos de dados de coluna devem corresponder.</span><span class="sxs-lookup"><span data-stu-id="a2f01-104">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="a2f01-105">Caso contrário, o Designer [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] exibirá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="a2f01-105">Otherwise, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
 <span data-ttu-id="a2f01-106">Para obter mais informações sobre a Transformação Cache, consulte [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="a2f01-106">To learn more about the Cache Transform, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
 <span data-ttu-id="a2f01-107">Para saber mais sobre o Gerenciador de conexões de cache, consulte [cache Connection Manager](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a2f01-107">To learn more about the Cache connection manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a2f01-108">Opções</span><span class="sxs-lookup"><span data-stu-id="a2f01-108">Options</span></span>  
 <span data-ttu-id="a2f01-109">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="a2f01-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="a2f01-110">Exiba a lista das colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a2f01-110">View the list of available input columns.</span></span> <span data-ttu-id="a2f01-111">Use uma operação de arrastar e soltar para mapear as colunas de entrada disponíveis para colunas de destino.</span><span class="sxs-lookup"><span data-stu-id="a2f01-111">Use a drag-and-drop operation to map available input columns to destination columns.</span></span>  
  
 <span data-ttu-id="a2f01-112">Você também pode mapear as colunas de entrada para as colunas de destino usando o teclado, destacando a coluna na tabela **Colunas de Entrada Disponíveis** , pressionando a tecla de menu e selecionando **Mapear Itens por Correspondência de Nomes**.</span><span class="sxs-lookup"><span data-stu-id="a2f01-112">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="a2f01-113">**Colunas de Destino Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="a2f01-113">**Available Destination Columns**</span></span>  
 <span data-ttu-id="a2f01-114">Exiba a lista de colunas de destino disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a2f01-114">View the list of available destination columns.</span></span> <span data-ttu-id="a2f01-115">Use uma operação de arrastar e soltar para mapear as colunas de destino disponíveis para colunas de entrada.</span><span class="sxs-lookup"><span data-stu-id="a2f01-115">Use a drag-and-drop operation to map available destination columns to input columns.</span></span>  
  
 <span data-ttu-id="a2f01-116">Você também pode mapear as colunas de entrada para as colunas de destino usando o teclado, destacando a coluna na tabela **Colunas de Destino Disponíveis** , pressionando a tecla de menu e selecionando **Mapear Itens por Correspondência de Nomes**.</span><span class="sxs-lookup"><span data-stu-id="a2f01-116">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Destination Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="a2f01-117">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="a2f01-117">**Input Column**</span></span>  
 <span data-ttu-id="a2f01-118">Exiba as colunas de entrada selecionadas anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a2f01-118">View input columns selected earlier in this topic.</span></span> <span data-ttu-id="a2f01-119">É possível alterar os mapeamentos usando a lista **Colunas de Entrada Disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="a2f01-119">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="a2f01-120">**Coluna de Destino**</span><span class="sxs-lookup"><span data-stu-id="a2f01-120">**Destination Column**</span></span>  
 <span data-ttu-id="a2f01-121">Exiba todas as colunas de destino disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a2f01-121">View each available destination column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f01-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2f01-122">See Also</span></span>  
 [<span data-ttu-id="a2f01-123">Editor de Transformação Cache &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="a2f01-123">Cache Transformation Editor &#40;Connection Manager Page&#41;</span></span>](../../2014/integration-services/cache-transformation-editor-connection-manager-page.md)  
  
  
