---
title: Analisar no Excel (guia navegador, designer de cubo) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.datapane.f1
- sql12.asvs.ssms.analyzeinexcel.f1
ms.assetid: 890ed457-137e-44ac-9b2c-83344a1b8fc9
author: minewiskan
ms.author: owend
ms.openlocfilehash: b9fa27ae291d40b7f5637e3968438fcaec1de03d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571190"
---
# <a name="analyze-in-excel-browser-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="29028-102">Analisar no Excel (guia Navegador, Designer de Cubo) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="29028-102">Analyze in Excel (Browser Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="29028-103">**Analisar no Excel** oferece ao desenvolvedor de cubo uma forma rápida de examinar a aparência de um projeto para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="29028-103">**Analyze in Excel** provides the cube developer with a way to quickly review how a project would look to the end user.</span></span> <span data-ttu-id="29028-104">O recurso **Analisar no Excel** abre o Microsoft Excel, cria uma conexão da fonte de dados para o banco de dados de workspace e adiciona automaticamente uma Tabela Dinâmica à planilha.</span><span class="sxs-lookup"><span data-stu-id="29028-104">The **Analyze in Excel** feature opens Microsoft Excel, creates a data source connection to the workspace database, and automatically adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="29028-105">Esse recurso substitui o Office Web Control que forneceu um Tabela Dinâmica inserida na guia Navegador nas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="29028-105">This feature replaces the Office Web Control that provided an embedded PivotTable in the Browser tab in previous releases.</span></span>  
  
 <span data-ttu-id="29028-106">**Para exibir dados de cubo:**</span><span class="sxs-lookup"><span data-stu-id="29028-106">**To view cube data:**</span></span>  
  
1.  <span data-ttu-id="29028-107">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no Gerenciador de Soluções, clique duas vezes em um cubo para abri-lo no Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="29028-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in Solution Explorer, double-click a cube to open it in Cube Designer.</span></span>  
  
2.  <span data-ttu-id="29028-108">Clique na guia **Navegador** .</span><span class="sxs-lookup"><span data-stu-id="29028-108">Click the **Browser** tab.</span></span>  
  
3.  <span data-ttu-id="29028-109">Clique em **Reconectar** para validar a conexão.</span><span class="sxs-lookup"><span data-stu-id="29028-109">Click **Reconnect** to validate the connection.</span></span>  
  
4.  <span data-ttu-id="29028-110">Clique no ícone do Excel na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="29028-110">Click the Excel icon in the menu bar.</span></span>  
  
5.  <span data-ttu-id="29028-111">Quando solicitado a habilitar conexões de dados, clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="29028-111">When asked to enable data connections, click **Enable**.</span></span> <span data-ttu-id="29028-112">O Excel é aberto usando a conexão de dados atual, adicionando uma Tabela Dinâmica à planilha para que você possa começar a procurar seus dados.</span><span class="sxs-lookup"><span data-stu-id="29028-112">Excel opens using the current data connection, adding a PivotTable to the worksheet so that you can begin browsing your data.</span></span>  
  
 <span data-ttu-id="29028-113">Agora você pode criar uma Tabela Dinâmica de modo interativo arrastando medidas da tabela de fatos para a área Valores e atributos de dimensão para as áreas Linha e Coluna.</span><span class="sxs-lookup"><span data-stu-id="29028-113">You can now build a PivotTable interactively by dragging measures from the fact table to the Values area, and dimension attributes to the Row and Column areas.</span></span> <span data-ttu-id="29028-114">Se você tiver hierarquias, adicione-as às áreas Linhas ou Coluna.</span><span class="sxs-lookup"><span data-stu-id="29028-114">If you have hierarchies, add them to Rows or Column areas.</span></span> <span data-ttu-id="29028-115">Você pode acumular ou fazer uma busca detalhada na hierarquia para procurar dados de fato em níveis diferentes.</span><span class="sxs-lookup"><span data-stu-id="29028-115">You can roll up or drill down the hierarchy to browse fact data at different levels.</span></span>  
  
 <span data-ttu-id="29028-116">Os objetos e os dados são exibidos no contexto do usuário efetivo ou de função e perspectiva.</span><span class="sxs-lookup"><span data-stu-id="29028-116">Objects and data are viewed within the context of the effective user or role and perspective.</span></span> <span data-ttu-id="29028-117">Ao usar o Excel, as credenciais do usuário atual, e não as credenciais especificadas na página **Informações da Representação** , são usadas na conexão com a fonte de dados quando uma consulta é executada.</span><span class="sxs-lookup"><span data-stu-id="29028-117">When using Excel, the credentials of the current user, not the credentials specified in the **Impersonation Information** page, are used to connect to the data source when a query is executed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29028-118">Para usar o recurso Analisar no Excel, o Excel deve estar instalado no mesmo computador do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29028-118">To use the Analyze in Excel feature, Excel must be installed on the same computer as [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="29028-119">Se o Excel não estiver instalado no mesmo computador, você poderá usar o Excel em outro computador e conectar-se ao cubo como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="29028-119">If Excel is not installed on the same computer, you can use Excel on another computer and connect to the cube as a data source.</span></span> <span data-ttu-id="29028-120">Você pode então adicionar manualmente uma Tabela Dinâmica à planilha.</span><span class="sxs-lookup"><span data-stu-id="29028-120">You can then manually add a PivotTable to the worksheet.</span></span> <span data-ttu-id="29028-121">Os objetos de modelo (tabelas, colunas, medidas e KPIs) são incluídos como campos na lista de campos da Tabela Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="29028-121">Model objects (tables, columns, measures, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
 <span data-ttu-id="29028-122">Para obter mais informações sobre o recurso **Analisar no Excel** , consulte estes recursos:</span><span class="sxs-lookup"><span data-stu-id="29028-122">For more information about the **Analyze in Excel** feature, see these resources:</span></span>  
  
 [<span data-ttu-id="29028-123">Analisar no Excel &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="29028-123">Analyze in Excel &#40;SSAS Tabular&#41;</span></span>](tabular-models/analyze-in-excel-ssas-tabular.md)  
  
 [<span data-ttu-id="29028-124">Analisar um modelo de tabela no Excel &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="29028-124">Analyze a Tabular Model in Excel &#40;SSAS Tabular&#41;</span></span>](tabular-models/analyze-a-tabular-model-in-excel-ssas-tabular.md)  
  
 [<span data-ttu-id="29028-125">Procurar dados e metadados no Cubo</span><span class="sxs-lookup"><span data-stu-id="29028-125">Browse data and metadata in Cube</span></span>](multidimensional-models/browse-data-and-metadata-in-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="29028-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29028-126">See Also</span></span>  
 <span data-ttu-id="29028-127">[Navegador &#40;designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="29028-127">[Browser &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="29028-128">[Barra de ferramentas &#40;guia navegador, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](toolbar-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="29028-128">[Toolbar &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="29028-129">[Guia do navegador de metadados &#40;, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](metadata-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="29028-129">[Metadata &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](metadata-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="29028-130">Consulta e filtro &#40;guia navegador, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="29028-130">Query and Filter &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](query-filter-browser-cube-designer-analysis-services-multidimensional-data.md)  
  
  