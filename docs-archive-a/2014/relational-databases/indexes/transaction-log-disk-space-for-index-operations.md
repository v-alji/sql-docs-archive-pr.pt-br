---
title: Espaço em disco do log de transações para operações de índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index disk space [SQL Server]
- space [SQL Server], indexes
- transaction logs [SQL Server], disk space
- disk space [SQL Server], transaction logs
- space [SQL Server], transaction logs
ms.assetid: 4f8a4922-4507-4072-be67-c690528d5c3b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c34c9ff7a9494496d6c60d5920184c0ce86131d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684725"
---
# <a name="transaction-log-disk-space-for-index-operations"></a><span data-ttu-id="4243d-102">Espaço em disco de log de transações para operações de índice</span><span class="sxs-lookup"><span data-stu-id="4243d-102">Transaction Log Disk Space for Index Operations</span></span>
  <span data-ttu-id="4243d-103">Operações de índice de larga escala podem gerar grandes carregamentos de dados que podem fazer com que o log da transação seja preenchido rapidamente.</span><span class="sxs-lookup"><span data-stu-id="4243d-103">Large-scale index operations can generate large data loads that can cause the transaction log to fill quickly.</span></span> <span data-ttu-id="4243d-104">Para assegurar a reversão da operação de índice, o log da transação não pode ser truncado até que a operação de índice se complete. Durante a operação, no entanto, poderá ser feito backup do log.</span><span class="sxs-lookup"><span data-stu-id="4243d-104">To make sure that the index operation can be rolled back, the transaction log cannot be truncated until the index operation has completed; however, the log can be backed up during the index operation.</span></span> <span data-ttu-id="4243d-105">Portanto, o log de transações deve ter espaço suficiente para armazenar as transações da operação de índice e todas as transações simultâneas de usuário pelo período da operação de índice.</span><span class="sxs-lookup"><span data-stu-id="4243d-105">Therefore, the transaction log must have sufficient room to store both the index operation transactions and any concurrent user transactions for the duration of the index operation.</span></span> <span data-ttu-id="4243d-106">Isso é verdade para operações de índice offline e online.</span><span class="sxs-lookup"><span data-stu-id="4243d-106">This is true for both offline and online index operations.</span></span> <span data-ttu-id="4243d-107">Como as tabelas subjacentes não podem ser acessadas durante a operação de índice offline, pode haver poucas transações de usuário e o log pode não crescer na mesma proporção.</span><span class="sxs-lookup"><span data-stu-id="4243d-107">Because the underlying tables cannot be accessed during an offline index operation, there may be few user transactions and the log may not grow as quickly.</span></span> <span data-ttu-id="4243d-108">As operações de índice online não impedem atividades simultâneas de usuário. Por isso, as operações de índice online de larga escala, combinadas com transações simultâneas significativas de usuário, podem causar o crescimento contínuo do log de transações sem opção para truncar o log.</span><span class="sxs-lookup"><span data-stu-id="4243d-108">Online index operations do not prevent concurrent user activity, therefore, large-scale online index operations combined with significant concurrent user transactions can cause continuous growth of the transaction log without an option to truncate the log.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="4243d-109">Recomendações</span><span class="sxs-lookup"><span data-stu-id="4243d-109">Recommendations</span></span>  
 <span data-ttu-id="4243d-110">Durante a execução de operações de índice de grande escala, considere estas recomendações:</span><span class="sxs-lookup"><span data-stu-id="4243d-110">When you run large-scale index operations, consider the following recommendations:</span></span>  
  
1.  <span data-ttu-id="4243d-111">Verifique se foi feito o backup do log de transações e se ele foi truncado antes de executar as operações de índice online de grande escala, e se o log tem espaço suficiente para armazenar o índice projetado e as transações do usuário.</span><span class="sxs-lookup"><span data-stu-id="4243d-111">Make sure the transaction log has been backed up and truncated before running large-scale index operations online, and that the log has sufficient space to store the projected index and user transactions.</span></span>  
  
2.  <span data-ttu-id="4243d-112">Considere definir a opção SORT_IN_TEMPDB como ON para a operação de índice.</span><span class="sxs-lookup"><span data-stu-id="4243d-112">Consider setting the SORT_IN_TEMPDB option to ON for the index operation.</span></span> <span data-ttu-id="4243d-113">Isso separará as transações de índice das transações de usuário simultâneas.</span><span class="sxs-lookup"><span data-stu-id="4243d-113">This separates the index transactions from the concurrent user transactions.</span></span> <span data-ttu-id="4243d-114">As transações de índice serão armazenadas no log de transações **tempdb** , e as transações de usuário simultâneas serão armazenadas no log de transações do banco de dados de usuário.</span><span class="sxs-lookup"><span data-stu-id="4243d-114">The index transactions will be stored in the **tempdb** transaction log, and the concurrent user transactions will be stored in the transaction log of the user database.</span></span> <span data-ttu-id="4243d-115">Isso permitirá que o log de transações do banco de dados de usuário seja truncado durante a operação de índice, se necessário.</span><span class="sxs-lookup"><span data-stu-id="4243d-115">This allows for the transaction log of the user database to be truncated during the index operation if it is required.</span></span> <span data-ttu-id="4243d-116">Além disso, se o log **tempdb** não estiver no mesmo disco do log de banco de dados de usuário, os dois logs não estarão competindo pelo mesmo espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="4243d-116">Additionally, if the **tempdb** log is not on the same disk as the user database log, the two logs are not competing for the same disk space.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4243d-117">Confirme se o banco de dados **tempdb** e o log de transações têm espaço em disco suficiente para controlar a operação de índice.</span><span class="sxs-lookup"><span data-stu-id="4243d-117">Verify that the **tempdb** database and transaction log have sufficient disk space to handle the index operation.</span></span> <span data-ttu-id="4243d-118">O log de transações **tempdb** não pode ser truncado até que a operação de índice seja concluída.</span><span class="sxs-lookup"><span data-stu-id="4243d-118">The **tempdb** transaction log cannot be truncated until the index operation is completed.</span></span>  
  
3.  <span data-ttu-id="4243d-119">Use um modelo de recuperação de banco de dados que permita o registro mínimo da operação de índice.</span><span class="sxs-lookup"><span data-stu-id="4243d-119">Use a database recovery model that allows for minimal logging of the index operation.</span></span> <span data-ttu-id="4243d-120">Isso poderá reduzir o tamanho do log e impedir que o log preencha o espaço de log.</span><span class="sxs-lookup"><span data-stu-id="4243d-120">This may reduce the size of the log and prevent the log from filling the log space.</span></span>  
  
4.  <span data-ttu-id="4243d-121">Não execute a operação de índice online em uma transação explícita.</span><span class="sxs-lookup"><span data-stu-id="4243d-121">Do not run the online index operation in an explicit transaction.</span></span> <span data-ttu-id="4243d-122">O log não será truncado até que a transação explícita termine.</span><span class="sxs-lookup"><span data-stu-id="4243d-122">The log will not be truncated until the explicit transaction ends.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="4243d-123">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="4243d-123">Related Content</span></span>  
 [<span data-ttu-id="4243d-124">Requisitos de espaço em disco para operações de DDL de índice</span><span class="sxs-lookup"><span data-stu-id="4243d-124">Disk Space Requirements for Index DDL Operations</span></span>](disk-space-requirements-for-index-ddl-operations.md)  
  
 [<span data-ttu-id="4243d-125">Exemplo de espaço em disco de índice</span><span class="sxs-lookup"><span data-stu-id="4243d-125">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
  
