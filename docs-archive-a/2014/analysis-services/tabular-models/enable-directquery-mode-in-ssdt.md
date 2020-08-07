---
title: Habilitar o modo de design do DirectQuery (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 71fc7ebd-2e86-4a76-994b-66d3a57bcc9b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ccd2dc88f447e78f6558565a89accc341eac37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574921"
---
# <a name="enable-directquery-design-mode-ssas-tabular"></a><span data-ttu-id="a9dde-102">Habilitar o modo de design de DirectQuery (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="a9dde-102">Enable DirectQuery Design Mode (SSAS Tabular)</span></span>
  <span data-ttu-id="a9dde-103">Para criar um modelo no modo DirectQuery, primeiro altere o ambiente de tempo de design para que ele ofereça suporte ao usuário do modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="a9dde-103">To create a model in DirectQuery mode, you must first change the design-time environment so that it supports the user of DirectQuery mode.</span></span> <span data-ttu-id="a9dde-104">Quando você faz isso, o designer também executa as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="a9dde-104">When you do so, the designer will also do the following:</span></span>  
  
-   <span data-ttu-id="a9dde-105">Habilitar o uso de propriedades de implantação do DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="a9dde-105">Enable the use of the DirectQuery deployment properties.</span></span>  
  
-   <span data-ttu-id="a9dde-106">Alterar o banco de dados do workspace para que seja executado em um modo híbrido que utiliza o cache para design.</span><span class="sxs-lookup"><span data-stu-id="a9dde-106">Change the workspace database to run in a hybrid mode that uses the cache for designing.</span></span> <span data-ttu-id="a9dde-107">Quando você de fato implanta o modelo, o modo retorna ao valor especificado nas propriedades de implantação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a9dde-107">When you actually deploy the model, the mode will be changed back to whatever value you specified in the project deployment properties.</span></span>  
  
-   <span data-ttu-id="a9dde-108">Desabilitar recursos de design que sejam incompatíveis com o modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="a9dde-108">Disable design features that are incompatible with DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="a9dde-109">Validar o modelo existente.</span><span class="sxs-lookup"><span data-stu-id="a9dde-109">Validate the existing model.</span></span>  
  
 <span data-ttu-id="a9dde-110">Este procedimento descreve como habilitar o modo DirectQuery no designer.</span><span class="sxs-lookup"><span data-stu-id="a9dde-110">This procedure describes how to enable DirectQuery mode in the designer.</span></span>  
  
### <a name="to-enable-use-of-directquery-in-a-model"></a><span data-ttu-id="a9dde-111">Para habilitar o uso do DirectQuery em um modelo</span><span class="sxs-lookup"><span data-stu-id="a9dde-111">To enable use of DirectQuery in a model</span></span>  
  
1.  <span data-ttu-id="a9dde-112">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o arquivo de solução.</span><span class="sxs-lookup"><span data-stu-id="a9dde-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the solution file.</span></span>  
  
2.  <span data-ttu-id="a9dde-113">No Pesquisador de Objetos, clique duas vezes no arquivo Model.bim.</span><span class="sxs-lookup"><span data-stu-id="a9dde-113">In Object Explorer, double-click the Model.bim file.</span></span>  
  
3.  <span data-ttu-id="a9dde-114">No painel **Propriedades** , altere a propriedade, **DirectQueryMode**, para **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="a9dde-114">In the **Properties** pane, change the property, **DirectQueryMode**, to **On**.</span></span>  
  
4.  <span data-ttu-id="a9dde-115">Em caso de erros, no Visual Studio, abra a **Lista de Erros** e resolva os problemas que possam impedir a alternância do modelo para o modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="a9dde-115">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being switched to DirectQuery mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9dde-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a9dde-116">See Also</span></span>  
 [<span data-ttu-id="a9dde-117">Modo DirectQuery &#40;SSAS de tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="a9dde-117">DirectQuery Mode &#40;SSAS Tabular&#41;</span></span>](directquery-mode-ssas-tabular.md)  
  
  
