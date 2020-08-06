---
title: Executar scripts durante a sincronização (programação Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synchronization [SQL Server replication], scripts
- scripts [SQL Server replication], synchronization and
- sp_addscriptexec
ms.assetid: b58a0877-4e43-4fab-a281-24e6022d3fb1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bc217ad160a0238cc4247600d65eb32f156071f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569904"
---
# <a name="execute-scripts-during-synchronization-replication-transact-sql-programming"></a><span data-ttu-id="207a6-102">Executar scripts durante a sincronização (Programação Transact-SQL de replicação)</span><span class="sxs-lookup"><span data-stu-id="207a6-102">Execute Scripts During Synchronization (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="207a6-103">A replicação dá suporte à execução de scripts sob demanda para Assinantes para publicações transacionais e de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="207a6-103">Replication supports on demand script execution for Subscribers to transactional and merge publications.</span></span> <span data-ttu-id="207a6-104">Essa funcionalidade copia o script no diretório que executa a replicação e usa **sqlcmd** para aplicar o script no Assinante.</span><span class="sxs-lookup"><span data-stu-id="207a6-104">This functionality copies the script to the replication working directory and then uses **sqlcmd** to apply the script at the Subscriber.</span></span> <span data-ttu-id="207a6-105">Por padrão, se houver uma falha ao aplicar o script para uma assinatura em uma publicação transacional, o Agente de Distribuição se deterá.</span><span class="sxs-lookup"><span data-stu-id="207a6-105">By default, if there is a failure when applying the script for a subscription to a transactional publication, the Distribution Agent will stop.</span></span> <span data-ttu-id="207a6-106">Você pode especificar um script [!INCLUDE[tsql](../../includes/tsql-md.md)] para ser executado programaticamente usando procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="207a6-106">You can specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script to execute programmatically using replication stored procedures.</span></span>  
  
### <a name="to-specify-a-script-to-run-for-all-subscribers-to-a-snapshot-transactional-or-merge-publication"></a><span data-ttu-id="207a6-107">Para especificar um script para ser executado para todos os Assinantes para uma publicação de instantâneo, transacional ou de mesclagem</span><span class="sxs-lookup"><span data-stu-id="207a6-107">To specify a script to run for all Subscribers to a snapshot, transactional or merge publication</span></span>  
  
1.  <span data-ttu-id="207a6-108">Componha e teste o script [!INCLUDE[tsql](../../includes/tsql-md.md)] que será executado sob demanda.</span><span class="sxs-lookup"><span data-stu-id="207a6-108">Compose and test the [!INCLUDE[tsql](../../includes/tsql-md.md)] script that will be executed on demand.</span></span>  
  
2.  <span data-ttu-id="207a6-109">Salve o arquivo de script em um local em que possa ser acessado pelo Snapshot Agent para a publicação.</span><span class="sxs-lookup"><span data-stu-id="207a6-109">Save the script file to a location where it can be accessed by the Snapshot Agent for the publication.</span></span>  
  
3.  <span data-ttu-id="207a6-110">No Publicador no banco de dados de publicação, execute [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="207a6-110">At the Publisher on the publication database, execute [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span> <span data-ttu-id="207a6-111">Especifique a \*\* \@ publicação**, o nome do arquivo de script com o caminho UNC completo criado na etapa 2 para \*\* \@ scriptfile**e um dos valores a seguir para \*\* \@ skiperror\*\*:</span><span class="sxs-lookup"><span data-stu-id="207a6-111">Specify **\@publication**, the name of the script file with full UNC path created in step 2 for **\@scriptfile**, and one of the following values for **\@skiperror**:</span></span>  
  
    -   <span data-ttu-id="207a6-112">**0** - o agente deixará de executar o script se um erro for encontrado.</span><span class="sxs-lookup"><span data-stu-id="207a6-112">**0** - the agent will stop executing the script if an error is encountered.</span></span>  
  
    -   <span data-ttu-id="207a6-113">**1** - o agente fará log dos erros e continuará executando o script quando forem encontrados erros.</span><span class="sxs-lookup"><span data-stu-id="207a6-113">**1** - the agent will log errors and continue executing the script when errors are encountered.</span></span>  
  
4.  <span data-ttu-id="207a6-114">O script especificado será executado para cada Assinante na próxima vez que o agente for executado para sincronizar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="207a6-114">The specified script will be executed at each Subscriber when the agent next runs to synchronize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="207a6-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="207a6-115">See Also</span></span>  
 [<span data-ttu-id="207a6-116">Sincronizar dados</span><span class="sxs-lookup"><span data-stu-id="207a6-116">Synchronize Data</span></span>](synchronize-data.md)  
  
  
