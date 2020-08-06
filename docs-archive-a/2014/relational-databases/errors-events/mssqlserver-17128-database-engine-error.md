---
title: MSSQLSERVER_17128 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17128 (Database Engine error)
ms.assetid: 7b15a5e6-fd41-47ce-ba87-54f72acea4bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e08c668acd0a8b2decb14da338b8d1f1e650de5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679976"
---
# <a name="mssqlserver_17128"></a>MSSQLSERVER_17128
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do Produto|SQL Server|  
|ID do evento|17128|  
|Origem do Evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|INIT_NOBUFSPACE|  
|Texto da mensagem|initdata: sem memória para buffers de kernel.|  
  
## <a name="explanation"></a>Explicação  
 Falha nas alocações ou reservas de memória iniciais do pool de buffers. O SQL Server foi encerrado.  
  
## <a name="user-action"></a>Ação do usuário  
 Isso geralmente ocorre ao iniciar o SQL Server em um computador extremamente pequeno (bem menor que os requisitos mínimos do sistema).  
  
  
