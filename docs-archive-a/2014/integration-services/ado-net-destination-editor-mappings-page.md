---
title: Editor de destino ADO NET (página Mapeamentos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetdest.mappings.f1
ms.assetid: 842d075f-8b7a-457c-a1a1-a7acbe10e9b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7e7a2397e4e2d16e6eeca93d41f5127dfde4c35e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568753"
---
# <a name="ado-net-destination-editor-mappings-page"></a><span data-ttu-id="b8585-102">Editor de Destino ADO NET (Página Mapeamentos)</span><span class="sxs-lookup"><span data-stu-id="b8585-102">ADO NET Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="b8585-103">Use a página **Mapeamentos** da caixa de diálogo **Editor de Destino ADO NET** para mapear as colunas de entrada nas colunas de destino.</span><span class="sxs-lookup"><span data-stu-id="b8585-103">Use the **Mappings** page of the **ADO NET Destination Editor** dialog box to map input columns to destination columns.</span></span>  
  
 <span data-ttu-id="b8585-104">Para obter mais informações sobre o destino ADO NET, consulte [ADO NET Destination](data-flow/ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="b8585-104">To learn more about the ADO NET destination, see [ADO NET Destination](data-flow/ado-net-destination.md).</span></span>  
  
 <span data-ttu-id="b8585-105">**Para abrir a página Mapeamentos**</span><span class="sxs-lookup"><span data-stu-id="b8585-105">**To open the Mappings page**</span></span>  
  
1.  <span data-ttu-id="b8585-106">Em [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que tenha o destino ADO NET.</span><span class="sxs-lookup"><span data-stu-id="b8585-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET destination.</span></span>  
  
2.  <span data-ttu-id="b8585-107">Na guia **Fluxo de Dados** , clique duas vezes no destino ADO NET.</span><span class="sxs-lookup"><span data-stu-id="b8585-107">On the **Data Flow** tab, double-click the ADO NET destination.</span></span>  
  
3.  <span data-ttu-id="b8585-108">No **Editor de Destino ADO NET**, clique em **Mapeamentos**.</span><span class="sxs-lookup"><span data-stu-id="b8585-108">In the **ADO NET Destination Editor**, click **Mappings**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b8585-109">Opções</span><span class="sxs-lookup"><span data-stu-id="b8585-109">Options</span></span>  
 <span data-ttu-id="b8585-110">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="b8585-110">**Available Input Columns**</span></span>  
 <span data-ttu-id="b8585-111">Exiba a lista das colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b8585-111">View the list of available input columns.</span></span> <span data-ttu-id="b8585-112">Use uma operação de arrastar e soltar para mapear colunas de entrada disponíveis na tabela para as colunas de destino.</span><span class="sxs-lookup"><span data-stu-id="b8585-112">Use a drag-and-drop operation to map available input columns in the table to destination columns.</span></span>  
  
 <span data-ttu-id="b8585-113">**Colunas de Destino Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="b8585-113">**Available Destination Columns**</span></span>  
 <span data-ttu-id="b8585-114">Exiba a lista de colunas de destino disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b8585-114">View the list of available destination columns.</span></span> <span data-ttu-id="b8585-115">Use uma operação de arrastar e soltar para mapear as colunas de destino disponíveis na tabela para as colunas de entrada.</span><span class="sxs-lookup"><span data-stu-id="b8585-115">Use a drag-and-drop operation to map available destination columns in the table to input columns.</span></span>  
  
 <span data-ttu-id="b8585-116">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="b8585-116">**Input Column**</span></span>  
 <span data-ttu-id="b8585-117">Exiba as colunas de entrada que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="b8585-117">View the input columns that you selected.</span></span> <span data-ttu-id="b8585-118">Você pode remover os mapeamentos selecionando **\<ignore>** para excluir colunas da saída.</span><span class="sxs-lookup"><span data-stu-id="b8585-118">You can remove mappings by selecting **\<ignore>** to exclude columns from the output.</span></span>  
  
 <span data-ttu-id="b8585-119">**Coluna de Destino**</span><span class="sxs-lookup"><span data-stu-id="b8585-119">**Destination Column**</span></span>  
 <span data-ttu-id="b8585-120">Visualize cada coluna de destino disponível, esteja ela mapeada ou não.</span><span class="sxs-lookup"><span data-stu-id="b8585-120">View each available destination column, regardless of whether it is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8585-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b8585-121">See Also</span></span>  
 <span data-ttu-id="b8585-122">[Editor de destino ADO NET &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="b8585-122">[ADO NET Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="b8585-123">Editor de Destino ADO NET &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="b8585-123">ADO NET Destination Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/ado-net-destination-editor-error-output-page.md)  
  
  
