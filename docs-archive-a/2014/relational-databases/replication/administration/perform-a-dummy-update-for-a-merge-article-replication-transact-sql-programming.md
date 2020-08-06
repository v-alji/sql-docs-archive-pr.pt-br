---
title: Executar uma atualização fictícia para um artigo de mesclagem (Programação Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_mergedummyupdate
- dummy updates [SQL Server replication]
ms.assetid: 2f339210-4d85-4843-bd94-e86f7100d3ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fa0f868b2c3f98496046b138424d7d3a2fa2fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683511"
---
# <a name="perform-a-dummy-update-for-a-merge-article-replication-transact-sql-programming"></a><span data-ttu-id="6f393-102">Executar uma atualização fictícia para um artigo de mesclagem (Programação Transact-SQL de replicação)</span><span class="sxs-lookup"><span data-stu-id="6f393-102">Perform a Dummy Update for a Merge Article (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="6f393-103">As replicações de mesclagem usam gatilhos como parte do processo de replicação. Quando uma atualização é executada em uma tabela publicada, um gatilho de atualização é acionado.</span><span class="sxs-lookup"><span data-stu-id="6f393-103">Merge replication uses triggers as part of the replication process; when an update is made to published table, an update trigger fires.</span></span> <span data-ttu-id="6f393-104">Em alguns casos, os dados podem ser atualizados sem que o gatilho seja acionado, como durante as operações WRITETEXT e UPDATETEXT.</span><span class="sxs-lookup"><span data-stu-id="6f393-104">In some cases, data can be updated without the trigger firing, such as during the WRITETEXT and UPDATETEXT operations.</span></span> <span data-ttu-id="6f393-105">Nesses casos, você precisa adicionar uma instrução UPDATE fictícia explicitamente para replicar a alteração.</span><span class="sxs-lookup"><span data-stu-id="6f393-105">In these cases, you need to add a dummy UPDATE statement explicitly to replicate the change.</span></span> <span data-ttu-id="6f393-106">Você pode adicionar uma instrução UPDATE fictícia que usa procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="6f393-106">You can add a dummy UPDATE statement using replication stored procedures.</span></span>  
  
### <a name="to-add-a-dummy-update-statement"></a><span data-ttu-id="6f393-107">Para adicionar uma instrução UPDATE fictícia</span><span class="sxs-lookup"><span data-stu-id="6f393-107">To add a dummy UPDATE statement</span></span>  
  
1.  <span data-ttu-id="6f393-108">Execute a operação (por exemplo, UPDATETEXT) em uma linha em uma tabela de mesclagem publicada que exija uma atualização fictícia.</span><span class="sxs-lookup"><span data-stu-id="6f393-108">Execute the operation (for example, UPDATETEXT) on a row in a merge published table  that requires a dummy update.</span></span>  
  
2.  <span data-ttu-id="6f393-109">No servidor (Publicador ou Assinante) do banco de dados em que foi feita a alteração, execute [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6f393-109">At the server (Publisher or Subscriber) on the database where the change was made, execute [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql).</span></span> <span data-ttu-id="6f393-110">Especifique a tabela na qual a alteração foi feita **@source_object** e o identificador exclusivo da linha alterada para **@rowguid** .</span><span class="sxs-lookup"><span data-stu-id="6f393-110">Specify the table on which the change was made for **@source_object**, and the unique identifier of the changed row for **@rowguid**.</span></span>  
  
3.  <span data-ttu-id="6f393-111">Sincronize a assinatura para replicar a linha alterada.</span><span class="sxs-lookup"><span data-stu-id="6f393-111">Synchronize the subscription to replicate the changed row.</span></span>  
  
  
