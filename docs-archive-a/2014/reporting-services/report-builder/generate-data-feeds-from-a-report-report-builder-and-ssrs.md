---
title: Gerar feeds de dados com base em um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e68baae2-9f2a-4f13-9179-9ac7f29111c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 340191396aaaa92fe14fe8c3c6b42539a713eb45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569164"
---
# <a name="generate-data-feeds-from-a-report-report-builder-and-ssrs"></a><span data-ttu-id="61986-102">Gerar feeds de dados de um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="61986-102">Generate Data Feeds from a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="61986-103">Você pode gerar feeds de dados em conformidade com Atom a partir de relatórios e, em seguida, usar os feeds de dados em aplicativos, como o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] cliente, que pode consumir feeds de dados.</span><span class="sxs-lookup"><span data-stu-id="61986-103">You can generate Atom-compliant data feeds from reports, and then use the data feeds in applications, such as the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] client, that can consume data feeds.</span></span>  
  
 <span data-ttu-id="61986-104">A extensão de renderização do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Atom gera um documento de serviço Atom que lista os feeds de dados disponíveis a partir de um relatório.</span><span class="sxs-lookup"><span data-stu-id="61986-104">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Atom rendering extension generates an Atom service document that lists the data feeds available from a report.</span></span> <span data-ttu-id="61986-105">O documento lista pelo menos um feed de dados para cada região no relatório.</span><span class="sxs-lookup"><span data-stu-id="61986-105">The document lists at least one data feed for each data region in the report.</span></span> <span data-ttu-id="61986-106">Dependendo do tipo de região de dados e dos dados que a região de dados exibe, o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] pode gerar vários feeds de dados de uma região de dados.</span><span class="sxs-lookup"><span data-stu-id="61986-106">Depending on the type of data region and the data that the data region displays, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might generate multiple data feeds from a data region.</span></span>  
  
 <span data-ttu-id="61986-107">O documento de serviço Atom contém um identificador exclusivo para cada feed de dados e você usa o identificador em uma URL para exibir o conteúdo do feed de dados.</span><span class="sxs-lookup"><span data-stu-id="61986-107">Atom service document contains a unique identifier for each the data feed and you use the identifier in a URL to view the content of the data feed.</span></span>  
  
 <span data-ttu-id="61986-108">Para obter mais informações, consulte [gerando feeds de dados de relatórios &#40;Construtor de relatórios e SSRS&#41;](generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="61986-108">For more information, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-generate-an-atom-service-document"></a><span data-ttu-id="61986-109">Para gerar um documento de serviço Atom</span><span class="sxs-lookup"><span data-stu-id="61986-109">To generate an Atom service document</span></span>  
  
1.  <span data-ttu-id="61986-110">Na página **inicial** do Gerenciador de Relatórios, navegue até o relatório do qual você deseja gerar feeds de dados.</span><span class="sxs-lookup"><span data-stu-id="61986-110">From the Report Manager **Home** page, navigate to the report from which you want to generate data feeds.</span></span>  
  
2.  <span data-ttu-id="61986-111">Clique no relatório.</span><span class="sxs-lookup"><span data-stu-id="61986-111">Click the report.</span></span>  
  
     <span data-ttu-id="61986-112">O relatório é executado.</span><span class="sxs-lookup"><span data-stu-id="61986-112">The report is run.</span></span>  
  
3.  <span data-ttu-id="61986-113">Na barra de ferramentas, clique no ícone Exportar para Feed de Dados.</span><span class="sxs-lookup"><span data-stu-id="61986-113">On the toolbar, click the Export to Data Feed icon.</span></span>  
  
     <span data-ttu-id="61986-114">Uma mensagem é exibida perguntando se você deseja salvar ou abrir o documento Atom que contém o feed de dados.</span><span class="sxs-lookup"><span data-stu-id="61986-114">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
4.  <span data-ttu-id="61986-115">Clique em **Salvar** para salvar o documento no sistema de arquivos, ou clique em **Abrir** para exibir o conteúdo do documento antes de salvá-lo.</span><span class="sxs-lookup"><span data-stu-id="61986-115">Click **Save** to save the document to the file system, or click **Open** to view the document content before saving.</span></span> <span data-ttu-id="61986-116">**Por padrão, o documento é aberto em um navegador.**</span><span class="sxs-lookup"><span data-stu-id="61986-116">**By default, the document opens in a browser.**</span></span>  
  
5.  <span data-ttu-id="61986-117">Navegue até o local onde o documento será salvo.</span><span class="sxs-lookup"><span data-stu-id="61986-117">Browse to the location to save the document.</span></span>  
  
6.  <span data-ttu-id="61986-118">Outra opção é alterar o nome do documento.</span><span class="sxs-lookup"><span data-stu-id="61986-118">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61986-119">Por padrão, o nome do documento é o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="61986-119">By default, the document name is the report name.</span></span>  
  
7.  <span data-ttu-id="61986-120">Verifique se o tipo do documento é **Arquivo ATOMSVC**e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="61986-120">Verify the document type is **ATOMSVC File**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="61986-121">Opcionalmente, abra o arquivo .atomsvc em um navegador, editor de texto ou editor de XML.</span><span class="sxs-lookup"><span data-stu-id="61986-121">Optionally, open the .atomsvc file in a browser or text or XML editor.</span></span>  
  
### <a name="to-view-an-atom-compliant-data-feed"></a><span data-ttu-id="61986-122">Para exibir um feed de dados compatível com Atom</span><span class="sxs-lookup"><span data-stu-id="61986-122">To view an Atom-compliant data feed</span></span>  
  
1.  <span data-ttu-id="61986-123">Se o documento de serviço Atom ainda não estiver aberto, localize-o e abra-o em um navegador como o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="61986-123">If the Atom service document is not already open, locate it and open it in a browser such as Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="61986-124">Copie no navegador a URL do feed de dados a ser exibida a partir do documento de serviço Atom.</span><span class="sxs-lookup"><span data-stu-id="61986-124">Copy the URL of the data feed that you want to view from the Atom service document to the browser.</span></span>  
  
     <span data-ttu-id="61986-125">Este é o formato da URL:</span><span class="sxs-lookup"><span data-stu-id="61986-125">The format of the URL is the following:</span></span>  
  
 `http://<server name>/ReportServer?%2f<ReportName>rs%3aCommand=Render&rs%3aFormat=ATOM&rc%3aDataFeed=<Identifier>`  
  
1.  <span data-ttu-id="61986-126">Pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="61986-126">Press ENTER.</span></span>  
  
     <span data-ttu-id="61986-127">Uma mensagem é exibida perguntando se você deseja salvar ou abrir o documento Atom que contém o feed de dados.</span><span class="sxs-lookup"><span data-stu-id="61986-127">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
2.  <span data-ttu-id="61986-128">Clique em **Salvar** para salvar o documento no sistema de arquivos, ou clique em **Abrir** para exibir o feed de dados antes de salvar o documento.</span><span class="sxs-lookup"><span data-stu-id="61986-128">Click **Save** to save the document to the file system, or click **Open** to view the data feed before saving.</span></span>  
  
3.  <span data-ttu-id="61986-129">Navegue até o local onde o documento será salvo.</span><span class="sxs-lookup"><span data-stu-id="61986-129">Browse to the location to save the document.</span></span>  
  
4.  <span data-ttu-id="61986-130">Outra opção é alterar o nome do documento.</span><span class="sxs-lookup"><span data-stu-id="61986-130">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61986-131">Por padrão, o nome do documento é o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="61986-131">By default the document name is the report name.</span></span> <span data-ttu-id="61986-132">Se o documento de serviço Atom tiver vários feeds, por padrão todos usarão o mesmo nome, o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="61986-132">If the Atom service document has multiple feeds, by default all use the same name, the report name.</span></span> <span data-ttu-id="61986-133">Para diferenciá-los, renomeie-os para usar nomes significativos.</span><span class="sxs-lookup"><span data-stu-id="61986-133">To differentiate them, rename them to use meaningful names.</span></span>  
  
5.  <span data-ttu-id="61986-134">Verifique se o tipo do documento é **Arquivo ATOM**e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="61986-134">Verify the document type is **ATOM File**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="61986-135">Opcionalmente, abra o arquivo .atom em um navegador, editor de texto ou editor de XML.</span><span class="sxs-lookup"><span data-stu-id="61986-135">Optionally, open the .atom file in a browser or text editor or XML editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61986-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="61986-136">See Also</span></span>  
 [<span data-ttu-id="61986-137">Exportando relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="61986-137">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](export-reports-report-builder-and-ssrs.md)  
  
  
