---
title: Substituir parâmetros do modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.templates.replaceparameters.f1
helpviewer_keywords:
- template parameters [Template Explorer]
- templates [Transact-SQL], replacing parameters
- Replace (Query) Template Parameters dialog box
- replacing template parameters
ms.assetid: 1234aa14-3464-4a3e-922a-5cfb8fb23627
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d87b17a110efe118f7796487448e4d3bae30375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575519"
---
# <a name="replace-template-parameters"></a><span data-ttu-id="dfd83-102">Substituir Parâmetros do Modelo</span><span class="sxs-lookup"><span data-stu-id="dfd83-102">Replace Template Parameters</span></span>
  <span data-ttu-id="dfd83-103">Modelos contêm parâmetros que podem ser substituídos por valores específicos de implementação cada vez que o modelo é usado.</span><span class="sxs-lookup"><span data-stu-id="dfd83-103">Templates contain parameters that can be replaced by implementation-specific values each time the template is used.</span></span> <span data-ttu-id="dfd83-104">Depois de abrir um modelo em um editor de código, você pode substituir os parâmetros pelos valores relevantes à sua implementação.</span><span class="sxs-lookup"><span data-stu-id="dfd83-104">After opening a template in a code editor, you can replace the parameters with values relevant to your implementation.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="dfd83-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="dfd83-105">Before You Begin</span></span>  
 <span data-ttu-id="dfd83-106">A caixa de diálogo **Especificar Valores para Parâmetros de Modelo** é uma grade com três colunas.</span><span class="sxs-lookup"><span data-stu-id="dfd83-106">The **Specify Values for Template Parameters** dialog is a grid with three columns.</span></span> <span data-ttu-id="dfd83-107">As colunas **Parâmetro** e **Tipo** são somente leitura e não podem ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="dfd83-107">The **Parameter** and **Type** columns are read-only and cannot be changed.</span></span> <span data-ttu-id="dfd83-108">Examine o conteúdo da coluna **Valor** e altere qualquer um dos padrões para valores apropriados para sua implementação.</span><span class="sxs-lookup"><span data-stu-id="dfd83-108">Review the contents of the **Value** column, and change any of the defaults to values appropriate for your implementation.</span></span>  
  
 <span data-ttu-id="dfd83-109">Para usar essa caixa de diálogo, os parâmetros em seu script devem estar entre colchetes angulares (`< >`) no formato `<`*parameter_name*`,` *data_type*`,` *default_value*`>`.</span><span class="sxs-lookup"><span data-stu-id="dfd83-109">To use this dialog box, you must have parameters in your script enclosed in angle brackets (`< >`) in the format `<`*parameter_name*`,` *data_type*`,` *default_value*`>`.</span></span>  
  
## <a name="replace-template-parameters"></a><span data-ttu-id="dfd83-110">Substituir Parâmetros do Modelo</span><span class="sxs-lookup"><span data-stu-id="dfd83-110">Replace Template Parameters</span></span>  
 <span data-ttu-id="dfd83-111">Depois de abrir o modelo em uma janela de editor de código:</span><span class="sxs-lookup"><span data-stu-id="dfd83-111">After opening the template in a code editor window:</span></span>  
  
1.  <span data-ttu-id="dfd83-112">No menu **Consulta** , clique em **Especificar Valores para Parâmetros de Modelo**.</span><span class="sxs-lookup"><span data-stu-id="dfd83-112">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
2.  <span data-ttu-id="dfd83-113">Na caixa de diálogo **Especificar Valores para Parâmetros de Modelo** , a coluna **Valores** contém um valor sugerido para cada parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dfd83-113">In the **Specify Values for Template Parameters** dialog box, the **Values** column contains a suggested value for each parameter.</span></span> <span data-ttu-id="dfd83-114">Aceite o valor ou substitua-o por um novo valor.</span><span class="sxs-lookup"><span data-stu-id="dfd83-114">Accept the value or replace it with a new value.</span></span>  
  
3.  <span data-ttu-id="dfd83-115">Clique em **OK** para fechar a caixa de diálogo **Substituir Parâmetros do Modelo** e modificar o script no editor de consulta.</span><span class="sxs-lookup"><span data-stu-id="dfd83-115">Click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the query editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfd83-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dfd83-116">See Also</span></span>  
 <span data-ttu-id="dfd83-117">[Gerenciador de modelos](template-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="dfd83-117">[Template Explorer](template-explorer.md) </span></span>  
 [<span data-ttu-id="dfd83-118">Abrir um modelo</span><span class="sxs-lookup"><span data-stu-id="dfd83-118">Open a Template</span></span>](open-a-template.md)  
  
  
