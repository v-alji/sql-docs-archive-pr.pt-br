---
title: Passar um parâmetro de relatório em uma URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services], passing parameters
- passing parameters [Reporting Services]
ms.assetid: f93a94cc-27b5-435a-aa85-69e6ec6459ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cf41ed82728d5d7c840276e135937b08f83fb131
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684592"
---
# <a name="pass-a-report-parameter-within-a-url"></a><span data-ttu-id="6ac49-102">Pass a Report Parameter Within a URL</span><span class="sxs-lookup"><span data-stu-id="6ac49-102">Pass a Report Parameter Within a URL</span></span>
  <span data-ttu-id="6ac49-103">Você pode transmitir parâmetros de relatório a um relatório incluindo-os em uma URL de relatório.</span><span class="sxs-lookup"><span data-stu-id="6ac49-103">You can pass report parameters to a report by including them in a report URL.</span></span> <span data-ttu-id="6ac49-104">Esses parâmetros de URL não são prefixados, pois eles são transmitidos diretamente para o mecanismo de processamento de relatório.</span><span class="sxs-lookup"><span data-stu-id="6ac49-104">These URL parameters are not prefixed because they are passed directly to the report processing engine.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6ac49-105">É importante que a URL inclua a sintaxe do proxy `_vti_bin` para rotear a solicitação através do SharePoint e do proxy HTTP [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ac49-105">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="6ac49-106">O proxy adiciona qualquer contexto à solicitação HTTP, o contexto necessário para garantir a execução adequada do relatório para servidores de relatório no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6ac49-106">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
>   
>  <span data-ttu-id="6ac49-107">Se você não incluir a sintaxe do proxy, será necessário prefixar o parâmetro com *RP:*.</span><span class="sxs-lookup"><span data-stu-id="6ac49-107">If you don't include the proxy syntax, then you need to prefix the parameter with *rp:*.</span></span>  
  
 <span data-ttu-id="6ac49-108">Todos os parâmetros de consulta podem ter parâmetros de relatório correspondentes.</span><span class="sxs-lookup"><span data-stu-id="6ac49-108">All query parameters can have corresponding report parameters.</span></span> <span data-ttu-id="6ac49-109">Você passa um parâmetro de consulta para um relatório, transmitindo o parâmetro de relatório correspondente.</span><span class="sxs-lookup"><span data-stu-id="6ac49-109">You pass a query parameter to a report by passing the corresponding report parameter.</span></span> <span data-ttu-id="6ac49-110">Para obter mais informações, consulte [Criar uma consulta no Designer de Consultas Relacionais &#40;Construtor de Relatórios e SSRS&#41;](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6ac49-110">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6ac49-111">Os parâmetros de relatório diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6ac49-111">Report parameters are case-sensitive.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="6ac49-112">Os parâmetros de relatório diferenciam maiúsculas de minúsculas e utilizam os seguintes caracteres especiais:</span><span class="sxs-lookup"><span data-stu-id="6ac49-112">Report parameters are case-sensitive and utilize the following special characters:</span></span>  
> 
>  -   <span data-ttu-id="6ac49-113">Qualquer caractere de espaço na cadeia de caracteres da URL será substituído pelos caracteres "% 20", de acordo com os padrões de codificação de URL.</span><span class="sxs-lookup"><span data-stu-id="6ac49-113">Any space characters in the URL string are replaced with the characters "%20," according to URL encoding standards.</span></span>  
> -   <span data-ttu-id="6ac49-114">Um caractere de espaço na parte do parâmetro da URL será substituído por um sinal de adição (+).</span><span class="sxs-lookup"><span data-stu-id="6ac49-114">A space character in the parameter portion of the URL is replaced with a plus character (+).</span></span>  
> -   <span data-ttu-id="6ac49-115">Um ponto-e-vírgula em qualquer parte da cadeia de caracteres será substituído pelos caracteres "%3A."</span><span class="sxs-lookup"><span data-stu-id="6ac49-115">A semicolon in any portion of the string is replaced with the characters "%3A."</span></span>  
> -   <span data-ttu-id="6ac49-116">Os navegadores devem executar a codificação de URL apropriada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6ac49-116">Browsers should automatically perform the proper URL encoding.</span></span> <span data-ttu-id="6ac49-117">Não é preciso codificar os caracteres manualmente.</span><span class="sxs-lookup"><span data-stu-id="6ac49-117">You do not have to encode any of the characters manually.</span></span>  
  
 <span data-ttu-id="6ac49-118">Para definir um parâmetro de relatório em uma URL, use a sintaxe a seguir:</span><span class="sxs-lookup"><span data-stu-id="6ac49-118">To set a report parameter within a URL, use the following syntax:</span></span>  
  
```  
  
parameter=value  
```  
  
 <span data-ttu-id="6ac49-119">Por exemplo, para especificar dois parâmetros, "ReportMonth" e "ReportYear", definidos em um relatório, use a URL a seguir para um servidor de relatório de modo nativo:</span><span class="sxs-lookup"><span data-stu-id="6ac49-119">For example, to specify two parameters, "ReportMonth" and "ReportYear", defined in a report, use the following URL for a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="6ac49-120">Por exemplo, para especificar os mesmos dois parâmetros definidos em um relatório, use a URL de um servidor de relatório no modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6ac49-120">For example, to specify the same two parameters defined in a report, use the following URL for a SharePoint integrated mode report server.</span></span> <span data-ttu-id="6ac49-121">Observe o `/_vti_bin`:</span><span class="sxs-lookup"><span data-stu-id="6ac49-121">Note the `/_vti_bin`:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="6ac49-122">Para transmitir um valor nulo para um parâmetro, use a sintaxe a seguir:</span><span class="sxs-lookup"><span data-stu-id="6ac49-122">To pass a null value for a parameter, use the following syntax:</span></span>  
  
```  
  
parameter  
:isnull=true  
  
```  
  
 <span data-ttu-id="6ac49-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6ac49-123">For example,</span></span>  
  
```  
SalesOrderNumber:isnull=true  
```  
  
 <span data-ttu-id="6ac49-124">Para passar um valor `Boolean`, use 0 para false ou 1 para true.</span><span class="sxs-lookup"><span data-stu-id="6ac49-124">To pass a `Boolean` value, use 0 for false and 1 for true.</span></span> <span data-ttu-id="6ac49-125">Para passar um valor `Float`, inclua o separador decimal da localidade do servidor</span><span class="sxs-lookup"><span data-stu-id="6ac49-125">To pass a `Float` value, include the decimal separator of the server locale</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ac49-126">Se o seu relatório contiver um parâmetro que tenha um valor padrão e o valor da propriedade `Prompt` for `false` (isto é, a propriedade Avisar Usuário não for selecionada no Gerenciador de Relatórios), você não poderá transmitir um valor para esse parâmetro em uma URL.</span><span class="sxs-lookup"><span data-stu-id="6ac49-126">If your report contains a report parameter that has a default value and the value of the `Prompt` property is `false` (that is, the Prompt User property is not selected in Report Manager), then you cannot pass a value for that report parameter within a URL.</span></span> <span data-ttu-id="6ac49-127">Isso fornece aos administradores a opção de impedir que usuários finais adicionem ou modifiquem os valores de determinados parâmetros de relatório.</span><span class="sxs-lookup"><span data-stu-id="6ac49-127">This provides administrators an option for preventing end users from adding or modifying the values of certain report parameters.</span></span>  
  
##  <a name="additional-examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="6ac49-128">Exemplos adicionais</span><span class="sxs-lookup"><span data-stu-id="6ac49-128">Additional Examples</span></span>  
 <span data-ttu-id="6ac49-129">O exemplo de URL a seguir inclui espaços e vários parâmetros</span><span class="sxs-lookup"><span data-stu-id="6ac49-129">The following URL example includes spaces and multiple parameters</span></span>  
  
-   <span data-ttu-id="6ac49-130">O nome de pasta "Equipe de Instrução do Usuário do SQL Server" inclui espaços e, portanto, o sinal "+" substitui cada espaço.</span><span class="sxs-lookup"><span data-stu-id="6ac49-130">Folder name of "SQL Server User Education Team" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="6ac49-131">O nome de relatório "relatório do projeto de equipe" inclui espaços e, portanto, o sinal "+" substitui cada espaço.</span><span class="sxs-lookup"><span data-stu-id="6ac49-131">Report name of "team project report" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="6ac49-132">Passa dois parâmetros "teamgrouping2" com um valor "xgroup" e "teamgrouping1" com um valor "ygroup".</span><span class="sxs-lookup"><span data-stu-id="6ac49-132">Passes two parameters of "teamgrouping2" with a value of "xgroup" and "teamgrouping1" with a value of "ygroup".</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup  
```  
  
 <span data-ttu-id="6ac49-133">O exemplo de URL a seguir inclui um parâmetros com vários valores, "OrderID.</span><span class="sxs-lookup"><span data-stu-id="6ac49-133">The following URL example includes a multi-value parameter "OrderID.</span></span> <span data-ttu-id="6ac49-134">O formato de um parâmetro com vários valores é repetir o nome do parâmetro para cada valor.</span><span class="sxs-lookup"><span data-stu-id="6ac49-134">The format for a Multi-Value parameter is to repeat the parameter name for each value.</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup&OrderID=747&OrderID=787&OrderID=12  
```  
  
 <span data-ttu-id="6ac49-135">O exemplo de URL a seguir passa um único parâmetro de *SellStartDate* com um valor de "7/1/2005" para um servidor de relatório de modo nativo.</span><span class="sxs-lookup"><span data-stu-id="6ac49-135">The following URL example passes a single parameter of *SellStartDate* with a value of "7/1/2005", for a native mode report server.</span></span>  
  
```  
http://myserver/ReportServer/Pages/ReportViewer.aspx?%2fProduct_and_Sales_Report_AdventureWorks&SellStartDate=7/1/2005  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ac49-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ac49-136">See Also</span></span>  
 <span data-ttu-id="6ac49-137">[Acesso à URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6ac49-137">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="6ac49-138">Referência de parâmetro de acesso de URL</span><span class="sxs-lookup"><span data-stu-id="6ac49-138">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
