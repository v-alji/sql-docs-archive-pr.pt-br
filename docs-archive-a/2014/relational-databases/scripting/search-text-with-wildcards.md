---
title: Pesquisar texto com curingas
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vswildcardsbuilder
helpviewer_keywords:
- searches [SQL Server Management Studio], wildcards
- Query Editor [SQL Server Management Studio], wildcard searches
- wildcard options [SQL Server Management Studio]
ms.assetid: 449600f8-cc87-4b3f-878a-59c158a88a40
author: rothja
ms.author: jroth
ms.openlocfilehash: cc4e24c3dce73e46350b0c106429c42ab5f0edb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583467"
---
# <a name="search-text-with-wildcards"></a><span data-ttu-id="2553a-102">Pesquisar texto com curingas</span><span class="sxs-lookup"><span data-stu-id="2553a-102">Search Text with Wildcards</span></span>
  <span data-ttu-id="2553a-103">As expressões a seguir podem substituir caracteres ou dígitos no campo **O que localizar** da caixa de diálogo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Localizar e Substituir**do**.</span><span class="sxs-lookup"><span data-stu-id="2553a-103">The following expressions can replace characters or digits in the **Find what** field of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Find and Replace** dialog box.</span></span>  
  
#### <a name="to-search-using-wildcards"></a><span data-ttu-id="2553a-104">Para pesquisar usando curingas</span><span class="sxs-lookup"><span data-stu-id="2553a-104">To search using wildcards</span></span>  
  
1.  <span data-ttu-id="2553a-105">Para habilitar o uso de curingas no campo **Localizar** durante a Localização Rápida, **Localizar em Arquivos**, **Substituição Rápida**ou em operações **Substituir nos Arquivos** , selecione a opção **Usar** em **Opções de Pesquisa** e selecione **Curingas**.</span><span class="sxs-lookup"><span data-stu-id="2553a-105">To enable the use of wildcards in the **Find what** field during Quick Find, **Find in Files**, **Quick Replace**, or **Replace in Files** operations, select the **Use** option under **Find Options** and then choose **Wildcards**.</span></span>  
  
2.  <span data-ttu-id="2553a-106">O botão triangular **Lista de Referências** próximo ao campo **Localizar** torna-se disponível.</span><span class="sxs-lookup"><span data-stu-id="2553a-106">The triangular **Reference List** button next to the **Find what** field then becomes available.</span></span> <span data-ttu-id="2553a-107">Clique nesse botão para exibir uma lista dos curingas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2553a-107">Click this button to display a list of the available wildcards.</span></span> <span data-ttu-id="2553a-108">Quando você selecionar qualquer item da **Lista de Referências**, ele será inserido na cadeia de caracteres **Localizar** .</span><span class="sxs-lookup"><span data-stu-id="2553a-108">When you choose any item from the **Reference List**, it is inserted into the **Find what** string.</span></span>  
  
 <span data-ttu-id="2553a-109">A tabela a seguir descreve os curingas disponíveis na **Lista de Referências**.</span><span class="sxs-lookup"><span data-stu-id="2553a-109">The following table describes the wildcards available in the **Reference List**.</span></span>  
  
|<span data-ttu-id="2553a-110">Expression</span><span class="sxs-lookup"><span data-stu-id="2553a-110">Expression</span></span>|<span data-ttu-id="2553a-111">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2553a-111">Syntax</span></span>|<span data-ttu-id="2553a-112">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2553a-112">Description</span></span>|  
|----------------|------------|-----------------|  
|<span data-ttu-id="2553a-113">Qualquer caractere único</span><span class="sxs-lookup"><span data-stu-id="2553a-113">Any single character</span></span>|<span data-ttu-id="2553a-114">?</span><span class="sxs-lookup"><span data-stu-id="2553a-114">?</span></span>|<span data-ttu-id="2553a-115">Corresponde a qualquer caractere único.</span><span class="sxs-lookup"><span data-stu-id="2553a-115">Matches any single character.</span></span>|  
|<span data-ttu-id="2553a-116">Qualquer dígito único</span><span class="sxs-lookup"><span data-stu-id="2553a-116">Any single digit</span></span>|#|<span data-ttu-id="2553a-117">Corresponde a qualquer dígito único.</span><span class="sxs-lookup"><span data-stu-id="2553a-117">Matches any single digit.</span></span> <span data-ttu-id="2553a-118">Por exemplo, 7# corresponde a números que incluem 7 seguidos por outro número, como 71, mas não 17.</span><span class="sxs-lookup"><span data-stu-id="2553a-118">For example, 7# matches numbers that include 7 followed by another number, such as 71, but not 17.</span></span>|  
|<span data-ttu-id="2553a-119">Caracteres fora de um conjunto</span><span class="sxs-lookup"><span data-stu-id="2553a-119">Characters not in set</span></span>|<span data-ttu-id="2553a-120">[!</span><span class="sxs-lookup"><span data-stu-id="2553a-120">[!</span></span> <span data-ttu-id="2553a-121">]</span><span class="sxs-lookup"><span data-stu-id="2553a-121">]</span></span>|<span data-ttu-id="2553a-122">Corresponde a qualquer caractere único que não esteja especificado no conjunto.</span><span class="sxs-lookup"><span data-stu-id="2553a-122">Matches any one character that is not specified in the set.</span></span>|  
|<span data-ttu-id="2553a-123">Um ou mais caracteres</span><span class="sxs-lookup"><span data-stu-id="2553a-123">One or more characters</span></span>|*|<span data-ttu-id="2553a-124">Corresponde a qualquer um ou mais caracteres.</span><span class="sxs-lookup"><span data-stu-id="2553a-124">Matches any one or more characters.</span></span> <span data-ttu-id="2553a-125">Por exemplo, new\* corresponde a qualquer texto que inclui "new", como newfile.txt.</span><span class="sxs-lookup"><span data-stu-id="2553a-125">For example, new\* matches any text that includes "new", such as newfile.txt.</span></span>|  
|<span data-ttu-id="2553a-126">Conjunto de caracteres</span><span class="sxs-lookup"><span data-stu-id="2553a-126">Set of characters</span></span>|<span data-ttu-id="2553a-127">[ ]</span><span class="sxs-lookup"><span data-stu-id="2553a-127">[ ]</span></span>|<span data-ttu-id="2553a-128">Corresponde a qualquer um dos caracteres especificados no conjunto.</span><span class="sxs-lookup"><span data-stu-id="2553a-128">Matches any one of the characters specified in the set.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2553a-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2553a-129">See Also</span></span>  
 <span data-ttu-id="2553a-130">[Pesquisar e substituir](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="2553a-130">[Search and Replace](search-and-replace.md) </span></span>  
 [<span data-ttu-id="2553a-131">Pesquisar texto com expressões regulares</span><span class="sxs-lookup"><span data-stu-id="2553a-131">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
