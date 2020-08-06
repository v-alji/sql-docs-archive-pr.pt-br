---
title: Editor de origem de OLE DB (página saída de erro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.errorhandling.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: 7737c6ae-c16b-4856-aa6e-5882640093b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ded87747f041a4d8451048d4ef4671b029125873
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582536"
---
# <a name="ole-db-source-editor-error-output-page"></a><span data-ttu-id="9d174-102">Editor de Origem de OLE DB (página Saída de Erro)</span><span class="sxs-lookup"><span data-stu-id="9d174-102">OLE DB Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="9d174-103">Use a página **Saída de Erro** da caixa de diálogo do **Editor de Origem OLE DB** para selecionar opções de tratamento de erro e definir propriedades em colunas de saída de erros.</span><span class="sxs-lookup"><span data-stu-id="9d174-103">Use the **Error Output** page of the **OLE DB Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="9d174-104">Para saber mais sobre a origem de OLE DB, consulte [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="9d174-104">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9d174-105">Opções</span><span class="sxs-lookup"><span data-stu-id="9d174-105">Options</span></span>  
 <span data-ttu-id="9d174-106">**Entrada/Saída**</span><span class="sxs-lookup"><span data-stu-id="9d174-106">**Input/Output**</span></span>  
 <span data-ttu-id="9d174-107">Exibe o nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9d174-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="9d174-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9d174-108">**Column**</span></span>  
 <span data-ttu-id="9d174-109">Exiba as colunas externas (origem) que você selecionou na página **Gerenciador de Conexões** da caixa de diálogo do **Editor de Origem OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="9d174-109">View the external (source) columns that you selected on the **Connection Manager** page of the **OLE DB Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="9d174-110">**Erro**</span><span class="sxs-lookup"><span data-stu-id="9d174-110">**Error**</span></span>  
 <span data-ttu-id="9d174-111">Especifique o que deve acontecer quando ocorre um erro: ignorar a falha, redirecionar a linha ou causar falha no componente.</span><span class="sxs-lookup"><span data-stu-id="9d174-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="9d174-112">**Tópicos relacionados:** [Tratamento de erro em dados](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="9d174-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="9d174-113">**Truncation**</span><span class="sxs-lookup"><span data-stu-id="9d174-113">**Truncation**</span></span>  
 <span data-ttu-id="9d174-114">Especifique o que deve acontecer quando ocorre um truncamento: ignorar a falha, redirecionar a linha ou causar falha do componente.</span><span class="sxs-lookup"><span data-stu-id="9d174-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="9d174-115">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9d174-115">**Description**</span></span>  
 <span data-ttu-id="9d174-116">Exiba a descrição do erro.</span><span class="sxs-lookup"><span data-stu-id="9d174-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="9d174-117">**Definir este valor para células selecionadas**</span><span class="sxs-lookup"><span data-stu-id="9d174-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="9d174-118">Especifique o que deve acontecer a todas as células selecionadas quando ocorre um erro ou um truncamento: ignorar a falha, redirecionar a linha ou causar a falha no componente.</span><span class="sxs-lookup"><span data-stu-id="9d174-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="9d174-119">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="9d174-119">**Apply**</span></span>  
 <span data-ttu-id="9d174-120">Aplique a opção de tratamento de erros às células selecionadas.</span><span class="sxs-lookup"><span data-stu-id="9d174-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d174-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9d174-121">See Also</span></span>  
 <span data-ttu-id="9d174-122">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9d174-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="9d174-123">[Editor de origem OLE DB &#40;página do Gerenciador de conexões&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="9d174-123">[OLE DB Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="9d174-124">[Editor de fonte de OLE DB &#40;página colunas&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="9d174-124">[OLE DB Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="9d174-125">[Extrair dados usando a fonte de OLE DB](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="9d174-125">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="9d174-126">Gerenciador de conexões OLE DB</span><span class="sxs-lookup"><span data-stu-id="9d174-126">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
