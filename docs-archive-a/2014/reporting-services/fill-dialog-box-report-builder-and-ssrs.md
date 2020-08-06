---
title: Caixa de diálogo preenchimento (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportbody.fill.f1
- "10065"
- "10501"
- sql12.rtp.rptdesigner.shared.filldv.f1
- sql12.rtp.rptdesigner.rectangleproperties.fill.f1
- "10064"
- sql12.rtp.rptdesigner.textboxproperties.fill.f1
- "10124"
ms.assetid: 93a91d02-d558-4a0e-8d17-3fdf21e208d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ae7f2b05d4d108c77f1dcae9ce7fefe5073e2522
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574511"
---
# <a name="fill-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="b5f30-102">Caixa de diálogo Preenchimento (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="b5f30-102">Fill Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b5f30-103">Na guia **Preenchimento** , você pode especificar as opções de cor da tela de fundo de uma única ou de várias células dentro de uma região de dados ou de uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b5f30-103">On the **Fill** tab, you can specify color options for the background of a single cell or multiple cells within a data region or a text box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b5f30-104">Opções</span><span class="sxs-lookup"><span data-stu-id="b5f30-104">Options</span></span>  
 <span data-ttu-id="b5f30-105">**Cor de Preenchimento**</span><span class="sxs-lookup"><span data-stu-id="b5f30-105">**Fill Color**</span></span>  
 <span data-ttu-id="b5f30-106">Clique no botão de cor para selecionar uma cor de preenchimento para o retângulo.</span><span class="sxs-lookup"><span data-stu-id="b5f30-106">Click the color button to select a fill color for the rectangle.</span></span> <span data-ttu-id="b5f30-107">Clique no botão **Expressão**_(fx)_ para editar a expressão, que pode ser um valor hexadecimal para a cor RGB ou um dos nomes de cor predefinidos que foram fornecidos na caixa de diálogo **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="b5f30-107">Click the **Expression**_(fx)_ button to edit the expression, which can be a hexadecimal value for the RGB color or one of the predefined color names that are provided in the **Expression** dialog box.</span></span> <span data-ttu-id="b5f30-108">Para consultar uma lista de cores predefinidas, selecione **Web** no painel **Item**.</span><span class="sxs-lookup"><span data-stu-id="b5f30-108">To see a list of predefined colors, in the **Item** pane, select **Web**.</span></span> <span data-ttu-id="b5f30-109">Os nomes de cor listados no painel **Título** podem ser digitados no painel de texto da expressão.</span><span class="sxs-lookup"><span data-stu-id="b5f30-109">The color names listed in the **Title** pane can be typed into the expression text pane.</span></span> <span data-ttu-id="b5f30-110">Não use sinal de igual (=) ou aspas ("") ao digitar o nome da cor.</span><span class="sxs-lookup"><span data-stu-id="b5f30-110">Do not use an equal sign (=) or quotation marks ("") when typing the color name.</span></span>  
  
 <span data-ttu-id="b5f30-111">**Selecione a origem da imagem**</span><span class="sxs-lookup"><span data-stu-id="b5f30-111">**Select the image source**</span></span>  
 <span data-ttu-id="b5f30-112">Indique onde a imagem está armazenada para que, quando o relatório for renderizado, o processador de relatórios possa exibi-la.</span><span class="sxs-lookup"><span data-stu-id="b5f30-112">Indicate where the image is stored so that when the report is rendered, the report processor can display it.</span></span>  
  
-   <span data-ttu-id="b5f30-113">**Externa** Escolha essa opção quando quiser que a imagem continue existindo como um arquivo em um servidor Web ou um servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="b5f30-113">**External** Choose this option when you want the image to continue to exist as a file on a report server or Web server.</span></span>  
  
-   <span data-ttu-id="b5f30-114">**Inserido** Escolha essa opção quando quiser inserir a imagem no relatório.</span><span class="sxs-lookup"><span data-stu-id="b5f30-114">**Embedded** Choose this option when you want to embed the image into the report.</span></span>  
  
-   <span data-ttu-id="b5f30-115">**Banco de Dados** Escolha essa opção quando quiser incluir um nome de campo do banco de dados que representa as imagens que deseja incluir em seu relatório.</span><span class="sxs-lookup"><span data-stu-id="b5f30-115">**Database** Choose this option when you want to include a database field name that represents the images that you want to include in your report.</span></span>  
  
 <span data-ttu-id="b5f30-116">**Usar esta imagem**</span><span class="sxs-lookup"><span data-stu-id="b5f30-116">**Use this image**</span></span>  
 <span data-ttu-id="b5f30-117">Essa opção aparece quando você seleciona a opção **Inserido** ou **Externo** .</span><span class="sxs-lookup"><span data-stu-id="b5f30-117">This option appears when you select the **Embedded** or **External** option.</span></span>  
  
 <span data-ttu-id="b5f30-118">Se estiver inserindo a imagem, na lista suspensa, escolha a imagem a ser adicionada ao relatório.</span><span class="sxs-lookup"><span data-stu-id="b5f30-118">If you are embedding the image, choose the picture that you want to add to the report from the drop-down list.</span></span> <span data-ttu-id="b5f30-119">Clique em **Importar** para adicionar a imagem à lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b5f30-119">Click **Import** to add the image to the drop-down list.</span></span> <span data-ttu-id="b5f30-120">Se você adicionou uma imagem ao painel **Dados** , poderá selecioná-la escolhendo a opção **Inserido** e, em seguida, selecionar a imagem na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b5f30-120">If you added an image to the **Data** pane, you can select that image by choosing **Embedded** and then selecting the image from the drop-down list.</span></span>  
  
 <span data-ttu-id="b5f30-121">Se você selecionar a opção **Externo** , digite a URL da imagem.</span><span class="sxs-lookup"><span data-stu-id="b5f30-121">If you select the **External** option, type the URL of the image.</span></span> <span data-ttu-id="b5f30-122">Para um relatório publicado em um servidor de relatório configurado para o modo nativo, use um caminho completo ou relativo (por exemplo, http:// *\<servername>* /images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="b5f30-122">For a report published to a report server configured for native mode, use a full or relative path (for example, http://*\<servername>*/images/image1.jpg).</span></span> <span data-ttu-id="b5f30-123">Para um relatório publicado em um servidor de relatório configurado no modo integrado do SharePoint, use uma URL totalmente qualificada (por exemplo, http:// *\<SharePointservername>/\<site>* /Documents/images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="b5f30-123">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL (for example, http://*\<SharePointservername>/\<site>*/Documents/images/image1.jpg).</span></span>  
  
 <span data-ttu-id="b5f30-124">**Importaçãoação**</span><span class="sxs-lookup"><span data-stu-id="b5f30-124">**Import**</span></span>  
 <span data-ttu-id="b5f30-125">Disponível quando você seleciona **Inserido**.</span><span class="sxs-lookup"><span data-stu-id="b5f30-125">Available when you select **Embedded**.</span></span> <span data-ttu-id="b5f30-126">Clique para adicionar uma imagem à lista suspensa **Usar esta imagem** .</span><span class="sxs-lookup"><span data-stu-id="b5f30-126">Click to add an image to the **Use this image** drop-down list.</span></span>  
  
 <span data-ttu-id="b5f30-127">**Usar este campo**</span><span class="sxs-lookup"><span data-stu-id="b5f30-127">**Use this field**</span></span>  
 <span data-ttu-id="b5f30-128">Disponível quando você seleciona **Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="b5f30-128">Available when you select **Database**.</span></span> <span data-ttu-id="b5f30-129">Selecione o nome do campo.</span><span class="sxs-lookup"><span data-stu-id="b5f30-129">Select the field name.</span></span>  
  
 <span data-ttu-id="b5f30-130">**Usar este tipo MIME**</span><span class="sxs-lookup"><span data-stu-id="b5f30-130">**Use this MIME type**</span></span>  
 <span data-ttu-id="b5f30-131">Escolha o formato apropriado das imagens contidas no banco de dados (por exemplo, .bmp, .jpeg, .gif, .png ou .x-png).</span><span class="sxs-lookup"><span data-stu-id="b5f30-131">Choose the appropriate format of the pictures contained in the database (for example, .bmp, .jpeg, .gif, .png, or .x-png).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f30-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5f30-132">See Also</span></span>  
 <span data-ttu-id="b5f30-133">[Formatando itens de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b5f30-133">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b5f30-134">[Formatando texto e espaços reservados &#40;Construtor de Relatórios e SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b5f30-134">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b5f30-135">Imagens &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b5f30-135">Images &#40;Report Builder and SSRS&#41;</span></span>](report-design/images-report-builder-and-ssrs.md)  
  
  
