---
title: Transações do Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], transactions
- transactions [Integration Services], about transactions in packages
- tasks [Integration Services], transactions
- transactions [Integration Services]
ms.assetid: 3c78bb26-ddce-4831-a5f8-09d4f4fd53cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5c0ee195bbcb7b9779111add4c1f2349816d5441
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574157"
---
# <a name="integration-services-transactions"></a><span data-ttu-id="fbfb4-102">Transações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="fbfb4-102">Integration Services Transactions</span></span>
  <span data-ttu-id="fbfb4-103">Os pacotes usam transações para associar as ações do banco de dados realizadas pelas tarefas em unidades atômicas e, ao fazer isso, a integridade dos dados é mantida.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-103">Packages use transactions to bind the database actions that tasks perform into atomic units, and by doing this maintain data integrity.</span></span> <span data-ttu-id="fbfb4-104">Todos os tipos de contêineres do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], como os pacotes, o Loop For, o Loop Foreach, os contêineres de sequência e os hosts de tarefa que encapsulam cada tarefa, podem ser configurados para usar transações.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-104">All [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] container types-packages, the For Loop, Foreach Loop, and Sequence containers, and the task hosts that encapsulate each task-can be configured to use transactions.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="fbfb4-105">fornece três opções para configurar transações: **Sem Suporte**, **Há Suporte**e **Necessário**.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-105">provides three options for configuring transactions: **NotSupported**, **Supported**, and **Required**.</span></span>  
  
-   <span data-ttu-id="fbfb4-106">**Necessário** indica que o contêiner inicia uma transação, a menos que uma já tenha sido iniciada por seu contêiner pai.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-106">**Required** indicates that the container starts a transaction, unless one is already started by its parent container.</span></span> <span data-ttu-id="fbfb4-107">Se uma transação já existir, o contêiner se unirá à transação.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-107">If a transaction already exists, the container joins the transaction.</span></span> <span data-ttu-id="fbfb4-108">Por exemplo, se um pacote que não está configurado para dar suporte a transações incluísse um contêiner Sequência que usa a opção **Necessário** , o contêiner iniciaria sua própria transação.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-108">For example, if a package that is not configured to support transactions includes a Sequence container that uses the **Required** option, the Sequence container would start its own transaction.</span></span> <span data-ttu-id="fbfb4-109">Se o pacote fosse configurado para usar a opção **Necessário** , o contêiner Sequência se uniria à transação do pacote.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-109">If the package were configured to use the **Required** option, the Sequence container would join the package transaction.</span></span>  
  
-   <span data-ttu-id="fbfb4-110">**Há Suporte** indica que o contêiner não inicia uma transação, mas se une a qualquer transação iniciada por seu contêiner pai.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-110">**Supported** indicates that the container does not start a transaction, but joins any transaction started by its parent container.</span></span> <span data-ttu-id="fbfb4-111">Por exemplo, se um pacote com quatro tarefas Executar SQL iniciar uma transação e todas as quatro tarefas usarem a opção **Há Suporte** , as atualizações de banco de dados realizadas pelas tarefas Executar SQL serão revertidas se qualquer tarefa falhar.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-111">For example, if a package with four Execute SQL tasks starts a transaction and all four tasks use the **Supported** option, the database updates performed by the Execute SQL tasks are rolled back if any task fails.</span></span> <span data-ttu-id="fbfb4-112">Se o pacote não iniciar uma transação, as quatro tarefas Executar SQL não serão associadas por uma transação e nenhuma atualização de banco de dados, exceto as realizadas pela tarefa que falhou, será revertida.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-112">If the package does not start a transaction, the four Execute SQL tasks are not bound by a transaction, and no database updates except the ones performed by the failed task are rolled back.</span></span>  
  
-   <span data-ttu-id="fbfb4-113">**Sem Suporte** indica que o contêiner não inicia uma transação ou se une a uma transação existente.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-113">**NotSupported** indicates that the container does not start a transaction or join an existing transaction.</span></span> <span data-ttu-id="fbfb4-114">Uma transação iniciada por um contêiner pai não afeta contêineres filhos que foram configurados para não suportar transações.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-114">A transaction started by a parent container does not affect child containers that have been configured to not support transactions.</span></span> <span data-ttu-id="fbfb4-115">Por exemplo, se um pacote for configurado para iniciar uma transação e um contêiner Loop For no pacote usar a opção **Sem Suporte** , nenhuma das tarefas no Loop For poderão ser revertidas se falharem.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-115">For example, if a package is configured to start a transaction and a For Loop container in the package uses the **NotSupported** option, none of the tasks in the For Loop can roll back if they fail.</span></span>  
  
 <span data-ttu-id="fbfb4-116">Você configura transações definindo a propriedade TransactionOption no contêiner.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-116">You configure transactions by setting the TransactionOption property on the container.</span></span> <span data-ttu-id="fbfb4-117">É possível definir essa propriedade na janela **Propriedades** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]ou definir a propriedade programaticamente.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-117">You can set this property by using the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], or you can set the property programmatically.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fbfb4-118">A propriedade `TransactionOption` influencia a aplicação ou não do valor da propriedade `IsolationLevel` solicitada por um contêiner.</span><span class="sxs-lookup"><span data-stu-id="fbfb4-118">The `TransactionOption` property influences whether or not the value of the `IsolationLevel` property requested by a container is applied.</span></span> <span data-ttu-id="fbfb4-119">Para obter mais informações, consulte a descrição da `IsolationLevel` propriedade no tópico [definindo propriedades do pacote](set-package-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fbfb4-119">For more information, see the description of the `IsolationLevel` property in the topic, [Setting Package Properties](set-package-properties.md).</span></span>  
  
### <a name="to-configure-a-package-to-use-transactions"></a><span data-ttu-id="fbfb4-120">Para configurar um pacote para usar transações</span><span class="sxs-lookup"><span data-stu-id="fbfb4-120">To configure a package to use transactions</span></span>  
  
-   [<span data-ttu-id="fbfb4-121">Configurar um pacote para usar transações</span><span class="sxs-lookup"><span data-stu-id="fbfb4-121">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)  
  
## <a name="external-resources"></a><span data-ttu-id="fbfb4-122">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="fbfb4-122">External Resources</span></span>  
  
-   <span data-ttu-id="fbfb4-123">Entrada de blog, [How to Use Transactions in SQL Server Integration Services SSIS (em inglês)](https://go.microsoft.com/fwlink/?LinkId=157783), em www.mssqltips.com</span><span class="sxs-lookup"><span data-stu-id="fbfb4-123">Blog entry, [How to Use Transactions in SQL Server Integration Services SSIS](https://go.microsoft.com/fwlink/?LinkId=157783), on www.mssqltips.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbfb4-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fbfb4-124">See Also</span></span>  
 <span data-ttu-id="fbfb4-125">[Transações herdadas](../../2014/integration-services/inherited-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="fbfb4-125">[Inherited Transactions](../../2014/integration-services/inherited-transactions.md) </span></span>  
 [<span data-ttu-id="fbfb4-126">Transações múltiplas</span><span class="sxs-lookup"><span data-stu-id="fbfb4-126">Multiple Transactions</span></span>](../../2014/integration-services/multiple-transactions.md)  
  
  
