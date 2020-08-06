---
title: Aplicar regras de qualidade de dados à fonte de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a965e8f2-004d-4ccc-8523-a185b35b26e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d59e6fb5ffb752b3346d40740e0b841bf574344e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678874"
---
# <a name="apply-data-quality-rules-to-data-source"></a><span data-ttu-id="168ab-102">Aplicar regras de qualidade de dados à fonte de dados</span><span class="sxs-lookup"><span data-stu-id="168ab-102">Apply Data Quality Rules to Data Source</span></span>
  <span data-ttu-id="168ab-103">Você pode usar o DQS (Data Quality Services) para corrigir dados no fluxo de dados de pacote conectando a transformação de limpeza DQS à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="168ab-103">You can use Data Quality Services (DQS) to correct data in the package data flow by connecting the DQS Cleansing transformation to the data source.</span></span> <span data-ttu-id="168ab-104">Para obter mais informações sobre DQS, consulte [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="168ab-104">For more information about DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span> <span data-ttu-id="168ab-105">Para obter mais informações sobre a transformação, consulte [DQS Cleansing Transformation](dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="168ab-105">For more information about the transformation, see [DQS Cleansing Transformation](dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="168ab-106">Quando você processar dados com a transformação de limpeza DQS, um projeto de qualidade de dados é criado no Data Quality Server.</span><span class="sxs-lookup"><span data-stu-id="168ab-106">When you process data with the DQS Cleansing transformation, a data quality project is created on the Data Quality Server.</span></span> <span data-ttu-id="168ab-107">Você usa o Cliente Data Quality para gerenciar o projeto.</span><span class="sxs-lookup"><span data-stu-id="168ab-107">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="168ab-108">Para obter mais informações, consulte [Gerenciar &#40;Abrir, desbloquear, renomear e excluir&#41; um projeto de qualidade de dados](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span><span class="sxs-lookup"><span data-stu-id="168ab-108">For more information, see [Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span></span>  
  
### <a name="to-correct-data-in-the-data-flow"></a><span data-ttu-id="168ab-109">Para corrigir dados no fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="168ab-109">To correct data in the data flow</span></span>  
  
1.  <span data-ttu-id="168ab-110">Criar um pacote.</span><span class="sxs-lookup"><span data-stu-id="168ab-110">Create a package.</span></span>  
  
2.  <span data-ttu-id="168ab-111">Adicione e configure a transformação Limpeza DQS.</span><span class="sxs-lookup"><span data-stu-id="168ab-111">Add and configure the DQS Cleansing transformation.</span></span> <span data-ttu-id="168ab-112">Para obter mais informações, consulte [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="168ab-112">For more information, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="168ab-113">Conecte a transformação Limpeza DQS a uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="168ab-113">Connect the DQS Cleansing transformation to a data source.</span></span>  
  
  
