---
title: Carregar dados em massa em tabelas em uma publicação de mesclagem (Programação Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- bulk load [SQL Server replication]
- merge replication bulk loading [SQL Server replication]
- sp_addtabletocontents
ms.assetid: 16e6498a-b449-4051-aec4-ea814a2ad993
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f669a1f7132aa0f588fd89fb9747a7dc9017fcf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685574"
---
# <a name="bulk-load-data-into-tables-in-a-merge-publication-replication-transact-sql-programming"></a><span data-ttu-id="809c7-102">Carregar dados em massa em tabelas em uma publicação de mesclagem (Programação Transact-SQL de replicação)</span><span class="sxs-lookup"><span data-stu-id="809c7-102">Bulk-Load Data into Tables in a Merge Publication (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="809c7-103">Quando os dados são carregados em tabelas com o comando [bcp Utility](../../tools/bcp-utility.md) ou [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) , por padrão, os gatilhos da replicação de mesclagem que mantêm dados de rastreamento na tabela de sistema [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql) não são acionados.</span><span class="sxs-lookup"><span data-stu-id="809c7-103">When data is loaded into tables using the [bcp Utility](../../tools/bcp-utility.md) or the [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) command, by default, the merge replication triggers that maintain tracking data in the [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql) system table are not fired.</span></span> <span data-ttu-id="809c7-104">Você pode forçar os gatilhos de replicação de mesclagem para serem acionados enquanto os dados forem carregados ou, você pode inserir os metadados de replicação gerados programaticamente após a operação de cópia em massa usando os procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="809c7-104">You can either force the merge replication triggers to fire as the data is loaded, or you can insert the generated replication metadata programmatically after the bulk copy operation using replication stored procedures.</span></span>  
  
### <a name="to-bulk-load-data-into-tables-published-by-merge-replication-using-the-bcp-utility"></a><span data-ttu-id="809c7-105">Para carregar dados em massa em tabelas publicadas por replicação de mesclagem usando o utilitário bcp</span><span class="sxs-lookup"><span data-stu-id="809c7-105">To bulk-load data into tables published by merge replication using the bcp utility</span></span>  
  
1.  <span data-ttu-id="809c7-106">No Publicador ou no Assinante, execute [bcp Utility](../../tools/bcp-utility.md) ou [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) para inserir dados em uma tabela publicada usando a replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="809c7-106">At either the Publisher or Subscriber, execute the [bcp Utility](../../tools/bcp-utility.md) or [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) to insert data into a table published using merge replication.</span></span>  
  
2.  <span data-ttu-id="809c7-107">Use um dos métodos abaixo para assegurar que são gerados os metadados de replicação para os dados inseridos.</span><span class="sxs-lookup"><span data-stu-id="809c7-107">Use one of the following methods to ensure that replication metadata is generated for the inserted data.</span></span>  
  
    -   <span data-ttu-id="809c7-108">Execute a cópia em massa usando a opção FIRE_TRIGGERS.</span><span class="sxs-lookup"><span data-stu-id="809c7-108">Execute the bulk copy using the FIRE_TRIGGERS option.</span></span>  
  
    -   <span data-ttu-id="809c7-109">No banco de dados no qual os dados foram inseridos, execute [sp_addtabletocontents &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addtabletocontents-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="809c7-109">On the database into which data was inserted, execute [sp_addtabletocontents &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addtabletocontents-transact-sql).</span></span> <span data-ttu-id="809c7-110">Especifique o nome da tabela para a qual os dados foram inseridos **@table_name** .</span><span class="sxs-lookup"><span data-stu-id="809c7-110">Specify the table name into which the data was inserted for **@table_name**.</span></span>  
  
  
