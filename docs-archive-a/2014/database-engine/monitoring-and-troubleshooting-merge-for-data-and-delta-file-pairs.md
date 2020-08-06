---
title: Monitoramento e solução de problemas de mesclagem para dados e pares de arquivos Delta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a8b0bacc-4d2c-42e4-84bf-1a97e0bd385b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5dc57d08f3db1792a9359b3aa79aaceecd03a025
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582615"
---
# <a name="monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs"></a><span data-ttu-id="70b62-102">Monitorando e solucionando problemas de mesclagem de pares de arquivos delta e de dados</span><span class="sxs-lookup"><span data-stu-id="70b62-102">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>
  <span data-ttu-id="70b62-103">O OLTP na memória usa uma política de mesclagem para mesclar automaticamente pares adjacentes de arquivos delta e de dados.</span><span class="sxs-lookup"><span data-stu-id="70b62-103">In-Memory OLTP uses a merge policy to merge adjacent data and delta file pairs automatically.</span></span> <span data-ttu-id="70b62-104">Você não pode desabilitar a atividade de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="70b62-104">You cannot disable merge activity.</span></span>  
  
 <span data-ttu-id="70b62-105">Você pode monitorar pares de arquivos delta e de dados, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="70b62-105">You can monitor data and delta file pairs, as follows:</span></span>  
  
-   <span data-ttu-id="70b62-106">Compare o tamanho do armazenamento na memória ao tamanho geral do armazenamento.</span><span class="sxs-lookup"><span data-stu-id="70b62-106">Compare the size of in-memory storage to overall size of storage.</span></span> <span data-ttu-id="70b62-107">Se o armazenamento for desproporcionalmente grande, provavelmente a mesclagem não está sendo disparada.</span><span class="sxs-lookup"><span data-stu-id="70b62-107">If the storage is dis-proportionately large, then it is likely that merge is not getting triggered.</span></span> <span data-ttu-id="70b62-108">Para obter informações</span><span class="sxs-lookup"><span data-stu-id="70b62-108">For information</span></span>  
  
-   <span data-ttu-id="70b62-109">Examine o espaço usado em arquivos de dados e Delta usando [Sys. dm_db_xtp_checkpoint_files &#40;&#41;Transact-SQL](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) para ver se a mesclagem não está sendo disparada quando deveria.</span><span class="sxs-lookup"><span data-stu-id="70b62-109">Look at the used space in data and delta files using [sys.dm_db_xtp_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) to see if merge is not getting triggered when it should.</span></span>  
  
## <a name="performing-a-manual-merge"></a><span data-ttu-id="70b62-110">Executando uma mesclagem manual</span><span class="sxs-lookup"><span data-stu-id="70b62-110">Performing a Manual Merge</span></span>  
 <span data-ttu-id="70b62-111">Você pode usar [Sys. sp_xtp_merge_checkpoint_files &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) para executar uma mesclagem manual.</span><span class="sxs-lookup"><span data-stu-id="70b62-111">You can use [sys.sp_xtp_merge_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) to perform a manual merge.</span></span>  
  
 <span data-ttu-id="70b62-112">Use a seguinte consulta para recuperar informações sobre os arquivos delta e de dados,</span><span class="sxs-lookup"><span data-stu-id="70b62-112">Use the following query to retrieve information about the data and delta files,</span></span>  
  
```sql  
select checkpoint_file_id, file_type_desc, internal_storage_slot, file_size_in_bytes, file_size_used_in_bytes,   
inserted_row_count, deleted_row_count, lower_bound_tsn, upper_bound_tsn   
from sys.dm_db_xtp_checkpoint_files  
where state = 1  
order by file_type_desc, upper_bound_tsn  
```  
  
 <span data-ttu-id="70b62-113">Suponha que você encontrou três arquivos de dados que não foram mesclados.</span><span class="sxs-lookup"><span data-stu-id="70b62-113">Assume that you found three data files that have not been merged.</span></span> <span data-ttu-id="70b62-114">Usando o valor de `lower_bound_tsn` do primeiro arquivo de dados e o valor de `upper_bound_tsn` do último arquivo de dados, você poderá emitir o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="70b62-114">Using the `lower_bound_tsn` value of the first data file and the `upper_bound_tsn` of the last data file, you can issue the following command:</span></span>  
  
```sql  
exec sys.sp_xtp_merge_checkpoint_files 'H_DB',  12345, 67890  
```  
  
 <span data-ttu-id="70b62-115">Suponha que os três pares de arquivos delta e de dados tinham 15.836 linhas e 5.279 linhas excluídas cada um.</span><span class="sxs-lookup"><span data-stu-id="70b62-115">Assume that the three data and delta file pairs each had 15,836 rows and 5,279 deleted rows.</span></span> <span data-ttu-id="70b62-116">Após a mesclagem, o novo arquivo de dados tem 31.872 linhas e 0 linhas excluídas.</span><span class="sxs-lookup"><span data-stu-id="70b62-116">After the merge, the new data file has 31,872 rows and 0 deleted rows.</span></span> <span data-ttu-id="70b62-117">O tamanho do novo arquivo de dados pode ser muito maior que o tamanho inicialmente alocado de 128 MB.</span><span class="sxs-lookup"><span data-stu-id="70b62-117">The size of the new data file can be much larger than the initially allocated size of 128MB.</span></span> <span data-ttu-id="70b62-118">Isso acontece porque a mesclagem manual substitui a política de mesclagem e força a mesclagem dos arquivos solicitados.</span><span class="sxs-lookup"><span data-stu-id="70b62-118">This is because manual merge overrides the merge policy and forces the merge of the requested files.</span></span>  
  
 <span data-ttu-id="70b62-119">A [transição de estado do blog de arquivos de ponto de verificação em bancos de dados com tabelas com otimização de memória](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) descreve a transição de estado de pares de arquivos Delta e de entrada para a coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="70b62-119">The blog [State Transition of Checkpoint Files in Databases with Memory-Optimized Tables](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) describes state transition of data and delta file pairs from inception to garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b62-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="70b62-120">See Also</span></span>  
 [<span data-ttu-id="70b62-121">Criando e gerenciando armazenamento para objetos com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="70b62-121">Creating and Managing Storage for Memory-Optimized Objects</span></span>](../relational-databases/in-memory-oltp/creating-and-managing-storage-for-memory-optimized-objects.md)  
  
