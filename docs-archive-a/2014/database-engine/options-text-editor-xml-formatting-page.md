---
title: Opções (página Editor de texto – XML – formatação) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97373178-d288-4127-af37-d9f5fe1b8607
author: rothja
ms.author: jroth
ms.openlocfilehash: dce36142fe9974c0167fca700c509642e05d89b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681066"
---
# <a name="options-text-editor---xml---formatting-page"></a><span data-ttu-id="a8d76-102">Opções (página Editor de texto – XML – Formatação)</span><span class="sxs-lookup"><span data-stu-id="a8d76-102">Options (Text Editor - XML - Formatting Page)</span></span>

<span data-ttu-id="a8d76-103">Esta caixa de diálogo permite que você especifique as configurações de formatação para o Editor de XML.</span><span class="sxs-lookup"><span data-stu-id="a8d76-103">This dialog box allows you to specify the formatting settings for the XML Editor.</span></span> <span data-ttu-id="a8d76-104">Você pode acessar a caixa de diálogo **Opções** no menu **Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="a8d76-104">You can access the **Options** dialog box from the **Tools** menu.</span></span>  
  
> [!NOTE]  
> <span data-ttu-id="a8d76-105">Estas configurações estão disponíveis quando você seleciona a pasta **Editor de Texto**, a pasta **XML** e a opção **Formatação** na caixa de diálogo **Opções**.</span><span class="sxs-lookup"><span data-stu-id="a8d76-105">These settings are available when you select the **Text Editor** folder, the **XML** folder, and then the **Formatting** option from the **Options** dialog box.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="a8d76-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="a8d76-106">Attributes</span></span>  
 <span data-ttu-id="a8d76-107">**Preservar formatação manual de atributos**</span><span class="sxs-lookup"><span data-stu-id="a8d76-107">**Preserve manual attribute formatting**</span></span>  
 <span data-ttu-id="a8d76-108">Não reformate os atributos.</span><span class="sxs-lookup"><span data-stu-id="a8d76-108">Do not reformat attributes.</span></span> <span data-ttu-id="a8d76-109">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="a8d76-109">This is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8d76-110">Se os atributos estiverem em linhas múltiplas, o editor recua cada linha de atributos para corresponder ao recuo do elemento pai.</span><span class="sxs-lookup"><span data-stu-id="a8d76-110">If the attributes are on multiple lines, the editor indents each line of attributes to match the indentation of the parent element.</span></span>  
  
 <span data-ttu-id="a8d76-111">**Alinhar cada atributo em uma linha separada**</span><span class="sxs-lookup"><span data-stu-id="a8d76-111">**Align attributes each on a separate line**</span></span>  
 <span data-ttu-id="a8d76-112">Alinha o segundo e os atributos subsequentes verticalmente para corresponder ao recuo do primeiro atributo.</span><span class="sxs-lookup"><span data-stu-id="a8d76-112">Align the second and subsequent attributes vertically to match the indentation of the first attribute.</span></span> <span data-ttu-id="a8d76-113">O seguinte texto XML é um exemplo de como os atributos seriam alinhados.</span><span class="sxs-lookup"><span data-stu-id="a8d76-113">The following XML text is an example of how the attributes would be aligned.</span></span>  
  
```  
<item id = "123-A"  
      name = "hammer"  
      price = "9.95"  
</item>  
```  
  
## <a name="auto-reformat"></a><span data-ttu-id="a8d76-114">Reformatação Automática</span><span class="sxs-lookup"><span data-stu-id="a8d76-114">Auto Reformat</span></span>  
 <span data-ttu-id="a8d76-115">**Ao colar da área de transferência.**</span><span class="sxs-lookup"><span data-stu-id="a8d76-115">**On paste from clipboard.**</span></span>  
 <span data-ttu-id="a8d76-116">Reformata o texto XML colado da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a8d76-116">Reformat XML text pasted from the clipboard.</span></span>  
  
 <span data-ttu-id="a8d76-117">**Ao concluir a marca final**</span><span class="sxs-lookup"><span data-stu-id="a8d76-117">**On completion of end tag**</span></span>  
 <span data-ttu-id="a8d76-118">Reformata o elemento quando a marca final é concluída.</span><span class="sxs-lookup"><span data-stu-id="a8d76-118">Reformat the element when the end tag is completed.</span></span>  
  
## <a name="mixed-content"></a><span data-ttu-id="a8d76-119">Conteúdo Misto</span><span class="sxs-lookup"><span data-stu-id="a8d76-119">Mixed Content</span></span>  
 <span data-ttu-id="a8d76-120">**Formatar conteúdo misto por padrão.**</span><span class="sxs-lookup"><span data-stu-id="a8d76-120">**Format mixed content by default.**</span></span>  
 <span data-ttu-id="a8d76-121">Tenta reformatar conteúdo misto, exceto quando o conteúdo encontra-se em um escopo `xml:space="preserve"`.</span><span class="sxs-lookup"><span data-stu-id="a8d76-121">Attempt to reformat mixed content, except when the content is found in an `xml:space="preserve"` scope.</span></span> <span data-ttu-id="a8d76-122">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="a8d76-122">This is the default.</span></span>  
  
 <span data-ttu-id="a8d76-123">Se um elemento contiver uma mistura de texto e marcação, os conteúdos serão considerados de conteúdo misto.</span><span class="sxs-lookup"><span data-stu-id="a8d76-123">If an element contains a mix of text and markup, the contents are considered to be mixed content.</span></span> <span data-ttu-id="a8d76-124">A seguir há um exemplo de um elemento com conteúdo misto.</span><span class="sxs-lookup"><span data-stu-id="a8d76-124">Following is an example of an element with mixed content.</span></span>  
  
```  
<dir>c:\data\AlphaProject\  
  <file readOnly="false">test1.txt</file>  
  <file readOnly="false">test2.txt</file>  
```  
  
 \</dir>  
  
## <a name="see-also"></a><span data-ttu-id="a8d76-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a8d76-125">See Also</span></span>  
 [<span data-ttu-id="a8d76-126">Editor XML &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a8d76-126">XML Editor &#40;SQL Server Management Studio&#41;</span></span>](../ssms/sql-server-management-studio-ssms.md)  
