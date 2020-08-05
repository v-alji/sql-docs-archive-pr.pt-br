---
title: Construções com suporte em procedimentos armazenados compilados nativamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 6b21f47e-bceb-4054-8b3c-9d39bb9583c0
author: rothja
ms.author: jroth
ms.openlocfilehash: f3bc7e28fa2a868ac39c6adbb2dea3cc5c3ace73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572556"
---
# <a name="supported-constructs-on-natively-compiled-stored-procedures"></a>Construções com suporte em procedimentos armazenados compilados de modo nativo
  Este tópico lista as construções com suporte nos procedimentos armazenados compilados nativamente.  
  
 Para obter informações sobre construções sem suporte, veja [Construções do Transact-SQL sem suporte pelo OLTP in-memory](transact-sql-constructs-not-supported-by-in-memory-oltp.md).  
  
## <a name="procedure-ddl"></a>DDL do procedimento  
 Há suporte para o seguinte:  
  
-   CREATE PROCEDURE  
  
-   DROP PROCEDURE  
  
-   SCHEMABINDING (necessário para procedimentos armazenados compilados nativamente)  
  
-   NATIVE_COMPILATION  
  
-   Os parâmetros podem ser declarados com NOT NULL.  
  
-   Parâmetros com valor de tabela.  
  
## <a name="security"></a>Segurança  
 Há suporte para o seguinte:  
  
-   Para procedimentos: EXECUTE AS OWNER, SELF e usuário.  
  
-   Permissões GRANT e DENY em tabelas e procedimentos.  
  
## <a name="see-also"></a>Consulte Também  
 [Procedimentos armazenados compilados nativamente](natively-compiled-stored-procedures.md)  
  
  
