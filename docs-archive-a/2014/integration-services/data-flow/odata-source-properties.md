---
title: Propriedades do OData Source | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4fde5bb0-6d78-4ec4-8f0b-67f91c53fe99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8139f79ed595ca3e6204f96823f6bc95e6fb40df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685216"
---
# <a name="odata-source-properties"></a><span data-ttu-id="1eecc-102">Propriedades da origem do OData</span><span class="sxs-lookup"><span data-stu-id="1eecc-102">OData Source Properties</span></span>
  <span data-ttu-id="1eecc-103">Ao clicar com o botão direito do mouse em **Origem OData** no fluxo de dados e clicar em **Propriedades**, você verá as propriedades do componente de **Origem OData** na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="1eecc-103">When you right-click **OData Source** in the data flow and click **Properties**, you will see properties for the **OData Source** component in the **Properties** window.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1eecc-104">Propriedade</span><span class="sxs-lookup"><span data-stu-id="1eecc-104">Property</span></span>|<span data-ttu-id="1eecc-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="1eecc-105">Description</span></span>|  
|<span data-ttu-id="1eecc-106">CollectionName</span><span class="sxs-lookup"><span data-stu-id="1eecc-106">CollectionName</span></span>|<span data-ttu-id="1eecc-107">Nome da coleção que você deseja recuperar do serviço OData.</span><span class="sxs-lookup"><span data-stu-id="1eecc-107">Name of the collection you wish to retrieve from the OData service.</span></span> <span data-ttu-id="1eecc-108">A propriedade **CollectionName** é usada quando **UseResourcePath** é falso.</span><span class="sxs-lookup"><span data-stu-id="1eecc-108">The **CollectionName** property is used when **UseResourcePath** is False.</span></span><br /><br /> <span data-ttu-id="1eecc-109">Esta propriedade pode receber expressão, permitindo que o valor seja definido em runtime.</span><span class="sxs-lookup"><span data-stu-id="1eecc-109">This property is expression-able, allowing the value to be set at runtime.</span></span> <span data-ttu-id="1eecc-110">No entanto, se os metadados da coleção não corresponderem aos metadados usados em tempo de design, um erro de validação ocorrerá, fazendo com que a execução do fluxo de dados falhe.</span><span class="sxs-lookup"><span data-stu-id="1eecc-110">However, if the metadata of the collection does not match the metadata that was used at design time, a validation error will occur, causing the data flow execution to fail.</span></span>|  
|<span data-ttu-id="1eecc-111">DefaultStringLength</span><span class="sxs-lookup"><span data-stu-id="1eecc-111">DefaultStringLength</span></span>|<span data-ttu-id="1eecc-112">Este valor especifica o comprimento padrão para as colunas de cadeia de caracteres que não têm nenhum comprimento máximo.</span><span class="sxs-lookup"><span data-stu-id="1eecc-112">This value specifies default length for string columns that have no max length.</span></span><br /><br /> <span data-ttu-id="1eecc-113">**Padrão:** 4000</span><span class="sxs-lookup"><span data-stu-id="1eecc-113">**Default:** 4000</span></span>|  
|<span data-ttu-id="1eecc-114">Consulta</span><span class="sxs-lookup"><span data-stu-id="1eecc-114">Query</span></span>|<span data-ttu-id="1eecc-115">Os parâmetros de consulta do OData.</span><span class="sxs-lookup"><span data-stu-id="1eecc-115">The OData query parameters.</span></span> <span data-ttu-id="1eecc-116">Esta propriedade pode receber expressão e pode ser definida em runtime.</span><span class="sxs-lookup"><span data-stu-id="1eecc-116">This property is expression-able and can be set at runtime.</span></span>|  
|<span data-ttu-id="1eecc-117">ResourcePath</span><span class="sxs-lookup"><span data-stu-id="1eecc-117">ResourcePath</span></span>|<span data-ttu-id="1eecc-118">Use essa propriedade quando precisar especificar um caminho completo de recurso, em vez de apenas selecionar um nome de coleção.</span><span class="sxs-lookup"><span data-stu-id="1eecc-118">Use this property when you need to specify a full resource path, rather than just selecting a collection name.</span></span> <span data-ttu-id="1eecc-119">Esta propriedade é usada quando **UseResourcePath** é verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="1eecc-119">This property is used when **UseResourcePath** is True.</span></span>|  
|<span data-ttu-id="1eecc-120">UseResourcePath</span><span class="sxs-lookup"><span data-stu-id="1eecc-120">UseResourcePath</span></span>|<span data-ttu-id="1eecc-121">Quando definido como verdadeiro, o valor de **ResourcePath** é anexado à URL de base para determinar o local do feed de OData.</span><span class="sxs-lookup"><span data-stu-id="1eecc-121">When set to True, the **ResourcePath** value is appended to the base URL to determine the OData feed location.</span></span> <span data-ttu-id="1eecc-122">Quando definido como falso, o valor de **CollectionName** é usado.</span><span class="sxs-lookup"><span data-stu-id="1eecc-122">When set to False, the **CollectionName** value is used.</span></span><br /><br /> <span data-ttu-id="1eecc-123">**Padrão:** For</span><span class="sxs-lookup"><span data-stu-id="1eecc-123">**Default:** False</span></span>|  
  
  
