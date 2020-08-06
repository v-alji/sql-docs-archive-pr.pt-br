---
title: Validar um pacote de DAC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- data-tier application [SQL Server], validate
- data-tier application [SQL Server], compare
- validate DAC
- compare DACs
- data-tier application [SQL Server], view
- view DAC
ms.assetid: 726ffcc2-9221-424a-8477-99e3f85f03bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 078c7bfeef2ff8636243f4853c03de252c7b9289
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583112"
---
# <a name="validate-a-dac-package"></a><span data-ttu-id="c5da1-102">Validar um pacote de DAC</span><span class="sxs-lookup"><span data-stu-id="c5da1-102">Validate a DAC Package</span></span>
  <span data-ttu-id="c5da1-103">Esta é uma prática recomendada para revisar o conteúdo de um pacote de DAC antes de implantá-lo em produção e também para validar as ações de atualização antes de atualizar um DAC existente.</span><span class="sxs-lookup"><span data-stu-id="c5da1-103">It is a good practice to review the contents of a DAC package before deploying it in production, and to validate the upgrade actions before upgrading an existing DAC.</span></span> <span data-ttu-id="c5da1-104">Isso é especialmente válido durante a implantação de pacotes que não foram desenvolvidos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c5da1-104">This is especially true when deploying packages that were not developed in your organization.</span></span>  
  
1.  <span data-ttu-id="c5da1-105">**Antes de começar:**  [Pré-requisitos](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="c5da1-105">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
2.  <span data-ttu-id="c5da1-106">**Para atualizar um DAC, usando:**  [Exibir o Conteúdo de um DAC](#ViewDACContents), [Exibir Alterações no Banco de Dados](#ViewDBChanges), [Exibir Ações de Atualização](#ViewUpgradeActions), [Compare DACs](#CompareDACs)</span><span class="sxs-lookup"><span data-stu-id="c5da1-106">**To upgrade a DAC, using:**  [View the Contents of a DAC](#ViewDACContents), [View Database Changes](#ViewDBChanges), [View Upgrade Actions](#ViewUpgradeActions), [Compare DACs](#CompareDACs)</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c5da1-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c5da1-107">Prerequisites</span></span>  
 <span data-ttu-id="c5da1-108">Recomendamos não implantar um pacote de DAC de origens desconhecidas ou não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="c5da1-108">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="c5da1-109">Como os DACs podem conter código mal-intencionado que pode executar código [!INCLUDE[tsql](../../includes/tsql-md.md)] sem finalidade ou provocar erros modificando o esquema.</span><span class="sxs-lookup"><span data-stu-id="c5da1-109">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="c5da1-110">Antes de usar um DAC de uma origem desconhecida ou não confiável, implante-o em uma instância de teste isolada do [!INCLUDE[ssDE](../../includes/ssde-md.md)], execute [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) no banco de dados. Além disso, examine o código, como procedimentos armazenados ou outro código definido pelo usuário, no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c5da1-110">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], run [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database, and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
##  <a name="view-the-contents-of-a-dac"></a><a name="ViewDACContents"></a> <span data-ttu-id="c5da1-111">Exibir o Conteúdo de um DAC</span><span class="sxs-lookup"><span data-stu-id="c5da1-111">View the Contents of a DAC</span></span>  
 <span data-ttu-id="c5da1-112">Existem dois mecanismos para exibição do conteúdo de um pacote de DAC (aplicativo da camada de dados).</span><span class="sxs-lookup"><span data-stu-id="c5da1-112">There are two mechanisms for viewing the contents of a data-tier application (DAC) package.</span></span> <span data-ttu-id="c5da1-113">Você pode importar o pacote de DAC para um projeto de DAC no SQL Server Developer Tools.</span><span class="sxs-lookup"><span data-stu-id="c5da1-113">You can import the DAC package to a DAC project in SQL Server Developer Tools.</span></span> <span data-ttu-id="c5da1-114">É possível desempacotar o conteúdo do pacote em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="c5da1-114">You can unpack the contents of the package to a folder.</span></span>  
  
 <span data-ttu-id="c5da1-115">**Exiba um DAC no SQL Server Developer Tools**</span><span class="sxs-lookup"><span data-stu-id="c5da1-115">**View a DAC in SQL Server Developer Tools**</span></span>  
  
1.  <span data-ttu-id="c5da1-116">Abra o menu **Arquivo**, selecione **Novo** e, em seguida, selecione **Projeto...** .</span><span class="sxs-lookup"><span data-stu-id="c5da1-116">Open the **File** menu, select **New**, and then select **Project...**.</span></span>  
  
2.  <span data-ttu-id="c5da1-117">Selecione o modelo de projeto **SQL Server** e especifique um **Nome**, um **Local**e um **Nome de solução**.</span><span class="sxs-lookup"><span data-stu-id="c5da1-117">Select the **SQL Server** project template, and specify a **Name**, **Location**, and **Solution name**.</span></span>  
  
3.  <span data-ttu-id="c5da1-118">No **Gerenciador de Soluções**, clique com o botão direito do mouse no nó do projeto e selecione **Propriedades...** .</span><span class="sxs-lookup"><span data-stu-id="c5da1-118">In **Solution Explorer**, right click the project node and select **Properties...**.</span></span>  
  
4.  <span data-ttu-id="c5da1-119">Na guia **Configurações de Projeto** , na seção **Tipos de Saída** , marque a caixa de seleção **Aplicativo da Camada de Dados (arquivo .dacpac)** e feche a caixa de diálogo de propriedades.</span><span class="sxs-lookup"><span data-stu-id="c5da1-119">On the **Project Settings** tab, in the **Output Types** section, select the **Data-tier Application (.dacpac File)** check box, and then close the properties dialog.</span></span>  
  
5.  <span data-ttu-id="c5da1-120">No **Gerenciador de Soluções**, clique com o botão direito do mouse no nó do projeto e selecione **Importar Aplicativo da Camada de Dados...** .</span><span class="sxs-lookup"><span data-stu-id="c5da1-120">In **Solution Explorer**, right click the project node and select **Import Data-tier Application...**.</span></span>  
  
6.  <span data-ttu-id="c5da1-121">Use o **Gerenciador de Soluções** para abrir todos os arquivos no DAC, como a política de seleção de servidor e os scripts de pré e pós-implantação.</span><span class="sxs-lookup"><span data-stu-id="c5da1-121">Use **Solution Explorer** to open all of the files in the DAC, such as the server selection policy and the pre- and post-deployment scripts.</span></span>  
  
7.  <span data-ttu-id="c5da1-122">Use a **Exibição de Esquema** para examinar todos os objetos no esquema, especialmente o código em objetos, como funções ou procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="c5da1-122">Use the **Schema View** to review all of the objects in the schema, particularly reviewing the code in objects such as functions or stored procedures.</span></span>  
  
 <span data-ttu-id="c5da1-123">**Exibir um DAC em uma pasta**</span><span class="sxs-lookup"><span data-stu-id="c5da1-123">**View a DAC in a Folder**</span></span>  
  
-   <span data-ttu-id="c5da1-124">Desempacote o pacote de DAC em uma pasta seguindo as instruções em [Unpack a DAC Package](unpack-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="c5da1-124">Unpack the DAC package into a folder by following the instructions in [Unpack a DAC Package](unpack-a-dac-package.md).</span></span>  
  
-   <span data-ttu-id="c5da1-125">Exiba os conteúdo dos scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] abrindo-os no Editor de Consulta [!INCLUDE[ssDE](../../includes/ssde-md.md)] no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5da1-125">View the contents of the [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts by opening them in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
-   <span data-ttu-id="c5da1-126">Exiba o conteúdo dos arquivos de texto em ferramentas como o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="c5da1-126">View the contents of the text files in tools such as notepad.</span></span>  
  
##  <a name="view-database-changes"></a><a name="ViewDBChanges"></a> <span data-ttu-id="c5da1-127">Exibir Alterações no Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="c5da1-127">View Database Changes</span></span>  
 <span data-ttu-id="c5da1-128">Depois que a versão atual de um DAC for implantada para produção, alterações poderão ter sido feitas diretamente no banco de dados associado que podem estar em conflito com o esquema definido em uma nova versão do DAC.</span><span class="sxs-lookup"><span data-stu-id="c5da1-128">After the current version of a DAC was deployed to production, changes may have been made directly to the associated database that might conflict with the schema defined in a new version of the DAC.</span></span> <span data-ttu-id="c5da1-129">Antes de atualizar para uma nova versão do DAC, verifique se foram feitas alterações no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c5da1-129">Before upgrading to a new version of the DAC, check to see if such changes have been made to the database.</span></span>  
  
 <span data-ttu-id="c5da1-130">**Exibir alterações do banco de dados usando um assistente**</span><span class="sxs-lookup"><span data-stu-id="c5da1-130">**View Database Changes by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="c5da1-131">Execute o assistente para **Atualizar Aplicativo da Camada de Dados** , especificando o DAC implantado no momento e o pacote de DAC que contém a nova versão do DAC.</span><span class="sxs-lookup"><span data-stu-id="c5da1-131">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="c5da1-132">Na página **Detectar Alteração** , examine o relatório das alterações que foram feitas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c5da1-132">On the **Detect Change** page, review the report of the changes that have been made to the database.</span></span>  
  
3.  <span data-ttu-id="c5da1-133">Selecione **Cancelar** se não desejar continuar com a atualização.</span><span class="sxs-lookup"><span data-stu-id="c5da1-133">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="c5da1-134">Para obter mais informações sobre como usar o assistente, veja [Atualizar um aplicativo da camada de dados](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="c5da1-134">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
### <a name="view-database-changes-by-using-powershell"></a><span data-ttu-id="c5da1-135">Exibir alterações do banco de dados usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5da1-135">View Database Changes by Using PowerShell</span></span>
  
1.  <span data-ttu-id="c5da1-136">Crie um objeto de servidor SMO e defina-o como a instância que contém o DAC a ser exibido.</span><span class="sxs-lookup"><span data-stu-id="c5da1-136">Create a SMO Server object and set it to the instance that contains the DAC to be viewed.</span></span>  
  
2.  <span data-ttu-id="c5da1-137">Abra um objeto `ServerConnection` e conecte-se à mesma instância.</span><span class="sxs-lookup"><span data-stu-id="c5da1-137">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="c5da1-138">Especifique o nome de DAC em uma variável.</span><span class="sxs-lookup"><span data-stu-id="c5da1-138">Specify the DAC name in a variable.</span></span>  
  
4.  <span data-ttu-id="c5da1-139">Use o método `GetDatabaseChanges()` para recuperar um objeto `ChangeResults` e redirecione o objeto para um arquivo de texto para gerar um relatório simples de objetos novos, excluídos e alterados.</span><span class="sxs-lookup"><span data-stu-id="c5da1-139">Use the `GetDatabaseChanges()` method to retrieve a `ChangeResults` object, and pipe the object to a text file to generate a simple report of new, deleted, and changed objects.</span></span>  
  
### <a name="view-database-changes-example-powershell"></a><span data-ttu-id="c5da1-140">Exibir exemplo de alterações do banco de dados (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c5da1-140">View Database Changes Example (PowerShell)</span></span>
  
 <span data-ttu-id="c5da1-141">O exemplo a seguir relata alterações de banco de dados realizadas em um DAC implantado denominado MyApplicaiton.</span><span class="sxs-lookup"><span data-stu-id="c5da1-141">The following example reports any database changes that have been made in a deployed DAC named MyApplicaiton.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the change list and save to file.  
$dacChanges = $dacstore.GetDatabaseChanges($dacName) | Out-File -Filepath C:\DACScripts\MyApplicationChanges.txt  
```  
  
##  <a name="view-upgrade-actions"></a><a name="ViewUpgradeActions"></a> <span data-ttu-id="c5da1-142">Exibir Ações de Atualização</span><span class="sxs-lookup"><span data-stu-id="c5da1-142">View Upgrade Actions</span></span>  
 <span data-ttu-id="c5da1-143">Antes de usar uma nova versão de um pacote de DAC para atualizar um DAC que foi implantado de um pacote de DAC anterior, você pode gerar um relatório que contém as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] a serem executadas durante a atualização e, depois, examinar as instruções.</span><span class="sxs-lookup"><span data-stu-id="c5da1-143">Before using a new version of a DAC package to upgrade a DAC that was deployed from an earlier DAC package, you can generate a report that contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that will be run during the upgrade, and then review the statements.</span></span>  
  
 <span data-ttu-id="c5da1-144">**Relate ações de atualização usando um assistente**</span><span class="sxs-lookup"><span data-stu-id="c5da1-144">**Report Upgrade Actions by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="c5da1-145">Execute o assistente para **Atualizar Aplicativo da Camada de Dados** , especificando o DAC implantado no momento e o pacote de DAC que contém a nova versão do DAC.</span><span class="sxs-lookup"><span data-stu-id="c5da1-145">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="c5da1-146">Na página **Resumo** , examine o relatório das ações de atualização.</span><span class="sxs-lookup"><span data-stu-id="c5da1-146">On the **Summary** page, review the report of the upgrade actions.</span></span>  
  
3.  <span data-ttu-id="c5da1-147">Selecione **Cancelar** se não desejar continuar com a atualização.</span><span class="sxs-lookup"><span data-stu-id="c5da1-147">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="c5da1-148">Para obter mais informações sobre como usar o assistente, veja [Atualizar um aplicativo da camada de dados](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="c5da1-148">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
 <span data-ttu-id="c5da1-149">**Relate ações de atualização usando o PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c5da1-149">**Report Upgrade Actions by Using PowerShell**</span></span>  
  
1.  <span data-ttu-id="c5da1-150">Crie um objeto de servidor SMO e defina-o como a instância que contém o DAC implantado.</span><span class="sxs-lookup"><span data-stu-id="c5da1-150">Create a SMO Server object and set it to the instance that contains the deployed DAC.</span></span>  
  
2.  <span data-ttu-id="c5da1-151">Abra um objeto `ServerConnection` e conecte-se à mesma instância.</span><span class="sxs-lookup"><span data-stu-id="c5da1-151">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="c5da1-152">Use `System.IO.File` para carregar o arquivo de pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="c5da1-152">Use `System.IO.File` to load the DAC package file.</span></span>  
  
4.  <span data-ttu-id="c5da1-153">Especifique o nome de DAC em uma variável.</span><span class="sxs-lookup"><span data-stu-id="c5da1-153">Specify the DAC name in a variable.</span></span>  
  
5.  <span data-ttu-id="c5da1-154">Use o método `GetIncrementalUpgradeScript()` para obter uma lista das instruções Transact-SQL que uma atualização executaria e redirecione a lista para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c5da1-154">Use the `GetIncrementalUpgradeScript()` method to get a list of the Transact-SQL statements an upgrade would run, and pipe the list to a text file.</span></span>  
  
6.  <span data-ttu-id="c5da1-155">Feche o fluxo de arquivos usado para ler o arquivo de pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="c5da1-155">Close the file stream used to read the DAC package file.</span></span>  
  
### <a name="view-upgrade-actions-example-powershell"></a><span data-ttu-id="c5da1-156">Exibir o exemplo de ações de atualização (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c5da1-156">View Upgrade Actions Example (PowerShell)</span></span>
  
 <span data-ttu-id="c5da1-157">O exemplo a seguir relata as instruções Transact-SQL que seriam executadas para atualizar um DAC denominado MyApplicaiton para o esquema definido em um arquivo MyApplicationVNext.dacpac.</span><span class="sxs-lookup"><span data-stu-id="c5da1-157">The following example reports the Transact-SQL statements that would be run to upgrading a DAC named MyApplicaiton to the schema defined in a MyApplicationVNext.dacpac file.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Load the DAC package file.  
$dacpacPath = "C:\MyDACs\MyApplicationVNext.dacpac"  
$fileStream = [System.IO.File]::Open($dacpacPath,[System.IO.FileMode]::OpenOrCreate)  
$dacType = [Microsoft.SqlServer.Management.Dac.DacType]::Load($fileStream)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the upgrade script and save to file.  
$dacstore.GetIncrementalUpgradeScript($dacName, $dacType) | Out-File -Filepath C:\DACScripts\MyApplicationUpgrade.sql  
  
## Close the filestream to the new DAC package.  
$fileStream.Close()  
```  
  
##  <a name="compare-dacs"></a><a name="CompareDACs"></a><span data-ttu-id="c5da1-158">Comparar DACs</span><span class="sxs-lookup"><span data-stu-id="c5da1-158">Compare DACs</span></span>  
 <span data-ttu-id="c5da1-159">Antes de atualizar um DAC, é recomendável revisar as diferenças nos objetos em nível de banco de dados e instância entre o DAC atual e o novo.</span><span class="sxs-lookup"><span data-stu-id="c5da1-159">Before upgrading a DAC, it is a good practice to review the differences in the database and instance-level objects between the current and new DACs.</span></span> <span data-ttu-id="c5da1-160">Se você não tiver uma cópia do pacote para o DAC atual, poderá extrair um pacote do banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="c5da1-160">If you do not have a copy of the package for the current DAC, you can extract a package from the current database.</span></span>  
  
 <span data-ttu-id="c5da1-161">Se você importar os pacotes de DAC para projetos de DAC no SQL Server Developer Tools, poderá usar a ferramenta de comparação de esquemas para analisar as diferenças entre o dois DACs.</span><span class="sxs-lookup"><span data-stu-id="c5da1-161">If you import both DAC packages into DAC projects in SQL Server Developer Tools, you can use the Schema Compare tool to analyze the differences between the two DACs.</span></span>  
  
 <span data-ttu-id="c5da1-162">Outra alternativa é desempacotar os DACs em pastas separadas.</span><span class="sxs-lookup"><span data-stu-id="c5da1-162">Alternatively, unpack the DACs into separate folders.</span></span> <span data-ttu-id="c5da1-163">Você pode usar uma ferramenta de diferenças, como o utilitário WinDiff, para analisar as diferenças.</span><span class="sxs-lookup"><span data-stu-id="c5da1-163">You can then use a difference tool, such as the WinDiff utility, to analyze the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5da1-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c5da1-164">See Also</span></span>  
 <span data-ttu-id="c5da1-165">[Aplicativos da Camada de Dados](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="c5da1-165">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="c5da1-166">[Implantar um aplicativo da camada de dados](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="c5da1-166">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="c5da1-167">Atualizar um aplicativo da camada de dados</span><span class="sxs-lookup"><span data-stu-id="c5da1-167">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
