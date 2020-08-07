---
title: Criar banco de dados (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createdatabase.f1
ms.assetid: 56a8a79f-086c-4bdc-8888-0045bb4b0cbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 617b3fe10a17ae2d8659b51e85cdb3fed4470506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575940"
---
# <a name="create-database-sql-server-import-and-export-wizard"></a><span data-ttu-id="bc31e-102">Criar banco de dados (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bc31e-102">Create Database (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="bc31e-103">Use a página **criar banco de dados** para definir um novo banco de dados para um arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="bc31e-103">Use the **Create Database** page to define a new database for a destination file.</span></span>  
  
 <span data-ttu-id="bc31e-104">Essa página oferece um subconjunto das opções disponíveis por criar um novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc31e-104">This page offers a subset of the available options for creating a new database.</span></span> <span data-ttu-id="bc31e-105">Para exibir todas as opções, use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc31e-105">To view all the options, use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="bc31e-106">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="bc31e-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="bc31e-107">Para saber mais sobre as opções de inicialização do assistente e sobre as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="bc31e-107">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="bc31e-108">O objetivo do Assistente de Importação e Exportação do SQL Server é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="bc31e-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="bc31e-109">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="bc31e-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="bc31e-110">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="bc31e-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="bc31e-111">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="bc31e-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bc31e-112">Opções</span><span class="sxs-lookup"><span data-stu-id="bc31e-112">Options</span></span>  
 <span data-ttu-id="bc31e-113">**Nome**</span><span class="sxs-lookup"><span data-stu-id="bc31e-113">**Name**</span></span>  
 <span data-ttu-id="bc31e-114">Forneça um nome exclusivo para o banco de dados de destino do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc31e-114">Provide a unique name for the destination SQL Server database.</span></span> <span data-ttu-id="bc31e-115">Certifique-se de que as convenções do SQL Server estão sendo seguidas ao nomear o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc31e-115">Make sure that you follow SQL Server conventions when you name this database.</span></span>  
  
 <span data-ttu-id="bc31e-116">**Nome de arquivo de dados**</span><span class="sxs-lookup"><span data-stu-id="bc31e-116">**Data file name**</span></span>  
 <span data-ttu-id="bc31e-117">Exibe o nome do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="bc31e-117">View the name of the data file.</span></span> <span data-ttu-id="bc31e-118">Esse nome é originário do nome de banco de dados definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bc31e-118">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="bc31e-119">**Nome do arquivo de log**</span><span class="sxs-lookup"><span data-stu-id="bc31e-119">**Log file name**</span></span>  
 <span data-ttu-id="bc31e-120">Exibe o nome do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="bc31e-120">View the name of the log file.</span></span> <span data-ttu-id="bc31e-121">Esse nome é originário do nome de banco de dados definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bc31e-121">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="bc31e-122">**Tamanho inicial (arquivo de dados)**</span><span class="sxs-lookup"><span data-stu-id="bc31e-122">**Initial size (data file)**</span></span>  
 <span data-ttu-id="bc31e-123">Especifique o número de megabytes para o tamanho inicial do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="bc31e-123">Specify the number of megabytes for the initial size of the data file.</span></span>  
  
 <span data-ttu-id="bc31e-124">**Não são permitidos crescimentos (arquivo de dados)**</span><span class="sxs-lookup"><span data-stu-id="bc31e-124">**No growth allowed (data file)**</span></span>  
 <span data-ttu-id="bc31e-125">Indique se o arquivo de dados pode crescer além do tamanho inicial especificado.</span><span class="sxs-lookup"><span data-stu-id="bc31e-125">Indicate whether the data file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="bc31e-126">**Crescimento por porcentagem (arquivo de dados)**</span><span class="sxs-lookup"><span data-stu-id="bc31e-126">**Grow by percentage (data file)**</span></span>  
 <span data-ttu-id="bc31e-127">Especifique uma porcentagem para o crescimento do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="bc31e-127">Specify a percentage by which the data file can grow.</span></span>  
  
 <span data-ttu-id="bc31e-128">**Crescimento por tamanho (arquivo de dados)**</span><span class="sxs-lookup"><span data-stu-id="bc31e-128">**Grow by size (data file)**</span></span>  
 <span data-ttu-id="bc31e-129">Especifique um número de megabytes para o crescimento do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="bc31e-129">Specify a number of megabytes by which the data file can grow.</span></span>  
  
 <span data-ttu-id="bc31e-130">**Tamanho inicial (arquivo de log)**</span><span class="sxs-lookup"><span data-stu-id="bc31e-130">**Initial size (log file)**</span></span>  
 <span data-ttu-id="bc31e-131">Especifique o número de megabytes para o tamanho inicial do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="bc31e-131">Specify the number of megabytes for the initial size of the log file.</span></span>  
  
 <span data-ttu-id="bc31e-132">**Não são permitidos crescimentos (arquivo de log)**</span><span class="sxs-lookup"><span data-stu-id="bc31e-132">**No growth allowed (log file)**</span></span>  
 <span data-ttu-id="bc31e-133">Indique se o arquivo de log pode crescer além do tamanho inicial especificado.</span><span class="sxs-lookup"><span data-stu-id="bc31e-133">Indicate whether the log file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="bc31e-134">**Crescimento por porcentagem (arquivo de log)**</span><span class="sxs-lookup"><span data-stu-id="bc31e-134">**Grow by percentage (log file)**</span></span>  
 <span data-ttu-id="bc31e-135">Especifique uma porcentagem para o crescimento do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="bc31e-135">Specify a percentage by which the log file can grow.</span></span>  
  
 <span data-ttu-id="bc31e-136">**Crescimento por tamanho (arquivo de log)**</span><span class="sxs-lookup"><span data-stu-id="bc31e-136">**Grow by size (log file)**</span></span>  
 <span data-ttu-id="bc31e-137">Especifique um número de megabytes para o crescimento do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="bc31e-137">Specify a number of megabytes by which the log file can grow.</span></span>  
  
  
