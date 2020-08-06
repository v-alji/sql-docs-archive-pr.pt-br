---
title: Formato de arquivo de saída XML (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose]
- ssbdiagnose
ms.assetid: 3ceb991b-6f15-4504-8828-de5adf448bc5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 612b317f7220f502faf1adc82cf9c1dcc8bc20a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683232"
---
# <a name="xml-output-file-format-ssbdiagnose"></a><span data-ttu-id="d433c-102">Formato de arquivo de saída XML (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="d433c-102">XML Output File Format (ssbdiagnose)</span></span>
  <span data-ttu-id="d433c-103">O utilitário **ssbdiagnose** entrega sua saída como um arquivo XML quando você o executa com a opção **-XML** .</span><span class="sxs-lookup"><span data-stu-id="d433c-103">The **ssbdiagnose** utility delivers its output as an XML file when you run it with the **-XML** switch.</span></span> <span data-ttu-id="d433c-104">O arquivo de saída XML lista informações de cabeçalho e erros encontrados na configuração ou conversa do [!INCLUDE[ssSB](../../includes/sssb-md.md)] analisadas.</span><span class="sxs-lookup"><span data-stu-id="d433c-104">The XML output file lists header information and the errors that it found in the [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration or conversation that was analyzed.</span></span> <span data-ttu-id="d433c-105">Você pode escrever um aplicativo para analisar ou reportar os erros listados no arquivo.</span><span class="sxs-lookup"><span data-stu-id="d433c-105">You can write an application to analyze or report on the errors listed in the file.</span></span> <span data-ttu-id="d433c-106">Ou pode exibir o arquivo de XML em um editor de XML geral, como o Bloco de Notas XML.</span><span class="sxs-lookup"><span data-stu-id="d433c-106">Or, you can view the XML file in a general XML editor, such as XML Notepad.</span></span>  
  
 <span data-ttu-id="d433c-107">Um arquivo de saída do **ssbdiangose** contém um elemento raiz DiagnosticInformation com dois tipos de filho:</span><span class="sxs-lookup"><span data-stu-id="d433c-107">An **ssbdiangose** output file contains a DiagnosticInformation root element with two child types:</span></span>  
  
-   <span data-ttu-id="d433c-108">Um elemento Banner com informações de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="d433c-108">A Banner element with header information.</span></span>  
  
-   <span data-ttu-id="d433c-109">Um elemento Issue para cada problema reportado por **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="d433c-109">An Issue element for each issue that is reported by **ssbdiagnose**.</span></span>  
  
## <a name="diagnosticinformation-root-element"></a><span data-ttu-id="d433c-110">Elemento raiz DiagnosticInformation</span><span class="sxs-lookup"><span data-stu-id="d433c-110">DiagnosticInformation Root Element</span></span>  
  
-   [<span data-ttu-id="d433c-111">Elemento DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="d433c-111">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)  
  
## <a name="banner-element"></a><span data-ttu-id="d433c-112">Elemento Banner</span><span class="sxs-lookup"><span data-stu-id="d433c-112">Banner Element</span></span>  
  
-   [<span data-ttu-id="d433c-113">Elemento Banner &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="d433c-113">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)  
  
## <a name="issue-element"></a><span data-ttu-id="d433c-114">Elemento Issue</span><span class="sxs-lookup"><span data-stu-id="d433c-114">Issue Element</span></span>  
  
-   [<span data-ttu-id="d433c-115">Elemento Issue &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="d433c-115">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)  
  
## <a name="see-also"></a><span data-ttu-id="d433c-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d433c-116">See Also</span></span>  
 [<span data-ttu-id="d433c-117">Utilitário ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="d433c-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
