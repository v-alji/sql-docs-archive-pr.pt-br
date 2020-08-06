---
title: MSSQLSERVER_1458 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1458 (Database Engine error)
ms.assetid: adc78c59-a6f2-432b-9a07-fdd1dc2b9026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: efa45177a92402b25099be5bb3e3dcc91a5fa6d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581898"
---
# <a name="mssqlserver_1458"></a>MSSQLSERVER_1458
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do Produto|SQL Server|  
|ID do evento|1458|  
|Origem do Evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|DBM_FAILREDO_ON_PRIMARY|  
|Texto da mensagem|A cópia principal do banco de dados '%.*ls' encontrou o erro %d, status %d, severidade %d. O espelhamento de banco de dados foi suspenso. Tente resolver a condição de erro e retomar o espelhamento.|  
  
## <a name="explanation"></a>Explicação  
 Essa mensagem indica que o banco de dados principal encontrou um erro que causou a suspensão do espelhamento de banco de dados.  
  
## <a name="user-action"></a>Ação do usuário  
 A maioria dos casos desse erro é corrigida automaticamente. Se o problema persistir, reiniciar o banco de dados ou a instância do servidor geralmente corrige o problema. Para obter mais informações, procure no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em cada parceiro o erro associado que precedeu essa mensagem.  
  
## <a name="see-also"></a>Consulte Também  
 [Monitorando o espelhamento de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
