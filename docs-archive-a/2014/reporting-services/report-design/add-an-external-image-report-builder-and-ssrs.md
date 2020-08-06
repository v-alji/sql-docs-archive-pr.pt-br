---
title: Adicionar uma imagem externa (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 81fd4a1f-79a9-4967-86d6-6229413c0995
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8d0030c8f29b14b2c62048be306daa15948cd8d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679142"
---
# <a name="add-an-external-image-report-builder-and-ssrs"></a><span data-ttu-id="69080-102">Adicionar uma imagem externa (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="69080-102">Add an External Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="69080-103">Imagens externas podem estar em um servidor de relatório em modo nativo ou em modo Integrado do SharePoint, ou em qualquer outro site.</span><span class="sxs-lookup"><span data-stu-id="69080-103">External images can be on a report server in native mode or SharePoint integrated mode, or on any other Web site.</span></span> <span data-ttu-id="69080-104">Quando você incluir imagens externas em seu relatório, verifique se a imagem existe e se o leitor do relatório tem permissões para acessar a imagem.</span><span class="sxs-lookup"><span data-stu-id="69080-104">When you include external images in your report, you must verify that the image exists and that the report reader has permissions to access the image.</span></span> <span data-ttu-id="69080-105">Para obter mais informações, consulte [Imagens &#40;Construtor de Relatórios e SSRS&#41;](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="69080-105">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-external-image"></a><span data-ttu-id="69080-106">Para adicionar uma imagem externa</span><span class="sxs-lookup"><span data-stu-id="69080-106">To add an external image</span></span>  
  
1.  <span data-ttu-id="69080-107">No modo design de relatório, na guia **Inserir** , clique em **Imagem**.</span><span class="sxs-lookup"><span data-stu-id="69080-107">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="69080-108">Na superfície de design, clique e arraste uma caixa até o tamanho desejado da imagem.</span><span class="sxs-lookup"><span data-stu-id="69080-108">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="69080-109">Na guia **Geral** da caixa de diálogo **Propriedades da Imagem** , digite um nome na caixa de texto **Nome** ou aceite o padrão.</span><span class="sxs-lookup"><span data-stu-id="69080-109">On the **General** tab of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="69080-110">(Opcional) Na caixa de texto **Dica de Ferramenta** , digite o texto a ser exibido quando o usuário passar o mouse sobre a imagem em um relatório renderizado para HTML.</span><span class="sxs-lookup"><span data-stu-id="69080-110">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in a report rendered for HTML.</span></span>  
  
5.  <span data-ttu-id="69080-111">Em **Selecione a origem da imagem**, selecione **Externa**.</span><span class="sxs-lookup"><span data-stu-id="69080-111">In **Select the image source**, select **External**.</span></span>  
  
     <span data-ttu-id="69080-112">Para uma imagem que está em um servidor de relatório no modo nativo, digite um caminho relativo até a imagem na caixa **Usar esta imagem**, por exemplo, ../images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="69080-112">For an image on a report server in native mode, type a relative path to the image in the **Use this image** box-for example, ../images/image1.jpg.</span></span>  
  
     <span data-ttu-id="69080-113">Para uma imagem em um servidor de relatório no modo integrado do SharePoint ou em qualquer outro site da Web, digite uma URL completa para a imagem na caixa **usar esta imagem** , por exemplo, http:// \<SharePointservername> / \<site> /Documents/images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="69080-113">For an image on a report server in SharePoint integrated mode, or any other Web site, type a full URL to the image in the **Use this image** box-for example, http://\<SharePointservername>/\<site>/Documents/images/image1.jpg.</span></span>  
  
     <span data-ttu-id="69080-114">Para obter mais informações, consulte [Especificando caminhos para itens externos &#40;Construtor de Relatórios e SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="69080-114">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="69080-115">(Opcional) Clique em **Tamanho**, **Visibilidade**, **Ação**ou **Borda** para definir as propriedades adicionais do item de relatório da imagem.</span><span class="sxs-lookup"><span data-stu-id="69080-115">(Optional) Click **Size**, **Visibility**, **Action**, or **Border** to set additional properties for the image report item.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="69080-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="69080-116">See Also</span></span>  
 <span data-ttu-id="69080-117">[Inserir uma imagem em um relatório &#40;Construtor de Relatórios e SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="69080-117">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="69080-118">[Adicionar uma imagem de tela de fundo &#40;Construtor de Relatórios e SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="69080-118">[Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="69080-119">Caixa de diálogo Propriedades da Imagem, Geral &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="69080-119">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
