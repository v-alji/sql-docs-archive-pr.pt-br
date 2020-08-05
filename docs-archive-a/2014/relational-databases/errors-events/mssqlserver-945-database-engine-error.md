---
title: MSSQLSERVER_945 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 945 (Database Engine error)
ms.assetid: ee501d13-0bd9-4627-896c-ed5b1bdb88b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 51284cdcf48f1bf713a853f9c87457cb5291cc4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573042"
---
# <a name="mssqlserver_945"></a>MSSQLSERVER_945
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do Produto|SQL Server|  
|ID do evento|945|  
|Origem do Evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|DB_IS_SHUTDOWN|  
|Texto da mensagem|O banco de dados '%.*ls' não pode ser aberto devido a arquivos inacessíveis, memória ou espaço em disco insuficiente.  Consulte o log de erros do SQL Server para obter detalhes.|  
  
## <a name="explanation"></a>Explicação  
 O banco de dados não pôde ser acessado porque faltam arquivos ou outros recursos.  
  
## <a name="user-action"></a>Ação do usuário  
 Verifique o log de erros para obter informações adicionais sobre memória, espaço em disco ou falha de permissão. Confirme o local dos arquivos .mdf e .ndf do banco de dados afetado e confirme se a conta usada pelo [!INCLUDE[ssDE](../../includes/ssde-md.md)] tem permissão para acessar esses arquivos. Depois de corrigir o problema, reinicialize o banco de dados usando ALTER DATABASE para defini-lo como ONLINE.  
  
  
