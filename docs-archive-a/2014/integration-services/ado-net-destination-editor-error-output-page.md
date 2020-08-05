---
title: Editor de destino ADO NET (página saída de erro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetdest.erroroutput.f1
ms.assetid: 1a56c3cf-fb6a-416d-a62c-bb19fe441ae5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cfd69d3adec2aa617f5e9d3add35a1a6923804
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574239"
---
# <a name="ado-net-destination-editor-error-output-page"></a><span data-ttu-id="877dc-102">Editor de Destino ADO NET (Página Saída de Erro)</span><span class="sxs-lookup"><span data-stu-id="877dc-102">ADO NET Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="877dc-103">Use a página **Saída de Erro** da caixa de diálogo **Editor de Destino ADO NET** para especificar as opções para tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="877dc-103">Use the **Error Output** page of the **ADO NET Destination Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="877dc-104">Para obter mais informações sobre o destino ADO NET, consulte [ADO NET Destination](data-flow/ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="877dc-104">To learn more about the ADO NET destination, see [ADO NET Destination](data-flow/ado-net-destination.md).</span></span>  
  
 <span data-ttu-id="877dc-105">**Para abrir a página Saída de Erro**</span><span class="sxs-lookup"><span data-stu-id="877dc-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="877dc-106">Em [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que tenha o destino ADO NET.</span><span class="sxs-lookup"><span data-stu-id="877dc-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET destination.</span></span>  
  
2.  <span data-ttu-id="877dc-107">Na guia **Fluxo de Dados** , clique duas vezes no destino ADO NET.</span><span class="sxs-lookup"><span data-stu-id="877dc-107">On the **Data Flow** tab, double-click the ADO NET destination.</span></span>  
  
3.  <span data-ttu-id="877dc-108">No **Editor de Destino ADO NET**, clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="877dc-108">In the **ADO NET Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="877dc-109">Opções</span><span class="sxs-lookup"><span data-stu-id="877dc-109">Options</span></span>  
 <span data-ttu-id="877dc-110">**Entrada ou Saída**</span><span class="sxs-lookup"><span data-stu-id="877dc-110">**Input or Output**</span></span>  
 <span data-ttu-id="877dc-111">Visualize o nome da entrada.</span><span class="sxs-lookup"><span data-stu-id="877dc-111">View the name of the input.</span></span>  
  
 <span data-ttu-id="877dc-112">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="877dc-112">**Column**</span></span>  
 <span data-ttu-id="877dc-113">Não usado.</span><span class="sxs-lookup"><span data-stu-id="877dc-113">Not used.</span></span>  
  
 <span data-ttu-id="877dc-114">**Erro**</span><span class="sxs-lookup"><span data-stu-id="877dc-114">**Error**</span></span>  
 <span data-ttu-id="877dc-115">Especifique o que deve acontecer quando ocorre um erro: ignorar a falha, redirecionar a linha ou causar falha no componente.</span><span class="sxs-lookup"><span data-stu-id="877dc-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="877dc-116">**Tópicos relacionados:** [Tratamento de erro em dados](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="877dc-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="877dc-117">**Truncation**</span><span class="sxs-lookup"><span data-stu-id="877dc-117">**Truncation**</span></span>  
 <span data-ttu-id="877dc-118">Não usado.</span><span class="sxs-lookup"><span data-stu-id="877dc-118">Not used.</span></span>  
  
 <span data-ttu-id="877dc-119">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="877dc-119">**Description**</span></span>  
 <span data-ttu-id="877dc-120">Visualize a descrição da operação.</span><span class="sxs-lookup"><span data-stu-id="877dc-120">View the description of the operation.</span></span>  
  
 <span data-ttu-id="877dc-121">**Definir este valor para células selecionadas**</span><span class="sxs-lookup"><span data-stu-id="877dc-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="877dc-122">Especifique o que deve acontecer a todas as células selecionadas quando ocorre um erro ou um truncamento: ignorar a falha, redirecionar a linha ou causar a falha no componente.</span><span class="sxs-lookup"><span data-stu-id="877dc-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="877dc-123">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="877dc-123">**Apply**</span></span>  
 <span data-ttu-id="877dc-124">Aplique a opção de tratamento de erros às células selecionadas.</span><span class="sxs-lookup"><span data-stu-id="877dc-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="877dc-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="877dc-125">See Also</span></span>  
 <span data-ttu-id="877dc-126">[Editor de destino ADO NET &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="877dc-126">[ADO NET Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="877dc-127">Editor de Destino ADO NET &#40;página Mapeamentos&#41;</span><span class="sxs-lookup"><span data-stu-id="877dc-127">ADO NET Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/ado-net-destination-editor-mappings-page.md)  
  
  
