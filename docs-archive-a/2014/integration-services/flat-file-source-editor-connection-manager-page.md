---
title: Editor de fonte de arquivo simples (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.connection.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: 2efd6baa-ed75-4f3f-b667-514024cebdb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03c1693c001dad2c8e90211b065eda208c42a07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570147"
---
# <a name="flat-file-source-editor-connection-manager-page"></a><span data-ttu-id="6dd84-102">Editor de Fonte de Arquivo Simples (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="6dd84-102">Flat File Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="6dd84-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Fonte de Arquivo Simples** para selecionar o gerenciador de conexões que a fonte do arquivo simples usará.</span><span class="sxs-lookup"><span data-stu-id="6dd84-103">Use the **Connection Manager** page of the **Flat File Source Editor** dialog box to select the connection manager that the Flat File source will use.</span></span> <span data-ttu-id="6dd84-104">A fonte de Arquivo Simples lê dados de um arquivo de texto, que pode estar em formato de largura delimitada, fixa ou mista.</span><span class="sxs-lookup"><span data-stu-id="6dd84-104">The Flat File source reads data from a text file, which can be in a delimited, fixed width, or mixed format.</span></span>  
  
 <span data-ttu-id="6dd84-105">Uma fonte de Arquivo Simples pode usar um dos seguintes tipos de gerenciadores de conexões:</span><span class="sxs-lookup"><span data-stu-id="6dd84-105">A Flat File source can use one of the following types of connection managers:</span></span>  
  
-   <span data-ttu-id="6dd84-106">Um gerenciador de conexões de Arquivo Simples se a fonte for um arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="6dd84-106">A Flat File connection manager if the source is a single flat file.</span></span> <span data-ttu-id="6dd84-107">Para obter mais informações, consulte [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6dd84-107">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
-   <span data-ttu-id="6dd84-108">Um gerenciador de conexões de Vários Arquivos Simples se a fonte corresponder a vários arquivos simples e a tarefa Fluxo de Dados estiver dentro de um contêiner de loop, como o contêiner de Loop For.</span><span class="sxs-lookup"><span data-stu-id="6dd84-108">A Multiple Flat Files connection manager if the source is multiple flat files and the Data Flow task is inside a loop container, such as the For Loop container.</span></span> <span data-ttu-id="6dd84-109">Em cada loop do contêiner, a fonte de Arquivo Simples carrega dados do nome de arquivo seguinte fornecido pelo gerenciador de conexões de Vários Arquivos Simples.</span><span class="sxs-lookup"><span data-stu-id="6dd84-109">On each loop of the container, the Flat File source loads data from the next file name that the Multiple Flat Files connection manager provides.</span></span> <span data-ttu-id="6dd84-110">Para obter mais informações, consulte [Gerenciador de conexões de vários arquivos simples](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6dd84-110">For more information, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
 <span data-ttu-id="6dd84-111">Para saber mais sobre a fonte de Arquivo Simples, consulte [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="6dd84-111">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6dd84-112">Opções</span><span class="sxs-lookup"><span data-stu-id="6dd84-112">Options</span></span>  
 <span data-ttu-id="6dd84-113">**Gerenciador de conexões de arquivos simples**</span><span class="sxs-lookup"><span data-stu-id="6dd84-113">**Flat file connection manager**</span></span>  
 <span data-ttu-id="6dd84-114">Selecione um gerenciador de conexões na lista ou crie um novo gerenciador de conexões clicando em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="6dd84-114">Select an existing connection manager from the list, or create a new connection manager by clicking **New**.</span></span>  
  
 <span data-ttu-id="6dd84-115">**Novo**</span><span class="sxs-lookup"><span data-stu-id="6dd84-115">**New**</span></span>  
 <span data-ttu-id="6dd84-116">Crie um novo gerenciador de conexões, usando a caixa de diálogo **Editor de Gerenciador de Conexões de Arquivo Simples** .</span><span class="sxs-lookup"><span data-stu-id="6dd84-116">Create a new connection manager by using the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="6dd84-117">**Reter valores nulos da origem como valores nulos no fluxo de dados**</span><span class="sxs-lookup"><span data-stu-id="6dd84-117">**Retain null values from the source as null values in the data flow**</span></span>  
 <span data-ttu-id="6dd84-118">Especifique se os valores nulos devem ser mantidos na extração dos dados.</span><span class="sxs-lookup"><span data-stu-id="6dd84-118">Specify whether to keep null values when data is extracted.</span></span> <span data-ttu-id="6dd84-119">O valor padrão dessa propriedade é **false**.</span><span class="sxs-lookup"><span data-stu-id="6dd84-119">The default value of this property is **false**.</span></span> <span data-ttu-id="6dd84-120">Quando o valor é f`alse`, a fonte de Arquivo Simples substitui valores nulos dos dados de fonte por valores padrão apropriados para cada coluna, como cadeias de caracteres vazias, no caso de colunas de cadeia de caracteres, e zero, no caso de colunas numéricas.</span><span class="sxs-lookup"><span data-stu-id="6dd84-120">When this value is f`alse`, the Flat File source replaces null values from the source data with appropriate default values for each column, such as empty strings for string columns and zero for numeric columns.</span></span>  
  
 <span data-ttu-id="6dd84-121">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="6dd84-121">**Preview**</span></span>  
 <span data-ttu-id="6dd84-122">Visualize os resultados usando a caixa de diálogo **Exibição de Dados** .</span><span class="sxs-lookup"><span data-stu-id="6dd84-122">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="6dd84-123">A visualização pode exibir até 200 linhas.</span><span class="sxs-lookup"><span data-stu-id="6dd84-123">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd84-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6dd84-124">See Also</span></span>  
 <span data-ttu-id="6dd84-125">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6dd84-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6dd84-126">[Editor de fonte de arquivo simples &#40;página colunas&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="6dd84-126">[Flat File Source Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="6dd84-127">[Editor de fonte de arquivo simples &#40;página saída de erro&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="6dd84-127">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="6dd84-128">Gerenciador de Conexões de Arquivos Simples</span><span class="sxs-lookup"><span data-stu-id="6dd84-128">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
