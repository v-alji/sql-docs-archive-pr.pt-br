---
title: Executar lógica de negócios durante sincronizações de mesclagem | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- custom error resolution [SQL Server replication]
- custom change handling [SQL Server replication]
- errors [SQL Server replication], business logic handlers
- merge replication business logic handlers [SQL Server replication]
- conflict resolution [SQL Server replication], merge replication
- business logic handlers [SQL Server replication]
ms.assetid: 9d4da2ef-c17f-4a31-a1f6-5c3b7ca85f71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1e082cbbb46ceae712cd39925c28fe89988a3793
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568508"
---
# <a name="execute-business-logic-during-merge-synchronization"></a><span data-ttu-id="d5699-102">Executar lógica de negócios durante sincronizações de mesclagem</span><span class="sxs-lookup"><span data-stu-id="d5699-102">Execute Business Logic During Merge Synchronization</span></span>
  <span data-ttu-id="d5699-103">A estrutura do manipulador de lógica comercial permite que você grave um assembly de código gerenciado que é chamado durante o processo de sincronização de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="d5699-103">The business logic handler framework allows you to write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="d5699-104">O assembly inclui lógica comercial que pode responder a uma série de condições durante a sincronização: alterações de dados, conflitos e erros.</span><span class="sxs-lookup"><span data-stu-id="d5699-104">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="d5699-105">A estrutura do manipulador de lógica comercial oferece um modelo de programação simples e os dados que o processo de mesclagem oferece ao seu assembly estão na forma de um conjunto de dados ADO.NET, portanto você pode aproveitar do conhecimento de ADO.NET ao invés de aprender uma interface proprietária.</span><span class="sxs-lookup"><span data-stu-id="d5699-105">The business logic handler framework provides a simple programming model, and the data that the merge process provides to your assembly is in the form of an ADO.NET data set, so you can leverage knowledge of ADO.NET rather than learning a proprietary interface.</span></span> <span data-ttu-id="d5699-106">Para obter mais informações sobre como programar manipuladores de lógica comercial, consulte:</span><span class="sxs-lookup"><span data-stu-id="d5699-106">For more information on programming business logic handlers, see:</span></span>  
  
-   <span data-ttu-id="d5699-107">A referência da interface de programas aplicativos (API): <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span><span class="sxs-lookup"><span data-stu-id="d5699-107">The application programming interface (API) reference: <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span></span>  
  
-   <span data-ttu-id="d5699-108">Instruções sobre como implementar um manipulador de lógica de negócios: [Implementar um manipulador de lógica de negócios para um artigo de mesclagem](../implement-a-business-logic-handler-for-a-merge-article.md)</span><span class="sxs-lookup"><span data-stu-id="d5699-108">Instructions on how to implement a business logic handler: [Implement a Business Logic Handler for a Merge Article](../implement-a-business-logic-handler-for-a-merge-article.md)</span></span>  
  
## <a name="uses-for-business-logic-handlers"></a><span data-ttu-id="d5699-109">Usos para manipuladores de lógica comercial</span><span class="sxs-lookup"><span data-stu-id="d5699-109">Uses for Business Logic Handlers</span></span>  
 <span data-ttu-id="d5699-110">O processo de sincronização de mesclagem pode chamar manipuladores de lógica comercial para executar:</span><span class="sxs-lookup"><span data-stu-id="d5699-110">The merge synchronization process can invoke business logic handlers to perform:</span></span>  
  
-   <span data-ttu-id="d5699-111">Manipulação de alteração personalizada</span><span class="sxs-lookup"><span data-stu-id="d5699-111">Custom change handling</span></span>  
  
-   <span data-ttu-id="d5699-112">Resolução de conflito personalizada</span><span class="sxs-lookup"><span data-stu-id="d5699-112">Custom conflict resolution</span></span>  
  
-   <span data-ttu-id="d5699-113">Resolução de erro personalizada</span><span class="sxs-lookup"><span data-stu-id="d5699-113">Custom error resolution</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5699-114">O manipulador de lógica de negócios que você especificar será executado para cada linha que for sincronizada.</span><span class="sxs-lookup"><span data-stu-id="d5699-114">The business logic handler you specify is executed for every row that is synchronized.</span></span> <span data-ttu-id="d5699-115">A lógica complexa e as chamadas para outros aplicativos ou serviços de rede podem comprometer o desempenho.</span><span class="sxs-lookup"><span data-stu-id="d5699-115">Complex logic and calls to other applications or network services can impact performance.</span></span>  
  
### <a name="custom-change-handling"></a><span data-ttu-id="d5699-116">Manipulação de alteração personalizada</span><span class="sxs-lookup"><span data-stu-id="d5699-116">Custom Change Handling</span></span>  
 <span data-ttu-id="d5699-117">O manipulador de lógica comercial pode ser invocado durante o processamento de alterações de dados não conflitantes e pode executar uma destas três ações:</span><span class="sxs-lookup"><span data-stu-id="d5699-117">The business logic handler can be invoked during the processing of non-conflicting data changes and can perform one of three actions:</span></span>  
  
-   <span data-ttu-id="d5699-118">Rejeite os dados</span><span class="sxs-lookup"><span data-stu-id="d5699-118">Reject the data</span></span>  
  
     <span data-ttu-id="d5699-119">Isso é útil para aplicativos que não querem alterações propagadas para ou de um determinado Assinante.</span><span class="sxs-lookup"><span data-stu-id="d5699-119">This is useful for applications that do not want changes propagated to or from a given Subscriber.</span></span> <span data-ttu-id="d5699-120">Por exemplo, um administrador poderá retirar inserções que não pertencem à partição do Assinante ou possivelmente rejeitar exclusões executadas em um Assinante.</span><span class="sxs-lookup"><span data-stu-id="d5699-120">For example, an administrator could filter out inserts that do not belong in the Subscriber's partition, or possibly reject deletes performed at a Subscriber.</span></span> <span data-ttu-id="d5699-121">Como outro exemplo, um aplicativo poderá rejeitar uma ordem inserida em um Assinante porque o inventário não está mais disponível.</span><span class="sxs-lookup"><span data-stu-id="d5699-121">As another example, an application could reject an order entered at a Subscriber because the inventory is no longer available.</span></span>  
  
-   <span data-ttu-id="d5699-122">Aceite os dados</span><span class="sxs-lookup"><span data-stu-id="d5699-122">Accept the data</span></span>  
  
     <span data-ttu-id="d5699-123">Isto é útil para aplicativos nos quais é necessário rever alterações de dados feitas no Publicador ou Assinante antes de permitir a sua propagação.</span><span class="sxs-lookup"><span data-stu-id="d5699-123">This is useful for applications in which it is necessary to review data changes made at either the Publisher or Subscriber before allowing them to be propagated.</span></span> <span data-ttu-id="d5699-124">Por exemplo, um aplicativo da camada intermediária poderá examinar novas ordens provenientes do campo e integrá-las com um processo de fluxo de trabalho de aquisição na camada intermediária.</span><span class="sxs-lookup"><span data-stu-id="d5699-124">For example, a mid-tier application could examine new orders coming in from the field and integrate with a procurement workflow process in the mid-tier.</span></span>  
  
-   <span data-ttu-id="d5699-125">Aplique dados personalizados</span><span class="sxs-lookup"><span data-stu-id="d5699-125">Apply custom data</span></span>  
  
     <span data-ttu-id="d5699-126">Isto é útil para aplicativos que precisam substituir valores de dados ou operações específicos.</span><span class="sxs-lookup"><span data-stu-id="d5699-126">This is useful for applications that need to override specific data values or operations.</span></span> <span data-ttu-id="d5699-127">Por exemplo, uma aplicativo poderá transformar a exclusão de uma linha em uma atualização especial que define uma coluna de **status** na linha a um valor de "excluído" e então rastreia a identidade do cliente executando a exclusão.</span><span class="sxs-lookup"><span data-stu-id="d5699-127">For example, an application could transform a row delete into a special update that sets a **status** column in the row to a value of "deleted" and then tracks the identity of the client performing the delete.</span></span> <span data-ttu-id="d5699-128">Isto poderá ser útil para fins de auditoria ou de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d5699-128">This might be useful for auditing or workflow purposes.</span></span>  
  
### <a name="custom-conflict-resolution"></a><span data-ttu-id="d5699-129">Resolução de conflito personalizada</span><span class="sxs-lookup"><span data-stu-id="d5699-129">Custom Conflict Resolution</span></span>  
 <span data-ttu-id="d5699-130">A replicação de mesclagem fornece detecção e solução de conflitos, permitindo que você aceite uma estratégia de resolução padrão ou escolha uma resolução personalizada para conflitos.</span><span class="sxs-lookup"><span data-stu-id="d5699-130">Merge replication provides conflict detection and resolution, allowing you to accept a default resolution strategy or choose custom resolution for conflicts.</span></span> <span data-ttu-id="d5699-131">Para obter mais informações, consulte [Replicação de mesclagem avançada – detecção e resolução de conflito](advanced-merge-replication-conflict-detection-and-resolution.md).</span><span class="sxs-lookup"><span data-stu-id="d5699-131">For more information, see [Advanced Merge Replication Conflict Detection and Resolution](advanced-merge-replication-conflict-detection-and-resolution.md).</span></span> <span data-ttu-id="d5699-132">O manipulador de lógica comercial pode ser chamado durante o processamento de alterações de dados conflitantes e pode executar uma destas duas ações:</span><span class="sxs-lookup"><span data-stu-id="d5699-132">The business logic handler can be invoked during the processing of conflicting data changes and can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="d5699-133">Aceite resolução padrão</span><span class="sxs-lookup"><span data-stu-id="d5699-133">Accept default resolution</span></span>  
  
     <span data-ttu-id="d5699-134">Isso é útil para aplicativos que podem precisar analisar o conflito, executar ações adicionais e possivelmente registrar uma mensagem de log de conflito personalizada.</span><span class="sxs-lookup"><span data-stu-id="d5699-134">This is useful for applications that might need to review the conflict, perform additional actions, and possibly log a custom conflict log message.</span></span>  
  
-   <span data-ttu-id="d5699-135">Execute resolução personalizada</span><span class="sxs-lookup"><span data-stu-id="d5699-135">Perform custom resolution</span></span>  
  
     <span data-ttu-id="d5699-136">Isso é útil para aplicativos que podem precisar selecionar valores de dados que são específicos à sua lógica comercial e fornecer o processo de sincronização com este conjunto de dados personalizados.</span><span class="sxs-lookup"><span data-stu-id="d5699-136">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="d5699-137">Por exemplo, um aplicativo poderá fornecer uma nova versão da linha vencedora combinando valores dos conjuntos de dados do Publicador e Assinante.</span><span class="sxs-lookup"><span data-stu-id="d5699-137">For example, an application could provide a new version of the winning row by combining values from the Publisher and Subscriber data sets.</span></span>  
  
### <a name="custom-error-resolution"></a><span data-ttu-id="d5699-138">Resolução de erro personalizada</span><span class="sxs-lookup"><span data-stu-id="d5699-138">Custom Error Resolution</span></span>  
 <span data-ttu-id="d5699-139">A lógica personalizada pode ser chamada durante a propagação de alterações que resultam em erros.</span><span class="sxs-lookup"><span data-stu-id="d5699-139">Custom logic can be invoked during the propagation of changes that result in errors.</span></span> <span data-ttu-id="d5699-140">A lógica pode executar uma dessas duas ações:</span><span class="sxs-lookup"><span data-stu-id="d5699-140">The logic can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="d5699-141">Aceite resolução de erro padrão</span><span class="sxs-lookup"><span data-stu-id="d5699-141">Accept default error resolution</span></span>  
  
     <span data-ttu-id="d5699-142">Isso é útil para aplicativos precisam analisar o erro e executar outras ações e, possivelmente, registrar uma mensagem de log de erros personalizada.</span><span class="sxs-lookup"><span data-stu-id="d5699-142">This is useful for applications that might need to review the error and perform additional action and possibly log a custom error log message.</span></span>  
  
-   <span data-ttu-id="d5699-143">Aceite resolução de erro personalizada</span><span class="sxs-lookup"><span data-stu-id="d5699-143">Accept custom error resolution</span></span>  
  
     <span data-ttu-id="d5699-144">Isso é útil para aplicativos que podem precisar selecionar valores de dados que são específicos à sua lógica comercial e fornecer o processo de sincronização com este conjunto de dados personalizados.</span><span class="sxs-lookup"><span data-stu-id="d5699-144">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="d5699-145">Por exemplo, se o processo de replicação encontrar uma violação de chave duplicada, o manipulador de lógica comercial poderá fornecer uma nova versão da alteração de dados em que a chave não será mais conflitante.</span><span class="sxs-lookup"><span data-stu-id="d5699-145">For example, if the replication process encounters a duplicate key violation, the business logic handler could provide a new version of the data change in which the key will no longer conflict.</span></span> <span data-ttu-id="d5699-146">As alterações feitas no Publicador e Assinante poderão então persistir no banco de dados e o processo de replicação não terá que compensar pela inserção falha com uma exclusão.</span><span class="sxs-lookup"><span data-stu-id="d5699-146">Changes made at the Publisher and Subscriber can then persist in the database, and the replication process doesn't have to compensate for the failed insert with a delete.</span></span>  
  
## <a name="deployment-scenarios-for-business-logic-handlers"></a><span data-ttu-id="d5699-147">Cenários de Implantação para manipuladores de lógica comercial</span><span class="sxs-lookup"><span data-stu-id="d5699-147">Deployment Scenarios for Business Logic Handlers</span></span>  
 <span data-ttu-id="d5699-148">Manipuladores de lógica comercial podem ser implantados no:</span><span class="sxs-lookup"><span data-stu-id="d5699-148">Business logic handlers can be deployed at:</span></span>  
  
-   <span data-ttu-id="d5699-149">O Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d5699-149">The Distributor.</span></span> <span data-ttu-id="d5699-150">Use uma assinatura push de forma que a lógica comercial seja executada no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d5699-150">Use a push subscription so that business logic is executed at the Distributor.</span></span>  
  
-   <span data-ttu-id="d5699-151">Assinante.</span><span class="sxs-lookup"><span data-stu-id="d5699-151">The Subscriber.</span></span> <span data-ttu-id="d5699-152">Use uma assinatura pull de forma que a lógica comercial seja executada no Assinante.</span><span class="sxs-lookup"><span data-stu-id="d5699-152">Use a pull subscription so that business logic is executed at the Subscriber.</span></span>  
  
-   <span data-ttu-id="d5699-153">Um servidor IIS (Serviços de Informações da Internet) se a sincronização da Web for usada.</span><span class="sxs-lookup"><span data-stu-id="d5699-153">An Internet Information Services (IIS) server if Web synchronization is used.</span></span> <span data-ttu-id="d5699-154">Use uma assinatura pull sincronizada com a sincronização da Web e o manipulador de lógica comercial executará no Servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="d5699-154">Use a pull subscription synchronized with Web synchronization, and the business logic handler will execute at the IIS Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5699-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d5699-155">See Also</span></span>  
 <span data-ttu-id="d5699-156">[Replicação de mesclagem](merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d5699-156">[Merge Replication](merge-replication.md) </span></span>  
 <span data-ttu-id="d5699-157">[Subscribe to Publications](../subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="d5699-157">[Subscribe to Publications](../subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="d5699-158">[Sincronizar dados](../synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="d5699-158">[Synchronize Data](../synchronize-data.md) </span></span>  
 [<span data-ttu-id="d5699-159">Sincronização da Web para replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="d5699-159">Web Synchronization for Merge Replication</span></span>](../web-synchronization-for-merge-replication.md)  
  
  
