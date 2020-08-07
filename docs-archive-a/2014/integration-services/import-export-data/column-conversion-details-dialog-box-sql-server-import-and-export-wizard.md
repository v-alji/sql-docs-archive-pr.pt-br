---
title: Caixa de diálogo Detalhes da Conversão de Coluna (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.issuedetails.f1
ms.assetid: e2d00a39-dfbd-4821-a4d8-a5bd1164ed4d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9207e76191060c56acad37db734827579a83aae0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575948"
---
# <a name="column-conversion-details-dialog-box-sql-server-import-and-export-wizard"></a><span data-ttu-id="4e3b3-102">Caixa de diálogo Detalhes da Conversão de Coluna (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4e3b3-102">Column Conversion Details Dialog Box (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="4e3b3-103">Use a caixa de diálogo **detalhes de conversão de coluna** para examinar informações de conversão detalhadas sobre uma coluna individual.</span><span class="sxs-lookup"><span data-stu-id="4e3b3-103">Use the **Column Conversion Details** dialog box to review detailed conversion information about an individual column.</span></span> <span data-ttu-id="4e3b3-104">Essas informações de conversão contêm o tipo de dados da coluna na origem e no destino, além da conversão a ser realizada pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="4e3b3-104">This conversion information contains the column's data type at the source and the destination, and the conversion that the wizard will perform.</span></span> <span data-ttu-id="4e3b3-105">Essa página também relaciona os arquivos de mapeamento de tipo de dados usados pelo assistente para determinar as conversões de tipo de dados necessárias.</span><span class="sxs-lookup"><span data-stu-id="4e3b3-105">This page also lists the data type mapping files that the wizard uses to determine the data type conversions that are required.</span></span> <span data-ttu-id="4e3b3-106">O [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instala esses tipos de dados com o mapeamento de arquivos durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="4e3b3-106">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installs these data type mapping files during setup.</span></span>  
  
 <span data-ttu-id="4e3b3-107">**Para abrir a caixa de diálogo Detalhes da Conversão de Coluna**</span><span class="sxs-lookup"><span data-stu-id="4e3b3-107">**To open the Column Conversion Details dialog box**</span></span>  
  
1.  <span data-ttu-id="4e3b3-108">Na página **examinar problemas de tipo de dados** do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Assistente de importação e exportação do, na lista **tabela** , selecione uma tabela.</span><span class="sxs-lookup"><span data-stu-id="4e3b3-108">On the **Review Data Type Issues** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, in the **Table** list, select a table.</span></span>  
  
2.  <span data-ttu-id="4e3b3-109">Na lista **mapeamento de tipo de dados** , clique duas vezes na linha que contém a coluna para a qual você deseja exibir os detalhes da conversão.</span><span class="sxs-lookup"><span data-stu-id="4e3b3-109">In the **Data type mapping** list, double-click the row that contains the column for which you want to view conversion details.</span></span>  
  
 <span data-ttu-id="4e3b3-110">Para saber mais sobre o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Assistente de importação e exportação do, consulte [SQL Server assistente de importação e exportação](import-and-export-data-with-the-sql-server-import-and-export-wizard.md)do.</span><span class="sxs-lookup"><span data-stu-id="4e3b3-110">To learn more about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="4e3b3-111">Para saber mais sobre as opções de inicialização do assistente e sobre as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4e3b3-111">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="4e3b3-112">O objetivo do Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="4e3b3-112">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="4e3b3-113">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="4e3b3-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="4e3b3-114">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="4e3b3-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="4e3b3-115">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4e3b3-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
  
