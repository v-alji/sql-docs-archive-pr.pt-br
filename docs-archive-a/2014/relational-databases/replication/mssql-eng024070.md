---
title: MSSQL_ENG024070 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG024070 error
ms.assetid: 23ac7e00-fab6-429b-9f85-2736a322aa65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fcfcb96b284d46d46f63af4a650f925ef2de73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679859"
---
# <a name="mssql_eng024070"></a>MSSQL_ENG024070
    
## <a name="message-details"></a>Detalhes da mensagem  
  
|||  
|-|-|  
|Nome do Produto|SQL Server|  
|ID do evento|24070|  
|Origem do Evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nome simbólico||  
|Texto da mensagem|O cliente não possui o privilégio exigido.|  
  
## <a name="explanation"></a>Explicação  
 Este é um erro geral que pode ocorrer independentemente do uso de replicação. Para um servidor em uma topologia de replicação, geralmente o erro ocorre porque a conta do serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é alterada usando o Gerenciador de Controle de Serviços do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows em vez do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager. Ao tentar executar um trabalho de agente após alterar a conta de serviço, pode ocorrer falha no trabalho com uma mensagem de erro semelhante à seguinte:  
  
 "Executado como usuário: \<UserAccount> . Replicação-subsistema de instantâneos de replicação: falha do agente \<AgentName> . Executado como usuário: \<UserAccount> . O cliente não possui o privilégio exigido. A etapa falhou. `[SQLSTATE 42000] (Error 14151)`. A etapa falhou."  
  
 Esse problema ocorre porque o Gerenciador de Controle de Serviços do Windows não é capaz de conceder as permissões solicitadas para a nova conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.  
  
## <a name="user-action"></a>Ação do usuário  
 Para evitar esse problema posteriormente, sempre use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager em vez do Gerenciador de Controle de Serviços do Windows para alterar as contas e as senhas de serviço.  
  
 Para resolver esse problema, use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager para alterar a conta de serviço de volta para a conta original. Em seguida, use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager para alterar para a nova conta. Ao fazer isso, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager adiciona a nova conta ao seguinte grupo de segurança:  
  
 SQLServer2008SQLAgentUser$ComputerName$InstanceName  
  
 Ser um membro desse grupo de segurança concede à nova conta as permissões exigidas para executar o trabalho do agente de replicação.  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md)   
 [Gerenciar logons e senhas na replicação](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication)   
 [SQL Server Configuration Manager](../sql-server-configuration-manager.md)  
  
  
