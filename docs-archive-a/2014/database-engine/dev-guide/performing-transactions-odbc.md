---
title: Executando transações (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, transactions
- transactions [ODBC]
- ODBC, transactions
ms.assetid: f431191a-5762-4f0b-85bb-ac99aff29724
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8abc09c9395225dd653a072fd6c25dadce0849b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685264"
---
# <a name="performing-transactions-odbc"></a><span data-ttu-id="b1706-102">Executando transações (ODBC)</span><span class="sxs-lookup"><span data-stu-id="b1706-102">Performing Transactions (ODBC)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b1706-103">e o driver OBDC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client oferecem suporte a funções de gerenciamento de transação de ODBC API.</span><span class="sxs-lookup"><span data-stu-id="b1706-103">and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver support the ODBC API transaction management functions.</span></span> <span data-ttu-id="b1706-104">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] oferece suporte completo a transações locais em um servidor específico.</span><span class="sxs-lookup"><span data-stu-id="b1706-104">[!INCLUDE[msCoName](../../includes/msconame-md.md)] offers full support for local transactions on an individual server.</span></span> <span data-ttu-id="b1706-105">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client usa esses recursos para dar suporte às funções de ODBC API que gerenciam transações.</span><span class="sxs-lookup"><span data-stu-id="b1706-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses these features to support the ODBC API functions that manage transactions.</span></span>  
  
 <span data-ttu-id="b1706-106">Com o uso do MS DTC (Microsoft Distributed Transaction Coordinator), o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client pode participar de transações distribuídas em vários servidores.</span><span class="sxs-lookup"><span data-stu-id="b1706-106">Through the use of the Microsoft Distributed Transaction Coordinator (MS DTC), the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver can participate in distributed transactions spanning multiple servers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1706-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b1706-107">In This Section</span></span>  
  
-   [<span data-ttu-id="b1706-108">Transações em ODBC</span><span class="sxs-lookup"><span data-stu-id="b1706-108">Transactions in ODBC</span></span>](../../relational-databases/native-client/odbc/performing-transactions-in-odbc.md)  
  
-   [<span data-ttu-id="b1706-109">Executando transações distribuídas</span><span class="sxs-lookup"><span data-stu-id="b1706-109">Performing Distributed Transactions</span></span>](../../relational-databases/native-client-ole-db-transactions/transactions.md)  
  
  
