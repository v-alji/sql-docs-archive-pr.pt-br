---
title: Editor de transformação Agrupamento Difuso (guia Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.connection.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 47b1446d-5331-473c-9cb5-a98b1f55bf5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2a8b0af9f36fdd386f7da375184fd4e4ec5c4be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582009"
---
# <a name="fuzzy-grouping-transformation-editor-connection-manager-tab"></a><span data-ttu-id="a553b-102">Editor de Transformação Agrupamento Difuso (guia Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="a553b-102">Fuzzy Grouping Transformation Editor (Connection Manager Tab)</span></span>
  <span data-ttu-id="a553b-103">Use a guia **Gerenciador de Conexões** da caixa de diálogo **Editor de Transformação Agrupamento Difuso** para selecionar uma conexão existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="a553b-103">Use the **Connection Manager** tab of the **Fuzzy Grouping Transformation Editor** dialog box to select an existing connection or create a new one.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a553b-104">O servidor especificado pela conexão deve estar executando o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a553b-104">The server specified by the connection must be running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a553b-105">A transformação Agrupamento Difuso cria objetos de dados temporários no tempdb que podem ser tão grandes quanto a entrada completa para a transformação.</span><span class="sxs-lookup"><span data-stu-id="a553b-105">The Fuzzy Grouping transformation creates temporary data objects in tempdb that may be as large as the full input to the transformation.</span></span> <span data-ttu-id="a553b-106">A execução da transformação emite, em seu decorrer, consultas de servidor contra esses objetos temporários.</span><span class="sxs-lookup"><span data-stu-id="a553b-106">While the transformation executes, it issues server queries against these temporary objects.</span></span> <span data-ttu-id="a553b-107">Isso pode afetar o desempenho global de servidor.</span><span class="sxs-lookup"><span data-stu-id="a553b-107">This can affect overall server performance.</span></span>  
  
 <span data-ttu-id="a553b-108">Para saber mais sobre a transformação Agrupamento Difuso, consulte [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a553b-108">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a553b-109">Opções</span><span class="sxs-lookup"><span data-stu-id="a553b-109">Options</span></span>  
 <span data-ttu-id="a553b-110">**Gerenciador de conexões OLE DB**</span><span class="sxs-lookup"><span data-stu-id="a553b-110">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="a553b-111">Selecione um gerenciador de conexões OLE DB existente usando a caixa de listagem ou crie uma nova conexão usando o botão **Novo** .</span><span class="sxs-lookup"><span data-stu-id="a553b-111">Select an existing OLE DB connection manager by using the list box, or create a new connection by using the **New** button.</span></span>  
  
 <span data-ttu-id="a553b-112">**Novo**</span><span class="sxs-lookup"><span data-stu-id="a553b-112">**New**</span></span>  
 <span data-ttu-id="a553b-113">Crie uma nova conexão usando a caixa de diálogo **Configurar Gerenciador de Conexões OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="a553b-113">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a553b-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a553b-114">See Also</span></span>  
 <span data-ttu-id="a553b-115">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a553b-115">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="a553b-116">Identificar linhas de dados semelhantes por meio da transformação Agrupamento Difuso</span><span class="sxs-lookup"><span data-stu-id="a553b-116">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
