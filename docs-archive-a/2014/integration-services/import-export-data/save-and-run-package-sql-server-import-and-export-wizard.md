---
title: Salvar e executar pacote (SQL Server assistente de importação e exportação) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.saveschedule.f1
ms.assetid: b582c462-3d7a-4a4c-a2a2-2c79fedab75a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a23f69bf66ca3355f1e1c62cc42d51e4aea3da5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575927"
---
# <a name="save-and-execute-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="14d21-102">Salvar e Executar Pacote (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="14d21-102">Save and Execute Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="14d21-103">Use a caixa de diálogo **salvar e executar pacote** para executar o pacote imediatamente, salve-o para execução posterior ou ambos.</span><span class="sxs-lookup"><span data-stu-id="14d21-103">Use the **Save and Execute Package** dialog box to run the package immediately, save it to run later, or both.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14d21-104">Se você parar um pacote antes de concluir a execução, o pacote não será salvo, mesmo que você tenha marcado a caixa de seleção **salvar** .</span><span class="sxs-lookup"><span data-stu-id="14d21-104">If you stop a package before it finishes running, the package is not saved, even if you selected the **Save** check box.</span></span>  
  
 <span data-ttu-id="14d21-105">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="14d21-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="14d21-106">Para saber mais sobre as opções de inicialização do assistente, bem como as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="14d21-106">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="14d21-107">O objetivo do Assistente de Importação e Exportação do SQL Server é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="14d21-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="14d21-108">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="14d21-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="14d21-109">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="14d21-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="14d21-110">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="14d21-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="14d21-111">Opções</span><span class="sxs-lookup"><span data-stu-id="14d21-111">Options</span></span>  
 <span data-ttu-id="14d21-112">**Executar imediatamente**</span><span class="sxs-lookup"><span data-stu-id="14d21-112">**Execute immediately**</span></span>  
 <span data-ttu-id="14d21-113">Selecione esta opção para executar o pacote imediatamente.</span><span class="sxs-lookup"><span data-stu-id="14d21-113">Select this option to run the package immediately.</span></span>  
  
 <span data-ttu-id="14d21-114">**Salvar Pacote SSIS**</span><span class="sxs-lookup"><span data-stu-id="14d21-114">**Save SSIS Package**</span></span>  
 <span data-ttu-id="14d21-115">Salve o pacote para executá-lo posteriormente, com a opção de executá-lo imediatamente.</span><span class="sxs-lookup"><span data-stu-id="14d21-115">Save the package to run later, with the option to run it immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14d21-116">No [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , a opção para salvar o pacote criado pelo assistente não está disponível.</span><span class="sxs-lookup"><span data-stu-id="14d21-116">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="14d21-117">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="14d21-117">**SQL Server**</span></span>  
 <span data-ttu-id="14d21-118">Selecione esta opção para salvar o pacote no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` banco de dados.</span><span class="sxs-lookup"><span data-stu-id="14d21-118">Select this option to save the package to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14d21-119">Essa opção só estará disponível se você tiver selecionado a opção **salvar pacote SSIS** .</span><span class="sxs-lookup"><span data-stu-id="14d21-119">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="14d21-120">**Sistema de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="14d21-120">**File system**</span></span>  
 <span data-ttu-id="14d21-121">Selecione esta opção para salvar o pacote como um arquivo com extensão .dtsx.</span><span class="sxs-lookup"><span data-stu-id="14d21-121">Select this option to save the package as a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14d21-122">Essa opção só estará disponível se você tiver selecionado a opção **salvar pacote SSIS** .</span><span class="sxs-lookup"><span data-stu-id="14d21-122">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="14d21-123">**Nível de Proteção do Pacote**</span><span class="sxs-lookup"><span data-stu-id="14d21-123">**Package protection level**</span></span>  
 <span data-ttu-id="14d21-124">Selecione um nível de proteção na lista.</span><span class="sxs-lookup"><span data-stu-id="14d21-124">Select a protection level from the list.</span></span>  
  
 <span data-ttu-id="14d21-125">O nível de proteção determina o método de proteção, a senha ou a chave de usuário, bem como o escopo de proteção do pacote.</span><span class="sxs-lookup"><span data-stu-id="14d21-125">The protection level determines the protection method, the password or user key, and the scope of package protection.</span></span> <span data-ttu-id="14d21-126">A proteção pode incluir todos os dados ou apenas os dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="14d21-126">Protection can include all data or sensitive data only.</span></span> <span data-ttu-id="14d21-127">Para entender os requisitos e as opções de segurança do pacote, consulte [controle de acesso para dados confidenciais em pacotes](../security/access-control-for-sensitive-data-in-packages.md) e [visão geral de segurança &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="14d21-127">To understand the requirements and options for package security, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md) and [Security Overview &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14d21-128">Essa opção só estará disponível se você tiver selecionado a opção **salvar pacote SSIS** .</span><span class="sxs-lookup"><span data-stu-id="14d21-128">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="14d21-129">**Senha**</span><span class="sxs-lookup"><span data-stu-id="14d21-129">**Password**</span></span>  
 <span data-ttu-id="14d21-130">Digite uma senha.</span><span class="sxs-lookup"><span data-stu-id="14d21-130">Type a password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14d21-131">Essa opção só estará disponível se você tiver definido a opção **nível de proteção do pacote** para **criptografar dados confidenciais com senha** ou **criptografar todos os dados com senha**.</span><span class="sxs-lookup"><span data-stu-id="14d21-131">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
 <span data-ttu-id="14d21-132">**Digite a senha novamente**</span><span class="sxs-lookup"><span data-stu-id="14d21-132">**Retype password**</span></span>  
 <span data-ttu-id="14d21-133">Digite a senha novamente.</span><span class="sxs-lookup"><span data-stu-id="14d21-133">Type the password again.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14d21-134">Essa opção só estará disponível se você tiver definido a opção **nível de proteção do pacote** para **criptografar dados confidenciais com senha** ou **criptografar todos os dados com senha**.</span><span class="sxs-lookup"><span data-stu-id="14d21-134">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14d21-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="14d21-135">See Also</span></span>  
 <span data-ttu-id="14d21-136">[Execução de projetos e pacotes](../packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="14d21-136">[Execution of Projects and Packages](../packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="14d21-137">Salvar pacotes</span><span class="sxs-lookup"><span data-stu-id="14d21-137">Save Packages</span></span>](../save-packages.md)  
  
  
