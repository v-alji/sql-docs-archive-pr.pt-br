---
title: Extrair um DAC de um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.extractdacwizard.buildandsave.f1
- sql12.swb.extractdacwizard.setdacproperties.f1
- sql12.swb.extractdacwizard.validationandsummary.f1
- sql12.swb.extractdacwizard.introduction.f1
- sql12.swb.extractdacwizard.selectdatapage.f1
helpviewer_keywords:
- extract DAC
- How to [DAC], extract
- data-tier application [SQL Server], extract
- wizard [DAC], extract
ms.assetid: ae52a723-91c4-43fd-bcc7-f8de1d1f90e5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd024af9c201563773e20bae7e5fded1985abbe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583114"
---
# <a name="extract-a-dac-from-a-database"></a><span data-ttu-id="8ed04-102">Extrair um DAC de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="8ed04-102">Extract a DAC From a Database</span></span>
  <span data-ttu-id="8ed04-103">Use o **Assistente para Extrair um Aplicativo da Camada de Dados** ou um script do Windows PowerShell para extrair um pacote de DAC (aplicativo da camada de dados) de um banco de dados do SQL Server existente.</span><span class="sxs-lookup"><span data-stu-id="8ed04-103">Use either the **Extract Data-tier Application Wizard** or a Windows PowerShell script to extract a data-tier application (DAC) package from an existing SQL Server database.</span></span> <span data-ttu-id="8ed04-104">O processo de extração cria um arquivo de pacote de DAC que contém definições dos objetos de banco de dados e os elementos em nível de instância relacionados.</span><span class="sxs-lookup"><span data-stu-id="8ed04-104">The extraction process creates a DAC package file that contains definitions of the database objects and their related instance-level elements.</span></span> <span data-ttu-id="8ed04-105">Por exemplo, um arquivo de pacote de DAC contém as tabelas do banco de dados, os procedimentos armazenados, as exibições e os usuários junto com os logons que mapeiam para os usuários de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8ed04-105">For example, a DAC package file contains the database tables, stored procedures, views, and users, along with the logins that map to the database users.</span></span>  
  
-   <span data-ttu-id="8ed04-106">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="8ed04-106">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="8ed04-107">**Para extrair um DAC, usando:**  [o assistente para extrair aplicativo da camada de dados](#UsingDACExtractWizard), [PowerShell](#ExtractDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="8ed04-107">**To extract a DAC, using:**  [The Extract Data-tier Application Wizard](#UsingDACExtractWizard), [PowerShell](#ExtractDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="8ed04-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8ed04-108">Before You Begin</span></span>  
 <span data-ttu-id="8ed04-109">É possível extrair um DAC de bancos de dados que residam em instâncias do [!INCLUDE[ssSDS](../../includes/sssds-md.md)], do [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] Service Pack 4 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="8ed04-109">You can extract a DAC from databases residing on instances of [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] Service Pack 4 or later.</span></span> <span data-ttu-id="8ed04-110">Se o processo de extração for executado em um banco de dados que foi implantado de um DAC, só serão extraídas as definições dos objetos no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8ed04-110">If the extraction process is run against a database that was deployed from a DAC, only the definitions of the objects in the database are extracted.</span></span> <span data-ttu-id="8ed04-111">O processo não faz referência ao DAC registrado no `msdb` (**Master** in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="8ed04-111">The process does not reference the DAC registered in `msdb` (**master** in [!INCLUDE[ssSDS](../../includes/sssds-md.md)]).</span></span> <span data-ttu-id="8ed04-112">O processo de extração não registra a definição do DAC na instância atual do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="8ed04-112">The extraction process does not register the DAC definition in the current instance of the Database Engine.</span></span> <span data-ttu-id="8ed04-113">Para obter mais informações sobre como registrar um DAC, consulte [Register a Database As a DAC](register-a-database-as-a-dac.md).</span><span class="sxs-lookup"><span data-stu-id="8ed04-113">For more information about registering a DAC, see [Register a Database As a DAC](register-a-database-as-a-dac.md).</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="8ed04-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8ed04-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="8ed04-115">Um DAC só pode ser extraído de um banco de dados no [!INCLUDE[ssSDS](../../includes/sssds-md.md)]ou [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) ou posterior.</span><span class="sxs-lookup"><span data-stu-id="8ed04-115">A DAC can only be extracted from a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span> <span data-ttu-id="8ed04-116">Você não poderá extrair um DAC se o banco de dados tiver objetos que não tenham suporte em um DAC ou usuários contidos.</span><span class="sxs-lookup"><span data-stu-id="8ed04-116">You cannot extract a DAC if the database has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="8ed04-117">Para obter mais informações sobre os tipos de objetos com suporte em um DAC, consulte [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="8ed04-117">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8ed04-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="8ed04-118">Permissions</span></span>  
 <span data-ttu-id="8ed04-119">A extração de um DAC exige, pelo menos, as permissões ALTER ANY LOGIN e VIEW DEFINITION do escopo do banco de dados, bem como as permissões SELECT em **sys.sql_expression_dependencies**.</span><span class="sxs-lookup"><span data-stu-id="8ed04-119">Extracting a DAC requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, as well as SELECT permissions on **sys.sql_expression_dependencies**.</span></span> <span data-ttu-id="8ed04-120">A extração de um DAC pode ser feita por membros da função de servidor fixa securityadmin que também são membros da função de banco de dados fixa database_owner no banco de dados do qual o DAC é extraído.</span><span class="sxs-lookup"><span data-stu-id="8ed04-120">Extracting a DAC can be done by members of the securityadmin fixed server role who are also members of the database_owner fixed database role in the database from which the DAC is extracted.</span></span> <span data-ttu-id="8ed04-121">Membros da função de servidor fixa sysadmin ou a conta interna do administrador do sistema do SQL Server chamada **sa** também podem extrair um DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-121">Members of the sysadmin fixed server role or the built-in SQL Server system administrator account named **sa** can also extract a DAC.</span></span>  
  
##  <a name="using-the-extract-data-tier-application-wizard"></a><a name="UsingDACExtractWizard"></a> <span data-ttu-id="8ed04-122">Usando o Assistente para Extrair um Aplicativo da Camada de Dados</span><span class="sxs-lookup"><span data-stu-id="8ed04-122">Using the Extract Data-tier Application Wizard</span></span>  
 <span data-ttu-id="8ed04-123">**Para extrair um DAC usando um assistente**</span><span class="sxs-lookup"><span data-stu-id="8ed04-123">**To Extract a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="8ed04-124">No **Pesquisador de Objetos**, expanda o nó da instância que contém o banco de dados do qual o DAC será extraído.</span><span class="sxs-lookup"><span data-stu-id="8ed04-124">In **Object Explorer**, expand the node for the instance containing the database from which the DAC is to be extracted.</span></span>  
  
2.  <span data-ttu-id="8ed04-125">Expanda o nó **Bancos de Dados** .</span><span class="sxs-lookup"><span data-stu-id="8ed04-125">Expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="8ed04-126">Clique com o botão direito do mouse no nó do banco de dados do qual o DAC é extraído, aponte para **Tarefas** e selecione **Extrair Aplicativo da Camada de Dados...**</span><span class="sxs-lookup"><span data-stu-id="8ed04-126">Right-click the node for the database from which the DAC is to be extracted, point to **Tasks**, and then select **Extract Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="8ed04-127">Conclua as etapas das caixas de diálogo do assistente:</span><span class="sxs-lookup"><span data-stu-id="8ed04-127">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="8ed04-128">Página de Introdução</span><span class="sxs-lookup"><span data-stu-id="8ed04-128">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="8ed04-129">página Selecionar Dados</span><span class="sxs-lookup"><span data-stu-id="8ed04-129">Select Data Page</span></span>](#SelectData)  
  
    3.  [<span data-ttu-id="8ed04-130">Página Definir Propriedades</span><span class="sxs-lookup"><span data-stu-id="8ed04-130">Set Properties Page</span></span>](#SetProperties)  
  
    4.  [<span data-ttu-id="8ed04-131">Página Validação e Resumo</span><span class="sxs-lookup"><span data-stu-id="8ed04-131">Validation and Summary Page</span></span>](#ValidateSummary)  
  
    5.  [<span data-ttu-id="8ed04-132">Página Criar Pacote</span><span class="sxs-lookup"><span data-stu-id="8ed04-132">Build Package Page</span></span>](#BuildPackage)  
  
###  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="8ed04-133">Página de Introdução</span><span class="sxs-lookup"><span data-stu-id="8ed04-133">Introduction Page</span></span>  
 <span data-ttu-id="8ed04-134">Esta página descreve as etapas para extrair um aplicativo da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="8ed04-134">This page describes the steps for extracting a data-tier application.</span></span>  
  
 <span data-ttu-id="8ed04-135">**Não mostrar esta página novamente.**</span><span class="sxs-lookup"><span data-stu-id="8ed04-135">**Do not show this page again.**</span></span> <span data-ttu-id="8ed04-136">- Clique na caixa de seleção para interromper a exibição da página no futuro.</span><span class="sxs-lookup"><span data-stu-id="8ed04-136">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="8ed04-137">**Avançar >**: continua para a página **Escolher Método**.</span><span class="sxs-lookup"><span data-stu-id="8ed04-137">**Next >** - Proceeds to the **Choose Method** page.</span></span>  
  
 <span data-ttu-id="8ed04-138">**Cancelar** – Encerra o assistente sem extrair um aplicativo da camada de dados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8ed04-138">**Cancel** - Ends the wizard without extracting a data-tier application from the database.</span></span>  
  
###  <a name="select-data-page"></a><a name="SelectData"></a><span data-ttu-id="8ed04-139">Página selecionar dados</span><span class="sxs-lookup"><span data-stu-id="8ed04-139">Select Data Page</span></span>  
 <span data-ttu-id="8ed04-140">Use esta página do assistente para selecionar os dados de referência que você deseja incluir em seu arquivo de pacote de DAC (aplicativo da camada de dados).</span><span class="sxs-lookup"><span data-stu-id="8ed04-140">Use this page of the wizard to select the reference data that you want to include in your data-tier application (DAC) package file.</span></span> <span data-ttu-id="8ed04-141">A inclusão de dados em seu pacote de DAC é opcional.</span><span class="sxs-lookup"><span data-stu-id="8ed04-141">Including data in your DAC package is optional.</span></span> <span data-ttu-id="8ed04-142">O pacote de DAC já incluirá o esquema de todos os objetos de banco de dados com suporte e objetos de instância relacionados a seu banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8ed04-142">The DAC package will already include the schema of all supported database objects and instance objects related to your database.</span></span>  
  
 <span data-ttu-id="8ed04-143">Você pode incluir até 10 MB de dados de referência em seu arquivo de pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-143">You can include up to 10 MB of reference data in your DAC package file.</span></span> <span data-ttu-id="8ed04-144">No entanto, para que tabelas sejam incluídas no DAC, elas não podem conter tipos de dados BLOB (objeto binário grande) como **image** ou **varchar(max)**.</span><span class="sxs-lookup"><span data-stu-id="8ed04-144">However, for tables to be included in the DAC, they may not contain binary large object (BLOB) data types such as **image** or **varchar(max)**.</span></span> <span data-ttu-id="8ed04-145">Para extrair quantidades maiores de dados para transferência para outro banco de dados, use o SQL Server Integration Services, o utilitário de cópia em massa ou um das muitas outras técnicas de migração de dados.</span><span class="sxs-lookup"><span data-stu-id="8ed04-145">To extract larger amounts of data for transferring to another database, use SQL Server Integration Services, the bulk copy utility, or one of many other data migration techniques.</span></span>  
  
 <span data-ttu-id="8ed04-146">**Tabela de banco de dados** – Marque a caixa de seleção ao lado das tabelas do banco de dados que contêm os dados que você deseja incluir em seu pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-146">**Database table** - Select the check box next to the database tables which contain the data that you want to include in your DAC package.</span></span> <span data-ttu-id="8ed04-147">Você pode selecionar até dez tabelas com mais ou menos 10.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="8ed04-147">You can select up to ten tables that have 10,000 rows or less.</span></span>  
  
###  <a name="set-properties-page"></a><a name="SetProperties"></a> <span data-ttu-id="8ed04-148">Página Definir Propriedades</span><span class="sxs-lookup"><span data-stu-id="8ed04-148">Set Properties Page</span></span>  
 <span data-ttu-id="8ed04-149">Use esta página do assistente para descrever o aplicativo da camada de dados (DAC).</span><span class="sxs-lookup"><span data-stu-id="8ed04-149">Use this page of the wizard to describe the data-tier application (DAC).</span></span> <span data-ttu-id="8ed04-150">Estas propriedades são usadas para identificar o DAC e ajudam a distingui-lo de outros.</span><span class="sxs-lookup"><span data-stu-id="8ed04-150">These properties are used to identify the DAC and help distinguish it from others.</span></span>  
  
 <span data-ttu-id="8ed04-151">**Nome** – Este nome identifica o DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-151">**Name** - This name identifies the DAC.</span></span> <span data-ttu-id="8ed04-152">Pode ser diferente do nome do arquivo de pacote de DAC e deve descrever seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8ed04-152">It can be different than the name of the DAC package file and should describe your application.</span></span> <span data-ttu-id="8ed04-153">Por exemplo, se o banco de dados for usado para um aplicativo de finanças, você poderá nomeá-lo como Finanças do DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-153">For example, if the database is used for a finance application, you may wish to name the DAC Finance.</span></span>  
  
 <span data-ttu-id="8ed04-154">**Versão (use xx.xx.xx.xx, em que x é um número)** – Um valor numérico que identifica a versão do DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-154">**Version (use xx.xx.xx.xx, where x is a number)** - A numeric value that identifies the version of the DAC.</span></span> <span data-ttu-id="8ed04-155">A versão do DAC é usada no Visual Studio para identificar a versão do DAC em que os desenvolvedores estão trabalhando.</span><span class="sxs-lookup"><span data-stu-id="8ed04-155">The DAC version is used in Visual Studio to identify the version of the DAC that developers are working on.</span></span> <span data-ttu-id="8ed04-156">Ao implantar um DAC, a versão é armazenada no `msdb` banco de dados e, posteriormente, pode ser exibida no nó **aplicativos da camada de dados** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ed04-156">When deploying a DAC, the version is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="8ed04-157">**Descrição:** – Opcional.</span><span class="sxs-lookup"><span data-stu-id="8ed04-157">**Description:** - Optional.</span></span> <span data-ttu-id="8ed04-158">Descreve o DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-158">Describes the DAC.</span></span> <span data-ttu-id="8ed04-159">Ao implantar um DAC, a descrição é armazenada no `msdb` banco de dados e, posteriormente, pode ser exibida no nó **aplicativos da camada data** no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ed04-159">When deploying a DAC, the description is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="8ed04-160">**Salvar o arquivo de pacote de DAC (inclua a extensão .dacpac no nome do arquivo):** – Salva o DAC em um arquivo de pacote de DAC, com uma extensão .dacpac.</span><span class="sxs-lookup"><span data-stu-id="8ed04-160">**Save to DAC package file (include .dacpac extension with file name):** - Saves the DAC to a DAC package file, with a .dacpac extension.</span></span> <span data-ttu-id="8ed04-161">Clique no botão **Procurar** para especificar um nome e um local para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="8ed04-161">Click the **Browse** button to specify a name and location for the file.</span></span>  
  
 <span data-ttu-id="8ed04-162">**Substituir o arquivo existente** – Marque esta caixa de seleção para substituir o arquivo do pacote de DAC se já existir um com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="8ed04-162">**Overwrite existing file** - Select this check box to replace the DAC package file if one already exists with the same name.</span></span>  
  
###  <a name="validation-and-summary-page"></a><a name="ValidateSummary"></a> <span data-ttu-id="8ed04-163">Página Validação e Resumo</span><span class="sxs-lookup"><span data-stu-id="8ed04-163">Validation and Summary Page</span></span>  
 <span data-ttu-id="8ed04-164">Nesta página, o assistente valida se todos os objetos de banco de dados têm suporte de um DAC (aplicativo da camada de dados).</span><span class="sxs-lookup"><span data-stu-id="8ed04-164">On this page, the wizard validates that all database objects are supported by a data-tier application (DAC).</span></span> <span data-ttu-id="8ed04-165">Também verifica dependências entre objetos de banco de dados para determinar o conjunto de objetos que podem ser incluídos com êxito no DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-165">It also checks dependencies across database objects to determine the set of objects that can be successfully included in the DAC.</span></span> <span data-ttu-id="8ed04-166">Depois disso, exibe o relatório de validação e resume as opções que você selecionou neste assistente.</span><span class="sxs-lookup"><span data-stu-id="8ed04-166">After that, it displays the validation report and summarizes the options that you have selected in this wizard.</span></span> <span data-ttu-id="8ed04-167">Para alterar uma opção, clique em **Anterior**.</span><span class="sxs-lookup"><span data-stu-id="8ed04-167">To change an option, click **Previous**.</span></span> <span data-ttu-id="8ed04-168">Para iniciar a extração de um DAC, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8ed04-168">To begin extracting a DAC, click **Next**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ed04-169">Se um ou mais objetos não tiverem suporte de um DAC, o botão **Avançar** será desabilitado e o processo de extração talvez não continue.</span><span class="sxs-lookup"><span data-stu-id="8ed04-169">If one or more objects are not supported by a DAC, then the **Next** button is disabled and the extraction process may not continue.</span></span> <span data-ttu-id="8ed04-170">Nesses casos, é recomendável remover os objetos sem suporte e, em seguida, executar esse assistente novamente.</span><span class="sxs-lookup"><span data-stu-id="8ed04-170">In such cases, it is recommended to remove the non-supported objects and then run this wizard again.</span></span>  
  
 <span data-ttu-id="8ed04-171">**Resumo** – Um resumo das opções que você selecionou é listado em **Propriedades do DAC**.</span><span class="sxs-lookup"><span data-stu-id="8ed04-171">**Summary** - A summary of the options you have selected are listed under **DAC properties**.</span></span> <span data-ttu-id="8ed04-172">Os resultados da validação são listados em **Objetos do DAC**.</span><span class="sxs-lookup"><span data-stu-id="8ed04-172">The results of the validation are listed under **DAC objects**.</span></span> <span data-ttu-id="8ed04-173">Há três tipos de resultados da validação:</span><span class="sxs-lookup"><span data-stu-id="8ed04-173">There are three types of results from the validation:</span></span>  
  
-   <span data-ttu-id="8ed04-174">**Objetos incluídos no DAC com êxito**: estes objetos e suas dependências têm suporte e podem ser incluídos com êxito no DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-174">**Objects included in DAC successfully**: these objects and their dependencies are supported, and can be included in the DAC successfully.</span></span>  
  
-   <span data-ttu-id="8ed04-175">**Objetos incluídos no DAC com avisos**: estes objetos têm suporte, mas dependem de outros objetos que não têm suporte em um DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-175">**Objects included in DAC with warnings**: these objects are supported, but depend on other objects that are not supported in a DAC.</span></span>  
  
-   <span data-ttu-id="8ed04-176">**Objetos não incluídos no DAC**: estes objetos não têm suporte e devem ser removidos do banco de dados antes da extração bem-sucedida de um DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-176">**Objects not included in DAC**: these objects are not supported and must be removed from the database before successfully extracting a DAC.</span></span>  
  
 <span data-ttu-id="8ed04-177">O processo de validação verifica vários níveis de dependências.</span><span class="sxs-lookup"><span data-stu-id="8ed04-177">The validation process checks multiple levels of dependencies.</span></span> <span data-ttu-id="8ed04-178">Por exemplo, se um procedimento armazenado depender de uma tabela que usa o tipo de dados de CLR não tiver suporte, o procedimento armazenado será listado em **Objetos incluídos no DAC com avisos**.</span><span class="sxs-lookup"><span data-stu-id="8ed04-178">For example, if a stored procedure depends on a table that uses the unsupported CLR data type, the stored procedure will be listed under **Objects included in DAC with warnings**.</span></span>  
  
 <span data-ttu-id="8ed04-179">Se um ou mais objetos não tiverem suporte de um DAC, o botão **Avançar** será desabilitado e o processo de extração não continuará.</span><span class="sxs-lookup"><span data-stu-id="8ed04-179">If one or more objects are not supported by a DAC, then the **Next** button is disabled and the extraction process will not continue.</span></span> <span data-ttu-id="8ed04-180">Nesses casos, é recomendável remover os objetos que não têm suporte e, em seguida, executar esse assistente novamente.</span><span class="sxs-lookup"><span data-stu-id="8ed04-180">In such cases, it is recommended to remove the objects that are not supported and then run this wizard again.</span></span>  
  
 <span data-ttu-id="8ed04-181">**Salvar Relatório** – Permite salvar um arquivo baseado em HTML que lista todos os objetos no nó **Objetos do DAC** no resumo.</span><span class="sxs-lookup"><span data-stu-id="8ed04-181">**Save Report** - Enables you to save an HTML-based file that lists all of the objects under the **DAC Objects** node in the summary.</span></span> <span data-ttu-id="8ed04-182">Esse relatório pode ser útil quando alguns de seus objetos de banco de dados não têm suporte em um DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-182">This report can be useful when some of your database objects are not supported in a DAC.</span></span> <span data-ttu-id="8ed04-183">Use o relatório para alterar ou remover objetos que não têm suporte, antes de tentar extrair o DAC novamente.</span><span class="sxs-lookup"><span data-stu-id="8ed04-183">Use the report to change or remove objects that are not supported, before trying to extract the DAC again.</span></span>  
  
###  <a name="build-package-page"></a><a name="BuildPackage"></a><span data-ttu-id="8ed04-184">Página Criar pacote</span><span class="sxs-lookup"><span data-stu-id="8ed04-184">Build Package Page</span></span>  
 <span data-ttu-id="8ed04-185">Use esta página para monitorar o andamento do assistente enquanto ele extrai o aplicativo da camada de dados (DAC).</span><span class="sxs-lookup"><span data-stu-id="8ed04-185">Use this page to monitor the progress of the wizard as it extracts the data-tier application (DAC).</span></span>  
  
 <span data-ttu-id="8ed04-186">**Ação** – Durante a ação **Criar e salvar arquivo de pacote de DAC** , o assistente extrai um DAC do banco de dados SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8ed04-186">**Action** - During the **Create and save DAC package file** action, the wizard extracts a DAC from your SQL Server database.</span></span> <span data-ttu-id="8ed04-187">Em seguida, o pacote de DAC é criado na memória e salvo no local especificado.</span><span class="sxs-lookup"><span data-stu-id="8ed04-187">Then, a DAC package is created in memory and saved to the location you specified.</span></span> <span data-ttu-id="8ed04-188">Clique nos links na coluna **Resultado** para ver o resultado da etapa correspondente.</span><span class="sxs-lookup"><span data-stu-id="8ed04-188">Click on the links in the **Result** column to see the outcome of the corresponding step.</span></span>  
  
 <span data-ttu-id="8ed04-189">**Salvar Relatório** – Clique para salvar os resultados do progresso do assistente em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="8ed04-189">**Save Report** - Click to save the results of the wizard's progress to a file.</span></span>  
  
 <span data-ttu-id="8ed04-190">**Concluir** – Clique para fechar o assistente após a conclusão do processamento, ou se ocorrer um erro.</span><span class="sxs-lookup"><span data-stu-id="8ed04-190">**Finish** - Click to close the wizard after processing has completed, or if an error occurs.</span></span>  
  
##  <a name="extract-a-dac-using-powershell"></a><a name="ExtractDACPowerShell"></a><span data-ttu-id="8ed04-191">Extrair um DAC usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ed04-191">Extract a DAC Using PowerShell</span></span>  
 <span data-ttu-id="8ed04-192">**Para extrair um DAC de um banco de dados usando o método Extract() em um script do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8ed04-192">**To extract a DAC from a database using the Extract() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="8ed04-193">Crie um objeto do Servidor SMO e defina-o como a instância que contém o banco de dados do qual o DAC será extraído.</span><span class="sxs-lookup"><span data-stu-id="8ed04-193">Create a SMO Server object and set it to the instance that contains the database from which the DAC is to be extracted.</span></span>  
  
2.  <span data-ttu-id="8ed04-194">Adicione uma variável que especifique o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8ed04-194">Add a variable that specifies the name of the database.</span></span>  
  
3.  <span data-ttu-id="8ed04-195">Especifique os metadados do DAC, como o nome, a versão e a descrição do DAC.</span><span class="sxs-lookup"><span data-stu-id="8ed04-195">Specify the metadata for the DAC, such as the DAC name, version, and description.</span></span>  
  
4.  <span data-ttu-id="8ed04-196">Especifique o caminho completo e o nome de arquivo do arquivo de pacote de DAC extraído.</span><span class="sxs-lookup"><span data-stu-id="8ed04-196">Specify the path and file name for the extracted DAC package file.</span></span>  
  
5.  <span data-ttu-id="8ed04-197">Execute o método Extract com as informações especificadas acima.</span><span class="sxs-lookup"><span data-stu-id="8ed04-197">Run the Extract method with the information specified above.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="8ed04-198">Exemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="8ed04-198">Example (PowerShell)</span></span>  
 <span data-ttu-id="8ed04-199">O exemplo a seguir extrai um DAC denominado MyApplication de um banco de dados denominado MyDB.</span><span class="sxs-lookup"><span data-stu-id="8ed04-199">The following example extracts a DAC named MyApplication from a database named MyDB.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Specify the database to extract to a DAC.  
$dbname = "MyDB"  
  
## Specify the DAC metadata.  
$applicationname = "MyApplication"  
$version = "1.0.0.0"  
$description = "This DAC defines the database used by my application."  
  
## Specify the location and name for the extracted DAC package.  
$dacpacPath = "C:\MyDACs\MyApplication.dacpac"  
  
## Extract the DAC.  
$extractionunit = New-Object Microsoft.SqlServer.Management.Dac.DacExtractionUnit($srv, $dbname, $applicationname, $version)  
$extractionunit.Description = $description  
$extractionunit.Extract($dacpacPath)  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ed04-200">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8ed04-200">See Also</span></span>  
 [<span data-ttu-id="8ed04-201">Aplicativos da camada de dados</span><span class="sxs-lookup"><span data-stu-id="8ed04-201">Data-tier Applications</span></span>](data-tier-applications.md)  
