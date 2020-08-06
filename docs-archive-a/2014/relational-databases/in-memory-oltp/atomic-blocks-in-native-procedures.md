---
title: Blocos atômicos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 40e0e749-260c-4cfc-a848-444d30c09d85
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ca8f5b4d767ef0fe836cd260f8d12dd5b40c75d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570009"
---
# <a name="atomic-blocks"></a><span data-ttu-id="004b5-102">Blocos atômicos</span><span class="sxs-lookup"><span data-stu-id="004b5-102">Atomic Blocks</span></span>
  <span data-ttu-id="004b5-103">`BEGIN ATOMIC` não faz parte do padrão ANSI SQL.</span><span class="sxs-lookup"><span data-stu-id="004b5-103">`BEGIN ATOMIC` is part of the ANSI SQL standard.</span></span> <span data-ttu-id="004b5-104">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte a blocos atômicos somente no nível superior dos procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="004b5-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports atomic blocks only at the top-level of natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="004b5-105">Cada procedimento armazenado compilado nativamente contém exatamente um bloco de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="004b5-105">Every natively compiled stored procedure contains exactly one block of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="004b5-106">Esse é um bloco ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="004b5-106">This is an ATOMIC block.</span></span>  
  
-   <span data-ttu-id="004b5-107">Os procedimentos armazenados [!INCLUDE[tsql](../../includes/tsql-md.md)] não nativos interpretados e os lotes ad hoc não oferecem suporte a blocos atômicos.</span><span class="sxs-lookup"><span data-stu-id="004b5-107">Non-native, interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and ad hoc batches do not support atomic blocks.</span></span>  
  
 <span data-ttu-id="004b5-108">Os blocos atômicos são executados (atomicamente) na transação.</span><span class="sxs-lookup"><span data-stu-id="004b5-108">Atomic blocks are executed (atomically) within the transaction.</span></span> <span data-ttu-id="004b5-109">Todas as instruções no bloco foram bem-sucedidas ou o bloco inteiro será revertido para o ponto de salvamento criado no início do bloco.</span><span class="sxs-lookup"><span data-stu-id="004b5-109">Either all statements in the block succeed or the entire block will be rolled back to the savepoint that was created at the start of the block.</span></span> <span data-ttu-id="004b5-110">Além disso, as configurações da sessão são corrigidas para o bloco atômico.</span><span class="sxs-lookup"><span data-stu-id="004b5-110">In addition, the session settings are fixed for the atomic block.</span></span> <span data-ttu-id="004b5-111">A execução do mesmo bloco atômico nas sessões com diferentes configurações resultará no mesmo comportamento, independentemente das configurações da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="004b5-111">Executing the same atomic block in sessions with different settings will result in the same behavior, independent of the settings of the current session.</span></span>  
  
## <a name="transactions-and-error-handling"></a><span data-ttu-id="004b5-112">Transações e tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="004b5-112">Transactions and Error Handling</span></span>  
 <span data-ttu-id="004b5-113">Se uma transação já existir em uma sessão (porque um lote executou uma instrução `BEGIN TRANSACTION` e a transação permanece ativa), iniciar um bloco atômico criará um ponto de salvamento na transação.</span><span class="sxs-lookup"><span data-stu-id="004b5-113">If a transaction already exists on a session (because a batch executed a `BEGIN TRANSACTION` statement and the transaction remains active), then starting an atomic block will create a savepoint in the transaction.</span></span> <span data-ttu-id="004b5-114">Se o bloco sair sem uma exceção, um novo ponto de salvamento criado para o bloco é confirmado, mas a transação não será confirmada até que isso ocorra no nível da sessão.</span><span class="sxs-lookup"><span data-stu-id="004b5-114">If the block exits without an exception, the savepoint that was created for the block commits, but the transaction will not commit until the transaction at the session level commits.</span></span> <span data-ttu-id="004b5-115">Se o bloco lançar uma exceção, os efeitos do bloco serão revertidos, mas a transação no nível da sessão continuará, a menos que a exceção seja decretada por transação.</span><span class="sxs-lookup"><span data-stu-id="004b5-115">If the block throws an exception, the effects of the block are rolled back but the transaction at the session level will proceed, unless the exception is transaction-dooming.</span></span> <span data-ttu-id="004b5-116">Por exemplo, um conflito de gravação é decretado por transação, mas não um erro de conversão de tipo.</span><span class="sxs-lookup"><span data-stu-id="004b5-116">For example a write conflict is transaction-dooming, but not a type casting error.</span></span>  
  
 <span data-ttu-id="004b5-117">Se não houver transação ativa em uma sessão, `BEGIN ATOMIC` iniciará uma nova transação.</span><span class="sxs-lookup"><span data-stu-id="004b5-117">If there is no active transaction on a session, `BEGIN ATOMIC` will start a new transaction.</span></span> <span data-ttu-id="004b5-118">Se nenhuma exceção for lançada fora do escopo do bloco, a transação será confirmada no fim do bloco.</span><span class="sxs-lookup"><span data-stu-id="004b5-118">If no exception is thrown outside the scope of the block, the transaction will be committed at the end of the block.</span></span> <span data-ttu-id="004b5-119">Se o bloco lançar uma exceção (ou seja, se a exceção não for capturada e tratada no bloco), a transação será revertida.</span><span class="sxs-lookup"><span data-stu-id="004b5-119">If the block throws an exception (that is, the exception is not caught and handled within the block), the transaction will be rolled back.</span></span> <span data-ttu-id="004b5-120">Para transações que abrangem um único bloco atômico (um único procedimento armazenado compilado nativamente), você não precisa gravar instruções `BEGIN TRANSACTION` e `COMMIT` ou `ROLLBACK` explícitas.</span><span class="sxs-lookup"><span data-stu-id="004b5-120">For transactions that span a single atomic block (a single natively compiled stored procedure), you do not need to write explicit `BEGIN TRANSACTION` and `COMMIT` or `ROLLBACK` statements.</span></span>  
  
 <span data-ttu-id="004b5-121">Os procedimentos armazenados compilados nativamente oferecem suporte às construções `TRY`, `CATCH` e `THROW` para tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="004b5-121">Natively compiled stored procedures support the `TRY`, `CATCH`, and `THROW` constructs for error handling.</span></span> <span data-ttu-id="004b5-122">`RAISERROR` não é suportado.</span><span class="sxs-lookup"><span data-stu-id="004b5-122">`RAISERROR` is not supported.</span></span>  
  
 <span data-ttu-id="004b5-123">O exemplo a seguir ilustra o comportamento de tratamento de erros com blocos atômicos e procedimentos armazenados compilados nativamente:</span><span class="sxs-lookup"><span data-stu-id="004b5-123">The following example illustrates the error handling behavior with atomic blocks and natively compiled stored procedures:</span></span>  
  
```sql  
-- sample table  
CREATE TABLE dbo.t1 (  
  c1 int not null primary key nonclustered  
)  
WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- sample proc that inserts 2 rows  
CREATE PROCEDURE dbo.usp_t1 @v1 bigint not null, @v2 bigint not null  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC  
WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english', DELAYED_DURABILITY = ON)  
  
  INSERT dbo.t1 VALUES (@v1)  
  INSERT dbo.t1 VALUES (@v2)  
  
END  
GO  
  
-- insert two rows  
EXEC dbo.usp_t1 1, 2  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify the rows 1 and 2 were committed  
SELECT c1 FROM dbo.t1  
GO  
  
-- execute proc with arithmetic overflow  
EXEC dbo.usp_t1 3, 4444444444444  
GO  
-- expected error message:  
-- Msg 8115, Level 16, State 0, Procedure usp_t1  
-- Arithmetic overflow error converting bigint to data type int.  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 was not committed; usp_t1 has been rolled back  
SELECT c1 FROM dbo.t1  
GO  
  
-- start a new transaction  
BEGIN TRANSACTION  
  -- insert rows 3 and 4  
  EXEC dbo.usp_t1 3, 4  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify the rows 3 and 4 were inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
  -- catch the arithmetic overflow error  
  BEGIN TRY  
    EXEC dbo.usp_t1 5, 4444444444444  
  END TRY  
  BEGIN CATCH  
    PRINT N'Error occurred: ' + error_message()  
  END CATCH  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify rows 3 and 4 are still in the table, and row 5 has not been inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
COMMIT  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 and 4 has been committed  
SELECT c1 FROM dbo.t1  
ORDER BY c1  
GO  
```  
  
 <span data-ttu-id="004b5-124">As mensagens de erro a seguir específicas de tabelas com otimização de memória são decretadas por transação.</span><span class="sxs-lookup"><span data-stu-id="004b5-124">The following error messages specific to memory-optimized tables are transaction dooming.</span></span> <span data-ttu-id="004b5-125">Se elas ocorrerem no escopo de um bloco atômico, a transação será anulada: 10772, 41301, 41302, 41305, 41325, 41332 e 41333.</span><span class="sxs-lookup"><span data-stu-id="004b5-125">If they occur in the scope of an atomic block, they will cause the transaction to abort: 10772, 41301, 41302, 41305, 41325, 41332, and 41333.</span></span>  
  
## <a name="session-settings"></a><span data-ttu-id="004b5-126">Configurações da sessão</span><span class="sxs-lookup"><span data-stu-id="004b5-126">Session Settings</span></span>  
 <span data-ttu-id="004b5-127">As configurações da sessão nos blocos atômicos são corrigidas quando o procedimento armazenado é compilado.</span><span class="sxs-lookup"><span data-stu-id="004b5-127">The session settings in atomic blocks are fixed when the stored procedure is compiled.</span></span> <span data-ttu-id="004b5-128">Algumas configurações podem ser especificadas com `BEGIN ATOMIC`, enquanto outras configurações sempre são corrigidas para o mesmo valor.</span><span class="sxs-lookup"><span data-stu-id="004b5-128">Some settings can be specified with `BEGIN ATOMIC` while other settings are always fixed to the same value.</span></span>  
  
 <span data-ttu-id="004b5-129">As seguintes opções são necessárias com `BEGIN ATOMIC`:</span><span class="sxs-lookup"><span data-stu-id="004b5-129">The following options are required with `BEGIN ATOMIC`:</span></span>  
  
|<span data-ttu-id="004b5-130">Configuração necessária</span><span class="sxs-lookup"><span data-stu-id="004b5-130">Required Setting</span></span>|<span data-ttu-id="004b5-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="004b5-131">Description</span></span>|  
|----------------------|-----------------|  
|`TRANSACTION ISOLATION LEVEL`|<span data-ttu-id="004b5-132">Os valores com suporte são `SNAPSHOT`, `REPEATABLEREAD` e `SERIALIZABLE`.</span><span class="sxs-lookup"><span data-stu-id="004b5-132">Supported values are `SNAPSHOT`, `REPEATABLEREAD`, and `SERIALIZABLE`.</span></span>|  
|`LANGUAGE`|<span data-ttu-id="004b5-133">Determina os formatos de data e hora, e as mensagens do sistema.</span><span class="sxs-lookup"><span data-stu-id="004b5-133">Determines date and time formats and system messages.</span></span> <span data-ttu-id="004b5-134">Todos os idiomas e alias em [sys.syslanguages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) têm suporte.</span><span class="sxs-lookup"><span data-stu-id="004b5-134">All languages and aliases in [sys.syslanguages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) are supported.</span></span>|  
  
 <span data-ttu-id="004b5-135">As seguintes configurações são opcionais:</span><span class="sxs-lookup"><span data-stu-id="004b5-135">The following settings are optional:</span></span>  
  
|<span data-ttu-id="004b5-136">Configuração opcional</span><span class="sxs-lookup"><span data-stu-id="004b5-136">Optional Setting</span></span>|<span data-ttu-id="004b5-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="004b5-137">Description</span></span>|  
|----------------------|-----------------|  
|`DATEFORMAT`|<span data-ttu-id="004b5-138">Há suporte para todos os formatos de data do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="004b5-138">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date formats are supported.</span></span> <span data-ttu-id="004b5-139">Quando especificado, `DATEFORMAT` substitui o formato de data padrão associado a `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="004b5-139">When specified, `DATEFORMAT` overrides the default date format associated with `LANGUAGE`.</span></span>|  
|`DATEFIRST`|<span data-ttu-id="004b5-140">Quando especificado, `DATEFIRST` substitui o padrão associado a `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="004b5-140">When specified, `DATEFIRST` overrides the default associated with `LANGUAGE`.</span></span>|  
|`DELAYED_DURABILITY`|<span data-ttu-id="004b5-141">Os valores com suporte são `OFF` e `ON`.</span><span class="sxs-lookup"><span data-stu-id="004b5-141">Supported values are `OFF` and `ON`.</span></span><br /><br /> <span data-ttu-id="004b5-142">Confirmações de transação [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem ser completamente duráveis, o padrão ou duráveis atrasadas. Para obter mais informações, consulte [Controlar a durabilidade da transação](../logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="004b5-142">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction commits can be either fully durable, the default, or delayed durable.For more information, see [Control Transaction Durability](../logs/control-transaction-durability.md).</span></span>|  
  
 <span data-ttu-id="004b5-143">As opções SET a seguir têm o mesmo valor padrão de sistema para todos os blocos atômicos em todos os procedimentos armazenados compilados nativamente:</span><span class="sxs-lookup"><span data-stu-id="004b5-143">The following SET options have the same system default value for all atomic blocks in all natively compiled stored procedures:</span></span>  
  
|<span data-ttu-id="004b5-144">Opção Set</span><span class="sxs-lookup"><span data-stu-id="004b5-144">Set Option</span></span>|<span data-ttu-id="004b5-145">Padrão do sistema para blocos atômicos</span><span class="sxs-lookup"><span data-stu-id="004b5-145">System Default for Atomic Blocks</span></span>|  
|----------------|--------------------------------------|  
|<span data-ttu-id="004b5-146">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="004b5-146">ANSI_NULLS</span></span>|<span data-ttu-id="004b5-147">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="004b5-147">ON</span></span>|  
|<span data-ttu-id="004b5-148">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="004b5-148">ANSI_PADDING</span></span>|<span data-ttu-id="004b5-149">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="004b5-149">ON</span></span>|  
|<span data-ttu-id="004b5-150">ANSI_WARNING</span><span class="sxs-lookup"><span data-stu-id="004b5-150">ANSI_WARNING</span></span>|<span data-ttu-id="004b5-151">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="004b5-151">ON</span></span>|  
|<span data-ttu-id="004b5-152">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="004b5-152">ARITHABORT</span></span>|<span data-ttu-id="004b5-153">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="004b5-153">ON</span></span>|  
|<span data-ttu-id="004b5-154">ARITHIGNORE</span><span class="sxs-lookup"><span data-stu-id="004b5-154">ARITHIGNORE</span></span>|<span data-ttu-id="004b5-155">OFF</span><span class="sxs-lookup"><span data-stu-id="004b5-155">OFF</span></span>|  
|<span data-ttu-id="004b5-156">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="004b5-156">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="004b5-157">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="004b5-157">ON</span></span>|  
|<span data-ttu-id="004b5-158">IDENTITY_INSERT</span><span class="sxs-lookup"><span data-stu-id="004b5-158">IDENTITY_INSERT</span></span>|<span data-ttu-id="004b5-159">OFF</span><span class="sxs-lookup"><span data-stu-id="004b5-159">OFF</span></span>|  
|<span data-ttu-id="004b5-160">NOCOUNT</span><span class="sxs-lookup"><span data-stu-id="004b5-160">NOCOUNT</span></span>|<span data-ttu-id="004b5-161">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="004b5-161">ON</span></span>|  
|<span data-ttu-id="004b5-162">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="004b5-162">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="004b5-163">OFF</span><span class="sxs-lookup"><span data-stu-id="004b5-163">OFF</span></span>|  
|<span data-ttu-id="004b5-164">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="004b5-164">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="004b5-165">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="004b5-165">ON</span></span>|  
|<span data-ttu-id="004b5-166">ROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="004b5-166">ROWCOUNT</span></span>|<span data-ttu-id="004b5-167">0</span><span class="sxs-lookup"><span data-stu-id="004b5-167">0</span></span>|  
|<span data-ttu-id="004b5-168">TEXTSIZE</span><span class="sxs-lookup"><span data-stu-id="004b5-168">TEXTSIZE</span></span>|<span data-ttu-id="004b5-169">0</span><span class="sxs-lookup"><span data-stu-id="004b5-169">0</span></span>|  
|<span data-ttu-id="004b5-170">XACT_ABORT</span><span class="sxs-lookup"><span data-stu-id="004b5-170">XACT_ABORT</span></span>|<span data-ttu-id="004b5-171">OFF</span><span class="sxs-lookup"><span data-stu-id="004b5-171">OFF</span></span><br /><br /> <span data-ttu-id="004b5-172">As exceções não capturadas fazem com que o bloco atômico seja revertido, mas não fazem com que a transação seja anulada, a menos que o erro seja decretado por transação.</span><span class="sxs-lookup"><span data-stu-id="004b5-172">Uncaught exceptions cause the atomic block to roll back, but not cause the transaction to abort unless the error is transaction dooming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="004b5-173">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="004b5-173">See Also</span></span>  
 [<span data-ttu-id="004b5-174">Procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="004b5-174">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
