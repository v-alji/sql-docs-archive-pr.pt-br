---
title: Compilação nativa de tabelas e procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5880fbd9-a23e-464a-8b44-09750eeb2dad
author: rothja
ms.author: jroth
ms.openlocfilehash: 32c5b04610d894e06278fbeecdaf3bbebe850d60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575123"
---
# <a name="native-compilation-of-tables-and-stored-procedures"></a><span data-ttu-id="aab58-102">Compilação nativa de tabelas e procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="aab58-102">Native Compilation of Tables and Stored Procedures</span></span>
  <span data-ttu-id="aab58-103">O OLTP na memória apresenta o conceito de compilação nativa.</span><span class="sxs-lookup"><span data-stu-id="aab58-103">In-Memory OLTP introduces the concept of native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aab58-104">pode compilar nativamente procedimentos armazenados que acessam tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="aab58-104">can natively compile stored procedures that access memory-optimized tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aab58-105">também pode compilar nativamente tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="aab58-105">is also able to natively compile memory-optimized tables.</span></span> <span data-ttu-id="aab58-106">A compilação nativa permite o acesso mais rápido a dados e a execução mais eficiente de consultas, em comparação ao [!INCLUDE[tsql](../../includes/tsql-md.md)]interpretado (tradicional).</span><span class="sxs-lookup"><span data-stu-id="aab58-106">Native compilation allows faster data access and more efficient query execution than interpreted (traditional) [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="aab58-107">A compilação nativa de tabelas e procedimentos armazenados gera DLLs.</span><span class="sxs-lookup"><span data-stu-id="aab58-107">Native compilation of tables and stored procedures produce DLLs.</span></span>  
  
 <span data-ttu-id="aab58-108">A compilação nativa de tipos de tabelas com otimização de memória também tem suporte.</span><span class="sxs-lookup"><span data-stu-id="aab58-108">Native compilation of memory optimized table types is also supported.</span></span> <span data-ttu-id="aab58-109">Para obter mais informações, consulte [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span><span class="sxs-lookup"><span data-stu-id="aab58-109">For more information, see [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span></span>  
  
 <span data-ttu-id="aab58-110">A compilação nativa refere-se ao processo de converter construções de programação em código nativo, que consiste em instruções de processador, dispensando compilação ou interpretação adicional.</span><span class="sxs-lookup"><span data-stu-id="aab58-110">Native compilation refers to the process of converting programming constructs to native code, consisting of processor instructions without the need for further compilation or interpretation.</span></span>  
  
 <span data-ttu-id="aab58-111">OLTP em memória compila tabelas com otimização de memória quando elas são criadas e procedimentos armazenados compilados nativamente quando são carregados para DLLs nativos.</span><span class="sxs-lookup"><span data-stu-id="aab58-111">In-Memory OLTP compiles memory-optimized tables when they are created, and natively compiled stored procedures when they are loaded to native DLLs.</span></span> <span data-ttu-id="aab58-112">Além disso, as DLLs são recompiladas após a reinicialização de um banco de dados ou servidor.</span><span class="sxs-lookup"><span data-stu-id="aab58-112">In addition, the DLLs are recompiled after a database or server restart.</span></span> <span data-ttu-id="aab58-113">As informações necessárias para recriar as DLLs são armazenadas nos metadados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aab58-113">The information necessary to recreate the DLLs is stored in the database metadata.</span></span> <span data-ttu-id="aab58-114">As DLLs não fazem parte do banco de dados, embora elas estejam associadas ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aab58-114">The DLLs are not part of the database, though they are associated with the database.</span></span> <span data-ttu-id="aab58-115">Por exemplo, as DLLs não são incluídas nos backups de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="aab58-115">For example, the DLLs are not included in database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aab58-116">Tabelas com otimização de memória são recompiladas durante uma reinicialização do servidor.</span><span class="sxs-lookup"><span data-stu-id="aab58-116">Memory-optimized tables are recompiled during a server restart.</span></span> <span data-ttu-id="aab58-117">Para acelerar a recuperação do banco de dados, procedimentos armazenados compilados nativamente não são recompilados durante uma reinicialização do servidor, mas no momento da primeira execução.</span><span class="sxs-lookup"><span data-stu-id="aab58-117">To speed up database recovery, natively compiled stored procedures are not recompiled during a server restart, they are compiled at the time of first execution.</span></span> <span data-ttu-id="aab58-118">Como resultado dessa compilação adiada, procedimentos de armazenamento compilados nativamente aparecem apenas ao chamar [sys.dm_os_loaded_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) após a primeira execução.</span><span class="sxs-lookup"><span data-stu-id="aab58-118">As a result of this deferred compilation, natively compiled stored procedures only appear when calling [sys.dm_os_loaded_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) after first execution.</span></span>  
  
## <a name="maintenance-of-in-memory-oltp-dlls"></a><span data-ttu-id="aab58-119">Manutenção das DLLs do OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="aab58-119">Maintenance of In-Memory OLTP DLLs</span></span>  
 <span data-ttu-id="aab58-120">A consulta a seguir mostra todas as DLLs de tabela e procedimento armazenado atualmente carregadas na memória do servidor.</span><span class="sxs-lookup"><span data-stu-id="aab58-120">The following query shows all table and stored procedure DLLs currently loaded in memory on the server:</span></span>  
  
```sql  
SELECT name, description FROM sys.dm_os_loaded_modules  
where description = 'XTP Native DLL'  
```  
  
 <span data-ttu-id="aab58-121">Os administradores de banco de dados não precisam manter os arquivos gerados por um compilação nativa.</span><span class="sxs-lookup"><span data-stu-id="aab58-121">Database administrators do not need to maintain files that are generated by a native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aab58-122">remove automaticamente os arquivos gerados que não são mais necessários.</span><span class="sxs-lookup"><span data-stu-id="aab58-122">automatically removes generated files that are no longer needed.</span></span> <span data-ttu-id="aab58-123">Por exemplo, os arquivos gerados serão excluídos quando uma tabela e um procedimento armazenado forem excluídos, ou se um banco de dados for descartado.</span><span class="sxs-lookup"><span data-stu-id="aab58-123">For example, generated files will be deleted when a table and stored procedure is deleted, or if a database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aab58-124">Se a compilação falhar ou for interrompida, alguns arquivos gerados não serão removidos.</span><span class="sxs-lookup"><span data-stu-id="aab58-124">If compilation fails or is interrupted, some generated files are not removed.</span></span> <span data-ttu-id="aab58-125">Esses arquivos são deixados para trás intencionalmente, por questões de capacidade de suporte, e são removidos quando o banco de dados é descartado.</span><span class="sxs-lookup"><span data-stu-id="aab58-125">These files are intentionally left behind for supportability and are removed when the database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aab58-126">Durante a inicialização do banco de dados, o SQL Server compila DLLs para todas as tabelas necessárias para a recuperação de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aab58-126">During database startup, SQL Server compiles DLLs for all tables needed for database recovery.</span></span> <span data-ttu-id="aab58-127">Se uma tabela foi descartada logo antes de uma reinicialização do banco de dados, ainda pode haver resíduos da tabela nos arquivos do ponto de verificação ou no log de transações, de modo que a DLL para a tabela pode ser recompilada durante a inicialização do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aab58-127">If a table was dropped just prior to a database restart there can still be remnants of the table in the checkpoint files or the transaction log so the DLL for the table might be recompiled during database startup.</span></span> <span data-ttu-id="aab58-128">Após a reinicialização, a DLL será descarregada e os arquivos serão removidos pelo processo normal de limpeza.</span><span class="sxs-lookup"><span data-stu-id="aab58-128">After restart the DLL will be unloaded and the files will be removed by the normal cleanup process.</span></span>  
  
## <a name="native-compilation-of-tables"></a><span data-ttu-id="aab58-129">Compilação nativa de tabelas</span><span class="sxs-lookup"><span data-stu-id="aab58-129">Native Compilation of Tables</span></span>  
 <span data-ttu-id="aab58-130">A criação de uma tabela com otimização de memória usando a `CREATE TABLE` instrução resulta na gravação das informações de tabela nos metadados do banco de dados e nas estruturas de tabela e índice criadas na memória.</span><span class="sxs-lookup"><span data-stu-id="aab58-130">Creating a memory-optimized table using the `CREATE TABLE` statement results in the table information being written to the database metadata and the table and index structures created in memory.</span></span> <span data-ttu-id="aab58-131">A tabela também será compilada em uma DLL.</span><span class="sxs-lookup"><span data-stu-id="aab58-131">The table will also be compiled to a DLL.</span></span>  
  
 <span data-ttu-id="aab58-132">Considere o script de exemplo a seguir, que cria um banco de dados e uma tabela com otimização de memória:</span><span class="sxs-lookup"><span data-stu-id="aab58-132">Consider the following sample script, which creates a database and a memory-optimized table:</span></span>  
  
```sql  
use master  
go  
create database db1  
go  
alter database db1 add filegroup db1_mod contains memory_optimized_data  
go  
-- adapt filename as needed  
alter database db1 add file (name='db1_mod', filename='c:\data\db1_mod') to filegroup db1_mod  
go  
use db1  
go  
create table dbo.t1  
   (c1 int not null primary key nonclustered,  
    c2 INT)  
with (memory_optimized=on)  
go  
-- retrieve the path of the DLL for table t1  
select name, description FROM sys.dm_os_loaded_modules  
where name like '%xtp_t_' + cast(db_id() as varchar(10)) + '_' + cast(object_id('dbo.t1') as varchar(10)) + '.dll'  
go  
```  
  
 <span data-ttu-id="aab58-133">A criação da tabela também cria a DLL de tabela e a carrega na memória.</span><span class="sxs-lookup"><span data-stu-id="aab58-133">Creating the table also creates the table DLL and loads the DLL in memory.</span></span> <span data-ttu-id="aab58-134">A consulta DMV imediatamente após a instrução CREATE TABLE recupera o caminho da DLL de tabela.</span><span class="sxs-lookup"><span data-stu-id="aab58-134">The DMV query immediately after the CREATE TABLE statement retrieves the path of the table DLL.</span></span>  
  
 <span data-ttu-id="aab58-135">A DLL de tabela entende as estruturas de índice e o formato da linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="aab58-135">The table DLL understands the index structures and row format of the table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aab58-136">usa a DLL para percorrer índices, recuperar linhas e armazenar o conteúdo das linhas.</span><span class="sxs-lookup"><span data-stu-id="aab58-136">uses the DLL for traversing indexes, retrieving rows, as well as storing the contents of the rows.</span></span>  
  
## <a name="native-compilation-of-stored-procedures"></a><span data-ttu-id="aab58-137">Compilação nativa de procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="aab58-137">Native Compilation of Stored Procedures</span></span>  
 <span data-ttu-id="aab58-138">Os procedimentos armazenados que são marcados com NATIVE_COMPILATION são compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="aab58-138">Stored procedures that are marked with NATIVE_COMPILATION are natively compiled.</span></span> <span data-ttu-id="aab58-139">Isso significa que as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] no procedimento são todas compiladas em código nativo para execução eficiente da lógica de negócios crítica ao desempenho.</span><span class="sxs-lookup"><span data-stu-id="aab58-139">This means the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure are all compiled to native code for efficient execution of performance-critical business logic.</span></span>  
  
 <span data-ttu-id="aab58-140">Para obter mais informações sobre procedimentos armazenados nativamente compilados, consulte [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="aab58-140">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="aab58-141">Considere o procedimento armazenado do exemplo a seguir, que insere linhas na tabela t1 do exemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="aab58-141">Consider the following sample stored procedure, which inserts rows in the table t1 from the previous example:</span></span>  
  
```sql  
create procedure dbo.native_sp  
with native_compilation, schemabinding, execute as owner  
as  
begin atomic  
with (transaction isolation level=snapshot, language=N'us_english')  
  
  declare @i int = 1000000  
  while @i > 0  
  begin  
    insert dbo.t1 values (@i, @i+1)  
    set @i -= 1  
  end  
  
end  
go  
exec dbo.native_sp  
go  
-- reset  
delete from dbo.t1  
go  
```  
  
 <span data-ttu-id="aab58-142">A DLL para native_sp pode interagir diretamente com a DLL para t1, bem como com o mecanismo de armazenamento do OLTP na memória, para inserir as linhas o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="aab58-142">The DLL for native_sp can interact directly with the DLL for t1, as well as the In-Memory OLTP storage engine, to insert the rows as fast as possible.</span></span>  
  
 <span data-ttu-id="aab58-143">O compilador do OLTP na memória aproveita o otimizador de consulta para criar um plano de execução eficiente para cada uma das consultas no procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="aab58-143">The In-Memory OLTP compiler leverages the query optimizer to create an efficient execution plan for each of the queries in the stored procedure.</span></span> <span data-ttu-id="aab58-144">Observe que os procedimentos armazenados compilados nativamente serão recompilados automaticamente se os dados na tabela forem alterados.</span><span class="sxs-lookup"><span data-stu-id="aab58-144">Note that natively compiled stored procedures are not automatically recompiled if the data in the table changes.</span></span> <span data-ttu-id="aab58-145">Para obter mais informações sobre como manter estatísticas e procedimentos armazenados com OLTP in-memory, consulte [Estatísticas para tabelas com otimização de memória](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="aab58-145">For more information on maintaining statistics and stored procedures with In-Memory OLTP see [Statistics for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="security-considerations-for-native-compilation"></a><span data-ttu-id="aab58-146">Considerações de segurança para compilação nativa</span><span class="sxs-lookup"><span data-stu-id="aab58-146">Security Considerations for Native Compilation</span></span>  
 <span data-ttu-id="aab58-147">A compilação nativa de tabelas e procedimentos armazenados usa o compilador OLTP na memória.</span><span class="sxs-lookup"><span data-stu-id="aab58-147">Native compilation of tables and stored procedures uses the In-Memory OLTP compiler.</span></span> <span data-ttu-id="aab58-148">Esse compilador gera arquivos que são gravados no disco e carregados na memória.</span><span class="sxs-lookup"><span data-stu-id="aab58-148">This compiler produces files that are written to disk and loaded into memory.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aab58-149">usa os seguintes mecanismos para limitar o acesso a esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="aab58-149">uses the following mechanisms to limit access to these files.</span></span>  
  
### <a name="native-compiler"></a><span data-ttu-id="aab58-150">Compilador nativo</span><span class="sxs-lookup"><span data-stu-id="aab58-150">Native Compiler</span></span>  
 <span data-ttu-id="aab58-151">O executável do compilador, bem como os binários e os arquivos de cabeçalho necessários à compilação nativa são instalados como parte da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na pasta MSSQL\Binn\Xtp.</span><span class="sxs-lookup"><span data-stu-id="aab58-151">The compiler executable, as well as binaries and header files required for native compilation are installed as part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance under the folder MSSQL\Binn\Xtp.</span></span> <span data-ttu-id="aab58-152">Portanto, se a instância padrão for instalada em c:\Program Files, os arquivos do compilador serão instalados em c:\Arquivos de programas \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \MSSQL12. MSSQLSERVER\MSSQL\Binn\Xtp.</span><span class="sxs-lookup"><span data-stu-id="aab58-152">So, if the default instance is installed under C:\Program Files, the compiler files are installed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\Binn\Xtp.</span></span>  
  
 <span data-ttu-id="aab58-153">Para limitar o acesso ao compilador, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use listas de controle de acesso (ACLs) para restringir o acesso aos arquivos binários.</span><span class="sxs-lookup"><span data-stu-id="aab58-153">To limit access to the compiler, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses access control lists (ACLs) to restrict access to binary files.</span></span> <span data-ttu-id="aab58-154">Todos os binários do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são protegidos contra a modificação ou violação através de ACLs.</span><span class="sxs-lookup"><span data-stu-id="aab58-154">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries are protected against modification or tampering through ACLs.</span></span> <span data-ttu-id="aab58-155">As ACLs do compilador nativo também limitam o uso do compilador; somente os administradores de sistema e de conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] têm permissões de leitura e execução nos arquivos do compilador nativo.</span><span class="sxs-lookup"><span data-stu-id="aab58-155">The native compiler's ACLs also limit use of the compiler; only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators have read and execute permissions for native compiler files.</span></span>  
  
### <a name="files-generated-by-a-native-compilation"></a><span data-ttu-id="aab58-156">Arquivos gerados por uma compilação nativa</span><span class="sxs-lookup"><span data-stu-id="aab58-156">Files Generated by a Native Compilation</span></span>  
 <span data-ttu-id="aab58-157">Os arquivos gerados quando uma tabela ou um procedimento armazenado é compilado são arquivos DLL e intermediários que incluem arquivos com as seguintes extensões: .c, .obj, .xml, e .pdb.</span><span class="sxs-lookup"><span data-stu-id="aab58-157">The files produced when a table or stored procedure is compiled include the DLL and intermediate files including files with the following extensions: .c, .obj, .xml, and .pdb.</span></span> <span data-ttu-id="aab58-158">Os arquivos gerados são salvos em uma subpasta da pasta de dados padrão.</span><span class="sxs-lookup"><span data-stu-id="aab58-158">The generated files are saved in a subfolder of the default data folder.</span></span> <span data-ttu-id="aab58-159">A subpasta é chamada Xtp.</span><span class="sxs-lookup"><span data-stu-id="aab58-159">The subfolder is called Xtp.</span></span> <span data-ttu-id="aab58-160">Ao instalar a instância padrão com a pasta de dados padrão, os arquivos gerados são colocados em c:\Arquivos de programas \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \MSSQL12. MSSQLSERVER\MSSQL\DATA\Xtp.</span><span class="sxs-lookup"><span data-stu-id="aab58-160">When installing the default instance with the default data folder, the generated files are placed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\DATA\Xtp.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aab58-161">evita a violação das DLLs geradas de três maneiras:</span><span class="sxs-lookup"><span data-stu-id="aab58-161">prevents tampering with the generated DLLs in three ways:</span></span>  
  
-   <span data-ttu-id="aab58-162">Quando uma tabela ou um procedimento armazenado é compilado em uma DLL, esta é carregada imediatamente na memória e vinculada ao processo do sqlserver.exe.</span><span class="sxs-lookup"><span data-stu-id="aab58-162">When a table or stored procedure is compiled to a DLL, this DLL is immediately loaded into memory and linked to the sqlserver.exe process.</span></span> <span data-ttu-id="aab58-163">Uma DLL não pode ser modificada enquanto está vinculada a um processo.</span><span class="sxs-lookup"><span data-stu-id="aab58-163">A DLL cannot be modified while it is linked to a process.</span></span>  
  
-   <span data-ttu-id="aab58-164">Quando um banco de dados é reinicializado, todas as tabelas e procedimentos armazenados são recompilados (removidos e recriados) com base nos metadados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aab58-164">When a database is restarted, all tables and stored procedures are recompiled (removed and recreated) based on the database metadata.</span></span> <span data-ttu-id="aab58-165">Isso removerá todas as alterações feitas em um arquivo gerado por um agente mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="aab58-165">This will remove any changes made to a generated file by a malicious agent.</span></span>  
  
-   <span data-ttu-id="aab58-166">Os arquivos gerados são considerados parte dos dados do usuário e têm as mesmas restrições de segurança, via ACLs, que arquivos de banco de dados: somente os administradores de sistema e de conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem acessar esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="aab58-166">The generated files are considered part of user data, and have the same security restrictions, via ACLs, as database files: only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators can access these files.</span></span>  
  
 <span data-ttu-id="aab58-167">Nenhuma interação do usuário é necessária para gerenciar esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="aab58-167">No user interaction is needed to manage these files.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aab58-168">criará e removerá os arquivos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="aab58-168">will create and remove the files as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab58-169">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aab58-169">See Also</span></span>  
 <span data-ttu-id="aab58-170">[Tabelas com otimização de memória](memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="aab58-170">[Memory-Optimized Tables](memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="aab58-171">Procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="aab58-171">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
