---
title: Adicionar ou remover um cabeçalho ou rodapé de página (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 72988623-fee8-4a05-9f72-8fcb8e668576
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b29db3f72323c460360c872a0f60d13a808e3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682134"
---
# <a name="add-or-remove-a-page-header-or-footer-report-builder-and-ssrs"></a><span data-ttu-id="d490f-102">Adicionar ou remover um cabeçalho ou rodapé de página (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="d490f-102">Add or Remove a Page Header or Footer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d490f-103">É possível adicionar texto, imagens, linhas, retângulos e bordas estáticas aos cabeçalhos ou rodapés das páginas.</span><span class="sxs-lookup"><span data-stu-id="d490f-103">You can add static text, images, lines, rectangles, and borders to page headers or footers.</span></span> <span data-ttu-id="d490f-104">Você poderá colocar expressões e imagens associadas a dados em uma caixa de texto, se desejar a variável ou os dados computados em um cabeçalho ou rodapé.</span><span class="sxs-lookup"><span data-stu-id="d490f-104">You can place expressions and data-bound images in a textbox if you want variable or computed data in a header or footer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d490f-105">Cada extensão de renderização processa cabeçalhos e rodapés de páginas de modo diferente.</span><span class="sxs-lookup"><span data-stu-id="d490f-105">Each rendering extension processes page headers and footers differently.</span></span> <span data-ttu-id="d490f-106">Para obter mais informações, consulte [Cabeçalhos e rodapés de página &#40;Construtor de Relatórios e SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) e [Paginação no Reporting Services &#40;Construtor de Relatórios e SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d490f-106">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) and [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-header-or-footer"></a><span data-ttu-id="d490f-107">Para adicionar um cabeçalho ou rodapé de página</span><span class="sxs-lookup"><span data-stu-id="d490f-107">To add a page header or footer</span></span>  
  
1.  <span data-ttu-id="d490f-108">Abra um relatório.</span><span class="sxs-lookup"><span data-stu-id="d490f-108">Open a report.</span></span>  
  
2.  <span data-ttu-id="d490f-109">Na superfície de design, clique com o botão direito do mouse no relatório, aponte para **Inserir**e clique em **Cabeçalho** ou **Rodapé**.</span><span class="sxs-lookup"><span data-stu-id="d490f-109">On the design surface, right-click the report, point to **Insert**, and then click **Header** or **Footer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d490f-110">As opções **Cabeçalho** e **Rodapé** são exibidas apenas quando um cabeçalho ou um rodapé ainda não faz parte do relatório.</span><span class="sxs-lookup"><span data-stu-id="d490f-110">The **Header** and **Footer** options appear only when a header or footer is not already part of the report.</span></span>  
  
### <a name="to-configure-a-page-header-or-footer"></a><span data-ttu-id="d490f-111">Para configurar um cabeçalho ou rodapé de página</span><span class="sxs-lookup"><span data-stu-id="d490f-111">To configure a page header or footer</span></span>  
  
1.  <span data-ttu-id="d490f-112">Na superfície de design, clique com o botão direito do mouse no cabeçalho ou rodapé de página.</span><span class="sxs-lookup"><span data-stu-id="d490f-112">On the design surface, right-click the page header or footer.</span></span>  
  
2.  <span data-ttu-id="d490f-113">Aponte para **Inserir**e clique em um dos seguintes itens para adicioná-lo à área do cabeçalho ou rodapé:</span><span class="sxs-lookup"><span data-stu-id="d490f-113">Point to **Insert**, and then click one of the following items to add it to the header or footer area:</span></span>  
  
    -   <span data-ttu-id="d490f-114">**Caixa de texto**</span><span class="sxs-lookup"><span data-stu-id="d490f-114">**Textbox**</span></span>  
  
    -   <span data-ttu-id="d490f-115">**Linha**</span><span class="sxs-lookup"><span data-stu-id="d490f-115">**Line**</span></span>  
  
    -   <span data-ttu-id="d490f-116">**Retângulo**</span><span class="sxs-lookup"><span data-stu-id="d490f-116">**Rectangle**</span></span>  
  
    -   <span data-ttu-id="d490f-117">**Imagem**</span><span class="sxs-lookup"><span data-stu-id="d490f-117">**Image**</span></span>  
  
3.  <span data-ttu-id="d490f-118">Clique com o botão direito do mouse no cabeçalho da página e clique em **Propriedades do Cabeçalho** para adicionar bordas, imagens de tela de fundo ou cores, ou para ajustar a largura do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="d490f-118">Right-click the page header, and then click **Header Properties** to add borders, background images, or colors, or to adjust the width of the header.</span></span> <span data-ttu-id="d490f-119">Em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d490f-119">Then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d490f-120">Clique com o botão direito do mouse no rodapé da página e clique em **Propriedades do Rodapé** para adicionar bordas, imagens de tela de fundo ou cores, ou para ajustar a largura do rodapé.</span><span class="sxs-lookup"><span data-stu-id="d490f-120">Right-click the page footer, and then click **Footer Properties** to add borders, background images, or colors, or to adjust the width of the footer.</span></span> <span data-ttu-id="d490f-121">Em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d490f-121">Then click **OK**.</span></span>  
  
### <a name="to-remove-a-page-header-or-footer"></a><span data-ttu-id="d490f-122">Para remover o cabeçalho ou rodapé de uma página</span><span class="sxs-lookup"><span data-stu-id="d490f-122">To remove a page header or footer</span></span>  
  
1.  <span data-ttu-id="d490f-123">Abra um relatório.</span><span class="sxs-lookup"><span data-stu-id="d490f-123">Open a report.</span></span>  
  
2.  <span data-ttu-id="d490f-124">Na superfície de design, clique com o botão direito do mouse no cabeçalho ou rodapé e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="d490f-124">On the design surface, right-click the page header or footer, and then click **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d490f-125">Ao remover um cabeçalho ou rodapé de página, você o exclui do relatório.</span><span class="sxs-lookup"><span data-stu-id="d490f-125">When you remove a page header or footer, you delete it from the report.</span></span> <span data-ttu-id="d490f-126">Quaisquer itens adicionados anteriormente ao cabeçalho ou rodapé de página não voltarão a ser exibidos, se você adicionar o cabeçalho ou rodapé novamente mais tarde.</span><span class="sxs-lookup"><span data-stu-id="d490f-126">Any items that you previously added to the page header or footer will not reappear if you subsequently add the header or footer again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d490f-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d490f-127">See Also</span></span>  
 [<span data-ttu-id="d490f-128">Cabeçalhos e rodapés de página &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d490f-128">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
