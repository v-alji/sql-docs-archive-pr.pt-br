---
title: Salvar Pacote SSIS (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.savedtspackage.f1
ms.assetid: 7bf8ac6a-5599-43ab-bf5c-e072c11b85a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d4e582558a1f86b18d935fcc6235ba5839faa031
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575923"
---
# <a name="save-ssis-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="5037f-102">Salvar Pacote SSIS (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5037f-102">Save SSIS Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="5037f-103">Use a página **salvar pacote SSIS** para nomear, descrever e salvar um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pacote Integration Services ( [!INCLUDE[ssIS](../../includes/ssis-md.md)] ) no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` banco de dados ou em um arquivo que tenha a extensão. dtsx.</span><span class="sxs-lookup"><span data-stu-id="5037f-103">Use the **Save SSIS Package** page to name, describe, and save a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database or to a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5037f-104">No [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , a opção para salvar o pacote criado pelo assistente não está disponível.</span><span class="sxs-lookup"><span data-stu-id="5037f-104">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="5037f-105">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5037f-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="5037f-106">Para saber mais sobre as opções de inicialização do assistente e sobre as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5037f-106">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="5037f-107">O objetivo do Assistente de Importação e Exportação do SQL Server é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="5037f-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="5037f-108">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="5037f-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="5037f-109">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="5037f-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="5037f-110">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5037f-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="5037f-111">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="5037f-111">Static Options</span></span>  
 <span data-ttu-id="5037f-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5037f-112">**Name**</span></span>  
 <span data-ttu-id="5037f-113">Forneça um nome exclusivo para o pacote.</span><span class="sxs-lookup"><span data-stu-id="5037f-113">Provide a unique name for the package.</span></span>  
  
 <span data-ttu-id="5037f-114">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5037f-114">**Description**</span></span>  
 <span data-ttu-id="5037f-115">Forneça uma descrição para o pacote.</span><span class="sxs-lookup"><span data-stu-id="5037f-115">Provide a description for the package.</span></span> <span data-ttu-id="5037f-116">Como prática recomendada, descreva o pacote em termos de objetivo, para facilitar a documentação e a manutenção dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="5037f-116">As a best practice, describe the package in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="5037f-117">**Target (destino)**</span><span class="sxs-lookup"><span data-stu-id="5037f-117">**Target**</span></span>  
 <span data-ttu-id="5037f-118">Exiba o destino ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou arquivo) que foi especificado previamente para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="5037f-118">View the target ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or file) that was previously specified for the destination file.</span></span>  
  
## <a name="target-dynamic-options"></a><span data-ttu-id="5037f-119">Opções dinâmicas de destino</span><span class="sxs-lookup"><span data-stu-id="5037f-119">Target Dynamic Options</span></span>  
  
### <a name="target--sql-server"></a><span data-ttu-id="5037f-120">Destino = SQL Server</span><span class="sxs-lookup"><span data-stu-id="5037f-120">Target = SQL Server</span></span>  
 <span data-ttu-id="5037f-121">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="5037f-121">**Server name**</span></span>  
 <span data-ttu-id="5037f-122">Depois de selecionar um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], digite ou selecione o nome do servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="5037f-122">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, type or select the destination server name.</span></span>  
  
 <span data-ttu-id="5037f-123">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="5037f-123">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="5037f-124">Depois de selecionar um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], especifique se deseja se conectar ao servidor usando a Autenticação Integrada do Windows.</span><span class="sxs-lookup"><span data-stu-id="5037f-124">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using Windows Integrated Authentication.</span></span> <span data-ttu-id="5037f-125">Esse é o método de autenticação preferido.</span><span class="sxs-lookup"><span data-stu-id="5037f-125">This is the preferred authentication method.</span></span>  
  
 <span data-ttu-id="5037f-126">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5037f-126">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="5037f-127">Depois de selecionar um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], especifique se deseja se conectar ao servidor usando a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5037f-127">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="5037f-128">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="5037f-128">**User name**</span></span>  
 <span data-ttu-id="5037f-129">Depois de selecionar um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e especificar a Autenticação do SQL Server, digite o nome de usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5037f-129">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user name.</span></span>  
  
 <span data-ttu-id="5037f-130">**Senha**</span><span class="sxs-lookup"><span data-stu-id="5037f-130">**Password**</span></span>  
 <span data-ttu-id="5037f-131">Depois de selecionar um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e especificar a Autenticação do SQL Server, digite a senha do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5037f-131">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] password.</span></span>  
  
### <a name="target--file-system"></a><span data-ttu-id="5037f-132">Destino = Sistema de Arquivos</span><span class="sxs-lookup"><span data-stu-id="5037f-132">Target = File System</span></span>  
 <span data-ttu-id="5037f-133">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="5037f-133">**File name**</span></span>  
 <span data-ttu-id="5037f-134">Quando você tiver selecionado um destino de arquivo, digite o caminho para o arquivo de destino ou use o botão **procurar** .</span><span class="sxs-lookup"><span data-stu-id="5037f-134">When you have selected a file destination, type the path for the destination file, or use the **Browse** button.</span></span>  
  
 <span data-ttu-id="5037f-135">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="5037f-135">**Browse**</span></span>  
 <span data-ttu-id="5037f-136">Quando você tiver selecionado um destino de arquivo, navegue até o arquivo de destino usando a caixa de diálogo **salvar pacote** .</span><span class="sxs-lookup"><span data-stu-id="5037f-136">When you have selected a file destination, browse to the destination file by using the **Save Package** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5037f-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5037f-137">See Also</span></span>  
 [<span data-ttu-id="5037f-138">Salvar pacotes</span><span class="sxs-lookup"><span data-stu-id="5037f-138">Save Packages</span></span>](../save-packages.md)  
  
  
