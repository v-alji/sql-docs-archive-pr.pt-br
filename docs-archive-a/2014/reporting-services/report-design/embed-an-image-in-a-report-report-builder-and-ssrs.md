---
title: Inserir uma imagem em um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.embeddedimages.f1
- "10060"
ms.assetid: aed77345-5eeb-41f0-96c9-db6b4a11ec6f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6599092e0ef37dd9bbc15f4815c0315c77e7943b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678638"
---
# <a name="embed-an-image-in-a-report-report-builder-and-ssrs"></a><span data-ttu-id="1d595-102">Inserir uma imagem em um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="1d595-102">Embed an Image in a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1d595-103">Um relatório pode conter uma imagem inserida.</span><span class="sxs-lookup"><span data-stu-id="1d595-103">A report can include an embedded image.</span></span> <span data-ttu-id="1d595-104">Inserir uma imagem garante que ela estará sempre disponível para um relatório, mas também afeta o tamanho da definição de relatório, o arquivo que define o relatório.</span><span class="sxs-lookup"><span data-stu-id="1d595-104">Embedding an image ensures that the image is always available to a report, but can affect the size of the report definition, the file that defines the report.</span></span> <span data-ttu-id="1d595-105">As imagens inseridas em um relatório estão listadas no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="1d595-105">The images embedded in a report are listed in the Report Data pane.</span></span>  
  
 <span data-ttu-id="1d595-106">Talvez você queira inserir uma imagem na definição de relatório antes de adicionar a imagem à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="1d595-106">You might want to embed an image in the report definition before adding the image to the design surface.</span></span> <span data-ttu-id="1d595-107">Para obter mais informações, consulte [Adicionar uma imagem de tela de fundo &#40;Construtor de Relatórios e SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1d595-107">For more information, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-a-report"></a><span data-ttu-id="1d595-108">Para inserir uma imagem em um relatório</span><span class="sxs-lookup"><span data-stu-id="1d595-108">To embed an image in a report</span></span>  
  
1.  <span data-ttu-id="1d595-109">No modo design de relatório, na guia **Inserir** , clique em **Imagem**.</span><span class="sxs-lookup"><span data-stu-id="1d595-109">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="1d595-110">Na superfície de design, clique e arraste uma caixa até o tamanho desejado da imagem.</span><span class="sxs-lookup"><span data-stu-id="1d595-110">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="1d595-111">Na página **Geral** da caixa de diálogo **Propriedades da Imagem** , digite um nome na caixa de texto **Nome** ou aceite o padrão.</span><span class="sxs-lookup"><span data-stu-id="1d595-111">In the **General** page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="1d595-112">(Opcional) Na caixa de texto **Dica de Ferramenta** , digite o texto que você deseja que apareça quando o usuário passar o mouse sobre a imagem no relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="1d595-112">(Optional) In the **ToolTip** text box, type the text that you want to appear when the user hovers over the image in the rendered report.</span></span>  
  
5.  <span data-ttu-id="1d595-113">Em **Selecione a origem da imagem**, selecione **Inserida**.</span><span class="sxs-lookup"><span data-stu-id="1d595-113">In **Select the image source**, select **Embedded**.</span></span>  
  
6.  <span data-ttu-id="1d595-114">Clique no botão **Importar** ao lado da caixa de texto **Usar esta imagem**</span><span class="sxs-lookup"><span data-stu-id="1d595-114">Click the **Import** button next to the **Use this image** text box</span></span>  
  
7.  <span data-ttu-id="1d595-115">Em **Arquivos do tipo**, selecione o tipo de arquivo de imagem, navegue até o arquivo e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="1d595-115">In **Files of type**, select the image file type, navigate to the file, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="1d595-116">Na caixa de diálogo **Propriedades da Imagem** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d595-116">In the **Image Properties** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="1d595-117">A imagem é exibida na caixa que você desenhou na superfície de design, e o arquivo é exibido sob a pasta Imagens no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="1d595-117">The image is displayed in the box you drew on the design surface, and the file is displayed under the Images folder in the Report Data pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1d595-118">O tipo MIME (por exemplo, bmp) será extraído automaticamente quando a imagem for importada.</span><span class="sxs-lookup"><span data-stu-id="1d595-118">The MIME type (for example, bmp) is derived automatically when the image is imported.</span></span> <span data-ttu-id="1d595-119">Para alterar o tipo MIME, consulte o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="1d595-119">To change the MIME type, see the next procedure.</span></span>  
  
### <a name="optional-to-change-the-mime-type-of-an-imported-image"></a><span data-ttu-id="1d595-120">(Opcional) Para alterar o tipo MIME de uma imagem importada</span><span class="sxs-lookup"><span data-stu-id="1d595-120">(optional) To change the MIME type of an imported image</span></span>  
  
1.  <span data-ttu-id="1d595-121">Abra o relatório no modo Design.</span><span class="sxs-lookup"><span data-stu-id="1d595-121">Open the report in Design view.</span></span>  
  
2.  <span data-ttu-id="1d595-122">Selecione a imagem na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="1d595-122">Select the image on the design surface.</span></span> <span data-ttu-id="1d595-123">O painel **Propriedades** exibe as propriedades da imagem.</span><span class="sxs-lookup"><span data-stu-id="1d595-123">The **Properties** pane displays the image properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1d595-124">Se o painel Propriedades não estiver visível, na guia **Exibir** , clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1d595-124">If the Properties pane is not visible, on the **View** tab, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="1d595-125">Clique na caixa de texto próxima à propriedade **MIMEType** e selecione um novo tipo MIME na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="1d595-125">Click in the text box next to the **MIMEType** property and select a new MIME type from the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d595-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d595-126">See Also</span></span>  
 <span data-ttu-id="1d595-127">[Imagens &#40;Construtor de Relatórios e SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1d595-127">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1d595-128">[Adicionar uma imagem vinculada a dados &#40;Construtor de Relatórios e SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1d595-128">[Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1d595-129">Caixa de diálogo Propriedades da Imagem, Geral &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1d595-129">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
