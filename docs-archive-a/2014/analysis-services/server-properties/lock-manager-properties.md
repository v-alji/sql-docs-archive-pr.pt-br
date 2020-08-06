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
# <a name="lock-manager-properties"></a>Propriedades do gerenciador de bloqueio
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] oferece suporte às propriedades do servidor do gerenciador de bloqueio, listadas na tabela a seguir. Para obter mais informações sobre as propriedades de servidor adicionais e como defini-las, consulte [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).  
  
 **Aplica-se a:** modo de servidor multidimensional e tabular  
  
## <a name="properties"></a>Propriedades  
 `DefaultLockTimeoutMS`  
 Uma propriedade de inteiro de 32 bits assinada que define o tempo limite de bloqueio padrão em milissegundos para solicitações de bloqueio internas.  
  
 O valor padrão para essa propriedade é -1, o que indica que não há nenhum tempo limite para solicitações de bloqueio interno.  
  
 `LockWaitGranularityMS`  
 Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .  
  
 `DeadlockDetectionGranularityMS`  
 Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .  
  
## <a name="see-also"></a>Consulte Também  
 [Configurar propriedades do servidor no Analysis Services](server-properties-in-analysis-services.md)   
 [Determina o Modo de Servidor de uma instância do Analysis Services.](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
