---
title: Instrução Create Table do SQL (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createtablesql.f1
ms.assetid: 0d6f6b3b-d023-4770-a8a9-65b2977c8d05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3fc2054711708a27691f2d7219c33749f11b977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575942"
---
# <a name="create-table-sql-statement-sql-server-import-and-export-wizard"></a><span data-ttu-id="31132-102">Instrução Create Table SQL (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31132-102">Create Table SQL Statement (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="31132-103">Use a caixa de diálogo **instrução SQL CREATE TABLE** para exibir a instrução que foi gerada automaticamente ou para modificá-la para suas finalidades.</span><span class="sxs-lookup"><span data-stu-id="31132-103">Use the **Create Table SQL Statement** dialog box to view the statement that was generated automatically, or to modify it for your purposes.</span></span> <span data-ttu-id="31132-104">Se você modificar essa instrução, também poderá fazer alterações associadas ao mapeamento de coluna e poderá manter a instrução SQL editada manualmente.</span><span class="sxs-lookup"><span data-stu-id="31132-104">If you modify this statement, you may also have to make associated changes to column mapping, and you will have to maintain the edited SQL statement manually thereafter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="31132-105">gera uma instrução CREATE TABLE padrão baseada na fonte de dados conectada.</span><span class="sxs-lookup"><span data-stu-id="31132-105">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="31132-106">A instrução CREATE TABLE padrão não incluirá o atributo FILESTREAM mesmo que a tabela de origem inclua uma coluna com o atributo FILESTREAM declarado.</span><span class="sxs-lookup"><span data-stu-id="31132-106">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="31132-107">Para executar um componente [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] com o atributo FILESTREAM, implemente primeiro o armazenamento FILESTREAM no banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="31132-107">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="31132-108">Em seguida, adicione o atributo FILESTREAM à instrução CREATE TABLE na caixa de diálogo **Criar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="31132-108">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="31132-109">Para obter mais informações, consulte [Dados de blob &#40;objeto binário grande&#41; &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="31132-109">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="31132-110">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="31132-110">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="31132-111">Para saber mais sobre as opções de inicialização do assistente, bem como as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="31132-111">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="31132-112">O objetivo do Assistente de Importação e Exportação do SQL Server é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="31132-112">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="31132-113">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="31132-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="31132-114">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="31132-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="31132-115">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="31132-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="31132-116">Opções</span><span class="sxs-lookup"><span data-stu-id="31132-116">Options</span></span>  
 <span data-ttu-id="31132-117">**Instrução SQL**</span><span class="sxs-lookup"><span data-stu-id="31132-117">**SQL statement**</span></span>  
 <span data-ttu-id="31132-118">Exiba a instrução SQL gerada automaticamente e permite que ela seja editada.</span><span class="sxs-lookup"><span data-stu-id="31132-118">Displays the auto-generated SQL statement and lets it be edited.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31132-119">Se desejar incluir um retorno de carro na instrução SQL, pressione CTRL+ENTER.</span><span class="sxs-lookup"><span data-stu-id="31132-119">If you want to include a carriage return in the SQL statement, press CTRL+ENTER.</span></span> <span data-ttu-id="31132-120">Se você pressionar somente ENTER, a caixa de diálogo será fechada.</span><span class="sxs-lookup"><span data-stu-id="31132-120">If you press only ENTER, the dialog box closes.</span></span>  
  
 <span data-ttu-id="31132-121">**AutoGenerate**</span><span class="sxs-lookup"><span data-stu-id="31132-121">**Autogenerate**</span></span>  
 <span data-ttu-id="31132-122">Restaure a instrução SQL padrão, caso ela tenha sido modificada, clicando em **Gerar Automaticamente**.</span><span class="sxs-lookup"><span data-stu-id="31132-122">Restore the default SQL statement, if you have modified it, by clicking **Autogenerate**.</span></span>  
  
  
