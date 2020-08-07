---
title: Definir atribuições e outros comandos de script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- empty scripts [Analysis Services]
- calculations [Analysis Services], scripts
- MDX [Analysis Services], scripts
- scripts [Analysis Services], calculations
ms.assetid: f28b9b22-3dc7-4a45-b4eb-2d023f2c94b8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 184c998bb4bd27d077cca78e792a7e7712f87666
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581566"
---
# <a name="define-assignments-and-other-script-commands"></a><span data-ttu-id="d8425-102">Definir atribuições e outros comandos de script</span><span class="sxs-lookup"><span data-stu-id="d8425-102">Define Assignments and Other Script Commands</span></span>
  <span data-ttu-id="d8425-103">Para criar um script vazio, no Designer de Cubo, na guia **Cálculos** , clique no ícone **Novo ScriptCommand** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="d8425-103">On the **Calculations** tab of Cube Designer, click the **New ScriptCommand** icon on the toolbar to create an empty script.</span></span> <span data-ttu-id="d8425-104">Quando você cria um novo script, inicialmente ele é exibido com um título em branco no painel **organizador de script** da guia cálculos. Os caracteres que você digitar no painel expressões de cálculo ficarão visíveis como o nome do item no **organizador de script**.</span><span class="sxs-lookup"><span data-stu-id="d8425-104">When you create a new script, it initially is displayed with a blank title in the **Script Organizer** pane of the Calculations tab. The characters you type in the Calculation Expressions pane will be visible as the name of the item in **Script Organizer**.</span></span> <span data-ttu-id="d8425-105">Portanto, convém digitar um nome comentado na primeira linha para facilitar a identificação do script no painel **Organizador de Script** .</span><span class="sxs-lookup"><span data-stu-id="d8425-105">Therefore, you may want to type a commented name on the first line to more easily identify the script in the **Script Organizer** pane.</span></span> <span data-ttu-id="d8425-106">Para obter mais informações, consulte [Introdução ao script MDX no Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span><span class="sxs-lookup"><span data-stu-id="d8425-106">For more information, see [Introduction to MDX Scripting in Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span></span> <span data-ttu-id="d8425-107">Para obter mais informações sobre problemas de desempenho relacionados a cálculos e consultas MDX, consulte a seção "escrevendo MDX eficiente" no [Guia de desempenho do SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="d8425-107">For more information about performance issues related to MDX queries and calculations, see the section "Writing Efficient MDX" in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d8425-108">Quando você inicialmente muda para a guia **Cálculos** do Designer de Cubo, o painel **Organizador de Script** contém um único script com um comando CALCULATE.</span><span class="sxs-lookup"><span data-stu-id="d8425-108">When you initially switch to the **Calculations** tab of Cube Designer, the **Script Organizer** pane contains a single script with a CALCULATE command.</span></span> <span data-ttu-id="d8425-109">O comando CALCULATE controla a agregação das células do cubo e deve ser editado somente se você pretender especificar manualmente como o cubo será agregado.</span><span class="sxs-lookup"><span data-stu-id="d8425-109">The CALCULATE command controls the aggregation of the cells in the cube and should be edited only if you intend to manually specify how the cube is to be aggregated.</span></span>  
  
 <span data-ttu-id="d8425-110">Você pode usar o painel Expressões de Cálculo para construir uma expressão em sintaxe MDX.</span><span class="sxs-lookup"><span data-stu-id="d8425-110">You can use the Calculation Expressions pane to build an expression in Multidimensional Expressions (MDX) syntax.</span></span> <span data-ttu-id="d8425-111">Ao criar a expressão, você pode copiar ou arrastar os componentes, funções e modelos do cubo do painel **Ferramentas de Cálculo** para o painel Expressões de Cálculo.</span><span class="sxs-lookup"><span data-stu-id="d8425-111">While you build the expression, you can drag or copy cube components, functions, and templates from the **Calculation Tools** pane to the Calculation Expressions pane.</span></span> <span data-ttu-id="d8425-112">Isso adicionará o script do item ao painel Expressões de Cálculo no local para onde você o arrastar ou copiar.</span><span class="sxs-lookup"><span data-stu-id="d8425-112">Doing so adds the script for the item to the Calculation Expressions pane in the location that you drop or paste it.</span></span> <span data-ttu-id="d8425-113">Substitua os argumentos e seus delimitadores (« e ») pelos valores apropriados.</span><span class="sxs-lookup"><span data-stu-id="d8425-113">Replace arguments and their delimiters (« and ») with the appropriate values.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d8425-114">Ao gravar uma expressão que contém várias instruções usando o painel Expressões de Cálculo, certifique-se de que todas as linhas do script MDX, exceto a última, terminam com um ponto-e-vírgula (;).</span><span class="sxs-lookup"><span data-stu-id="d8425-114">When writing an expression that contains multiple statements using the Calculation Expressions pane, ensure that all lines except the last line of the MDX script end with a semi-colon (;).</span></span> <span data-ttu-id="d8425-115">Os cálculos são concatenados em um único script MDX e cada script possui um ponto-e-vírgula anexado a ele para garantir a compilação correta do script MDX.</span><span class="sxs-lookup"><span data-stu-id="d8425-115">Calculations are concatenated into a single MDX script, and each script has a semi-colon appended to it to ensure that the MDX script compiles correctly.</span></span> <span data-ttu-id="d8425-116">Se você adicionar um ponto-e-vírgula à última linha do script no painel Expressões de Cálculo, o cubo será construído e implantado corretamente, mas não será possível executar consultas nele.</span><span class="sxs-lookup"><span data-stu-id="d8425-116">If you add a semi-colon to the last line of the script in the Calculation Expressions pane, the cube will build and deploy correctly but you will be unable to run queries against it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8425-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d8425-117">See Also</span></span>  
 [<span data-ttu-id="d8425-118">Cálculos em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="d8425-118">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)  
  
  
