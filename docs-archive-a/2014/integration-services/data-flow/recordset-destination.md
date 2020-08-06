---
title: Destino do conjunto de registros | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.recordsetdest.f1
helpviewer_keywords:
- Recordset destination
- ADO recordsets [Integration Services]
- destinations [Integration Services], Recordset
- in-memory ADO recordsets [Integration Services]
ms.assetid: be973cf1-c4ff-49f8-987e-314c08ef98e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1acc29c904e9020721e8ac62dff09a8ec29a392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571460"
---
# <a name="recordset-destination"></a><span data-ttu-id="90ea0-102">Destino do Conjunto de Registros</span><span class="sxs-lookup"><span data-stu-id="90ea0-102">Recordset Destination</span></span>
  <span data-ttu-id="90ea0-103">O destino do conjunto de registros cria e popula um conjunto de registros ADO na memória.</span><span class="sxs-lookup"><span data-stu-id="90ea0-103">The Recordset destination creates and populates an in-memory ADO recordset.</span></span> <span data-ttu-id="90ea0-104">A forma do conjunto de registros é definida na entrada para o destino de conjunto de registros no tempo de design.</span><span class="sxs-lookup"><span data-stu-id="90ea0-104">The shape of the recordset is defined by the input to the Recordset destination at design time.</span></span>  
  
## <a name="configuration-of-the-recordset-destination"></a><span data-ttu-id="90ea0-105">Configuração do destino do conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="90ea0-105">Configuration of the Recordset Destination</span></span>  
 <span data-ttu-id="90ea0-106">Configure o destino do conjunto de registros especificando a variável que armazena o conjunto de registros ADO.</span><span class="sxs-lookup"><span data-stu-id="90ea0-106">You configure the Recordset destination by specifying the variable that stores the ADO recordset.</span></span>  
  
 <span data-ttu-id="90ea0-107">No tempo de execução, um conjunto de registros ADO é gravado para a variável de tipo, Objeto, que é especificado na propriedade VariableName do destino do conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="90ea0-107">At run time, an ADO recordset is written to the variable of type, Object, that is specified in the VariableName property of the Recordset destination.</span></span> <span data-ttu-id="90ea0-108">A variável torna o conjunto de registros disponível fora do fluxo de dados, onde pode ser usado por scripts e outros elementos de pacote.</span><span class="sxs-lookup"><span data-stu-id="90ea0-108">The variable then makes the Recordset available outside the data flow, where it can be used by scripts and other package elements.</span></span>  
  
 <span data-ttu-id="90ea0-109">Esta fonte tem uma entrada.</span><span class="sxs-lookup"><span data-stu-id="90ea0-109">This source has one input.</span></span> <span data-ttu-id="90ea0-110">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="90ea0-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="90ea0-111">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="90ea0-111">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="90ea0-112">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="90ea0-112">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="90ea0-113">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="90ea0-113">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="90ea0-114">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="90ea0-114">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="90ea0-115">Propriedades personalizadas do destino do conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="90ea0-115">Recordset Destination Custom Properties</span></span>](recordset-destination-custom-properties.md)  
  
 <span data-ttu-id="90ea0-116">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="90ea0-116">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="90ea0-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="90ea0-117">Related Tasks</span></span>  
 [<span data-ttu-id="90ea0-118">Usar um destino do conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="90ea0-118">Use a Recordset Destination</span></span>](recordset-destination.md)  
  
  
