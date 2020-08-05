---
title: Editor de transformação pesquisa (página avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.advanced.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: f3395c65-0320-47f9-8d83-daaa082d8713
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 23f235ef0506da7ac808d832db6ac36d53cfa604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574109"
---
# <a name="lookup-transformation-editor-advanced-page"></a><span data-ttu-id="71709-102">Editor da Transformação Pesquisa (página Avançado)</span><span class="sxs-lookup"><span data-stu-id="71709-102">Lookup Transformation Editor (Advanced Page)</span></span>
  <span data-ttu-id="71709-103">Use a página **Avançado** da caixa de diálogo **Editor da Transformação Pesquisa** para configurar o cache parcial e para modificar a instrução SQL da transformação Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="71709-103">Use the **Advanced** page of the **Lookup Transformation Editor** dialog box to configure partial caching and to modify the SQL statement for the Lookup transformation.</span></span>  
  
 <span data-ttu-id="71709-104">Para saber mais sobre a transformação Pesquisa, consulte [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="71709-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="71709-105">Opções</span><span class="sxs-lookup"><span data-stu-id="71709-105">Options</span></span>  
 <span data-ttu-id="71709-106">**Tamanho de cache (32 bits)**</span><span class="sxs-lookup"><span data-stu-id="71709-106">**Cache size (32-bit)**</span></span>  
 <span data-ttu-id="71709-107">Ajuste o tamanho de cache (em megabytes) para computadores de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="71709-107">Adjust the  cache size (in megabytes) for 32-bit computers.</span></span> <span data-ttu-id="71709-108">O valor padrão é 5 megabytes.</span><span class="sxs-lookup"><span data-stu-id="71709-108">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="71709-109">**Tamanho de cache (64 bits)**</span><span class="sxs-lookup"><span data-stu-id="71709-109">**Cache size (64-bit)**</span></span>  
 <span data-ttu-id="71709-110">Ajuste o tamanho de cache (em megabytes) para computadores de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="71709-110">Adjust the cache size (in megabytes) for 64-bit computers.</span></span> <span data-ttu-id="71709-111">O valor padrão é 5 megabytes.</span><span class="sxs-lookup"><span data-stu-id="71709-111">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="71709-112">**Ativar cache para linhas com entradas sem-correspondência**</span><span class="sxs-lookup"><span data-stu-id="71709-112">**Enable cache for rows with no matching entries**</span></span>  
 <span data-ttu-id="71709-113">Linhas de cache com entradas sem-correspondência no conjunto de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="71709-113">Cache rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="71709-114">**Alocação de cache**</span><span class="sxs-lookup"><span data-stu-id="71709-114">**Allocation from cache**</span></span>  
 <span data-ttu-id="71709-115">Especifique o percentual de cache a ser alocado para as linhas com entradas sem-correspondência no conjunto de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="71709-115">Specify the percentage of the cache to allocate for rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="71709-116">**Modificar instrução SQL**</span><span class="sxs-lookup"><span data-stu-id="71709-116">**Modify the SQL statement**</span></span>  
 <span data-ttu-id="71709-117">Modifique a instrução SQL usada para gerar o conjunto de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="71709-117">Modify the SQL statement that is used to generate the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71709-118">A instrução SQL opcional especificada nesta página substituirá o nome da tabela especificado na página **Conexão** do **Editor da Transformação Pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="71709-118">The optional SQL statement that you specify on this page overrides and replaces the table name that you specified on the **Connection** page of the **Lookup Transformation Editor**.</span></span> <span data-ttu-id="71709-119">Para obter mais informações, consulte [Editor de Transformação Pesquisa &#40;Página Conexão&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span><span class="sxs-lookup"><span data-stu-id="71709-119">For more information, see [Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span></span>  
  
 <span data-ttu-id="71709-120">**Definir Parâmetros**</span><span class="sxs-lookup"><span data-stu-id="71709-120">**Set Parameters**</span></span>  
 <span data-ttu-id="71709-121">Mapeie colunas de entrada para parâmetros usando a caixa de diálogo **Definir Parâmetros da Consulta** .</span><span class="sxs-lookup"><span data-stu-id="71709-121">Map input columns to parameters by using the **Set Query Parameters** dialog box.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="71709-122">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="71709-122">External Resources</span></span>  
 <span data-ttu-id="71709-123">Entrada de blog, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) (em inglês) em blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="71709-123">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71709-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71709-124">See Also</span></span>  
 <span data-ttu-id="71709-125">[Editor de transformação pesquisa &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="71709-125">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="71709-126">[Editor de transformação pesquisa &#40;página conexão&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="71709-126">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="71709-127">[Editor de transformação pesquisa &#40;página colunas&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="71709-127">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="71709-128">[Editor de transformação pesquisa &#40;página saída de erro&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="71709-128">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="71709-129">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="71709-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="71709-130">transformação Pesquisa Difusa</span><span class="sxs-lookup"><span data-stu-id="71709-130">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
