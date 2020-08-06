---
title: Instalar e configurar a pesquisa semântica | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], installing
- semantic search [SQL Server], configuring
ms.assetid: 2cdd0568-7799-474b-82fb-65d79df3057c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8d95e0bb2adf3bacf7057b881ab2e85afd50feef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681512"
---
# <a name="install-and-configure-semantic-search"></a><span data-ttu-id="e603c-102">Instalar e configurar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="e603c-102">Install and Configure Semantic Search</span></span>
  <span data-ttu-id="e603c-103">Descreve os pré-requisitos para a pesquisa semântica estatística e como instalá-los ou verificá-los.</span><span class="sxs-lookup"><span data-stu-id="e603c-103">Describes the prerequisites for statistical semantic search and how to install or check them.</span></span>  
  
## <a name="installing-semantic-search"></a><span data-ttu-id="e603c-104">Instalando a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="e603c-104">Installing Semantic Search</span></span>  
  
###  <a name="how-to-check-whether-semantic-search-is-installed"></a><a name="HowToCheckInstalled"></a><span data-ttu-id="e603c-105">Como verificar se a pesquisa semântica está instalada</span><span class="sxs-lookup"><span data-stu-id="e603c-105">How To: Check Whether Semantic Search Is Installed</span></span>  
 <span data-ttu-id="e603c-106">Consulte a propriedade **IsFullTextInstalled** da função de metadados [SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e603c-106">Query the **IsFullTextInstalled** property of the [SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="e603c-107">Um valor de retorno 1 indica que a pesquisa de texto completo e a pesquisa semântica estão instaladas; um valor de retorno 0 indica que não estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="e603c-107">A return value of 1 indicates that Full-Text Search and Semantic Search are installed; a return value of 0 indicates that they are not installed.</span></span>  
  
```sql  
SELECT SERVERPROPERTY('IsFullTextInstalled');  
GO  
```  
  
###  <a name="how-to-install-semantic-search"></a><a name="BasicsSemanticSearch"></a><span data-ttu-id="e603c-108">Como instalar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="e603c-108">How To: Install Semantic Search</span></span>  
 <span data-ttu-id="e603c-109">Para instalar a Pesquisa Semântica, selecione **Extrações Semânticas e de Texto Completo para Pesquisa** na página **Recursos para Instalar** durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="e603c-109">To install Semantic Search, select **Full-Text and Semantic Extractions for Search** on the **Features to Install** page during setup.</span></span>  
  
 <span data-ttu-id="e603c-110">A pesquisa semântica estatística depende da pesquisa de texto completo.</span><span class="sxs-lookup"><span data-stu-id="e603c-110">Statistical Semantic Search depends on Full-Text Search.</span></span> <span data-ttu-id="e603c-111">Esses dois recursos opcionais do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] são instalados juntos.</span><span class="sxs-lookup"><span data-stu-id="e603c-111">These two optional features of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are installed together.</span></span>  
  
## <a name="installing-or-removing-the-semantic-language-statistics-database"></a><span data-ttu-id="e603c-112">Instalando ou removendo o banco de dados de estatísticas semânticas de idioma</span><span class="sxs-lookup"><span data-stu-id="e603c-112">Installing or Removing the Semantic Language Statistics Database</span></span>  
 <span data-ttu-id="e603c-113">A Pesquisa Semântica tem uma dependência externa adicional denominada banco de dados de estatísticas semânticas de idioma.</span><span class="sxs-lookup"><span data-stu-id="e603c-113">Semantic Search has an additional external dependency that is called the semantic language statistics database.</span></span> <span data-ttu-id="e603c-114">Esse banco de dados contém os modelos de idioma estatísticos requeridos pela pesquisa semântica.</span><span class="sxs-lookup"><span data-stu-id="e603c-114">This database contains the statistical language models required by semantic search.</span></span> <span data-ttu-id="e603c-115">Um único banco de dados de estatísticas semânticas de idioma contém os modelos para todos os idiomas com suporte na indexação semântica.</span><span class="sxs-lookup"><span data-stu-id="e603c-115">A single semantic language statistics database contains the language models for all the languages that are supported for semantic indexing.</span></span>  
  
###  <a name="how-to-check-whether-the-semantic-language-statistics-database-is-installed"></a><a name="HowToCheckDatabase"></a><span data-ttu-id="e603c-116">Como verificar se o banco de dados do Estatísticas Semânticas de Idioma está instalado</span><span class="sxs-lookup"><span data-stu-id="e603c-116">How To: Check Whether the Semantic Language Statistics Database Is Installed</span></span>  
 <span data-ttu-id="e603c-117">Consulte a exibição de catálogo [sys.fulltext_semantic_language_statistics_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-language-statistics-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e603c-117">Query the catalog view [sys.fulltext_semantic_language_statistics_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-language-statistics-database-transact-sql).</span></span>  
  
 <span data-ttu-id="e603c-118">Se o banco de dados de estatísticas semânticas de idioma for instalado e registrado para a instância, os resultados da consulta conterão uma única linha de informações sobre o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e603c-118">If the semantic language statistics database is installed and registered for the instance, then the query results contain a single row of information about the database.</span></span>  
  
```vb  
SELECT * FROM sys.fulltext_semantic_language_statistics_database;  
GO  
```  
  
###  <a name="how-to-install-attach-and-register-the-semantic-language-statistics-database"></a><a name="HowToInstallModel"></a><span data-ttu-id="e603c-119">Como instalar, anexar e registrar o banco de dados Estatísticas Semânticas de Idioma</span><span class="sxs-lookup"><span data-stu-id="e603c-119">How To: Install, Attach, and Register the Semantic Language Statistics Database</span></span>  
 <span data-ttu-id="e603c-120">O banco de dados de estatísticas semânticas de idioma não é instalado pelo programa de instalação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e603c-120">The semantic language statistics database is not installed by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] setup program.</span></span> <span data-ttu-id="e603c-121">Para configurar o banco de dados de estatísticas semânticas de idioma como um pré-requisito para a indexação semântica, execute estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="e603c-121">To set up the Semantic Language Statistics database as a prerequisite for semantic indexing, do the following tasks:</span></span>  
  
 <span data-ttu-id="e603c-122">**1. Instale o banco de dados de estatísticas semânticas de idioma.**</span><span class="sxs-lookup"><span data-stu-id="e603c-122">**1. Install the semantic language statistics database.**</span></span>  
 1.  <span data-ttu-id="e603c-123">Localize o banco de dados de estatísticas semânticas de idioma nas mídias de instalação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou baixe-o da Web.</span><span class="sxs-lookup"><span data-stu-id="e603c-123">Locate the semantic language statistics database on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation media or download it from the Web.</span></span>  
  
    -   <span data-ttu-id="e603c-124">Localize o pacote do Windows Installer nomeado **SemanticLanguageDatabase.msi** na mídia de instalação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e603c-124">Locate the Windows installer package named **SemanticLanguageDatabase.msi** on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation media.</span></span> <span data-ttu-id="e603c-125">Localize a versão de 32 ou 64 bits do pacote de instalador, dependendo do sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="e603c-125">Locate the 32-bit or 64-bit version of the installer package depending on the target system.</span></span> <span data-ttu-id="e603c-126">O nome da pasta contêiner identifica a versão de 32 ou 64 bits do arquivo; o nome do arquivo é o mesmo para ambas as versões.</span><span class="sxs-lookup"><span data-stu-id="e603c-126">The name of the containing folder identifies the 32-bit or 64-bit version of the file; the file name itself is the same for both versions.</span></span>  
  
    -   <span data-ttu-id="e603c-127">Baixar o pacote do instalador da [Microsoft? SQL Server?? 2014 Estatísticas Semânticas de Idioma](https://go.microsoft.com/fwlink/?LinkID=296743) página no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] centro de download.</span><span class="sxs-lookup"><span data-stu-id="e603c-127">Download the installer package from the [Microsoft?? SQL Server?? 2014 Semantic Language Statistics](https://go.microsoft.com/fwlink/?LinkID=296743) page on the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Download Center.</span></span>  
  
2.  <span data-ttu-id="e603c-128">Execute o **SemanticLanguageDatabase.msi** pacote do Windows Installer para extrair o banco de dados e o arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="e603c-128">Run the **SemanticLanguageDatabase.msi** Windows installer package to extract the database and log file.</span></span>  
  
     <span data-ttu-id="e603c-129">Se desejar, você pode alterar o diretório de destino.</span><span class="sxs-lookup"><span data-stu-id="e603c-129">You can optionally change the destination directory.</span></span> <span data-ttu-id="e603c-130">Por padrão, o instalador extrai os arquivos para uma pasta chamada **banco de dados de idioma semântico da Microsoft** na pasta arquivos de programas de 32 bits ou 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e603c-130">By default, the installer extracts the files to a folder named **Microsoft Semantic Language Database** in the 32-bit or 64-bit Program Files folder.</span></span> <span data-ttu-id="e603c-131">O arquivo MSI contém um arquivo de banco de dados compactado e um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="e603c-131">The MSI file contains a compressed database file and log file.</span></span>  
  
3.  <span data-ttu-id="e603c-132">Mova o arquivo de banco de dados extraído e o arquivo de log para um local adequado no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e603c-132">Move the extracted database file and log file to a suitable location in the file system.</span></span>  
  
     <span data-ttu-id="e603c-133">Se você deixar os arquivos no local padrão, não será possível extrair outra cópia do banco de dados para outra instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e603c-133">If you leave the files in their default location, it will not be possible to extract another copy of the database for another instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e603c-134">Quando o banco de dados de estatísticas semânticas de idioma é extraído, permissões restritas são atribuídas ao arquivo de banco de dados e arquivo de log no local padrão no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e603c-134">When the semantic language statistics database is extracted, restricted permissions are assigned to the database file and log file in the default location in the file system.</span></span> <span data-ttu-id="e603c-135">Como resultado, você possivelmente não terá permissão para anexar o banco de dados se deixá-lo no local padrão.</span><span class="sxs-lookup"><span data-stu-id="e603c-135">As a result, you may not have permission to attach the database if you leave it in the default location.</span></span> <span data-ttu-id="e603c-136">Se um erro ocorrer quando você tenta anexar o banco de dados, mova os arquivos ou verifique e corrija as permissões do sistema de arquivos conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="e603c-136">If an error is raised when you try to attach the database, move the files, or check and fix file system permissions as appropriate.</span></span>  
  
 <span data-ttu-id="e603c-137">**2. Anexe o banco de dados de estatísticas semânticas de idioma.**</span><span class="sxs-lookup"><span data-stu-id="e603c-137">**2. Attach the semantic language statistics database.**</span></span>  
 <span data-ttu-id="e603c-138">Anexe o banco de dados à instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ou chamando [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) com a sintaxe **FOR ATTACH**.</span><span class="sxs-lookup"><span data-stu-id="e603c-138">Attach the database to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] or by calling [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) with the **FOR ATTACH** syntax.</span></span> <span data-ttu-id="e603c-139">Para obter mais informações, consulte [Anexar e desanexar bancos de dados &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e603c-139">For more information, see [Database Detach and Attach &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md).</span></span>  
  
 <span data-ttu-id="e603c-140">Por padrão, o nome do banco de dados é **semanticsdb**.</span><span class="sxs-lookup"><span data-stu-id="e603c-140">By default, the name of the database is **semanticsdb**.</span></span> <span data-ttu-id="e603c-141">Se desejar, você poderá atribuir ao banco de dados um nome diferente quando anexá-lo.</span><span class="sxs-lookup"><span data-stu-id="e603c-141">You can optionally give the database a different name when you attach it.</span></span> <span data-ttu-id="e603c-142">Você tem que fornecer esse nome ao registrar o banco de dados na etapa subsequente.</span><span class="sxs-lookup"><span data-stu-id="e603c-142">You have to provide this name when you register the database in the subsequent step.</span></span>  
  
```sql  
CREATE DATABASE semanticsdb  
            ON ( FILENAME = 'C:\Microsoft Semantic Language Database\semanticsdb.mdf' )  
            LOG ON ( FILENAME = 'C:\Microsoft Semantic Language Database\semanticsdb_log.ldf' )  
            FOR ATTACH;  
GO  
```  
  
 <span data-ttu-id="e603c-143">Esse exemplo de código pressupõe que você moveu o banco de dados de seu local padrão para um novo local.</span><span class="sxs-lookup"><span data-stu-id="e603c-143">This code sample assumes that you have moved the database from its default location to a new location.</span></span>  
  
 <span data-ttu-id="e603c-144">**3. Registre o banco de dados de estatísticas semânticas de idioma.**</span><span class="sxs-lookup"><span data-stu-id="e603c-144">**3. Register the semantic language statistics database.**</span></span>  
 <span data-ttu-id="e603c-145">Chame o procedimento armazenado [sp_fulltext_semantic_register_language_statistics_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-register-language-statistics-db-transact-sql) e forneça o nome que você atribuiu ao banco de dados quando o anexou.</span><span class="sxs-lookup"><span data-stu-id="e603c-145">Call the stored procedure [sp_fulltext_semantic_register_language_statistics_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-register-language-statistics-db-transact-sql) and provide the name that you gave to the database when you attached it.</span></span>  
  
```sql  
EXEC sp_fulltext_semantic_register_language_statistics_db @dbname = N'semanticsdb';  
GO  
```  
  
###  <a name="how-to-unregister-detach-and-remove-the-semantic-language-statistics-database"></a><a name="HowToUnregister"></a><span data-ttu-id="e603c-146">Como: cancelar o registro, desanexar e remover o banco de dados Estatísticas Semânticas de Idioma</span><span class="sxs-lookup"><span data-stu-id="e603c-146">How To: Unregister, Detach, and Remove the Semantic Language Statistics Database</span></span>  
 <span data-ttu-id="e603c-147">**Cancelar o registro do banco de dados de estatísticas semânticas de idioma.**</span><span class="sxs-lookup"><span data-stu-id="e603c-147">**Unregister the semantic language statistics database.**</span></span>  
 <span data-ttu-id="e603c-148">Chame o procedimento armazenado [sp_fulltext_semantic_unregister_language_statistics_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-unregister-language-statistics-db-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e603c-148">Call the stored procedure [sp_fulltext_semantic_unregister_language_statistics_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-unregister-language-statistics-db-transact-sql).</span></span> <span data-ttu-id="e603c-149">Você não precisa fornecer o nome do banco de dados, já que uma instância pode ter somente um banco de dados de estatísticas semânticas de idioma.</span><span class="sxs-lookup"><span data-stu-id="e603c-149">You do not have to provide the name of the database since an instance can have only one semantic language statistics database.</span></span>  
  
```sql  
EXEC sp_fulltext_semantic_unregister_language_statistics_db;  
GO  
```  
  
 <span data-ttu-id="e603c-150">**Desanexe o banco de dados de estatísticas semânticas de idioma.**</span><span class="sxs-lookup"><span data-stu-id="e603c-150">**Detach the semantic language statistics database.**</span></span>  
 <span data-ttu-id="e603c-151">Chame o procedimento armazenado [sp_detach_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql) e forneça o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e603c-151">Call the stored procedure [sp_detach_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql) and provide the name of the database.</span></span>  
  
```sql  
USE master;  
GO  
  
EXEC sp_detach_db @dbname = N'semanticsdb';  
GO  
```  
  
 <span data-ttu-id="e603c-152">**Remova o banco de dados de estatísticas semânticas de idioma.**</span><span class="sxs-lookup"><span data-stu-id="e603c-152">**Remove the semantic language statistics database.**</span></span>  
 <span data-ttu-id="e603c-153">Após cancelar o registro do banco de dados e desanexá-lo, você poderá simplesmente excluir o arquivo de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e603c-153">After unregistering and detaching the database, you can simply delete the database file.</span></span> <span data-ttu-id="e603c-154">Não há nenhum programa de desinstalação e nenhuma entrada em **Programas e Recursos** no Painel de Controle.</span><span class="sxs-lookup"><span data-stu-id="e603c-154">There is no uninstall program and there is no entry in **Programs and Features** in the Control Panel.</span></span>  
  
###  <a name="requirements-and-restrictions-for-installing-and-removing-the-semantic-language-statistics-database"></a><a name="reqinstall"></a><span data-ttu-id="e603c-155">Requisitos e restrições para instalar e remover o banco de dados Estatísticas Semânticas de Idioma</span><span class="sxs-lookup"><span data-stu-id="e603c-155">Requirements and Restrictions for Installing and Removing the Semantic Language Statistics Database</span></span>  
  
-   <span data-ttu-id="e603c-156">Você pode anexar e registrar somente um banco de dados de estatísticas semânticas de idioma em uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e603c-156">You can only attach and register one semantic language statistics database on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="e603c-157">Cada instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] em um único computador requer uma cópia física separada do banco de dados de estatísticas semânticas de idioma.</span><span class="sxs-lookup"><span data-stu-id="e603c-157">Each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on a single computer requires a separate physical copy of the semantic language statistics database.</span></span> <span data-ttu-id="e603c-158">Anexe uma cópia a cada instância.</span><span class="sxs-lookup"><span data-stu-id="e603c-158">Attach one copy to each instance.</span></span>  
  
-   <span data-ttu-id="e603c-159">Você não pode desanexar um banco de dados de estatísticas semânticas de idioma válido e registrado, e substituí-lo por um banco de dados arbitrário que tenha o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="e603c-159">You cannot detach a valid and registered semantic language statistics database and replace it with an arbitrary database that has the same name.</span></span> <span data-ttu-id="e603c-160">Isso causará a falha de populações de índice ativas ou futuras.</span><span class="sxs-lookup"><span data-stu-id="e603c-160">Doing so will cause active or future index populations to fail.</span></span>  
  
-   <span data-ttu-id="e603c-161">O banco de dados de estatísticas semânticas de idioma é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="e603c-161">The semantic language statistics database is read-only.</span></span> <span data-ttu-id="e603c-162">Você não pode personalizar esse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e603c-162">You cannot customize this database.</span></span> <span data-ttu-id="e603c-163">Se você alterar o conteúdo do banco de dados de alguma forma, os resultados da indexação semântica futura não serão determinísticos.</span><span class="sxs-lookup"><span data-stu-id="e603c-163">If you alter the content of the database in any way, the results for future semantic indexing are indeterministic.</span></span> <span data-ttu-id="e603c-164">Para restaurar o estado original desses dados, você poderá remover o banco de dados alterado, e baixar e anexar uma cópia nova e inalterada do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e603c-164">To restore the original state of this data, you can drop the altered database, and download and attach a new and unaltered copy of the database.</span></span>  
  
-   <span data-ttu-id="e603c-165">É possível desanexar ou remover o banco de dados de estatísticas semânticas de idioma.</span><span class="sxs-lookup"><span data-stu-id="e603c-165">It is possible to detach or drop the semantic language statistics database.</span></span> <span data-ttu-id="e603c-166">Se houver quaisquer operações de indexação ativas que tenham bloqueios de leitura no banco de dados, a operação desanexar ou soltar falhará ou atingirá o tempo limite. Isso é consistente com o comportamento existente.</span><span class="sxs-lookup"><span data-stu-id="e603c-166">If there are any active indexing operations that have read locks on the database, then the detach or drop operation will fail or time out. This is consistent with existing behavior.</span></span> <span data-ttu-id="e603c-167">Depois que o banco de dados for removido, as operações de indexação semântica falharão.</span><span class="sxs-lookup"><span data-stu-id="e603c-167">After the database is removed, semantic indexing operations will fail.</span></span>  
  
## <a name="installing-optional-support-for-newer-document-types"></a><span data-ttu-id="e603c-168">Instalando suporte opcional para tipos de documento mais novos</span><span class="sxs-lookup"><span data-stu-id="e603c-168">Installing Optional Support for Newer Document Types</span></span>  
  
###  <a name="how-to-install-the-latest-filters-for-microsoft-office-and-other-microsoft-document-types"></a><a name="office"></a><span data-ttu-id="e603c-169">Como instalar os filtros mais recentes para Microsoft Office e outros tipos de documento da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e603c-169">How to: Install the Latest Filters for Microsoft Office and other Microsoft Document Types</span></span>  
 <span data-ttu-id="e603c-170">Esta versão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instala os separadores de palavras e lematizadores mais recentes do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] , mas não instala os últimos filtros de documentos do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office e outros tipos de documento [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e603c-170">This release of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installs the latest [!INCLUDE[msCoName](../../../includes/msconame-md.md)] word breakers and stemmers, but does not install the latest filters for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office documents and other [!INCLUDE[msCoName](../../../includes/msconame-md.md)] document types.</span></span> <span data-ttu-id="e603c-171">Esses filtros são necessários para indexação de documentos criados com versões recentes do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office e outros aplicativos [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e603c-171">These filters are required for indexing documents created with recent versions of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office and other [!INCLUDE[msCoName](../../../includes/msconame-md.md)] applications.</span></span> <span data-ttu-id="e603c-172">Para baixar os filtros mais recentes, consulte [Microsoft Office 2010 Filter Packs](https://www.microsoft.com/download/details.aspx?id=17062).</span><span class="sxs-lookup"><span data-stu-id="e603c-172">To download the latest filters, see [Microsoft Office 2010 Filter Packs](https://www.microsoft.com/download/details.aspx?id=17062).</span></span>  
  
  
