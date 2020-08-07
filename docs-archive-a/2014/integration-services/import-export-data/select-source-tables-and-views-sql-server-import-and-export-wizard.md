---
title: Selecionar tabelas de origem e exibições (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.selectsourcetablesandviews.f1
ms.assetid: f60e1a19-2ea6-403c-89ab-3e60ac533ea0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e18f9f34db7965033d4e1e62964060a26404a45e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575922"
---
# <a name="select-source-tables-and-views-sql-server-import-and-export-wizard"></a><span data-ttu-id="6ecb3-102">Selecionar tabelas de origem e exibições (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6ecb3-102">Select Source Tables and Views (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="6ecb3-103">Use a página **selecionar tabelas e exibições de origem** para especificar as tabelas e exibições a serem copiadas da fonte de dados para o destino.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-103">Use the **Select Source Tables and Views** page to specify the tables and views to be copied from the data source to the destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ecb3-104">Não é necessário copiar todas as colunas em uma tabela ao selecionar a opção Cópia de Tabela.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-104">You do not have to copy all the columns in a table when you select the Table Copy option.</span></span> <span data-ttu-id="6ecb3-105">Depois de selecionar uma tabela de destino, clique em editar mapeamentos para exibir a caixa de diálogo **mapeamentos de coluna** .</span><span class="sxs-lookup"><span data-stu-id="6ecb3-105">After selecting a destination table, click Edit Mappings to display the **Column Mappings** dialog box.</span></span> <span data-ttu-id="6ecb3-106">Selecione **\<ignore>** na coluna **destino** da caixa de diálogo **mapeamentos de coluna** para as colunas que você deseja ignorar.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-106">Select **\<ignore>** in the **Destination** column of the **Column Mappings** dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="6ecb3-107">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="6ecb3-107">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="6ecb3-108">Para saber mais sobre as opções de inicialização do assistente e sobre as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="6ecb3-108">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="6ecb3-109">O objetivo do Assistente de Importação e Exportação do SQL Server é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-109">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="6ecb3-110">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-110">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="6ecb3-111">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-111">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="6ecb3-112">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="6ecb3-112">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6ecb3-113">Opções</span><span class="sxs-lookup"><span data-stu-id="6ecb3-113">Options</span></span>  
  
### <a name="tables-and-views-list"></a><span data-ttu-id="6ecb3-114">Lista de tabelas e exibições</span><span class="sxs-lookup"><span data-stu-id="6ecb3-114">Tables and views List</span></span>  
 <span data-ttu-id="6ecb3-115">**Origem**</span><span class="sxs-lookup"><span data-stu-id="6ecb3-115">**Source**</span></span>  
 <span data-ttu-id="6ecb3-116">Usando as caixas de seleção, selecione da lista de tabelas e exibições disponíveis para copiar para o destino.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-116">Using the check boxes, select from the list of available tables and views to copy to the destination.</span></span> <span data-ttu-id="6ecb3-117">Se uma tabela ou exibição de origem foi selecionada e nenhuma outra ação foi efetuada, o esquema e os dados da origem serão copiados sem qualquer alteração.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-117">If you select a source table or view and perform no other action, the schema and data from the source are copied without changes.</span></span>  
  
 <span data-ttu-id="6ecb3-118">**Destino**</span><span class="sxs-lookup"><span data-stu-id="6ecb3-118">**Destination**</span></span>  
 <span data-ttu-id="6ecb3-119">Selecione uma tabela de destino da lista para cada tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-119">Select a destination table from the list for each source table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ecb3-120">Se o assistente for interrompido neste momento para a criação de uma tabela de destino no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ou de qualquer outra ferramenta, a nova tabela não ficará visível imediatamente na lista de tabelas de destino disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-120">If you pause at this point in the wizard to create a destination table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] or another tool, the new table is not immediately visible in the list of available destination tables.</span></span> <span data-ttu-id="6ecb3-121">Para atualizar a lista de tabelas de destino, volte duas páginas para a página **escolher um destino** , selecione novamente o banco de dados de destino e, em seguida, avance novamente para **selecionar tabelas e exibições de origem**.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-121">To refresh the list of destination tables, step back two pages to the **Choose a Destination** page, re-select the destination database, then step forward again to the **Select Source Tables and Views**.</span></span>  
  
### <a name="other-options"></a><span data-ttu-id="6ecb3-122">Outras opções</span><span class="sxs-lookup"><span data-stu-id="6ecb3-122">Other Options</span></span>  
 <span data-ttu-id="6ecb3-123">**Editar mapeamentos**</span><span class="sxs-lookup"><span data-stu-id="6ecb3-123">**Edit mappings**</span></span>  
 <span data-ttu-id="6ecb3-124">Use a caixa de diálogo **mapeamentos de coluna** para especificar as colunas de destino para receber os dados de origem.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-124">Use the **Column Mappings** dialog box to specify destination columns to receive the source data.</span></span> <span data-ttu-id="6ecb3-125">Você pode copiar apenas um subconjunto de colunas selecionando \<ignore> na coluna **destino** da caixa de diálogo **mapeamentos de coluna** para colunas que você deseja ignorar.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-125">You can copy only a subset of columns by selecting \<ignore> in the **Destination** column of the **Column Mappings** dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="6ecb3-126">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="6ecb3-126">**Preview**</span></span>  
 <span data-ttu-id="6ecb3-127">Visualize os dados de origem na caixa de diálogo **Visualizar dados** para verificá-los antes de executar a importação ou exportação.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-127">Preview source data in the **Preview Data** dialog box to verify it before performing the import or export.</span></span> <span data-ttu-id="6ecb3-128">A caixa de diálogo **Visualizar dados** exibe até 200 linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-128">The **Preview Data** dialog box displays up to 200 rows of data.</span></span>  
  
 <span data-ttu-id="6ecb3-129">Após visualizar os dados, é possível alterar as opções selecionadas para a origem e destino de dados.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-129">After previewing the data, you might want to change the options that you have selected for the data source and destination.</span></span> <span data-ttu-id="6ecb3-130">Para fazer essas alterações, na página **Selecionar Tabelas e Exibições de Origem**, clique em **Voltar** para retornar às páginas anteriores nas quais é possível alterar as seleções.</span><span class="sxs-lookup"><span data-stu-id="6ecb3-130">To make these changes, on the **Select Source Tables and Views** page, click **Back** to return to previous pages where you can change your selections.</span></span>  
  
  
