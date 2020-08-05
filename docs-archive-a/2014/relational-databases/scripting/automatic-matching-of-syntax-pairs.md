---
title: Correspondência automática de pares de sintaxe
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], delimiter highlighting
- IntelliSense [SQL Server], syntax pair matching
ms.assetid: bfc54cda-bfd6-4545-a5b9-f9db2ae13769
author: rothja
ms.author: jroth
ms.openlocfilehash: d1237eeb9aaec39e3210b00c880c0005ef3d95bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572466"
---
# <a name="automatic-matching-of-syntax-pairs"></a><span data-ttu-id="6b3eb-102">Correspondência automática de pares de sintaxe</span><span class="sxs-lookup"><span data-stu-id="6b3eb-102">Automatic Matching of Syntax Pairs</span></span>
  <span data-ttu-id="6b3eb-103">A correspondência automática de pares de sintaxe informa imediatamente se os elementos de sintaxe que devem ser codificados em pares estão formando pares corretos.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-103">Automatic matching of syntax pairs gives you immediate feedback on whether syntax elements that must be coded in pairs are correctly paired.</span></span> <span data-ttu-id="6b3eb-104">Isso é conhecido como correspondência de delimitadores no Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] , correspondência de colchetes no Editor de Consultas XMLA do Analysis Services e correspondência de parênteses nos editores MDX e DMX.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-104">This is known as delimiter matching in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor, brace matching in the Analysis Services XMLA Query Editor, and parenthesis matching in the MDX and DMX editors.</span></span>  
  
## <a name="database-engine-query-editor-delimiter-matching"></a><span data-ttu-id="6b3eb-105">Correspondência de delimitadores do Editor de Consultas do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="6b3eb-105">Database Engine Query Editor Delimiter Matching</span></span>  
 <span data-ttu-id="6b3eb-106">O Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] faz a correspondência de delimitadores que identificam os limites dos blocos de código.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-106">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor matches the delimiters that identify the boundaries of code blocks.</span></span> <span data-ttu-id="6b3eb-107">A correspondência é feita de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="6b3eb-107">The matching is done in two ways:</span></span>  
  
-   <span data-ttu-id="6b3eb-108">O editor realça ambos delimitadores em um par quando você termina de digitar o segundo delimitador do par.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-108">The editor highlights both delimiters in a pair when you finish typing the second delimiter in the pair.</span></span>  
  
-   <span data-ttu-id="6b3eb-109">Sempre que o cursor estiver em um dos delimitadores de um par, você poderá usar o atalho de teclado CTRL+] para saltar para o delimitador correspondente.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-109">Anytime the cursor is in one of the delimiters in a pair, you can use the CTRL+] keyboard shortcut to jump to the matching delimiter.</span></span>  
  
### <a name="delimiter-pairs"></a><span data-ttu-id="6b3eb-110">Pares de delimitadores</span><span class="sxs-lookup"><span data-stu-id="6b3eb-110">Delimiter Pairs</span></span>  
 <span data-ttu-id="6b3eb-111">A correspondência automática de delimitadores reconhece os seguintes conjuntos de delimitadores:</span><span class="sxs-lookup"><span data-stu-id="6b3eb-111">Automatic delimiter matching recognizes the following sets of delimiters:</span></span>  
  
|<span data-ttu-id="6b3eb-112">Delimitador inicial</span><span class="sxs-lookup"><span data-stu-id="6b3eb-112">Lead Delimiter</span></span>|<span data-ttu-id="6b3eb-113">Delimitador de fechamento</span><span class="sxs-lookup"><span data-stu-id="6b3eb-113">Closing Delimiter</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="6b3eb-114">**(**</span><span class="sxs-lookup"><span data-stu-id="6b3eb-114">**(**</span></span>|<span data-ttu-id="6b3eb-115">**)**</span><span class="sxs-lookup"><span data-stu-id="6b3eb-115">**)**</span></span>|  
|<span data-ttu-id="6b3eb-116">**BEGIN**</span><span class="sxs-lookup"><span data-stu-id="6b3eb-116">**BEGIN**</span></span>|<span data-ttu-id="6b3eb-117">**END**</span><span class="sxs-lookup"><span data-stu-id="6b3eb-117">**END**</span></span>|  
|<span data-ttu-id="6b3eb-118">**BEGIN TRY**</span><span class="sxs-lookup"><span data-stu-id="6b3eb-118">**BEGIN TRY**</span></span>|<span data-ttu-id="6b3eb-119">**END TRY**</span><span class="sxs-lookup"><span data-stu-id="6b3eb-119">**END TRY**</span></span>|  
|<span data-ttu-id="6b3eb-120">**BEGIN CATCH**</span><span class="sxs-lookup"><span data-stu-id="6b3eb-120">**BEGIN CATCH**</span></span>|<span data-ttu-id="6b3eb-121">**END CATCH**</span><span class="sxs-lookup"><span data-stu-id="6b3eb-121">**END CATCH**</span></span>|  
  
 <span data-ttu-id="6b3eb-122">A correspondência automática de delimitadores não reconhece os delimitadores de identificadores entre colchetes ([ObjectName]) ou identificadores entre aspas ("ObjectName").</span><span class="sxs-lookup"><span data-stu-id="6b3eb-122">Automatic delimiter matching does not recognize the delimiters for bracketed identifiers ([ObjectName]), or quoted identifiers ("ObjectName").</span></span> <span data-ttu-id="6b3eb-123">A correspondência de pares não faz a correspondência dos delimitadores aspas simples de literais de cadeia de caracteres ('cadeia de caracteres') porque a codificação por cores já indica visualmente se a cadeia de caracteres foi delimitada ou não.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-123">Pair matching does not match the single quotation delimiters for string literals ('string') because color coding already gives a visual indication of whether the string has been delimited.</span></span>  
  
### <a name="delimiter-highlighting"></a><span data-ttu-id="6b3eb-124">Realce de delimitadores</span><span class="sxs-lookup"><span data-stu-id="6b3eb-124">Delimiter Highlighting</span></span>  
 <span data-ttu-id="6b3eb-125">A correspondência realça os elementos inicial e de fechamento de um par de delimitadores.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-125">Matching highlights both the lead and closing element of a pair of delimiters.</span></span> <span data-ttu-id="6b3eb-126">Isso permite identificar visualmente os blocos de código e verificar se existem pares de delimitadores incompletos.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-126">This lets you visually identify code blocks and check for mismatched pairs of delimiters.</span></span>  
  
 <span data-ttu-id="6b3eb-127">Os delimitadores são realçados quando você digita a letra final que completa o par.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-127">Delimiters are highlighted when you type the final letter that completes the pair.</span></span> <span data-ttu-id="6b3eb-128">Por exemplo, em um par BEGIN END em que você digita BEGIN primeiro, seguido por END, o realce será ativado quando você digitar a letra final de END.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-128">For example, for a BEGIN END pair where you type BEGIN first followed by END, highlighting turns on when you type the final letter in END.</span></span> <span data-ttu-id="6b3eb-129">Não é necessário digitar o delimitador inicial seguido pelo delimitador de fechamento para ativar o realce.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-129">You do not have to type the lead delimiter followed by the closing delimiter to turn on highlighting.</span></span> <span data-ttu-id="6b3eb-130">Se você digitar END primeiro e, em seguida, retroceder no script e digitar BEGIN, o realce será ativado quando você digitar a letra final de BEGIN.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-130">If you type END first, then scroll back up the script and type BEGIN, highlighting is turned on when you type the final letter in BEGIN.</span></span> <span data-ttu-id="6b3eb-131">A letra final digitada não precisa ser a letra final do delimitador.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-131">The final letter typed does not have to be the end letter in the delimiter.</span></span> <span data-ttu-id="6b3eb-132">Por exemplo, se você digitar incorretamente BEGIN como BEIN, quando inserir o G final, o par BEGIN END será realçado.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-132">For example, you could misspell BEGIN as BEIN, when you insert the final G the BEGIN END pair is highlighted.</span></span>  
  
 <span data-ttu-id="6b3eb-133">Os par de delimitadores permanecerá realçado até que você mova o cursor.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-133">The delimiter pair remains highlighted until you move the cursor.</span></span> <span data-ttu-id="6b3eb-134">O realce é desativado quando o cursor se move, mesmo que a nova posição do cursor permaneça no mesmo delimitador.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-134">The highlighting is turned off when the cursor is moved, even if the new cursor position remains in the same delimiter.</span></span> <span data-ttu-id="6b3eb-135">Você pode reativar o realce excluindo e digitando novamente qualquer letra de qualquer membro do par.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-135">You can turn the highlighting back on by deleting and retyping any letter in either member of the pair.</span></span>  
  
## <a name="analysis-services-xmla-query-editor-brace-matching"></a><span data-ttu-id="6b3eb-136">Correspondência de colchetes do Editor de Consultas XMLA do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6b3eb-136">Analysis Services XMLA Query Editor Brace Matching</span></span>  
 <span data-ttu-id="6b3eb-137">A correspondência de colchetes do Editor de Consultas XMLA mostra se você fechou os elementos realçando os colchetes de abertura e de fechamento.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-137">The XMLA Query Editor brace matching shows if you have closed elements by highlighting opening and closing braces.</span></span> <span data-ttu-id="6b3eb-138">Também é possível usar o atalho de teclado CTRL+] para saltar de uma chave para a chave correspondente.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-138">You can also use the CTRL+] keyboard shortcut to jump from one brace to the matching brace.</span></span>  
  
 <span data-ttu-id="6b3eb-139">O Editor de Consultas XMLA faz a correspondência de chaves dos seguintes termos:</span><span class="sxs-lookup"><span data-stu-id="6b3eb-139">The XMLA Query Editor does brace matching for the following terms:</span></span>  
  
-   <span data-ttu-id="6b3eb-140">Correspondência de marcas inicial e de fim.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-140">Matching start and end tags.</span></span>  
  
-   <span data-ttu-id="6b3eb-141">Qualquer par de \<" and "> colchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-141">Any pair of "\<" and ">" angle brackets.</span></span>  
  
-   <span data-ttu-id="6b3eb-142">Início e fim de comentários.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-142">Start and end of comments.</span></span>  
  
-   <span data-ttu-id="6b3eb-143">Início e fim de instruções de processamento.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-143">Start and end of processing instructions.</span></span>  
  
-   <span data-ttu-id="6b3eb-144">Início e fim de blocos CDATA.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-144">Start and end of CDATA blocks.</span></span>  
  
-   <span data-ttu-id="6b3eb-145">Início e fim de declarações DTD.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-145">Start and end of DTD declarations.</span></span>  
  
-   <span data-ttu-id="6b3eb-146">Aspas de abertura e fechamento em abributos.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-146">Opening and closing quotes on attributes.</span></span>  
  
## <a name="mdx-and-dmx-editor-parenthesis-matching"></a><span data-ttu-id="6b3eb-147">Correspondência de parênteses dos Editores MDX e DMX</span><span class="sxs-lookup"><span data-stu-id="6b3eb-147">MDX and DMX Editor Parenthesis Matching</span></span>  
 <span data-ttu-id="6b3eb-148">Os Editores MDX (Expressões Multidimensionais) e DMX (Expressões de Mineração de Dados) combinam automaticamente pares de parênteses nas funções.</span><span class="sxs-lookup"><span data-stu-id="6b3eb-148">The Multi-Dimensional Expressions (MDX) and Data Mining Expressions (DMX) Editors automatically match parenthesis pairs in functions.</span></span>  
  
  
