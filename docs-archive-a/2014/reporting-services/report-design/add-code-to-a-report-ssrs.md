---
title: Adicionar um código a um relatório (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom code [Reporting Services]
- expressions [Reporting Services], code
- adding code
- reports [Reporting Services], code
ms.assetid: 00ef8fc6-99fe-49b2-8a22-7eb475881dc4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c1964e69d00e1a27da29ce8cfb73b7bee1bece7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681443"
---
# <a name="add-code-to-a-report-ssrs"></a><span data-ttu-id="20b02-102">Adicionar código a um relatório (SSRS)</span><span class="sxs-lookup"><span data-stu-id="20b02-102">Add Code to a Report (SSRS)</span></span>
  <span data-ttu-id="20b02-103">Em qualquer expressão, você pode chamar seu próprio código personalizado.</span><span class="sxs-lookup"><span data-stu-id="20b02-103">In any expression, you can call your own custom code.</span></span> <span data-ttu-id="20b02-104">Você pode fornecer código das duas maneiras a seguir:</span><span class="sxs-lookup"><span data-stu-id="20b02-104">You can provide code in the following two ways:</span></span>  
  
-   <span data-ttu-id="20b02-105">Insira código gravado no [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] diretamente no seu relatório.</span><span class="sxs-lookup"><span data-stu-id="20b02-105">Embed code written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] directly in your report.</span></span> <span data-ttu-id="20b02-106">Se o código fizer referência a um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que não é <xref:System.Math> nem <xref:System.Convert>, você deverá adicionar a referência ao relatório.</span><span class="sxs-lookup"><span data-stu-id="20b02-106">If your code refers to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that is not <xref:System.Math> or <xref:System.Convert>, you must add the reference to the report.</span></span> <span data-ttu-id="20b02-107">Para obter mais informações, consulte [Adicionar uma referência de assembly a um relatório &#40;SSRS&#41;](add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="20b02-107">For more information, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](add-an-assembly-reference-to-a-report-ssrs.md).</span></span> <span data-ttu-id="20b02-108">Para obter mais informações sobre outras referências que podem ser feitas no código, consulte [Referências a código personalizado e assemblies em expressões no Designer de Relatórios &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="20b02-108">For more information about other references you can make from your code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
-   <span data-ttu-id="20b02-109">Forneça um assembly de código personalizado usando o [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20b02-109">Provide a custom code assembly by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="20b02-110">Se você fornecer um assembly personalizado, deverá instalá-lo no computador no qual o relatório é criado e no servidor de relatórios no qual o relatório é exibido.</span><span class="sxs-lookup"><span data-stu-id="20b02-110">If you provide a custom assembly, you must install it on both the computer where you author the report and the report server where you view the report.</span></span> <span data-ttu-id="20b02-111">Para obter mais informações, consulte [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md).</span><span class="sxs-lookup"><span data-stu-id="20b02-111">For more information, see [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md).</span></span>  
  
### <a name="to-add-embedded-code-to-a-report"></a><span data-ttu-id="20b02-112">Para adicionar código inserido em um relatório</span><span class="sxs-lookup"><span data-stu-id="20b02-112">To add embedded code to a report</span></span>  
  
1.  <span data-ttu-id="20b02-113">No modo de exibição de **Design** , clique com o botão direito do mouse na superfície de design fora da borda do relatório e clique em **Propriedades do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="20b02-113">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="20b02-114">Clique em **Código**.</span><span class="sxs-lookup"><span data-stu-id="20b02-114">Click **Code**.</span></span>  
  
3.  <span data-ttu-id="20b02-115">No **Código personalizado**, digite o código.</span><span class="sxs-lookup"><span data-stu-id="20b02-115">In **Custom code**, type the code.</span></span> <span data-ttu-id="20b02-116">Erros no código geram avisos quando o relatório é executado.</span><span class="sxs-lookup"><span data-stu-id="20b02-116">Errors in the code produce warnings when the report runs.</span></span> <span data-ttu-id="20b02-117">O exemplo a seguir cria uma função personalizada chamada `ChangeWord` que substitui a palavra "`Bike`" por "`Bicycle`".</span><span class="sxs-lookup"><span data-stu-id="20b02-117">The following example creates a custom function named `ChangeWord` that replaces the word "`Bike`" with "`Bicycle`".</span></span>  
  
    ```  
    Public Function ChangeWord(ByVal s As String) As String  
       Dim strBuilder As New System.Text.StringBuilder(s)  
       If s.Contains("Bike") Then  
          strBuilder.Replace("Bike", "Bicycle")  
          Return strBuilder.ToString()  
          Else : Return s  
       End If  
    End Function  
    ```  
  
4.  <span data-ttu-id="20b02-118">O exemplo a seguir mostra como transmitir um campo de conjunto de dados nomeado Categoria para esta função em uma expressão:</span><span class="sxs-lookup"><span data-stu-id="20b02-118">The following example shows how to pass a dataset field named Category to this function in an expression:</span></span>  
  
    ```  
    =Code.ChangeWord(Fields!Category.Value)  
    ```  
  
     <span data-ttu-id="20b02-119">Se você adicionar essa expressão a uma célula de tabela que exibe valores de categoria, sempre que a palavra "Bike" estiver no campo de conjunto de dados daquela linha, o valor da célula de tabela exibirá a palavra "Bicicleta".</span><span class="sxs-lookup"><span data-stu-id="20b02-119">If you add this expression to a table cell that displays category values, whenever the word "Bike" is in the dataset field for that row, the table cell value displays the word "Bicycle" instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b02-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="20b02-120">See Also</span></span>  
 <span data-ttu-id="20b02-121">[Caixa de diálogo Propriedades do Relatório, Código](../report-properties-dialog-box-code.md) </span><span class="sxs-lookup"><span data-stu-id="20b02-121">[Report Properties Dialog Box, Code](../report-properties-dialog-box-code.md) </span></span>  
 <span data-ttu-id="20b02-122">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="20b02-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="20b02-123">Referências de coleções de parâmetros &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="20b02-123">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
