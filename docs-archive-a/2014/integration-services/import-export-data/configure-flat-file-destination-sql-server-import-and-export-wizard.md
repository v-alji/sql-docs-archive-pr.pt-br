---
title: Configurar destino de arquivo simples (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.configureflatfiledest.f1
ms.assetid: 318e8da0-37d3-46cd-943a-fc5d66aad93a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2af8a1653d9a1aef0828aa112a25825ed23b8bf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575944"
---
# <a name="configure-flat-file-destination-sql-server-import-and-export-wizard"></a><span data-ttu-id="40e09-102">Configurar Destino Arquivo Simples (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="40e09-102">Configure Flat File Destination (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="40e09-103">Use a página **Configurar destino de arquivo simples** para especificar opções de formatação para o arquivo simples de destino e para visualizar os resultados antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="40e09-103">Use the **Configure Flat File Destination** page to specify formatting options for the destination flat file, and to preview results before continuing.</span></span>  
  
 <span data-ttu-id="40e09-104">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="40e09-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="40e09-105">Para saber mais sobre as opções de inicialização do assistente, bem como as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="40e09-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="40e09-106">O objetivo do Assistente de Importação e Exportação do SQL Server é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="40e09-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="40e09-107">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="40e09-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="40e09-108">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="40e09-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="40e09-109">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="40e09-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="40e09-110">Opções</span><span class="sxs-lookup"><span data-stu-id="40e09-110">Options</span></span>  
 <span data-ttu-id="40e09-111">**Arquivo simples de origem**</span><span class="sxs-lookup"><span data-stu-id="40e09-111">**Source flat file**</span></span>  
 <span data-ttu-id="40e09-112">O nome do arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="40e09-112">The name of the destination file.</span></span>  
  
 <span data-ttu-id="40e09-113">**Delimitador de linha**</span><span class="sxs-lookup"><span data-stu-id="40e09-113">**Row delimiter**</span></span>  
 <span data-ttu-id="40e09-114">Selecione na lista de delimitadores para linhas.</span><span class="sxs-lookup"><span data-stu-id="40e09-114">Select from the list of delimiters for rows.</span></span>  
  
|<span data-ttu-id="40e09-115">Valor</span><span class="sxs-lookup"><span data-stu-id="40e09-115">Value</span></span>|<span data-ttu-id="40e09-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="40e09-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="40e09-117">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="40e09-117">**{CR}{LF}**</span></span>|<span data-ttu-id="40e09-118">A linha é delimitada por uma combinação de retorno de carro e avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="40e09-118">The row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="40e09-119">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="40e09-119">**{CR}**</span></span>|<span data-ttu-id="40e09-120">A linha é delimitada por um retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="40e09-120">The row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="40e09-121">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="40e09-121">**{LF}**</span></span>|<span data-ttu-id="40e09-122">A linha é delimitada por uma alimentação de linha.</span><span class="sxs-lookup"><span data-stu-id="40e09-122">The row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="40e09-123">**Ponto-e-vírgula {;}**</span><span class="sxs-lookup"><span data-stu-id="40e09-123">**Semicolon {;}**</span></span>|<span data-ttu-id="40e09-124">A linha é delimitada por um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="40e09-124">The row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="40e09-125">**Dois-pontos {:}**</span><span class="sxs-lookup"><span data-stu-id="40e09-125">**Colon {:}**</span></span>|<span data-ttu-id="40e09-126">A linha é delimitada por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="40e09-126">The row is delimited by a colon.</span></span>|  
|<span data-ttu-id="40e09-127">**Vírgula {,}**</span><span class="sxs-lookup"><span data-stu-id="40e09-127">**Comma {,}**</span></span>|<span data-ttu-id="40e09-128">A linha é delimitada por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="40e09-128">The row is delimited by a comma.</span></span>|  
|<span data-ttu-id="40e09-129">**Tabulação {t}**</span><span class="sxs-lookup"><span data-stu-id="40e09-129">**Tab {t}**</span></span>|<span data-ttu-id="40e09-130">A linha é delimitada por uma tabulação.</span><span class="sxs-lookup"><span data-stu-id="40e09-130">The row is delimited by a tab.</span></span>|  
|<span data-ttu-id="40e09-131">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="40e09-131">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="40e09-132">A linha é delimitada por uma barra vertical.</span><span class="sxs-lookup"><span data-stu-id="40e09-132">The row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="40e09-133">**Delimitador de coluna**</span><span class="sxs-lookup"><span data-stu-id="40e09-133">**Column delimiter**</span></span>  
 <span data-ttu-id="40e09-134">Selecione na lista de delimitadores para colunas.</span><span class="sxs-lookup"><span data-stu-id="40e09-134">Select from the list of delimiters for columns.</span></span>  
  
|<span data-ttu-id="40e09-135">Valor</span><span class="sxs-lookup"><span data-stu-id="40e09-135">Value</span></span>|<span data-ttu-id="40e09-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="40e09-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="40e09-137">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="40e09-137">**{CR}{LF}**</span></span>|<span data-ttu-id="40e09-138">As colunas são delimitadas por uma combinação de retorno de carro e alimentação de linha.</span><span class="sxs-lookup"><span data-stu-id="40e09-138">The columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="40e09-139">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="40e09-139">**{CR}**</span></span>|<span data-ttu-id="40e09-140">As colunas são delimitadas por um retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="40e09-140">The columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="40e09-141">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="40e09-141">**{LF}**</span></span>|<span data-ttu-id="40e09-142">As colunas são delimitadas por uma alimentação de linha.</span><span class="sxs-lookup"><span data-stu-id="40e09-142">The columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="40e09-143">**Ponto-e-vírgula {;}**</span><span class="sxs-lookup"><span data-stu-id="40e09-143">**Semicolon {;}**</span></span>|<span data-ttu-id="40e09-144">As colunas são delimitadas por um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="40e09-144">The columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="40e09-145">**Dois-pontos {:}**</span><span class="sxs-lookup"><span data-stu-id="40e09-145">**Colon {:}**</span></span>|<span data-ttu-id="40e09-146">As colunas são delimitadas por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="40e09-146">The columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="40e09-147">**Vírgula {,}**</span><span class="sxs-lookup"><span data-stu-id="40e09-147">**Comma {,}**</span></span>|<span data-ttu-id="40e09-148">As colunas são delimitadas por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="40e09-148">The columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="40e09-149">**Tabulação {t}**</span><span class="sxs-lookup"><span data-stu-id="40e09-149">**Tab {t}**</span></span>|<span data-ttu-id="40e09-150">As colunas são delimitadas por uma tabulação.</span><span class="sxs-lookup"><span data-stu-id="40e09-150">The columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="40e09-151">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="40e09-151">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="40e09-152">As colunas são delimitadas por uma barra vertical.</span><span class="sxs-lookup"><span data-stu-id="40e09-152">The columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="40e09-153">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="40e09-153">**Preview**</span></span>  
 <span data-ttu-id="40e09-154">Exibir na caixa de diálogo **Visualizar dados** os resultados das opções de formatação selecionadas para o arquivo simples de destino.</span><span class="sxs-lookup"><span data-stu-id="40e09-154">View in the **Preview Data** dialog box the results of the selected formatting options for the destination flat file.</span></span>  
  
 <span data-ttu-id="40e09-155">**Editar transformação**</span><span class="sxs-lookup"><span data-stu-id="40e09-155">**Edit transform**</span></span>  
 <span data-ttu-id="40e09-156">Exclua linhas, acrescente linhas e configure colunas no arquivo de destino usando a caixa de diálogo **mapeamentos de coluna** .</span><span class="sxs-lookup"><span data-stu-id="40e09-156">Delete rows, append rows, and configure columns in the destination file by using the **Column Mappings** dialog box.</span></span>  
  
  
