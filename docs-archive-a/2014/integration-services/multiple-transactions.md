---
title: Transações múltiplas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], multiple
- multiple transactions
ms.assetid: c3664a94-be89-40c0-a3a0-84b74a7fedbe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ff909c92a23c965047edc0fcf278e17e4c76d94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574101"
---
# <a name="multiple-transactions"></a><span data-ttu-id="8879a-102">Transações múltiplas</span><span class="sxs-lookup"><span data-stu-id="8879a-102">Multiple Transactions</span></span>
  <span data-ttu-id="8879a-103">É possível que um pacote inclua transações não relacionadas em um pacote [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8879a-103">It is possible for a package to include unrelated transactions in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="8879a-104">A qualquer hora que um contêiner no meio de uma hierarquia de contêineres aninhada não oferecer suporte a transações, os contêineres acima ou abaixo da mesma na hierarquia começa a separar as transações, se elas estiverem configuradas para oferecem suporte às transações.</span><span class="sxs-lookup"><span data-stu-id="8879a-104">Any time a container in the middle of a nested container hierarchy does not support transactions, the containers above or below it in the hierarchy start separate transactions if they are configured to support transactions.</span></span> <span data-ttu-id="8879a-105">As transações confirmam ou revertem na ordem da tarefa interna na hierarquia de contêineres aninhados para o pacote.</span><span class="sxs-lookup"><span data-stu-id="8879a-105">The transactions commit or roll back in order from the innermost task in the nested container hierarchy to the package.</span></span> <span data-ttu-id="8879a-106">Entretanto, depois que a transação interna é confirmada, ela não será revertida se uma transação externa for anulada.</span><span class="sxs-lookup"><span data-stu-id="8879a-106">However, after the inner transaction commits, it does not roll back if an outer transaction is aborted.</span></span>

## <a name="illustration-of-multiple-transactions"></a><span data-ttu-id="8879a-107">Ilustração de várias transações</span><span class="sxs-lookup"><span data-stu-id="8879a-107">Illustration of Multiple Transactions</span></span>
 <span data-ttu-id="8879a-108">Por exemplo, um pacote tem um contêiner de Sequência que mantém dois contêineres Loop Foreach, e cada contêiner inclui duas tarefas Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="8879a-108">For example, a package has a Sequence container that holds two Foreach Loop containers, and each container include two Execute SQL tasks.</span></span> <span data-ttu-id="8879a-109">O contêiner Sequência oferece suporte a transações, os contêineres Loop Foreach não oferecem e as tarefas Executar SQL oferecem.</span><span class="sxs-lookup"><span data-stu-id="8879a-109">The Sequence container supports transactions, the Foreach Loop containers do not, and the Execute SQL tasks do.</span></span> <span data-ttu-id="8879a-110">Nesse exemplo, cada tarefa Executar SQL começaria sua própria transação e não reverteria se a transação da tarefa de Sequência fosse cancelada.</span><span class="sxs-lookup"><span data-stu-id="8879a-110">In this example, each Execute SQL task would start its own transaction and would not roll back if the transaction on the Sequence task was aborted.</span></span>

 <span data-ttu-id="8879a-111">As propriedades TransactionOption do contêiner Sequência, do contêiner Loop Foreach e das tarefas Executar SQL são definidas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="8879a-111">The TransactionOption properties of the Sequence container, Foreach Loop container and the Execute SQL tasks are set as follows:</span></span>

-   <span data-ttu-id="8879a-112">As propriedades TransactionOption do contêiner de Sequência está definida como **Obrigatória**.</span><span class="sxs-lookup"><span data-stu-id="8879a-112">The TransactionOption property of the Sequence container is set to **Required**.</span></span>

-   <span data-ttu-id="8879a-113">As propriedades TransactionOption dos contêineres Loop Foreach são definidas como **NotSupported**.</span><span class="sxs-lookup"><span data-stu-id="8879a-113">The TransactionOption properties of the Foreach Loop containers are set to **NotSupported**.</span></span>

-   <span data-ttu-id="8879a-114">As propriedades TransactionOption das tarefas Executar SQL são definidas como **Obrigatória**.</span><span class="sxs-lookup"><span data-stu-id="8879a-114">The TransactionOption properties of the Execute SQL tasks are set to **Required**.</span></span>

 <span data-ttu-id="8879a-115">O diagrama a seguir mostra as cinco transações não relacionadas no pacote.</span><span class="sxs-lookup"><span data-stu-id="8879a-115">The following diagram shows the five unrelated transactions in the package.</span></span> <span data-ttu-id="8879a-116">Uma transação é iniciada pelo contêiner de Sequência e quatro transações são iniciadas pelas tarefas Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="8879a-116">One transaction is started by the Sequence container and four transactions are started by the Execute SQL tasks.</span></span>

 <span data-ttu-id="8879a-117">![Implementação de várias transações](media/mw-dts-trans2.gif "Implementação de várias transações")</span><span class="sxs-lookup"><span data-stu-id="8879a-117">![Implementation of multiple transactions](media/mw-dts-trans2.gif "Implementation of multiple transactions")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="8879a-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8879a-118">Related Tasks</span></span>
 [<span data-ttu-id="8879a-119">Configurar um pacote para usar transações</span><span class="sxs-lookup"><span data-stu-id="8879a-119">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)


