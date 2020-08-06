---
title: MSSQLSERVER_17132 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17132 (Database Engine error)
ms.assetid: d1d198bd-6730-4394-bd5f-28f320c01a38
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 609b9cea138db15cefd002f494620b5a1da7b208
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680452"
---
# <a name="mssqlserver_17132"></a>MSSQLSERVER_17132
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do Produto|SQL Server|  
|ID do evento|17132|  
|Origem do Evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|INIT_NODESSPACE|  
|Texto da mensagem|Ocorreu uma falha na inicialização do servidor devido à falta de memória para o descritor. Reduza a carga de memória dispensável ou aumente a memória do sistema.|  
  
## <a name="explanation"></a>Explicação  
 Falha ao alocar memória suficiente para armazenar o descritor interno do servidor.  
  
## <a name="user-action"></a>Ação do usuário  
 Adicione mais memória ao computador. As etapas genéricas para a solução de problemas de memória podem ser úteis.  
  
  
