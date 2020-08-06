---
title: Exportar um relatório usando o acesso à URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- formats [Reporting Services], URL rendering
- URL access [Reporting Services], rendering formats
ms.assetid: 6a3b7fc3-3d91-4d12-8371-42ea12e74517
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 69f340855e37ffde49aec0af096c094a142659d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678653"
---
# <a name="export-a-report-using-url-access"></a><span data-ttu-id="64420-102">Exportar um relatório com acesso à URL</span><span class="sxs-lookup"><span data-stu-id="64420-102">Export a Report Using URL Access</span></span>
  <span data-ttu-id="64420-103">Opcionalmente, você pode especificar o formato no qual renderizar um relatório usando o parâmetro *RS: Format* .</span><span class="sxs-lookup"><span data-stu-id="64420-103">You can optionally specify the format in which to render a report by using the *rs:Format* parameter.</span></span> <span data-ttu-id="64420-104">Por exemplo, para obter uma cópia em PDF de um relatório diretamente de um servidor de relatório de modo nativo:</span><span class="sxs-lookup"><span data-stu-id="64420-104">For example, to get a PDF copy of a report directly from a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/myreport&rs:Format=PDF  
```  
  
 <span data-ttu-id="64420-105">E, em um servidor de relatório no modo integrado do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="64420-105">And, from a SharePoint integrated mode report server:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/myrereport.rdl&rs:Format=PDF  
```  
  
 <span data-ttu-id="64420-106">Os valores válidos desse parâmetro se baseiam nas extensões de renderização de relatório que estão instaladas no servidor de relatório que está sendo acessado.</span><span class="sxs-lookup"><span data-stu-id="64420-106">Valid values for this parameter are based on the report rendering extensions that are installed on the report server being accessed.</span></span> <span data-ttu-id="64420-107">Extensões comuns são HTML4.0, MHTML, IMAGE, EXCEL, WORD, CSV, PDF, XML e NULL.</span><span class="sxs-lookup"><span data-stu-id="64420-107">Common extensions are HTML4.0, MHTML, IMAGE, EXCEL, WORD, CSV, PDF, XML, and NULL.</span></span> <span data-ttu-id="64420-108">Se uma extensão de renderização especificada não estiver instalada no servidor de relatórios, o relatório não será renderizado, e um erro será gerado e exibido no pesquisador.</span><span class="sxs-lookup"><span data-stu-id="64420-108">If a specified rendering extension is not installed on the report server, the report is not rendered and an error is generated and displayed in the browser.</span></span>  
  
 <span data-ttu-id="64420-109">Se você não incluir o parâmetro *Format* como parte da URL, o servidor de relatórios detectará o pesquisador e renderizará o relatório no formato HTML apropriado.</span><span class="sxs-lookup"><span data-stu-id="64420-109">If you do not include the *Format* parameter as part of the URL, the report server detects the browser and renders the report in the appropriate HTML format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64420-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="64420-110">See Also</span></span>  
 <span data-ttu-id="64420-111">[Acesso à URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="64420-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="64420-112">Referência de parâmetro de acesso de URL</span><span class="sxs-lookup"><span data-stu-id="64420-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
