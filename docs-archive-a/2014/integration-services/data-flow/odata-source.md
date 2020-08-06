---
title: OData Source | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ODATASOURCE.F1
ms.assetid: cc9003c9-638e-432b-867e-e949d50cec90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 98b14ef034597f6098f70386ca41c1b90be86500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685215"
---
# <a name="odata-source"></a><span data-ttu-id="9f804-102">Origem do OData</span><span class="sxs-lookup"><span data-stu-id="9f804-102">OData Source</span></span>
  <span data-ttu-id="9f804-103">Você usa o componente de origem OData em um pacote do SSIS para consumir os dados dos serviços do OData (protocolo Open Data).</span><span class="sxs-lookup"><span data-stu-id="9f804-103">You use the OData Source component in an SSIS package to consume data from Open Data Protocol (OData) services.</span></span> <span data-ttu-id="9f804-104">O componente oferece suporte aos protocolos v2 e v3 do OData, bem como os formatos de dados ATOM e JSON.</span><span class="sxs-lookup"><span data-stu-id="9f804-104">The component supports the OData v2 and v3 protocols, as well as the ATOM and JSON data formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f804-105">A origem OData pode ser usada para ler listas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9f804-105">The OData Source can be used to read from SharePoint lists.</span></span> <span data-ttu-id="9f804-106">Para ver todas as listas no servidor do SharePoint, use a seguinte URL: http:// \<server> /_vti_bin/listdata.svc.</span><span class="sxs-lookup"><span data-stu-id="9f804-106">To see all lists on your SharePoint server, use the following URL: http://\<server>/_vti_bin/ListData.svc.</span></span> <span data-ttu-id="9f804-107">Para obter mais informações sobre as convenções de URL do SharePoint, consulte [Interface REST do SharePoint Foundation](https://msdn.microsoft.com/library/ff521587.aspx).</span><span class="sxs-lookup"><span data-stu-id="9f804-107">For more information about SharePoint URL conventions, see [SharePoint Foundation REST Interface](https://msdn.microsoft.com/library/ff521587.aspx).</span></span>  
  
## <a name="odata-format"></a><span data-ttu-id="9f804-108">Formato OData</span><span class="sxs-lookup"><span data-stu-id="9f804-108">OData Format</span></span>  
 <span data-ttu-id="9f804-109">A maioria dos serviços do OData retornam os resultados em vários formatos.</span><span class="sxs-lookup"><span data-stu-id="9f804-109">Most OData services return results in multiple formats.</span></span> <span data-ttu-id="9f804-110">Você pode especificar o formato do conjunto de resultados usando a opção de consulta de $format.</span><span class="sxs-lookup"><span data-stu-id="9f804-110">You can specify the format of the result set by using the $format query option.</span></span> <span data-ttu-id="9f804-111">Os formatos como JSON e JSON Light são mais eficientes do que ATOM/XML, e podem oferecer melhor desempenho durante a transferência de grandes quantidades de dados.</span><span class="sxs-lookup"><span data-stu-id="9f804-111">Formats such as JSON and JSON Light are more efficient than ATOM/XML, and may give you better performance when transferring large amounts of data.</span></span> <span data-ttu-id="9f804-112">A tabela a seguir fornece os resultados dos testes de exemplo.</span><span class="sxs-lookup"><span data-stu-id="9f804-112">The following table provides results from sample tests.</span></span> <span data-ttu-id="9f804-113">Como você pode ver, houve um ganho de desempenho de 30% a 53% ao alternar de ATOM para JSON, e um ganho de desempenho de 67% ao alternar de ATOM para o novo formato JSON Light (disponível nos serviços de dados do WCF 5.1).</span><span class="sxs-lookup"><span data-stu-id="9f804-113">As you can see, there was a 30-53% performance gain when switching from ATOM to JSON and 67% performance gain when switching from ATOM to the new JSON light format (available in WCF Data Services 5.1).</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="9f804-114">Linhas</span><span class="sxs-lookup"><span data-stu-id="9f804-114">Rows</span></span>|<span data-ttu-id="9f804-115">ATOM</span><span class="sxs-lookup"><span data-stu-id="9f804-115">ATOM</span></span>|<span data-ttu-id="9f804-116">JSON</span><span class="sxs-lookup"><span data-stu-id="9f804-116">JSON</span></span>|<span data-ttu-id="9f804-117">JSON (Light)</span><span class="sxs-lookup"><span data-stu-id="9f804-117">JSON (Light)</span></span>|  
|<span data-ttu-id="9f804-118">10000</span><span class="sxs-lookup"><span data-stu-id="9f804-118">10000</span></span>|<span data-ttu-id="9f804-119">113 segundos</span><span class="sxs-lookup"><span data-stu-id="9f804-119">113 seconds</span></span>|<span data-ttu-id="9f804-120">74 segundos</span><span class="sxs-lookup"><span data-stu-id="9f804-120">74 seconds</span></span>|<span data-ttu-id="9f804-121">68 segundos</span><span class="sxs-lookup"><span data-stu-id="9f804-121">68 seconds</span></span>|  
|<span data-ttu-id="9f804-122">1.000.000</span><span class="sxs-lookup"><span data-stu-id="9f804-122">1000000</span></span>|<span data-ttu-id="9f804-123">1.110 segundos</span><span class="sxs-lookup"><span data-stu-id="9f804-123">1110 seconds</span></span>|<span data-ttu-id="9f804-124">853 segundos</span><span class="sxs-lookup"><span data-stu-id="9f804-124">853 seconds</span></span>|<span data-ttu-id="9f804-125">665 segundos</span><span class="sxs-lookup"><span data-stu-id="9f804-125">665 seconds</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="9f804-126">A origem OData SSIS usa o ODataLib 5.5.0 para avaliar os feeds do OData e pode ler todos os formatos suportados por essa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9f804-126">The SSIS OData Source uses ODataLib 5.5.0 to parse OData feeds and it can read all formats supported by this library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f804-127">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9f804-127">In This Section</span></span>  
  
-   [<span data-ttu-id="9f804-128">Instalar e desinstalar o componente de origem do OData</span><span class="sxs-lookup"><span data-stu-id="9f804-128">Install and Uninstall OData Source Component</span></span>](../install-and-uninstall-odata-source-component.md)  
  
-   [<span data-ttu-id="9f804-129">Tutorial: usando a fonte OData &#91;SSIS&#93;</span><span class="sxs-lookup"><span data-stu-id="9f804-129">Tutorial: Using the OData Source &#91;SSIS&#93;</span></span>](tutorial-using-the-odata-source.md)  
  
-   [<span data-ttu-id="9f804-130">Modifique a consulta de origem do OData em runtime</span><span class="sxs-lookup"><span data-stu-id="9f804-130">Modify OData Source Query at Runtime</span></span>](modify-odata-source-query-at-runtime.md)  
  
-   [<span data-ttu-id="9f804-131">Editor de Origem do OData &#40;Página Conexão&#41;</span><span class="sxs-lookup"><span data-stu-id="9f804-131">OData Source Editor &#40;Connection Page&#41;</span></span>](../odata-source-editor-connection-page.md)  
  
-   [<span data-ttu-id="9f804-132">Editor de Fonte OData &#40;Página Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="9f804-132">OData Source Editor &#40;Columns Page&#41;</span></span>](../odata-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="9f804-133">Editor de Fonte OData &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="9f804-133">OData Source Editor &#40;Error Output Page&#41;</span></span>](../odata-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="9f804-134">Propriedades da origem do OData</span><span class="sxs-lookup"><span data-stu-id="9f804-134">OData Source Properties</span></span>](odata-source-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="9f804-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9f804-135">See Also</span></span>  
 [<span data-ttu-id="9f804-136">Gerenciador de conexões do OData</span><span class="sxs-lookup"><span data-stu-id="9f804-136">OData Connection Manager</span></span>](../connection-manager/odata-connection-manager.md)  
  
  
