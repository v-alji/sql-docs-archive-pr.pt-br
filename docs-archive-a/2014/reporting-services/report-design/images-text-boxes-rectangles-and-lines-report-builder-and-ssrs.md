---
title: Imagens, caixas de texto, retângulos e linhas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aa7ad08f-dd49-401e-9619-522e27055bb9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fb9a47bb3b8d68d48be42f8f0a2adddfc3ba130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679706"
---
# <a name="images-text-boxes-rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="25a19-102">Imagens, caixas de texto, retângulos e linhas (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="25a19-102">Images, Text Boxes, Rectangles, and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="25a19-103">Além das regiões de dados, como tabelas, matrizes e gráficos, os relatórios usam outros itens de relatório, como imagens, caixas de texto e retângulos, para adicionar interesse visual, realçar informações importantes ou fornecer informações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="25a19-103">In addition to data regions like tables, matrices, and charts, reports use other report items like images, text boxes, and rectangles to add visual interest, highlight key information, or provide related information.</span></span> <span data-ttu-id="25a19-104">É possível alterar a formatação de um item de relatório.</span><span class="sxs-lookup"><span data-stu-id="25a19-104">You can change the formatting of a report item.</span></span> <span data-ttu-id="25a19-105">Por exemplo, você pode adicionar uma borda ou um preenchimento, alterar a visibilidade inicial ou a direção ou especificar um tamanho e local exatos para o item.</span><span class="sxs-lookup"><span data-stu-id="25a19-105">For example, you can add a border or padding, change the initial visibility or direction, or specify an exact size and location for the item.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="25a19-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="25a19-106">In This Section</span></span>  
 [<span data-ttu-id="25a19-107">Caixas de texto &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="25a19-107">Text Boxes &#40;Report Builder and SSRS&#41;</span></span>](text-boxes-report-builder-and-ssrs.md)  
 <span data-ttu-id="25a19-108">As caixas de texto podem ser colocadas em qualquer lugar em um relatório e podem conter rótulos, campos ou dados calculados.</span><span class="sxs-lookup"><span data-stu-id="25a19-108">Text boxes can be placed anywhere on a report and can contain labels, fields, or calculated data.</span></span> <span data-ttu-id="25a19-109">As expressões são usadas para definir o valor a ser exibido em uma caixa de texto quando você exibe um relatório.</span><span class="sxs-lookup"><span data-stu-id="25a19-109">You use expressions to define the value to display in a text box when you view a report.</span></span>  
  
 <span data-ttu-id="25a19-110">Todas as células de uma tabela ou matriz também são uma caixa de texto, que podem ser formatadas da mesma forma que caixas de texto autônomas.</span><span class="sxs-lookup"><span data-stu-id="25a19-110">Every cell in a table or matrix is also a text box, which you can format in the same way that you format stand-alone text boxes.</span></span>  
  
 [<span data-ttu-id="25a19-111">Retângulos e linhas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="25a19-111">Rectangles and Lines &#40;Report Builder and SSRS&#41;</span></span>](rectangles-and-lines-report-builder-and-ssrs.md)  
 <span data-ttu-id="25a19-112">**Linhas** são exibidas horizontal, vertical ou diagonalmente.</span><span class="sxs-lookup"><span data-stu-id="25a19-112">**Lines** display horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="25a19-113">Uma linha é definida com um ponto de início e de término e pode ter vários estilos (por exemplo, peso e cor) atribuídos a ela.</span><span class="sxs-lookup"><span data-stu-id="25a19-113">A line is defined with a start and end point and can have various styles (for example, weight and color) assigned to it.</span></span> <span data-ttu-id="25a19-114">Uma linha não possui dados associados a ela.</span><span class="sxs-lookup"><span data-stu-id="25a19-114">A line has no data associated with it.</span></span>  
  
 <span data-ttu-id="25a19-115">**Os retângulos** podem ser usados como um elemento gráfico e como um contêiner para outros itens de relatório.</span><span class="sxs-lookup"><span data-stu-id="25a19-115">**Rectangles** can be used as a graphical element, or as a container for other report items.</span></span> <span data-ttu-id="25a19-116">Como um elemento gráfico, um retângulo possui as mesmas propriedades de uma linha.</span><span class="sxs-lookup"><span data-stu-id="25a19-116">As a graphical element, a rectangle has the same properties as a line.</span></span> <span data-ttu-id="25a19-117">Como um contêiner, um retângulo funciona como um contêiner pai para todos os itens de relatório dentro dele.</span><span class="sxs-lookup"><span data-stu-id="25a19-117">As a container, a rectangle acts as a parent container for all report items inside it.</span></span> <span data-ttu-id="25a19-118">Colocar itens de relatório em um contêiner pai ajuda a controlar o modo como eles são exibidos em cada página do relatório.</span><span class="sxs-lookup"><span data-stu-id="25a19-118">Placing report items in a parent container helps control how they appear on each report page.</span></span>  
  
 [<span data-ttu-id="25a19-119">Imagens &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="25a19-119">Images &#40;Report Builder and SSRS&#41;</span></span>](images-report-builder-and-ssrs.md)  
 <span data-ttu-id="25a19-120">As imagens exibem dados de imagem binária em um relatório.</span><span class="sxs-lookup"><span data-stu-id="25a19-120">Images display binary image data in a report.</span></span> <span data-ttu-id="25a19-121">Você fornece a origem da imagem.</span><span class="sxs-lookup"><span data-stu-id="25a19-121">You provide the source for the image.</span></span> <span data-ttu-id="25a19-122">A origem pode ser uma referência à URL para uma imagem armazenada em um servidor da Web, uma referência aos dados da imagem inserida ou uma referência aos dados da imagem binária em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25a19-122">The source can be a URL reference to an image stored on a Web server, a reference to embedded image data, or a reference to binary image data in a database.</span></span> <span data-ttu-id="25a19-123">O Construtor de Relatórios e o Designer de Relatórios dão suporte a arquivos .bmp, .jpeg, .gif e .png.</span><span class="sxs-lookup"><span data-stu-id="25a19-123">Report Builder and Report Designer support .bmp, .jpeg, .gif, and .png files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25a19-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25a19-124">See Also</span></span>  
 [<span data-ttu-id="25a19-125">Formatando itens de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="25a19-125">Formatting Report Items &#40;Report Builder and SSRS&#41;</span></span>](formatting-report-items-report-builder-and-ssrs.md)  
  
  
