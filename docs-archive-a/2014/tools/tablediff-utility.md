---
title: Utilitário tablediff | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- comparing data
- tablediff utility
- tables [SQL Server replication]
- table comparisons [SQL Server]
- command prompt utilities [SQL Server], tablediff
- troubleshooting [SQL Server replication], non-convergence
- non-convergence [SQL Server]
ms.assetid: 3c3cb865-7a4d-4d66-98f2-5935e28929fc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a23465a7d2c7db53475a6dca81a8471a3b78b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683236"
---
# <a name="tablediff-utility"></a><span data-ttu-id="c4cce-102">utilitário tablediff</span><span class="sxs-lookup"><span data-stu-id="c4cce-102">tablediff Utility</span></span>
  <span data-ttu-id="c4cce-103">O utilitário **tablediff** é usado para comparar dados em duas tabelas para não convergência e é particularmente útil para solução de problemas de não convergência em uma topologia de replicação.</span><span class="sxs-lookup"><span data-stu-id="c4cce-103">The **tablediff** utility is used to compare the data in two tables for non-convergence, and is particularly useful for troubleshooting non-convergence in a replication topology.</span></span> <span data-ttu-id="c4cce-104">Esse utilitário pode ser usado no prompt de comando ou em um arquivo em lotes para executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="c4cce-104">This utility can be used from the command prompt or in a batch file to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="c4cce-105">Uma comparação linha por linha entre uma tabela de origem em uma instância do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] agindo como um Publicador de replicação e a tabela de destino em uma ou mais instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] agindo como Assinantes de replicação.</span><span class="sxs-lookup"><span data-stu-id="c4cce-105">A row by row comparison between a source table in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as a replication Publisher and the destination table at one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as replication Subscribers.</span></span>  
  
-   <span data-ttu-id="c4cce-106">Executa uma comparação rápida comparando apenas contagens de linha e esquema.</span><span class="sxs-lookup"><span data-stu-id="c4cce-106">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
-   <span data-ttu-id="c4cce-107">Executar comparações em nível de coluna.</span><span class="sxs-lookup"><span data-stu-id="c4cce-107">Perform column-level comparisons.</span></span>  
  
-   <span data-ttu-id="c4cce-108">Gerar um script [!INCLUDE[tsql](../includes/tsql-md.md)] para corrigir discrepâncias no servidor de destino a fim de que haja convergência entre as tabelas de origem e de destino.</span><span class="sxs-lookup"><span data-stu-id="c4cce-108">Generate a [!INCLUDE[tsql](../includes/tsql-md.md)] script to fix discrepancies at the destination server to bring the source and destination tables into convergence.</span></span>  
  
-   <span data-ttu-id="c4cce-109">Registrar resultados em um arquivo de saída ou em uma tabela no banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="c4cce-109">Log results to an output file or into a table in the destination database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4cce-110">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c4cce-110">Syntax</span></span>  
  
```  
  
      tablediff   
[ -? ] |   
{  
        -sourceserversource_server_name[\instance_name]  
        -sourcedatabasesource_database-sourcetablesource_table_name   
    [ -sourceschemasource_schema_name ]  
    [ -sourcepasswordsource_password ]  
    [ -sourceusersource_login ]  
    [ -sourcelocked ]  
        -destinationserverdestination_server_name[\instance_name]  
        -destinationdatabasesubscription_database-destinationtabledestination_table   
    [ -destinationschemadestination_schema_name ]  
    [ -destinationpassworddestination_password ]  
    [ -destinationuserdestination_login ]  
    [ -destinationlocked ]  
    [ -blarge_object_bytes ]   
    [ -bfnumber_of_statements ]   
    [ -c ]   
    [ -dt ]   
    [ -ettable_name ]   
    [ -f [ file_name ] ]   
    [ -ooutput_file_name ]   
    [ -q ]   
    [ -rcnumber_of_retries ]   
    [ -riretry_interval ]   
    [ -strict ]  
    [ -tconnection_timeouts ]   
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4cce-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c4cce-111">Arguments</span></span>  
 <span data-ttu-id="c4cce-112">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="c4cce-112">[ **-?**</span></span> <span data-ttu-id="c4cce-113">]</span><span class="sxs-lookup"><span data-stu-id="c4cce-113">]</span></span>  
 <span data-ttu-id="c4cce-114">Retorna a lista de parâmetros com suporte.</span><span class="sxs-lookup"><span data-stu-id="c4cce-114">Returns the list of supported parameters.</span></span>  
  
 <span data-ttu-id="c4cce-115">**-SourceServer** *source_server_name*[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="c4cce-115">**-sourceserver** *source_server_name*[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="c4cce-116">É o nome do servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="c4cce-116">Is the name of the source server.</span></span> <span data-ttu-id="c4cce-117">Especifique _o \_ \_ nome do servidor de origem_ para a instância padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4cce-117">Specify _source\_server\_name_ for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c4cce-118">Especifique o nome da instância do _ \_ \_ nome do servidor de origem_ **\\** para uma instância nomeada do_ \_ _ [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4cce-118">Specify _source\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c4cce-119">**-sourcedatabase** *source_database*</span><span class="sxs-lookup"><span data-stu-id="c4cce-119">**-sourcedatabase** *source_database*</span></span>  
 <span data-ttu-id="c4cce-120">É o nome do banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="c4cce-120">Is the name of the source database.</span></span>  
  
 <span data-ttu-id="c4cce-121">**-sourcetable** *source_table_name*</span><span class="sxs-lookup"><span data-stu-id="c4cce-121">**-sourcetable** *source_table_name*</span></span>  
 <span data-ttu-id="c4cce-122">É o nome da tabela de origem que está sendo verificada.</span><span class="sxs-lookup"><span data-stu-id="c4cce-122">Is the name of the source table being checked.</span></span>  
  
 <span data-ttu-id="c4cce-123">**-sourceschema** *source_schema_name*</span><span class="sxs-lookup"><span data-stu-id="c4cce-123">**-sourceschema** *source_schema_name*</span></span>  
 <span data-ttu-id="c4cce-124">O proprietário de esquema da tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="c4cce-124">The schema owner of the source table.</span></span> <span data-ttu-id="c4cce-125">Por padrão, supõe-se que o proprietário de tabela seja dbo.</span><span class="sxs-lookup"><span data-stu-id="c4cce-125">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="c4cce-126">**-sourcepassword** *source_password*</span><span class="sxs-lookup"><span data-stu-id="c4cce-126">**-sourcepassword** *source_password*</span></span>  
 <span data-ttu-id="c4cce-127">É a senha para o logon usada para a conexão com o servidor de origem que usa Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4cce-127">Is the password for the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c4cce-128">Quando possível, forneça credenciais de segurança em runtime.</span><span class="sxs-lookup"><span data-stu-id="c4cce-128">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="c4cce-129">Se você precisar armazenar credenciais em um arquivo de script, deverá proteger o arquivo para evitar acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="c4cce-129">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="c4cce-130">**-sourceuser** *source_login*</span><span class="sxs-lookup"><span data-stu-id="c4cce-130">**-sourceuser** *source_login*</span></span>  
 <span data-ttu-id="c4cce-131">É o logon usado para a conexão com o servidor de origem que usa Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4cce-131">Is the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="c4cce-132">Se *source_login* não for fornecido, então a autenticação do Windows será usada no momento da conexão com o servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="c4cce-132">If *source_login* is not supplied, then Windows Authentication is used when connecting to the source server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="c4cce-133">**-sourcelocked**</span><span class="sxs-lookup"><span data-stu-id="c4cce-133">**-sourcelocked**</span></span>  
 <span data-ttu-id="c4cce-134">A tabela de origem é bloqueada durante a comparação que usa dicas de tabela TABLOCK e HOLDLOCK.</span><span class="sxs-lookup"><span data-stu-id="c4cce-134">The source table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="c4cce-135">**-DestinationServer** *destination_server_name*[ **\\** _ \_ nome da instância_]</span><span class="sxs-lookup"><span data-stu-id="c4cce-135">**-destinationserver** *destination_server_name*[**\\**_instance\_name_]</span></span>  
 <span data-ttu-id="c4cce-136">É o nome do servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="c4cce-136">Is the name of the destination server.</span></span> <span data-ttu-id="c4cce-137">Especifique *destination_server_name* para a instância padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4cce-137">Specify *destination_server_name* for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c4cce-138">Especifique o nome da instância do _ \_ \_ nome do servidor de destino_ **\\** para uma instância nomeada do_ \_ _ [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4cce-138">Specify _destination\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c4cce-139">**-destinationdatabase** *subscription_database*</span><span class="sxs-lookup"><span data-stu-id="c4cce-139">**-destinationdatabase** *subscription_database*</span></span>  
 <span data-ttu-id="c4cce-140">É o nome do banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="c4cce-140">Is the name of the destination database.</span></span>  
  
 <span data-ttu-id="c4cce-141">**-destinationtable** *destination_table*</span><span class="sxs-lookup"><span data-stu-id="c4cce-141">**-destinationtable** *destination_table*</span></span>  
 <span data-ttu-id="c4cce-142">É o nome da tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="c4cce-142">Is the name of the destination table.</span></span>  
  
 <span data-ttu-id="c4cce-143">**-destinationschema** *destination_schema_name*</span><span class="sxs-lookup"><span data-stu-id="c4cce-143">**-destinationschema** *destination_schema_name*</span></span>  
 <span data-ttu-id="c4cce-144">O proprietário de esquema da tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="c4cce-144">The schema owner of the destination table.</span></span> <span data-ttu-id="c4cce-145">Por padrão, supõe-se que o proprietário de tabela seja dbo.</span><span class="sxs-lookup"><span data-stu-id="c4cce-145">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="c4cce-146">**-destinationpassword** *destination_password*</span><span class="sxs-lookup"><span data-stu-id="c4cce-146">**-destinationpassword** *destination_password*</span></span>  
 <span data-ttu-id="c4cce-147">É a senha para o logon usada para a conexão com o servidor de destino que usa Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4cce-147">Is the password for the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c4cce-148">Quando possível, forneça credenciais de segurança em runtime.</span><span class="sxs-lookup"><span data-stu-id="c4cce-148">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="c4cce-149">Se você precisar armazenar credenciais em um arquivo de script, deverá proteger o arquivo para evitar acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="c4cce-149">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="c4cce-150">**-destinationuser** *destination_login*</span><span class="sxs-lookup"><span data-stu-id="c4cce-150">**-destinationuser** *destination_login*</span></span>  
 <span data-ttu-id="c4cce-151">É o logon usado para a conexão com o servidor de destino que usa Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4cce-151">Is the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="c4cce-152">Se *destination_login* não for fornecido, então a autenticação do Windows será usada no momento da conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="c4cce-152">If *destination_login* is not supplied, then Windows Authentication is used when connecting to the server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="c4cce-153">**-destinationlocked**</span><span class="sxs-lookup"><span data-stu-id="c4cce-153">**-destinationlocked**</span></span>  
 <span data-ttu-id="c4cce-154">A tabela de destino é bloqueada durante a comparação que usa dicas de tabela TABLOCK e HOLDLOCK.</span><span class="sxs-lookup"><span data-stu-id="c4cce-154">The destination table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="c4cce-155">**-b** *large_object_bytes*</span><span class="sxs-lookup"><span data-stu-id="c4cce-155">**-b** *large_object_bytes*</span></span>  
 <span data-ttu-id="c4cce-156">É o número de bytes a comparar para colunas de tipo de dados de objetos grandes, o que inclui padrões de: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` e `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="c4cce-156">Is the number of bytes to compare for large object data type columns, which includes: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` and `varbinary(max)`.</span></span> <span data-ttu-id="c4cce-157">*large_object_bytes* segue o padrão do tamanho da coluna.</span><span class="sxs-lookup"><span data-stu-id="c4cce-157">*large_object_bytes* defaults to the size of the column.</span></span> <span data-ttu-id="c4cce-158">Os dados acima de *large_object_bytes* não serão comparados.</span><span class="sxs-lookup"><span data-stu-id="c4cce-158">Any data above *large_object_bytes* will not be compared.</span></span>  
  
 <span data-ttu-id="c4cce-159">**-bf** *number_of_statements*</span><span class="sxs-lookup"><span data-stu-id="c4cce-159">**-bf**  *number_of_statements*</span></span>  
 <span data-ttu-id="c4cce-160">É o número de instruções [!INCLUDE[tsql](../includes/tsql-md.md)] a serem gravadas no arquivo de script [!INCLUDE[tsql](../includes/tsql-md.md)] atual quando a opção **-f** é usada.</span><span class="sxs-lookup"><span data-stu-id="c4cce-160">Is the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements to write to the current [!INCLUDE[tsql](../includes/tsql-md.md)] script file when the **-f** option is used.</span></span> <span data-ttu-id="c4cce-161">Quando o número de instruções [!INCLUDE[tsql](../includes/tsql-md.md)] exceder *number_of_statements*, um arquivo de script [!INCLUDE[tsql](../includes/tsql-md.md)] novo será criado.</span><span class="sxs-lookup"><span data-stu-id="c4cce-161">When the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements exceeds *number_of_statements*, a new [!INCLUDE[tsql](../includes/tsql-md.md)] script file is created.</span></span>  
  
 <span data-ttu-id="c4cce-162">**-c**</span><span class="sxs-lookup"><span data-stu-id="c4cce-162">**-c**</span></span>  
 <span data-ttu-id="c4cce-163">Compare diferenças em nível de coluna.</span><span class="sxs-lookup"><span data-stu-id="c4cce-163">Compare column-level differences.</span></span>  
  
 <span data-ttu-id="c4cce-164">**- dt**</span><span class="sxs-lookup"><span data-stu-id="c4cce-164">**-dt**</span></span>  
 <span data-ttu-id="c4cce-165">Descarte a tabela de resultado especificada por *table_name*, se a tabela já existir.</span><span class="sxs-lookup"><span data-stu-id="c4cce-165">Drop the result table specified by *table_name*, if the table already exists.</span></span>  
  
 <span data-ttu-id="c4cce-166">**-et** *table_name*</span><span class="sxs-lookup"><span data-stu-id="c4cce-166">**-et** *table_name*</span></span>  
 <span data-ttu-id="c4cce-167">Especifica o nome da tabela de resultado a ser criada.</span><span class="sxs-lookup"><span data-stu-id="c4cce-167">Specifies the name of the result table to create.</span></span> <span data-ttu-id="c4cce-168">Se essa tabela já existir, **-DT** deverá ser usado ou ocorrerá falha na operação.</span><span class="sxs-lookup"><span data-stu-id="c4cce-168">If this table already exists, **-DT** must be used or the operation will fail.</span></span>  
  
 <span data-ttu-id="c4cce-169">**-f** [ *file_name* ]</span><span class="sxs-lookup"><span data-stu-id="c4cce-169">**-f** [ *file_name* ]</span></span>  
 <span data-ttu-id="c4cce-170">Gera um script [!INCLUDE[tsql](../includes/tsql-md.md)] para trazer a tabela ao servidor de destino em convergência com a tabela no servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="c4cce-170">Generates a [!INCLUDE[tsql](../includes/tsql-md.md)] script to bring the table at the destination server into convergence with the table at the source server.</span></span> <span data-ttu-id="c4cce-171">Pode-se optar por especificar um nome e caminho para o arquivo de script [!INCLUDE[tsql](../includes/tsql-md.md)] gerado.</span><span class="sxs-lookup"><span data-stu-id="c4cce-171">You can optionally specify a name and path for the generated [!INCLUDE[tsql](../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="c4cce-172">Se *file_name* não for especificado, o arquivo de script [!INCLUDE[tsql](../includes/tsql-md.md)] será gerado no diretório no qual o utilitário é executado.</span><span class="sxs-lookup"><span data-stu-id="c4cce-172">If *file_name* is not specified, the [!INCLUDE[tsql](../includes/tsql-md.md)] script file is generated in the directory where the utility runs.</span></span>  
  
 <span data-ttu-id="c4cce-173">**-o** *output_file_name*</span><span class="sxs-lookup"><span data-stu-id="c4cce-173">**-o** *output_file_name*</span></span>  
 <span data-ttu-id="c4cce-174">É o nome e caminho completo do arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="c4cce-174">Is the full name and path of the output file.</span></span>  
  
 <span data-ttu-id="c4cce-175">**-q**</span><span class="sxs-lookup"><span data-stu-id="c4cce-175">**-q**</span></span>  
 <span data-ttu-id="c4cce-176">Executa uma comparação rápida comparando apenas contagens de linha e esquema.</span><span class="sxs-lookup"><span data-stu-id="c4cce-176">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
 <span data-ttu-id="c4cce-177">**-rc** *number_of_retries*</span><span class="sxs-lookup"><span data-stu-id="c4cce-177">**-rc** *number_of_retries*</span></span>  
 <span data-ttu-id="c4cce-178">Número de vezes que o utilitário repete uma operação com falha.</span><span class="sxs-lookup"><span data-stu-id="c4cce-178">Number of times that the utility retries a failed operation.</span></span>  
  
 <span data-ttu-id="c4cce-179">**-ri** *retry_interval*</span><span class="sxs-lookup"><span data-stu-id="c4cce-179">**-ri**  *retry_interval*</span></span>  
 <span data-ttu-id="c4cce-180">Intervalo, em segundos, a esperar entre repetições.</span><span class="sxs-lookup"><span data-stu-id="c4cce-180">Interval, in seconds, to wait between retries.</span></span>  
  
 <span data-ttu-id="c4cce-181">**-strict**</span><span class="sxs-lookup"><span data-stu-id="c4cce-181">**-strict**</span></span>  
 <span data-ttu-id="c4cce-182">Esquema de destino e origem são comparados de forma rigorosa.</span><span class="sxs-lookup"><span data-stu-id="c4cce-182">Source and destination schema are strictly compared.</span></span>  
  
 <span data-ttu-id="c4cce-183">**-t** *connection_timeouts*</span><span class="sxs-lookup"><span data-stu-id="c4cce-183">**-t** *connection_timeouts*</span></span>  
 <span data-ttu-id="c4cce-184">Define o período de tempo limite da conexão, em segundos, para conexões para o servidor de origem e servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="c4cce-184">Sets the connection timeout period, in seconds, for connections to the source server and destination server.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4cce-185">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="c4cce-185">Return Value</span></span>  
  
|<span data-ttu-id="c4cce-186">Valor</span><span class="sxs-lookup"><span data-stu-id="c4cce-186">Value</span></span>|<span data-ttu-id="c4cce-187">Descrição</span><span class="sxs-lookup"><span data-stu-id="c4cce-187">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c4cce-188">**0**</span><span class="sxs-lookup"><span data-stu-id="c4cce-188">**0**</span></span>|<span data-ttu-id="c4cce-189">Sucesso</span><span class="sxs-lookup"><span data-stu-id="c4cce-189">Success</span></span>|  
|<span data-ttu-id="c4cce-190">**1**</span><span class="sxs-lookup"><span data-stu-id="c4cce-190">**1**</span></span>|<span data-ttu-id="c4cce-191">Erro crítico</span><span class="sxs-lookup"><span data-stu-id="c4cce-191">Critical error</span></span>|  
|<span data-ttu-id="c4cce-192">**2**</span><span class="sxs-lookup"><span data-stu-id="c4cce-192">**2**</span></span>|<span data-ttu-id="c4cce-193">Diferenças de tabela</span><span class="sxs-lookup"><span data-stu-id="c4cce-193">Table differences</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4cce-194">Comentários</span><span class="sxs-lookup"><span data-stu-id="c4cce-194">Remarks</span></span>  
 <span data-ttu-id="c4cce-195">O utilitário **tablediff** não pode ser usado com [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] servidores não.</span><span class="sxs-lookup"><span data-stu-id="c4cce-195">The **tablediff** utility cannot be used with non-[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="c4cce-196">Não há suporte para tabelas com colunas de tipo de dados `sql_variant`.</span><span class="sxs-lookup"><span data-stu-id="c4cce-196">Tables with `sql_variant` data type columns are not supported.</span></span>  
  
 <span data-ttu-id="c4cce-197">Por padrão, o utilitário **tablediff** dá suporte aos mapeamentos de tipo de dados a seguir entre colunas de origem e de destino.</span><span class="sxs-lookup"><span data-stu-id="c4cce-197">By default, the **tablediff** utility supports the following data type mappings between source and destination columns.</span></span>  
  
|<span data-ttu-id="c4cce-198">Tipo de dados de origem</span><span class="sxs-lookup"><span data-stu-id="c4cce-198">Source data type</span></span>|<span data-ttu-id="c4cce-199">Tipo de dados de destino</span><span class="sxs-lookup"><span data-stu-id="c4cce-199">Destination data type</span></span>|  
|----------------------|---------------------------|  
|`tinyint`|<span data-ttu-id="c4cce-200">`smallint`, `int` ou `bigint`</span><span class="sxs-lookup"><span data-stu-id="c4cce-200">`smallint`, `int`, or `bigint`</span></span>|  
|`smallint`|<span data-ttu-id="c4cce-201">`int` ou `bigint`</span><span class="sxs-lookup"><span data-stu-id="c4cce-201">`int` or `bigint`</span></span>|  
|`int`|`bigint`|  
|`timestamp`|`varbinary`|  
|`varchar(max)`|`text`|  
|`nvarchar(max)`|`ntext`|  
|`varbinary(max)`|`image`|  
|`text`|`varchar(max)`|  
|`ntext`|`nvarchar(max)`|  
|`image`|`varbinary(max)`|  
  
 <span data-ttu-id="c4cce-202">Use a opção **-strict** para desabilitar esses mapeamentos e executar uma validação rigorosa.</span><span class="sxs-lookup"><span data-stu-id="c4cce-202">Use the **-strict** option to disallow these mappings and perform a strict validation.</span></span>  
  
 <span data-ttu-id="c4cce-203">A tabela de origem na comparação deve conter pelo menos uma chave primária, identidade ou coluna ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="c4cce-203">The source table in the comparison must contain at least one primary key, identity, or ROWGUID column.</span></span> <span data-ttu-id="c4cce-204">Quando você usa a opção **-strict** , a tabela de destino também deve ter uma chave primária, identidade ou coluna ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="c4cce-204">When you use the **-strict** option, the destination table must also have a primary key, identity, or ROWGUID column.</span></span>  
  
 <span data-ttu-id="c4cce-205">O script [!INCLUDE[tsql](../includes/tsql-md.md)] gerado para trazer a tabela de destino em convergência não inclui os seguintes tipos de dados:</span><span class="sxs-lookup"><span data-stu-id="c4cce-205">The [!INCLUDE[tsql](../includes/tsql-md.md)] script generated to bring the destination table into convergence does not include the following data types:</span></span>  
  
-   `varchar(max)`  
  
-   `nvarchar(max)`  
  
-   `varbinary(max)`  
  
-   `timestamp`  
  
-   <span data-ttu-id="c4cce-206">**xml**</span><span class="sxs-lookup"><span data-stu-id="c4cce-206">**xml**</span></span>  
  
-   `text`  
  
-   `ntext`  
  
-   `image`  
  
## <a name="permissions"></a><span data-ttu-id="c4cce-207">Permissões</span><span class="sxs-lookup"><span data-stu-id="c4cce-207">Permissions</span></span>  
 <span data-ttu-id="c4cce-208">Para comparar tabelas, é preciso ter permissões SELECT ALL nos objetos de tabela que são comparados.</span><span class="sxs-lookup"><span data-stu-id="c4cce-208">To compare tables, you need SELECT ALL permissions on the table objects being compared.</span></span>  
  
 <span data-ttu-id="c4cce-209">Para usar a opção **-et** é preciso ser membro da função de banco de dados fixo db_owner ou pelo menos ter permissão CREATE TABLE no banco de dados de assinatura e permissão ALTER no esquema de proprietário de destino no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="c4cce-209">To use the **-et** option, you must be a member of the db_owner fixed database role, or at least have CREATE TABLE permission in the subscription database and ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="c4cce-210">Para usar a opção **-dt** é preciso ser membro da função de banco de dados fixo db_owner ou pelo menos ter permissão ALTER no esquema de proprietário do destino no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="c4cce-210">To use the **-dt** option, you must be a member of the db_owner fixed database role, or at least have ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="c4cce-211">Para usar as opções **-o** ou **-f** , é preciso ter permissão de gravação para o local de diretório de arquivos especificado.</span><span class="sxs-lookup"><span data-stu-id="c4cce-211">To use the **-o** or **-f** options, you must have write permissions to the specified file directory location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4cce-212">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c4cce-212">See Also</span></span>  
 [<span data-ttu-id="c4cce-213">Comparar tabelas replicadas para descobrir diferenças &#40;Programação de replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="c4cce-213">Compare Replicated Tables for Differences &#40;Replication Programming&#41;</span></span>](../relational-databases/replication/administration/compare-replicated-tables-for-differences-replication-programming.md)  
  
  
