---
title: Definir a localidade em um relatório ou caixa de texto (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- locales [Reporting Services]
ms.assetid: df115b01-184b-47f0-b5ec-0ad965ff9bee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb2b0cbd6e4216138520834216358ee455729386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570441"
---
# <a name="set-the-locale-for-a-report-or-text-box-reporting-services"></a><span data-ttu-id="f3637-102">Definir a localidade em um relatório ou caixa de texto (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="f3637-102">Set the Locale for a Report or Text Box (Reporting Services)</span></span>
  <span data-ttu-id="f3637-103">A propriedade **Language** em um relatório ou caixa de texto contém as configurações de localidade, que determinam os formatos padrão para a exibição dos dados do relatório que são diferenciados por idioma e região, como, por exemplo, data, moeda ou valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="f3637-103">The **Language** property on a report or a text box contains the locale setting, which determines the default formats for displaying report data that differ by language and region, for example, date, currency, or number values.</span></span> <span data-ttu-id="f3637-104">A propriedade **Language** em uma caixa de texto substitui a propriedade **Language** em um relatório.</span><span class="sxs-lookup"><span data-stu-id="f3637-104">The **Language** property on a text box overrides the **Language** property on the report.</span></span> <span data-ttu-id="f3637-105">Quando nenhum valor é especificado para **Language**, o Reporting Services usa a localidade do sistema operacional no servidor de relatórios para os relatórios publicados ou do computador em que o relatório está sendo gerado na visualização do relatório.</span><span class="sxs-lookup"><span data-stu-id="f3637-105">If no value is specified for **Language**, Reporting Services uses the locale of the operating system on the report server for published reports or of the report authoring computer for report preview.</span></span>  
  
 <span data-ttu-id="f3637-106">Em relatórios em HTML, você pode substituir o valor **Idioma** padrão e usar o idioma especificado pelo cabeçalho HTTP do cliente navegador usando o campo interno User!Language em uma expressão para a propriedade **Language** de um relatório ou caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="f3637-106">For HTML reports, you can override the default **Language** value and use the language specified by the HTTP header of the browser client by using the built-in field User!Language in an expression for the **Language** property of a report or a text box.</span></span>  
  
 <span data-ttu-id="f3637-107">A propriedade **Language** também pode ser especificada para um relatório em uma URL.</span><span class="sxs-lookup"><span data-stu-id="f3637-107">You can also specify the **Language** property for a report in a URL.</span></span> <span data-ttu-id="f3637-108">Para mais informações, consulte [Definir o idioma dos parâmetros do relatório em uma URL](../set-the-language-for-report-parameters-in-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="f3637-108">For more information, see [Set the Language for Report Parameters in a URL](../set-the-language-for-report-parameters-in-a-url.md).</span></span>  
  
### <a name="to-set-the-locale-for-a-report"></a><span data-ttu-id="f3637-109">Para definir a localidade para um relatório</span><span class="sxs-lookup"><span data-stu-id="f3637-109">To set the locale for a report</span></span>  
  
1.  <span data-ttu-id="f3637-110">No modo Design, clique fora da superfície de design para selecionar o relatório.</span><span class="sxs-lookup"><span data-stu-id="f3637-110">In Design view, click outside the report design surface to select the report.</span></span>  
  
2.  <span data-ttu-id="f3637-111">No painel Propriedades, na propriedade **Language** , digite ou selecione o idioma que deseja usar no relatório.</span><span class="sxs-lookup"><span data-stu-id="f3637-111">In the Properties pane, for the **Language** property, type or select the language that you want to use for the report.</span></span>  
  
### <a name="to-set-the-locale-for-a-text-box"></a><span data-ttu-id="f3637-112">Para definir a localidade para uma caixa de texto</span><span class="sxs-lookup"><span data-stu-id="f3637-112">To set the locale for a text box</span></span>  
  
1.  <span data-ttu-id="f3637-113">No modo Design, selecione a caixa de texto para a qual você deseja aplicar as configurações de localidade.</span><span class="sxs-lookup"><span data-stu-id="f3637-113">In Design view, select the text box to which you want to apply the locale settings.</span></span>  
  
2.  <span data-ttu-id="f3637-114">No painel Propriedades, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f3637-114">In the Properties pane, do the following:</span></span>  
  
    -   <span data-ttu-id="f3637-115">Na propriedade **Calendar** , digite ou selecione o calendário que deseja usar para as datas.</span><span class="sxs-lookup"><span data-stu-id="f3637-115">For the **Calendar** property, type or select the calendar that you want to use for dates.</span></span>  
  
    -   <span data-ttu-id="f3637-116">Na propriedade **Direction** , digite ou selecione a direção na qual deseja que o texto seja exibido.</span><span class="sxs-lookup"><span data-stu-id="f3637-116">For the **Direction** property, type or select the direction in which the text is written.</span></span>  
  
    -   <span data-ttu-id="f3637-117">Na propriedade **Language** , digite ou selecione o idioma que deseja usar na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="f3637-117">For the **Language** property, type or select the language that you want to use for the text box.</span></span> <span data-ttu-id="f3637-118">Esse valor substitui a propriedade **Language** para o Relatório.</span><span class="sxs-lookup"><span data-stu-id="f3637-118">This value overrides the **Language** property for the Report.</span></span>  
  
    -   <span data-ttu-id="f3637-119">Na propriedade **NumeralLanguage** , digite ou selecione o formato que deseja usar para os números na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="f3637-119">For the **NumeralLanguage** property, type or select the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="f3637-120">Na propriedade **NumeralVariant** , digite ou selecione a variação do formato que deseja usar para os números na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="f3637-120">For the **NumeralVariant** property, type or select the variant of the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="f3637-121">Na propriedade **UnicodeBiDi** , digite ou selecione o nível de inserção bidirecional que deseja usar na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="f3637-121">For the **UnicodeBiDi** property, select the level of bidirectional embedding to use in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3637-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f3637-122">See Also</span></span>  
 [<span data-ttu-id="f3637-123">Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f3637-123">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)  
  
  
