---
title: Adicionar um hiperlink a uma URL (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d3392c0b-7b62-4d27-bc04-2bd0c5487d08
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d3db3fc75feca1393e73e698f44db633f09e8dc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679709"
---
# <a name="add-a-hyperlink-to-a-url-report-builder-and-ssrs"></a><span data-ttu-id="ab3fc-102">Adicionar um hiperlink a uma URL (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="ab3fc-102">Add a Hyperlink to a URL (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ab3fc-103">É possível adicionar um hiperlink a um item de relatório quando você deseja que os usuários possam clicar em um link de um relatório e abrir um navegador para a URL especificada.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-103">You can add a hyperlink to a report item when you want your users to be able to click a link in a report and open a browser to the URL that you specify.</span></span> <span data-ttu-id="ab3fc-104">Um hiperlink pode ser uma URL estático ou uma expressão que seja avaliada como uma URL.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-104">A hyperlink can be a static URL or an expression that evaluates to a URL.</span></span> <span data-ttu-id="ab3fc-105">Se você tiver um campo em um banco de dados que contenha URLs, a expressão poderá conter esse campo, resultando em uma lista dinâmica de hiperlinks no relatório.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-105">If you have a field in a database that contains URLs, the expression can contain that field, resulting in a dynamic list of hyperlinks in the report.</span></span> <span data-ttu-id="ab3fc-106">Os hiperlinks podem ser adicionados a caixas de texto, imagens, gráficos e medidores.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-106">You can add hyperlinks to text boxes, images, charts, and gauges.</span></span> <span data-ttu-id="ab3fc-107">Certifique-se de que o usuário tenha acesso ao URL fornecido.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-107">You must ensure that the user has access to the URL that you provide.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="ab3fc-108">Você também pode especificar URLs para relatórios em qualquer servidor de relatórios ao qual você e os usuários tenham permissão para exibir usando solicitações de URL para o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-108">You can also specify URLs to reports on any report server that you and your users have permission to view using URL requests to the report server.</span></span> <span data-ttu-id="ab3fc-109">Por exemplo, você pode especificar um relatório e ocultar o mapa do documento para o usuário quando ele exibir o relatório pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-109">For example, you can specify a report and hide the document map for the user when they first view the report.</span></span> <span data-ttu-id="ab3fc-110">Para obter mais informações, consulte [Acesso à URL &#40;SSRS&#41;](../url-access-ssrs.md) na [documentação do Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab3fc-110">For more information, see [URL Access &#40;SSRS&#41;](../url-access-ssrs.md) in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="ab3fc-111">Você pode adicionar um hiperlink a uma URL para qualquer item que tenha uma propriedade **Action** , como uma caixa de texto, uma imagem ou uma série calculada em um gráfico.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-111">You can add a hyperlink to a URL to any item that has an **Action** property, for example, a text box, an image, or a calculated series in a chart.</span></span> <span data-ttu-id="ab3fc-112">Quando o usuário clicar nesse item de relatório, ocorrerá a ação definida.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-112">When the user clicks that report item, the action that you define takes place.</span></span> <span data-ttu-id="ab3fc-113">Para obter mais informações, consulte a [Caixa de diálogo Propriedades de ação &#40;Construtor de Relatórios e SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) e [Especificando caminhos para itens externos &#40;Construtor de Relatórios e SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ab3fc-113">For more information, see the [Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) and [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="ab3fc-114">Para começar a usar rapidamente, consulte [Tutorial: Formatar texto &#40;Construtor de Relatórios&#41;](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="ab3fc-114">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab3fc-115">Links associados a campos de conjuntos de dados podem ser vulneráveis à violação para fins mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-115">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="ab3fc-116">Para obter mais informações, consulte [Proteger Relatórios e Recursos](../security/secure-reports-and-resources.md) nos [Manuais Online](https://go.microsoft.com/fwlink/?LinkId=154888) do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-116">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
### <a name="to-add-a-hyperlink"></a><span data-ttu-id="ab3fc-117">Para adicionar um hiperlink</span><span class="sxs-lookup"><span data-stu-id="ab3fc-117">To add a hyperlink</span></span>  
  
1.  <span data-ttu-id="ab3fc-118">No modo de exibição de Design de relatório, clique com o botão direito do mouse na caixa de texto, na imagem ou no gráfico a que você deseja adicionar um link e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-118">In report design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ab3fc-119">Na caixa de diálogo Propriedades, clique em **Ação**.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-119">In the Properties dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="ab3fc-120">Selecione **Ir para URL**.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-120">Select **Go to URL**.</span></span> <span data-ttu-id="ab3fc-121">Aparecerá uma seção adicional na caixa de diálogo para essa opção.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-121">An additional section appears in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="ab3fc-122">Em **Selecionar URL**, digite ou selecione uma URL ou uma expressão avaliada como uma URL, ou clique na seta suspensa e no nome de um campo que contenha uma URL.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-122">In **Select URL**, type or select a URL or an expression that evaluates to a URL, or click the drop-down arrow and click the name of a field that contains a URL.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="ab3fc-123">(Opcional) O texto não é formatado automaticamente como um link.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-123">(Optional) The text is not automatically formatted as a link.</span></span> <span data-ttu-id="ab3fc-124">Para textos, é recomendável alterar sua cor e seu efeito para indicar que ele é um link.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-124">For text, it is helpful to change the color and effect of the text to indicate that the text is a link.</span></span> <span data-ttu-id="ab3fc-125">Por exemplo, altere a cor para azul e o efeito para sublinhado na seção **Fonte** da guia Página Inicial da Faixa de Opções.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-125">For example, change the color to blue and the effect to underline in the **Font** section in the Home tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="ab3fc-126">Para testar o link, clique em **Executar** para visualizar o relatório e, em seguida, no item de relatório no qual você definiu esse link.</span><span class="sxs-lookup"><span data-stu-id="ab3fc-126">To test the link, click **Run** to preview the report, and then click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab3fc-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ab3fc-127">See Also</span></span>  
 <span data-ttu-id="ab3fc-128">[Classificação interativa, mapas de documentos e links &#40;Construtor de Relatórios e SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ab3fc-128">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ab3fc-129">Criar um mapa de documentos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ab3fc-129">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
  
  
