---
title: Transformação Cache | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetrans.f1
helpviewer_keywords:
- Cache transform
ms.assetid: a5683fc8-9c32-4634-819e-e9815627e4f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34be3252a3caf344c95e13ae45cc485a8c4ffdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575250"
---
# <a name="cache-transform"></a><span data-ttu-id="f1667-102">transformação Cache</span><span class="sxs-lookup"><span data-stu-id="f1667-102">Cache Transform</span></span>
  <span data-ttu-id="f1667-103">A Transformação Cache gera um conjunto de dados de referência para uma Transformação Pesquisa, gravando dados de uma fonte de dados conectada no fluxo de dados para um gerenciador de conexões de Cache.</span><span class="sxs-lookup"><span data-stu-id="f1667-103">The Cache Transform transformation generates a reference dataset for the Lookup Transformation by writing data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="f1667-104">A transformação Pesquisa executa pesquisas, unindo dados em colunas de entrada de uma fonte de dados conectados com colunas no banco de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="f1667-104">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference database.</span></span>  
  
 <span data-ttu-id="f1667-105">Você pode usar o gerenciador de conexões de Cache quando deseja configurar a Transformação Pesquisa para executar no modo de cache cheio.</span><span class="sxs-lookup"><span data-stu-id="f1667-105">You can use the Cache connection manager when you want to configure the Lookup Transformation to run in the full cache mode.</span></span> <span data-ttu-id="f1667-106">Nesse modo, o conjunto de dados de referência é carregado no cache antes da execução da Transformação Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f1667-106">In this mode, the reference dataset is loaded into cache before the Lookup Transformation runs.</span></span>  
  
 <span data-ttu-id="f1667-107">Para obter instruções sobre como configurar a Transformação Pesquisa em modo de cache cheio com o gerenciador de conexões de Cache e a Transformação Cache, consulte [Implementar uma Transformação Pesquisa em modo cache cheio usando o Gerenciador de Conexões do Cache](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f1667-107">For instructions on how to configure the Lookup transformation in full cache mode with the Cache connection manager and Cache Transform transformation, see [Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="f1667-108">Para obter mais informações sobre o cache do conjunto de dados de referência, consulte [Lookup Transformation](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="f1667-108">For more information on caching the reference dataset, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1667-109">A Transformação Cache grava apenas linhas exclusivas no gerenciador de conexões do Cache.</span><span class="sxs-lookup"><span data-stu-id="f1667-109">The Cache Transform writes only unique rows to the Cache connection manager.</span></span>  
  
 <span data-ttu-id="f1667-110">Em um único pacote, somente uma transformação Cache pode gravar dados no mesmo gerenciador de conexões de cache.</span><span class="sxs-lookup"><span data-stu-id="f1667-110">In a single package, only one Cache Transform can write data to the same Cache connection manager.</span></span> <span data-ttu-id="f1667-111">Se o pacote contiver várias transformações Cache, a primeira transformação, que é chamada quando o pacote é executado, gravará os dados no gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="f1667-111">If the package contains multiple Cache Transforms, the first Cache Transform that is called when the package runs, writes the data to the connection manager.</span></span> <span data-ttu-id="f1667-112">As operações de gravação das transformações Cache subsequentes falham.</span><span class="sxs-lookup"><span data-stu-id="f1667-112">The write operations of subsequent Cache Transforms fail.</span></span>  
  
 <span data-ttu-id="f1667-113">Para obter mais informações, consulte [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) e [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="f1667-113">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
## <a name="configuration-of-the-cache-transform"></a><span data-ttu-id="f1667-114">Configuração da transformação Cache</span><span class="sxs-lookup"><span data-stu-id="f1667-114">Configuration of the Cache Transform</span></span>  
 <span data-ttu-id="f1667-115">Você pode configurar o gerenciador de conexões de cache para salvar os dados em um arquivo de cache (.caw).</span><span class="sxs-lookup"><span data-stu-id="f1667-115">You can configure the Cache connection manager to save the data to a cache file (.caw).</span></span>  
  
 <span data-ttu-id="f1667-116">Você pode configurar a transformação Cache das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="f1667-116">You can configure the Cache Transform in the following ways:</span></span>  
  
-   <span data-ttu-id="f1667-117">Especificando o gerenciador de conexões de cache.</span><span class="sxs-lookup"><span data-stu-id="f1667-117">Specify the Cache connection manager.</span></span>  
  
-   <span data-ttu-id="f1667-118">Mapeando as colunas de entrada na transformação Cache para as colunas de destino do gerenciador de conexões de cache.</span><span class="sxs-lookup"><span data-stu-id="f1667-118">Map the input columns in the Cache Transform to destination columns in the Cache connection manager.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f1667-119">Cada coluna de entrada deve ser mapeada para uma coluna de destino e os tipos de dados de coluna devem corresponder.</span><span class="sxs-lookup"><span data-stu-id="f1667-119">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="f1667-120">Caso contrário, o Designer [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] exibirá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="f1667-120">Otherwise, [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
     <span data-ttu-id="f1667-121">Você pode usar o **Editor do Gerenciador de Conexões de Cache** para modificar tipos de dados de coluna, nomes e outras propriedades de coluna.</span><span class="sxs-lookup"><span data-stu-id="f1667-121">You can use the **Cache Connection Manager Editor** to modify column data types, names, and other column properties.</span></span>  
  
 <span data-ttu-id="f1667-122">Você pode definir propriedades por meio do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="f1667-122">You can set properties through [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer.</span></span> <span data-ttu-id="f1667-123">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** , consulte [Transformation Custom Properties](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f1667-123">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="f1667-124">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="f1667-124">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1667-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1667-125">See Also</span></span>  
 <span data-ttu-id="f1667-126">[Transformações do Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="f1667-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 [<span data-ttu-id="f1667-127">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="f1667-127">Data Flow</span></span>](../data-flow.md)  
  
  
