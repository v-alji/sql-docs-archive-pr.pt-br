---
title: Criando procedimentos armazenados compilados nativamente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: e6b34010-cf62-4f65-bbdf-117f291cde7b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3e8e8139427c7f2ad92eea856be8da542f65e344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571392"
---
# <a name="creating-natively-compiled-stored-procedures"></a><span data-ttu-id="8952d-102">Criando procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="8952d-102">Creating Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="8952d-103">Os procedimentos armazenados compilados nativamente não implementam a programação [!INCLUDE[tsql](../../includes/tsql-md.md)] completa e a área de superfície da consulta.</span><span class="sxs-lookup"><span data-stu-id="8952d-103">Natively compiled stored procedures do not implement the full [!INCLUDE[tsql](../../includes/tsql-md.md)] programmability and query surface area.</span></span> <span data-ttu-id="8952d-104">Há determinadas construções [!INCLUDE[tsql](../../includes/tsql-md.md)] que não podem ser usadas nos procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="8952d-104">There are certain [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs that cannot be used inside natively compiled stored procedures.</span></span> <span data-ttu-id="8952d-105">Para obter mais informações, consulte [construções com suporte em procedimentos armazenados compilados nativamente](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md).</span><span class="sxs-lookup"><span data-stu-id="8952d-105">For more information, see [Supported Constructs in Natively Compiled Stored Procedures](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md).</span></span>  
  
 <span data-ttu-id="8952d-106">No entanto, existem vários recursos do [!INCLUDE[tsql](../../includes/tsql-md.md)] com suporte apenas nos procedimentos armazenados compilados nativamente:</span><span class="sxs-lookup"><span data-stu-id="8952d-106">There are, however, several [!INCLUDE[tsql](../../includes/tsql-md.md)] features that are only supported for natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="8952d-107">Blocos atômicos.</span><span class="sxs-lookup"><span data-stu-id="8952d-107">Atomic blocks.</span></span> <span data-ttu-id="8952d-108">Para obter mais informações, veja [Blocos atômicos](atomic-blocks-in-native-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8952d-108">For more information, see [Atomic Blocks](atomic-blocks-in-native-procedures.md).</span></span>  
  
-   <span data-ttu-id="8952d-109">Restrições `NOT NULL` nos parâmetros e variáveis dos procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="8952d-109">`NOT NULL` constraints on parameters of and variables in natively compiled stored procedures.</span></span> <span data-ttu-id="8952d-110">Você não pode atribuir valores `NULL` a parâmetros ou variáveis declarados como `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="8952d-110">You cannot assign `NULL` values to parameters or variables declared as `NOT NULL`.</span></span> <span data-ttu-id="8952d-111">Para obter mais informações, consulte [DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8952d-111">For more information, see [DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span></span>  
  
-   <span data-ttu-id="8952d-112">Associação de esquema de procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="8952d-112">Schema binding of natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="8952d-113">Procedimentos armazenados compilados de modo nativo são criados com [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8952d-113">Natively compiled stored procedures are created using [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span> <span data-ttu-id="8952d-114">O exemplo a seguir mostra uma tabela com otimização de memória e um procedimento armazenado compilado nativamente usado para inserção de linhas na tabela.</span><span class="sxs-lookup"><span data-stu-id="8952d-114">The following example shows a memory-optimized table and a natively compiled stored procedure used for inserting rows into the table.</span></span>  
  
```sql  
create table dbo.Ord  
(OrdNo integer not null primary key nonclustered,   
 OrdDate datetime not null,   
 CustCode nvarchar(5) not null)   
 with (memory_optimized=on)  
go  
  
create procedure dbo.OrderInsert(@OrdNo integer, @CustCode nvarchar(5))  
with native_compilation, schemabinding, execute as owner  
as   
begin atomic with  
(transaction isolation level = snapshot,  
language = N'English')  
  
  declare @OrdDate datetime = getdate();  
  insert into dbo.Ord (OrdNo, CustCode, OrdDate) values (@OrdNo, @CustCode, @OrdDate);  
end  
go  
```  
  
 <span data-ttu-id="8952d-115">No exemplo de código, `NATIVE_COMPILATION` indica que esse procedimento armazenado [!INCLUDE[tsql](../../includes/tsql-md.md)] é compilado nativamente.</span><span class="sxs-lookup"><span data-stu-id="8952d-115">In the code sample, `NATIVE_COMPILATION` indicates that this [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure is a natively compiled stored procedure.</span></span> <span data-ttu-id="8952d-116">As seguintes opções são necessárias:</span><span class="sxs-lookup"><span data-stu-id="8952d-116">The following options are required:</span></span>  
  
|<span data-ttu-id="8952d-117">Opção</span><span class="sxs-lookup"><span data-stu-id="8952d-117">Option</span></span>|<span data-ttu-id="8952d-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="8952d-118">Description</span></span>|  
|------------|-----------------|  
|`SCHEMABINDING`|<span data-ttu-id="8952d-119">Os procedimentos armazenados compilados nativamente devem ser associados ao esquema dos objetos que ele referencia.</span><span class="sxs-lookup"><span data-stu-id="8952d-119">Natively compiled stored procedures must be bound to the schema of the objects it references.</span></span> <span data-ttu-id="8952d-120">Isso significa que as referências de tabela pelo procedimento não podem ser eliminadas.</span><span class="sxs-lookup"><span data-stu-id="8952d-120">This means that table references by the procedure cannot be dropped.</span></span> <span data-ttu-id="8952d-121">As tabelas referenciadas no procedimento devem incluir o nome do esquema e os curingas ( \* ) não são permitidos em consultas.</span><span class="sxs-lookup"><span data-stu-id="8952d-121">Tables referenced in the procedure must include their schema name, and wildcards (\*) are not allowed in queries.</span></span> <span data-ttu-id="8952d-122">Há suporte para `SCHEMABINDING` somente nos procedimentos armazenados compilados nativamente nesta versão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8952d-122">`SCHEMABINDING` is only supported for natively compiled stored procedures in this version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>|  
|`EXECUTE AS`|<span data-ttu-id="8952d-123">Os procedimentos armazenados compilados nativamente não oferecem suporte a `EXECUTE AS CALLER`, que é o contexto de execução padrão.</span><span class="sxs-lookup"><span data-stu-id="8952d-123">Natively compiled stored procedures do not support `EXECUTE AS CALLER`, which is the default execution context.</span></span> <span data-ttu-id="8952d-124">Portanto, a especificação do contexto de execução é necessária.</span><span class="sxs-lookup"><span data-stu-id="8952d-124">Therefore, specifying the execution context is required.</span></span> <span data-ttu-id="8952d-125">Há `EXECUTE AS OWNER` suporte para as opções, o `EXECUTE AS` *usuário*e o `EXECUTE AS SELF` .</span><span class="sxs-lookup"><span data-stu-id="8952d-125">The options `EXECUTE AS OWNER`, `EXECUTE AS`*user*, and `EXECUTE AS SELF` are supported.</span></span>|  
|`BEGIN ATOMIC`|<span data-ttu-id="8952d-126">O corpo do procedimento armazenado compilado nativamente deve consistir em exatamente um bloco atômico.</span><span class="sxs-lookup"><span data-stu-id="8952d-126">The natively compiled stored procedure body must consist of exactly one atomic block.</span></span> <span data-ttu-id="8952d-127">Os blocos atômicos garantem a execução atômica do procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="8952d-127">Atomic blocks guarantee atomic execution of the stored procedure.</span></span> <span data-ttu-id="8952d-128">Se o procedimento for chamado fora do contexto de uma transação ativa, ele iniciará uma nova transação, que é confirmada no fim do bloco atômico.</span><span class="sxs-lookup"><span data-stu-id="8952d-128">If the procedure is invoked outside the context of an active transaction, it will start a new transaction, which commits at the end of the atomic block.</span></span> <span data-ttu-id="8952d-129">Os blocos atômicos nos procedimentos armazenados compilados nativamente têm duas opções necessárias:</span><span class="sxs-lookup"><span data-stu-id="8952d-129">Atomic blocks in natively compiled stored procedures have two required options:</span></span><br /><br /> <span data-ttu-id="8952d-130">`TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="8952d-130">`TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="8952d-131">Consulte [níveis de isolamento da transação](../../database-engine/transaction-isolation-levels.md) para obter os níveis de isolamento com suporte.</span><span class="sxs-lookup"><span data-stu-id="8952d-131">See [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md) for supported isolation levels.</span></span><br /><br /> <span data-ttu-id="8952d-132">`LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="8952d-132">`LANGUAGE`.</span></span> <span data-ttu-id="8952d-133">O idioma do procedimento armazenado deve ser definido para um dos idiomas ou alias de idioma disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8952d-133">The language for the stored procedure must be set to one of the available languages or language aliases.</span></span>|  
  
 <span data-ttu-id="8952d-134">Quanto a `EXECUTE AS` e aos logons do Windows, um erro poderá ocorrer devido à representação feita através de `EXECUTE AS`.</span><span class="sxs-lookup"><span data-stu-id="8952d-134">Regarding `EXECUTE AS` and Windows logins, an error can occur because of the impersonation done through `EXECUTE AS`.</span></span> <span data-ttu-id="8952d-135">Se uma conta de usuário usa a Autenticação do Windows, deve haver uma confiança total entre a conta de serviço usada para a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e o domínio do logon do Windows.</span><span class="sxs-lookup"><span data-stu-id="8952d-135">If a user account uses Windows Authentication, there must be full trust between the service account used for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance and the domain of the Windows login.</span></span> <span data-ttu-id="8952d-136">Se não houver confiança total, a seguinte mensagem de erro será retornada durante a criação de um procedimento armazenado compilado nativamente: msg 15404, não foi possível obter informações sobre o grupo/usuário ' username ' do Windows NT, código de erro 0x5.</span><span class="sxs-lookup"><span data-stu-id="8952d-136">If there is not full trust, the following error message is returned when creating a natively compiled stored procedure: Msg 15404, Could not obtain information about Windows NT group/user 'username', error code 0x5.</span></span>  
  
 <span data-ttu-id="8952d-137">Para resolver esse erro, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="8952d-137">To resolve this error, use one of the following:</span></span>  
  
-   <span data-ttu-id="8952d-138">Use uma conta do mesmo domínio que o usuário do Windows para o serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8952d-138">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="8952d-139">Se [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o estiver usando uma conta de computador, como serviço de rede ou sistema local, o computador deverá ser confiável pelo domínio que contém o usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="8952d-139">If [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows user.</span></span>  
  
-   <span data-ttu-id="8952d-140">Use a Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8952d-140">Use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="8952d-141">Você também pode ver o erro 15517 ao criar um procedimento armazenado compilado de modo nativo.</span><span class="sxs-lookup"><span data-stu-id="8952d-141">You may also see error 15517 when creating a natively compiled stored procedure.</span></span> <span data-ttu-id="8952d-142">Para obter mais informações, consulte [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="8952d-142">For more information, see [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span></span>  
  
## <a name="updating-a-natively-compiled-stored-procedure"></a><span data-ttu-id="8952d-143">Atualizando um procedimento armazenado nativamente compilado</span><span class="sxs-lookup"><span data-stu-id="8952d-143">Updating a Natively Compiled Stored Procedure</span></span>  
 <span data-ttu-id="8952d-144">Não há suporte para a execução de operações de alteração em procedimentos armazenados compilados de modo nativo.</span><span class="sxs-lookup"><span data-stu-id="8952d-144">Performing alter operations on natively compiled stored procedures is not supported.</span></span> <span data-ttu-id="8952d-145">Uma maneira de modificar um procedimento armazenado compilado nativamente é remover e recriar o procedimento armazenado:</span><span class="sxs-lookup"><span data-stu-id="8952d-145">One way to modify a natively compiled stored procedure is to drop and recreate the stored procedure:</span></span>  
  
1.  <span data-ttu-id="8952d-146">Gere o script para as permissões no procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="8952d-146">Generate script for the permissions on the stored procedure.</span></span>  
  
2.  <span data-ttu-id="8952d-147">(Opcional) Gere o script para o procedimento armazenado e salve como um backup.</span><span class="sxs-lookup"><span data-stu-id="8952d-147">Optional, generate script for the stored procedure and save as a backup.</span></span>  
  
3.  <span data-ttu-id="8952d-148">Descarte o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="8952d-148">Drop the stored procedure.</span></span>  
  
4.  <span data-ttu-id="8952d-149">Crie o procedimento armazenado alterado.</span><span class="sxs-lookup"><span data-stu-id="8952d-149">Create the altered stored procedure.</span></span>  
  
5.  <span data-ttu-id="8952d-150">Reaplique as permissões em script ao procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="8952d-150">Re-apply the scripted permissions to the stored procedure.</span></span>  
  
 <span data-ttu-id="8952d-151">A desvantagem desse procedimento é que o aplicativo estará offline desde o início da etapa 3 até a conclusão da etapa 5.</span><span class="sxs-lookup"><span data-stu-id="8952d-151">The disadvantage to this procedure is the application will be offline from the start of step 3 through the completion of step 5.</span></span> <span data-ttu-id="8952d-152">Isso pode levar alguns segundos e o cliente que estiver usando o aplicativo poderá ver mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="8952d-152">This may take a few seconds and the client using the application may see error messages.</span></span>  
  
 <span data-ttu-id="8952d-153">Outra maneira de modificar (com eficiência) um procedimento armazenado compilado nativamente é criar primeiro uma nova versão do procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="8952d-153">Another way to (effectively) modify a natively compiled stored procedure is to first create a new version of the stored procedure.</span></span> <span data-ttu-id="8952d-154">Aqui, o procedimento armazenado compilado nativamente tem um número de versão associado.</span><span class="sxs-lookup"><span data-stu-id="8952d-154">Here, the natively compiled stored procedure has an associated version number.</span></span> <span data-ttu-id="8952d-155">Chamaremos a versão antiga de SP_Vold e a nova versão de SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="8952d-155">We will call the old version SP_Vold and the new version SP_Vnew.</span></span>  
  
1.  <span data-ttu-id="8952d-156">Gere o script para as permissões em SP_Vold.</span><span class="sxs-lookup"><span data-stu-id="8952d-156">Generate script for the permissions on SP_Vold.</span></span>  
  
2.  <span data-ttu-id="8952d-157">Crie SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="8952d-157">Create SP_Vnew.</span></span>  
  
3.  <span data-ttu-id="8952d-158">Aplique as permissões de SP_Vold a SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="8952d-158">Apply the permissions of SP_Vold to SP_Vnew.</span></span>  
  
4.  <span data-ttu-id="8952d-159">Atualize as referências a SP_Vold para apontar para SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="8952d-159">Update references to SP_Vold to point to SP_Vnew.</span></span> <span data-ttu-id="8952d-160">Há várias maneiras de se fazer isso. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8952d-160">This can be accomplished in different of ways, for example:</span></span>  
  
     <span data-ttu-id="8952d-161">Use um procedimento armazenado de wrapper (baseado em disco) e altere-o para apontar para SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="8952d-161">Use a wrapper (disk-based) stored procedure, and alter that procedure to point to SP_Vnew.</span></span> <span data-ttu-id="8952d-162">A desvantagem dessa abordagem é o impacto no desempenho da indireção.</span><span class="sxs-lookup"><span data-stu-id="8952d-162">The disadvantage of this approach is the performance impact of the indirection.</span></span>  
  
    ```sql  
    ALTER PROCEDURE dbo.SP p1,...,pn  
    AS  
      EXEC dbo.SP_Vnew p1,...,pn  
    GO  
    ```  
  
5.  <span data-ttu-id="8952d-163">(Opcional) Descarte SP_Vold.</span><span class="sxs-lookup"><span data-stu-id="8952d-163">Optional, drop SP_Vold.</span></span>  
  
 <span data-ttu-id="8952d-164">A vantagem dessa abordagem é que o aplicativo não fica offline.</span><span class="sxs-lookup"><span data-stu-id="8952d-164">The advantage of this approach is that the application does not go offline.</span></span> <span data-ttu-id="8952d-165">No entanto, é mais trabalhoso manter as referências e ter certeza de que elas apontam para a versão mais recente do procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="8952d-165">However, more work is required to maintain the references and make sure they always point to the latest version of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8952d-166">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8952d-166">See Also</span></span>  
 [<span data-ttu-id="8952d-167">Procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="8952d-167">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
