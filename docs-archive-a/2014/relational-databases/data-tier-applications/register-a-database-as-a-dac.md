---
title: Registrar um banco de dados como um DAC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerdacwizard.registerdac.f1
- sql12.swb.registerdacwizard.summary.f1
- sql12.swb.registerdacwizard.introduction.f1
- sql12.swb.registerdacwizard.setproperties.f1
helpviewer_keywords:
- wizard [DAC], register
- How to [DAC], register
- register DAC
- data-tier application [SQL Server], register
ms.assetid: 08e52aa6-12f3-41dd-a793-14b99a083fd5
author: stevestein
ms.author: sstein
ms.openlocfilehash: c4e8061362d013dbfbd6cbaba47d0f2cb4d8e83b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583627"
---
# <a name="register-a-database-as-a-dac"></a><span data-ttu-id="2fbb0-102">Registrar um banco de dados como um DAC</span><span class="sxs-lookup"><span data-stu-id="2fbb0-102">Register a Database As a DAC</span></span>
  <span data-ttu-id="2fbb0-103">Use o **Assistente para registrar o aplicativo da camada de dados** ou um script do Windows PowerShell para criar uma definição de DAC (aplicativo da camada de dados) que descreva os objetos em um banco de dado existente e registre a definição de DAC no banco de dados do `msdb` sistema (**mestre** no [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="2fbb0-103">Use either the **Register Data-tier Application Wizard** or a Windows PowerShell script to build a data-tier application (DAC) definition that describes the objects in an existing database, and register the DAC definition in the `msdb` system database (**master** in [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]).</span></span>  
  
-   <span data-ttu-id="2fbb0-104">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="2fbb0-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="2fbb0-105">**Para atualizar um DAC, usando:**  [O Assistente de Aplicativo da Camada de Dados de Registro](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="2fbb0-105">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="2fbb0-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2fbb0-106">Before You Begin</span></span>  
 <span data-ttu-id="2fbb0-107">O processo de registro cria uma definição do DAC que define os objetos no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-107">The registration process creates a DAC definition that defines the objects in the database.</span></span> <span data-ttu-id="2fbb0-108">A combinação da definição do DAC e do banco de dados forma uma instância do DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-108">The combination of the DAC definition and the database form a DAC instance.</span></span> <span data-ttu-id="2fbb0-109">Se você registrar um banco de dados como um DAC em uma instância gerenciada do Mecanismo de Banco de Dados, o DAC registrado será incorporado ao Utilitário do SQL Server na próxima vez que o conjunto de coleta do utilitário for enviado da instância para o Ponto de Controle do Utilitário.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-109">If you register a database as a DAC on a managed instance of the Database Engine, the registered DAC will be incorporated into the SQL Server Utility the next time the utility collection set is sent from the instance to the Utility Control Point.</span></span> <span data-ttu-id="2fbb0-110">O DAC estará presente no nó **Aplicativos no Nível de Dados Implantados** do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Gerenciador do Utilitário** e é relatado na página de detalhes **Aplicativos no Nível de Dados Implantados**.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-110">The DAC will then be present in the **Deployed Data-tier Applications** node of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Utility Explorer** and reported in the **Deployed Data-tier Applications** details page.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="2fbb0-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="2fbb0-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2fbb0-112">O registro do DAC só pode ser executado em um banco de dados no [!INCLUDE[ssSDS](../../includes/sssds-md.md)]ou no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) ou posterior.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-112">DAC registration can only be performed on a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span> <span data-ttu-id="2fbb0-113">O registro do DAC não poderá ser executado se um DAC já estiver registrado para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-113">DAC registration cannot be performed if a DAC is already registered for the database.</span></span> <span data-ttu-id="2fbb0-114">Por exemplo, se o banco de dados foi criado através da implantação de um DAC, você não poderá executar o **Assistente para Registrar o Aplicativo da Camada de Dados**.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-114">For example, if the database was created by deploying a DAC, you cannot run the **Register Data-tier Application Wizard**.</span></span>  
  
 <span data-ttu-id="2fbb0-115">Você não poderá registrar um DAC se o banco de dados tiver objetos que não tenham suporte em um DAC ou usuários contidos.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-115">You cannot register a DAC if the database has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="2fbb0-116">Para obter mais informações sobre os tipos de objetos com suporte em um DAC, consulte [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="2fbb0-116">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2fbb0-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="2fbb0-117">Permissions</span></span>  
 <span data-ttu-id="2fbb0-118">O registro de um DAC em uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] requer, pelo menos, permissões VIEW DEFINITION de escopo de banco de dados e ALTER ANY LOGIN, permissões SELECT em **sys.sql_expression_dependencies**, e associação na função de servidor fixa **dbcreator** .</span><span class="sxs-lookup"><span data-stu-id="2fbb0-118">Registering a DAC in an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, SELECT permissions on **sys.sql_expression_dependencies**, and membership in the **dbcreator** fixed server role.</span></span> <span data-ttu-id="2fbb0-119">Os membros da função de servidor fixa **sysadmin** ou a conta interna do administrador do sistema do SQL Server denominada **sa** também podem registrar um DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-119">Members of the **sysadmin** fixed server role or the built-in SQL Server system administrator account named **sa** can also register a DAC.</span></span> <span data-ttu-id="2fbb0-120">O registro de um DAC que não contém logons no [!INCLUDE[ssSDS](../../includes/sssds-md.md)] exige associação nas funções **dbmanager** ou **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="2fbb0-120">Registering a DAC that does not contain logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **dbmanager** or **serveradmin** roles.</span></span> <span data-ttu-id="2fbb0-121">O registro de um DAC que contém logons no [!INCLUDE[ssSDS](../../includes/sssds-md.md)] exige associação nas funções **loginmanager** or **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="2fbb0-121">Registering a DAC that contains logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **loginmanager** or **serveradmin** roles.</span></span>  
  
##  <a name="using-the-register-data-tier-application-wizard"></a><a name="UsingRegisterDACWizard"></a> <span data-ttu-id="2fbb0-122">Usando o Assistente para Registrar o Aplicativo da Camada de Dados</span><span class="sxs-lookup"><span data-stu-id="2fbb0-122">Using the Register Data-tier Application Wizard</span></span>  
 <span data-ttu-id="2fbb0-123">**Para registrar um DAC usando um assistente**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-123">**To Register a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="2fbb0-124">No **Pesquisador de Objetos**, expanda o nó da instância que contém o banco de dados a ser registrado como um DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-124">In **Object Explorer**, expand the node for the instance containing the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="2fbb0-125">Expanda o nó **Bancos de Dados** .</span><span class="sxs-lookup"><span data-stu-id="2fbb0-125">Expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="2fbb0-126">Clique com o botão direito do mouse no banco de dados a ser registrado, aponte para **Tarefas** e selecione **Registrar como Aplicativo da Camada de Dados...**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-126">Right-click the database to be registered, point to **Tasks**, and then select **Register As Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="2fbb0-127">Conclua as etapas das caixas de diálogo do assistente:</span><span class="sxs-lookup"><span data-stu-id="2fbb0-127">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="2fbb0-128">Página de Introdução</span><span class="sxs-lookup"><span data-stu-id="2fbb0-128">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="2fbb0-129">Página Definir Propriedades</span><span class="sxs-lookup"><span data-stu-id="2fbb0-129">Set Properties Page</span></span>](#Set_properties)  
  
    3.  [<span data-ttu-id="2fbb0-130">Página Validação e Resumo</span><span class="sxs-lookup"><span data-stu-id="2fbb0-130">Validation and Summary Page</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="2fbb0-131">Página Registrar o DAC</span><span class="sxs-lookup"><span data-stu-id="2fbb0-131">Register DAC Page</span></span>](#Register)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="2fbb0-132">Página de Introdução</span><span class="sxs-lookup"><span data-stu-id="2fbb0-132">Introduction Page</span></span>  
 <span data-ttu-id="2fbb0-133">Essa página descreve as etapas do registro de um aplicativo da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-133">This page describes the steps for registering a data-tier application.</span></span>  
  
 <span data-ttu-id="2fbb0-134">**Não mostrar esta página novamente.**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-134">**Do not show this page again.**</span></span> <span data-ttu-id="2fbb0-135">- Clique na caixa de seleção para interromper a exibição da página no futuro.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-135">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="2fbb0-136">**Avançar >** - Continua na página **Definir Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-136">**Next >** - Proceeds to the **Set Properties** page.</span></span>  
  
 <span data-ttu-id="2fbb0-137">**Cancelar** - Finaliza o assistente sem registrar um DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-137">**Cancel** - Terminates the wizard without registering a DAC.</span></span>  
  
##  <a name="set-properties-page"></a><a name="Set_properties"></a> <span data-ttu-id="2fbb0-138">Página Definir Propriedades</span><span class="sxs-lookup"><span data-stu-id="2fbb0-138">Set Properties Page</span></span>  
 <span data-ttu-id="2fbb0-139">Use essa página para especificar propriedades no nível do DAC, como o nome e a versão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-139">Use this page to specify DAC-level properties such as the application name and version.</span></span>  
  
 <span data-ttu-id="2fbb0-140">**Nome do aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-140">**Application name.**</span></span> <span data-ttu-id="2fbb0-141">– Uma cadeia de caracteres que especifica o nome usado para identificar a definição do DAC, o campo foi populado com o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-141">- A string that specifies the name used to identify the DAC definition, the field is been populated with the database name.</span></span>  
  
 <span data-ttu-id="2fbb0-142">**Versão.**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-142">**Version.**</span></span> <span data-ttu-id="2fbb0-143">- Um valor numérico que identifica a versão do DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-143">- A numeric value that identifies the version of the DAC.</span></span> <span data-ttu-id="2fbb0-144">A versão do DAC é usada no Visual Studio para identificar a versão do DAC em que os desenvolvedores estão trabalhando.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-144">The DAC version is used in Visual Studio to identify the version of the DAC that developers are working on.</span></span> <span data-ttu-id="2fbb0-145">Ao implantar um DAC, a versão é armazenada no `msdb` banco de dados e, posteriormente, pode ser exibida no nó **aplicativos da camada de dados** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2fbb0-145">When deploying a DAC, the version is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="2fbb0-146">**Descrição.**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-146">**Description.**</span></span> <span data-ttu-id="2fbb0-147">- Opcional.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-147">- Optional.</span></span> <span data-ttu-id="2fbb0-148">Texto que explica a finalidade do DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-148">Text that explains the purpose of the DAC.</span></span> <span data-ttu-id="2fbb0-149">Ao implantar um DAC, a descrição é armazenada no `msdb` banco de dados e, posteriormente, pode ser exibida no nó **aplicativos da camada data** no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2fbb0-149">When deploying a DAC, the description is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="2fbb0-150">\*\* \< Anterior\*\* – retorna para a página **introdução** .</span><span class="sxs-lookup"><span data-stu-id="2fbb0-150">**\< Previous** - Returns you to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="2fbb0-151">**Avançar >** - Verifica se um DAC pode ser compilado por meio dos objetos do banco de dados e exibe os resultados na página de **Validação e Resumo**.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-151">**Next >** - Verifies that a DAC can be built from the objects in the database, and displays the results in the **Validation and Summary** page.</span></span>  
  
 <span data-ttu-id="2fbb0-152">**Cancelar** - Finaliza o assistente sem registrar o DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-152">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="validation-and-summary-page"></a><a name="Summary"></a> <span data-ttu-id="2fbb0-153">Página Validação e Resumo</span><span class="sxs-lookup"><span data-stu-id="2fbb0-153">Validation and Summary Page</span></span>  
 <span data-ttu-id="2fbb0-154">Use essa página para revisar as ações do assistente ao registrar o DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-154">Use this page to review the actions the wizard will take when registering the DAC.</span></span> <span data-ttu-id="2fbb0-155">A página faz transição por três estados ao verificar se um DAC pode ser compilado a partir dos objetos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-155">The page transitions through three states as it verifies that a DAC can be built from the objects in the database.</span></span>  
  
### <a name="retrieving-objects"></a><span data-ttu-id="2fbb0-156">Recuperando objetos</span><span class="sxs-lookup"><span data-stu-id="2fbb0-156">Retrieving Objects</span></span>  
 <span data-ttu-id="2fbb0-157">**Recuperando os objetos de banco de dados e de servidor.**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-157">**Retrieving database and server objects.**</span></span> <span data-ttu-id="2fbb0-158">- Exibe uma barra de progresso enquanto o assistente recupera todos os objetos necessários do banco de dados e da instância do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-158">- Displays a progress bar as the wizard retrieves all of the required objects from the database and the instance of the Database Engine.</span></span>  
  
 <span data-ttu-id="2fbb0-159">\*\* \< Anterior\*\* – retorna para a página **definir propriedades** para alterar suas entradas.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-159">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="2fbb0-160">**Avançar >** - Registra o DAC e exibe os resultados na página **Registrar o DAC**.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-160">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="2fbb0-161">**Cancelar** - Finaliza o assistente sem registrar o DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-161">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="validating-objects"></a><span data-ttu-id="2fbb0-162">Validando objetos</span><span class="sxs-lookup"><span data-stu-id="2fbb0-162">Validating Objects</span></span>  
 <span data-ttu-id="2fbb0-163">**Verificando** _SchemaName_ **.**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-163">**Checking**  _SchemaName_ **.**</span></span> <span data-ttu-id="2fbb0-164">_ObjectName_ **.**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-164">_ObjectName_ **.**</span></span> <span data-ttu-id="2fbb0-165">- Exibe uma barra de progresso enquanto o assistente verifica as dependências dos objetos recuperados e se todos eles são objetos válidos para um DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-165">- Displays a progress bar as the wizard verifies the dependencies of the retrieved objects, and verifies that they are all valid objects for a DAC.</span></span> <span data-ttu-id="2fbb0-166">_SchemaName_ **.** _ObjectName_ identifica qual objeto está sendo verificado no momento.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-166">_SchemaName_**.**_ObjectName_ identify which object is currently being verified.</span></span>  
  
 <span data-ttu-id="2fbb0-167">\*\* \< Anterior\*\* – retorna para a página **definir propriedades** para alterar suas entradas.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-167">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="2fbb0-168">**Avançar >** - Registra o DAC e exibe os resultados na página **Registrar o DAC**.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-168">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="2fbb0-169">**Cancelar** - Finaliza o assistente sem registrar o DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-169">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="summary"></a><span data-ttu-id="2fbb0-170">Resumo</span><span class="sxs-lookup"><span data-stu-id="2fbb0-170">Summary</span></span>  
 <span data-ttu-id="2fbb0-171">**A configuração a seguir será usada para registrar o DAC.**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-171">**The following setting will be used to register your DAC.**</span></span> <span data-ttu-id="2fbb0-172">- Exibe um relatório das propriedades e objetos que serão incluídos no DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-172">- Displays a report of the properties and objects that will be included in the DAC.</span></span>  
  
 <span data-ttu-id="2fbb0-173">**Salvar Relatório** - Selecione esse botão para salvar uma cópia do relatório de validação em um arquivo HTML.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-173">**Save Report** - Select this button to save a copy of the validation report to an HTML file.</span></span> <span data-ttu-id="2fbb0-174">A pasta padrão é **SQL Server Gerenciamento Studio\DAC Packages** na pasta Documentos da conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-174">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span>  
  
 <span data-ttu-id="2fbb0-175">\*\* \< Anterior\*\* – retorna para a página **definir propriedades** para alterar suas entradas.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-175">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="2fbb0-176">**Avançar >** - Registra o DAC e exibe os resultados na página **Registrar o DAC**.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-176">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="2fbb0-177">**Cancelar** - Finaliza o assistente sem registrar o DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-177">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="register-dac-page"></a><a name="Register"></a> <span data-ttu-id="2fbb0-178">Página Registrar o DAC</span><span class="sxs-lookup"><span data-stu-id="2fbb0-178">Register DAC Page</span></span>  
 <span data-ttu-id="2fbb0-179">Essa página relata o êxito ou a falha da operação de registro.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-179">This page reports the success or failure of the registration.</span></span>  
  
 <span data-ttu-id="2fbb0-180">**Registrando o DAC** - Relata o êxito ou a falha de cada ação realizada para registrar o DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-180">**Registering the DAC** - Reports the success or failure of each action taken to register the DAC.</span></span> <span data-ttu-id="2fbb0-181">Analise as informações para determinar o êxito ou falha de cada ação.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-181">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="2fbb0-182">Todas as ações que encontrarem um erro terão um link na coluna **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="2fbb0-182">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="2fbb0-183">Selecione o link para exibir um relatório do erro para aquela ação.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-183">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="2fbb0-184">**Salvar Relatório** - Selecione esse botão para salvar o relatório de registro em um arquivo HTML.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-184">**Save Report** - Select this button to save the registration report to an HTML file.</span></span> <span data-ttu-id="2fbb0-185">O arquivo relata o status de cada ação, inclusive todos os erros gerados por qualquer uma das ações.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-185">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="2fbb0-186">A pasta padrão é **SQL Server Gerenciamento Studio\DAC Packages** na pasta Documentos da conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-186">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span> <span data-ttu-id="2fbb0-187">O nome de arquivo está no formato \<DACPackageName>_RegisterDACReport_yyyymmdd.html, em que \<*DACPackageName*> é o nome do pacote que está sendo implantado, *yyyy* = ano atual, *mm* = mês atual e *dd* = dia atual.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-187">The file name is in the format \<DACPackageName>_RegisterDACReport_yyyymmdd.html, where \<*DACPackageName*> is the name of the package being deployed, *yyyy* = the current year, *mm* = the current month, and *dd* = the current day.</span></span>  
  
 <span data-ttu-id="2fbb0-188">**Concluir** – Encerra o assistente.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-188">**Finish** - Terminates the wizard.</span></span>  
  
##  <a name="register-a-dac-using-powershell"></a><a name="RegisterDACPowerShell"></a> <span data-ttu-id="2fbb0-189">Registrar um DAC usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fbb0-189">Register a DAC Using PowerShell</span></span>  
 <span data-ttu-id="2fbb0-190">**Para registrar um banco de dados como um DAC usando o método Register() em um script de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2fbb0-190">**To register a database as a DAC using the Register() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="2fbb0-191">Crie um objeto de servidor SMO e defina-o como a instância que contém o banco de dados a ser registrado como um DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-191">Create a SMO Server object and set it to the instance that contains the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="2fbb0-192">Adicione uma variável que especifique o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-192">Add a variable that specifies the name of the database.</span></span>  
  
3.  <span data-ttu-id="2fbb0-193">Especifique os metadados do DAC, como o nome, a versão e a descrição do DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-193">Specify the metadata for the DAC, such as the DAC name, version, and description.</span></span>  
  
4.  <span data-ttu-id="2fbb0-194">Execute o método Register com as informações especificadas acima.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-194">Run the Register method with the information specified above.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="2fbb0-195">Exemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="2fbb0-195">Example (PowerShell)</span></span>  
 <span data-ttu-id="2fbb0-196">O exemplo a seguir registra um banco de dados chamado MyDB como um DAC.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-196">The following example registers a database named MyDB as a DAC.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Specify the database to register as a DAC.  
$dbname = "MyDB"  
  
## Specify the DAC metadata.  
$applicationname = "MyApplication"  
$version = "1.0.0.0"  
$description = "This DAC defines the database used by my application."  
  
## Register the DAC.  
$registerunit = New-Object Microsoft.SqlServer.Management.Dac.DacExtractionUnit($srv, $dbname, $applicationname, $version)  
$registerunit.Description = $description  
$registerunit.Register()  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fbb0-197">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2fbb0-197">See Also</span></span>  
 [<span data-ttu-id="2fbb0-198">Aplicativos da camada de dados</span><span class="sxs-lookup"><span data-stu-id="2fbb0-198">Data-tier Applications</span></span>](data-tier-applications.md)  
