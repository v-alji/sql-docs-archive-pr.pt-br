---
title: Adicionar uma referência de assembly a um relatório (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom assemblies [Reporting Services], referencing
- custom code [Reporting Services]
- adding assembly references
- assemblies [Reporting Services], references
ms.assetid: 0a03939e-48ce-4c30-b227-98533f2e0ccb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23dda0c65589e55849f906c621e42ce70f0d7ab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576221"
---
# <a name="add-an-assembly-reference-to-a-report-ssrs"></a><span data-ttu-id="0f76c-102">Adicionar uma referência de assembly a um relatório (SSRS)</span><span class="sxs-lookup"><span data-stu-id="0f76c-102">Add an Assembly Reference to a Report (SSRS)</span></span>
  <span data-ttu-id="0f76c-103">Quando você insere o código personalizado que contém referências a classes [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que não estão no <xref:System.Math> ou <xref:System.Convert>, você deve fornecer uma referência de assembly ao relatório para que o processador de relatórios possa resolver os nomes.</span><span class="sxs-lookup"><span data-stu-id="0f76c-103">When you embed custom code that contains references to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that are not in <xref:System.Math> or <xref:System.Convert>, you must provide an assembly reference to the report so that the report processor can resolve the names.</span></span> <span data-ttu-id="0f76c-104">Para obter mais informações, consulte [Adicionar código a um relatório &#40;SSRS&#41;](add-code-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0f76c-104">For more information, see [Add Code to a Report &#40;SSRS&#41;](add-code-to-a-report-ssrs.md).</span></span>  
  
### <a name="to-add-an-assembly-reference-to-a-report"></a><span data-ttu-id="0f76c-105">Para adicionar uma referência de assembly a um relatório</span><span class="sxs-lookup"><span data-stu-id="0f76c-105">To add an assembly reference to a report</span></span>  
  
1.  <span data-ttu-id="0f76c-106">No modo de exibição de **Design** , clique com o botão direito do mouse na superfície de design fora da borda do relatório e clique em **Propriedades do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="0f76c-106">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="0f76c-107">Clique em **Referências**.</span><span class="sxs-lookup"><span data-stu-id="0f76c-107">Click **References**.</span></span>  
  
3.  <span data-ttu-id="0f76c-108">Em **Adicionar ou remover assemblies**, clique em **Adicionar** e clique no botão de reticências para procurar para o assembly.</span><span class="sxs-lookup"><span data-stu-id="0f76c-108">In **Add or remove assemblies**, click **Add** and then click the ellipsis button to browse to the assembly.</span></span>  
  
4.  <span data-ttu-id="0f76c-109">Em **Adicionar ou remover classes**, clique em **Adicionar** e digite o nome da classe e forneça um nome de instância a ser usado no relatório.</span><span class="sxs-lookup"><span data-stu-id="0f76c-109">In **Add or remove classes**, click **Add** and then type name of the class and provide an instance name to use within the report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0f76c-110">Especifique uma classe e um nome de instância somente para membros com base em instâncias.</span><span class="sxs-lookup"><span data-stu-id="0f76c-110">Specify a class and instance name only for instance-based members.</span></span> <span data-ttu-id="0f76c-111">Não especifique os membros estáticos na lista **Classes** .</span><span class="sxs-lookup"><span data-stu-id="0f76c-111">Do not specify static members in the **Classes** list.</span></span> <span data-ttu-id="0f76c-112">Para obter mais informações, consulte [Referências a código personalizado e assemblies em expressões no Designer de Relatórios &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0f76c-112">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0f76c-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0f76c-113">See Also</span></span>  
 <span data-ttu-id="0f76c-114">[Usando assemblies personalizados com relatórios](../custom-assemblies/using-custom-assemblies-with-reports.md) </span><span class="sxs-lookup"><span data-stu-id="0f76c-114">[Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md) </span></span>  
 [<span data-ttu-id="0f76c-115">Caixa de diálogo Propriedades do Relatório, Referências</span><span class="sxs-lookup"><span data-stu-id="0f76c-115">Report Properties Dialog Box, References</span></span>](../report-properties-dialog-box-references.md)  
  
  
