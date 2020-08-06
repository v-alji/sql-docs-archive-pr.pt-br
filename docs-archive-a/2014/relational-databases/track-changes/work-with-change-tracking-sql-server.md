---
title: Trabalhar com o controle de alterações (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], making changes
- change tracking [SQL Server], troubleshooting
- updating data [SQL Server]
- troubleshooting [SQL Server], change tracking
- data changes [SQL Server]
- tracking data changes [SQL Server]
- data [SQL Server], changing
- change tracking [SQL Server], data restore
- change tracking [SQL Server], ensuring consistent results
- change tracking [SQL Server], handling changes
ms.assetid: 5aec22ce-ae6f-4048-8a45-59ed05f04dc5
author: rothja
ms.author: jroth
ms.openlocfilehash: bdb8205a789894caf8c8e2d3c3f491751757bab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582901"
---
# <a name="work-with-change-tracking-sql-server"></a><span data-ttu-id="0ebc3-102">Trabalhar com o controle de alterações (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0ebc3-102">Work with Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="0ebc3-103">Os aplicativos que usam o controle de alterações devem ser capazes de obter as alterações controladas, aplicá-las a outro repositório de dados e atualizar o banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-103">Applications that use change tracking must be able to obtain tracked changes, apply these changes to another data store, and update the source database.</span></span> <span data-ttu-id="0ebc3-104">Este tópico descreve como executar essas tarefas e também a função que o controle de alterações desempenha quando ocorre um failover e um banco de dados precisa ser restaurado de um backup.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-104">This topic describes how to perform these tasks, and also the role change tracking plays when a failover occurs and a database must be restored from a backup.</span></span>  
  
##  <a name="obtain-changes-by-using-change-tracking-functions"></a><a name="Obtain"></a> <span data-ttu-id="0ebc3-105">Obter alterações usando as funções de controle de alterações</span><span class="sxs-lookup"><span data-stu-id="0ebc3-105">Obtain Changes by Using Change Tracking Functions</span></span>  
 <span data-ttu-id="0ebc3-106">Descreve como usar as funções de controle de alterações para obter as alterações feitas em um banco de dados e as respectivas informações.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-106">Describes how to use the change tracking functions to obtain changes and information about the changes that were made to a database.</span></span>  
  
### <a name="about-the-change-tracking-functions"></a><span data-ttu-id="0ebc3-107">Sobre as funções de controle de alterações</span><span class="sxs-lookup"><span data-stu-id="0ebc3-107">About the Change Tracking Functions</span></span>  
 <span data-ttu-id="0ebc3-108">Os aplicativos podem usar as funções a seguir para obter as alterações feitas em um banco de dados e as informações sobre as alterações:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-108">Applications can use the following functions to obtain the changes that are made in a database and information about the changes:</span></span>  
  
 <span data-ttu-id="0ebc3-109">Função CHANGETABLE(CHANGES ...)</span><span class="sxs-lookup"><span data-stu-id="0ebc3-109">CHANGETABLE(CHANGES ...) function</span></span>  
 <span data-ttu-id="0ebc3-110">Esta função de conjunto de linhas é usada para consultar informações de alteração.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-110">This rowset function is used to query for change information.</span></span> <span data-ttu-id="0ebc3-111">A função consulta os dados armazenados nas tabelas internas de controle de alterações e</span><span class="sxs-lookup"><span data-stu-id="0ebc3-111">The function queries the data stored in the internal change tracking tables.</span></span> <span data-ttu-id="0ebc3-112">retorna um conjunto de resultados que contém as chaves primárias de linhas, que foram alteradas, junto com outras informações de alterações como a operação, as colunas atualizadas e a versão da linha.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-112">The function returns a results set that contains the primary keys of rows that have changed together with other change information such as the operation, columns updated and version for the row.</span></span>  
  
 <span data-ttu-id="0ebc3-113">A função CHANGETABLE(CHANGES ...) usa uma última versão de sincronização como um argumento.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-113">CHANGETABLE(CHANGES ...) takes a last synchronization version as an argument.</span></span> <span data-ttu-id="0ebc3-114">A última versão de sincronização é obtida por meio da variável `@last_synchronization_version` .</span><span class="sxs-lookup"><span data-stu-id="0ebc3-114">The last sychronization version is obtained using the `@last_synchronization_version` variable.</span></span> <span data-ttu-id="0ebc3-115">A semântica da última versão de sincronização é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-115">The semantics of the last synchronization version are as follows:</span></span>  
  
-   <span data-ttu-id="0ebc3-116">O cliente de chamada obteve e tem conhecimento de todas as alterações até, e inclusive, a última versão de sincronização.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-116">The calling client has obtained changes and knows about all changes up to and including the last synchronization version.</span></span>  
  
-   <span data-ttu-id="0ebc3-117">A função CHANGETABLE(CHANGES ...) retornará todas as alterações ocorridas depois da última versão de sincronização.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-117">CHANGETABLE(CHANGES ...) will therefore return all changes that have occurred after the last synchronization version.</span></span>  
  
     <span data-ttu-id="0ebc3-118">A ilustração a seguir mostra como a função CHANGETABLE(CHANGES ...) é usada para obter alterações.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-118">The following illustration shows how CHANGETABLE(CHANGES ...) is used to obtain changes.</span></span>  
  
     <span data-ttu-id="0ebc3-119">![Exemplo da saída de consulta de controle de alterações](../../database-engine/media/queryoutput.gif "Exemplo da saída de consulta de controle de alterações")</span><span class="sxs-lookup"><span data-stu-id="0ebc3-119">![Example of change tracking query output](../../database-engine/media/queryoutput.gif "Example of change tracking query output")</span></span>  
  
 <span data-ttu-id="0ebc3-120">Função CHANGE_TRACKING_CURRENT_VERSION()</span><span class="sxs-lookup"><span data-stu-id="0ebc3-120">CHANGE_TRACKING_CURRENT_VERSION() function</span></span>  
 <span data-ttu-id="0ebc3-121">É usada para obter a versão atual que será usada na próxima vez ao consultar alterações.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-121">Is used to obtain the current version that will be used the next time when querying changes.</span></span> <span data-ttu-id="0ebc3-122">Essa versão representa a versão da última transação confirmada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-122">This version represents the version of the last committed transaction.</span></span>  
  
 <span data-ttu-id="0ebc3-123">Função CHANGE_TRACKING_MIN_VALID_VERSION()</span><span class="sxs-lookup"><span data-stu-id="0ebc3-123">CHANGE_TRACKING_MIN_VALID_VERSION()function</span></span>  
 <span data-ttu-id="0ebc3-124">Esta função é usada para obter a versão mínima válida que o cliente pode ter e também obter os resultados válidos de CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="0ebc3-124">Is used to obtain the minimum valid version that a client can have and still obtain valid results from CHANGETABLE().</span></span> <span data-ttu-id="0ebc3-125">O cliente deverá comparar a última versão de sincronização com o valor retornado por essa função.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-125">The client should check the last synchronization version against the value thatis returned by this function.</span></span> <span data-ttu-id="0ebc3-126">Se a última versão de sincronização for menor que a versão retornada por essa função, o cliente não poderá obter os resultados válidos de CHANGETABLE() e deverá reinicializar os dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-126">If the last synchronization version is less than the version returned by this function, the client will be unable to obtain valid results from CHANGETABLE() and will have to reinitialize.</span></span>  
  
### <a name="obtaining-initial-data"></a><span data-ttu-id="0ebc3-127">Obtendo dados iniciais</span><span class="sxs-lookup"><span data-stu-id="0ebc3-127">Obtaining Initial Data</span></span>  
 <span data-ttu-id="0ebc3-128">Antes que um aplicativo possa obter as alterações pela primeira vez, ele deverá enviar uma consulta para obter os dados iniciais e a versão de sincronização.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-128">Before an application can obtain changes for the first time, the application must send a query to obtain the initial data and the synchronization version.</span></span> <span data-ttu-id="0ebc3-129">O aplicativo deve obter os dados adequados diretamente da tabela e usar a função CHANGE_TRACKING_CURRENT_VERSION() para obter a versão inicial.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-129">The application must obtain the appropriate data directly from the table, and then use CHANGE_TRACKING_CURRENT_VERSION() to obtain the initial version.</span></span> <span data-ttu-id="0ebc3-130">Essa versão passará para CHANGETABLE(CHANGES ...) na primeira vez em que as alterações forem obtidas.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-130">This version will be passed to CHANGETABLE(CHANGES ...) the first time that changes are obtained.</span></span>  
  
 <span data-ttu-id="0ebc3-131">O exemplo a seguir mostra como obter a versão de sincronização inicial, bem como o conjunto de dados inicial.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-131">The following example shows how to obtain the initial synchronization version and the initial data set.</span></span>  
  
```sql  
    -- Obtain the current synchronization version. This will be used next time that changes are obtained.  
    SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
    -- Obtain initial data set.  
    SELECT  
        P.ProductID, P.Name, P.ListPrice  
    FROM  
        SalesLT.Product AS P  
```  
  
### <a name="using-the-change-tracking-functions-to-obtain-changes"></a><span data-ttu-id="0ebc3-132">Usando as funções de controle de alterações para obter alterações</span><span class="sxs-lookup"><span data-stu-id="0ebc3-132">Using the Change Tracking Functions to Obtain Changes</span></span>  
 <span data-ttu-id="0ebc3-133">Para obter as linhas alteradas de uma tabela e as informações sobre as alterações, use a função CHANGETABLE(CHANGES...). Por exemplo, a consulta a seguir obtém as alterações da tabela `SalesLT.Product` .</span><span class="sxs-lookup"><span data-stu-id="0ebc3-133">To obtain the changed rows for a table and information about the changes, use CHANGETABLE(CHANGES...). For example, the following query obtains changes for the `SalesLT.Product` table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, CT.SYS_CHANGE_OPERATION,  
    CT.SYS_CHANGE_COLUMNS, CT.SYS_CHANGE_CONTEXT  
FROM  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
  
```  
  
 <span data-ttu-id="0ebc3-134">Geralmente, um cliente optará por obter os últimos dados de uma linha em vez de apenas as chaves primárias da linha.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-134">Usually, a client will want to obtain the latest data for a row instead of only the primary keys for the row.</span></span> <span data-ttu-id="0ebc3-135">Além disso, um aplicativo juntaria os resultados de CHANGETABLE(CHANGES ...) com os dados na tabela do usuário.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-135">Therefore, an application would join the results from CHANGETABLE(CHANGES ...) with the data in the user table.</span></span> <span data-ttu-id="0ebc3-136">Por exemplo, a consulta a seguir une as linhas da tabela `SalesLT.Product` para obter os valores das colunas `Name` e `ListPrice` .</span><span class="sxs-lookup"><span data-stu-id="0ebc3-136">For example, the following query joins with the `SalesLT.Product` table to obtain the values for the `Name` and `ListPrice` columns.</span></span> <span data-ttu-id="0ebc3-137">Observe o uso da função `OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-137">Note the use of `OUTER JOIN`.</span></span> <span data-ttu-id="0ebc3-138">Ela é obrigatória para garantir que as informações de alteração sejam retornadas para essas linhas que foram excluídas da tabela do usuário.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-138">This is required to make sure that the change information is returned for those rows that have been deleted from the user table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
 <span data-ttu-id="0ebc3-139">Para obter a versão a ser usada na próxima enumeração de alteração, use  CHANGE_TRACKING_CURRENT_VERSION(), como mostra o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-139">To obtain the version for use in the next change enumeration, use CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION()  
```  
  
 <span data-ttu-id="0ebc3-140">Quando um aplicativo obtiver alterações, ele deverá usar CHANGETABLE(CHANGES...) e CHANGE_TRACKING_CURRENT_VERSION(), como mostra o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-140">When an application obtains changes, it must use both CHANGETABLE(CHANGES...) and CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
-- Obtain the current synchronization version. This will be used the next time CHANGETABLE(CHANGES...) is called.  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
-- Obtain incremental changes by using the synchronization version obtained the last time the data was synchronized.  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
### <a name="version-numbers"></a><span data-ttu-id="0ebc3-141">Números de versão</span><span class="sxs-lookup"><span data-stu-id="0ebc3-141">Version Numbers</span></span>  
 <span data-ttu-id="0ebc3-142">Um banco de dados com o controle de alterações habilitado tem um contador de versões que aumenta à medida que são realizadas mudanças nas tabelas controladas.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-142">A database that has change tracking enabled has a version counter that increases as changes are made to change tracked tables.</span></span> <span data-ttu-id="0ebc3-143">Cada linha alterada tem um número de versão associado.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-143">Each changed row has a version number that is associated with it.</span></span> <span data-ttu-id="0ebc3-144">Quando uma solicitação é enviada a um aplicativo para consultar as alterações, uma função é chamada para fornecer um número de versão.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-144">When a request is sent to an application to query for changes, a function is called that supplies a version number.</span></span> <span data-ttu-id="0ebc3-145">A função retorna informações sobre todas as alterações que foram feitas desde aquela versão.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-145">The function returns information about all the changes that have been made since that version.</span></span> <span data-ttu-id="0ebc3-146">De alguma maneira, a versão de controle de alterações é semelhante ao conceito do tipo de dados de `rowversion`.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-146">In some ways, change tracking version is similar in concept to the `rowversion` data type.</span></span>  
  
### <a name="validating-the-last-synchronized-version"></a><span data-ttu-id="0ebc3-147">Validando a última versão sincronizada</span><span class="sxs-lookup"><span data-stu-id="0ebc3-147">Validating the Last Synchronized Version</span></span>  
 <span data-ttu-id="0ebc3-148">As informações sobre as alterações são mantidas por um período limitado.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-148">Information about changes is maintained for a limited time.</span></span> <span data-ttu-id="0ebc3-149">A duração desse tempo e controlada pelo parâmetro CHANGE_RETENTION que pode ser especificado como parte de ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-149">The length of time is controlled by the CHANGE_RETENTION parameter that can be specified as part of the ALTER DATABASE.</span></span>  
  
 <span data-ttu-id="0ebc3-150">Tenha em mente que o tempo especificado em CHANGE_RETENTION determina a frequência com que todos os aplicativos solicitarão alterações do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-150">Be aware that the time specified for CHANGE_RETENTION determines how frequently all applications must request changes from the database.</span></span> <span data-ttu-id="0ebc3-151">Se o valor de *last_synchronization_version* em um aplicativo for anterior ao valor da versão de sincronização mínima válida para uma tabela, esse aplicativo não poderá executar a enumeração de alteração válida.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-151">If an application has a value for *last_synchronization_version* that is older than the minimum valid synchronization version for a table, that application cannot perform valid change enumeration.</span></span> <span data-ttu-id="0ebc3-152">Isso ocorre porque algumas informações de alteração podem ser apagadas.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-152">This is because some change information might have been cleaned up.</span></span> <span data-ttu-id="0ebc3-153">Antes que um aplicativo possa obter as alterações usando a função CHANGETABLE(CHANGES...), ele deve validar o valor de *last_synchronization_version* para passá-lo para CHANGETABLE(CHANGES ...). Se o valor de *last_synchronization_version* não for válido, esse aplicativo deverá reinicializar todos os dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-153">Before an application obtains changes by using CHANGETABLE(CHANGES ...), the application must validate the value for *last_synchronization_version* that it plans to pass to CHANGETABLE(CHANGES ...). If the value of *last_synchronization_version* is not valid, that application must reinitialize all the data.</span></span>  
  
 <span data-ttu-id="0ebc3-154">O exemplo a seguir mostra como verificar a validade do valor de `last_synchronization_version` para cada tabela.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-154">The following example shows how to verify the validity of the value of `last_synchronization_version` for each table.</span></span>  
  
```sql  
-- Check individual table.  
IF (@last_synchronization_version < CHANGE_TRACKING_MIN_VALID_VERSION(  
                                   OBJECT_ID('SalesLT.Product')))  
BEGIN  
  -- Handle invalid version and do not enumerate changes.  
  -- Client must be reinitialized.  
END  
```  
  
 <span data-ttu-id="0ebc3-155">Como mostra o exemplo a seguir, a validade do valor de `last_synchronization_version` pode ser verificada em comparação a todas as tabelas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-155">As the following example shows, the validity of the value of `last_synchronization_version` can be checked against all tables in the database.</span></span>  
  
```sql  
-- Check all tables with change tracking enabled  
IF EXISTS (  
  SELECT COUNT(*) FROM sys.change_tracking_tables  
  WHERE min_valid_version > @last_synchronization_version )  
BEGIN  
  -- Handle invalid version & do not enumerate changes  
  -- Client must be reinitialized  
END  
```  
  
### <a name="using-column-tracking"></a><span data-ttu-id="0ebc3-156">Usando o rastreamento de coluna</span><span class="sxs-lookup"><span data-stu-id="0ebc3-156">Using Column Tracking</span></span>  
 <span data-ttu-id="0ebc3-157">O rastreamento de coluna permite que os aplicativos obtenham dados apenas das colunas que foram alteradas em vez de toda a linha.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-157">Column tracking enables applications to obtain the data for only the columns that have changed instead of the whole row.</span></span> <span data-ttu-id="0ebc3-158">Por exemplo, considere o cenário no qual uma tabela tem uma ou mais colunas extensas, mas que raramente têm alterações, e outras colunas com alterações frequentes.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-158">For example, consider the scenario in which a table has one or more columns that are large, but rarely change; and also has other columns that frequently change.</span></span> <span data-ttu-id="0ebc3-159">Com o rastreamento de coluna, um aplicativo pode determinar se apenas uma linha foi alterada e se seria preciso sincronizar todos os dados da coluna maior.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-159">Without column tracking, an application can only determine that a row has changed and would have to synchronize all the data that includes the large column data.</span></span> <span data-ttu-id="0ebc3-160">Entretanto, por meio do rastreamento de coluna, um aplicativo poderá determinar se os dados da coluna grande foram alterados e sincronizar apenas os dados, caso tenham sido alterados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-160">However, by using column tracking, an application can determine whether the large column data changed and only synchronize the data if it has changed.</span></span>  
  
 <span data-ttu-id="0ebc3-161">As informações de acompanhamento de coluna são exibidas na coluna SYS_CHANGE_COLUMNS que é retornada pela função CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="0ebc3-161">Column tracking information appears in the SYS_CHANGE_COLUMNS column that is returned by the CHANGETABLE(CHANGES ...) function.</span></span>  
  
 <span data-ttu-id="0ebc3-162">O rastreamento de coluna pode ser usado de forma que NULL seja retornado para uma coluna que não tenha sido alterada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-162">Column tracking can be used so that NULL is returned for a column that has not changed.</span></span> <span data-ttu-id="0ebc3-163">Se a coluna puder ser alterada para NULL, outra coluna deverá ser retornada para indicar se a coluna foi alterada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-163">If the column can be changed to NULL, a separate column must be returned to indicate whether the column changed.</span></span>  
  
 <span data-ttu-id="0ebc3-164">No exemplo a seguir, a coluna `CT_ThumbnailPhoto` será `NULL` se ela não tiver sido alterada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-164">In the following example, the `CT_ThumbnailPhoto` column will be `NULL` if that column did not change.</span></span> <span data-ttu-id="0ebc3-165">Esta coluna também deve ser `NULL` porque ela foi alterada para `NULL` - o aplicativo pode usar a coluna `CT_ThumbNailPhoto_Changed` para determinar se a coluna foi alterada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-165">This column could also be `NULL` because it was changed to `NULL` - the application can use the `CT_ThumbNailPhoto_Changed` column to determine whether the column changed.</span></span>  
  
```sql  
DECLARE @PhotoColumnId int = COLUMNPROPERTY(  
    OBJECT_ID('SalesLT.Product'),'ThumbNailPhoto', 'ColumnId')  
  
SELECT  
    CT.ProductID, P.Name, P.ListPrice, -- Always obtain values.  
    CASE  
           WHEN CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) = 1  
            THEN ThumbNailPhoto  
            ELSE NULL  
      END AS CT_ThumbNailPhoto,  
      CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) AS  
                                   CT_ThumbNailPhoto_Changed  
     CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
     CT.SYS_CHANGE_CONTEXT  
FROM  
     SalesLT.Product AS P  
INNER JOIN  
     CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
     P.ProductID = CT.ProductID AND  
     CT.SYS_CHANGE_OPERATION = 'U'  
```  
  
### <a name="obtaining-consistent-and-correct-results"></a><span data-ttu-id="0ebc3-166">Obtendo resultados consistentes e corretos</span><span class="sxs-lookup"><span data-stu-id="0ebc3-166">Obtaining Consistent and Correct Results</span></span>  
 <span data-ttu-id="0ebc3-167">Para obter os dados alterados de uma tabela é preciso seguir várias etapas.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-167">Obtaining the changed data for a table requires multiple steps.</span></span> <span data-ttu-id="0ebc3-168">Lembre-se de que podem ocorrer resultados inconsistentes ou incorretos, se determinados problemas não forem considerados e tratados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-168">Be aware that inconsistent or incorrect results could be returned if certain issues are not considered and handled.</span></span>  
  
 <span data-ttu-id="0ebc3-169">Por exemplo, para obter as alterações realizadas em uma tabela Sales e uma tabela SalesOrders, um aplicativo executaria as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-169">For example, to obtain the changes that were made to a Sales table and SalesOrders table, an application would perform the following steps:</span></span>  
  
1.  <span data-ttu-id="0ebc3-170">Validar a última versão sincronizada por meio de CHANGE_TRACKING_MIN_VALID_VERSION().</span><span class="sxs-lookup"><span data-stu-id="0ebc3-170">Validate the last synchronized version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
2.  <span data-ttu-id="0ebc3-171">Obter a versão que pode ser usada para obter a alteração na próxima vez por meio de CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="0ebc3-171">Obtain the version that can be used to obtain change the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
3.  <span data-ttu-id="0ebc3-172">Obtenha as alterações da tabela Sales usando CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="0ebc3-172">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...).</span></span>  
  
4.  <span data-ttu-id="0ebc3-173">Obtenha as alterações da tabela SalesOrders usando CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="0ebc3-173">Obtain the changes for the SalesOrders table by using CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="0ebc3-174">Dois processos estão ocorrendo no banco de dados que podem afetar os resultados retornados pelas etapas anteriores:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-174">Two processes are occurring in the database that can affect the results that are returned by the previous steps:</span></span>  
  
-   <span data-ttu-id="0ebc3-175">O processo de limpeza é executado em segundo plano e remove as informações de controle de alterações anteriores ao período de retenção especificado.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-175">The cleanup process runs in the background and removes change tracking information that is older than the specified retention period.</span></span>  
  
     <span data-ttu-id="0ebc3-176">A limpeza é um processo interno e em segundo plano que usa um período de retenção especificado quando você configura o controle de alterações para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-176">The cleanup process is a separate background process that uses the retention period that is specified when you configure change tracking for the database.</span></span> <span data-ttu-id="0ebc3-177">O problema é que o processo de limpeza pode ocorrer na hora em que a última versão de sincronização foi validada e quando a chamada para CHANGETABLE(CHANGES...) for feita.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-177">The issue is that the cleanup process can occur in the time between when the last synchronization version was validated and when the call to CHANGETABLE(CHANGES...) is made.</span></span> <span data-ttu-id="0ebc3-178">Uma última versão de sincronização que acabou de ser validada pode não ser mais válida no momento em que as alterações forem obtidas.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-178">A last synchronization version that was just valid might no longer be valid by the time the changes are obtained.</span></span> <span data-ttu-id="0ebc3-179">Portanto, talvez sejam retornados resultados incorretos.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-179">Therefore, incorrect results might be returned.</span></span>  
  
-   <span data-ttu-id="0ebc3-180">Operações de DML contínuas ocorrem nas tabelas Sales e SalesOrders, como as operações a seguir:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-180">Ongoing DML operations are occurring in the Sales and SalesOrders tables, such as the following operations:</span></span>  
  
    -   <span data-ttu-id="0ebc3-181">Alterações poderão ser feitas na tabela depois que a versão tiver sido obtida por meio de CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="0ebc3-181">Changes can be made to the tables after the version for next time has been obtained by using CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="0ebc3-182">Talvez sejam retornadas mais alterações do que o esperado.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-182">Therefore, more changes can be returned than expected.</span></span>  
  
    -   <span data-ttu-id="0ebc3-183">Uma transação pode ocorrer no período entre a chamada para obter as alterações da tabela Sales e a chamada para obter as alterações da tabela SalesOrders.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-183">A transaction could commit in the time between the call to obtain changes from the Sales table and the call to obtain changes from the SalesOrders table.</span></span> <span data-ttu-id="0ebc3-184">Entre os resultados da tabela SalesOrder pode haver um valor de chave estrangeira que não exista na tabela Sales.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-184">Therefore, the results for the SalesOrder table could have foreign key value that does not exist in the Sales table.</span></span>  
  
 <span data-ttu-id="0ebc3-185">Para superar os desafios previamente listados, é recomendável usar o isolamento de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-185">To overcome the previously listed challenges, we recommend that you use snapshot isolation.</span></span> <span data-ttu-id="0ebc3-186">Isso ajudará a garantir a consistência das informações de alterações e evitará situações de competição relacionadas à tarefa de limpeza em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-186">This will help to ensure consistency of change information and avoid race conditions that are related to the background cleanup task.</span></span> <span data-ttu-id="0ebc3-187">Se você optar por não usar as transações de instantâneo, o desenvolvendo um aplicativo que usa controle de alterações poderá exigeer mais esforço.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-187">If you do not use snapshot transactions, developing an application that uses change tracking could require significantly more effort.</span></span>  
  
#### <a name="using-snapshot-isolation"></a><span data-ttu-id="0ebc3-188">Usando o isolamento de instantâneo</span><span class="sxs-lookup"><span data-stu-id="0ebc3-188">Using Snapshot Isolation</span></span>  
 <span data-ttu-id="0ebc3-189">O controle de alterações foi projetado para funcionar bem com o isolamento de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-189">Change tracking has been designed to work well with snapshot isolation.</span></span> <span data-ttu-id="0ebc3-190">O isolamento de instantâneo deve estar habilitado para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-190">Snapshot isolation must be enabled for the database.</span></span> <span data-ttu-id="0ebc3-191">Todas as etapas são obrigatórias para obter as alterações que devem estar incluídas em uma transação de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-191">All the steps that are required to obtain changes must be included inside a snapshot transaction.</span></span> <span data-ttu-id="0ebc3-192">Isso garantirá que todas as alterações realizadas nos dados durante a obtenção de alterações não estarão visíveis às consultas dentro da transação de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-192">This will ensure that all changes that are made to data while obtaining changes will not be visible to the queries inside the snapshot transaction.</span></span>  
  
 <span data-ttu-id="0ebc3-193">Para obter dados dentro de uma transação de instantâneo, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-193">To obtain data inside a snapshot transaction, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="0ebc3-194">Defina o nível de isolamento da transação para o instantâneo e inicie uma transação.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-194">Set the transaction isolation level to snapshot and start a transaction.</span></span>  
  
2.  <span data-ttu-id="0ebc3-195">Valide a última versão de sincronização usando a função CHANGE_TRACKING_MIN_VALID_VERSION().</span><span class="sxs-lookup"><span data-stu-id="0ebc3-195">Validate the last synchronization version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
3.  <span data-ttu-id="0ebc3-196">Obtenha a versão a ser usada na próxima vez por meio de CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="0ebc3-196">Obtain the version to be used the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
4.  <span data-ttu-id="0ebc3-197">Obtenha as alterações da tabela Sales usando CHANGETABLE(CHANGES ...)</span><span class="sxs-lookup"><span data-stu-id="0ebc3-197">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...)</span></span>  
  
5.  <span data-ttu-id="0ebc3-198">Obtenha as alterações da tabela SalesOrders usando CHANGETABLE(CHANGES ...)</span><span class="sxs-lookup"><span data-stu-id="0ebc3-198">Obtain the changes for the Salesorders table by using CHANGETABLE(CHANGES ...)</span></span>  
  
6.  <span data-ttu-id="0ebc3-199">Confirme a transação.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-199">Commit the transaction.</span></span>  
  
 <span data-ttu-id="0ebc3-200">Alguns pontos a serem lembrados, uma vez que todas as etapas para obter alterações estão em uma transação de instantâneo:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-200">Some points to remember as all steps to obtain changes are inside a snapshot transaction:</span></span>  
  
-   <span data-ttu-id="0ebc3-201">Se a limpeza ocorrer depois que a última versão de sincronização for validada, os resultados da função CHANGETABLE(CHANGES ...) ainda serão válidos, pois as operações de exclusão executadas pela limpeza não serão visíveis dentro da transação.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-201">If cleanup occurs after the last synchronization version is validated, the results from CHANGETABLE(CHANGES ...) will still be valid as the delete operations performed by cleanup will not be visible inside the transaction.</span></span>  
  
-   <span data-ttu-id="0ebc3-202">Todas as alterações realizadas nas tabelas Sales ou SalesOrders depois que a versão de sincronização tiver sido obtida não estarão visíveis e as chamadas para CHANGETABLE(CHANGES ...) nunca retornarão alterações com uma versão posterior àquela retornada pela função CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="0ebc3-202">Any changes that are made to the Sales table or the SalesOrders table after the next synchronization version is obtained will not be visible, and the calls to CHANGETABLE(CHANGES ...) will never return changes with a version later than that returned by CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="0ebc3-203">A consistência entre as tabelas Sales e SalesOrders também será mantida porque as transações que foram confirmadas no período entre as chamadas para CHANGETABLE(CHANGES ...) não estarão visíveis.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-203">Consistency between the Sales table and the SalesOrders table will also be maintained, because the transactions that were committed in the time between calls to CHANGETABLE(CHANGES ...) will not be visible.</span></span>  
  
 <span data-ttu-id="0ebc3-204">O exemplo a seguir mostra como o isolamento de instantâneo é habilitado para um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-204">The following example shows how snapshot isolation is enabled for a database.</span></span>  
  
```sql  
-- The database must be configured to enable snapshot isolation.  
ALTER DATABASE AdventureWorksLT  
    SET ALLOW_SNAPSHOT_ISOLATION ON;  
```  
  
 <span data-ttu-id="0ebc3-205">Uma transação de instantâneo é usada a seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-205">A snapshot transaction is used as follows:</span></span>  
  
```sql  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
  -- Verify that version of the previous synchronization is valid.  
  -- Obtain the version to use next time.  
  -- Obtain changes.  
COMMIT TRAN  
```  
  
 <span data-ttu-id="0ebc3-206">Para obter mais informações sobre transações de instantâneos, veja [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0ebc3-206">For more information about snapshot transactions, see [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
#### <a name="alternatives-to-using-snapshot-isolation"></a><span data-ttu-id="0ebc3-207">Alternativas para usar o isolamento de instantâneo</span><span class="sxs-lookup"><span data-stu-id="0ebc3-207">Alternatives to Using Snapshot Isolation</span></span>  
 <span data-ttu-id="0ebc3-208">Existem alternativas para o uso do isolamento de instantâneo, mas elas exigem mais trabalho para certificar-se de que todos os requisitos do aplicativos sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-208">There are alternatives to using snapshot isolation, but they require more work to make sure all application requirements are met.</span></span> <span data-ttu-id="0ebc3-209">Para verificar se *last_synchronization_version* é válido e se os dados não foram removidos pelo processo de limpeza antes de as alterações serem obtidas, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-209">To make sure the *last_synchronization_version* is valid and data is not removed by the cleanup process before changes are obtained, do the following:</span></span>  
  
1.  <span data-ttu-id="0ebc3-210">Verificar *last_synchronization_version* depois das chamadas para CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="0ebc3-210">Check *last_synchronization_version* after the calls to CHANGETABLE().</span></span>  
  
2.  <span data-ttu-id="0ebc3-211">Verifique *last_synchronization_version* como parte de cada consulta para obter alterações usando CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="0ebc3-211">Check *last_synchronization_version* as part of each query to obtain changes by using CHANGETABLE().</span></span>  
  
 <span data-ttu-id="0ebc3-212">As alterações podem ocorrer depois da versão de sincronização para a próxima enumeração for obtida.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-212">Changes can occur after the synchronization version for the next enumeration has been obtained.</span></span> <span data-ttu-id="0ebc3-213">Existem duas maneiras para controlar essa situação:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-213">There are two ways to handle this situation.</span></span> <span data-ttu-id="0ebc3-214">A opção que é usada depende do aplicativo e como ele pode controlar os efeitos colaterais de cada abordagem:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-214">The option that is used depends on the application and how it can handle the side-effects of each approach:</span></span>  
  
-   <span data-ttu-id="0ebc3-215">Ignore as alterações cuja versão é maior que a nova versão de sincronização.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-215">Ignore changes that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="0ebc3-216">O efeito colateral dessa abordagem é fazer com que uma nova linha ou uma linha atualizada seja ignorada caso ela tenha sido criada ou atualizada antes da nova versão de sincronização, exceto a atualização posterior.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-216">This approach has the side effect that a new or updated row would be skipped if it was created or updated before the new synchronization version, but then updated afterward.</span></span> <span data-ttu-id="0ebc3-217">Se houver uma nova linha, poderá ocorrer um problema de integridade referencial caso tenha existido uma linha em outra tabela que tenha sido criada com referência à linha ignorada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-217">If there is a new row, a referential integrity problem might occur if there was a row in another table that was created that referenced the skipped row.</span></span> <span data-ttu-id="0ebc3-218">Se houver uma linha existente atualizada, a linha será ignorada e não será sincronizada até o próximo período.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-218">If there is an updated existing row, the row will be skipped and not synchronized until the next time.</span></span>  
  
-   <span data-ttu-id="0ebc3-219">Inclua todas as alterações, até mesmo aquelas que contêm uma versão maior que a nova versão de sincronização.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-219">Include all changes, even those that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="0ebc3-220">As linhas com uma versão maior que a nova versão de sincronização serão obtidas na próxima sincronização.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-220">The rows that have a version larger than the new synchronization version will be obtained again on the next synchronization.</span></span> <span data-ttu-id="0ebc3-221">Isso deve ser esperado e controlado pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-221">This must be expected and handled by the application.</span></span>  
  
 <span data-ttu-id="0ebc3-222">Além das duas opções anteriores, você pode criar uma abordagem que combine ambas as opções, dependendo da operação.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-222">In addition to the previous two options, you can devise approach that combines both options, depending on the operation.</span></span> <span data-ttu-id="0ebc3-223">Por exemplo, você poder desejar uma aplicação na qual seja melhor ignorar as alterações mais recentes do que a próxima versão de sincronização na qual a fila foi criada ou excluída, mas as atualizações não foram ignoradas.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-223">For example, you might want an application for which it is best to ignore changes newer than the next synchronization version in which the row was created or deleted, but updates are not ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ebc3-224">Ao optar pela abordagem que funcionará com o aplicativo quando você estiver usando o controle de alterações (ou qualquer mecanismo de controle personalizado), será preciso considerar uma análise significativa.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-224">Choosing the approach that will work for the application when you are using change tracking (or any custom tracking mechanism), requires significant analysis.</span></span> <span data-ttu-id="0ebc3-225">Portanto, é muito mais simples usar o isolamento de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-225">Therefore, it is much simpler to use snapshot isolation.</span></span>  
  
##  <a name="how-change-tracking-handles-changes-to-a-database"></a><a name="Handles"></a><span data-ttu-id="0ebc3-226">Como Controle de Alterações manipula alterações em um banco de dados</span><span class="sxs-lookup"><span data-stu-id="0ebc3-226">How Change Tracking Handles Changes to a Database</span></span>  
 <span data-ttu-id="0ebc3-227">Alguns aplicativos que usam controle de alterações executam sincronização de duas vias com outro repositório de dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-227">Some applications that use change tracking perform two-way synchronization with another data store.</span></span> <span data-ttu-id="0ebc3-228">Isto é, as alterações que são feitas no banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são atualizadas no outro armazenamento de dados, e as alterações feitas no outro repositório são atualizadas no banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ebc3-228">That is, changes that are made in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database are updated in the other data store, and changes that are made in the other store are updated in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="0ebc3-229">Quando um aplicativo atualiza o banco de dados local com alteração de outro armazenamento de dados, o aplicativo deve executar as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-229">When an application updates the local database with changes from another data store, the application must perform the following operations:</span></span>  
  
-   <span data-ttu-id="0ebc3-230">Verifique os conflitos.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-230">Check for conflicts.</span></span>  
  
     <span data-ttu-id="0ebc3-231">Um conflito acontece quando os mesmos dados são alterados ao mesmo tempo em ambos os armazenamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-231">A conflict occurs when the same data is changed at the same time in both data stores.</span></span> <span data-ttu-id="0ebc3-232">O aplicativo deve poder verificar um conflito e obter informações suficientes para permitir a solução do conflito.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-232">The application must be able to check for a conflict and obtain enough information to enable the conflict to be resolved.</span></span>  
  
-   <span data-ttu-id="0ebc3-233">Armazene informações de contexto de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-233">Store application context information.</span></span>  
  
     <span data-ttu-id="0ebc3-234">O aplicativo armazena dados que têm as informações de controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-234">The application stores data that has the change tracking information.</span></span> <span data-ttu-id="0ebc3-235">Essas informações estariam disponíveis junto com outras informações de controle de alterações quando foram obtidas alterações do banco de dados local.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-235">This information would be available together with other change tracking information when changes were obtained from the local database.</span></span> <span data-ttu-id="0ebc3-236">Um exemplo comum dessas informações de contexto é um identificador para o repositório de dados que era a origem da alteração.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-236">A common example of this contextual information is an identifier for the data store that was the source of the change.</span></span>  
  
 <span data-ttu-id="0ebc3-237">Para executar as operações anteriores, um aplicativo de sincronização pode usar as funções a seguir:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-237">To perform the previous operations, a synchronization application can use the following functions:</span></span>  
  
-   <span data-ttu-id="0ebc3-238">CHANGETABLE(VERSION...)</span><span class="sxs-lookup"><span data-stu-id="0ebc3-238">CHANGETABLE(VERSION...)</span></span>  
  
     <span data-ttu-id="0ebc3-239">Quando um aplicativo estiver fazendo alterações, poderá usar esta função para verificar conflitos.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-239">When an application is making changes, it can use this function to check for conflicts.</span></span> <span data-ttu-id="0ebc3-240">A função obtém as últimas informações de controle de alterações por uma linha especificada em uma tabela de alteração rastreada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-240">The function obtains the latest change tracking information for a specified row in a change tracked table.</span></span> <span data-ttu-id="0ebc3-241">As informações do controle de alterações incluem a versão da última vez que a linha foi alterada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-241">The change tracking information includes the version of the row that was last changed.</span></span> <span data-ttu-id="0ebc3-242">Essa informação permite que um aplicativo determine se a linha foi alterada, depois da última vez que o aplicativo foi sincronizado.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-242">This information enables an application to determine whether the row was changed after the last time that the application was synchronized.</span></span>  
  
-   <span data-ttu-id="0ebc3-243">WITH CHANGE_TRACKING_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="0ebc3-243">WITH CHANGE_TRACKING_CONTEXT</span></span>  
  
     <span data-ttu-id="0ebc3-244">Um aplicativo pode usar esta cláusula para armazenar dados de contexto.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-244">An application can use this clause to store context data.</span></span>  
  
### <a name="checking-for-conflicts"></a><span data-ttu-id="0ebc3-245">Verificando conflitos</span><span class="sxs-lookup"><span data-stu-id="0ebc3-245">Checking for Conflicts</span></span>  
 <span data-ttu-id="0ebc3-246">Em um cenário de sincronização de duas vias, o aplicativo cliente deve determinar se uma linha não foi atualizada desde que o aplicativo obteve as últimas alterações.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-246">In a two-way synchronization scenario, the client application must determine whether a row has not been updated since the application last obtained the changes.</span></span>  
  
 <span data-ttu-id="0ebc3-247">O exemplo a seguir mostra como usar a função CHANGETABLE(VERSION ...) para verificar conflitos do modo mais eficiente, sem uma consulta separada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-247">The following example shows how to use the CHANGETABLE(VERSION ...) function to check for conflicts in the most efficient way, without a separate query.</span></span> <span data-ttu-id="0ebc3-248">No exemplo, `CHANGETABLE(VERSION ...)` determina o `SYS_CHANGE_VERSION` para a linha especificada por `@product id`.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-248">In the example, `CHANGETABLE(VERSION ...)` determines the `SYS_CHANGE_VERSION` for the row specified by `@product id`.</span></span> <span data-ttu-id="0ebc3-249">`CHANGETABLE(CHANGES ...)` pode obter as mesmas informações, mas isso seria menos eficiente.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-249">`CHANGETABLE(CHANGES ...)` can obtain the same information, but that would be less efficient.</span></span> <span data-ttu-id="0ebc3-250">Se o valor de `SYS_CHANGE_VERSION` para a linha for maior que o valor de `@last_sync_version`, haverá um conflito.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-250">If the value of `SYS_CHANGE_VERSION` for the row is larger than the value of `@last_sync_version`, there is a conflict.</span></span> <span data-ttu-id="0ebc3-251">Se houver um conflito, a linha não será atualizada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-251">If there is a conflict, the row will not be updated.</span></span> <span data-ttu-id="0ebc3-252">A verificação `ISNULL()` é necessária porque não poderia haver nenhuma informações de alteração disponível para a linha.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-252">The `ISNULL()` check is required because there might be no change information available for the row.</span></span> <span data-ttu-id="0ebc3-253">Nenhuma informação de alteração existiria se a linha não tivesse sido atualizada, visto que o controle de alteração estava habilitado ou a informação de alteração foi limpa.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-253">No change information would exist if the row had not been updated since change tracking was enabled or since the change information was cleaned up.</span></span>  
  
```sql  
-- Assumption: @last_sync_version has been validated.  
  
UPDATE  
    SalesLT.Product  
SET  
    ListPrice = @new_listprice  
FROM  
    SalesLT.Product AS P  
WHERE  
    ProductID = @product_id AND  
    @last_sync_version >= ISNULL (  
        SELECT CT.SYS_CHANGE_VERSION  
        FROM CHANGETABLE(VERSION SalesLT.Product,  
                        (ProductID), (P.ProductID)) AS CT),  
        0)  
```  
  
 <span data-ttu-id="0ebc3-254">O código a seguir pode verificar a conta de linha atualizada e identificar mais informações sobre o conflito.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-254">The following code can check the updated row count and can identify more information about the conflict.</span></span>  
  
```sql  
-- If the change cannot be made, find out more information.  
IF (@@ROWCOUNT = 0)  
BEGIN  
    -- Obtain the complete change information for the row.  
    SELECT  
        CT.SYS_CHANGE_VERSION, CT.SYS_CHANGE_CREATION_VERSION,  
        CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS  
    FROM  
        CHANGETABLE(CHANGES SalesLT.Product, @last_sync_version) AS CT  
    WHERE  
        CT.ProductID = @product_id;  
  
    -- Check CT.SYS_CHANGE_VERSION to verify that it really was a conflict.  
    -- Check CT.SYS_CHANGE_OPERATION to determine the type of conflict:  
    -- update-update or update-delete.  
    -- The row that is specified by @product_id might no longer exist   
    -- if it has been deleted.  
END  
```  
  
### <a name="setting-context-information"></a><span data-ttu-id="0ebc3-255">Configurando informações de contexto</span><span class="sxs-lookup"><span data-stu-id="0ebc3-255">Setting Context Information</span></span>  
 <span data-ttu-id="0ebc3-256">Usando a cláusula WITH CHANGE_TRACKING_CONTEXT, um aplicativo pode armazenar informações de contexto junto com as informações de alteração.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-256">By using the WITH CHANGE_TRACKING_CONTEXT clause, an application can store context information together with the change information.</span></span> <span data-ttu-id="0ebc3-257">Essas informações podem ser obtidas na coluna SYS_CHANGE_CONTEXT que é retornada por CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="0ebc3-257">This information can then be obtained from the SYS_CHANGE_CONTEXT column that is returned by CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="0ebc3-258">Informações de contexto são normalmente usadas para identificar a origem das alterações.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-258">Context information is typically used to identify the source of the changes.</span></span> <span data-ttu-id="0ebc3-259">Se a origem da alteração puder ser identificada, aquela informação poderá ser usada por um repositório de dados para evitar a obtenção de alterações quando ele for novamente sincronizado.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-259">If the source of the change can be identified, that information can be used by a data store to avoid obtaining changes when it synchronizes again.</span></span>  
  
```sql  
  -- Try to update the row and check for a conflict.  
  WITH CHANGE_TRACKING_CONTEXT (@source_id)  
  UPDATE  
     SalesLT.Product  
  SET  
      ListPrice = @new_listprice  
  FROM  
      SalesLT.Product AS P  
  WHERE  
     ProductID = @product_id AND  
     @last_sync_version >= ISNULL (  
         (SELECT CT.SYS_CHANGE_VERSION FROM CHANGETABLE(VERSION SalesLT.Product,  
         (ProductID), (P.ProductID)) AS CT),  
         0)  
```  
  
### <a name="ensuring-consistent-and-correct-results"></a><span data-ttu-id="0ebc3-260">Assegurando resultados consistentes e corretos</span><span class="sxs-lookup"><span data-stu-id="0ebc3-260">Ensuring Consistent and Correct Results</span></span>  
 <span data-ttu-id="0ebc3-261">Um aplicativo deve considerar o processo de limpeza ao validar o valor de @last_sync_version.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-261">An application must consider the cleanup process when it validates the value of @last_sync_version.</span></span> <span data-ttu-id="0ebc3-262">Isso é porque dados podem ter sido removidos depois que CHANGE_TRACKING_MIN_VALID_VERSION () foi chamado, mas antes que a atualização fosse feita.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-262">This is because data could have been removed after CHANGE_TRACKING_MIN_VALID_VERSION() was called, but before the update was made.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0ebc3-263">Recomendamos que você use isolamento de instantâneo e faça as alterações dentro de uma transação de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-263">We recommend that you use snapshot isolation and make the changes within a snapshot transaction.</span></span>  
  
```sql  
-- Prerequisite is to ensure ALLOW_SNAPSHOT_ISOLATION is ON for the database.  
  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
    -- Verify that last_sync_version is valid.  
    IF (@last_sync_version <  
CHANGE_TRACKING_MIN_VALID_VERSION(OBJECT_ID('SalesLT.Product')))  
    BEGIN  
       RAISERROR (N'Last_sync_version too old', 16, -1);  
    END  
    ELSE  
    BEGIN  
        -- Try to update the row.  
        -- Check @@ROWCOUNT and check for a conflict.  
    END  
COMMIT TRAN  
```  
  
> [!NOTE]  
>  <span data-ttu-id="0ebc3-264">Há uma possibilidade de que a linha, que está sendo atualizada dentro da transação de instantâneo, possa ter sido atualizada em uma outra transação depois que a transação de instantâneo foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-264">There is a possibility that the row being updated within the snapshot transaction could have been updated in another transaction after the snapshot transaction was started.</span></span> <span data-ttu-id="0ebc3-265">Nesse caso, um conflito de atualização de isolamento do instantâneo acontecerá e a transação será encerrada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-265">In this case, a snapshot isolation update conflict will occur and lead to the transaction being terminated.</span></span> <span data-ttu-id="0ebc3-266">Se isso acontecer, tente novamente a atualização.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-266">If this happens, retry the update.</span></span> <span data-ttu-id="0ebc3-267">Isso levará então a detecção de um conflito do controle de alterações e nenhuma linha será alterada.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-267">This will then lead to a change tracking conflict being detected and no rows being changed.</span></span>  
  
##  <a name="change-tracking-and-data-restore"></a><a name="DataRestore"></a><span data-ttu-id="0ebc3-268">Controle de Alterações e restauração de dados</span><span class="sxs-lookup"><span data-stu-id="0ebc3-268">Change Tracking and Data Restore</span></span>  
 <span data-ttu-id="0ebc3-269">Os aplicativos que requerem sincronização devem considerar o caso de um banco de dados, com o controle de alterações habilitado, reverter a uma versão anterior dos dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-269">Applications that require synchronization must consider the case in which a database that has change tracking enabled reverts to an earlier version of the data.</span></span> <span data-ttu-id="0ebc3-270">Isso pode ocorrer quando um banco de dados é restaurado de um backup, quando há failover de um espelho de banco de dados assíncrono ou quando há uma falha ao usar o envio de logs.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-270">This can occur after a database is restored from a backup, when there is a failover to an asynchronous database mirror, or when there is a failure when using log shipping.</span></span> <span data-ttu-id="0ebc3-271">O cenário a seguir ilustra o assunto:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-271">The following scenario illustrates the issue:</span></span>  
  
1.  <span data-ttu-id="0ebc3-272">A tabela T1 tem as alterações controladas, e a versão válida mínima para tabela é 50.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-272">Table T1 is change tracked, and the minimum valid version for table is 50.</span></span>  
  
2.  <span data-ttu-id="0ebc3-273">Um aplicativo cliente sincroniza dados com a versão 100 e obtém informações sobre todas as alterações entre as versões 50 e 100.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-273">A client application synchronizes data at version 100 and obtains information about all changes between versions 50 and 100.</span></span>  
  
3.  <span data-ttu-id="0ebc3-274">São feitas alterações adicionais na tabela T1 depois da versão 100.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-274">Additional changes are made to table T1 after version 100.</span></span>  
  
4.  <span data-ttu-id="0ebc3-275">Na versão 120, há uma falha e o administrador do banco de dados restaura o banco de dados com perda de dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-275">At version 120, there is a failure and the database administrator restores the database with data loss.</span></span> <span data-ttu-id="0ebc3-276">Depois da operação de restauração, a tabela contém dados até a versão 70, e a versão sincronizada mínima ainda é 50.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-276">After the restore operation, the table contains data up through version 70, and the minimum synchronized version is still 50.</span></span>  
  
     <span data-ttu-id="0ebc3-277">Isso significa que o repositório de dados sincronizado tem dados que já não existem mais no repositório de dados primário.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-277">This means that the synchronized data store has data that no longer exists in the primary data store.</span></span>  
  
5.  <span data-ttu-id="0ebc3-278">A T1 é atualizada muitas vezes.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-278">T1 is updated many times.</span></span> <span data-ttu-id="0ebc3-279">Isso traz a versão atual para 130.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-279">This brings the current version to 130.</span></span>  
  
6.  <span data-ttu-id="0ebc3-280">O aplicativo cliente é sincronizado novamente e fornece uma última versão sincronizada de 100.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-280">The client application synchronizes again and supplies a last-synchronized version of 100.</span></span> <span data-ttu-id="0ebc3-281">O cliente valida esse número com êxito porque 100 é maior do que 50.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-281">The client validates this number successfully because 100 is greater than 50.</span></span>  
  
     <span data-ttu-id="0ebc3-282">O cliente obtém alterações entre as versões 100 e 130.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-282">The client obtains changes between version 100 and 130.</span></span> <span data-ttu-id="0ebc3-283">Nesse ponto, o cliente não reconhece que as alterações entre 70 e 100 não são as mesmas de antes.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-283">At this point, the client is not aware that the changes between 70 and 100 are not the same as before.</span></span> <span data-ttu-id="0ebc3-284">Os dados no cliente e no servidor não estão sincronizados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-284">The data on the client and server are not synchronized.</span></span>  
  
 <span data-ttu-id="0ebc3-285">Observe que, se o banco de dados foi recuperado em um ponto depois da versão 100, não haverá problemas com a sincronização.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-285">Note that if the database was recovered to a point after version 100, there would be no problems with synchronization.</span></span> <span data-ttu-id="0ebc3-286">O cliente e o servidor sincronizarão os dados corretamente durante o próximo intervalo de sincronização.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-286">The client and server would synchronize data correctly during the next synchronization interval.</span></span>  
  
 <span data-ttu-id="0ebc3-287">O controle de alterações não oferece suporte para a recuperação da perda de dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-287">Change tracking does not provide support for recovering from the loss of data.</span></span> <span data-ttu-id="0ebc3-288">No entanto, há duas opções para detectar esses problemas de sincronização:</span><span class="sxs-lookup"><span data-stu-id="0ebc3-288">However, there are two options for detecting these types of synchronization issues:</span></span>  
  
-   <span data-ttu-id="0ebc3-289">Armazene um ID da versão do banco de dados no servidor e atualize esse valor sempre que o banco de dados for recuperado ou perder dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-289">Store a database version ID on the server, and update this value whenever a database is recovered or otherwise loses data.</span></span> <span data-ttu-id="0ebc3-290">Cada aplicativo cliente armazenará o ID, e cada cliente terá de validar esse ID quando sincronizar os dados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-290">Each client application would store the ID, and each client would have to validate this ID when it synchronizes data.</span></span> <span data-ttu-id="0ebc3-291">Se ocorrer perda de dados, os IDs serão incompatíveis, e os clientes serão reinicializados.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-291">If data loss occurs, the IDs will not match and the clients would reinitialize.</span></span> <span data-ttu-id="0ebc3-292">Um aspecto negativo é que, se a perda de dados não tiver ultrapassado o último limite sincronizado, o cliente poderá ser reinicializado desnecessariamente.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-292">One drawback is if the data loss had not crossed the last synchronized boundary, the client might do unnecessary reinitialization.</span></span>  
  
-   <span data-ttu-id="0ebc3-293">Quando um cliente consultar alterações, registre o último número de versão de sincronização para cada cliente no servidor.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-293">When a client queries for changes, record the last synchronization version number for each client on the server.</span></span> <span data-ttu-id="0ebc3-294">Se houver um problema com os dados, os últimos números de versão sincronizados não serão compatíveis.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-294">If there is a problem with the data, the last synchronized version numbers would not match.</span></span> <span data-ttu-id="0ebc3-295">Isso indica que é necessária uma reinicialização.</span><span class="sxs-lookup"><span data-stu-id="0ebc3-295">This indicates that a reinitialization is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebc3-296">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ebc3-296">See Also</span></span>  
 <span data-ttu-id="0ebc3-297">[Controle de alterações de dados &#40;SQL Server&#41;](../track-changes/track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0ebc3-297">[Track Data Changes &#40;SQL Server&#41;](../track-changes/track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="0ebc3-298">[Sobre o controle de alterações &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0ebc3-298">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="0ebc3-299">[Gerenciar Controle de Alterações &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0ebc3-299">[Manage Change Tracking &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="0ebc3-300">[Habilitar e desabilitar Controle de Alterações &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0ebc3-300">[Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="0ebc3-301">[&#41;CHANGEtable &#40;Transact-SQL](/sql/relational-databases/system-functions/changetable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ebc3-301">[CHANGETABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/changetable-transact-sql) </span></span>  
 <span data-ttu-id="0ebc3-302">[&#41;&#40;Transact-SQL de CHANGE_TRACKING_MIN_VALID_VERSION](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ebc3-302">[CHANGE_TRACKING_MIN_VALID_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span></span>  
 <span data-ttu-id="0ebc3-303">[&#41;&#40;Transact-SQL de CHANGE_TRACKING_CURRENT_VERSION](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ebc3-303">[CHANGE_TRACKING_CURRENT_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span></span>  
 [<span data-ttu-id="0ebc3-304">WITH CHANGE_TRACKING_CONTEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0ebc3-304">WITH CHANGE_TRACKING_CONTEXT &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/with-change-tracking-context-transact-sql)  
  
  
