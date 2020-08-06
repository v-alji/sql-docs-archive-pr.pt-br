---
title: Números em sequência | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sequence number object, overview
- sequence [Database Engine]
- autonumbers, sequences
- sequence numbers [SQL Server]
- sequence number object
ms.assetid: c900e30d-2fd3-4d5f-98ee-7832f37e79d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6c65b4df915a85cf0ec7c7c0c8c0ff9f6607ad96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685489"
---
# <a name="sequence-numbers"></a><span data-ttu-id="791f5-102">Números de sequência</span><span class="sxs-lookup"><span data-stu-id="791f5-102">Sequence Numbers</span></span>
  <span data-ttu-id="791f5-103">Uma sequência é um objeto associado a um esquema definido pelo usuário que gera uma sequência de valores numéricos de acordo com a especificação com a qual a sequência foi criada.</span><span class="sxs-lookup"><span data-stu-id="791f5-103">A sequence is a user-defined schema-bound object that generates a sequence of numeric values according to the specification with which the sequence was created.</span></span> <span data-ttu-id="791f5-104">A sequência de valores numéricos é gerada em ordem crescente ou decrescente em um intervalo definido e pode seguir um ciclo (repetir-se) conforme solicitado.</span><span class="sxs-lookup"><span data-stu-id="791f5-104">The sequence of numeric values is generated in an ascending or descending order at a defined interval and may cycle (repeat) as requested.</span></span> <span data-ttu-id="791f5-105">As sequências, ao contrário das colunas de identidade, não são associadas a tabelas.</span><span class="sxs-lookup"><span data-stu-id="791f5-105">Sequences, unlike identity columns, are not associated with tables.</span></span> <span data-ttu-id="791f5-106">Um aplicativo se refere a um objeto de sequência para receber seu próximo valor.</span><span class="sxs-lookup"><span data-stu-id="791f5-106">An application refers to a sequence object to receive its next value.</span></span> <span data-ttu-id="791f5-107">A relação entre sequências e tabelas é controlada pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="791f5-107">The relationship between sequences and tables is controlled by the application.</span></span> <span data-ttu-id="791f5-108">Os aplicativos de usuário podem referenciar um objeto de sequência e coordenar as chaves de valores em várias linhas e tabelas.</span><span class="sxs-lookup"><span data-stu-id="791f5-108">User applications can reference a sequence object and coordinate the values keys across multiple rows and tables.</span></span>  
  
 <span data-ttu-id="791f5-109">Uma sequência é criada independentemente das tabelas com o uso da instrução **CREATE SEQUENCE** .</span><span class="sxs-lookup"><span data-stu-id="791f5-109">A sequence is created independently of the tables by using the **CREATE SEQUENCE** statement.</span></span> <span data-ttu-id="791f5-110">Opções permitem que você controle o incremento, os valores máximo e mínimo, o ponto de partida, o recurso de reinício automático e o cache para melhorar desempenho.</span><span class="sxs-lookup"><span data-stu-id="791f5-110">Options enable you to control the increment, maximum and minimum values, starting point, automatic restarting capability, and caching to improve performance.</span></span> <span data-ttu-id="791f5-111">Para obter informações sobre as opções, veja [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="791f5-111">For information about the options, see [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span></span>  
  
 <span data-ttu-id="791f5-112">Ao contrário dos valores de coluna de identidade, que são gerados quando as linhas são inseridas, um aplicativo pode obter o próximo número de sequência antes de inserir a linha chamando a função [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="791f5-112">Unlike identity column values, which are generated when rows are inserted, an application can obtain the next sequence number before inserting the row by calling the [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) function.</span></span> <span data-ttu-id="791f5-113">O número de sequência é alocado quando NEXT VALUE FOR é chamado, mesmo quando o número nunca é inserido em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="791f5-113">The sequence number is allocated when NEXT VALUE FOR is called even if the number is never inserted into a table.</span></span> <span data-ttu-id="791f5-114">A função NEXT VALUE FOR pode ser usada como o valor padrão para uma coluna em uma definição de tabela.</span><span class="sxs-lookup"><span data-stu-id="791f5-114">The NEXT VALUE FOR function can be used as the default value for a column in a table definition.</span></span> <span data-ttu-id="791f5-115">Use [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) para obter um intervalo de vários números de sequência de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="791f5-115">Use [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) to get a range of multiple sequence numbers at once.</span></span>  
  
 <span data-ttu-id="791f5-116">Uma sequência pode ser definida como qualquer tipo de dados integer.</span><span class="sxs-lookup"><span data-stu-id="791f5-116">A sequence can be defined as any integer data type.</span></span> <span data-ttu-id="791f5-117">Se o tipo de dados não for especificado, uma sequência assumirá o padrão `bigint`.</span><span class="sxs-lookup"><span data-stu-id="791f5-117">If the data type is not specified, a sequence defaults to `bigint`.</span></span>  
  
## <a name="using-sequences"></a><span data-ttu-id="791f5-118">Usando sequências</span><span class="sxs-lookup"><span data-stu-id="791f5-118">Using Sequences</span></span>  
 <span data-ttu-id="791f5-119">Use sequências em vez de colunas de identidade nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="791f5-119">Use sequences instead of identity columns in the following scenarios:</span></span>  
  
-   <span data-ttu-id="791f5-120">O aplicativo requer um número antes da inserção na tabela.</span><span class="sxs-lookup"><span data-stu-id="791f5-120">The application requires a number before the insert into the table is made.</span></span>  
  
-   <span data-ttu-id="791f5-121">O aplicativo requer o compartilhamento de uma única série de números entre várias tabelas ou várias colunas dentro de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="791f5-121">The application requires sharing a single series of numbers between multiple tables or multiple columns within a table.</span></span>  
  
-   <span data-ttu-id="791f5-122">O aplicativo deve reiniciar a série de números quando um número especificado é alcançado.</span><span class="sxs-lookup"><span data-stu-id="791f5-122">The application must restart the number series when a specified number is reached.</span></span> <span data-ttu-id="791f5-123">Por exemplo, depois de atribuir valores de 1 a 10, o aplicativo inicia a atribuição de valores de 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="791f5-123">For example, after assigning values 1 through 10, the application starts assigning values 1 through 10 again.</span></span>  
  
-   <span data-ttu-id="791f5-124">O aplicativo requer que valores de sequência sejam classificados por outro campo.</span><span class="sxs-lookup"><span data-stu-id="791f5-124">The application requires sequence values to be sorted by another field.</span></span> <span data-ttu-id="791f5-125">A função NEXT VALUE FOR pode aplicar a cláusula OVER à chamada de função.</span><span class="sxs-lookup"><span data-stu-id="791f5-125">The NEXT VALUE FOR function can apply the OVER clause to the function call.</span></span> <span data-ttu-id="791f5-126">A cláusula OVER garante que os valores retornados sejam gerados na ordem da subcláusula ORDER BY da cláusula OVER.</span><span class="sxs-lookup"><span data-stu-id="791f5-126">The OVER clause guarantees that the values returned are generated in the order of the OVER clause's ORDER BY clause.</span></span>  
  
-   <span data-ttu-id="791f5-127">Um aplicativo requer que vários números sejam atribuídos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="791f5-127">An application requires multiple numbers to be assigned at the same time.</span></span> <span data-ttu-id="791f5-128">Por exemplo, um aplicativo precisa reservar cinco números sequenciais.</span><span class="sxs-lookup"><span data-stu-id="791f5-128">For example, an application needs to reserve five sequential numbers.</span></span> <span data-ttu-id="791f5-129">A solicitação de valores de identidade poderia resultar em intervalos na série se fossem emitidos números para outros processos simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="791f5-129">Requesting identity values could result in gaps in the series if other processes were simultaneously issued numbers.</span></span> <span data-ttu-id="791f5-130">A chamada a sp_sequence_get_range pode recuperar vários números na sequência de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="791f5-130">Calling sp_sequence_get_range can retrieve several numbers in the sequence at once.</span></span>  
  
-   <span data-ttu-id="791f5-131">Você precisa alterar a especificação da sequência, como o valor de incremento.</span><span class="sxs-lookup"><span data-stu-id="791f5-131">You need to change the specification of the sequence, such as the increment value.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="791f5-132">Limitações</span><span class="sxs-lookup"><span data-stu-id="791f5-132">Limitations</span></span>  
 <span data-ttu-id="791f5-133">Ao contrário das colunas de identidade, cujos valores não podem ser alterados, os valores de sequência não são protegidos automaticamente após a inserção na tabela.</span><span class="sxs-lookup"><span data-stu-id="791f5-133">Unlike identity columns, whose values cannot be changed, sequence values are not automatically protected after insertion into the table.</span></span> <span data-ttu-id="791f5-134">Para impedir a alteração de valores de sequência, use um gatilho de atualização na tabela reverter alterações.</span><span class="sxs-lookup"><span data-stu-id="791f5-134">To prevent sequence values from being changed, use an update trigger on the table to roll back changes.</span></span>  
  
 <span data-ttu-id="791f5-135">A exclusividade não é imposta automaticamente para valores de sequência.</span><span class="sxs-lookup"><span data-stu-id="791f5-135">Uniqueness is not automatically enforced for sequence values.</span></span> <span data-ttu-id="791f5-136">A capacidade de reutilizar valores de sequência é determinada pelo design.</span><span class="sxs-lookup"><span data-stu-id="791f5-136">The ability to reuse sequence values is by design.</span></span> <span data-ttu-id="791f5-137">Se os valores de sequência em uma tabela precisarem ser exclusivos, crie um índice exclusivo na coluna.</span><span class="sxs-lookup"><span data-stu-id="791f5-137">If sequence values in a table are required to be unique, create a unique index on the column.</span></span> <span data-ttu-id="791f5-138">Se os valores de sequência em uma tabela precisarem ser exclusivos em um grupo de tabelas, crie gatilhos para evitar duplicatas causadas por instruções de atualização ou pelo ciclo de números de sequência.</span><span class="sxs-lookup"><span data-stu-id="791f5-138">If sequence values in a table are required to be unique throughout a group of tables, create triggers to prevent duplicates caused by update statements or sequence number cycling.</span></span>  
  
 <span data-ttu-id="791f5-139">O objeto de sequência gera números de acordo com sua definição, mas o objeto de sequência não controla como os números são usados.</span><span class="sxs-lookup"><span data-stu-id="791f5-139">The sequence object generates numbers according to its definition, but the sequence object does not control how the numbers are used.</span></span> <span data-ttu-id="791f5-140">Os números de sequência inseridos em uma tabela podem ter intervalos quando uma transação é revertida, quando um objeto de sequência é compartilhado por várias tabelas ou quando os números de sequência são alocados e não são usados em tabelas.</span><span class="sxs-lookup"><span data-stu-id="791f5-140">Sequence numbers inserted into a table can have gaps when a transaction is rolled back, when a sequence object is shared by multiple tables, or when sequence numbers are allocated without using them in tables.</span></span> <span data-ttu-id="791f5-141">Quando criado com a opção CACHE, um desligamento inesperado, como uma deficiência de energia, pode perder os números de sequência no cache.</span><span class="sxs-lookup"><span data-stu-id="791f5-141">When created with the CACHE option, an unexpected shutdown, such as a power failure, can lose the sequence numbers in the cache.</span></span>  
  
 <span data-ttu-id="791f5-142">Se houver várias instâncias da função `NEXT VALUE FOR` especificando o mesmo gerador de sequência em uma única instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)], todas as instâncias retornarão o mesmo valor para uma determinada linha processada por essa instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="791f5-142">If there are multiple instances of the `NEXT VALUE FOR` function specifying the same sequence generator within a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, all those instances return the same value for a given row processed by that [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="791f5-143">Esse comportamento é coerente com o padrão ANSI.</span><span class="sxs-lookup"><span data-stu-id="791f5-143">This behavior is consistent with the ANSI standard.</span></span>  
  
## <a name="typical-use"></a><span data-ttu-id="791f5-144">Usos comum</span><span class="sxs-lookup"><span data-stu-id="791f5-144">Typical Use</span></span>  
 <span data-ttu-id="791f5-145">Para criar um número de sequência de inteiros com incrementos de 1 a partir de -2.147,483.648 até 2.147.483.647, use a instrução a seguir.</span><span class="sxs-lookup"><span data-stu-id="791f5-145">To create an integer sequence number that increments by 1 from -2,147,483,648 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    INCREMENT BY 1 ;  
```  
  
 <span data-ttu-id="791f5-146">Para criar um número de sequência de inteiros semelhante a uma coluna de identidade com incrementos de 1 a partir de 1 até 2.147.483.647, use a instrução a seguir.</span><span class="sxs-lookup"><span data-stu-id="791f5-146">To create an integer sequence number similar to an identity column that increments by 1 from 1 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
  
```  
  
## <a name="managing-sequences"></a><span data-ttu-id="791f5-147">Gerenciando sequências</span><span class="sxs-lookup"><span data-stu-id="791f5-147">Managing Sequences</span></span>  
 <span data-ttu-id="791f5-148">Para obter informações sobre sequências, consulte [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="791f5-148">For information about sequences, query [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="791f5-149">Exemplos</span><span class="sxs-lookup"><span data-stu-id="791f5-149">Examples</span></span>  
 <span data-ttu-id="791f5-150">Há outros exemplos nos tópicos [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR &#40;Transact-SQL&#41;](/sql/t-sql/functions/next-value-for-transact-sql) e [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="791f5-150">There are additional examples in the topics [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR &#40;Transact-SQL&#41;](/sql/t-sql/functions/next-value-for-transact-sql), and [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql).</span></span>  
  
### <a name="a-using-a-sequence-number-in-a-single-table"></a><span data-ttu-id="791f5-151">a.</span><span class="sxs-lookup"><span data-stu-id="791f5-151">A.</span></span> <span data-ttu-id="791f5-152">Usando um número de sequência em uma única tabela</span><span class="sxs-lookup"><span data-stu-id="791f5-152">Using a sequence number in a single table</span></span>  
 <span data-ttu-id="791f5-153">O exemplo a seguir cria um esquema denominado Test, uma tabela denominada Orders e uma sequência denominada CountBy1 e insere linhas na tabela usando a função NEXT VALUE FOR.</span><span class="sxs-lookup"><span data-stu-id="791f5-153">The following example creates a schema named Test, a table named Orders, and a sequence named CountBy1, and then inserts rows into the table using the NEXT VALUE FOR function.</span></span>  
  
```  
--Create the Test schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Orders  
    (OrderID int PRIMARY KEY,  
    Name varchar(20) NOT NULL,  
    Qty int NOT NULL);  
GO  
  
-- Create a sequence  
CREATE SEQUENCE Test.CountBy1  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
-- Insert three records  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Tire', 2) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Seat', 1) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Brake', 1) ;  
GO  
  
-- View the table  
SELECT * FROM Test.Orders ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `OrderID  Name    Qty`  
  
 `1        Tire    2`  
  
 `2        Seat    1`  
  
 `3        Brake   1`  
  
### <a name="b-calling-next-value-for-before-inserting-a-row"></a><span data-ttu-id="791f5-154">B.</span><span class="sxs-lookup"><span data-stu-id="791f5-154">B.</span></span> <span data-ttu-id="791f5-155">Chamando NEXT VALUE FOR antes de inserir uma linha</span><span class="sxs-lookup"><span data-stu-id="791f5-155">Calling NEXT VALUE FOR before inserting a row</span></span>  
 <span data-ttu-id="791f5-156">Usando a tabela `Orders` criada no exemplo A, o exemplo a seguir declara uma variável denominada `@nextID`e, em seguida, usa a função NEXT VALUE FOR para definir a variável como o próximo número de sequência disponível.</span><span class="sxs-lookup"><span data-stu-id="791f5-156">Using the `Orders` table created in example A, the following example declares a variable named `@nextID`, and then uses the NEXT VALUE FOR function to set the variable to the next available sequence number.</span></span> <span data-ttu-id="791f5-157">O aplicativo deve fazer algum processamento do pedido, como fornecer ao cliente o número `OrderID` do seu pedido em potencial, e depois validar a ordem.</span><span class="sxs-lookup"><span data-stu-id="791f5-157">The application is presumed to do some processing of the order, such as providing the customer with the `OrderID` number of their potential order, and then validates the order.</span></span> <span data-ttu-id="791f5-158">Independentemente de quanto tempo este processamento possa levar, ou de quantas outras ordens sejam adicionadas durante o processo, o número original é preservado para ser usado por esta conexão.</span><span class="sxs-lookup"><span data-stu-id="791f5-158">No matter how long this processing might take, or how many other orders are added during the process, the original number is preserved for use by this connection.</span></span> <span data-ttu-id="791f5-159">Por fim, a instrução `INSERT` adiciona o pedido à tabela `Orders` .</span><span class="sxs-lookup"><span data-stu-id="791f5-159">Finally, the `INSERT` statement adds the order to the `Orders` table.</span></span>  
  
```  
DECLARE @NextID int ;  
SET @NextID = NEXT VALUE FOR Test.CountBy1;  
-- Some work happens  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (@NextID, 'Rim', 2) ;  
GO  
  
```  
  
### <a name="c-using-a-sequence-number-in-multiple-tables"></a><span data-ttu-id="791f5-160">C.</span><span class="sxs-lookup"><span data-stu-id="791f5-160">C.</span></span> <span data-ttu-id="791f5-161">Usando um número de sequência em várias tabelas</span><span class="sxs-lookup"><span data-stu-id="791f5-161">Using a sequence number in multiple tables</span></span>  
 <span data-ttu-id="791f5-162">Este exemplo presume que um processo de monitoramento de linha de produção recebe a notificação dos eventos que ocorrem em toda a fábrica.</span><span class="sxs-lookup"><span data-stu-id="791f5-162">This example assumes that a production-line monitoring process receives notification of events that occur throughout the workshop.</span></span> <span data-ttu-id="791f5-163">Cada evento recebe um número `EventID` exclusivo e com aumento monotônico.</span><span class="sxs-lookup"><span data-stu-id="791f5-163">Each event receives a unique and monotonically increasing `EventID` number.</span></span> <span data-ttu-id="791f5-164">Todos os eventos usam o mesmo número de sequência `EventID` , de forma que os relatórios que combinam todos os eventos possam identificar cada evento de modo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="791f5-164">All events use the same `EventID` sequence number so that reports that combine all events can uniquely identify each event.</span></span> <span data-ttu-id="791f5-165">Entretanto, os dados do evento são armazenados em três tabelas diferentes, dependendo do tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="791f5-165">However the event data is stored in three different tables, depending on the type of event.</span></span> <span data-ttu-id="791f5-166">O exemplo de código cria um esquema chamado `Audit`, uma sequência chamada `EventCounter`e três tabelas que usam cada uma a sequência `EventCounter` como valor padrão.</span><span class="sxs-lookup"><span data-stu-id="791f5-166">The code example creates a schema named `Audit`, a sequence named `EventCounter`, and three tables which each use the `EventCounter` sequence as a default value.</span></span> <span data-ttu-id="791f5-167">Em seguida, o exemplo adiciona linhas às três tabelas e consulta os resultados.</span><span class="sxs-lookup"><span data-stu-id="791f5-167">Then the example adds rows to the three tables and queries the results.</span></span>  
  
```  
CREATE SCHEMA Audit ;  
GO  
CREATE SEQUENCE Audit.EventCounter  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
CREATE TABLE Audit.ProcessEvents  
(  
    EventID int PRIMARY KEY CLUSTERED   
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EventCode nvarchar(5) NOT NULL,  
    Description nvarchar(300) NULL  
) ;  
GO  
  
CREATE TABLE Audit.ErrorEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NULL,  
    ErrorNumber int NOT NULL,  
    EventDesc nvarchar(256) NULL  
) ;  
GO  
  
CREATE TABLE Audit.StartStopEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NOT NULL,  
    StartOrStop bit NOT NULL  
) ;  
GO  
  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 0) ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (72, 0) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (2735,   
    'Clean room temperature 18 degrees C.') ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (18, 'Spin rate threashold exceeded.') ;  
INSERT Audit.ErrorEvents (EquipmentID, ErrorNumber, EventDesc)   
    VALUES (248, 82, 'Feeder jam') ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 1) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (1841, 'Central feed in bypass mode.') ;  
-- The following statement combines all events, though not all fields.  
SELECT EventID, EventTime, Description FROM Audit.ProcessEvents   
UNION SELECT EventID, EventTime, EventDesc FROM Audit.ErrorEvents   
UNION SELECT EventID, EventTime,   
CASE StartOrStop   
    WHEN 0 THEN 'Start'   
    ELSE 'Stop'  
END   
FROM Audit.StartStopEvents  
ORDER BY EventID ;  
GO  
  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `EventID  EventTime                Description`  
  
 `1        2009-11-02 15:00:51.157  Start`  
  
 `2        2009-11-02 15:00:51.160  Start`  
  
 `3        2009-11-02 15:00:51.167  Clean room temperature 18 degrees C.`  
  
 `4        2009-11-02 15:00:51.167  Spin rate threshold exceeded.`  
  
 `5        2009-11-02 15:00:51.173  Feeder jam`  
  
 `6        2009-11-02 15:00:51.177  Stop`  
  
 `7        2009-11-02 15:00:51.180  Central feed in bypass mode.`  
  
### <a name="d-generating-repeating-sequence-numbers-in-a-result-set"></a><span data-ttu-id="791f5-168">D.</span><span class="sxs-lookup"><span data-stu-id="791f5-168">D.</span></span> <span data-ttu-id="791f5-169">Gerando números de sequência repetidos em um conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="791f5-169">Generating repeating sequence numbers in a result set</span></span>  
 <span data-ttu-id="791f5-170">O exemplo a seguir demonstra dois recursos de números de sequência: ciclos e o uso de `NEXT VALUE FOR` em uma instrução select.</span><span class="sxs-lookup"><span data-stu-id="791f5-170">The following example demonstrates two features of sequence numbers: cycling, and using `NEXT VALUE FOR` in a select statement.</span></span>  
  
```  
CREATE SEQUENCE CountBy5  
   AS tinyint  
    START WITH 1  
    INCREMENT BY 1  
    MINVALUE 1  
    MAXVALUE 5  
    CYCLE ;  
GO  
  
SELECT NEXT VALUE FOR CountBy5 AS SurveyGroup, Name FROM sys.objects ;  
GO  
```  
  
### <a name="e-generating-sequence-numbers-for-a-result-set-by-using-the-over-clause"></a><span data-ttu-id="791f5-171">E.</span><span class="sxs-lookup"><span data-stu-id="791f5-171">E.</span></span> <span data-ttu-id="791f5-172">Gerando números de sequência para um conjunto de resultados usando a cláusula OVER</span><span class="sxs-lookup"><span data-stu-id="791f5-172">Generating sequence numbers for a result set by using the OVER clause</span></span>  
 <span data-ttu-id="791f5-173">O exemplo a seguir usa a cláusula `OVER` para classificar o conjunto de resultados por `Name` antes de adicionar a coluna de números de sequência.</span><span class="sxs-lookup"><span data-stu-id="791f5-173">The following example uses the `OVER` clause to sort the result set by `Name` before it adds the sequence number column.</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE SCHEMA Samples ;  
GO  
  
CREATE SEQUENCE Samples.IDLabel  
    AS tinyint  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="f-resetting-the-sequence-number"></a><span data-ttu-id="791f5-174">F.</span><span class="sxs-lookup"><span data-stu-id="791f5-174">F.</span></span> <span data-ttu-id="791f5-175">Redefinindo o número de sequência</span><span class="sxs-lookup"><span data-stu-id="791f5-175">Resetting the sequence number</span></span>  
 <span data-ttu-id="791f5-176">O exemplo E consumiu os primeiros 79 dos números de sequência `Samples.IDLabel`.</span><span class="sxs-lookup"><span data-stu-id="791f5-176">Example E consumed the first 79 of the `Samples.IDLabel` sequence numbers.</span></span> <span data-ttu-id="791f5-177">(Sua versão do `AdventureWorks2012` poderá retornar um número diferente de resultados.) Execute a instrução a seguir para consumir os próximos 79 números de sequência (de 80 a 158).</span><span class="sxs-lookup"><span data-stu-id="791f5-177">(Your version of `AdventureWorks2012` may return a different number of results.) Execute the following to consume the next 79 sequence numbers (80 though 158).</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
 <span data-ttu-id="791f5-178">Execute a instrução a seguir para reiniciar a sequência `Samples.IDLabel`.</span><span class="sxs-lookup"><span data-stu-id="791f5-178">Execute the following statement to restart the `Samples.IDLabel` sequence.</span></span>  
  
```  
ALTER SEQUENCE Samples.IDLabel  
RESTART WITH 1 ;  
```  
  
 <span data-ttu-id="791f5-179">Execute a instrução select novamente para verificar se a sequência `Samples.IDLabel` foi reiniciada com o número 1.</span><span class="sxs-lookup"><span data-stu-id="791f5-179">Execute the select statement again to verify that the `Samples.IDLabel` sequence restarted with number 1.</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="g-changing-a-table-from-identity-to-sequence"></a><span data-ttu-id="791f5-180">G.</span><span class="sxs-lookup"><span data-stu-id="791f5-180">G.</span></span> <span data-ttu-id="791f5-181">Alterando uma tabela de identidade para sequência</span><span class="sxs-lookup"><span data-stu-id="791f5-181">Changing a table from identity to sequence</span></span>  
 <span data-ttu-id="791f5-182">O exemplo a seguir cria um esquema e tabela contendo três linhas para o exemplo.</span><span class="sxs-lookup"><span data-stu-id="791f5-182">The following example creates a schema and table containing three rows for the example.</span></span> <span data-ttu-id="791f5-183">Em seguida, o exemplo adiciona uma nova coluna e remove a coluna antiga.</span><span class="sxs-lookup"><span data-stu-id="791f5-183">Then the example adds a new column and drops the old column.</span></span>  
  
```  
-- Create a schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Department  
    (  
        DepartmentID smallint IDENTITY(1,1) NOT NULL,  
        Name nvarchar(100) NOT NULL,  
        GroupName nvarchar(100) NOT NULL  
    CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC)   
    ) ;  
GO  
  
-- Insert three rows into the table  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Engineering', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Tool Design', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Sales', 'Sales and Marketing');  
GO  
  
-- View the table that will be changed  
SELECT * FROM Test.Department ;  
GO  
  
-- End of portion creating a sample table  
--------------------------------------------------------  
-- Add the new column that does not have the IDENTITY property  
ALTER TABLE Test.Department   
    ADD DepartmentIDNew smallint NULL  
GO  
  
-- Copy values from the old column to the new column  
UPDATE Test.Department  
    SET DepartmentIDNew = DepartmentID ;  
GO  
  
-- Drop the primary key constraint on the old column  
ALTER TABLE Test.Department  
    DROP CONSTRAINT [PK_Department_DepartmentID];  
-- Drop the old column  
ALTER TABLE Test.Department  
    DROP COLUMN DepartmentID ;  
GO  
  
-- Rename the new column to the old columns name  
EXEC sp_rename 'Test.Department.DepartmentIDNew',   
    'DepartmentID', 'COLUMN';  
GO  
  
-- Change the new column to NOT NULL  
ALTER TABLE Test.Department  
    ALTER COLUMN DepartmentID smallint NOT NULL ;  
-- Add the unique primary key constraint  
ALTER TABLE Test.Department  
    ADD CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC) ;  
-- Get the highest current value from the DepartmentID column   
-- and create a sequence to use with the column. (Returns 3.)  
SELECT MAX(DepartmentID) FROM Test.Department ;  
-- Use the next desired value (4) as the START WITH VALUE;  
CREATE SEQUENCE Test.DeptSeq  
    AS smallint  
    START WITH 4  
    INCREMENT BY 1 ;  
GO  
  
-- Add a default value for the DepartmentID column  
ALTER TABLE Test.Department  
    ADD CONSTRAINT DefSequence DEFAULT (NEXT VALUE FOR Test.DeptSeq)   
        FOR DepartmentID;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;   
-- Test insert  
INSERT Test.Department (Name, GroupName)  
    VALUES ('Audit', 'Quality Assurance') ;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;  
GO  
  
```  
  
 <span data-ttu-id="791f5-184">As instruções [!INCLUDE[tsql](../../../includes/tsql-md.md)] que usam `SELECT *` receberão a nova coluna como a última coluna, e não a primeira.</span><span class="sxs-lookup"><span data-stu-id="791f5-184">[!INCLUDE[tsql](../../../includes/tsql-md.md)] statements that use `SELECT *` will receive the new column as the last column instead of the first column.</span></span> <span data-ttu-id="791f5-185">Se isso não for aceitável, você deverá criar uma tabela totalmente nova, mover os dados para ela e recriar as permissões na nova tabela.</span><span class="sxs-lookup"><span data-stu-id="791f5-185">If this is not acceptable, then you must create an entirely new table, move the data to it, and then recreate the permissions on the new table.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="791f5-186">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="791f5-186">Related Content</span></span>  
 [<span data-ttu-id="791f5-187">CREATE SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="791f5-187">CREATE SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-sequence-transact-sql)  
  
 [<span data-ttu-id="791f5-188">ALTER SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="791f5-188">ALTER SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-sequence-transact-sql)  
  
 [<span data-ttu-id="791f5-189">DROP SEQUENCE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="791f5-189">DROP SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-sequence-transact-sql)  
  
 [<span data-ttu-id="791f5-190">IDENTITY &#40;Propriedade&#41; &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="791f5-190">IDENTITY &#40;Property&#41; &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql-identity-property)  
  
  
