---
title: Especificar como as alterações são propagadas para artigos transacionais | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, propagation methods
ms.assetid: a10c5001-22cc-4667-8f0b-3d0818dca2e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72d377ba89f1d393eab48bd9c918012b0f503f9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680366"
---
# <a name="specify-how-changes-are-propagated-for-transactional-articles"></a><span data-ttu-id="3543b-102">Especificar como as alterações são propagadas para artigos transacionais</span><span class="sxs-lookup"><span data-stu-id="3543b-102">Specify How Changes Are Propagated for Transactional Articles</span></span>
  <span data-ttu-id="3543b-103">A replicação transacional permite que você especifique como as alterações de dados são propagadas do Publicador aos Assinantes.</span><span class="sxs-lookup"><span data-stu-id="3543b-103">Transactional replication allows you to specify how data changes are propagated from the Publisher to Subscribers.</span></span> <span data-ttu-id="3543b-104">Para cada tabela publicada, você pode especificar uma das quatro maneiras em que cada operação (INSERT, UPDATE ou DELETE) deverá ser propagada ao Assinante:</span><span class="sxs-lookup"><span data-stu-id="3543b-104">For each published table, you can specify one of four ways that each operation (INSERT, UPDATE, or DELETE) should be propagated to the Subscriber:</span></span>  
  
-   <span data-ttu-id="3543b-105">Especifique que a replicação transacional deverá gerar script e subsequentemente chamar um procedimento armazenado para propagar alterações aos Assinantes (o padrão).</span><span class="sxs-lookup"><span data-stu-id="3543b-105">Specify that transactional replication should script out and subsequently call a stored procedure to propagate changes to Subscribers (the default).</span></span>  
  
-   <span data-ttu-id="3543b-106">Especifique que a alteração deverá ser propagada usando uma instrução INSERT, UPDATE ou DELETE (o padrão para Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="3543b-106">Specify that the change should be propagated using an INSERT, UPDATE, or DELETE statement (the default for non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers).</span></span>  
  
-   <span data-ttu-id="3543b-107">Especifique que um procedimento armazenado personalizado deverá ser usado.</span><span class="sxs-lookup"><span data-stu-id="3543b-107">Specify that a custom stored procedure should be used.</span></span>  
  
-   <span data-ttu-id="3543b-108">Especifique que esta ação não deverá ser executada em qualquer Assinante.</span><span class="sxs-lookup"><span data-stu-id="3543b-108">Specify that this action should not be performed at any Subscriber.</span></span> <span data-ttu-id="3543b-109">As transações desse tipo não são replicadas.</span><span class="sxs-lookup"><span data-stu-id="3543b-109">Transactions of that type are not replicated.</span></span>  
  
 <span data-ttu-id="3543b-110">Por padrão, a replicação transacional propaga alterações aos Assinantes por um conjunto de procedimentos armazenados instalados em cada Assinante.</span><span class="sxs-lookup"><span data-stu-id="3543b-110">By default, transactional replication propagates changes to Subscribers through a set of stored procedures that are installed on each Subscriber.</span></span> <span data-ttu-id="3543b-111">Quando ocorre uma inserção, atualização ou exclusão em uma tabela no Publicador, a operação é convertida em uma chamada para um procedimento armazenado no Assinante.</span><span class="sxs-lookup"><span data-stu-id="3543b-111">When an insert, update or delete occurs on a table at the Publisher, the operation is translated into a call to a stored procedure at the Subscriber.</span></span> <span data-ttu-id="3543b-112">O procedimento armazenado aceita parâmetros que mapeiam para as colunas da tabela, permitindo que essas colunas sejam alteradas no Assinante.</span><span class="sxs-lookup"><span data-stu-id="3543b-112">The stored procedure accepts parameters that map to the columns in the table, allowing those columns to be changed at the Subscriber.</span></span>  
  
 <span data-ttu-id="3543b-113">Para definir o método de propagação de alterações de dados para artigos transacionais, consulte [Definir o método de propagação de alterações de dados para artigos transacionais](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span><span class="sxs-lookup"><span data-stu-id="3543b-113">To set the propagation method for data changes to transactional articles, see [Set the Propagation Method for Data Changes to Transactional Articles](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span></span>  
  
## <a name="default-and-custom-stored-procedures"></a><span data-ttu-id="3543b-114">Procedimentos armazenados padrão e personalizados</span><span class="sxs-lookup"><span data-stu-id="3543b-114">Default and custom stored procedures</span></span>  
 <span data-ttu-id="3543b-115">Os três procedimentos que a replicação cria por padrão para cada artigo de tabela são:</span><span class="sxs-lookup"><span data-stu-id="3543b-115">The three procedures that replication creates by default for each table article are:</span></span>  
  
-   <span data-ttu-id="3543b-116">**sp_MSins_\<** *tablename* **>** , que trata de inserções.</span><span class="sxs-lookup"><span data-stu-id="3543b-116">**sp_MSins_\<** *tablename* **>**, which handles inserts.</span></span>  
  
-   <span data-ttu-id="3543b-117">**sp_MSupd_\<** *tablename* **>** , que trata de atualizações.</span><span class="sxs-lookup"><span data-stu-id="3543b-117">**sp_MSupd_\<** *tablename* **>**, which handles updates.</span></span>  
  
-   <span data-ttu-id="3543b-118">**sp_MSdel_\<** *tablename* **>** , que trata de exclusões.</span><span class="sxs-lookup"><span data-stu-id="3543b-118">**sp_MSdel_\<** *tablename* **>**, which handles deletes.</span></span>  
  
 <span data-ttu-id="3543b-119">O **\<***tablename***>** usado no procedimento depende de como o artigo foi adicionado à publicação e se o banco de dados de assinatura contém uma tabela do mesmo nome com um proprietário diferente.</span><span class="sxs-lookup"><span data-stu-id="3543b-119">The **\<***tablename***>** used in the procedure depends on how the article was added to the publication and whether the subscription database contains a table of the same name with a different owner.</span></span>  
  
 <span data-ttu-id="3543b-120">Qualquer um desses procedimentos pode ser substituído com um procedimento personalizado que você especifica ao adicionar um artigo a uma publicação.</span><span class="sxs-lookup"><span data-stu-id="3543b-120">Any of these procedures can be replaced with a custom procedure that you specify when adding an article to a publication.</span></span> <span data-ttu-id="3543b-121">Os procedimentos personalizados são usados se um aplicativo requerer lógica personalizada, como inserir dados em uma tabela de auditoria quando uma linha é atualizada em um Assinante.</span><span class="sxs-lookup"><span data-stu-id="3543b-121">Custom procedures are used if an application requires custom logic, such as inserting data into an audit table when a row is updated at a Subscriber.</span></span> <span data-ttu-id="3543b-122">Para obter mais informações sobre como especificar procedimentos armazenados personalizados, consulte os tópicos de instruções relacionados acima.</span><span class="sxs-lookup"><span data-stu-id="3543b-122">For more information about specifying custom stored procedures, see the how to topics listed above.</span></span>  
  
 <span data-ttu-id="3543b-123">Se você especificar os procedimentos de replicação ou procedimentos personalizados, você especificará também a sintaxe de chamada para cada procedimento (a replicação seleciona padrões se você utilizar os procedimentos padrão).</span><span class="sxs-lookup"><span data-stu-id="3543b-123">If you specify the default replication procedures or custom procedures, you also specify call syntax for each procedure (replication selects defaults if you use the default procedures).</span></span> <span data-ttu-id="3543b-124">A sintaxe de chamada determina a estrutura dos parâmetros fornecidos para o procedimento e quanta informação é enviada ao Assinante com cada alteração de dados.</span><span class="sxs-lookup"><span data-stu-id="3543b-124">The call syntax determines the structure of the parameters provided to the procedure and how much information is sent to the Subscriber with each data change.</span></span> <span data-ttu-id="3543b-125">Para obter mais informações, consulte a seção "Sintaxe de chamada de procedimentos armazenados" neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3543b-125">For more information, see the section "Call Syntax for Stored Procedures" in this topic.</span></span>  
  
### <a name="considerations-for-using-custom-stored-procedures"></a><span data-ttu-id="3543b-126">Considerações ao usar procedimentos armazenados personalizados</span><span class="sxs-lookup"><span data-stu-id="3543b-126">Considerations for Using Custom Stored Procedures</span></span>  
 <span data-ttu-id="3543b-127">Lembre-se das seguintes considerações ao usar procedimentos armazenados personalizados:</span><span class="sxs-lookup"><span data-stu-id="3543b-127">Keep the following considerations in mind when using custom stored procedures:</span></span>  
  
-   <span data-ttu-id="3543b-128">Você deve oferecer suporte à lógica do procedimento armazenado; [!INCLUDE[msCoName](../../../includes/msconame-md.md)] não oferece suporte à lógica personalizada.</span><span class="sxs-lookup"><span data-stu-id="3543b-128">You must support the logic in the stored procedure; [!INCLUDE[msCoName](../../../includes/msconame-md.md)] does not provide support for custom logic.</span></span>  
  
-   <span data-ttu-id="3543b-129">Para evitar conflitos com as transações usadas pela replicação, transações explícitas não devem ser usadas em procedimentos personalizados.</span><span class="sxs-lookup"><span data-stu-id="3543b-129">In order to avoid conflicts with the transactions used by replication, explicit transactions should not be used in custom procedures.</span></span>  
  
-   <span data-ttu-id="3543b-130">O esquema no Assinante é geralmente idêntico ao esquema do Publicador, mas pode também ser um subconjunto do esquema do Publicador se for usado filtragem de coluna.</span><span class="sxs-lookup"><span data-stu-id="3543b-130">The schema at the Subscriber is typically identical to the schema at the Publisher, but can also be a subset of the Publisher schema if column filtering is used.</span></span> <span data-ttu-id="3543b-131">Porém, se você precisar transformar o esquema assim que os dados forem removidos de modo que o esquema do Assinante não seja um subconjunto do esquema do Publicador, o [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] é a solução recomendada.</span><span class="sxs-lookup"><span data-stu-id="3543b-131">However, if you need to transform the schema as the data is moved such that the schema on the Subscriber is not a subset of the schema on the Publisher, [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] is the recommended solution.</span></span> <span data-ttu-id="3543b-132">Para obter mais informações, consulte [SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="3543b-132">For more information, see [SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span></span>  
  
-   <span data-ttu-id="3543b-133">Se você fizer alterações de esquema a uma tabela publicada, os procedimentos personalizados devem ser regenerados.</span><span class="sxs-lookup"><span data-stu-id="3543b-133">If you make schema changes to a published table, the custom procedures must be regenerated.</span></span> <span data-ttu-id="3543b-134">Para obter mais informações, consulte [Regenerar os procedimentos transacionais personalizados para refletir alterações de esquema](transactional-articles-regenerate-to-reflect-schema-changes.md).</span><span class="sxs-lookup"><span data-stu-id="3543b-134">For more information, see [Regenerate Custom Transactional Procedures to Reflect Schema Changes](transactional-articles-regenerate-to-reflect-schema-changes.md).</span></span>  
  
-   <span data-ttu-id="3543b-135">Se você usar um valor maior do que 1 para o parâmetro **-SubscriptionStreams** do Agente de Distribuição, você deverá se assegurar de que as atualizações nas colunas de chave primária tiveram êxito.</span><span class="sxs-lookup"><span data-stu-id="3543b-135">If you use a value greater than 1 for **-SubscriptionStreams** parameter of the Distribution Agent, you must ensure that updates to primary key columns are successful.</span></span> <span data-ttu-id="3543b-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3543b-136">For example:</span></span>  
  
    ```  
    update ... set pk = 2 where pk = 1 -- update 1  
    update ... set pk = 3 where pk = 2 -- update 2  
    ```  
  
     <span data-ttu-id="3543b-137">Se o Agente de Distribuição usar mais de uma conexão, estas duas atualizações poderão ser replicadas em conexões diferentes.</span><span class="sxs-lookup"><span data-stu-id="3543b-137">If the Distribution Agent uses more than one connection, these two updates might be replicated over different connections.</span></span> <span data-ttu-id="3543b-138">Se a atualização 1 for aplicada primeiro, não haverá problema; se a atualização 2 for aplicada primeiro ela retornará '0 linhas afetadas' porque a atualização 1 ainda não ocorreu.</span><span class="sxs-lookup"><span data-stu-id="3543b-138">If update 1 is applied first, there is no problem; if update 2 is applied first it will return '0 rows affected' because update 1 has not yet occurred.</span></span> <span data-ttu-id="3543b-139">Essa situação é tratada nos procedimentos padrão ao gerar um erro se nenhuma linha for afetada na atualização:</span><span class="sxs-lookup"><span data-stu-id="3543b-139">This situation is handled in the default procedures by raising an error if no rows are affected on an update:</span></span>  
  
    ```  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sys.sp_MSreplraiserror 20598  
    ```  
  
     <span data-ttu-id="3543b-140">Elevar o erro forçará o Agente de Distribuição a tentar novamente as atualizações em uma única conexão, que terá sucesso.</span><span class="sxs-lookup"><span data-stu-id="3543b-140">Raising the error forces the Distribution Agent to retry the updates over a single connection, which will succeed.</span></span> <span data-ttu-id="3543b-141">Procedimentos armazenados personalizados devem incluir lógica semelhante.</span><span class="sxs-lookup"><span data-stu-id="3543b-141">Custom stored procedures must include similar logic.</span></span>  
  
### <a name="call-syntax-for-stored-procedures"></a><span data-ttu-id="3543b-142">Sintaxe de chamada para procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="3543b-142">Call syntax for stored procedures</span></span>  
 <span data-ttu-id="3543b-143">Há cinco opções para a sintaxe usada para chamar os procedimentos usados por replicação transacional:</span><span class="sxs-lookup"><span data-stu-id="3543b-143">There are five options for the syntax used to call the procedures used by transactional replication:</span></span>  
  
-   <span data-ttu-id="3543b-144">Sintaxe CALL.</span><span class="sxs-lookup"><span data-stu-id="3543b-144">CALL syntax.</span></span> <span data-ttu-id="3543b-145">Pode ser usada para inserções, atualizações e exclusões.</span><span class="sxs-lookup"><span data-stu-id="3543b-145">Can be used for inserts, updates, and deletes.</span></span> <span data-ttu-id="3543b-146">Por padrão, a replicação usa esta sintaxe para inserções e exclusões.</span><span class="sxs-lookup"><span data-stu-id="3543b-146">By default, replication uses this syntax for inserts and deletes.</span></span>  
  
-   <span data-ttu-id="3543b-147">Sintaxe SCALL.</span><span class="sxs-lookup"><span data-stu-id="3543b-147">SCALL syntax.</span></span> <span data-ttu-id="3543b-148">Só pode ser usada para atualizações.</span><span class="sxs-lookup"><span data-stu-id="3543b-148">Can be used for updates only.</span></span> <span data-ttu-id="3543b-149">Por padrão, a replicação usa esta sintaxe para atualizações.</span><span class="sxs-lookup"><span data-stu-id="3543b-149">By default, replication uses this syntax for updates.</span></span>  
  
-   <span data-ttu-id="3543b-150">Sintaxe MCALL.</span><span class="sxs-lookup"><span data-stu-id="3543b-150">MCALL syntax.</span></span> <span data-ttu-id="3543b-151">Só pode ser usada para atualizações.</span><span class="sxs-lookup"><span data-stu-id="3543b-151">Can be used for updates only.</span></span>  
  
-   <span data-ttu-id="3543b-152">Sintaxe XCALL.</span><span class="sxs-lookup"><span data-stu-id="3543b-152">XCALL syntax.</span></span> <span data-ttu-id="3543b-153">Pode ser usada para atualizações e exclusões.</span><span class="sxs-lookup"><span data-stu-id="3543b-153">Can be used for updates and deletes.</span></span>  
  
-   <span data-ttu-id="3543b-154">VCALL.</span><span class="sxs-lookup"><span data-stu-id="3543b-154">VCALL.</span></span> <span data-ttu-id="3543b-155">Usado para assinaturas atualizáveis.</span><span class="sxs-lookup"><span data-stu-id="3543b-155">Used for updatable subscriptions.</span></span> <span data-ttu-id="3543b-156">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="3543b-156">Internal use only.</span></span>  
  
 <span data-ttu-id="3543b-157">Cada método difere na quantia de dados que é propagada ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="3543b-157">Each method differs in the amount of data that is propagated to the Subscriber.</span></span> <span data-ttu-id="3543b-158">Por exemplo, SCALL só passa valores para as colunas que são atualmente afetadas por uma atualização.</span><span class="sxs-lookup"><span data-stu-id="3543b-158">For example, SCALL passes in values only for the columns that are actually affected by an update.</span></span> <span data-ttu-id="3543b-159">Ao contrário, XCALL requer todas as colunas (sejam ou não afetadas por uma atualização) e todos os valores de dados antigos para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="3543b-159">XCALL, by contrast, requires all columns (whether affected by an update or not) and all the old data values for each column.</span></span> <span data-ttu-id="3543b-160">Em muitos casos, SCALL é apropriado para atualizações, mas se o seu aplicativo requer todos os valores de dados durante uma atualização, XCALL permite isso.</span><span class="sxs-lookup"><span data-stu-id="3543b-160">In many cases, SCALL is appropriate for updates, but if your application requires all the data values during an update, XCALL allows for this.</span></span>  
  
#### <a name="call-syntax"></a><span data-ttu-id="3543b-161">Sintaxe CALL</span><span class="sxs-lookup"><span data-stu-id="3543b-161">CALL Syntax</span></span>  
 <span data-ttu-id="3543b-162">Procedimentos armazenados de INSERT</span><span class="sxs-lookup"><span data-stu-id="3543b-162">INSERT stored procedures</span></span>  
 <span data-ttu-id="3543b-163">Procedimentos armazenados que controlam instruções INSERT receberão os valores inseridos para todas as colunas:</span><span class="sxs-lookup"><span data-stu-id="3543b-163">Stored procedures handling INSERT statements will be passed the inserted values for all columns:</span></span>  
  
```  
c1, c2, c3,... cn  
```  
  
 <span data-ttu-id="3543b-164">Procedimentos armazenados de UPDATE</span><span class="sxs-lookup"><span data-stu-id="3543b-164">UPDATE stored procedures</span></span>  
 <span data-ttu-id="3543b-165">Procedimentos armazenados que controlam instruções UPDATE receberão valores atualizados para todas as colunas definidas no artigo, seguidos pelos valores originais para as colunas de chave primárias (não é feita nenhuma tentativa para determinar quais as colunas que foram alteradas.):</span><span class="sxs-lookup"><span data-stu-id="3543b-165">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns (no attempt is made to determine which columns were changed.):</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn  
```  
  
 <span data-ttu-id="3543b-166">Procedimentos armazenados de DELETE</span><span class="sxs-lookup"><span data-stu-id="3543b-166">DELETE stored procedures</span></span>  
 <span data-ttu-id="3543b-167">Procedimentos armazenados que controlam instruções DELETE receberão valores das colunas de chave primária:</span><span class="sxs-lookup"><span data-stu-id="3543b-167">Stored procedures handling DELETE statements will be passed values for the primary key columns:</span></span>  
  
```  
pkc1, pkc2, pkc3,... pkcn  
```  
  
#### <a name="scall-syntax"></a><span data-ttu-id="3543b-168">Sintaxe SCALL</span><span class="sxs-lookup"><span data-stu-id="3543b-168">SCALL Syntax</span></span>  
 <span data-ttu-id="3543b-169">Procedimentos armazenados de UPDATE</span><span class="sxs-lookup"><span data-stu-id="3543b-169">UPDATE stored procedures</span></span>  
 <span data-ttu-id="3543b-170">Procedimentos armazenados que controlam instruções UPDATE receberão valores atualizados apenas para as colunas que foram alteradas, seguidos pelos valores originais para as colunas de chave primária, seguidos por um parâmetro (`binary(n)`) bitmask que indica as colunas alteradas.</span><span class="sxs-lookup"><span data-stu-id="3543b-170">Stored procedures handling UPDATE statements will be passed the updated values only for those columns that have changed, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns.</span></span> <span data-ttu-id="3543b-171">No exemplo seguinte, a coluna 2 (c2) não foi alterada:</span><span class="sxs-lookup"><span data-stu-id="3543b-171">In the following example, column 2 (c2) has not changed:</span></span>  
  
```  
c1, , c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="mcall-syntax"></a><span data-ttu-id="3543b-172">Sintaxe MCALL</span><span class="sxs-lookup"><span data-stu-id="3543b-172">MCALL Syntax</span></span>  
 <span data-ttu-id="3543b-173">Procedimentos armazenados de UPDATE</span><span class="sxs-lookup"><span data-stu-id="3543b-173">UPDATE stored procedures</span></span>  
 <span data-ttu-id="3543b-174">Procedimentos armazenados que controlam instruções UPDATE receberão valores atualizados para todas as colunas definidas no artigo, seguidos pelos valores originais para as colunas de chave primária, seguidos por um parâmetro (`binary(n)`) bitmask que indica as colunas alteradas.</span><span class="sxs-lookup"><span data-stu-id="3543b-174">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns:</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="xcall-syntax"></a><span data-ttu-id="3543b-175">Sintaxe XCALL</span><span class="sxs-lookup"><span data-stu-id="3543b-175">XCALL Syntax</span></span>  
 <span data-ttu-id="3543b-176">Procedimentos armazenados de UPDATE</span><span class="sxs-lookup"><span data-stu-id="3543b-176">UPDATE stored procedures</span></span>  
 <span data-ttu-id="3543b-177">Procedimentos armazenados que controlam instruções UPDATE receberão os valores originais (a imagem anterior) para todas as colunas definidas no artigo, seguidos pelos valores atualizados (a imagem posterior) para todas as colunas definidas no artigo:</span><span class="sxs-lookup"><span data-stu-id="3543b-177">Stored procedures handling UPDATE statements will be passed the original values (the before image) for all columns defined in the article, followed by the updated values (the after image) for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn, c1, c2, c3,... cn,  
```  
  
 <span data-ttu-id="3543b-178">Procedimentos armazenados de DELETE</span><span class="sxs-lookup"><span data-stu-id="3543b-178">DELETE stored procedures</span></span>  
 <span data-ttu-id="3543b-179">Procedimentos armazenados que controlam instruções DELETE receberão os valores originais (a imagem anterior) para todas as colunas definidas no artigo:</span><span class="sxs-lookup"><span data-stu-id="3543b-179">Stored procedures handling DELETE statements will be passed the original (the before image) values for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3543b-180">Ao usar XCALL, os valores da imagem anterior para **texto** e colunas de **imagem** são esperados para ser NULL.</span><span class="sxs-lookup"><span data-stu-id="3543b-180">When using XCALL, the before image values for **text** and **image** columns are expected to be NULL.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3543b-181">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3543b-181">Examples</span></span>  
 <span data-ttu-id="3543b-182">Os procedimentos a seguir são os procedimentos padrão criados para a `Vendor Table` no banco de dados de exemplo [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3543b-182">The following procedures are the default procedures created for the `Vendor Table` in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database.</span></span>  
  
```  
--INSERT procedure using CALL syntax  
create procedure [sp_MSins_PurchasingVendor]   
  @c1 int,@c2 nvarchar(15),@c3 nvarchar(50),@c4 tinyint,@c5 bit,@c6 bit,@c7 nvarchar(1024),@c8 datetime  
as   
begin   
insert into [Purchasing].[Vendor]([VendorID]  
,[AccountNumber]  
,[Name]  
,[CreditRating]  
,[PreferredVendorStatus]  
,[ActiveFlag]  
,[PurchasingWebServiceURL]  
,[ModifiedDate])  
values (   
 @c1  
,@c2  
,@c3  
,@c4  
,@c5  
,@c6  
,@c7  
,@c8  
 )   
end  
go  
  
--UPDATE procedure using SCALL syntax  
create procedure [sp_MSupd_PurchasingVendor]   
 @c1 int = null,@c2 nvarchar(15) = null,@c3 nvarchar(50) = null,@c4 tinyint = null,@c5 bit = null,@c6 bit = null,@c7 nvarchar(1024) = null,@c8 datetime = null,@pkc1 int  
,@bitmap binary(2)  
as  
begin  
update [Purchasing].[Vendor] set   
 [AccountNumber] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [AccountNumber] end  
,[Name] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [Name] end  
,[CreditRating] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [CreditRating] end  
,[PreferredVendorStatus] = case substring(@bitmap,1,1) & 16 when 16 then @c5 else [PreferredVendorStatus] end  
,[ActiveFlag] = case substring(@bitmap,1,1) & 32 when 32 then @c6 else [ActiveFlag] end  
,[PurchasingWebServiceURL] = case substring(@bitmap,1,1) & 64 when 64 then @c7 else [PurchasingWebServiceURL] end  
,[ModifiedDate] = case substring(@bitmap,1,1) & 128 when 128 then @c8 else [ModifiedDate] end  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end  
go  
  
--DELETE procedure using CALL syntax  
create procedure [sp_MSdel_PurchasingVendor]   
  @pkc1 int  
as   
begin   
delete [Purchasing].[Vendor]  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end   
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="3543b-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3543b-183">See Also</span></span>  
 [<span data-ttu-id="3543b-184">Article Options for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="3543b-184">Article Options for Transactional Replication</span></span>](article-options-for-transactional-replication.md)  
  
  
