---
title: Editor de transformação Extração de termos (guia exclusão) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.inclusionexclusion.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 90110d95-fd97-4542-9cda-832c86606130
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bc4b0401a1dd27111d0498e9e0d848c80da1742
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583160"
---
# <a name="term-extraction-transformation-editor-exclusion-tab"></a><span data-ttu-id="a4d09-102">Editor de Transformação Extração de Termos (guia Exclusão)</span><span class="sxs-lookup"><span data-stu-id="a4d09-102">Term Extraction Transformation Editor (Exclusion Tab)</span></span>
  <span data-ttu-id="a4d09-103">Use a guia **Exclusão** da caixa de diálogo do **Editor de Transformação Extração de Termos** para definir uma conexão com uma tabela de exclusão e especificar as colunas que contêm termos de exclusão.</span><span class="sxs-lookup"><span data-stu-id="a4d09-103">Use the **Exclusion** tab of the **Term Extraction Transformation Editor** dialog box to set up a connection to an exclusion table and specify the columns that contain exclusion terms.</span></span>  
  
 <span data-ttu-id="a4d09-104">Para saber mais sobre a transformação Extração de Termos, consulte [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a4d09-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a4d09-105">Opções</span><span class="sxs-lookup"><span data-stu-id="a4d09-105">Options</span></span>  
 <span data-ttu-id="a4d09-106">**Usar termos de exclusão**</span><span class="sxs-lookup"><span data-stu-id="a4d09-106">**Use exclusion terms**</span></span>  
 <span data-ttu-id="a4d09-107">Indique se devem ser excluídos termos específicos durante uma extração de termos especificando uma coluna que contém termos de exclusão.</span><span class="sxs-lookup"><span data-stu-id="a4d09-107">Indicate whether to exclude specific terms during term extraction by specifying a column that contains exclusion terms.</span></span> <span data-ttu-id="a4d09-108">Você deve especificar as seguintes propriedades de origem caso opte por excluir termos.</span><span class="sxs-lookup"><span data-stu-id="a4d09-108">You must specify the following source properties if you choose to exclude terms.</span></span>  
  
 <span data-ttu-id="a4d09-109">**Gerenciador de conexões OLE DB**</span><span class="sxs-lookup"><span data-stu-id="a4d09-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="a4d09-110">Selecione um gerenciador de conexões OLE DB existente ou crie uma nova conexão clicando em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a4d09-110">Select an existing OLE DB connection manager, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="a4d09-111">**Novo**</span><span class="sxs-lookup"><span data-stu-id="a4d09-111">**New**</span></span>  
 <span data-ttu-id="a4d09-112">Crie uma nova conexão com um banco de dados usando a caixa de diálogo **Configurar Gerenciador de Conexões OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="a4d09-112">Create a new connection to a database by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="a4d09-113">**Tabela ou exibição**</span><span class="sxs-lookup"><span data-stu-id="a4d09-113">**Table or view**</span></span>  
 <span data-ttu-id="a4d09-114">Selecione a tabela ou exibição que contém os termos de exclusão.</span><span class="sxs-lookup"><span data-stu-id="a4d09-114">Select the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="a4d09-115">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a4d09-115">**Column**</span></span>  
 <span data-ttu-id="a4d09-116">Selecione a coluna na tabela ou exibição que contém os termos de exclusão.</span><span class="sxs-lookup"><span data-stu-id="a4d09-116">Select the column in the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="a4d09-117">**Configurar Saída de Erro**</span><span class="sxs-lookup"><span data-stu-id="a4d09-117">**Configure Error Output**</span></span>  
 <span data-ttu-id="a4d09-118">Use a caixa de diálogo [Configurar Saída de Erro](../../2014/integration-services/configure-error-output.md) para especificar tratamento de erro em linhas que causam erros.</span><span class="sxs-lookup"><span data-stu-id="a4d09-118">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d09-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4d09-119">See Also</span></span>  
 <span data-ttu-id="a4d09-120">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a4d09-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a4d09-121">[Editor de transformação Extração de termos &#40;guia extração de termos&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="a4d09-121">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="a4d09-122">[Editor de transformação Extração de termos &#40;guia Avançado&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="a4d09-122">[Term Extraction Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="a4d09-123">Transformação Pesquisa de Termos</span><span class="sxs-lookup"><span data-stu-id="a4d09-123">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
