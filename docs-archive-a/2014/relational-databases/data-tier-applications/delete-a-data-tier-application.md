---
title: Excluir um aplicativo da camada de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.deletedacwizard.introduction.f1
- sql12.swb.deletedacwizard.deletedac.f1
- sql12.swb.deletedacwizard.summary.f1
- sql12.swb.deletedacwizard.choosemethod.f1
helpviewer_keywords:
- How to [DAC], delete
- data-tier application [SQL Server], delete
- wizard [DAC], delete
- delete DAC
ms.assetid: 16fe1c18-4486-424d-81d6-d276ed97482f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 602256c287a8c7bcf9d3fa5597b2fec2085c626c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683550"
---
# <a name="delete-a-data-tier-application"></a><span data-ttu-id="3b8a0-102">Excluir um Aplicativo da Camada de Dados</span><span class="sxs-lookup"><span data-stu-id="3b8a0-102">Delete a Data-tier Application</span></span>
  <span data-ttu-id="3b8a0-103">Você poderá excluir um aplicativo da camada de dados usando o Assistente para Excluir Aplicativo da Camada de Dados ou um script do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-103">You can delete a data-tier application by using either the Delete Data-tier Application wizard or a Windows PowerShell script.</span></span> <span data-ttu-id="3b8a0-104">É possível especificar se o banco de dados associado será retido, desanexado ou removido.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-104">You can specify whether the associated database is retained, detached, or dropped.</span></span>  
  
-   <span data-ttu-id="3b8a0-105">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="3b8a0-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="3b8a0-106">**Para atualizar um DAC, usando:**  [O Assistente de Aplicativo da Camada de Dados de Registro](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="3b8a0-106">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="3b8a0-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3b8a0-107">Before You Begin</span></span>  
 <span data-ttu-id="3b8a0-108">Ao excluir uma instância de DAC (aplicativo da camada de dados), você escolhe uma das três opções que especificam o que será feito com o banco de dados associado ao aplicativo da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-108">When you delete a data-tier application (DAC) instance, you choose one of three options specifying what is to be done with the database associated with the data-tier application.</span></span> <span data-ttu-id="3b8a0-109">Todas as três opções excluem os metadados da definição do DAC.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-109">All three options delete the DAC definition metadata.</span></span> <span data-ttu-id="3b8a0-110">As opções diferem no que fazem com o banco de dados associado ao aplicativo da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-110">The options differ in what they do with the database associated with the data-tier application.</span></span> <span data-ttu-id="3b8a0-111">O assistente não exclui nenhum dos objetos do nível de instância associados ao DAC ou banco de dados, como logons.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-111">The wizard does not delete any of the instance-level objects associated with the DAC or database, such as logins.</span></span>  
  
|<span data-ttu-id="3b8a0-112">Opção</span><span class="sxs-lookup"><span data-stu-id="3b8a0-112">Option</span></span>|<span data-ttu-id="3b8a0-113">Ações de banco de dados</span><span class="sxs-lookup"><span data-stu-id="3b8a0-113">Database actions</span></span>|  
|------------|----------------------|  
|<span data-ttu-id="3b8a0-114">Excluir registro</span><span class="sxs-lookup"><span data-stu-id="3b8a0-114">Delete registration</span></span>|<span data-ttu-id="3b8a0-115">O banco de dados associado permanece intacto.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-115">The associated database remains intact.</span></span>|  
|<span data-ttu-id="3b8a0-116">Desanexar banco de dados</span><span class="sxs-lookup"><span data-stu-id="3b8a0-116">Detach database</span></span>|<span data-ttu-id="3b8a0-117">O banco de dados associado é desanexado.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-117">The associated database is detached.</span></span> <span data-ttu-id="3b8a0-118">A instância do Mecanismo de Banco de Dados não pode fazer referência ao banco de dados, mas os dados e os arquivos de log estão intatos.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-118">The instance of the Database Engine cannot reference the database, but the data and log files are intact.</span></span>|  
|<span data-ttu-id="3b8a0-119">Excluir banco de dados</span><span class="sxs-lookup"><span data-stu-id="3b8a0-119">Delete database</span></span>|<span data-ttu-id="3b8a0-120">O banco de dados associado é removido.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-120">The associated database is dropped.</span></span> <span data-ttu-id="3b8a0-121">Os dados e os arquivos de log são excluídos.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-121">The data and log files are deleted.</span></span>|  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="3b8a0-122">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="3b8a0-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3b8a0-123">Não há nenhum mecanismo automático para restaurar os metadados da definição do DAC ou o banco de dados depois que um DAC é excluído.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-123">There is no automatic mechanism to restore the DAC definition metadata or the database after you delete a DAC.</span></span> <span data-ttu-id="3b8a0-124">A maneira como a instância do DAC pode ser recriada manualmente depende da opção de exclusão.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-124">How you can manually rebuild the DAC instance depends on the delete option.</span></span>  
  
|<span data-ttu-id="3b8a0-125">Opção</span><span class="sxs-lookup"><span data-stu-id="3b8a0-125">Option</span></span>|<span data-ttu-id="3b8a0-126">Como recriar a instância do DAC</span><span class="sxs-lookup"><span data-stu-id="3b8a0-126">How to Rebuild the DAC Instance</span></span>|  
|------------|-------------------------------------|  
|<span data-ttu-id="3b8a0-127">Excluir registro</span><span class="sxs-lookup"><span data-stu-id="3b8a0-127">Delete registration</span></span>|<span data-ttu-id="3b8a0-128">Registrar um DAC do banco de dados deixado no lugar.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-128">Register a DAC from the database left in place.</span></span>|  
|<span data-ttu-id="3b8a0-129">Desanexar banco de dados</span><span class="sxs-lookup"><span data-stu-id="3b8a0-129">Detach database</span></span>|<span data-ttu-id="3b8a0-130">Reanexe o banco de dados usando **sp_attachdb** ou [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e registre uma nova instância de DAC do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-130">Re-attach the database by using **sp_attachdb** or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then register a new DAC instance from the database.</span></span>|  
|<span data-ttu-id="3b8a0-131">Excluir banco de dados</span><span class="sxs-lookup"><span data-stu-id="3b8a0-131">Delete database</span></span>|<span data-ttu-id="3b8a0-132">Restaure o banco de dados de um backup completo feito antes do DAC ser excluído e registre uma nova instância do DAC no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-132">Restore the database from a full backup made before the DAC was deleted, and then register a new DAC instance from the database.</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="3b8a0-133">A recompilação de uma instância de DAC através do registro de um DAC em um banco de dados restaurado ou reanexado não recriará algumas partes do DAC original, como a política de seleção de servidor.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-133">Rebuilding a DAC instance by registering a DAC from a restored or re-attached database will not recreate some parts of the original DAC, such as the server selection policy.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3b8a0-134">Permissões</span><span class="sxs-lookup"><span data-stu-id="3b8a0-134">Permissions</span></span>  
 <span data-ttu-id="3b8a0-135">Um DAC pode ser excluído somente pelos membros das funções de servidor fixas **sysadmin** ou **serveradmin** , ou pelo proprietário do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-135">A DAC can only be deleted by members of the **sysadmin** or **serveradmin** fixed server roles, or by the database owner.</span></span> <span data-ttu-id="3b8a0-136">A conta interna do administrador de sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] chamada **sa** também pode iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-136">The built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator account named **sa** can also launch the wizard.</span></span>  
  
##  <a name="using-the-delete-data-tier-application-wizard"></a><a name="UsingDeleteDACWizard"></a> <span data-ttu-id="3b8a0-137">Usando o Assistente para Excluir Aplicativo da Camada de Dados</span><span class="sxs-lookup"><span data-stu-id="3b8a0-137">Using the Delete Data-tier Application Wizard</span></span>  
 <span data-ttu-id="3b8a0-138">**Para excluir um DAC usando um assistente**</span><span class="sxs-lookup"><span data-stu-id="3b8a0-138">**To Delete a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="3b8a0-139">No **Pesquisador de Objetos**, expanda o nó da instância que contém o DAC a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-139">In **Object Explorer**, expand the node for the instance containing the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="3b8a0-140">Expanda o nó **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="3b8a0-140">Expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="3b8a0-141">Expanda o nó **Aplicativos da Camada de Dados** .</span><span class="sxs-lookup"><span data-stu-id="3b8a0-141">Expand the **Data-tier Applications** node.</span></span>  
  
4.  <span data-ttu-id="3b8a0-142">Clique com o botão direito do mouse no DAC a ser excluído e selecione **Excluir Aplicativo da Camada de Dados...**</span><span class="sxs-lookup"><span data-stu-id="3b8a0-142">Right-click the DAC to be deleted, and then select **Delete Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="3b8a0-143">Conclua as etapas das caixas de diálogo do assistente:</span><span class="sxs-lookup"><span data-stu-id="3b8a0-143">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="3b8a0-144">Introdução</span><span class="sxs-lookup"><span data-stu-id="3b8a0-144">Introduction</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="3b8a0-145">Escolher método</span><span class="sxs-lookup"><span data-stu-id="3b8a0-145">Choose Method</span></span>](#Choose_method)  
  
    3.  [<span data-ttu-id="3b8a0-146">Resumo</span><span class="sxs-lookup"><span data-stu-id="3b8a0-146">Summary</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="3b8a0-147">Excluir Aplicativo da Camada de Dados</span><span class="sxs-lookup"><span data-stu-id="3b8a0-147">Delete Data-tier Application</span></span>](#Delete_datatier_application)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="3b8a0-148">Página de Introdução</span><span class="sxs-lookup"><span data-stu-id="3b8a0-148">Introduction Page</span></span>  
 <span data-ttu-id="3b8a0-149">Esta página descreve as etapas para excluir um aplicativo da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-149">This page describes the steps for deleting a data-tier application.</span></span>  
  
 <span data-ttu-id="3b8a0-150">**Não mostrar esta página novamente.**</span><span class="sxs-lookup"><span data-stu-id="3b8a0-150">**Do not show this page again.**</span></span> <span data-ttu-id="3b8a0-151">- Clique na caixa de seleção para interromper a exibição da página no futuro.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-151">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="3b8a0-152">**Avançar >** : continua para a página **Escolher Método**.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-152">**Next >** - Proceeds to the **Choose Method** page.</span></span>  
  
 <span data-ttu-id="3b8a0-153">**Cancelar** : finaliza o assistente sem excluir um aplicativo da camada de dados ou banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-153">**Cancel** - Ends the wizard without deleting a data-tier application or database.</span></span>  
  
##  <a name="choose-method-page"></a><a name="Choose_method"></a> <span data-ttu-id="3b8a0-154">Página Escolher Método</span><span class="sxs-lookup"><span data-stu-id="3b8a0-154">Choose Method Page</span></span>  
 <span data-ttu-id="3b8a0-155">Use esta página para especificar a opção que tratará o banco de dados associado ao DAC que será excluído.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-155">Use this page to specify the option for handling the database associated with the DAC to be deleted.</span></span>  
  
 <span data-ttu-id="3b8a0-156">**Excluir registro** : remove os metadados que definem o aplicativo da camada de dados, mas deixa o banco de dados associado intacto.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-156">**Delete registration** - Removes the metadata defining the data-tier application, but leaves the associated database intact.</span></span>  
  
 <span data-ttu-id="3b8a0-157">**Desanexar banco de dados** : remove os metadados que definem o aplicativo da camada de dados e desanexa o banco de dados associado.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-157">**Detach database** - Removes the metadata defining the data-tier application and detaches the associated database.</span></span>  
  
 <span data-ttu-id="3b8a0-158">O banco de dados não pode mais ser referenciado por aquela instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)], mas os dados e os arquivos de log permanecem intactos.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-158">The database can no longer be referenced by that instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but the data and log files remain intact.</span></span>  
  
 <span data-ttu-id="3b8a0-159">**Excluir banco de dados** : remove os metadados que definem o DAC e descarta o banco de dados associado.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-159">**Delete database** - Removes the metadata defining the DAC and drops the associated database.</span></span>  
  
 <span data-ttu-id="3b8a0-160">Os dados e os arquivos de log do banco de dados são excluídos permanentemente.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-160">The data and log files for the database are permanently deleted.</span></span>  
  
 <span data-ttu-id="3b8a0-161">\*\* \< Anterior\*\* – retorna à página **introdução** .</span><span class="sxs-lookup"><span data-stu-id="3b8a0-161">**\< Previous** - Returns to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="3b8a0-162">**Avançar >**: continua para a página **Resumo**.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-162">**Next >** - Proceeds to the **Summary** page.</span></span>  
  
 <span data-ttu-id="3b8a0-163">**Cancelar** : finaliza o assistente sem excluir o DAC ou o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-163">**Cancel** - Ends the wizard without deleting the DAC or database.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="3b8a0-164">Página de Resumo</span><span class="sxs-lookup"><span data-stu-id="3b8a0-164">Summary Page</span></span>  
 <span data-ttu-id="3b8a0-165">Use esta página para examinar as ações que o assistente tomará ao excluir a instância do DAC.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-165">Use this page to review the actions the wizard will take when deleting the DAC instance.</span></span>  
  
 <span data-ttu-id="3b8a0-166">**Review your selection summary (Examinar o resumo de sua seleção)** : examine o DAC, o banco de dados e o método de exclusão exibidos na caixa.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-166">**Review your selection summary** - Review the DAC, database, and deletion method displayed in the box.</span></span> <span data-ttu-id="3b8a0-167">Se as informações estiverem corretas, selecione **Avançar** ou **Concluir** para excluir o DAC.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-167">If the information is correct, select either **Next** or **Finish** to delete the DAC.</span></span> <span data-ttu-id="3b8a0-168">Se o DAC e as informações do banco de dados não estiverem corretas, selecione **Cancelar** e selecione o DAC correto.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-168">If the DAC and database information is not correct, select **Cancel** and select the correct DAC.</span></span> <span data-ttu-id="3b8a0-169">Se o método de exclusão não estiver correto, selecione **Anterior** para retornar ou a página **Escolher Método** e selecione um método diferente.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-169">If the deletion method is not correct, select **Previous** to return to the **Choose Method** page and select a different method.</span></span>  
  
 <span data-ttu-id="3b8a0-170">\*\* \< Anterior\*\* – retorna para a página **escolher método** para escolher um método de exclusão diferente.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-170">**\< Previous** - Returns to the **Choose Method** page to choose a different delete method.</span></span>  
  
 <span data-ttu-id="3b8a0-171">**Avançar >**: exclui a instância de DAC usando o método escolhido na página anterior e continua para a página **Excluir Aplicativo da Camada de Dados**.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-171">**Next >** - Deletes the DAC instance using the method you chose on the previous page, and proceeds to the **Delete Data-tier Application** page.</span></span>  
  
 <span data-ttu-id="3b8a0-172">**Cancelar** : finaliza o assistente sem excluir a instância de DAC.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-172">**Cancel** - Ends the wizard without deleting the DAC instance.</span></span>  
  
##  <a name="delete-data-tier-application-page"></a><a name="Delete_datatier_application"></a><span data-ttu-id="3b8a0-173">Página excluir aplicativo da camada de dados</span><span class="sxs-lookup"><span data-stu-id="3b8a0-173">Delete Data-tier Application Page</span></span>  
 <span data-ttu-id="3b8a0-174">Esta página relata o êxito ou a falha da operação de exclusão.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-174">This page reports the success or failure of the delete operation.</span></span>  
  
 <span data-ttu-id="3b8a0-175">**Excluindo o DAC** : relata o êxito ou falha de cada ação realizada para excluir a instância de DAC.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-175">**Deleting the DAC** - Reports the success or failure of each action taken to delete the DAC instance.</span></span> <span data-ttu-id="3b8a0-176">Analise as informações para determinar o êxito ou falha de cada ação.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-176">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="3b8a0-177">Todas as ações que encontrarem um erro terão um link na coluna **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="3b8a0-177">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="3b8a0-178">Selecione o link para exibir um relatório do erro para aquela ação.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-178">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="3b8a0-179">**Salvar Relatório** : selecione esse botão para salvar o relatório de exclusão em um arquivo HTML.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-179">**Save Report** - Select this button to save the deletion report to an HTML file.</span></span> <span data-ttu-id="3b8a0-180">O arquivo relata o status de cada ação, inclusive todos os erros gerados por qualquer uma das ações.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-180">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="3b8a0-181">A pasta padrão é SQL Server Management Studio\DAC Packages na pasta Documents da conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-181">The default folder is a SQL Server Management Studio\DAC Packages folder in the Documents folder of your Windows account..</span></span>  
  
 <span data-ttu-id="3b8a0-182">**Concluir** : finaliza o assistente.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-182">**Finish** - Ends the wizard.</span></span>  
  
##  <a name="delete-a-dac-using-powershell"></a><a name="DeleteDACPowerShell"></a><span data-ttu-id="3b8a0-183">Excluir um DAC usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b8a0-183">Delete a DAC Using PowerShell</span></span>  
 <span data-ttu-id="3b8a0-184">**Para excluir um DAC usando o script do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3b8a0-184">**To delete a DAC using a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="3b8a0-185">Crie um objeto de servidor SMO e defina-o como a instância que contém o DAC a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-185">Create a SMO Server object and set it to the instance that contains the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="3b8a0-186">Abra um objeto `ServerConnection` e conecte-se à mesma instância.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-186">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="3b8a0-187">Use `add_DacActionStarted` e `add_DacActionFinished` para assinar os eventos de atualização do DAC.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-187">Use `add_DacActionStarted` and `add_DacActionFinished` to subscribe to the DAC upgrade events.</span></span>  
  
4.  <span data-ttu-id="3b8a0-188">Especifique o DAC a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-188">Specify the DAC to delete.</span></span>  
  
5.  <span data-ttu-id="3b8a0-189">Use um destes três conjuntos de códigos, dependendo da opção de exclusão apropriada:</span><span class="sxs-lookup"><span data-stu-id="3b8a0-189">Use one of these three sets of code, depending on which delete option is appropriate:</span></span>  
  
    -   <span data-ttu-id="3b8a0-190">Para excluir o registro do DAC, mas deixar o banco de dados intacto, use o método `Unmanage()`.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-190">To delete the DAC registration but leave the database intact, use the `Unmanage()` method.</span></span>  
  
    -   <span data-ttu-id="3b8a0-191">Para excluir o registro do DAC e desanexar o banco de dados, use o método `Uninstall()` e especifique `DetachDatabase`.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-191">To delete the DAC registration and detach the database, use the `Uninstall()` method and specify `DetachDatabase`.</span></span>  
  
    -   <span data-ttu-id="3b8a0-192">Para excluir o registro do DAC e remover o banco de dados, use o método `Uninstall()` e especifique `DropDatabase`.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-192">To delete the DAC registration and drop the database, use the `Uninstall()` method and specify `DropDatabase`.</span></span>  
  
### <a name="example-deleting-the-dac-but-leaving-the-database-powershell"></a><span data-ttu-id="3b8a0-193">Exemplo Excluindo o DAC mas deixando o banco de dados (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="3b8a0-193">Example Deleting the DAC but Leaving the Database (PowerShell)</span></span>  
 <span data-ttu-id="3b8a0-194">O exemplo a seguir exclui um DAC chamado MyApplication usando o método `Unmanage()` para excluir o DAC, mas deixar o banco de dados intacto.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-194">The following example deletes a DAC named MyApplication using the `Unmanage()` method to delete the DAC but leave the database intact.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Only delete the DAC definition from msdb, the associated database remains active.  
$dacstore.Unmanage($dacName)  
```  
  
### <a name="example-deleting-the-dac-and-detaching-the-database-powershell"></a><span data-ttu-id="3b8a0-195">Exemplo Excluindo o DAC e desanexando o banco de dados (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="3b8a0-195">Example Deleting the DAC and Detaching the Database (PowerShell)</span></span>  
 <span data-ttu-id="3b8a0-196">O exemplo a seguir exclui um DAC chamado MyApplication usando o método `Uninstall()` para excluir o DAC e desanexar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-196">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and detach the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = get-item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and detach the associated database.  
$dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DetachDatabase)  
```  
  
### <a name="example-deleting-the-dac-and-dropping-the-database-powershell"></a><span data-ttu-id="3b8a0-197">Exemplo Excluindo o DAC e removendo o banco de dados (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="3b8a0-197">Example Deleting the DAC and Dropping the Database (PowerShell)</span></span>  
 <span data-ttu-id="3b8a0-198">O exemplo a seguir exclui um DAC chamado MyApplication usando o método `Uninstall()` para excluir o DAC e remover o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3b8a0-198">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and drop the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and drop the associated database.  
## $dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DropDatabase)  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b8a0-199">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b8a0-199">See Also</span></span>  
 <span data-ttu-id="3b8a0-200">[Aplicativos da Camada de Dados](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="3b8a0-200">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="3b8a0-201">[Aplicativos da Camada de Dados](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="3b8a0-201">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="3b8a0-202">[Implantar um aplicativo da camada de dados](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="3b8a0-202">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="3b8a0-203">[Registrar um banco de dados como um DAC](register-a-database-as-a-dac.md) </span><span class="sxs-lookup"><span data-stu-id="3b8a0-203">[Register a Database As a DAC](register-a-database-as-a-dac.md) </span></span>  
 <span data-ttu-id="3b8a0-204">[Fazer backup e restaurar bancos de dados do SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="3b8a0-204">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="3b8a0-205">Anexar e desanexar bancos de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3b8a0-205">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  
