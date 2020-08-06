---
title: Editor de origem ADO NET (página saída de erro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.erroroutput.f1
ms.assetid: 4dd9d129-a95c-4d3a-bbbf-e84a39089950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9ee480caa8764d70b52b25a416f200f353d30c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684839"
---
# <a name="ado-net-source-editor-error-output-page"></a><span data-ttu-id="76a1a-102">Editor de Origem ADO NET (Página Saída de Erro)</span><span class="sxs-lookup"><span data-stu-id="76a1a-102">ADO NET Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="76a1a-103">Use a página **Saída de Erro** da caixa de diálogo **Editor de Origem ADO NET** para selecionar as opções de manipulação de erros e definir as propriedades nas colunas de saída de erros.</span><span class="sxs-lookup"><span data-stu-id="76a1a-103">Use the **Error Output** page of the **ADO NET Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="76a1a-104">Para obter mais informações sobre a origem ADO NET, consulte [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="76a1a-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="76a1a-105">**Para abrir a página Saída de Erro**</span><span class="sxs-lookup"><span data-stu-id="76a1a-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="76a1a-106">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que tenha a origem ADO NET.</span><span class="sxs-lookup"><span data-stu-id="76a1a-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="76a1a-107">Na guia **Fluxo de Dados** , clique duas vezes na origem ADO NET.</span><span class="sxs-lookup"><span data-stu-id="76a1a-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="76a1a-108">No **Editor de Origem ADO NET**, clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="76a1a-108">In the **ADO NET Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="76a1a-109">Opções</span><span class="sxs-lookup"><span data-stu-id="76a1a-109">Options</span></span>  
 <span data-ttu-id="76a1a-110">**Entrada/Saída**</span><span class="sxs-lookup"><span data-stu-id="76a1a-110">**Input/Output**</span></span>  
 <span data-ttu-id="76a1a-111">Exibe o nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="76a1a-111">View the name of the data source.</span></span>  
  
 <span data-ttu-id="76a1a-112">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="76a1a-112">**Column**</span></span>  
 <span data-ttu-id="76a1a-113">Exiba as colunas externas (origem) que você selecionou na página **Gerenciador de Conexões** da caixa de diálogo **Editor de Origem ADO NET** .</span><span class="sxs-lookup"><span data-stu-id="76a1a-113">View the external (source) columns that you selected on the **Connection Manager** page of the **ADO NET Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="76a1a-114">**Erro**</span><span class="sxs-lookup"><span data-stu-id="76a1a-114">**Error**</span></span>  
 <span data-ttu-id="76a1a-115">Especifique o que deve acontecer quando ocorre um erro: ignorar a falha, redirecionar a linha ou causar falha no componente.</span><span class="sxs-lookup"><span data-stu-id="76a1a-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="76a1a-116">**Tópicos relacionados:** [Tratamento de erro em dados](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="76a1a-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="76a1a-117">**Truncation**</span><span class="sxs-lookup"><span data-stu-id="76a1a-117">**Truncation**</span></span>  
 <span data-ttu-id="76a1a-118">Especifique o que deve acontecer quando ocorre um truncamento: ignorar a falha, redirecionar a linha ou causar falha do componente.</span><span class="sxs-lookup"><span data-stu-id="76a1a-118">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="76a1a-119">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="76a1a-119">**Description**</span></span>  
 <span data-ttu-id="76a1a-120">Exiba a descrição do erro.</span><span class="sxs-lookup"><span data-stu-id="76a1a-120">View the description of the error.</span></span>  
  
 <span data-ttu-id="76a1a-121">**Definir este valor para células selecionadas**</span><span class="sxs-lookup"><span data-stu-id="76a1a-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="76a1a-122">Especifique o que deve acontecer a todas as células selecionadas quando ocorre um erro ou um truncamento: ignorar a falha, redirecionar a linha ou causar a falha no componente.</span><span class="sxs-lookup"><span data-stu-id="76a1a-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="76a1a-123">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="76a1a-123">**Apply**</span></span>  
 <span data-ttu-id="76a1a-124">Aplique a opção de tratamento de erros às células selecionadas.</span><span class="sxs-lookup"><span data-stu-id="76a1a-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a1a-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="76a1a-125">See Also</span></span>  
 <span data-ttu-id="76a1a-126">[Editor de origem ADO NET &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="76a1a-126">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="76a1a-127">[Editor de origem ADO NET &#40;página colunas&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="76a1a-127">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="76a1a-128">Gerenciador de conexões ADO.NET</span><span class="sxs-lookup"><span data-stu-id="76a1a-128">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
