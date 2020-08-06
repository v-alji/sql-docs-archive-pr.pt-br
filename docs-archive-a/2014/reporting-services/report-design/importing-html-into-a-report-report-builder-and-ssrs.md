---
title: Importando HTML para um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dd0410ea-8839-4e8c-9944-8cdfe5465591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f978e67c67556184012db6b809e4f5754f2374c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679703"
---
# <a name="importing-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="a7ba6-102">Importando HTML para um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a7ba6-102">Importing HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a7ba6-103">É possível usar uma caixa de texto para inserir em um relatório um texto formatado em HTML recuperado de um campo em seu conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-103">You can use a text box to insert HTML-formatted text that you have retrieved from a field in your dataset into a report.</span></span> <span data-ttu-id="a7ba6-104">O texto pode ser de qualquer expressão simples ou complexa avaliada como HTML formatado corretamente.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-104">The text can come from any simple or complex expression that evaluates to correctly formatted HTML.</span></span> <span data-ttu-id="a7ba6-105">O texto formatado pode ser renderizado em todos os formatos de saída com suporte, inclusive PDF.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-105">Formatted text can be rendered to all supported output formats, including PDF.</span></span>  
  
 <span data-ttu-id="a7ba6-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span><span class="sxs-lookup"><span data-stu-id="a7ba6-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span></span>  
  
 <span data-ttu-id="a7ba6-107">Esta ilustração mostra texto com formatação HTML em uma exibição de design de relatório, além do mesmo texto como é renderizado quando o relatório é executado.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-107">This illustration shows text with HTML formatting in report design view, and the same text as it is rendered when the report is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7ba6-108">Ao importar texto contendo marcação HTML, os dados sempre devem ser analisados primeiro pela caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-108">When you import text that contains HTML markup, the data must always be parsed by the text box first.</span></span> <span data-ttu-id="a7ba6-109">Como apenas um subconjunto de marcas HTML possui suporte, o HTML mostrado no relatório renderizado pode ser diferente do HTML original.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-109">Because only a subset of HTML tags is supported, the HTML that is shown in the rendered report may differ from your original HTML.</span></span>  
  
 <span data-ttu-id="a7ba6-110">Para começar a usar rapidamente, consulte [Tutorial: Formatar texto &#40;Construtor de Relatórios&#41;](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="a7ba6-110">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="supported-html-tags"></a><span data-ttu-id="a7ba6-111">Tags HTML Suportadas</span><span class="sxs-lookup"><span data-stu-id="a7ba6-111">Supported HTML Tags</span></span>  
 <span data-ttu-id="a7ba6-112">A seguir, há uma lista completa de marcas que são renderizadas como HTML quando definidas como texto de espaço reservado:</span><span class="sxs-lookup"><span data-stu-id="a7ba6-112">The following is a complete list of tags that will render as HTML when defined as placeholder text:</span></span>  
  
-   <span data-ttu-id="a7ba6-113">Elementos de cabeçalho, estilo e bloco: \<H{n}> , \<DIV> , \<SPAN> , \<P> ,\<LI></span><span class="sxs-lookup"><span data-stu-id="a7ba6-113">Header, style and block elements: \<H{n}>, \<DIV>, \<SPAN>,\<P>, \<LI></span></span>  
  
 <span data-ttu-id="a7ba6-114">Qualquer outra marcação HTML será ignorada durante o processamento de relatório.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-114">Any other HTML markup tags will be ignored during report processing.</span></span> <span data-ttu-id="a7ba6-115">Se o HTML representado pela expressão no texto de espaço reservado não for bem formado, o espaço reservado será processado como texto sem-formatação.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-115">If the HTML represented by the expression in the placeholder text is not well formed, the placeholder is rendered as plain text.</span></span> <span data-ttu-id="a7ba6-116">Todas as marcas HTML não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-116">All HTML tags are case-insensitive.</span></span>  
  
 <span data-ttu-id="a7ba6-117">Se o texto na sua caixa de texto tiver apenas um bloco de texto, qualquer HTML no espaço reservado que define os elementos do bloco será renderizado corretamente.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-117">If the text in your text box contains only one block of text, any HTML in the placeholder that defines block elements will render correctly.</span></span> <span data-ttu-id="a7ba6-118">Entretanto, se a caixa de texto tiver vários blocos de texto, as marcas HTML serão ignoradas e a estrutura do texto será definida pelos blocos de texto.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-118">However, if the text box has multiple blocks of text, the HTML tags are ignored and the structure of the text is defined by the blocks of text.</span></span>  
  
 <span data-ttu-id="a7ba6-119">Se mais de uma marca for definida para texto, e o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] detectar um conflito entre o HTML e as restrições de relatório existentes, somente a marca HTML mais interna será tratada como HTML.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-119">If more than one tag is defined for text, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] detects a conflict between the HTML and existing report constraints, only the innermost HTML tag will be treated as HTML.</span></span>  
  
 <span data-ttu-id="a7ba6-120">Ao utilizar a lista de manipulação de rótulos, a fonte e o estilo de todos os prefixos de números e marcadores serão corrigidos para Arial black.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-120">When using the list handling tags, the font and style of all bullets and number prefixes will be fixed to Arial black.</span></span>  
  
 <span data-ttu-id="a7ba6-121">Para obter mais informações, consulte [Adicionar HTML a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a7ba6-121">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="limitations-of-cascading-style-sheet-attributes"></a><span data-ttu-id="a7ba6-122">Limitações de atributos de folha de estilos em cascata</span><span class="sxs-lookup"><span data-stu-id="a7ba6-122">Limitations of Cascading Style Sheet Attributes</span></span>  
 <span data-ttu-id="a7ba6-123">Ao usar atributos de folha de estilos em cascata (CSS), somente um conjunto básico de marcas é definido.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-123">When using cascading style sheet (CSS) attributes, only a basic set of tags are defined.</span></span> <span data-ttu-id="a7ba6-124">Estes são os atributos com suporte:</span><span class="sxs-lookup"><span data-stu-id="a7ba6-124">The following is a list of attributes that are supported:</span></span>  
  
-   <span data-ttu-id="a7ba6-125">alinhamento de texto, recuo de texto</span><span class="sxs-lookup"><span data-stu-id="a7ba6-125">text-align, text-indent</span></span>  
  
-   <span data-ttu-id="a7ba6-126">font-family</span><span class="sxs-lookup"><span data-stu-id="a7ba6-126">font-family</span></span>  
  
-   <span data-ttu-id="a7ba6-127">font-size</span><span class="sxs-lookup"><span data-stu-id="a7ba6-127">font-size</span></span>  
  
    -   <span data-ttu-id="a7ba6-128">Há suporte somente para valores de tamanho RDL válido em unidades de comprimento CSS absoluto.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-128">Only valid RDL size values, in absolute CSS length units are supported.</span></span> <span data-ttu-id="a7ba6-129">Unidades com suporte: in, cm, mm, pt, pc.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-129">Supported units are: in, cm, mm, pt, pc.</span></span>  
  
    -   <span data-ttu-id="a7ba6-130">As unidades de comprimento CSS relativas são ignoradas e não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-130">Relative CSS length units are ignored and not supported.</span></span> <span data-ttu-id="a7ba6-131">As unidades com suporte são em, ex, px,%,rem.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-131">Unsupported units include em, ex, px,%,rem.</span></span>  
  
-   <span data-ttu-id="a7ba6-132">cor</span><span class="sxs-lookup"><span data-stu-id="a7ba6-132">color</span></span>  
  
-   <span data-ttu-id="a7ba6-133">preenchimento, preenchimento inferior, preenchimento superior, preenchimento à direita, preenchimento à esquerda</span><span class="sxs-lookup"><span data-stu-id="a7ba6-133">padding, padding-bottom, padding-top, padding-right, padding-left</span></span>  
  
-   <span data-ttu-id="a7ba6-134">espessura da fonte</span><span class="sxs-lookup"><span data-stu-id="a7ba6-134">font-weight</span></span>  
  
 <span data-ttu-id="a7ba6-135">Eis algumas considerações quanto ao uso de CSS:</span><span class="sxs-lookup"><span data-stu-id="a7ba6-135">Here are some considerations for using CSS:</span></span>  
  
-   <span data-ttu-id="a7ba6-136">Valores CSS malformados são ignorados da mesma maneira que HTML malformado.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-136">Malformed CSS values are ignored in the same way as malformed HTML.</span></span>  
  
-   <span data-ttu-id="a7ba6-137">Quando o atributo e os atributos de estilo CSS existirem na mesma marca, a propriedade CSS tem maior precedência.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-137">When both attribute and CSS style attributes exist in the same tag, the CSS property has a higher precedence.</span></span> <span data-ttu-id="a7ba6-138">Por exemplo, se o texto for **\<p style="text-align: right" align="left">** , somente o atributo de alinhamento de texto será aplicado e o texto será alinhado à direita.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-138">For example, if your text is **\<p style="text-align: right" align="left">**, only the text-align attribute will be applied and the text will be right-aligned.</span></span>  
  
-   <span data-ttu-id="a7ba6-139">Para atributos e a estilos CSS, se uma propriedade for especificada mais de uma vez, somente sua última instância será aplicada.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-139">For attributes and CSS styles, if a property is specified more than once, only the last instance of the property is applied.</span></span> <span data-ttu-id="a7ba6-140">Por exemplo, se o texto for **\<p align="left" align="right">** , o texto será alinhado à direita.</span><span class="sxs-lookup"><span data-stu-id="a7ba6-140">For example, if your text is **\<p align="left" align="right">**, the text will be right-aligned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ba6-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a7ba6-141">See Also</span></span>  
 [<span data-ttu-id="a7ba6-142">Renderizando para HTML &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a7ba6-142">Rendering to HTML &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/rendering-to-html-report-builder-and-ssrs.md)  
  
  
