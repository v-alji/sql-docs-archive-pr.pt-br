---
title: Pesquisar um relatório usando o acesso à URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- searching reports
- text searches [Reporting Services]
- URL access [Reporting Services], report searches
ms.assetid: 6f3410c4-7944-448f-bae8-bab3e8152d46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b45f3fabf58a0980d41ee7b4b89a771655477d02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684484"
---
# <a name="search-a-report-using-url-access"></a><span data-ttu-id="1a65e-102">Pesquisar um relatório com acesso à URL</span><span class="sxs-lookup"><span data-stu-id="1a65e-102">Search a Report Using URL Access</span></span>
  <span data-ttu-id="1a65e-103">Você pode pesquisar um relatório para obter um conjunto específico de texto usando o acesso de URL.</span><span class="sxs-lookup"><span data-stu-id="1a65e-103">You can search a report for a specific set of text using URL access.</span></span> <span data-ttu-id="1a65e-104">Para pesquisar um relatório, defina o valor do parâmetro *rc:FindString* na URL igual ao texto para o qual você deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="1a65e-104">To search a report, set the value of the *rc:FindString* parameter on the URL equal to the text for which you want to search.</span></span> <span data-ttu-id="1a65e-105">Além disso, use os parâmetros *rc:StartFind* e *rc:EndFind* para estreitar sua pesquisa a páginas específicas dentro do relatório.</span><span class="sxs-lookup"><span data-stu-id="1a65e-105">Additionally, use the *rc:StartFind* and *rc:EndFind* parameters to narrow your search to specific pages within the report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a65e-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1a65e-106">Example</span></span>  
 <span data-ttu-id="1a65e-107">Este exemplo de acesso de URL procura a primeira ocorrência do texto "Mountain-400" no relatório de exemplo Catálogo de Produtos começando pela primeira página e terminando na página cinco:</span><span class="sxs-lookup"><span data-stu-id="1a65e-107">The following URL access example searches for the first occurrence of the text "Mountain-400" in the Product Catalog sample report starting with page one and ending with page five:</span></span>  
  
```  
http://server/Reportserver?/SampleReports/Product Catalog&rs:Command=Render&rc:StartFind=1&rc:EndFind=5&rc:FindString=Mountain-400  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a65e-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1a65e-108">See Also</span></span>  
 <span data-ttu-id="1a65e-109">[Acesso à URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1a65e-109">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="1a65e-110">Referência de parâmetro de acesso de URL</span><span class="sxs-lookup"><span data-stu-id="1a65e-110">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
