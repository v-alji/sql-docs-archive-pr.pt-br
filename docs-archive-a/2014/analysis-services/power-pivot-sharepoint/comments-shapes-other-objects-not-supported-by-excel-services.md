---
title: 'Os recursos a seguir não têm suporte dos serviços do Excel e podem não ser exibidos ou podem exibir apenas parcialmente: comentários, formas ou outros objetos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ade92e15-dfbf-496b-9378-a00bd83ba750
author: minewiskan
ms.author: owend
ms.openlocfilehash: 67c2989ab89f242fdce2ca64f3c2f361e17d49ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680658"
---
# <a name="the-following-features-are-not-supported-by-excel-services-and-may-not-display-or-may-display-only-partially-comments-shapes-or-other-objects"></a><span data-ttu-id="fc916-102">Os recursos a seguir não têm suporte dos Serviços do Excel e podem não ser exibidos ou ser exibidos apenas parcialmente: Comentários, Formas ou outros objetos</span><span class="sxs-lookup"><span data-stu-id="fc916-102">The following features are not supported by Excel Services and may not display or may display only partially: Comments, Shapes, or other objects</span></span>
  <span data-ttu-id="fc916-103">Este erro ocorre quando você adiciona segmentações de dados a uma pasta de trabalho PowerPivot a partir de uma lista de campos do PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fc916-103">This error occurs when you add Slicers to a PowerPivot workbook from a PowerPivot Field List.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fc916-104">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fc916-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fc916-105">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="fc916-105">Applies to</span></span>|<span data-ttu-id="fc916-106">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="fc916-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="fc916-107">Versão do produto</span><span class="sxs-lookup"><span data-stu-id="fc916-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="fc916-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc916-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="fc916-109">Causa</span><span class="sxs-lookup"><span data-stu-id="fc916-109">Cause</span></span>|<span data-ttu-id="fc916-110">O Excel Web Access não pode renderizar o objeto Forma usado para controlar o posicionamento e a formatação de Segmentações de Dados acrescentadas a uma pasta de trabalho da Lista de Campos do PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fc916-110">Excel Web Access cannot render the Shape object used to control positioning and formatting of Slicers added to a workbook from the PowerPivot Field List.</span></span>|  
|<span data-ttu-id="fc916-111">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="fc916-111">Message Text</span></span>|<span data-ttu-id="fc916-112">Os recursos a seguir não têm suporte dos Serviços do Excel e podem não ser exibidos ou ser exibidos apenas parcialmente:</span><span class="sxs-lookup"><span data-stu-id="fc916-112">The following features are not supported by Excel Services and may not display or may display only partially:</span></span><br /><br /> <span data-ttu-id="fc916-113">Comentários, Formas ou outros objetos</span><span class="sxs-lookup"><span data-stu-id="fc916-113">Comments, Shapes, or other objects</span></span><br /><br /> <span data-ttu-id="fc916-114">Alguns recursos, como consultas de dados externas, exibem dados armazenados em cache que só podem ser atualizados no Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="fc916-114">Some features, such as external data queries, display cached data which can only be refreshed in Microsoft Excel.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fc916-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="fc916-115">Explanation</span></span>  
 <span data-ttu-id="fc916-116">O Excel Acesso via Web mostra esse erro quando você abre uma pasta de trabalho PowerPivot em um navegador e clica no botão **detalhes** da mensagem, **recursos sem suporte essa pasta de trabalho pode não ser exibida como pretendida**.</span><span class="sxs-lookup"><span data-stu-id="fc916-116">Excel Web Access shows this error when you open a PowerPivot workbook in a browser and you click the **Details** button for the message, **Unsupported Features This workbook may not display as intended**.</span></span>  
  
 <span data-ttu-id="fc916-117">Este erro ocorre porque a pasta de trabalho PowerPivot contém Segmentações de Dados cujo layout é controlado por um objeto Forma oculto no Excel.</span><span class="sxs-lookup"><span data-stu-id="fc916-117">This error occurs because the PowerPivot workbook contains Slicers whose layout is controlled by a hidden Shape object in Excel.</span></span> <span data-ttu-id="fc916-118">O objeto Forma controla a formatação e o posicionamento das Segmentações de Dados em posicionamentos horizontais e verticais.</span><span class="sxs-lookup"><span data-stu-id="fc916-118">The Shape object controls the formatting and positioning of the Slicers in horizontal and vertical placements.</span></span>  
  
 <span data-ttu-id="fc916-119">Os Serviços do Excel não podem renderizar um objeto Forma, mas, como o objeto é oculto, o fato de ele não renderizar não é um problema.</span><span class="sxs-lookup"><span data-stu-id="fc916-119">Excel Services cannot render a Shape object, but because the object is hidden, the fact that it does not render is not an issue.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fc916-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="fc916-120">User Action</span></span>  
 <span data-ttu-id="fc916-121">Este erro pode ser ignorado.</span><span class="sxs-lookup"><span data-stu-id="fc916-121">This error can be ignored.</span></span> <span data-ttu-id="fc916-122">Clique em **OK** para fechar a mensagem de erro e continuar a usar a pasta de trabalho e as Segmentações de Dados sem problema.</span><span class="sxs-lookup"><span data-stu-id="fc916-122">Click **OK** to close the error message and proceed to use the workbook and Slicers with no problem.</span></span>  
  
  
