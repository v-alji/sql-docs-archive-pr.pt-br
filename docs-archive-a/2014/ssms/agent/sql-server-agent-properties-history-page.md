---
title: Propriedades do SQL Server Agent (página Histórico) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.history.f1
ms.assetid: dc73734c-b3c3-407f-bbd1-8714b4fa47b0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d67ff3da97e11292abcac03958fe1e423b35d7d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582253"
---
# <a name="sql-server-agent-properties-history-page"></a>Propriedades do SQL Server Agent (página Histórico)
  Use esta página para exibir e modificar as configurações de gerenciamento do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log de histórico de serviço do Agent.  
  
## <a name="options"></a>Opções  
 **Limitar tamanho do log do histórico de trabalho**  
 Define limites para a quantidade de informações do histórico de trabalho que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantém no log.  
  
 **Tamanho máximo (em linhas) do log do histórico de trabalho**  
 Define o número máximo de linhas que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantém. Quando o log aumenta para conter esse número de linhas, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent remove as linhas mais antigas do log à medida que novas linhas forem inseridas.  
  
 **Máximo de linhas do histórico de trabalho por trabalho**  
 Define o número máximo de linhas que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantém por trabalho. Quando o log de um determinado trabalho cresce até conter esse número de linhas, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent remove as linhas mais antigas do log à medida que novas linhas são inseridas.  
  
 **Remover histórico de agente**  
 Especifica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removerá as entradas presentes no log por mais tempo do que o período especificado. Essa é uma execução de uma vez para remover o histórico. Se um trabalho recorrente for necessário, crie e agende um plano de manutenção com um trabalho de limpeza.  
  
 **Com mais de**  
 Define o período durante o qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent manterá entradas.  
  
## <a name="see-also"></a>Consulte Também  
 [Log de erros do SQL Server Agent](sql-server-agent-error-log.md)  
  
  
