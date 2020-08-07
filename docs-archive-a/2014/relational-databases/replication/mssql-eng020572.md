---
title: MSSQL_ENG020572 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020572 error
ms.assetid: 636566db-ffcf-4109-8c11-15b8c7cb9cd9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5762f160e119012f4fdc0ca1a205ba0ecf690378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583533"
---
# <a name="mssql_eng020572"></a>MSSQL_ENG020572
    
## <a name="message-details"></a>Detalhes da mensagem  
  
|||  
|-|-|  
|Nome do Produto|SQL Server|  
|ID do evento|20572|  
|Origem do Evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nome simbólico||  
|Texto da mensagem|A assinatura do assinante '%s' para o artigo '%s' na publicação '%s' foi reiniciada após uma falha na validação.|  
  
## <a name="explanation"></a>Explicação  
 Os dados no Assinante foram validados de acordo com os dados no Publicador, e os dados não corresponderam, portanto, houve falha na validação. Quando você especificou que a validação deveria ser realizada, selecionou a opção de reinicialização da assinatura no caso de falha de validação. Reinicializar uma assinatura envolve a aplicação de um novo instantâneo no Assinante. Para obter mais informações sobre validação, consulte [Validate Replicated Data](validate-data-at-the-subscriber.md).  
  
## <a name="user-action"></a>Ação do usuário  
 Dados no Publicador e no Assinante serão correspondentes após a aplicação de um novo instantâneo no Assinante.  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md)  
  
  
