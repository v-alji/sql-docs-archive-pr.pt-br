---
title: Transações herdadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], inherited
- child packages
- inherited transactions [Integration Services]
ms.assetid: 90db5564-d41e-4cfe-8c9e-4e68d41eff1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ecb480420fe9f2492c29fad37ee3cc6e6501e3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574196"
---
# <a name="inherited-transactions"></a><span data-ttu-id="7f0e1-102">Transações herdadas</span><span class="sxs-lookup"><span data-stu-id="7f0e1-102">Inherited Transactions</span></span>
  <span data-ttu-id="7f0e1-103">Um pacote pode executar outro pacote usando a tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-103">A package can run another package by using the Execute Package task.</span></span> <span data-ttu-id="7f0e1-104">O pacote filho, que é o pacote executado pela tarefa Executar Pacote, pode criar sua própria transação de pacote ou pode herdar a transação do pacote pai.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-104">The child package, which is the package run by the Execute Package task, may create its own package transaction, or it may inherit the parent package transaction.</span></span>  
  
 <span data-ttu-id="7f0e1-105">Um pacote filho herda a transação do pacote pai se ambos os itens a seguir forem verdadeiros:</span><span class="sxs-lookup"><span data-stu-id="7f0e1-105">A child package inherits the parent package transaction if both of the following are true:</span></span>  
  
-   <span data-ttu-id="7f0e1-106">O pacote é invocado por uma tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-106">The package is invoked by an Execute Package task.</span></span>  
  
-   <span data-ttu-id="7f0e1-107">A tarefa Executar Pacote que invoca o pacote também tenha unido a transação de pacote pai.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-107">The Execute Package task that invoked the package also joined the parent package transaction.</span></span>  
  
 <span data-ttu-id="7f0e1-108">Os contêineres e tarefas no pacote filho não podem unir-se à transação de pacote pai, a menos que o próprio pacote filho seja unido na transação.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-108">Containers and tasks in the child package cannot join the parent package transaction unless the child package itself joins the transaction.</span></span>  
  
## <a name="illustration-of-package-transactions"></a><span data-ttu-id="7f0e1-109">Ilustração de transações de pacotes</span><span class="sxs-lookup"><span data-stu-id="7f0e1-109">Illustration of Package Transactions</span></span>  
 <span data-ttu-id="7f0e1-110">No diagrama a seguir, há três pacotes que usam transações.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-110">In the following diagram, there are three packages that all use transactions.</span></span> <span data-ttu-id="7f0e1-111">Cada pacote contém múltiplas tarefas.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-111">Each package contains multiple tasks.</span></span> <span data-ttu-id="7f0e1-112">Para enfatizar o comportamento das transações, só serão mostradas as tarefas Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-112">To emphasize the behavior of the transactions, only the Execute Package tasks are shown.</span></span> <span data-ttu-id="7f0e1-113">O pacote A executa os pacotes B e C. Por sua vez, o pacote B executa os pacotes D e E, e o pacote C executa o pacote F.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-113">Package A runs packages B and C. In turn, package B runs packages D and E, and package C runs package F.</span></span>  
  
 <span data-ttu-id="7f0e1-114">Os pacotes e tarefas têm os seguintes atributos de transação:</span><span class="sxs-lookup"><span data-stu-id="7f0e1-114">Packages and tasks have the following transaction attributes:</span></span>  
  
-   <span data-ttu-id="7f0e1-115">**TransactionOption** é definida como **Required** nos pacotes A e C</span><span class="sxs-lookup"><span data-stu-id="7f0e1-115">**TransactionOption** is set to **Required** on packages A and C</span></span>  
  
-   <span data-ttu-id="7f0e1-116">**TransactionOption** é definida como **Com Suporte** nos pacotes B e D, e nas tarefas Executar Pacote B, Executar Pacote C e Executar Pacote F.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-116">**TransactionOption** is set to **Supported** on packages B and D, and on the tasks Execute Package B, Execute Package D, and Execute Package F.</span></span>  
  
-   <span data-ttu-id="7f0e1-117">**TransactionOption** é definida como **NotSupported** no pacote E e nas tarefas Executar Pacote C e Executar Pacote E.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-117">**TransactionOption** is set to **NotSupported** on package E, and on the tasks Execute Package C and Execute Package E.</span></span>  
  
 <span data-ttu-id="7f0e1-118">![Fluxo de transações herdadas](media/mw-dts-executepack.gif "Fluxo de transações herdadas")</span><span class="sxs-lookup"><span data-stu-id="7f0e1-118">![Flow of inherited transactions](media/mw-dts-executepack.gif "Flow of inherited transactions")</span></span>  
  
 <span data-ttu-id="7f0e1-119">Só pacotes B, D e F podem herdar transações de seus pacotes pai.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-119">Only packages B, D, and F can inherit transactions from their parent packages.</span></span>  
  
 <span data-ttu-id="7f0e1-120">Pacotes B e D herdam a transação que foi iniciada pelo pacote A.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-120">Packages B and D inherit the transaction that was started by package A.</span></span>  
  
 <span data-ttu-id="7f0e1-121">Pacote F herda a transação que foi iniciada pelo pacote C.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-121">Package F inherits the transaction that was started by package C.</span></span>  
  
 <span data-ttu-id="7f0e1-122">Pacotes A e C controlam suas próprias transações.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-122">Packages A and C control their own transactions.</span></span>  
  
 <span data-ttu-id="7f0e1-123">Pacote E não usa transações.</span><span class="sxs-lookup"><span data-stu-id="7f0e1-123">Package E does not use transactions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7f0e1-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="7f0e1-124">Related Tasks</span></span>  
 [<span data-ttu-id="7f0e1-125">Configurar um pacote para usar transações</span><span class="sxs-lookup"><span data-stu-id="7f0e1-125">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)  
  
  
