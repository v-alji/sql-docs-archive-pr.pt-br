---
title: Definir o idioma para parâmetros de relatório em uma URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- overriding report language settings
- report servers [Reporting Services], language settings
- languages [Reporting Services]
- URL access [Reporting Services], language overrides
- international considerations [Reporting Services]
- global considerations [Reporting Services]
ms.assetid: e1ccf22f-80d6-45bc-aae0-f5f263275092
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8087a181906517bb60d4cd6839eed0681f52a5eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680806"
---
# <a name="set-the-language-for-report-parameters-in-a-url"></a><span data-ttu-id="311ec-102">Definir o idioma dos parâmetros do relatório em uma URL</span><span class="sxs-lookup"><span data-stu-id="311ec-102">Set the Language for Report Parameters in a URL</span></span>
  <span data-ttu-id="311ec-103">O parâmetro de acesso de URL *rs:ParameterLanguage* reduz o problema de os parâmetros de relatório sensíveis a cultura, como datas, horas, moeda e números serem interpretados por meio do idioma do navegador.</span><span class="sxs-lookup"><span data-stu-id="311ec-103">The *rs:ParameterLanguage* URL access parameter alleviates a problem in which culture-sensitive report parameters, such as dates, times, currency, and numbers, are interpreted using the browser language.</span></span> <span data-ttu-id="311ec-104">Com o *rs:ParameterLanguage*, a URL agora é interpretada independentemente do navegador.</span><span class="sxs-lookup"><span data-stu-id="311ec-104">With *rs:ParameterLanguage*, the URL is now interpreted independently of the browser.</span></span> <span data-ttu-id="311ec-105">Por exemplo, se o servidor de relatório for definido como uma configuração regional do alemão, mas um usuário estiver acessando um relatório via uma URL usando um navegador definido com inglês norte-americano, os valores do parâmetro que são transmitidos para um servidor de relatório serão interpretados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="311ec-105">For example, if the report server is set to a regional setting of German, but a user is accessing a report via a URL using a browser that is set to English-United States, parameter values that are passed to a report server will be misinterpreted.</span></span>  
  
 <span data-ttu-id="311ec-106">Considere a URL a seguir para um relatório:</span><span class="sxs-lookup"><span data-stu-id="311ec-106">Consider the following URL to a report:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008  
```  
  
 <span data-ttu-id="311ec-107">No caso acima, o servidor, executado em uma cultura de "de-de", gera uma URL por meio de uma assinatura de e-mail ou um hiperlink.</span><span class="sxs-lookup"><span data-stu-id="311ec-107">In the above case, the server, running under a culture of "de-de", generates a URL either through an e-mail subscription or a hyperlink.</span></span> <span data-ttu-id="311ec-108">O hyperlink indica que o relatório deve ser parametrizado pela data de início de 04 de outubro de 2008 e uma data de término de 11 de outubro de 2008 de acordo com os padrões de data/hora alemães.</span><span class="sxs-lookup"><span data-stu-id="311ec-108">The hyperlink indicates that the report should be parameterized by a start date of October 4, 2008 and an end date of October 11, 2008 according to German date/time standards.</span></span> <span data-ttu-id="311ec-109">Entretanto, um usuário que está acessando a URL por meio de um navegador definido como "en-us" força o servidor a interpretar os valores como 10 de abril de 2008 e 10 de novembro de 2008 de acordo com os padrões de data/hora do inglês norte-americano.</span><span class="sxs-lookup"><span data-stu-id="311ec-109">However, a user that is accessing the URL through a browser set to "en-us" forces the server to interpret the values as April 10, 2008 and November 10, 2008 under United States English date/time standards.</span></span> <span data-ttu-id="311ec-110">Para corrigir o problema, o *rs:ParameterLanguage* pode ser usado para substituir o idioma do navegador para interpretação de parâmetro:</span><span class="sxs-lookup"><span data-stu-id="311ec-110">To fix the problem, *rs:ParameterLanguage* can be used to override the browser language for parameter interpretation:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008&rs:ParameterLanguage=de-DE  
```  
  
 <span data-ttu-id="311ec-111">Além de um valor **true** e **false** para o parâmetro de acesso da URL *rc:Parameters*, agora você pode transmitir um valor de **Recolhido**.</span><span class="sxs-lookup"><span data-stu-id="311ec-111">In addition to a value of **true** and **false** for the URL access parameter *rc:Parameters*, you can now pass a value of **Collapsed**.</span></span> <span data-ttu-id="311ec-112">Ao usar *rc:Parameters*=**Recolhido** em uma URL, a área de prompt do parâmetro do visualizador de HTML será recolhida, mas ainda poderá ser alternada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="311ec-112">When using *rc:Parameters*=**Collapsed** on a URL, the parameter prompt area of the HTML viewer is collapsed out of sight, but can still be toggled by the user.</span></span> <span data-ttu-id="311ec-113">Um valor igual a **false** remove a área de prompt de parâmetro da barra de ferramentas do visualizador de HTML e a torna indisponível para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="311ec-113">A value of **false** removes the parameter prompt area from the HTML viewer toolbar and makes it unavailable to the end-user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="311ec-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="311ec-114">See Also</span></span>  
 <span data-ttu-id="311ec-115">[Acesso à URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="311ec-115">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="311ec-116">Referência de parâmetro de acesso de URL</span><span class="sxs-lookup"><span data-stu-id="311ec-116">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
