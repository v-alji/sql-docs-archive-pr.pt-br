---
title: Caixa de diálogo Ordenação (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.definecolumncollation
- vdtsql.chm:65561
ms.assetid: e4020f79-7abf-4839-b9b2-984ef7049817
author: stevestein
ms.author: sstein
ms.openlocfilehash: d551b2ae7ca27250c144afedf13038efd78ad6ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583937"
---
# <a name="collation-dialog-box-visual-database-tools"></a><span data-ttu-id="53765-102">Caixa de diálogo Ordenação (Ferramentas de Banco de Dados Visual)</span><span class="sxs-lookup"><span data-stu-id="53765-102">Collation Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="53765-103">Essa caixa de diálogo lhe permite especificar uma sequência de ordenação para a coluna.</span><span class="sxs-lookup"><span data-stu-id="53765-103">This dialog box lets you specify a collation sequence for the column.</span></span> <span data-ttu-id="53765-104">A sequência de ordenação de uma coluna é usada em qualquer operação que compare os valores da coluna com os de outra coluna ou com valores constantes.</span><span class="sxs-lookup"><span data-stu-id="53765-104">A column's collation sequence is used in any operation that compares values of the column to another column or to constant values.</span></span> <span data-ttu-id="53765-105">Isso também afeta o comportamento de algumas funções de cadeia de caracteres, como SUBSTRING e CHARINDEX.</span><span class="sxs-lookup"><span data-stu-id="53765-105">It also affects the behavior of some string functions, such as SUBSTRING and CHARINDEX.</span></span> <span data-ttu-id="53765-106">Para uma lista completa dos efeitos da configuração de ordenação de uma coluna, consulte a documentação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53765-106">For a complete list of the effects of a column's collation setting, see the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="53765-107">Essa caixa de diálogo aparece:</span><span class="sxs-lookup"><span data-stu-id="53765-107">This dialog box appears:</span></span>  
  
-   <span data-ttu-id="53765-108">Se você digitar um nome de ordenação inválido no campo **Ordenação** na guia **Propriedades de Coluna**.</span><span class="sxs-lookup"><span data-stu-id="53765-108">If you enter an invalid collation name in the **Collation** field on the **Column Properties** tab.</span></span>  
  
-   <span data-ttu-id="53765-109">Quando você clica no campo **Ordenação** na guia **Propriedades de Coluna** e, em seguida, clica no botão de reticências ( **…** ) à direita do campo.</span><span class="sxs-lookup"><span data-stu-id="53765-109">If you click in the **Collation** field on the **Column Properties** tab, and then click the ellipsis button (**...**) to the right of the field.</span></span>  
  
## <a name="options"></a><span data-ttu-id="53765-110">Opções</span><span class="sxs-lookup"><span data-stu-id="53765-110">Options</span></span>  
 <span data-ttu-id="53765-111">**Ordenação SQL**</span><span class="sxs-lookup"><span data-stu-id="53765-111">**SQL Collation**</span></span>  
 <span data-ttu-id="53765-112">Escolha na lista suspensa as sequências de ordenação definidas pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53765-112">Choose among the collation sequences defined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the drop-down list.</span></span>  
  
 <span data-ttu-id="53765-113">**Ordenação do Windows**</span><span class="sxs-lookup"><span data-stu-id="53765-113">**Windows Collation**</span></span>  
 <span data-ttu-id="53765-114">Escolha na lista suspensa as sequências de ordenação definidas pelo Windows.</span><span class="sxs-lookup"><span data-stu-id="53765-114">Choose among the collation sequences defined by Windows from the drop-down list.</span></span>  
  
 <span data-ttu-id="53765-115">**Classificação binária**</span><span class="sxs-lookup"><span data-stu-id="53765-115">**Binary Sort**</span></span>  
 <span data-ttu-id="53765-116">Use os códigos binários de valores de caractere para comparações.</span><span class="sxs-lookup"><span data-stu-id="53765-116">Use the binary codes of character values for comparisons.</span></span> <span data-ttu-id="53765-117">Se você selecionar essa opção, certas opções de comparação alfabéticas não estarão mais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="53765-117">If you select this option, certain alphabetic comparison options become unavailable.</span></span> <span data-ttu-id="53765-118">Por exemplo, comparações que não diferenciam maiúsculas de minúsculas ficam indisponíveis porque letras maiúsculas e letras minúsculas têm codificações binárias diferentes.</span><span class="sxs-lookup"><span data-stu-id="53765-118">For example, case-insensitive comparisons become unavailable because uppercase letters and lowercase letters have different binary encodings.</span></span> <span data-ttu-id="53765-119">Aplicável apenas se você selecionar **Ordenação do Windows**.</span><span class="sxs-lookup"><span data-stu-id="53765-119">Applies only if you select **Windows collation**.</span></span>  
  
 <span data-ttu-id="53765-120">**Classificação do Dicionário**</span><span class="sxs-lookup"><span data-stu-id="53765-120">**Dictionary Sort**</span></span>  
 <span data-ttu-id="53765-121">Use opções de comparação alfabéticas.</span><span class="sxs-lookup"><span data-stu-id="53765-121">Use alphabetic comparison options.</span></span> <span data-ttu-id="53765-122">Aplicável apenas se você selecionar **Ordenação do Windows**.</span><span class="sxs-lookup"><span data-stu-id="53765-122">Applies only if you select **Windows collation**.</span></span> <span data-ttu-id="53765-123">As opções de comparação alfabéticas são:</span><span class="sxs-lookup"><span data-stu-id="53765-123">The alphabetic comparisons options are:</span></span>  
  
-   <span data-ttu-id="53765-124">Selecione**Diferenciar Maiúsculas de Minúsculas** se quiser que as comparações considerem letras maiúsculas e letras minúsculas de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="53765-124">**Case Sensitive** Select this if you want comparisons to consider uppercase and lowercase letters to be unequal.</span></span>  
  
-   <span data-ttu-id="53765-125">Selecione**Diferenciar Acento** se quiser que as comparações considerem letras com e sem acento de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="53765-125">**Accent Sensitive** Select this if you want comparisons to consider accented and unaccented letters to be unequal.</span></span> <span data-ttu-id="53765-126">Ao selecione essa opção, as comparações também irão considerar de forma diferente letras com acento diferente.</span><span class="sxs-lookup"><span data-stu-id="53765-126">If you select this, comparisons will also consider differently accented letters to be unequal.</span></span>  
  
-   <span data-ttu-id="53765-127">Selecione**Diferenciar Katakana** se quiser que as comparações considerem de forma diferente sílabas japonesas katakana e hiragana.</span><span class="sxs-lookup"><span data-stu-id="53765-127">**Kana Sensitive** Select this if you want comparisons to consider katakana and hiragana Japanese syllables to be unequal.</span></span>  
  
-   <span data-ttu-id="53765-128">Selecione**Diferenciar Largura** se quiser que as comparações considerem de forma diferente caracteres de meia largura e de largura inteira.</span><span class="sxs-lookup"><span data-stu-id="53765-128">**Width Sensitive** Select this if you want comparisons to consider half-width and full-width characters to be unequal.</span></span>  
  
 <span data-ttu-id="53765-129">**Botão Restaurar padrão**</span><span class="sxs-lookup"><span data-stu-id="53765-129">**Restore Default Button**</span></span>  
 <span data-ttu-id="53765-130">Aplica à coluna a ordenação padrão para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="53765-130">Apply the default collation sequence for the database to the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53765-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="53765-131">See Also</span></span>  
 [<span data-ttu-id="53765-132">Trabalhar com colunas em consultas de agregação &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="53765-132">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
