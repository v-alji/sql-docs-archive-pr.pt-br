---
title: Editor de caminho de fluxo de dados (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.patheditor.general.f1
helpviewer_keywords:
- Data Flow Path Editor dialog box
ms.assetid: 72a9ff1d-3748-41d1-a9b2-63f4a77bba24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71eca61b1454e2e8cb811bbe450f584191ae77b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679469"
---
# <a name="data-flow-path-editor-general-page"></a><span data-ttu-id="3d097-102">Editor de Caminho do Fluxo de Dados (página Geral)</span><span class="sxs-lookup"><span data-stu-id="3d097-102">Data Flow Path Editor (General Page)</span></span>
  <span data-ttu-id="3d097-103">Use a caixa de diálogo **Editor de Caminho de Fluxo de Dados** para definir propriedades de caminho, visualizar metadados de colunas e gerenciar os visualizadores de dados que estão anexados ao caminho.</span><span class="sxs-lookup"><span data-stu-id="3d097-103">Use the **Data Flow Path Editor** dialog box to set path properties, view column metadata, and manage the data viewers attached to the path.</span></span>  
  
 <span data-ttu-id="3d097-104">Use o nó **Geral** da caixa de diálogo **Editor de Caminho de Fluxo de Dados** para nomear e descrever o caminho e especificar as opções de anotação de caminho.</span><span class="sxs-lookup"><span data-stu-id="3d097-104">Use the **General** node of the **Data Flow Path Editor** dialog box to name and describe the path, and to specify the options for path annotation.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3d097-105">Opções</span><span class="sxs-lookup"><span data-stu-id="3d097-105">Options</span></span>  
 <span data-ttu-id="3d097-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3d097-106">**Name**</span></span>  
 <span data-ttu-id="3d097-107">Forneça um nome exclusivo para o caminho.</span><span class="sxs-lookup"><span data-stu-id="3d097-107">Provide a unique name for the path.</span></span>  
  
 <span data-ttu-id="3d097-108">**ID**</span><span class="sxs-lookup"><span data-stu-id="3d097-108">**ID**</span></span>  
 <span data-ttu-id="3d097-109">O identificador de linhagem exclusivo do caminho.</span><span class="sxs-lookup"><span data-stu-id="3d097-109">The lineage identifier of the path.</span></span> <span data-ttu-id="3d097-110">Esta propriedade é somente para leitura.</span><span class="sxs-lookup"><span data-stu-id="3d097-110">This property is read-only.</span></span>  
  
 <span data-ttu-id="3d097-111">**IdentificationString**</span><span class="sxs-lookup"><span data-stu-id="3d097-111">**IdentificationString**</span></span>  
 <span data-ttu-id="3d097-112">A cadeia de caracteres que identifica o caminho.</span><span class="sxs-lookup"><span data-stu-id="3d097-112">The string that identifies the path.</span></span> <span data-ttu-id="3d097-113">Gerada automaticamente a partir do nome digitado acima.</span><span class="sxs-lookup"><span data-stu-id="3d097-113">Automatically generated from the name entered above.</span></span>  
  
 <span data-ttu-id="3d097-114">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3d097-114">**Description**</span></span>  
 <span data-ttu-id="3d097-115">Descreva o caminho.</span><span class="sxs-lookup"><span data-stu-id="3d097-115">Describe the path.</span></span>  
  
 <span data-ttu-id="3d097-116">**PathAnnotation**</span><span class="sxs-lookup"><span data-stu-id="3d097-116">**PathAnnotation**</span></span>  
 <span data-ttu-id="3d097-117">Especifique o tipo de anotação a ser usada.</span><span class="sxs-lookup"><span data-stu-id="3d097-117">Specify the type of annotation to use.</span></span> <span data-ttu-id="3d097-118">Escolha **Never** para desabilitar anotações, **AsNeeded** para habilitar anotação sob demanda, **SourceName** para anotações automáticas usando o valor da opção **SourceName** , e **PathName** para anotações automáticas usando o valor da propriedade **Name** .</span><span class="sxs-lookup"><span data-stu-id="3d097-118">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **SourceName** to automatically annotate using the value of the **SourceName** option, and **PathName** to automatically annotate using the value of the **Name** property.</span></span>  
  
 <span data-ttu-id="3d097-119">**DestinationName**</span><span class="sxs-lookup"><span data-stu-id="3d097-119">**DestinationName**</span></span>  
 <span data-ttu-id="3d097-120">Exibe a entrada que é o final do caminho.</span><span class="sxs-lookup"><span data-stu-id="3d097-120">Displays the input that is the end of the path.</span></span>  
  
 <span data-ttu-id="3d097-121">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="3d097-121">**SourceName**</span></span>  
 <span data-ttu-id="3d097-122">Exibe a saída que é o início do caminho.</span><span class="sxs-lookup"><span data-stu-id="3d097-122">Displays the output that is the start of the path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d097-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3d097-123">See Also</span></span>  
 <span data-ttu-id="3d097-124">[Editor de caminho de fluxo de dados &#40;página de metadados&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span><span class="sxs-lookup"><span data-stu-id="3d097-124">[Data Flow Path Editor &#40;Metadata Page&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span></span>  
 <span data-ttu-id="3d097-125">[Editor de caminho de fluxo de dados &#40;página visualizadores de dados&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span><span class="sxs-lookup"><span data-stu-id="3d097-125">[Data Flow Path Editor &#40;Data Viewers Page&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span></span>  
 <span data-ttu-id="3d097-126">[Fluxo de Dados](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="3d097-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="3d097-127">Usar anotações em pacotes</span><span class="sxs-lookup"><span data-stu-id="3d097-127">Use Annotations in Packages</span></span>](use-annotations-in-packages.md)  
  
  
