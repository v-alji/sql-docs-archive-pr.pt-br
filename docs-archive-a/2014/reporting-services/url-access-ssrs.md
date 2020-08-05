---
title: Acesso à URL (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services]
- links [Reporting Services], URL access
- URL access [Reporting Services], about URL access
- parameters [Reporting Services], URL access
- report servers [Reporting Services], URL access
- hyperlinks [Reporting Services]
ms.assetid: 52c3f2a3-3d6d-4fee-9c46-83f366919398
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf44ea3c15c12f37eebf6e89faf4ff3affd64433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572359"
---
# <a name="url-access-ssrs"></a><span data-ttu-id="4402a-102">Acesso à URL (SSRS)</span><span class="sxs-lookup"><span data-stu-id="4402a-102">URL Access (SSRS)</span></span>
  <span data-ttu-id="4402a-103">O acesso à URL do servidor de relatório do SQL Server Reporting Services (SSRS) permite enviar comandos a um servidor de relatório por meio de uma solicitação de URL.</span><span class="sxs-lookup"><span data-stu-id="4402a-103">URL access of the report server in SQL Server Reporting Services (SSRS) enables you to send commands to a report server through a URL request.</span></span> <span data-ttu-id="4402a-104">Por exemplo, você pode personalizar a renderização de um relatório em um servidor de relatório em modo nativo ou em uma biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4402a-104">For example, you can customize the rendering of a report on a native mode report server or in a SharePoint library.</span></span> <span data-ttu-id="4402a-105">Você pode exibir o relatório usando um conjunto específico de valores de parâmetros de relatório ou exibir uma página específica de interesse do relatório.</span><span class="sxs-lookup"><span data-stu-id="4402a-105">You may have viewed the report using a specific set of report parameter values, or you may have been viewing a particular page of interest in the report.</span></span> <span data-ttu-id="4402a-106">Você pode encapsular essas informações na URL usando parâmetros de acesso à URL predefinidos.</span><span class="sxs-lookup"><span data-stu-id="4402a-106">You can encapsulate this information in the URL using predefined URL access parameters.</span></span> <span data-ttu-id="4402a-107">Você pode personalizar ainda mais como o servidor de relatório processa o relatório inserindo parâmetros de renderização de formatos ou de aparência do visualizador de relatórios.</span><span class="sxs-lookup"><span data-stu-id="4402a-107">You can further customize how the report server processes the report by embedding parameters for rendering formats or for the look and feel of the report viewer.</span></span> <span data-ttu-id="4402a-108">Você pode colar essa URL diretamente em um email ou página da Web para permitir que outros acessem seu relatório da mesma maneira no navegador.</span><span class="sxs-lookup"><span data-stu-id="4402a-108">You can then paste this URL directly into an email or Web page to let others to access your report in the same manner in the browser.</span></span>  
  
 <span data-ttu-id="4402a-109">Outras ações que você pode executar por acesso à URL são:</span><span class="sxs-lookup"><span data-stu-id="4402a-109">Other actions you can perform through URL access are:</span></span>  
  
-   <span data-ttu-id="4402a-110">Enviar comandos ao visualizador de HTML, como ajuste de aparência</span><span class="sxs-lookup"><span data-stu-id="4402a-110">Send commands to the HTML viewer, such as adjusting its look and feel</span></span>  
  
-   <span data-ttu-id="4402a-111">Listar os itens filho de uma pasta de catálogo</span><span class="sxs-lookup"><span data-stu-id="4402a-111">List the children of a catalog folder</span></span>  
  
-   <span data-ttu-id="4402a-112">Recuperar a definição de XML de um item de catálogo</span><span class="sxs-lookup"><span data-stu-id="4402a-112">Retrieve the XML definition of a catalog item</span></span>  
  
-   <span data-ttu-id="4402a-113">Renderizar um instantâneo de histórico de relatório específico</span><span class="sxs-lookup"><span data-stu-id="4402a-113">Render a specific report history snapshot</span></span>  
  
-   <span data-ttu-id="4402a-114">Gerenciar sessões de relatório</span><span class="sxs-lookup"><span data-stu-id="4402a-114">Manage report sessions</span></span>  
  
 <span data-ttu-id="4402a-115">Para conferir a lista completa de comandos e configurações disponíveis por acesso à URL, consulte [Referência de parâmetro de acesso de URL](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4402a-115">For the complete list of commands and settings available through URL access, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="url-access-concepts"></a><span data-ttu-id="4402a-116">Conceitos do acesso à URL</span><span class="sxs-lookup"><span data-stu-id="4402a-116">URL Access Concepts</span></span>  
 <span data-ttu-id="4402a-117">As solicitações de URL ao servidor de relatório contêm parâmetros processados pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4402a-117">URL requests to the report server contain parameters that are processed by the report server.</span></span> <span data-ttu-id="4402a-118">A forma como o servidor de relatório manipula as solicitações de URL dependerá dos parâmetros, dos prefixos de parâmetro e dos tipos de item incluídos na URL.</span><span class="sxs-lookup"><span data-stu-id="4402a-118">The way in which the report server handles URL requests depends on the parameters, parameter prefixes, and types of items that are included in the URL.</span></span> <span data-ttu-id="4402a-119">As URLs dos servidores de relatório aderem às diretrizes de formatação de URL propostas pelo padrão de rascunho do consórcio W3C/IETF.</span><span class="sxs-lookup"><span data-stu-id="4402a-119">Report server URLs adhere to the URL formatting guidelines as proposed by the joint World Wide Web Consortium W3C/IETF draft standard.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="4402a-120">é compatível com a maioria dos navegadores de Internet ou dos aplicativos que dão suporte ao endereçamento de URL padrão.</span><span class="sxs-lookup"><span data-stu-id="4402a-120">URL functionality is compatible with most Internet browsers or applications that support standard URL addressing.</span></span>  
  
### <a name="url-access-syntax"></a><span data-ttu-id="4402a-121">Sintaxe do acesso à URL</span><span class="sxs-lookup"><span data-stu-id="4402a-121">URL Access Syntax</span></span>  
 <span data-ttu-id="4402a-122">As solicitações de URL podem conter vários parâmetros listados em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="4402a-122">URL requests can contain multiple parameters that are listed in any order.</span></span> <span data-ttu-id="4402a-123">Os parâmetros são separados por um E comercial (&) e os pares de nome/valor são separados por um sinal de igualdade (=).</span><span class="sxs-lookup"><span data-stu-id="4402a-123">Parameters are separated by an ampersand (&) and name/value pairs are separated by an equal sign (=).</span></span>  
  
```  
  
rswebserviceurl  
?  
reportpath  
      [&prefix:param=value]...n]  
  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="4402a-124">Descrição da sintaxe</span><span class="sxs-lookup"><span data-stu-id="4402a-124">Syntax Description</span></span>  
 <span data-ttu-id="4402a-125">*rswebserviceurl*</span><span class="sxs-lookup"><span data-stu-id="4402a-125">*rswebserviceurl*</span></span>  
 <span data-ttu-id="4402a-126">A URL do serviço Web do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4402a-126">The Web service URL of the report server.</span></span> <span data-ttu-id="4402a-127">No modo nativo, é a URL do serviço Web da instância do servidor de relatório configurada no Gerenciador de Configurações do Reporting Services (consulte [Configurar as URLs do Servidor de Relatório &#40; 	Gerenciador de Configurações do SSRS&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)).</span><span class="sxs-lookup"><span data-stu-id="4402a-127">For native mode, it is the Web service URL of the report server instance configured in Reporting Services Configuration Manager (see [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)).</span></span> <span data-ttu-id="4402a-128">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4402a-128">For example:</span></span>  
  
```  
http://myrshost/reportserver  
https://machine.adventure-works.com/reportserver_MYNAMEDINSTANCE  
```  
  
 <span data-ttu-id="4402a-129">No modo integrado do SharePoint, é a URL do proxy do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] em um site do SharePoint integrado ao [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4402a-129">For SharePoint integrated mode, it is the URL of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] proxy at a SharePoint site integrated with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="4402a-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4402a-130">For example:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver  
```  
  
> [!TIP]  
>  <span data-ttu-id="4402a-131">É importante que a URL inclua a sintaxe do proxy `_vti_bin` para rotear a solicitação através do SharePoint e do proxy HTTP [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4402a-131">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="4402a-132">O proxy adiciona qualquer contexto à solicitação HTTP, o contexto necessário para garantir a execução adequada do relatório para servidores de relatório no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4402a-132">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
 <span data-ttu-id="4402a-133">*pathinfo*</span><span class="sxs-lookup"><span data-stu-id="4402a-133">*pathinfo*</span></span>  
 <span data-ttu-id="4402a-134">O nome do caminho relativo do item no banco de dados do servidor de relatório no modo nativo ou a URL totalmente qualificada do item em um catálogo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4402a-134">The relative path name of the item in the native mode report server database, or the fully qualified URL of the item in a SharePoint catalog.</span></span>  
  
 <span data-ttu-id="4402a-135">O caminho do item de catálogo.</span><span class="sxs-lookup"><span data-stu-id="4402a-135">The path of the catalog item.</span></span> <span data-ttu-id="4402a-136">No modo nativo, é o caminho relativo do item no banco de dados do servidor de relatório, que começa com uma barra (`/`).</span><span class="sxs-lookup"><span data-stu-id="4402a-136">For native mode, it is the relative path of the item in the report server database, beginning with a slash (`/`).</span></span> <span data-ttu-id="4402a-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4402a-137">For example:</span></span>  
  
```  
/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2  
```  
  
 <span data-ttu-id="4402a-138">No modo integrado do SharePoint, é a URL totalmente qualificada do item na biblioteca do SharePoint, incluindo a extensão do item.</span><span class="sxs-lookup"><span data-stu-id="4402a-138">For SharePoint integrated mode, it is the fully qualified URL of the item in the SharePoint library, including the item extension.</span></span> <span data-ttu-id="4402a-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4402a-139">For example:</span></span>  
  
```  
http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl  
```  
  
 `&`  
 <span data-ttu-id="4402a-140">Usado para separar os pares de nome e valor dos parâmetros de acesso à URL.</span><span class="sxs-lookup"><span data-stu-id="4402a-140">Used to separate name and value pairs of URL access parameters.</span></span>  
  
 <span data-ttu-id="4402a-141">**prefixo**</span><span class="sxs-lookup"><span data-stu-id="4402a-141">**prefix**</span></span>  
 <span data-ttu-id="4402a-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4402a-142">Optional.</span></span> <span data-ttu-id="4402a-143">Um prefixo do parâmetro de acesso à URL (por exemplo, `rs:` ou `rc:`) que acessa um processo específico executado no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4402a-143">A prefix for the URL access parameter (for example, `rs:` or `rc:`) that accesses a specific process running within the report server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4402a-144">Se um prefixo de um parâmetro de acesso à URL não for incluído, o parâmetro será processado pelo servidor de relatório como um parâmetro de relatório.</span><span class="sxs-lookup"><span data-stu-id="4402a-144">If a prefix for a URL access parameter is not included, the parameter is processed by the report server as a report parameter.</span></span> <span data-ttu-id="4402a-145">Os parâmetros de relatório não usam um prefixo de parâmetro e diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4402a-145">Report parameters do not use a parameter prefix and are case-sensitive.</span></span>  
  
 <span data-ttu-id="4402a-146">**param**</span><span class="sxs-lookup"><span data-stu-id="4402a-146">**param**</span></span>  
 <span data-ttu-id="4402a-147">O nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4402a-147">The parameter name.</span></span>  
  
 <span data-ttu-id="4402a-148">*value*</span><span class="sxs-lookup"><span data-stu-id="4402a-148">*value*</span></span>  
 <span data-ttu-id="4402a-149">O texto da URL correspondente ao valor do parâmetro usado.</span><span class="sxs-lookup"><span data-stu-id="4402a-149">URL text corresponding to the value of the parameter being used.</span></span>  
  
 <span data-ttu-id="4402a-150">**Observação:** para obter uma lista dos parâmetros de acesso a URL disponíveis, consulte [URL Access Parameter Reference](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4402a-150">**Note:** For a list of the available URL access parameters, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span> <span data-ttu-id="4402a-151">Para obter exemplos de como transmitir parâmetros de relatório na URL, consulte [Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="4402a-151">For examples passing report parameters on the URL, see [Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4402a-152">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4402a-152">Related Tasks</span></span>  
  
|<span data-ttu-id="4402a-153">Descrições das tarefas</span><span class="sxs-lookup"><span data-stu-id="4402a-153">Task Descriptions</span></span>|<span data-ttu-id="4402a-154">Links</span><span class="sxs-lookup"><span data-stu-id="4402a-154">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="4402a-155">Acessar itens do servidor de relatório, como relatórios, fontes de dados compartilhadas e recursos.</span><span class="sxs-lookup"><span data-stu-id="4402a-155">Access report server items, such as reports, shared data sources, and resources.</span></span>|[<span data-ttu-id="4402a-156">Acessar itens de servidor de relatório com acesso à URL</span><span class="sxs-lookup"><span data-stu-id="4402a-156">Access Report Server Items Using URL Access</span></span>](access-report-server-items-using-url-access.md)|  
|<span data-ttu-id="4402a-157">Transmitir parâmetros de relatório a um relatório.</span><span class="sxs-lookup"><span data-stu-id="4402a-157">Pass report parameters to a report.</span></span>|[<span data-ttu-id="4402a-158">Passar um parâmetro de relatório em uma URL</span><span class="sxs-lookup"><span data-stu-id="4402a-158">Pass a Report Parameter Within a URL</span></span>](pass-a-report-parameter-within-a-url.md)|  
|<span data-ttu-id="4402a-159">Definir a localidade dos parâmetros de relatório na cadeia de caracteres de acesso à URL, o que define as interpretações de datas, moedas etc. específicas da localidade.</span><span class="sxs-lookup"><span data-stu-id="4402a-159">Set the locale of the report parameters in the URL access string, which defines the locale-specific interpretations of dates, currencies, and so on.</span></span>|[<span data-ttu-id="4402a-160">Definir o idioma para parâmetros de relatório em uma URL</span><span class="sxs-lookup"><span data-stu-id="4402a-160">Set the Language for Report Parameters in a URL</span></span>](set-the-language-for-report-parameters-in-a-url.md)|  
|<span data-ttu-id="4402a-161">Enviar configurações específicas da extensão de renderização que personalizam como o relatório é renderizado.</span><span class="sxs-lookup"><span data-stu-id="4402a-161">Send rendering extension specific settings that customize how the report is rendered.</span></span>|[<span data-ttu-id="4402a-162">Especificar configurações de informações de dispositivo em uma URL</span><span class="sxs-lookup"><span data-stu-id="4402a-162">Specify Device Information Settings in a URL</span></span>](specify-device-information-settings-in-a-url.md)|  
|<span data-ttu-id="4402a-163">Exportar um relatório diretamente para um formato de arquivo sem exibi-lo no navegador.</span><span class="sxs-lookup"><span data-stu-id="4402a-163">Export a report directly to a file format without viewing it in the browser.</span></span>|[<span data-ttu-id="4402a-164">Exportar um relatório com acesso à URL</span><span class="sxs-lookup"><span data-stu-id="4402a-164">Export a Report Using URL Access</span></span>](export-a-report-using-url-access.md)|  
|<span data-ttu-id="4402a-165">Abrir um relatório e navegar diretamente ao local de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4402a-165">Open a report and navigate directly to the location of a string.</span></span>|[<span data-ttu-id="4402a-166">Pesquisar um relatório com acesso à URL</span><span class="sxs-lookup"><span data-stu-id="4402a-166">Search a Report Using URL Access</span></span>](search-a-report-using-url-access.md)|  
|<span data-ttu-id="4402a-167">Renderizar um instantâneo de histórico de relatório específico.</span><span class="sxs-lookup"><span data-stu-id="4402a-167">Render a specific report history snapshot.</span></span>|[<span data-ttu-id="4402a-168">Renderizar um instantâneo de histórico de relatório com acesso à URL</span><span class="sxs-lookup"><span data-stu-id="4402a-168">Render a Report History Snapshot Using URL Access</span></span>](render-a-report-history-snapshot-using-url-access.md)|  
  
## <a name="see-also"></a><span data-ttu-id="4402a-169">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4402a-169">See Also</span></span>  
 <span data-ttu-id="4402a-170">[Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md) </span><span class="sxs-lookup"><span data-stu-id="4402a-170">[Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md) </span></span>  
 <span data-ttu-id="4402a-171">[Referência de parâmetro de acesso à URL](url-access-parameter-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4402a-171">[URL Access Parameter Reference](url-access-parameter-reference.md) </span></span>  
 <span data-ttu-id="4402a-172">[Integrando o Reporting Services usando o acesso à URL](application-integration/integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="4402a-172">[Integrating Reporting Services Using URL Access](application-integration/integrating-reporting-services-using-url-access.md) </span></span>  
 [<span data-ttu-id="4402a-173">Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4402a-173">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
