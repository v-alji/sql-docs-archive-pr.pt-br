---
title: Configuração de visibilidade de metadados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- subcomponents visibility [SQL Server]
- metadata [SQL Server], visibility
- permissions [SQL Server], metadata access
- viewing metadata
- objects [SQL Server], metadata
- displaying metadata
- database metadata [SQL Server]
- metadata [SQL Server], permissions
ms.assetid: 50d2e015-05ae-4014-a1cd-4de7866ad651
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5198dc4ba4e81bc1d7a8dd2411da59da81596102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574611"
---
# <a name="metadata-visibility-configuration"></a><span data-ttu-id="2ccf8-102">Configuração de visibilidade de metadados</span><span class="sxs-lookup"><span data-stu-id="2ccf8-102">Metadata Visibility Configuration</span></span>
  <span data-ttu-id="2ccf8-103">A visibilidade de metadados é limitada aos protegíveis que pertencem a um usuário ou sobre os quais recebeu alguma permissão.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-103">The visibility of metadata is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="2ccf8-104">Por exemplo, a consulta a seguir retornará uma linha se o usuário recebeu uma permissão SELECT ou INSERT na tabela `myTable`.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-104">For example, the following query returns a row if the user has been granted a permission such as SELECT or INSERT on the table `myTable`.</span></span>  
  
```  
SELECT name, object_id  
FROM sys.tables  
WHERE name = 'myTable';  
GO  
```  
  
 <span data-ttu-id="2ccf8-105">Entretanto, se o usuário não possuir nenhuma permissão em `myTable`, a consulta retornará um conjunto de resultados vazio.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-105">However, if the user does not have any permission on `myTable`, the query returns an empty result set.</span></span>  
  
## <a name="scope-and-impact-of-metadata-visibility-configuration"></a><span data-ttu-id="2ccf8-106">Escopo e impacto da configuração de visibilidade de metadados</span><span class="sxs-lookup"><span data-stu-id="2ccf8-106">Scope and Impact of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="2ccf8-107">A configuração de visibilidade de metadados apenas se aplica aos seguintes protegíveis.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-107">Metadata visibility configuration only applies to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ccf8-108">Exibições do catálogo</span><span class="sxs-lookup"><span data-stu-id="2ccf8-108">Catalog views</span></span>|<span data-ttu-id="2ccf8-109">Procedimentos armazenados do [!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-109">[!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures</span></span>|  
|<span data-ttu-id="2ccf8-110">Metadados com exposição de funções internas</span><span class="sxs-lookup"><span data-stu-id="2ccf8-110">Metadata exposing built-in functions</span></span>|<span data-ttu-id="2ccf8-111">Exibições do esquema de informações</span><span class="sxs-lookup"><span data-stu-id="2ccf8-111">Information schema views</span></span>|  
|<span data-ttu-id="2ccf8-112">Exibições de compatibilidade</span><span class="sxs-lookup"><span data-stu-id="2ccf8-112">Compatibility views</span></span>|<span data-ttu-id="2ccf8-113">Propriedades estendidas</span><span class="sxs-lookup"><span data-stu-id="2ccf8-113">Extended properties</span></span>|  
  
 <span data-ttu-id="2ccf8-114">A configuração de visibilidade de metadados não se aplica aos seguintes protegíveis.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-114">Metadata visibility configuration does not apply to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ccf8-115">Tabelas do sistema de envio de logs</span><span class="sxs-lookup"><span data-stu-id="2ccf8-115">Log shipping system tables</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2ccf8-116">Tabelas do sistema do Agent</span><span class="sxs-lookup"><span data-stu-id="2ccf8-116">Agent system tables</span></span>|  
|<span data-ttu-id="2ccf8-117">Tabelas do sistema de plano de manutenção do banco de dados</span><span class="sxs-lookup"><span data-stu-id="2ccf8-117">Database maintenance plan system tables</span></span>|<span data-ttu-id="2ccf8-118">Tabelas do sistema de backup</span><span class="sxs-lookup"><span data-stu-id="2ccf8-118">Backup system tables</span></span>|  
|<span data-ttu-id="2ccf8-119">Tabelas do sistema de replicação</span><span class="sxs-lookup"><span data-stu-id="2ccf8-119">Replication system tables</span></span>|<span data-ttu-id="2ccf8-120">Replicação e procedimento armazenados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **sp_help**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-120">Replication and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **sp_help** stored procedures</span></span>|  
  
 <span data-ttu-id="2ccf8-121">Acessibilidade de metadados limitada significa o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2ccf8-121">Limited metadata accessibility means the following:</span></span>  
  
-   <span data-ttu-id="2ccf8-122">Aplicativos que assumem que o acesso de metadados **público** será interrompido.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-122">Applications that assume **public** metadata access will break.</span></span>  
  
-   <span data-ttu-id="2ccf8-123">Consultas nas exibições de sistema podem retornar apenas um subconjunto de linhas, ou às vezes um conjunto de resultados vazio.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-123">Queries on system views might only return a subset of rows, or sometimes an empty result set.</span></span>  
  
-   <span data-ttu-id="2ccf8-124">Funções internas, que emitem metadados como em OBJECTPROPERTYEX podem retornar NULO.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-124">Metadata-emitting, built-in functions such as OBJECTPROPERTYEX may return NULL.</span></span>  
  
-   <span data-ttu-id="2ccf8-125">Os procedimentos armazenados do [!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** podem retornar apenas um subconjunto de linhas ou NULL.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures might return only a subset of rows, or NULL.</span></span>  
  
 <span data-ttu-id="2ccf8-126">Os módulos SQL, como os procedimentos armazenados e os gatilhos, são executados no contexto de segurança do chamador e, em consequência, têm acessibilidade limitada aos metadados.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-126">SQL modules, such as stored procedures and triggers, run under the security context of the caller and, therefore, have limited metadata accessibility.</span></span> <span data-ttu-id="2ccf8-127">Por exemplo, no código a seguir, quando o procedimento armazenado tentar acessar os metadados para a tabela `myTable` na qual o visitante não tem nenhum direito, há retorno de um conjunto de resultados vazio.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-127">For example, in the following code, when the stored procedure tries to access metadata for the table `myTable` on which the caller has no rights, an empty result set is returned.</span></span> <span data-ttu-id="2ccf8-128">Em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é retornada uma linha.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-128">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a row is returned.</span></span>  
  
```  
CREATE PROCEDURE assumes_caller_can_access_metadata  
BEGIN  
SELECT name, id   
FROM sysobjects   
WHERE name = 'myTable';  
END;  
GO  
```  
  
 <span data-ttu-id="2ccf8-129">Você pode conceder aos visitantes uma permissão VIEW DEFINITION, que permita aos visitantes exibir os metadados no escopo apropriado: nível de objeto, nível de banco de dados ou nível de servidor.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-129">To allow callers to view metadata, you can grant the callers VIEW DEFINITION permission at an appropriate scope: object level, database level or server level.</span></span> <span data-ttu-id="2ccf8-130">Assim, no exemplo prévio, se o visitante tiver uma permissão VIEW DEFINITION em `myTable`, o procedimento armazenado retornará uma linha.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-130">Therefore, in the previous example, if the caller has VIEW DEFINITION permission on `myTable`, the stored procedure returns a row.</span></span> <span data-ttu-id="2ccf8-131">Para obter mais informações, veja [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) e [Permissões de banco de dados GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ccf8-131">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="2ccf8-132">Você também pode modificar o procedimento armazenado de forma a executar com as credenciais do proprietário.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-132">You can also modify the stored procedure so that it executes under the credentials of the owner.</span></span> <span data-ttu-id="2ccf8-133">Quando o proprietário do procedimento e o da tabela forem o mesmo proprietário, o encadeamento de propriedade é aplicável e o contexto de segurança do proprietário do procedimento ativa o acesso aos metadados para `myTable`.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-133">When the procedure owner and the table owner are the same owner, ownership chaining applies, and the security context of the procedure owner enables access to the metadata for `myTable`.</span></span> <span data-ttu-id="2ccf8-134">Nesse cenário, o seguinte código retorna uma linha de metadados ao chamador.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-134">Under this scenario, the following code returns a row of metadata to the caller.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ccf8-135">O exemplo a seguir utiliza a exibição do catálogo [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) , em vez da exibição de compatibilidade [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2ccf8-135">The following example uses the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view instead of the [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) compatibility view.</span></span>  
  
```  
CREATE PROCEDURE does_not_assume_caller_can_access_metadata  
WITH EXECUTE AS OWNER  
AS  
BEGIN  
SELECT name, id  
FROM sys.objects   
WHERE name = 'myTable'   
END;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2ccf8-136">Você pode usar EXECUTE AS para alternar temporariamente para o contexto de segurança do chamador.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-136">You can use EXECUTE AS to temporarily switch to the security context of the caller.</span></span> <span data-ttu-id="2ccf8-137">Para obter mais informações, veja [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ccf8-137">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql).</span></span>  
  
## <a name="benefits-and-limits-of-metadata-visibility-configuration"></a><span data-ttu-id="2ccf8-138">Benefícios e limites da configuração de visibilidade de metadados</span><span class="sxs-lookup"><span data-stu-id="2ccf8-138">Benefits and Limits of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="2ccf8-139">A configuração de visibilidade de metadados pode ter uma função importante em seu plano de segurança global.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-139">Metadata visibility configuration can play an important role in your overall security plan.</span></span> <span data-ttu-id="2ccf8-140">Entretanto, há casos nos quais um usuário habilidoso e determinado pode forçar a divulgação de alguns metadados.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-140">However, there are cases in which a skilled and determined user can force the disclosure of some metadata.</span></span> <span data-ttu-id="2ccf8-141">Recomendamos que você implante permissões para metadados como um dos muitos detalhes de defesa.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-141">We recommend that you deploy metadata permissions as one of many defenses-in-depth.</span></span>  
  
 <span data-ttu-id="2ccf8-142">É teoricamente possível forçar a emissão de metadados em mensagens de erro manipulando a ordem de avaliação do predicado nas consultas.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-142">It is theoretically possible to force the emission of metadata in error messages by manipulating the order of predicate evaluation in queries.</span></span> <span data-ttu-id="2ccf8-143">A possibilidade de tais *ataques por tentativa e erro* não é específica do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ccf8-143">The possibility of such *trial-and-error attacks* is not specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2ccf8-144">Está implícita nas transformações associativas e comutativas permitidas pela álgebra relacional.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-144">It is implied by the associative and commutative transformations permitted in relational algebra.</span></span> <span data-ttu-id="2ccf8-145">Você pode reduzir esse risco limitando as informações retornadas nas mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-145">You can mitigate this risk by limiting the information returned in error messages.</span></span> <span data-ttu-id="2ccf8-146">Para restringir ainda mais a visibilidade de metadados desse modo, você pode iniciar o servidor com o sinalizador de rastreamento 3625.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-146">To further restrict the visibility of metadata in this way, you can start the server with trace flag 3625.</span></span> <span data-ttu-id="2ccf8-147">Este sinalizador de rastreamento limita a quantidade de informações mostradas nas mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-147">This trace flag limits the amount of information shown in error messages.</span></span> <span data-ttu-id="2ccf8-148">Por sua vez, isso ajuda a impedir divulgações forçadas.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-148">In turn, this helps to prevent forced disclosures.</span></span> <span data-ttu-id="2ccf8-149">Em compensação as mensagens de erro serão concisas e será difícil usar para propósitos de depuração.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-149">The tradeoff is that error messages will be terse and might be difficult to use for debugging purposes.</span></span> <span data-ttu-id="2ccf8-150">Para obter mais informações, consulte [Opções de inicialização do serviço Mecanismo de Banco de Dados](../../database-engine/configure-windows/database-engine-service-startup-options.md) e [Sinalizadores de rastreamento &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ccf8-150">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) and [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
 <span data-ttu-id="2ccf8-151">Os metadados a seguir não estão sujeitos a divulgação forçada:</span><span class="sxs-lookup"><span data-stu-id="2ccf8-151">The following metadata is not subject to forced disclosure:</span></span>  
  
-   <span data-ttu-id="2ccf8-152">O valor armazenado na coluna **provider_string** de **sys.servers**.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-152">The value stored in the **provider_string** column of **sys.servers**.</span></span> <span data-ttu-id="2ccf8-153">Um usuário que não tem permissão ALTER ANY LINKED SERVER verá um valor NULL nessa coluna.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-153">A user that does not have ALTER ANY LINKED SERVER permission will see a NULL value in this column.</span></span>  
  
-   <span data-ttu-id="2ccf8-154">Definição de fonte de um objeto definido pelo usuário como um procedimento armazenado ou gatilho.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-154">Source definition of a user-defined object such as a stored procedure or trigger.</span></span> <span data-ttu-id="2ccf8-155">O código de origem só é visível quando um destes for verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="2ccf8-155">The source code is visible only when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="2ccf8-156">O usuário tem permissão VIEW DEFINITION no objeto.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-156">The user has VIEW DEFINITION permission on the object.</span></span>  
  
    -   <span data-ttu-id="2ccf8-157">Não foi negada permissão ao usuário em VIEW DEFINITION no objeto e possui permissões em CONTROL, ALTER ou em TAKE OWNERSHIP no objeto.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-157">The user has not been denied VIEW DEFINITION permission on the object and has CONTROL, ALTER, or TAKE OWNERSHIP permission on the object.</span></span> <span data-ttu-id="2ccf8-158">Todos os outros usuários verão NULL.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-158">All other users will see NULL.</span></span>  
  
-   <span data-ttu-id="2ccf8-159">As colunas de definição encontradas nas exibições do catálogo a seguir:</span><span class="sxs-lookup"><span data-stu-id="2ccf8-159">The definition columns found in the following catalog views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="2ccf8-160">**sys.all_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-160">**sys.all_sql_modules**</span></span>|<span data-ttu-id="2ccf8-161">**sys.sql_modules**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-161">**sys.sql_modules**</span></span>|  
    |<span data-ttu-id="2ccf8-162">**sys.server_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-162">**sys.server_sql_modules**</span></span>|<span data-ttu-id="2ccf8-163">**sys.check_constraints**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-163">**sys.check_constraints**</span></span>|  
    |<span data-ttu-id="2ccf8-164">**sys.default_constraints**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-164">**sys.default_constraints**</span></span>|<span data-ttu-id="2ccf8-165">**sys.computed_columns**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-165">**sys.computed_columns**</span></span>|  
    |<span data-ttu-id="2ccf8-166">**sys.numbered_procedures**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-166">**sys.numbered_procedures**</span></span>||  
  
-   <span data-ttu-id="2ccf8-167">A coluna **ctext** na exibição de compatibilidade **syscomments** .</span><span class="sxs-lookup"><span data-stu-id="2ccf8-167">The **ctext** column in the **syscomments** compatibility view.</span></span>  
  
-   <span data-ttu-id="2ccf8-168">A saída do procedimento **sp_helptext** .</span><span class="sxs-lookup"><span data-stu-id="2ccf8-168">The output of the **sp_helptext** procedure.</span></span>  
  
-   <span data-ttu-id="2ccf8-169">As seguintes colunas nas exibições do esquema de informações:</span><span class="sxs-lookup"><span data-stu-id="2ccf8-169">The following columns in the information schema views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="2ccf8-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span><span class="sxs-lookup"><span data-stu-id="2ccf8-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span></span>|<span data-ttu-id="2ccf8-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2ccf8-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="2ccf8-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2ccf8-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span></span>|<span data-ttu-id="2ccf8-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2ccf8-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="2ccf8-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2ccf8-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span></span>|<span data-ttu-id="2ccf8-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="2ccf8-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span></span>|  
  
-   <span data-ttu-id="2ccf8-176">Função OBJECT_DEFINITION()</span><span class="sxs-lookup"><span data-stu-id="2ccf8-176">OBJECT_DEFINITION() function</span></span>  
  
-   <span data-ttu-id="2ccf8-177">O valor armazenado na coluna password_hash em **sys.sql_logins**.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-177">The value stored in the password_hash column of **sys.sql_logins**.</span></span>  <span data-ttu-id="2ccf8-178">Um usuário que não tenha a permissão CONTROL SERVER verá um valor NULL nessa coluna.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-178">A user that does not have CONTROL SERVER permission will see a NULL value in this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ccf8-179">As definições de SQL de procedimentos e funções de sistema internos são publicamente visíveis na exibição do catálogo **sys.system_sql_modules** , no procedimento armazenado **sp_helptext** e na função OBJECT_DEFINITION().</span><span class="sxs-lookup"><span data-stu-id="2ccf8-179">The SQL definitions of built-in system procedures and functions are publicly visible through the **sys.system_sql_modules** catalog view, the **sp_helptext** stored procedure, and the OBJECT_DEFINITION() function.</span></span>  
  
## <a name="general-principles-of-metadata-visibility"></a><span data-ttu-id="2ccf8-180">Princípios gerais de visibilidade de metadados</span><span class="sxs-lookup"><span data-stu-id="2ccf8-180">General Principles of Metadata Visibility</span></span>  
 <span data-ttu-id="2ccf8-181">A seguir, alguns princípios gerais para serem considerados relativos à visibilidade de metadados:</span><span class="sxs-lookup"><span data-stu-id="2ccf8-181">The following are some general principles to consider regarding metadata visibility:</span></span>  
  
-   <span data-ttu-id="2ccf8-182">Permissões implícitas de funções fixas</span><span class="sxs-lookup"><span data-stu-id="2ccf8-182">Fixed roles implicit permissions</span></span>  
  
-   <span data-ttu-id="2ccf8-183">Escopo das permissões</span><span class="sxs-lookup"><span data-stu-id="2ccf8-183">Scope of permissions</span></span>  
  
-   <span data-ttu-id="2ccf8-184">Precedência em DENY</span><span class="sxs-lookup"><span data-stu-id="2ccf8-184">Precedence of DENY</span></span>  
  
-   <span data-ttu-id="2ccf8-185">Visibilidade de metadados de subcomponente</span><span class="sxs-lookup"><span data-stu-id="2ccf8-185">Visibility of subcomponent metadata</span></span>  
  
### <a name="fixed-roles-and-implicit-permissions"></a><span data-ttu-id="2ccf8-186">Funções fixas e permissões implícitas</span><span class="sxs-lookup"><span data-stu-id="2ccf8-186">Fixed Roles and Implicit Permissions</span></span>  
 <span data-ttu-id="2ccf8-187">Os metadados que podem ser acessados através de funções fixas dependem de suas permissões implícitas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-187">Metadata that can be accessed by fixed roles depends upon their corresponding implicit permissions.</span></span>  
  
### <a name="scope-of-permissions"></a><span data-ttu-id="2ccf8-188">Escopo das permissões</span><span class="sxs-lookup"><span data-stu-id="2ccf8-188">Scope of Permissions</span></span>  
 <span data-ttu-id="2ccf8-189">Permissões em um escopo implicam na capacidade de ver os metadados nesse escopo e em todos os escopos inclusos.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-189">Permissions at one scope imply the ability to see metadata at that scope and at all enclosed scopes.</span></span> <span data-ttu-id="2ccf8-190">Por exemplo, a permissão SELECT dentro de um esquema implica que o beneficiado tem permissão SELECT em todos os protegíveis contidos nesse esquema.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-190">For example, SELECT permission on a schema implies that the grantee has SELECT permission on all securables that are contained by that schema.</span></span> <span data-ttu-id="2ccf8-191">A concessão de permissão SELECT em um esquema permite que usuário veja então os metadados do esquema e também todas as tabelas, exibições, funções, procedimentos, filas, sinônimos, tipos e coleções de esquema XML inclusos.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-191">The granting of SELECT permission on a schema therefore enables a user to see the metadata of the schema and also all tables, views, functions, procedures, queues, synonyms, types, and XML schema collections within it.</span></span> <span data-ttu-id="2ccf8-192">Para obter mais informações sobre escopos, veja [Hierarquia de permissões &#40;Mecanismo de Banco de Dados&#41;](permissions-hierarchy-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="2ccf8-192">For more information about scopes, see [Permissions Hierarchy &#40;Database Engine&#41;](permissions-hierarchy-database-engine.md).</span></span>  
  
### <a name="precedence-of-deny"></a><span data-ttu-id="2ccf8-193">Precedência em DENY</span><span class="sxs-lookup"><span data-stu-id="2ccf8-193">Precedence of DENY</span></span>  
 <span data-ttu-id="2ccf8-194">DENY normalmente tem precedência sobre outras permissões.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-194">DENY typically takes precedence over other permissions.</span></span> <span data-ttu-id="2ccf8-195">Por exemplo, se um usuário de banco de dados recebeu permissão EXECUTE em um esquema, mas teve a permissão EXECUTE negada em um procedimento armazenado nesse esquema, o usuário não pode exibir os metadados para esse procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-195">For example, if a database user is granted EXECUTE permission on a schema but has been denied EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="2ccf8-196">Além disso, se um usuário teve a permissão EXECUTE negada em um esquema, mas recebeu a permissão EXECUTE em um procedimento armazenado nesse esquema, o usuário não pode exibir os metadados para esse procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-196">Additionally, if a user is denied EXECUTE permission on a schema but has been granted EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="2ccf8-197">Outro exemplo, se um usuário teve permissão EXECUTE concedida e negada em um procedimento armazenado, o que é possível através de suas diversas associações à funções, DENY terá precedência e o usuário não poderá exibir os metadados do procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-197">For another example, if a user has been granted and denied EXECUTE permission on a stored procedure, which is possible through your various role memberships, DENY takes precedence and the user cannot view the metadata of the stored procedure.</span></span>  
  
### <a name="visibility-of-subcomponent-metadata"></a><span data-ttu-id="2ccf8-198">Visibilidade de metadados de subcomponente</span><span class="sxs-lookup"><span data-stu-id="2ccf8-198">Visibility of Subcomponent Metadata</span></span>  
 <span data-ttu-id="2ccf8-199">A visibilidade de subcomponentes, como índices, restrições de verificação e gatilhos são determinados através de permissões no pai.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-199">The visibility of subcomponents, such as indexes, check constraints, and triggers is determined by permissions on the parent.</span></span> <span data-ttu-id="2ccf8-200">Esses subcomponentes não têm permissões que possam ser concedidas.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-200">These subcomponents do not have grantable permissions.</span></span> <span data-ttu-id="2ccf8-201">Por exemplo, se um usuário recebeu alguma permissão em uma tabela, o usuário poderá exibir os metadados para as tabelas, colunas, índices, restrições de verificações, gatilhos e outros subcomponentes similares.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-201">For example, if a user has been granted some permission on a table, the user can view the metadata for the tables, columns, indexes, check constraints, triggers, and other such subcomponents.</span></span>  
  
#### <a name="metadata-that-is-accessible-to-all-database-users"></a><span data-ttu-id="2ccf8-202">Metadados acessíveis a todos os usuários do banco de dados</span><span class="sxs-lookup"><span data-stu-id="2ccf8-202">Metadata That Is Accessible to All Database Users</span></span>  
 <span data-ttu-id="2ccf8-203">Algum metadados devem ser acessíveis a todos os usuários em um banco de dados específico.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-203">Some metadata must be accessible to all users in a specific database.</span></span> <span data-ttu-id="2ccf8-204">Por exemplo, grupos de arquivos não têm permissões que possam ser conferidas; consequentemente, um usuário não pode receber permissão para exibir os metadados de um grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-204">For example, filegroups do not have conferrable permissions; therefore, a user cannot be granted permission to view the metadata of a filegroup.</span></span> <span data-ttu-id="2ccf8-205">Entretanto, qualquer usuário que possa criar uma tabela deve poder acessar os metadados de grupo de arquivos para usar *filegroup* ON ou as cláusulas TEXTIMAGE_ON *filegroup* da instrução CREATE TABLE.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-205">However, any user that can create a table must be able to access filegroup metadata to use the ON *filegroup* or TEXTIMAGE_ON *filegroup* clauses of the CREATE TABLE statement.</span></span>  
  
 <span data-ttu-id="2ccf8-206">Os metadados retornados pelas funções DB_ID() e DB_NAME() são visíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="2ccf8-206">The metadata that is returned by the DB_ID() and DB_NAME() functions is visible to all users.</span></span>  
  
 <span data-ttu-id="2ccf8-207">A tabela a seguir lista aos exibições do catálogo que são visíveis na função **pública** .</span><span class="sxs-lookup"><span data-stu-id="2ccf8-207">The following table lists the catalog views that are visible to the **public** role.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ccf8-208">**sys.partition_functions**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-208">**sys.partition_functions**</span></span>|<span data-ttu-id="2ccf8-209">**sys.partition_range_values**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-209">**sys.partition_range_values**</span></span>|  
|<span data-ttu-id="2ccf8-210">**sys.partition_schemes**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-210">**sys.partition_schemes**</span></span>|<span data-ttu-id="2ccf8-211">**sys.data_spaces**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-211">**sys.data_spaces**</span></span>|  
|<span data-ttu-id="2ccf8-212">**sys.filegroups**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-212">**sys.filegroups**</span></span>|<span data-ttu-id="2ccf8-213">**sys.destination_data_spaces**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-213">**sys.destination_data_spaces**</span></span>|  
|<span data-ttu-id="2ccf8-214">**sys.database_files**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-214">**sys.database_files**</span></span>|<span data-ttu-id="2ccf8-215">**sys.allocation_units**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-215">**sys.allocation_units**</span></span>|  
|<span data-ttu-id="2ccf8-216">**sys.partitions**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-216">**sys.partitions**</span></span>|<span data-ttu-id="2ccf8-217">**sys.messages**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-217">**sys.messages**</span></span>|  
|<span data-ttu-id="2ccf8-218">**sys.schemas**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-218">**sys.schemas**</span></span>|<span data-ttu-id="2ccf8-219">**sys.configurations**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-219">**sys.configurations**</span></span>|  
|<span data-ttu-id="2ccf8-220">**sys.sql_dependencies**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-220">**sys.sql_dependencies**</span></span>|<span data-ttu-id="2ccf8-221">**sys.type_assembly_usages**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-221">**sys.type_assembly_usages**</span></span>|  
|<span data-ttu-id="2ccf8-222">**sys.parameter_type_usages**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-222">**sys.parameter_type_usages**</span></span>|<span data-ttu-id="2ccf8-223">**sys.column_type_usages**</span><span class="sxs-lookup"><span data-stu-id="2ccf8-223">**sys.column_type_usages**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ccf8-224">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2ccf8-224">See Also</span></span>  
 <span data-ttu-id="2ccf8-225">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2ccf8-225">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 <span data-ttu-id="2ccf8-226">[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2ccf8-226">[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) </span></span>  
 <span data-ttu-id="2ccf8-227">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2ccf8-227">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="2ccf8-228">[Cláusula EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2ccf8-228">[EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql) </span></span>  
 <span data-ttu-id="2ccf8-229">[Exibições de catálogo &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2ccf8-229">[Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="2ccf8-230">Exibições de compatibilidade &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2ccf8-230">Compatibility Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql)  
  
  
