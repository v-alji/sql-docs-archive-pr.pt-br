---
title: Controlar o comportamento de gatilhos e restrições durante a sincronização (Programação Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- identities [SQL Server replication]
- constraints [SQL Server], replication
- triggers [SQL Server], replication
- triggers [SQL Server replication]
- constraints [SQL Server replication]
- NOT FOR REPLICATION option
- NFR option
ms.assetid: 7c4e0f0e-cadc-4c99-98f4-69799b9b356b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 88176f43295fe2ab1f5f5643a46db1ce6132c5f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569375"
---
# <a name="control-the-behavior-of-triggers-and-constraints-during-synchronization-replication-transact-sql-programming"></a><span data-ttu-id="2de10-102">Controlar o comportamento de gatilhos e restrições durante sincronização (Programação Transact-SQL de replicação)</span><span class="sxs-lookup"><span data-stu-id="2de10-102">Control the Behavior of Triggers and Constraints During Synchronization (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="2de10-103">Durante a sincronização, os agentes de replicação executam instruções [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) e [DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) em tabelas replicadas, o que pode fazer com que os gatilhos de DML (linguagem de manipulação de dados) nessas tabelas sejam executados.</span><span class="sxs-lookup"><span data-stu-id="2de10-103">During synchronization, replication agents execute [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql), and [DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) statements on replicated tables, which can cause data manipulation language (DML) triggers on these tables to be executed.</span></span> <span data-ttu-id="2de10-104">Há casos em que é possível que você precise impedir o acionamento desses gatilhos ou a imposição de restrições durante a sincronização.</span><span class="sxs-lookup"><span data-stu-id="2de10-104">There are cases when you may need to prevent these triggers from firing or constraints from being enforced during synchronization.</span></span> <span data-ttu-id="2de10-105">Esse comportamento depende de como o gatilho ou a restrição foram criados.</span><span class="sxs-lookup"><span data-stu-id="2de10-105">This behavior depends on how the trigger or constraint is created.</span></span>  
  
### <a name="to-prevent-triggers-from-executing-during-synchronization"></a><span data-ttu-id="2de10-106">Para evitar a execução de gatilhos durante a sincronização</span><span class="sxs-lookup"><span data-stu-id="2de10-106">To prevent triggers from executing during synchronization</span></span>  
  
1.  <span data-ttu-id="2de10-107">Ao criar um novo gatilho, especifique a opção NOT FOR REPLICATION de [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2de10-107">When creating a new trigger, specify the NOT FOR REPLICATION option of [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
2.  <span data-ttu-id="2de10-108">Para um gatilho existente, especifique a opção NOT FOR REPLICATION de [ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2de10-108">For an existing trigger, specify the NOT FOR REPLICATION option of [ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql).</span></span>  
  
### <a name="to-prevent-constraints-from-being-enforced-during-synchronization"></a><span data-ttu-id="2de10-109">Para impedir a imposição de restrições durante a sincronização</span><span class="sxs-lookup"><span data-stu-id="2de10-109">To prevent constraints from being enforced during synchronization</span></span>  
  
1.  <span data-ttu-id="2de10-110">Ao criar uma nova restrição CHECK ou FOREIGN KEY, especifique a opção de CHECK NOT FOR REPLICATION na definição da restrição de [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2de10-110">When creating a new CHECK or FOREIGN KEY constraint, specify CHECK NOT FOR REPLICATION option in the constraint definition of [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de10-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2de10-111">See Also</span></span>  
 [<span data-ttu-id="2de10-112">Criar tabelas &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="2de10-112">Create Tables &#40;Database Engine&#41;</span></span>](../tables/create-tables-database-engine.md)  
  
  
