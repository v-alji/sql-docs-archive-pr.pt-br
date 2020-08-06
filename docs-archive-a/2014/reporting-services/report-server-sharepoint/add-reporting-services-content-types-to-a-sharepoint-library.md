---
title: Adicionar a Web Part do Visualizador de relatórios a uma página da Web (Reporting Services no modo integrado do SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], viewing reports
- Web Parts [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
ms.assetid: cac75345-2380-467d-a394-0a2140908a5a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d9b933fad8bc566b3cb0ef04303a85c5f034e620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683404"
---
# <a name="add-the-report-viewer-web-part-to-a-web-page-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="e1d83-102">Adicionar a Web Part do Visualizador de Relatórios a uma página da Web (Reporting Services no modo integrado do SharePoint)</span><span class="sxs-lookup"><span data-stu-id="e1d83-102">Add the Report Viewer Web Part to a Web Page (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="e1d83-103">É possível usar a Web Part do Visualizador de Relatórios para exibir relatórios executados no servidor de relatório configurado para execução no modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1d83-103">You can use the Report Viewer Web Part to view reports that run on report server that is configured to run in SharePoint integrated mode.</span></span> <span data-ttu-id="e1d83-104">Você pode usar a Web Part para exibir arquivos de definição de relatório (.rdl) criados no Construtor de Relatórios ou Designer de Relatórios e carregados em uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e1d83-104">You can use the Web Part to display report definition (.rdl) files that you created in Report Builder or Report Designer and uploaded to a library.</span></span>  
  
 <span data-ttu-id="e1d83-105">É possível adicionar a Web Part do Visualizador de Relatórios a uma página da Web se você quiser inserir um relatório nessa página.</span><span class="sxs-lookup"><span data-stu-id="e1d83-105">You can add the Report Viewer Web Part to a Web page if you want to embed a report on that page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1d83-106">Apesar de terem nomes idênticos, a Web Part do Visualizador de Relatórios instalada pelo suplemento [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] é diferente da Web Part do Visualizador de Relatórios incluída no arquivo RSWebParts.cab.</span><span class="sxs-lookup"><span data-stu-id="e1d83-106">Although they have identical names, the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in is different from the Report Viewer Web Part that is included in the RSWebParts.cab file.</span></span> <span data-ttu-id="e1d83-107">As instruções neste tópico são específicas para a Web Part do Visualizador de Relatórios instalada pelo suplemento [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1d83-107">The instructions in this topic are specifically for the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
 <span data-ttu-id="e1d83-108">Para adicionar uma Web Part a uma página da Web é necessário ter a permissão Adicionar e Personalizar Páginas de site.</span><span class="sxs-lookup"><span data-stu-id="e1d83-108">To add a Web Part to a Web page, you must have the Add and Customize Pages permission at the site level.</span></span> <span data-ttu-id="e1d83-109">Se você estiver usando as configurações de segurança padrão, essa permissão será concedida a membros do grupo **Proprietários** que tenham nível de permissão Controle Total.</span><span class="sxs-lookup"><span data-stu-id="e1d83-109">If you are using default security settings, this permission is granted to members of the **Owners** group who have the Full Control level of permission.</span></span>  
  
### <a name="to-embed-a-report-in-a-web-page"></a><span data-ttu-id="e1d83-110">Para inserir um relatório em uma página da Web</span><span class="sxs-lookup"><span data-stu-id="e1d83-110">To embed a report in a Web page</span></span>  
  
1.  <span data-ttu-id="e1d83-111">Abra ou crie uma página ou um painel da Web Part.</span><span class="sxs-lookup"><span data-stu-id="e1d83-111">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="e1d83-112">Em **Ações do Site**, clique em **Editar Página**.</span><span class="sxs-lookup"><span data-stu-id="e1d83-112">On **Site Actions**, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="e1d83-113">Clique em **Adicionar uma Web Part**.</span><span class="sxs-lookup"><span data-stu-id="e1d83-113">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="e1d83-114">Na lista de categorias de web part, selecione a categoria **Diversas** e depois selecione **Visualizador de Relatórios do SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="e1d83-114">In the list of web part categories, select the **Miscellaneous** category, and then select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="e1d83-115">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e1d83-115">Click **Add**.</span></span> <span data-ttu-id="e1d83-116">A Web Part será adicionada à parte superior da zona.</span><span class="sxs-lookup"><span data-stu-id="e1d83-116">The Web Part is added at the top of the zone.</span></span> <span data-ttu-id="e1d83-117">Você pode arrastá-la para um local diferente na zona.</span><span class="sxs-lookup"><span data-stu-id="e1d83-117">You can drag it to a different location in the zone.</span></span>  
  
6.  <span data-ttu-id="e1d83-118">No visualizador, clique em **Clique aqui abrir o painel de ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="e1d83-118">Within the viewer, click **Click here to open the tool pane**.</span></span>  
  
7.  <span data-ttu-id="e1d83-119">Selecione um relatório de qualquer biblioteca na coleção de sites atuais clicando no botão Procurar (**...**).</span><span class="sxs-lookup"><span data-stu-id="e1d83-119">Select a report from any library in the current site collection by clicking the browse (**...**) button.</span></span> <span data-ttu-id="e1d83-120">Você também pode digitar a URL do relatório.</span><span class="sxs-lookup"><span data-stu-id="e1d83-120">You can also type the report URL.</span></span> <span data-ttu-id="e1d83-121">Para determinar a URL de um relatório, clique com o botão direito do mouse no relatório e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e1d83-121">To determine the URL for any report, right-click the report and select **Properties**.</span></span> <span data-ttu-id="e1d83-122">Não clique na seta para baixo ao lado do relatório; a URL do relatório não está indicada na página Exibir Propriedades do item.</span><span class="sxs-lookup"><span data-stu-id="e1d83-122">Do not click the down arrow next to the report; the report URL is not indicated in the View Properties page of the item.</span></span> <span data-ttu-id="e1d83-123">Se você copiar e colar a URL da caixa de diálogo **Propriedades** , substitua a codificação de URL "%20" por um espaço (por exemplo, "Company%20Sales" deverá ser "Company Sales").</span><span class="sxs-lookup"><span data-stu-id="e1d83-123">If you copy and paste the URL from the **Properties** dialog box, replace the "%20" URL encoding with a space (for example, "Company%20Sales" should be "Company Sales").</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e1d83-124">Cada Web Part do Visualizador de Relatórios contém um único relatório.</span><span class="sxs-lookup"><span data-stu-id="e1d83-124">Each Report Viewer Web Part contains a single report.</span></span> <span data-ttu-id="e1d83-125">É necessário que a URL seja totalmente qualificada para um relatório que está no site do SharePoint atual ou em um site no mesmo aplicativo ou farm da Web.</span><span class="sxs-lookup"><span data-stu-id="e1d83-125">The URL must be the fully qualified path to a report that is on the current SharePoint site, or on a site within the same Web application or farm.</span></span> <span data-ttu-id="e1d83-126">A URL deve apontar para uma biblioteca de documentos ou para uma pasta em uma biblioteca de documentos que contenha o relatório.</span><span class="sxs-lookup"><span data-stu-id="e1d83-126">The URL must resolve to a document library or to a folder within a document library that contains the report.</span></span> <span data-ttu-id="e1d83-127">A URL do relatório deve incluir a extensão de arquivo .rdl.</span><span class="sxs-lookup"><span data-stu-id="e1d83-127">The report URL must include the .rdl file extension.</span></span> <span data-ttu-id="e1d83-128">Se o relatório depender de um arquivo de fonte de dados compartilhados ou de modelo, não será necessário especificar esses arquivos na URL.</span><span class="sxs-lookup"><span data-stu-id="e1d83-128">If the report depends on a model or shared data source files, you do not need to specify those files in the URL.</span></span> <span data-ttu-id="e1d83-129">O relatório contém referências aos arquivos necessários.</span><span class="sxs-lookup"><span data-stu-id="e1d83-129">The report contains references to the files it needs.</span></span>  
  
8.  <span data-ttu-id="e1d83-130">Enquanto o painel de ferramentas estiver aberto, você poderá definir propriedades para modificar a aparência e o layout padrão.</span><span class="sxs-lookup"><span data-stu-id="e1d83-130">While the tool pane is open, you can set properties to modify the default appearance and layout.</span></span>  
  
9. <span data-ttu-id="e1d83-131">Clique em **Aplicar** na parte inferior do painel de ferramentas e clique em **OK** para fechar esse painel.</span><span class="sxs-lookup"><span data-stu-id="e1d83-131">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d83-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e1d83-132">See Also</span></span>  
 <span data-ttu-id="e1d83-133">[Web Part do Visualizador de relatórios em um site do SharePoint](../report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="e1d83-133">[Report Viewer Web Part on a SharePoint Site](../report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 <span data-ttu-id="e1d83-134">[Personalizar a Web Part do Visualizador de relatórios](../customize-the-report-viewer-web-part.md) </span><span class="sxs-lookup"><span data-stu-id="e1d83-134">[Customize the Report Viewer Web Part](../customize-the-report-viewer-web-part.md) </span></span>  
 <span data-ttu-id="e1d83-135">[Concedendo permissões em itens do servidor de relatório em um site do SharePoint](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="e1d83-135">[Granting Permissions on Report Server Items on a SharePoint Site](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="e1d83-136">Instalar ou desinstalar o suplemento Reporting Services para SharePoint &#40;SharePoint 2010 e SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="e1d83-136">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](../install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
