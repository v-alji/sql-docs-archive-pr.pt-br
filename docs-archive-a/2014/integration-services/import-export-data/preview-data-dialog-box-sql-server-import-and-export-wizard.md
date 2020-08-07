---
title: Caixa de diálogo Visualizar Dados (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.previewdata.f1
ms.assetid: 423ac26a-ba02-4fdf-88b4-07995fe4a97e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 17debc001d8ba7826fe845c006e944e5a3dc87a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575931"
---
# <a name="preview-data-dialog-box-sql-server-import-and-export-wizard"></a><span data-ttu-id="e1ff8-102">Caixa de diálogo Visualizar Dados (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e1ff8-102">Preview Data Dialog Box (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="e1ff8-103">Use a caixa de diálogo **Visualizar dados** para ver a consulta que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Assistente de importação e exportação enviará para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e1ff8-103">Use the **Preview Data** dialog box to see the query that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard will send to the data source.</span></span> <span data-ttu-id="e1ff8-104">Você também pode usar esta caixa de diálogo para visualizar até 200 linhas de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="e1ff8-104">You can also use this dialog box to preview up to 200 rows of sample data.</span></span>  
  
 <span data-ttu-id="e1ff8-105">Para saber mais sobre o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Assistente de importação e exportação do, consulte [SQL Server assistente de importação e exportação](import-and-export-data-with-the-sql-server-import-and-export-wizard.md)do.</span><span class="sxs-lookup"><span data-stu-id="e1ff8-105">To learn more about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="e1ff8-106">Para saber mais sobre as opções de inicialização do assistente e sobre as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e1ff8-106">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="e1ff8-107">O objetivo do Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="e1ff8-107">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="e1ff8-108">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="e1ff8-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="e1ff8-109">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="e1ff8-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="e1ff8-110">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e1ff8-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
 <span data-ttu-id="e1ff8-111">**Para abrir a caixa de diálogo Visualizar Dados**</span><span class="sxs-lookup"><span data-stu-id="e1ff8-111">**To open the Preview Data dialog box**</span></span>  
  
-   <span data-ttu-id="e1ff8-112">Na página **selecionar tabelas e exibições de origem** do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Assistente de importação e exportação do, clique em **Visualizar**.</span><span class="sxs-lookup"><span data-stu-id="e1ff8-112">On the **Select Source Tables and Views** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, click **Preview**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e1ff8-113">Opções</span><span class="sxs-lookup"><span data-stu-id="e1ff8-113">Options</span></span>  
 <span data-ttu-id="e1ff8-114">**Origem**</span><span class="sxs-lookup"><span data-stu-id="e1ff8-114">**Source**</span></span>  
 <span data-ttu-id="e1ff8-115">Exibe a consulta que o assistente enviará para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e1ff8-115">Displays the query that the wizard will send to the data source.</span></span>  
  
 <span data-ttu-id="e1ff8-116">**Grade de dados de exemplo**</span><span class="sxs-lookup"><span data-stu-id="e1ff8-116">**Sample data grid**</span></span>  
 <span data-ttu-id="e1ff8-117">Exibe até 200 linhas de dados de exemplo retornados pela consulta.</span><span class="sxs-lookup"><span data-stu-id="e1ff8-117">Displays up to 200 rows of sample data that the query returned.</span></span>  
  
  
