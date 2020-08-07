---
title: O que&#39;s novos no Construtor de Relatórios para SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8223c19b-4b0d-4b1d-a042-9a726c18e708
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ce72af225130bc3f081a53008a303c5213db636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575012"
---
# <a name="what39s-new-in-report-builder-for-sql-server-2014"></a><span data-ttu-id="480cb-102">O que&#39;s novos no Construtor de Relatórios para SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="480cb-102">What&#39;s New in Report Builder for SQL Server 2014</span></span>
  <span data-ttu-id="480cb-103">O [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] apresenta vários recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="480cb-103">The [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] introduces a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span>  
  
 <span data-ttu-id="480cb-104">Para obter informações sobre os recursos desta versão para outros [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] produtos e tecnologias, consulte [What ' s New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="480cb-104">For information about features in this release for other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="480cb-105">Para obter as informações e os recursos mais recentes relativos aos novos recursos desta versão, consulte [Informações adicionais sobre as novidades do SQL Server Reporting Services (SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span><span class="sxs-lookup"><span data-stu-id="480cb-105">For the most recent information and resources regarding new features in this release, see [Additional information on what is new in SQL Server Reporting Services (SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span></span>  
  
##  <a name="excel-renderer-for-microsoft-excel-2007-2010-and-microsoft-excel-2003"></a><a name="ExcelRenderer"></a><span data-ttu-id="480cb-106">Renderizador do Excel para Microsoft Excel 2007-2010 e Microsoft Excel 2003</span><span class="sxs-lookup"><span data-stu-id="480cb-106">Excel Renderer for Microsoft Excel 2007-2010 and Microsoft Excel 2003</span></span>  
 <span data-ttu-id="480cb-107">A extensão de renderização do Excel do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , nova no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]renderiza um relatório como um documento do Excel compatível com [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010, bem como com [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003 com o Pacote de Compatibilidade do Microsoft Office para Word, Excel e PowerPoint instalado.</span><span class="sxs-lookup"><span data-stu-id="480cb-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Excel rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as an Excel document that is compatible with [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010 as well as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="480cb-108">O formato é o Office Open XML e a extensão de arquivo dos arquivos é .xlsx.</span><span class="sxs-lookup"><span data-stu-id="480cb-108">The format is Office Open XML and the file extension of files is .xlsx.</span></span>  
  
 <span data-ttu-id="480cb-109">Esta extensão de renderização do Excel remove limitações da versão anterior, compatíveis com o Excel 2003.</span><span class="sxs-lookup"><span data-stu-id="480cb-109">This Excel-rendering extension removes limitations of the earlier version, compatible with Excel 2003.</span></span> <span data-ttu-id="480cb-110">Veja uma lista do aperfeiçoamento na extensão de renderização:</span><span class="sxs-lookup"><span data-stu-id="480cb-110">The following lists the improvement in the rendering extension:</span></span>  
  
-   <span data-ttu-id="480cb-111">O máximo de linhas por planilha é 1.048.576.</span><span class="sxs-lookup"><span data-stu-id="480cb-111">Maximum rows per worksheet is 1,048,576.</span></span>  
  
-   <span data-ttu-id="480cb-112">O máximo de colunas por planilha é 16.384.</span><span class="sxs-lookup"><span data-stu-id="480cb-112">Maximum columns per worksheet is 16,384.</span></span>  
  
-   <span data-ttu-id="480cb-113">O número de cores permitidas em uma planilha é aproximadamente de 16 milhões (cor de 24 bits).</span><span class="sxs-lookup"><span data-stu-id="480cb-113">Number of colors allowed in a worksheet is approximately 16 million (24-bit color).</span></span>  
  
-   <span data-ttu-id="480cb-114">A compactação em ZIP fornece tamanhos de arquivos menores.</span><span class="sxs-lookup"><span data-stu-id="480cb-114">ZIP compression provides smaller files sizes.</span></span>  
  
 <span data-ttu-id="480cb-115">Para obter mais informações, consulte [Exportar para Microsoft Excel &#40;Construtor de Relatórios e SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="480cb-115">For more information, see [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="word-renderer-for-microsoft-word-2007-2010-and-microsoft-word-2003"></a><a name="WordRenderer"></a><span data-ttu-id="480cb-116">Renderizador de Word para Microsoft Word 2007-2010 e Microsoft Word 2003</span><span class="sxs-lookup"><span data-stu-id="480cb-116">Word Renderer for Microsoft Word 2007-2010 and Microsoft Word 2003</span></span>  
 <span data-ttu-id="480cb-117">A extensão de renderização do Word do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , nova no [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]renderiza um relatório como um documento do Word compatível com [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010, bem como com [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003 com o Pacote de Compatibilidade do [!INCLUDE[msCoName](../includes/msconame-md.md)] Office para Word, Excel e PowerPoint instalado.</span><span class="sxs-lookup"><span data-stu-id="480cb-117">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Word rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as a Word document that is compatible with [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010 as well as [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003 with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="480cb-118">O formato é o Office Open XML e a extensão de arquivo dos arquivos é docx.</span><span class="sxs-lookup"><span data-stu-id="480cb-118">The format is Office Open XML and the file extension of files is docx.</span></span>  
  
 <span data-ttu-id="480cb-119">Além de disponibilizar os recursos que são novos no Word 2007-2010 para relatórios exportados, os arquivos \*.docx de relatórios exportados tendem a ser menores.</span><span class="sxs-lookup"><span data-stu-id="480cb-119">In addition to making the features that are new in Word 2007-2010 available to exported reports, \*.docx files of exported reports tend to be smaller.</span></span> <span data-ttu-id="480cb-120">Os relatórios exportados usando o renderizador do Word são geralmente significativamente menores que os mesmos relatórios exportados usando o renderizador do Word 2003.</span><span class="sxs-lookup"><span data-stu-id="480cb-120">Reports exported by using the Word renderer are typically significantly smaller than the same reports exported by using the Word 2003 renderer.</span></span>  
  
 <span data-ttu-id="480cb-121">Para obter mais informações, consulte [Exportar para Microsoft Word &#40;Construtor de Relatórios e SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="480cb-121">For more information, see [Exporting to Microsoft Word &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="480cb-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="480cb-122">See Also</span></span>  
 [<span data-ttu-id="480cb-123">Construtor de Relatórios no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="480cb-123">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
