---
title: Acessar itens do Servidor de Relatório usando o acesso à URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- referencing URL items for report server access
- URL access [Reporting Services], report servers
ms.assetid: a58b4ca6-129d-45e9-95c7-e9169fe5bba4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6693419490c1b3770ccb41b2645cbdba8996630a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575671"
---
# <a name="access-report-server-items-using-url-access"></a><span data-ttu-id="7c740-102">Acessar itens do Servidor de Relatório usando o acesso à URL</span><span class="sxs-lookup"><span data-stu-id="7c740-102">Access Report Server Items Using URL Access</span></span>
  <span data-ttu-id="7c740-103">Este tópico descreve como acessar itens de catálogo de diferentes tipos em um banco de dados do servidor de relatório ou em um site do SharePoint usando *rs:Command*=*Value*.</span><span class="sxs-lookup"><span data-stu-id="7c740-103">This topic describes how to access catalog items of different types in a report server data base or in a SharePoint site using *rs:Command*=*Value*.</span></span>  
  
 <span data-ttu-id="7c740-104">Não é necessário adicionar essa cadeia de caracteres de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7c740-104">It is not necessary to add this parameter string.</span></span> <span data-ttu-id="7c740-105">Se você omiti-la, o servidor de relatório avaliará o tipo de item e selecionará o valor de parâmetro apropriado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7c740-105">If you omit it, the report server evaluates the item type and selects the appropriate parameter value automatically.</span></span> <span data-ttu-id="7c740-106">No entanto, usar a cadeia de caracteres *rs:Command*=*Value* na URL melhora o desempenho do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="7c740-106">However, using the *rs:Command*=*Value* string in the URL improves the performance of the report server.</span></span>  
  
 <span data-ttu-id="7c740-107">Observe a sintaxe do proxy `_vti_bin` nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="7c740-107">Note the `_vti_bin` proxy syntax in the examples below.</span></span> <span data-ttu-id="7c740-108">Para obter mais informações sobre como usar a sintaxe do proxy, consulte [Referência de parâmetro de acesso à URL](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="7c740-108">For more information about using the proxy syntax, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="access-a-report"></a><span data-ttu-id="7c740-109">Acessar um relatório</span><span class="sxs-lookup"><span data-stu-id="7c740-109">Access a Report</span></span>  
 <span data-ttu-id="7c740-110">Para exibir um relatório no navegador, use o parâmetro de renderização *RS: Command* = *Render* .</span><span class="sxs-lookup"><span data-stu-id="7c740-110">To view a report in the browser, use the *rs:Command*=*Render* parameter.</span></span> <span data-ttu-id="7c740-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7c740-111">For example:</span></span>  
  
 <span data-ttu-id="7c740-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="7c740-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
 <span data-ttu-id="7c740-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="7c740-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="7c740-114">É importante que a URL inclua a sintaxe do proxy `_vti_bin` para rotear a solicitação através do SharePoint e do proxy HTTP [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c740-114">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="7c740-115">O proxy adiciona qualquer contexto à solicitação HTTP, o contexto necessário para garantir a execução adequada do relatório para servidores de relatório no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7c740-115">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
## <a name="access-a-resource"></a><span data-ttu-id="7c740-116">Acessar um recurso</span><span class="sxs-lookup"><span data-stu-id="7c740-116">Access a Resource</span></span>  
 <span data-ttu-id="7c740-117">Para acessar um recurso, use o parâmetro *RS: Command* = *GetResourceContents* . Se o recurso for compatível com o navegador, como uma imagem, ele será aberto no navegador.</span><span class="sxs-lookup"><span data-stu-id="7c740-117">To access a resource, use the *rs:Command*=*GetResourceContents* parameter.If the resource is compatible with the browser, such as an image, it is opened in the browser.</span></span> <span data-ttu-id="7c740-118">Caso contrário, você será solicitado a abrir ou salvar o arquivo ou recurso em disco.</span><span class="sxs-lookup"><span data-stu-id="7c740-118">Otherwise, you are prompted to open or save the file or resource to disk.</span></span>  
  
 <span data-ttu-id="7c740-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="7c740-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span></span>  
  
 <span data-ttu-id="7c740-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="7c740-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span></span>  
  
## <a name="access-a-data-source"></a><span data-ttu-id="7c740-121">Acessar uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="7c740-121">Access a Data Source</span></span>  
 <span data-ttu-id="7c740-122">Para acessar uma fonte de dados, use o parâmetro *RS: Command* = *GetDataSourceContents* .</span><span class="sxs-lookup"><span data-stu-id="7c740-122">To access a data source, use the *rs:Command*=*GetDataSourceContents* parameter.</span></span> <span data-ttu-id="7c740-123">Se houver suporte para XML em seu navegador, a definição de fonte de dados será exibida se você for um usuário autenticado com a permissão `Read Contents` na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7c740-123">If your browser supports XML, the data source definition is displayed if you are an authenticated user with `Read Contents` permission on the data source.</span></span> <span data-ttu-id="7c740-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7c740-124">For example:</span></span>  
  
 <span data-ttu-id="7c740-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="7c740-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="7c740-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="7c740-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="7c740-127">A estrutura XML pode ter uma aparência semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="7c740-127">The XML structure might look similar to the following example:</span></span>  
  
```  
<DataSourceDefinition>  
   <Extension>SQL</Extension>  
   <ConnectString>Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=AdventureWorks2012;Data Source=MYSERVER1;</ConnectString>  
   <CredentialRetrieval>Integrated</CredentialRetrieval>  
   <WindowsCredentials>False</WindowsCredentials>  
   <ImpersonateUser>False</ImpersonateUser>  
   <Prompt />  
   <Enabled>True</Enabled>  
</DataSourceDefinition>  
```  
  
 <span data-ttu-id="7c740-128">A cadeia de conexão é retornada com base na configuração **SecureConnectionLevel** do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="7c740-128">The connection string is returned based on the **SecureConnectionLevel** setting of the report server.</span></span> <span data-ttu-id="7c740-129">Para obter mais informações sobre a configuração **SecureConnectionLevel** , consulte [Usando métodos seguros do serviço Web](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="7c740-129">For more information about the **SecureConnectionLevel** setting, see [Using Secure Web Service Methods](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span></span>  
  
## <a name="access-the-contents-of-a-folder"></a><span data-ttu-id="7c740-130">Acessar o conteúdo de uma pasta</span><span class="sxs-lookup"><span data-stu-id="7c740-130">Access the Contents of a Folder</span></span>  
 <span data-ttu-id="7c740-131">Para acessar o conteúdo de uma pasta, use o parâmetro *RS: Command* = *GetChildren* .</span><span class="sxs-lookup"><span data-stu-id="7c740-131">To access the contents of a folder, use the *rs:Command*=*GetChildren* parameter.</span></span> <span data-ttu-id="7c740-132">Uma página genérica de navegação em pasta será retornada contendo links para subpastas, relatórios, fontes de dados e recursos na pasta solicitada.</span><span class="sxs-lookup"><span data-stu-id="7c740-132">A generic folder-navigation page is returned that contains links to the subfolders, reports, data sources, and resources in the requested folder.</span></span> <span data-ttu-id="7c740-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7c740-133">For example:</span></span>  
  
 <span data-ttu-id="7c740-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="7c740-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="7c740-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="7c740-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="7c740-136">A interface do usuário que você vê é semelhante ao modo de procura do diretório usado pelo [!INCLUDE[msCoName](../includes/msconame-md.md)] IIS (Servidor de Informações da Internet).</span><span class="sxs-lookup"><span data-stu-id="7c740-136">The user interface you see is similar to the directory browsing mode used by [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Information Server (IIS).</span></span> <span data-ttu-id="7c740-137">O número de versão, inclusive o número de compilação, do servidor de relatório também é exibido embaixo da listagem de pastas.</span><span class="sxs-lookup"><span data-stu-id="7c740-137">The version number, including the build number, of the report server is also displayed below the folder listing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c740-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7c740-138">See Also</span></span>  
 <span data-ttu-id="7c740-139">[Acesso à URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7c740-139">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="7c740-140">Referência de parâmetro de acesso de URL</span><span class="sxs-lookup"><span data-stu-id="7c740-140">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
