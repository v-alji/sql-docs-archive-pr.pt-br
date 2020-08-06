---
title: Propriedades do Gerenciador de bloqueio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- lock manager properties [Analysis Services]
- LockWaitGranularityMS property
- DefaultLockTimeoutMS property
- DeadlockDetectionGranularityMS property
ms.assetid: 15fe9ead-825b-4ac3-9191-7a07caa2861b
author: minewiskan
ms.author: owend
ms.openlocfilehash: d10927f1c549f00625b8affb801ec7b0831827c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686391"
---
# <a name="lock-manager-properties"></a><span data-ttu-id="94110-102">Propriedades do gerenciador de bloqueio</span><span class="sxs-lookup"><span data-stu-id="94110-102">Lock Manager Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="94110-103">oferece suporte às propriedades do servidor do gerenciador de bloqueio, listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="94110-103">supports the lock manager server properties listed in the following table.</span></span> <span data-ttu-id="94110-104">Para obter mais informações sobre as propriedades de servidor adicionais e como defini-las, consulte [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="94110-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="94110-105">**Aplica-se a:** modo de servidor multidimensional e tabular</span><span class="sxs-lookup"><span data-stu-id="94110-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="94110-106">Propriedades</span><span class="sxs-lookup"><span data-stu-id="94110-106">Properties</span></span>  
 `DefaultLockTimeoutMS`  
 <span data-ttu-id="94110-107">Uma propriedade de inteiro de 32 bits assinada que define o tempo limite de bloqueio padrão em milissegundos para solicitações de bloqueio internas.</span><span class="sxs-lookup"><span data-stu-id="94110-107">A signed 32-bit integer property that defines default lock timeout in milliseconds for internal lock requests.</span></span>  
  
 <span data-ttu-id="94110-108">O valor padrão para essa propriedade é -1, o que indica que não há nenhum tempo limite para solicitações de bloqueio interno.</span><span class="sxs-lookup"><span data-stu-id="94110-108">The default value for this property is -1, which indicates there is no timeout for internal lock requests.</span></span>  
  
 `LockWaitGranularityMS`  
 <span data-ttu-id="94110-109">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94110-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DeadlockDetectionGranularityMS`  
 <span data-ttu-id="94110-110">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94110-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94110-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94110-111">See Also</span></span>  
 <span data-ttu-id="94110-112">[Configurar propriedades do servidor no Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="94110-112">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="94110-113">Determina o Modo de Servidor de uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="94110-113">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
