---
title: Propriedades personalizadas do destino DataReader | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f151c3e8-3811-457d-a3d3-6158ca65a646
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62b6f628614d533e1bebcce071ce4761e73e08f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574823"
---
# <a name="datareader-destination-custom-properties"></a><span data-ttu-id="41d8c-102">Propriedades personalizadas do destino DataReader</span><span class="sxs-lookup"><span data-stu-id="41d8c-102">DataReader Destination Custom Properties</span></span>
  <span data-ttu-id="41d8c-103">O destino DataReader tem propriedades personalizadas e propriedades comuns a todos os componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="41d8c-103">The DataReader destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="41d8c-104">A tabela a seguir descreve as propriedades personalizadas do destino DataReader.</span><span class="sxs-lookup"><span data-stu-id="41d8c-104">The following table describes the custom properties of the DataReader destination.</span></span> <span data-ttu-id="41d8c-105">Todas as propriedades, exceto `DataReader`, são de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="41d8c-105">All properties except for `DataReader` are read/write.</span></span>  
  
|<span data-ttu-id="41d8c-106">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="41d8c-106">Property name</span></span>|<span data-ttu-id="41d8c-107">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="41d8c-107">Data Type</span></span>|<span data-ttu-id="41d8c-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="41d8c-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="41d8c-109">DataReader</span><span class="sxs-lookup"><span data-stu-id="41d8c-109">DataReader</span></span>|<span data-ttu-id="41d8c-110">String</span><span class="sxs-lookup"><span data-stu-id="41d8c-110">String</span></span>|<span data-ttu-id="41d8c-111">O nome da classe do destino DataReader.</span><span class="sxs-lookup"><span data-stu-id="41d8c-111">The class name of the DataReader destination.</span></span>|  
|<span data-ttu-id="41d8c-112">FailOnTimeout</span><span class="sxs-lookup"><span data-stu-id="41d8c-112">FailOnTimeout</span></span>|<span data-ttu-id="41d8c-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="41d8c-113">Boolean</span></span>|<span data-ttu-id="41d8c-114">Indica se deve haver falha na ocorrência de `ReadTimeout`.</span><span class="sxs-lookup"><span data-stu-id="41d8c-114">Indicates whether to fail when a `ReadTimeout` occurs.</span></span> <span data-ttu-id="41d8c-115">O valor padrão dessa propriedade é **False**.</span><span class="sxs-lookup"><span data-stu-id="41d8c-115">The default value of this property is **False**.</span></span>|  
|<span data-ttu-id="41d8c-116">ReadTimeout</span><span class="sxs-lookup"><span data-stu-id="41d8c-116">ReadTimeout</span></span>|<span data-ttu-id="41d8c-117">Integer</span><span class="sxs-lookup"><span data-stu-id="41d8c-117">Integer</span></span>|<span data-ttu-id="41d8c-118">O número de milissegundos antes de um tempo limite.</span><span class="sxs-lookup"><span data-stu-id="41d8c-118">The number of milliseconds before a time-out occurs.</span></span> <span data-ttu-id="41d8c-119">O valor padrão dessa propriedade é 30000 (30 segundos).</span><span class="sxs-lookup"><span data-stu-id="41d8c-119">The default value of this property is 30000 (30 seconds).</span></span>|  
  
 <span data-ttu-id="41d8c-120">A entrada e as colunas de entrada do destino DataReader não têm nenhuma propriedade personalizada.</span><span class="sxs-lookup"><span data-stu-id="41d8c-120">The input and the input columns of the DataReader destination have no custom properties.</span></span>  
  
 <span data-ttu-id="41d8c-121">Para obter mais informações, consulte [DataReader Destination](datareader-destination.md).</span><span class="sxs-lookup"><span data-stu-id="41d8c-121">For more information, see [DataReader Destination](datareader-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d8c-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="41d8c-122">See Also</span></span>  
 [<span data-ttu-id="41d8c-123">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="41d8c-123">Common Properties</span></span>](../common-properties.md)  
  
  
