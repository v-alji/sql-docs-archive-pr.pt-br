---
title: Operação de ponto de verificação para tabelas com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 47975bd5-373f-43cd-946a-da8e8088b610
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 07560ea0bf147198fb759f6769ae1c6d5c68a71e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685153"
---
# <a name="checkpoint-operation-for-memory-optimized-tables"></a><span data-ttu-id="d0b23-102">Operação de ponto de verificação para tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="d0b23-102">Checkpoint Operation for Memory-Optimized Tables</span></span>
  <span data-ttu-id="d0b23-103">Um ponto de verificação precisa ser executado periodicamente para dados com otimização de memória nos arquivos delta e de dados para avançar a parte ativa do log de transações.</span><span class="sxs-lookup"><span data-stu-id="d0b23-103">A checkpoint needs to occur periodically for memory-optimized data in data and delta files to advance the active part of transaction log.</span></span> <span data-ttu-id="d0b23-104">O ponto de verificação permite que as tabelas com otimização de memória sejam restauradas ou recuperadas no último ponto de verificação com êxito e, em seguida, a parte ativa do log de transações é aplicada de modo a atualizar as tabelas com otimização de memória para concluir a recuperação.</span><span class="sxs-lookup"><span data-stu-id="d0b23-104">The checkpoint allows memory-optimized tables to restore or recover to the last successful checkpoint and then the active portion of transaction log is applied to update the memory-optimized tables to complete the recovery.</span></span> <span data-ttu-id="d0b23-105">A operação de ponto de verificação para tabelas baseadas em disco e tabelas com otimização de memória são operações distintas.</span><span class="sxs-lookup"><span data-stu-id="d0b23-105">The checkpoint operation for disk-based tables and memory-optimized tables are distinct operations.</span></span> <span data-ttu-id="d0b23-106">A tabela a seguir descreve cenários diferentes e o comportamento do ponto de verificação para tabelas baseadas em disco e com otimização de memória:</span><span class="sxs-lookup"><span data-stu-id="d0b23-106">The following describes different scenarios and the checkpoint behavior for disk-based and memory-optimized tables:</span></span>  
  
## <a name="manual-checkpoint"></a><span data-ttu-id="d0b23-107">Ponto de verificação manual</span><span class="sxs-lookup"><span data-stu-id="d0b23-107">Manual Checkpoint</span></span>  
 <span data-ttu-id="d0b23-108">Quando você emite um ponto de verificação manual, o ponto de verificação é fechado para tabelas baseadas em disco e com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="d0b23-108">When you issue a manual checkpoint, it closes the checkpoint for both disk-based and memory-optimized tables.</span></span> <span data-ttu-id="d0b23-109">O arquivo de dados ativo é fechado mesmo que possa ser parcialmente preenchido.</span><span class="sxs-lookup"><span data-stu-id="d0b23-109">The active data file is closed even though it may be partially filled.</span></span>  
  
## <a name="automatic-checkpoint"></a><span data-ttu-id="d0b23-110">Ponto de verificação automático</span><span class="sxs-lookup"><span data-stu-id="d0b23-110">Automatic Checkpoint</span></span>  
 <span data-ttu-id="d0b23-111">O ponto de verificação automático é implementado de maneira distinta para tabelas baseadas em disco e tabelas com otimização de memória, pois os dados são mantidos de formas diferentes.</span><span class="sxs-lookup"><span data-stu-id="d0b23-111">Automatic checkpoint is implemented differently for disk-based and memory-optimized tables because of the different ways the data is persisted.</span></span>  
  
 <span data-ttu-id="d0b23-112">Para tabelas baseadas em disco, um ponto de verificação automático é obtido com base na opção de configuração de intervalo de recuperação (para obter mais informações, consulte [Alterar o tempo de recuperação de destino de um banco de dados &#40;SQL Server&#41;](../logs/change-the-target-recovery-time-of-a-database-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="d0b23-112">For disk-based tables, an automatic checkpoint is taken based on the recovery interval configuration option (for more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../logs/change-the-target-recovery-time-of-a-database-sql-server.md)).</span></span>  
  
 <span data-ttu-id="d0b23-113">Para tabelas com otimização de memória, um ponto de verificação automático é obtido quando o arquivo de log de transações se torna maior que 512 MB desde o último ponto de verificação.</span><span class="sxs-lookup"><span data-stu-id="d0b23-113">For memory-optimized tables, an automatic checkpoint is taken when transaction log file becomes bigger than 512 MB since the last checkpoint.</span></span> <span data-ttu-id="d0b23-114">512 MB inclui registros de log de transações para tabelas baseadas em disco e com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="d0b23-114">512 MB includes transaction log records for both disk-based and memory-optimized tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0b23-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d0b23-115">See Also</span></span>  
 [<span data-ttu-id="d0b23-116">Criando e gerenciando armazenamento para objetos com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="d0b23-116">Creating and Managing Storage for Memory-Optimized Objects</span></span>](creating-and-managing-storage-for-memory-optimized-objects.md)  
  
  
