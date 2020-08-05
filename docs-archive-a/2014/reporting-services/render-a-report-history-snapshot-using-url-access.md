---
title: Renderizar um instantâneo do histórico de relatórios usando o acesso à URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services], report history
- history snapshots [Reporting Services]
- historical data [Reporting Services]
- snapshots [Reporting Services], URL access
- snapshots [Reporting Services], rendering report history
ms.assetid: 3f87f82d-0e61-4492-9c4b-f5238c39e8cd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 67854a39ab7e38289627d03ac00cc4b2a6dca6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573793"
---
# <a name="render-a-report-history-snapshot-using-url-access"></a><span data-ttu-id="92a22-102">Renderizar instantâneo de histórico de relatório com o acesso à URL</span><span class="sxs-lookup"><span data-stu-id="92a22-102">Render a Report History Snapshot Using URL Access</span></span>
  <span data-ttu-id="92a22-103">Você pode renderizar um relatório com base em um instantâneo de histórico de relatório fornecendo o parâmetro *rs:Snapshot* e definindo seu valor como uma ID de instantâneo válida.</span><span class="sxs-lookup"><span data-stu-id="92a22-103">You can render a report based on a report history snapshot by supplying the *rs:Snapshot* parameter and setting its value to a valid snapshot ID.</span></span> <span data-ttu-id="92a22-104">O valor do parâmetro está no formato AAAA-MM-DDTHH:MM:SS, com base no padrão ISO (Organização Internacional de Padronização) 8601.</span><span class="sxs-lookup"><span data-stu-id="92a22-104">The parameter value is in the format YYYY-MM-DDTHH:MM:SS, based on the International Organization for Standardization (ISO) 8601 standard.</span></span>  
  
 <span data-ttu-id="92a22-105">Se você omitir esse parâmetro, o relatório será renderizado de acordo com a execução do relatório e das configurações da opção de gerenciamento de cache do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="92a22-105">If you omit this parameter, the report is rendered according to the report execution and cache management option settings of the report server.</span></span> <span data-ttu-id="92a22-106">Para obter mais informações sobre a execução do relatório, consulte [Definir as propriedades do processamento de relatórios](report-server/set-report-processing-properties.md).</span><span class="sxs-lookup"><span data-stu-id="92a22-106">For more information about report execution, see [Set Report Processing Properties](report-server/set-report-processing-properties.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92a22-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="92a22-107">Example</span></span>  
 <span data-ttu-id="92a22-108">O exemplo a seguir mostra uma URL que recupera um instantâneo de histórico de relatório:</span><span class="sxs-lookup"><span data-stu-id="92a22-108">The following example shows a URL that retrieves a report history snapshot:</span></span>  
  
```  
http://myrshost/reportserver?/SampleReports/Company Sales&rs:Snapshot=2003-04-07T13:40:02  
```  
  
## <a name="see-also"></a><span data-ttu-id="92a22-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92a22-109">See Also</span></span>  
 <span data-ttu-id="92a22-110">[Acesso à URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="92a22-110">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="92a22-111">Referência de parâmetro de acesso de URL</span><span class="sxs-lookup"><span data-stu-id="92a22-111">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
