---
title: Atualizar um aplicativo da camada de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.upgradedacwizard.reviewpolicy.f1
- sql12.swb.upgradedacwizard.selectoptions.f1
- sql12.swb.upgradedacwizard.selectpackage.f1
- sql12.swb.upgradedacwizard.reviewplan.f1
- sql12.swb.upgradedacwizard.checkdrift.f1
- sql12.swb.upgradedacwizard.summary.f1
- sql12.swb.upgradedacwizard.upgradedac.f1
- sql12.swb.upgradedacwizard.introduction.f1
helpviewer_keywords:
- upgrade DAC
- data-tier application [SQL Server], upgrade
- wizard [DAC], upgrade
- How to [DAC], upgrade
ms.assetid: c117df94-f02b-403f-9383-ec5b3ac3763c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0e597d02af28a16539b50ff76503059278ef7a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583113"
---
# <a name="upgrade-a-data-tier-application"></a><span data-ttu-id="82a8a-102">Atualizar um aplicativo da camada de dados</span><span class="sxs-lookup"><span data-stu-id="82a8a-102">Upgrade a Data-tier Application</span></span>
  <span data-ttu-id="82a8a-103">Use o Assistente para Atualizar Aplicativo da Camada de Dados ou um script do Windows PowerShell para alterar o esquema e as propriedades de um DAC (aplicativo da camada de dados) implantado no momento para coincidir com o esquema e as propriedades definidos em uma nova versão do DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-103">Use either the Upgrade Data-tier Application Wizard or a Windows PowerShell script to change the schema and properties of a currently deployed data-tier application (DAC) to match the schema and properties defined in a new version of the DAC.</span></span>  
  
-   <span data-ttu-id="82a8a-104">**Antes de começar:**  [Escolhendo Opções de Atualização de DAC](#ChoseDACUpgOptions), [Limitações e Restrições](#LimitationsRestrictions), [Pré-requisitos](#Prerequisites), [Segurança](#Security), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="82a8a-104">**Before you begin:**  [Choosing DAC Upgrade Options](#ChoseDACUpgOptions), [Limitations and Restrictions](#LimitationsRestrictions), [Prerequisites](#Prerequisites), [Security](#Security), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="82a8a-105">**Para atualizar um DAC, usando:**  [O Assistente para Atualizar Aplicativo da Camada de Dados](#UsingDACUpgradeWizard), [PowerShell](#UpgradeDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="82a8a-105">**To upgrade a DAC, using:**  [The Upgrade Data-tier Application Wizard](#UsingDACUpgradeWizard), [PowerShell](#UpgradeDACPowerShell)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="82a8a-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="82a8a-106">Before You Begin</span></span>  
 <span data-ttu-id="82a8a-107">Uma atualização de DAC é um processo no local que altera o esquema do banco de dados existente para corresponder ao esquema definido em uma nova versão do DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-107">A DAC upgrade is an in-place process that alters the schema of the existing database to match the schema defined in a new version of the DAC.</span></span> <span data-ttu-id="82a8a-108">A nova versão do DAC é fornecida em um arquivo de pacote DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-108">The new version of the DAC is supplied in a DAC package file.</span></span> <span data-ttu-id="82a8a-109">Para obter mais informações sobre como criar um pacote de DAC, veja [Aplicativos da camada de dados](data-tier-applications.md).</span><span class="sxs-lookup"><span data-stu-id="82a8a-109">For more information about creating a DAC package, see [Data-tier Applications](data-tier-applications.md).</span></span>  
  
###  <a name="choosing-dac-upgrade-options"></a><a name="ChoseDACUpgOptions"></a> <span data-ttu-id="82a8a-110">Escolhendo Opções de Atualização de DAC</span><span class="sxs-lookup"><span data-stu-id="82a8a-110">Choosing DAC Upgrade Options</span></span>  
 <span data-ttu-id="82a8a-111">Há quatro opções de atualização para uma atualização no local:</span><span class="sxs-lookup"><span data-stu-id="82a8a-111">There are four upgrade options for an in-place upgrade:</span></span>  
  
-   <span data-ttu-id="82a8a-112">**Ignorar perda de dados** -se `True` , a atualização continuará mesmo se algumas das operações resultarem na perda de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-112">**Ignore Data Loss** - If `True`, the upgrade will proceed even if some of the operations result in the loss of data.</span></span> <span data-ttu-id="82a8a-113">Se `False`, estas operações finalizarão a atualização.</span><span class="sxs-lookup"><span data-stu-id="82a8a-113">If `False`, these operations will terminate the upgrade.</span></span> <span data-ttu-id="82a8a-114">Por exemplo, se uma tabela no banco de dados atual não estiver presente no esquema do novo DAC, a tabela será removida se `True` for especificado.</span><span class="sxs-lookup"><span data-stu-id="82a8a-114">For example, if a table in the current database is not present in the schema of the new DAC, the table will be dropped if `True` is specified.</span></span> <span data-ttu-id="82a8a-115">A configuração padrão é `True`.</span><span class="sxs-lookup"><span data-stu-id="82a8a-115">The default setting is `True`.</span></span>  
  
-   <span data-ttu-id="82a8a-116">**Bloquear em alterações** -se `True` , a atualização será encerrada se o esquema de banco de dados for diferente daquele definido no DAC anterior.</span><span class="sxs-lookup"><span data-stu-id="82a8a-116">**Block on Changes** - If `True`, the upgrade is terminated if the database schema is different than that defined in the previous DAC.</span></span> <span data-ttu-id="82a8a-117">Se `False`, a atualização continuará mesmo que sejam detectadas alterações.</span><span class="sxs-lookup"><span data-stu-id="82a8a-117">If `False`, the upgrade continues even if changes are detected.</span></span> <span data-ttu-id="82a8a-118">A configuração padrão é `False`.</span><span class="sxs-lookup"><span data-stu-id="82a8a-118">The default setting is `False`.</span></span>  
  
-   <span data-ttu-id="82a8a-119">**Reversão em** caso de falha-se `True` , a atualização é colocada em uma transação e, se forem encontrados erros, será feita uma tentativa de reversão.</span><span class="sxs-lookup"><span data-stu-id="82a8a-119">**Rollback on Failure** - If `True`, the upgrade is enclosed in a transaction, and if errors are encountered a rollback will be attempted.</span></span> <span data-ttu-id="82a8a-120">Se `False`, todas as alterações serão confirmadas à medida que ocorrerem. Se houver erros, talvez você precise restaurar um backup anterior do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-120">If `False`, all changes are committed as they are made and if errors occur you may have to restore a previous backup of the database.</span></span> <span data-ttu-id="82a8a-121">A configuração padrão é `False`.</span><span class="sxs-lookup"><span data-stu-id="82a8a-121">The default setting is `False`.</span></span>  
  
-   <span data-ttu-id="82a8a-122">**Ignorar validação de política** -se `True` a política de seleção de servidor DAC não for avaliada.</span><span class="sxs-lookup"><span data-stu-id="82a8a-122">**Skip Policy Validation** - If `True`, the DAC server selection policy is not evaluated.</span></span> <span data-ttu-id="82a8a-123">Se `False`, a política será avaliada e a atualização finalizará se houver um erro de validação.</span><span class="sxs-lookup"><span data-stu-id="82a8a-123">If `False`, the policy is evaluated and the upgrade terminates if there is a validation error.</span></span> <span data-ttu-id="82a8a-124">A configuração padrão é `False`.</span><span class="sxs-lookup"><span data-stu-id="82a8a-124">The default setting is `False`.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="82a8a-125">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="82a8a-125">Limitations and Restrictions</span></span>  
 <span data-ttu-id="82a8a-126">Só podem ser executados uprades de DAC em [!INCLUDE[ssSDS](../../includes/sssds-md.md)]ou [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) ou posterior.</span><span class="sxs-lookup"><span data-stu-id="82a8a-126">DAC uprades can only be performed in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="82a8a-127">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="82a8a-127">Prerequisites</span></span>  
 <span data-ttu-id="82a8a-128">Convém fazer um backup completo do banco de dados antes de iniciar a atualização.</span><span class="sxs-lookup"><span data-stu-id="82a8a-128">It is prudent to take a full database backup before starting the upgrade.</span></span> <span data-ttu-id="82a8a-129">Se uma atualização encontrar um erro e não puder reverter todas as suas alterações, talvez seja preciso restaurar o backup.</span><span class="sxs-lookup"><span data-stu-id="82a8a-129">If an upgrade encounters an error and cannot roll back all of its changes, you may need to restore the backup.</span></span>  
  
 <span data-ttu-id="82a8a-130">Antes de iniciar a atualização, há várias ações a serem adotadas para validar o pacote de DAC e as ações de atualização.</span><span class="sxs-lookup"><span data-stu-id="82a8a-130">Before starting the upgrade, there are several actions that you should take to validate the DAC package and the upgrade actions.</span></span> <span data-ttu-id="82a8a-131">Para obter mais informações sobre como executar essas verificações, consulte [Validate a DAC Package](validate-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="82a8a-131">For more information about how to perform these checks, see [Validate a DAC Package](validate-a-dac-package.md).</span></span>  
  
-   <span data-ttu-id="82a8a-132">É recomendável não atualizar usando um pacote de DAC de origens desconhecidas ou não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="82a8a-132">We recommend that you do not upgrade by using a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="82a8a-133">Esses pacotes podem conter código mal-intencionado que possivelmente executarão códigos Transact-SQL inesperados ou provocarão erros ao modificar o esquema.</span><span class="sxs-lookup"><span data-stu-id="82a8a-133">Such packages could contain malicious code that might execute unintended Transact-SQL code or cause errors by modifying the schema.</span></span> <span data-ttu-id="82a8a-134">Antes de usar um pacote de uma origem desconhecida ou não confiável, desempacote o DAC e examine o código, como procedimentos armazenados ou outro código definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="82a8a-134">Before you use a package from an unknown or untrusted source, unpack the DAC and examine the code, such as stored procedures or other user-defined code.</span></span>  
  
-   <span data-ttu-id="82a8a-135">Se ocorreram alterações no banco de dados atual após a implantação da última versão do DAC, algumas dessas alterações talvez impeçam a conclusão bem-sucedida da atualização, ou talvez elas sejam removidas pela atualização.</span><span class="sxs-lookup"><span data-stu-id="82a8a-135">If changes have been made to the current database after the last version of the DAC was deployed, some of the changes may prevent the successful completion of the upgrade, or be removed by the upgrade.</span></span> <span data-ttu-id="82a8a-136">Você deve primeiro gerar e examinar um relatório de revisão que inclua as alterações feitas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-136">You should first generate and review a report of any such changes made in the database.</span></span>  
  
-   <span data-ttu-id="82a8a-137">É aconselhável gerar uma lista das alterações a serem feitas pela atualização no esquema, além de examinar essa lista para verificar se há problemas.</span><span class="sxs-lookup"><span data-stu-id="82a8a-137">It is prudent to generate a list of the schema changes the upgrade will perform, and review the list for any problems.</span></span>  
  
 <span data-ttu-id="82a8a-138">O nome do aplicativo no pacote de DAC deve corresponder ao nome do aplicativo do DAC implantado no momento.</span><span class="sxs-lookup"><span data-stu-id="82a8a-138">The application name in the DAC package must match the application name of the currently deployed DAC.</span></span> <span data-ttu-id="82a8a-139">Por exemplo, se o DAC atual tiver um nome de aplicativo **GeneralLedger**, somente será possível atualizar usando um pacote de DAC que também tenha um nome de aplicativo **GeneralLedger**.</span><span class="sxs-lookup"><span data-stu-id="82a8a-139">For example, if the current DAC has an application name of **GeneralLedger**, you can only upgrade by using a DAC package that also has an application name of **GeneralLedger**.</span></span>  
  
 <span data-ttu-id="82a8a-140">Verifique se há bastante espaço de log de transação disponível para registrar todas das modificações.</span><span class="sxs-lookup"><span data-stu-id="82a8a-140">Ensure there is enough transaction log space available to log all of the modifications.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="82a8a-141">Segurança</span><span class="sxs-lookup"><span data-stu-id="82a8a-141">Security</span></span>  
 <span data-ttu-id="82a8a-142">Para melhorar a segurança, os logons de autenticação do SQL Server são armazenados em um pacote do DAC sem senha.</span><span class="sxs-lookup"><span data-stu-id="82a8a-142">To improve security, SQL Server Authentication logins are stored in a DAC package without a password.</span></span> <span data-ttu-id="82a8a-143">Quando o pacote é implantado ou atualizado, o logon é criado como um logon desabilitado com uma senha gerada.</span><span class="sxs-lookup"><span data-stu-id="82a8a-143">When the package is deployed or upgraded, the login is created as a disabled login with a generated password.</span></span> <span data-ttu-id="82a8a-144">Para habilitar os logons, faça logon usando um logon que tenha a permissão de ALTER ANY LOGIN e use ALTER LOGIN para habilitar o logon e atribuir uma nova senha que possa ser comunicada ao usuário.</span><span class="sxs-lookup"><span data-stu-id="82a8a-144">To enable the logins, log in using a login that has ALTER ANY LOGIN permission and use ALTER LOGIN to enable the login and assign a new password that can be communicated to the user.</span></span> <span data-ttu-id="82a8a-145">Isso não é necessário para logons de Autenticação do Windows porque suas senhas não são gerenciadas pelo SQL Server.</span><span class="sxs-lookup"><span data-stu-id="82a8a-145">This is not needed for Windows Authentication logins because their passwords are not managed by SQL Server.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="82a8a-146">Permissões</span><span class="sxs-lookup"><span data-stu-id="82a8a-146">Permissions</span></span>  
 <span data-ttu-id="82a8a-147">Um DAC pode ser atualizado somente pelos membros das funções de servidor fixas **sysadmin** ou **serveradmin** ou por logons que estejam na função de servidor fixa **dbcreator** e tenham permissões ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="82a8a-147">A DAC can only be upgraded by members of the **sysadmin** or **serveradmin** fixed server roles, or by logins that are in the **dbcreator** fixed server role and have ALTER ANY LOGIN permissions.</span></span> <span data-ttu-id="82a8a-148">O logon deve ser o proprietário do banco de dados existente.</span><span class="sxs-lookup"><span data-stu-id="82a8a-148">The login must be the owner of the existing database.</span></span> <span data-ttu-id="82a8a-149">A conta interna do administrador de sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] chamada **sa** também pode atualizar um DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-149">The built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator account named **sa** can also upgrade a DAC.</span></span>  
  
##  <a name="using-the-upgrade-data-tier-application-wizard"></a><a name="UsingDACUpgradeWizard"></a> <span data-ttu-id="82a8a-150">Usando o Assistente para Atualizar Aplicativo da Camada de Dados</span><span class="sxs-lookup"><span data-stu-id="82a8a-150">Using the Upgrade Data-tier Application Wizard</span></span>  
 <span data-ttu-id="82a8a-151">**Para atualizar um DAC usando um assistente**</span><span class="sxs-lookup"><span data-stu-id="82a8a-151">**To Upgrade a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="82a8a-152">No **Pesquisador de Objetos**, expanda o nó da instância que contém o DAC a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="82a8a-152">In **Object Explorer**, expand the node for the instance containing the DAC to be upgraded.</span></span>  
  
2.  <span data-ttu-id="82a8a-153">Expanda os nós **Gerenciamento** e **Aplicativos da Camada de Dados** .</span><span class="sxs-lookup"><span data-stu-id="82a8a-153">Expand the **Management** node, and then expand the **Data-tier Applications** node.</span></span>  
  
3.  <span data-ttu-id="82a8a-154">Clique com o botão direito do mouse no nó do DAC a ser atualizado e selecione **Atualizar Aplicativo da Camada de Dados...**</span><span class="sxs-lookup"><span data-stu-id="82a8a-154">Right-click the node for the DAC to be upgraded, and then select **Upgrade Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="82a8a-155">Conclua as etapas das caixas de diálogo do assistente:</span><span class="sxs-lookup"><span data-stu-id="82a8a-155">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="82a8a-156">Página de Introdução</span><span class="sxs-lookup"><span data-stu-id="82a8a-156">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="82a8a-157">Página Selecionar Pacote</span><span class="sxs-lookup"><span data-stu-id="82a8a-157">Select Package Page</span></span>](#Select_dac_package)  
  
    3.  [<span data-ttu-id="82a8a-158">Página Analisar Política</span><span class="sxs-lookup"><span data-stu-id="82a8a-158">Review Policy Page</span></span>](#Review_policy)  
  
    4.  [<span data-ttu-id="82a8a-159">Página Detectar Alterações</span><span class="sxs-lookup"><span data-stu-id="82a8a-159">Detect Change Page</span></span>](#Detect_change)  
  
    5.  [<span data-ttu-id="82a8a-160">Analisar um plano de atualização</span><span class="sxs-lookup"><span data-stu-id="82a8a-160">Review the Upgrade Plan</span></span>](#ReviewUpgPlan)  
  
    6.  [<span data-ttu-id="82a8a-161">Página de Resumo</span><span class="sxs-lookup"><span data-stu-id="82a8a-161">Summary Page</span></span>](#Summary)  
  
    7.  [<span data-ttu-id="82a8a-162">Página Atualizar DAC</span><span class="sxs-lookup"><span data-stu-id="82a8a-162">Upgrade DAC Page</span></span>](#Upgrade)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="82a8a-163">Página de Introdução</span><span class="sxs-lookup"><span data-stu-id="82a8a-163">Introduction Page</span></span>  
 <span data-ttu-id="82a8a-164">Esta página descreve as etapas para atualizar um aplicativo da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-164">This page describes the steps for upgrading a data-tier application.</span></span>  
  
 <span data-ttu-id="82a8a-165">**Não mostrar esta página novamente.**</span><span class="sxs-lookup"><span data-stu-id="82a8a-165">**Do not show this page again.**</span></span> <span data-ttu-id="82a8a-166">- Clique na caixa de seleção para interromper a exibição da página no futuro.</span><span class="sxs-lookup"><span data-stu-id="82a8a-166">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="82a8a-167">**Avançar >** – Segue para a página **Selecionar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="82a8a-167">**Next >** - Proceeds to the **Select Package** page.</span></span>  
  
 <span data-ttu-id="82a8a-168">**Cancelar** – Encerra o assistente sem atualizar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-168">**Cancel** - Terminates the wizard without upgrading the DAC.</span></span>  
  
##  <a name="select-package-page"></a><a name="Select_dac_package"></a> <span data-ttu-id="82a8a-169">Página Selecionar Pacote</span><span class="sxs-lookup"><span data-stu-id="82a8a-169">Select Package Page</span></span>  
 <span data-ttu-id="82a8a-170">Use esta página para especificar o pacote de DAC que contém a nova versão do aplicativo da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-170">Use this page to specify the DAC package that contains the new version of the data-tier application.</span></span> <span data-ttu-id="82a8a-171">A página faz a transição por dois estados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-171">The page transitions through two states.</span></span>  
  
### <a name="select-the-dac-package"></a><span data-ttu-id="82a8a-172">Selecionar o pacote de DAC</span><span class="sxs-lookup"><span data-stu-id="82a8a-172">Select the DAC Package</span></span>  
 <span data-ttu-id="82a8a-173">Use o estado inicial da página para escolher o pacote de DAC a ser implantado.</span><span class="sxs-lookup"><span data-stu-id="82a8a-173">Use the initial state of the page to choose the DAC package to deploy.</span></span> <span data-ttu-id="82a8a-174">O pacote de DAC deve ser um arquivo de pacote de DAC válido e deve ter uma extensão .dacpac.</span><span class="sxs-lookup"><span data-stu-id="82a8a-174">The DAC package must be a valid DAC package file and must have a .dacpac extension.</span></span> <span data-ttu-id="82a8a-175">O nome do aplicativo de DAC no pacote de DAC deve ser igual ao nome do aplicativo do DAC atual.</span><span class="sxs-lookup"><span data-stu-id="82a8a-175">The DAC application name in the DAC package must be the same as the application name of the current DAC.</span></span>  
  
 <span data-ttu-id="82a8a-176">**Pacote de DAC** – Especifique o caminho e o nome de arquivo do pacote de DAC que contém a nova versão do aplicativo da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-176">**DAC Package** - Specify the path and file name of the DAC package that contains the new version of the data-tier application.</span></span> <span data-ttu-id="82a8a-177">Você pode selecionar o botão **Procurar** no lado direito da caixa para procurar o local do pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-177">You can select the **Browse** button at the right of the box to browse to the location of the DAC package.</span></span>  
  
 <span data-ttu-id="82a8a-178">**Nome do Aplicativo** – Uma caixa somente leitura que exibe o nome do aplicativo de DAC atribuído quando o DAC foi criado ou extraído de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-178">**Application Name** - A read-only box that displays the DAC application name assigned when the DAC was authored or extracted from a database.</span></span>  
  
 <span data-ttu-id="82a8a-179">**Versão** – Uma caixa somente leitura que exibe a versão atribuída quando o DAC foi criado ou extraído de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-179">**Version** - A read-only box that displays the version assigned when the DAC was authored or extracted from a database.</span></span>  
  
 <span data-ttu-id="82a8a-180">**Descrição** – Uma caixa somente leitura que exibe a descrição escrita quando o DAC foi criado ou extraído de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-180">**Description** - A read-only box that displays the description written when the DAC was authored or extracted from a database.</span></span>  
  
 <span data-ttu-id="82a8a-181">\*\* \< Anterior\*\* – retorna à página **introdução** .</span><span class="sxs-lookup"><span data-stu-id="82a8a-181">**\< Previous** - Returns to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="82a8a-182">**Avançar >** – Exibe uma barra de progresso enquanto o assistente confirma se o arquivo selecionado é um pacote de DAC válido.</span><span class="sxs-lookup"><span data-stu-id="82a8a-182">**Next >** - Displays a progress bar as the wizard confirms that the selected file is a valid DAC package.</span></span>  
  
 <span data-ttu-id="82a8a-183">**Cancelar** – Encerra o assistente sem atualizar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-183">**Cancel** - Terminates the wizard without upgrading the DAC.</span></span>  
  
### <a name="validating-the-dac-package"></a><span data-ttu-id="82a8a-184">Validando o pacote de DAC</span><span class="sxs-lookup"><span data-stu-id="82a8a-184">Validating the DAC Package</span></span>  
 <span data-ttu-id="82a8a-185">Exibe uma barra de progresso enquanto o assistente confirma se o arquivo selecionado é um pacote de DAC válido.</span><span class="sxs-lookup"><span data-stu-id="82a8a-185">Displays a progress bar as the wizard confirms that the selected file is a valid DAC package.</span></span> <span data-ttu-id="82a8a-186">Se o pacote de DAC for validado, o assistente seguirá para a página **Examinar Política** .</span><span class="sxs-lookup"><span data-stu-id="82a8a-186">If the DAC package is validated, the wizard proceeds to the **Review Policy** page.</span></span> <span data-ttu-id="82a8a-187">Se o arquivo não for um pacote de DAC válido, o assistente permanecerá na página **Selecionar Pacote de DAC** .</span><span class="sxs-lookup"><span data-stu-id="82a8a-187">If the file is not a valid DAC package, the wizard remains on the **Select DAC Package** page.</span></span> <span data-ttu-id="82a8a-188">Selecione outro pacote de DAC válido ou cancele o assistente e gere um novo pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-188">Either select another valid DAC package or cancel the wizard and generate a new DAC package.</span></span>  
  
 <span data-ttu-id="82a8a-189">**Validando o conteúdo do DAC** – A barra de progresso que relata o status atual do processo de validação.</span><span class="sxs-lookup"><span data-stu-id="82a8a-189">**Validating the contents of the DAC** - The progress bar that reports the current status of the validation process.</span></span>  
  
 <span data-ttu-id="82a8a-190">\*\* \< Anterior\*\* – retorna ao estado inicial da página **selecionar pacote** .</span><span class="sxs-lookup"><span data-stu-id="82a8a-190">**\< Previous** - Returns to the initial state of the **Select Package** page.</span></span>  
  
 <span data-ttu-id="82a8a-191">**Avançar >** – Segue para a versão final da página **Selecionar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="82a8a-191">**Next >** - Proceeds to the final version of the **Select Package** page.</span></span>  
  
 <span data-ttu-id="82a8a-192">**Cancelar** – Encerra o assistente sem implantar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-192">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="review-policy-page"></a><a name="Review_policy"></a> <span data-ttu-id="82a8a-193">Página Analisar Política</span><span class="sxs-lookup"><span data-stu-id="82a8a-193">Review Policy Page</span></span>  
 <span data-ttu-id="82a8a-194">Use esta página para examinar os resultados da avaliação da política de seleção de servidor de DAC, se o DAC tiver uma política.</span><span class="sxs-lookup"><span data-stu-id="82a8a-194">Use this page to review the results of evaluating the DAC server selection policy, if the DAC has a policy.</span></span> <span data-ttu-id="82a8a-195">A política de seleção de servidor de DAC é opcional e atribuída a um DAC criado no Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="82a8a-195">The DAC server selection policy is optional, and is assigned to a DAC authored in Microsoft Visual Studio.</span></span> <span data-ttu-id="82a8a-196">A política usa as facetas de política de seleção de servidor para especificar as condições que uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] deve atender para hospedar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-196">The policy uses the server selection policy facets to specify conditions an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] should meet to host the DAC.</span></span>  
  
 <span data-ttu-id="82a8a-197">**Resultados da avaliação das condições da política** – Um relatório somente leitura que mostra se as avaliações das condições na política de seleção de servidor de DAC foram bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="82a8a-197">**Evaluation results of policy conditions** - A read-only report showing whether the evaluations of the conditions in the DAC server selection policy succeeded.</span></span> <span data-ttu-id="82a8a-198">Os resultados da avaliação de cada condição são relatados em uma linha separada.</span><span class="sxs-lookup"><span data-stu-id="82a8a-198">The results of evaluating each condition are reported on a separate line.</span></span>  
  
 <span data-ttu-id="82a8a-199">**Ignorar violações de política** – Use esta caixa de seleção para continuar com a atualização se uma ou mais condições de política falharem.</span><span class="sxs-lookup"><span data-stu-id="82a8a-199">**Ignore policy violations** - Use this check box to proceed with the upgrade if one or more of the policy conditions failed.</span></span> <span data-ttu-id="82a8a-200">Somente selecione essa opção se você tiver certeza de que todas as condições que falharam não impedirão o funcionamento bem-sucedido do DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-200">Only select this option if you are sure that all of the conditions which failed will not prevent the successful operation of the DAC.</span></span>  
  
 <span data-ttu-id="82a8a-201">\*\* \< Anterior\*\* – retorna para a página **selecionar pacote** .</span><span class="sxs-lookup"><span data-stu-id="82a8a-201">**\< Previous** - Returns to the **Select Package** page.</span></span>  
  
 <span data-ttu-id="82a8a-202">**Avançar >** – Segue para a página **Detectar Alteração**.</span><span class="sxs-lookup"><span data-stu-id="82a8a-202">**Next >** - Proceeds to the **Detect Change** page.</span></span>  
  
 <span data-ttu-id="82a8a-203">**Cancelar** – Encerra o assistente sem atualizar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-203">**Cancel** - Terminates the wizard without upgrading the DAC.</span></span>  
  
##  <a name="detect-change-page"></a><a name="Detect_change"></a> <span data-ttu-id="82a8a-204">Página Detectar Alterações</span><span class="sxs-lookup"><span data-stu-id="82a8a-204">Detect Change Page</span></span>  
 <span data-ttu-id="82a8a-205">O uso desta página relata os resultados da verificação dos assistentes quanto às alterações feitas no banco de dados que tornam esse esquema diferente da definição de esquema armazenada nos metadados do DAC no **msdb**.</span><span class="sxs-lookup"><span data-stu-id="82a8a-205">Use this page reports the results of the wizards check for changes made to the database that make it's schema different than the schema definition stored in the DAC metadata in **msdb**.</span></span> <span data-ttu-id="82a8a-206">Por exemplo, se as instruções CREATE, ALTER ou DROP tiverem sido usadas para adicionar, alterar ou remover objetos do banco de dados após a implantação original do DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-206">For example, if CREATE, ALTER, or DROP statements have been used to add, change, or remove objects from the database after the DAC was originally deployed.</span></span> <span data-ttu-id="82a8a-207">Primeiro, a página exibe uma barra de progresso e depois relata os resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="82a8a-207">The page first displays a progress bar, and then reports the results of the analysis.</span></span>  
  
 <span data-ttu-id="82a8a-208">**Detectando alteração, isso pode demorar alguns minutos** – Exibe uma barra de progresso enquanto o assistente verifica as diferenças entre o esquema atual do banco de dados e os objetos na definição do DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-208">**Detecting change, this may take a few minutes** - Displays a progress bar as the wizard checks for differences between the current schema of the database and the objects in the DAC definition.</span></span>  
  
 <span data-ttu-id="82a8a-209">**Resultados da detecção de alterações:** – Indica se a análise foi concluída e os resultados são relatados abaixo.</span><span class="sxs-lookup"><span data-stu-id="82a8a-209">**Change detection results:** - Indicates that the analysis has completed and the results are reported below.</span></span>  
  
 <span data-ttu-id="82a8a-210">**O banco de dados DatabaseName não foi alterado** – O assistente não detectou diferenças nos objetos definidos no banco de dados e em suas contrapartes na definição do DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-210">**The database DatabaseName has not changed** - The wizard detected no differences in the objects defined in the database and their counterparts in the DAC definition.</span></span>  
  
 <span data-ttu-id="82a8a-211">**O banco de dados DatabaseName foi alterado** – O assistente detectou alterações entre os objetos no banco de dados e em suas contrapartes na definição do DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-211">**The database DatabaseName has changed** - The wizard detected changes between the objects in the database and their counterparts in the DAC definition.</span></span>  
  
 <span data-ttu-id="82a8a-212">**Continuar, apesar da possível perda de alterações** – Especifique que você entende que alguns dos objetos ou dados no banco de dados atual não estarão presentes no novo banco de dados e que está disposto a continuar com a atualização.</span><span class="sxs-lookup"><span data-stu-id="82a8a-212">**Proceed despite possible loss of changes** - Specifies that you understand some of the objects or data in the current database will not be present in the new database, and that you are willing to proceed with the upgrade.</span></span> <span data-ttu-id="82a8a-213">Somente selecione este botão se você tiver analisado o relatório de alterações e entender as etapas que deve executar para transferir manualmente os objetos ou os dados necessários no novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-213">You should select this button only if you have analyzed the change report and understand the steps you must perform to manually transfer any objects or data required in the new database.</span></span> <span data-ttu-id="82a8a-214">Se você não tiver certeza, clique no botão **Salvar Relatório** para salvar o relatório de alterações e clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="82a8a-214">If you are not sure, click the **Save Report** button to save the change report, then click **Cancel**.</span></span> <span data-ttu-id="82a8a-215">Analise o relatório, faça um planejamento de como transferir os objetos e os dados necessários após a conclusão da atualização e reinicie o assistente.</span><span class="sxs-lookup"><span data-stu-id="82a8a-215">Analyze the report, plan how to transfer any required objects and data after the upgrade completes, then restart the wizard.</span></span>  
  
 <span data-ttu-id="82a8a-216">**Salvar Relatório** – Clique no botão para salvar um relatório das alterações que o assistente detectou entre os objetos no banco de dados e suas contrapartes na definição do DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-216">**Save Report** - Click the button to save a report of the changes the wizard detected between the objects in the database and their counterparts in the DAC definition.</span></span> <span data-ttu-id="82a8a-217">Em seguida, você pode examinar o relatório para determinar se precisa executar ações após a conclusão da atualização para incorporar alguns ou todos os objetos listados no relatório para o novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-217">You can then review the report to determine if you need to take actions after the upgrade completes to incorporate some or all of the objects listed in the report into the new database.</span></span>  
  
 <span data-ttu-id="82a8a-218">\*\* \< Anterior\*\* – retorna para a página **selecionar pacote de DAC** .</span><span class="sxs-lookup"><span data-stu-id="82a8a-218">**\< Previous** - Returns to the **Select DAC Package** page.</span></span>  
  
 <span data-ttu-id="82a8a-219">**Avançar >** – Segue para a página **Opções**.</span><span class="sxs-lookup"><span data-stu-id="82a8a-219">**Next >** - Proceeds to the **Options** page.</span></span>  
  
 <span data-ttu-id="82a8a-220">**Cancelar** – Encerra o assistente sem implantar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-220">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
## <a name="options-page"></a><span data-ttu-id="82a8a-221">Página Opções</span><span class="sxs-lookup"><span data-stu-id="82a8a-221">Options Page</span></span>  
 <span data-ttu-id="82a8a-222">Use esta página para selecionar a reversão em opção de falha para a atualização.</span><span class="sxs-lookup"><span data-stu-id="82a8a-222">Use this page to select the rollback on failure option for the upgrade.</span></span>  
  
 <span data-ttu-id="82a8a-223">**Reversão em falha** – Selecione esta opção para incluir a atualização em uma transação que o assistente pode tentar reverter em caso de erros.</span><span class="sxs-lookup"><span data-stu-id="82a8a-223">**Rollback on failure** - Select this option to enclose the upgrade in a transaction which the wizard can attempt to roll back if errors occur.</span></span> <span data-ttu-id="82a8a-224">Para obter mais informações sobre a opção, consulte [Escolhendo Opções de Atualização de DAC](#ChoseDACUpgOptions).</span><span class="sxs-lookup"><span data-stu-id="82a8a-224">For more information about the option, see [Choosing DAC Upgrade Options](#ChoseDACUpgOptions).</span></span>  
  
 <span data-ttu-id="82a8a-225">**Restaurar Padrões** – Retorna a opção à configuração padrão de false.</span><span class="sxs-lookup"><span data-stu-id="82a8a-225">**Restore Defaults** - Returns the option to its default setting of false.</span></span>  
  
 <span data-ttu-id="82a8a-226">\*\* \< Anterior\*\* – retorna para a página **detectar alteração** .</span><span class="sxs-lookup"><span data-stu-id="82a8a-226">**\< Previous** - Returns to the **Detect Change** page.</span></span>  
  
 <span data-ttu-id="82a8a-227">**Avançar >** – Segue para a página **Examinar o Plano de Atualização**.</span><span class="sxs-lookup"><span data-stu-id="82a8a-227">**Next >** - Proceeds to the **Review the Upgrade Plan** page.</span></span>  
  
 <span data-ttu-id="82a8a-228">**Cancelar** – Encerra o assistente sem implantar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-228">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="review-the-upgrade-plan-page"></a><a name="ReviewUpgPlan"></a> <span data-ttu-id="82a8a-229">Página Analisar um plano de atualização</span><span class="sxs-lookup"><span data-stu-id="82a8a-229">Review the Upgrade Plan Page</span></span>  
 <span data-ttu-id="82a8a-230">Use esta página para examinar as ações que serão tomadas pelo processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="82a8a-230">Use this page to do review the actions that will be taken by the upgrade process.</span></span> <span data-ttu-id="82a8a-231">Só prossiga quando estiver certo de que a atualização não criará problemas.</span><span class="sxs-lookup"><span data-stu-id="82a8a-231">Only proceed when you are confident the upgrade will not create problems.</span></span>  
  
 <span data-ttu-id="82a8a-232">**As ações a seguir serão usadas para atualizar o DAC.**</span><span class="sxs-lookup"><span data-stu-id="82a8a-232">**The following actions will be used to upgrade the DAC.**</span></span> <span data-ttu-id="82a8a-233">- Examine as informações exibidas para assegurar que as ações executadas estarão corretas.</span><span class="sxs-lookup"><span data-stu-id="82a8a-233">- Review the information displayed to ensure the actions taken will be correct.</span></span> <span data-ttu-id="82a8a-234">A coluna **Ação** exibe as ações, tais como instruções Transact-SQL, que serão executadas para realizar a atualização.</span><span class="sxs-lookup"><span data-stu-id="82a8a-234">The **Action** column displays the actions, such as Transact-SQL statements, that will be run to perform the upgrade.</span></span> <span data-ttu-id="82a8a-235">A coluna **Perda de Dados** conterá um aviso se a ação associada puder excluir dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-235">The **Data Loss** column will contain a warning if the associated action could delete data.</span></span>  
  
 <span data-ttu-id="82a8a-236">**Atualizar** – Atualiza a lista de ações.</span><span class="sxs-lookup"><span data-stu-id="82a8a-236">**Refresh** - refreshes the action list.</span></span>  
  
 <span data-ttu-id="82a8a-237">**Salvar Relatório de Ação** – Salva o conteúdo da janela de ação em um arquivo HTML.</span><span class="sxs-lookup"><span data-stu-id="82a8a-237">**Save Action Report** - saves the contents of the action window to an HTML file.</span></span>  
  
 <span data-ttu-id="82a8a-238">**Continuar, apesar da possível perda de alterações** – Especifique que você entende que alguns dos objetos ou dados no banco de dados atual não estarão presentes no novo banco de dados e que está disposto a continuar com a atualização.</span><span class="sxs-lookup"><span data-stu-id="82a8a-238">**Proceed despite possible loss of changes** - Specifies that you understand some of the objects or data in the current database will not be present in the new database, and that you are willing to proceed with the upgrade.</span></span> <span data-ttu-id="82a8a-239">Somente selecione este botão se você tiver analisado o relatório de alterações e entender as etapas que deve executar para transferir manualmente os objetos ou os dados necessários no novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="82a8a-239">You should select this button only if you have analyzed the change report and understand the steps you must perform to manually transfer any objects or data required in the new database.</span></span> <span data-ttu-id="82a8a-240">Se você não tiver certeza, clique no botão **Salvar Relatório de Ação** para salvar o relatório de alterações e no botão **Salvar Scripts** para salvar o script Transact-SQL. Depois, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="82a8a-240">If you are not sure, click the **Save Action Report** button to save the change report and the **Save Scripts** button to save the Transact-SQL script, then click **Cancel**.</span></span> <span data-ttu-id="82a8a-241">Analise o relatório e o script. Em seguida, planeje como transferir os objetos e os dados necessários após a conclusão da atualização. Reinicie o assistente.</span><span class="sxs-lookup"><span data-stu-id="82a8a-241">Analyze the report and script, and then plan how to transfer any required objects and data after the upgrade completes, then restart the wizard.</span></span>  
  
 <span data-ttu-id="82a8a-242">**Salvar Scripts** – Salva as instruções Transact-SQL que serão usadas para executar a atualização em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="82a8a-242">**Save Scripts** - saves the Transact-SQL statements that will be used to perform the upgrade to a text file.</span></span>  
  
 <span data-ttu-id="82a8a-243">**Restaurar Padrões** – Retorna a opção à configuração padrão de false.</span><span class="sxs-lookup"><span data-stu-id="82a8a-243">**Restore Defaults** - Returns the option to its default setting of false.</span></span>  
  
 <span data-ttu-id="82a8a-244">\*\* \< Anterior\*\* – retorna para a página **detectar alteração** .</span><span class="sxs-lookup"><span data-stu-id="82a8a-244">**\< Previous** - Returns to the **Detect Change** page.</span></span>  
  
 <span data-ttu-id="82a8a-245">**Avançar >** : continua para a página **Resumo**.</span><span class="sxs-lookup"><span data-stu-id="82a8a-245">**Next >** - Proceeds to the **Summary** page.</span></span>  
  
 <span data-ttu-id="82a8a-246">**Cancelar** – Encerra o assistente sem implantar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-246">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="82a8a-247">Página de Resumo</span><span class="sxs-lookup"><span data-stu-id="82a8a-247">Summary Page</span></span>  
 <span data-ttu-id="82a8a-248">Use esta página para fazer uma análise final das ações do assistente ao atualizar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-248">Use this page to do a final review of the actions the wizard will take when upgrading the DAC.</span></span>  
  
 <span data-ttu-id="82a8a-249">**As configurações a seguir serão usadas para atualizar o DAC.**</span><span class="sxs-lookup"><span data-stu-id="82a8a-249">**The following settings will be used to upgrade your DAC.**</span></span> <span data-ttu-id="82a8a-250">- Examine as informações exibidas para assegurar que as ações executadas estarão corretas.</span><span class="sxs-lookup"><span data-stu-id="82a8a-250">- Review the information displayed to ensure the actions taken will be correct.</span></span> <span data-ttu-id="82a8a-251">A janela exibe o DAC selecionado para atualização e o pacote de DAC que contém a nova versão do DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-251">The window displays the DAC you selected to be upgraded, and the DAC package containing the new version of the DAC.</span></span> <span data-ttu-id="82a8a-252">A janela também exibe se a versão atual do banco de dados é igual à definição de DAC atual, ou se o banco de dados foi alterado.</span><span class="sxs-lookup"><span data-stu-id="82a8a-252">The window also displays whether the current version of the database is the same as the current DAC definition, or if the database has changed.</span></span>  
  
 <span data-ttu-id="82a8a-253">\*\* \< Anterior\*\* – retorna para a página **revisar o plano de atualização** .</span><span class="sxs-lookup"><span data-stu-id="82a8a-253">**\< Previous** - Returns you to the **Review the Upgrade Plan** page.</span></span>  
  
 <span data-ttu-id="82a8a-254">**Avançar >** – Implanta o DAC e exibe os resultados na página **Atualizar DAC**.</span><span class="sxs-lookup"><span data-stu-id="82a8a-254">**Next >** - Deploys the DAC and displays the results in the **Upgrade DAC** page.</span></span>  
  
 <span data-ttu-id="82a8a-255">**Cancelar** – Encerra o assistente sem implantar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-255">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="upgrade-dac-page"></a><a name="Upgrade"></a> <span data-ttu-id="82a8a-256">Página Atualizar DAC</span><span class="sxs-lookup"><span data-stu-id="82a8a-256">Upgrade DAC Page</span></span>  
 <span data-ttu-id="82a8a-257">Esta página relata o êxito ou falha da operação de atualização.</span><span class="sxs-lookup"><span data-stu-id="82a8a-257">This page reports the success or failure of the upgrade operation.</span></span>  
  
 <span data-ttu-id="82a8a-258">**Atualizando o DAC** – Relata o êxito ou falha de cada ação realizada para atualizar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-258">**Upgrading the DAC** - Reports the success or failure of each action taken to upgrade the DAC.</span></span> <span data-ttu-id="82a8a-259">Analise as informações para determinar o êxito ou falha de cada ação.</span><span class="sxs-lookup"><span data-stu-id="82a8a-259">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="82a8a-260">Todas as ações que encontrarem um erro terão um link na coluna **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="82a8a-260">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="82a8a-261">Selecione o link para exibir um relatório do erro para aquela ação.</span><span class="sxs-lookup"><span data-stu-id="82a8a-261">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="82a8a-262">**Salvar Relatório** – Selecione esse botão para salvar o relatório de atualização em um arquivo HTML.</span><span class="sxs-lookup"><span data-stu-id="82a8a-262">**Save Report** - Select this button to save the upgrade report to an HTML file.</span></span> <span data-ttu-id="82a8a-263">O arquivo relata o status de cada ação, inclusive todos os erros gerados por qualquer uma das ações.</span><span class="sxs-lookup"><span data-stu-id="82a8a-263">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="82a8a-264">A pasta padrão é uma pasta SQL Server Gerenciamento Studio\Pacotes de DAC na pasta Documentos da conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="82a8a-264">The default folder is a SQL Server Management Studio\DAC Packages folder in the Documents folder of your Windows account.</span></span>  
  
 <span data-ttu-id="82a8a-265">**Concluir** – Encerra o assistente.</span><span class="sxs-lookup"><span data-stu-id="82a8a-265">**Finish** - Terminates the wizard.</span></span>  
  
##  <a name="using-powershell"></a><a name="UpgradeDACPowerShell"></a> <span data-ttu-id="82a8a-266">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="82a8a-266">Using PowerShell</span></span>  
 <span data-ttu-id="82a8a-267">**Para atualizar um DAC que usa o método IncrementalUpgrade() em um script do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="82a8a-267">**To upgrade a DAC using the IncrementalUpgrade() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="82a8a-268">Crie um objeto de servidor SMO e defina-o como a instância que contém o DAC a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="82a8a-268">Create a SMO Server object and set it to the instance that contains the DAC to be upgraded.</span></span>  
  
2.  <span data-ttu-id="82a8a-269">Abra um objeto `ServerConnection` e conecte-se à mesma instância.</span><span class="sxs-lookup"><span data-stu-id="82a8a-269">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="82a8a-270">Use `System.IO.File` para carregar o arquivo de pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-270">Use `System.IO.File` to load the DAC package file.</span></span>  
  
4.  <span data-ttu-id="82a8a-271">Use `add_DacActionStarted` e `add_DacActionFinished` para assinar os eventos de atualização do DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-271">Use `add_DacActionStarted` and `add_DacActionFinished` to subscribe to the DAC upgrade events.</span></span>  
  
5.  <span data-ttu-id="82a8a-272">Defina o `DacUpgradeOptions`.</span><span class="sxs-lookup"><span data-stu-id="82a8a-272">Set the `DacUpgradeOptions`.</span></span>  
  
6.  <span data-ttu-id="82a8a-273">Use o método `IncrementalUpgrade` para atualizar o DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-273">Use the `IncrementalUpgrade` method to upgrade the DAC.</span></span>  
  
7.  <span data-ttu-id="82a8a-274">Feche o fluxo de arquivos usado para ler o arquivo de pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="82a8a-274">Close the file stream used to read the DAC package file.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="82a8a-275">Exemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="82a8a-275">Example (PowerShell)</span></span>  
 <span data-ttu-id="82a8a-276">O exemplo a seguir atualiza um DAC nomeado MyApplication em uma instância padrão do [!INCLUDE[ssDE](../../includes/ssde-md.md)], usando uma nova versão de DAC em um pacote de MyApplicationVNext.dacpac.</span><span class="sxs-lookup"><span data-stu-id="82a8a-276">The following example upgrades a DAC named MyApplication on a default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], using a new DAC version in a MyApplicationVNext.dacpac package.</span></span>  
  
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
  
## Subscribe to the DAC upgrade events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Upgrade the DAC and close the package.  
$dacName  = "MyApplication"  
  
## Set the upgrade options.  
$upgradeProperties = New-Object Microsoft.SqlServer.Management.Dac.DacUpgradeOptions  
$upgradeProperties.blockonchanges = $true  
$upgradeProperties.ignoredataloss = $false  
$upgradeProperties.rollbackonfailure = $true  
$ upgradeProperties.skippolicyvalidation = $false  
  
## Upgrade the DAC  
$dacstore.IncrementalUpgrade($dacName, $dacType, $upgradeProperties)  
## Close the package file.  
$fileStream.Close()  
```  
  
## <a name="see-also"></a><span data-ttu-id="82a8a-277">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82a8a-277">See Also</span></span>  
 <span data-ttu-id="82a8a-278">[Aplicativos da Camada de Dados](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="82a8a-278">[Data-tier Applications](data-tier-applications.md) </span></span>  
 [<span data-ttu-id="82a8a-279">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="82a8a-279">SQL Server PowerShell</span></span>](../../powershell/sql-server-powershell.md)  
