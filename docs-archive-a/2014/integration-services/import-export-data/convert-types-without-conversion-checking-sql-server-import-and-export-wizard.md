---
title: Converter tipos sem verificação de conversão (SQL Server assistente de importação e exportação) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.nomappingfile.f1
ms.assetid: 87d9d3e5-477f-4117-a37f-bff53ea3e14d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3874bcad23994fdcf69ade948239760d5c871917
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575941"
---
# <a name="convert-types-without-conversion-checking-sql-server-import-and-export-wizard"></a><span data-ttu-id="06778-102">Converter tipos sem verificação de conversão (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="06778-102">Convert Types without Conversion Checking (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="06778-103">Use a página **converter tipos sem verificação de conversão** para examinar os mapeamentos que o assistente executa quando o assistente não consegue localizar um ou mais [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] arquivos de conversão e mapeamento de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="06778-103">Use the **Convert Types without Conversion Checking** page to review the mappings that the wizard performs when the wizard cannot locate one or more of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type conversion and mapping files.</span></span> <span data-ttu-id="06778-104">Esta página inclui informações que ajudam a identificar o(s) arquivo(s) perdido(s).</span><span class="sxs-lookup"><span data-stu-id="06778-104">This page includes information that helps you identify the missing file or files.</span></span>  
  
 <span data-ttu-id="06778-105">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="06778-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="06778-106">Para saber mais sobre as opções de inicialização do assistente e sobre as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="06778-106">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="06778-107">O objetivo do Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="06778-107">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="06778-108">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="06778-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="06778-109">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="06778-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="06778-110">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="06778-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
  
