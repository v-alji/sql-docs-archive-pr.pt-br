---
title: Editor de transformação pesquisa (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.general.f1
ms.assetid: 4bd15e48-0feb-4f95-be91-5df58105dbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa178118f7e090b6a3c15c7ab9347f322461f07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679427"
---
# <a name="lookup-transformation-editor-general-page"></a><span data-ttu-id="75b53-102">Editor da Transformação Pesquisa (página Geral)</span><span class="sxs-lookup"><span data-stu-id="75b53-102">Lookup Transformation Editor (General Page)</span></span>
  <span data-ttu-id="75b53-103">Use a página **Geral** da caixa de diálogo Editor da Transformação Pesquisa para selecionar o modo de cache, selecionar o tipo de conexão e especificar como lidar com as linhas com entradas sem-correspondência.</span><span class="sxs-lookup"><span data-stu-id="75b53-103">Use the **General** page of the Lookup Transformation Editor dialog box to select the cache mode, select the connection type, and specify how to handle rows with no matching entries.</span></span>  
  
 <span data-ttu-id="75b53-104">Para saber mais sobre a transformação Pesquisa, consulte [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="75b53-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="75b53-105">Opções</span><span class="sxs-lookup"><span data-stu-id="75b53-105">Options</span></span>  
 <span data-ttu-id="75b53-106">**Cache cheio**</span><span class="sxs-lookup"><span data-stu-id="75b53-106">**Full cache**</span></span>  
 <span data-ttu-id="75b53-107">Gere e carregue o conjunto de dados de referência no cache antes de executar a transformação Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="75b53-107">Generate and load the reference dataset into cache before the Lookup transformation is executed.</span></span>  
  
 <span data-ttu-id="75b53-108">**Cache parcial**</span><span class="sxs-lookup"><span data-stu-id="75b53-108">**Partial cache**</span></span>  
 <span data-ttu-id="75b53-109">Gere o conjunto de dados de referência durante a execução da transformação Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="75b53-109">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="75b53-110">Carregue as linhas com entradas com correspondência no conjunto de dados de referência e as linhas com entradas sem-correspondência no conjunto de dados no cache.</span><span class="sxs-lookup"><span data-stu-id="75b53-110">Load the rows with matching entries in the reference dataset and the rows with no matching entries in the dataset into cache.</span></span>  
  
 <span data-ttu-id="75b53-111">**Nenhum cache**</span><span class="sxs-lookup"><span data-stu-id="75b53-111">**No cache**</span></span>  
 <span data-ttu-id="75b53-112">Gere o conjunto de dados de referência durante a execução da transformação Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="75b53-112">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="75b53-113">Nenhum dado é carregado no cache.</span><span class="sxs-lookup"><span data-stu-id="75b53-113">No data is loaded into cache.</span></span>  
  
 <span data-ttu-id="75b53-114">**Gerenciador de conexões de cache**</span><span class="sxs-lookup"><span data-stu-id="75b53-114">**Cache connection manager**</span></span>  
 <span data-ttu-id="75b53-115">Configure a transformação Pesquisa para usar um Gerenciador de conexão de cache.</span><span class="sxs-lookup"><span data-stu-id="75b53-115">Configure the Lookup transformation to use a Cache connection manager.</span></span> <span data-ttu-id="75b53-116">Esta opção estará disponível somente se a opção Cache cheio for selecionada.</span><span class="sxs-lookup"><span data-stu-id="75b53-116">This option is available only if the Full cache option is selected.</span></span>  
  
 <span data-ttu-id="75b53-117">**Gerenciador de conexões OLE DB**</span><span class="sxs-lookup"><span data-stu-id="75b53-117">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="75b53-118">Configure a transformação Pesquisa para usar um Gerenciador de conexões OLE DB.</span><span class="sxs-lookup"><span data-stu-id="75b53-118">Configure the Lookup transformation to use an OLE DB connection manager.</span></span>  
  
 <span data-ttu-id="75b53-119">**Especificar como lidar com linhas com entradas sem-correspondência**</span><span class="sxs-lookup"><span data-stu-id="75b53-119">**Specify how to handle rows with no matching entries**</span></span>  
 <span data-ttu-id="75b53-120">Selecione uma opção para lidar com as linhas que não correspondem a pelo menos uma entrada no conjunto de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="75b53-120">Select an option for handling rows that do not match at least one entry in the reference dataset.</span></span>  
  
 <span data-ttu-id="75b53-121">Ao selecionar **Redirecionar linhas para uma saída sem-correspondência**, as linhas serão redirecionadas a uma saída sem-correspondência e serão tratadas como erros.</span><span class="sxs-lookup"><span data-stu-id="75b53-121">When you select **Redirect rows to no match output**, the rows are redirected to a no match output and are not handled as errors.</span></span> <span data-ttu-id="75b53-122">A opção **Erro** na página **Saída de Erro** da caixa de diálogo **Editor da Transformação Pesquisa** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="75b53-122">The **Error** option on the **Error Output** page of the **Lookup Transformation Editor** dialog box is not available.</span></span>  
  
 <span data-ttu-id="75b53-123">Ao selecionar uma opção na caixa de listas **Especificar como lidar com linhas com entradas sem-correspondência** , as linhas serão tratadas como erros.</span><span class="sxs-lookup"><span data-stu-id="75b53-123">When you select any other option in the **Specify how to handle rows with no matching entries** list box, the rows are handled as errors.</span></span> <span data-ttu-id="75b53-124">A opção **Erro** na página **Saída de Erro** estará disponível.</span><span class="sxs-lookup"><span data-stu-id="75b53-124">The **Error** option on the **Error Output** page is available.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="75b53-125">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="75b53-125">External Resources</span></span>  
 <span data-ttu-id="75b53-126">Entrada de blog, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) (em inglês) em blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="75b53-126">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b53-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="75b53-127">See Also</span></span>  
 <span data-ttu-id="75b53-128">[Gerenciador de conexões de cache](connection-manager/cache-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="75b53-128">[Cache Connection Manager](connection-manager/cache-connection-manager.md) </span></span>  
 <span data-ttu-id="75b53-129">[Editor de transformação pesquisa &#40;página conexão&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="75b53-129">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="75b53-130">[Editor de transformação pesquisa &#40;página colunas&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="75b53-130">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="75b53-131">[Editor de transformação pesquisa &#40;página avançado&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="75b53-131">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="75b53-132">Editor de Transformação Pesquisa &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="75b53-132">Lookup Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/lookup-transformation-editor-error-output-page.md)  
  
  
