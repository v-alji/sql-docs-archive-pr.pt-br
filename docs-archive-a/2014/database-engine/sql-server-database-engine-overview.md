---
title: Mecanismo de Banco de Dados do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server]
- SQL Server Database Engine
ms.assetid: 65e2f424-1386-45a6-8912-bd053f434073
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a6c243115e940f7af085c0068d2ca5c277aa5162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569616"
---
# <a name="sql-server-database-engine"></a><span data-ttu-id="ffcc5-102">Mecanismo de Banco de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ffcc5-102">SQL Server Database Engine</span></span>
  <span data-ttu-id="ffcc5-103">O [!INCLUDE[ssDE](../includes/ssde-md.md)] é o serviço principal para armazenamento, processamento e segurança de dados.</span><span class="sxs-lookup"><span data-stu-id="ffcc5-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="ffcc5-104">O [!INCLUDE[ssDE](../includes/ssde-md.md)] fornece acesso controlado e processamento rápido de transações para atender aos requisitos dos mais exigentes aplicativos de consumo de dados dentro de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ffcc5-104">The [!INCLUDE[ssDE](../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications within your enterprise.</span></span>

 <span data-ttu-id="ffcc5-105">Use o [!INCLUDE[ssDE](../includes/ssde-md.md)] para criar bancos de dados relacionais para processamento de transações online ou dados de processamento analítico online.</span><span class="sxs-lookup"><span data-stu-id="ffcc5-105">Use the [!INCLUDE[ssDE](../includes/ssde-md.md)] to create relational databases for online transaction processing or online analytical processing data.</span></span> <span data-ttu-id="ffcc5-106">Isso inclui a criação de tabelas para armazenamento de dados e objetos de banco de dados, como índices, exibições e procedimentos armazenados para exibição, gerenciamento e segurança de dados.</span><span class="sxs-lookup"><span data-stu-id="ffcc5-106">This includes creating tables for storing data, and database objects such as indexes, views, and stored procedures for viewing, managing, and securing data.</span></span> <span data-ttu-id="ffcc5-107">Você pode usar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para gerenciar os objetos de banco de dados e o [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] para capturar eventos de servidor.</span><span class="sxs-lookup"><span data-stu-id="ffcc5-107">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to manage the database objects, and [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to capture server events.</span></span>

 <span data-ttu-id="ffcc5-108">**Procurar conteúdo por área** ![pequena pasta de arquivos ícone](../../2014/integration-services/media/filefolder-small.gif "Pequeno ícone de pasta de arquivos") [o que há de novo (mecanismo de banco de dados)](whats-new-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="ffcc5-108">**Browse Content by Area** ![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [What's New (Database Engine)](whats-new-in-sql-server-2016.md)</span></span>

 <span data-ttu-id="ffcc5-109">![Ícone de pasta de arquivos pequena](../../2014/integration-services/media/filefolder-small.gif "Pequeno ícone de pasta de arquivos") [SQL Server mecanismo de banco de dados compatibilidade com versões anteriores](sql-server-database-engine-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ffcc5-109">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Database Engine Backward Compatibility](sql-server-database-engine-backward-compatibility.md)</span></span>

 <span data-ttu-id="ffcc5-110">![Ícone de pasta de arquivos pequenos](../../2014/integration-services/media/filefolder-small.gif "Pequeno ícone de pasta de arquivos") [ferramentas de gerenciamento do SQL Server compatibilidade com versões anteriores](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ffcc5-110">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Management Tools Backward Compatibility](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span></span>

 <span data-ttu-id="ffcc5-111">![Ícone de pasta de arquivo pequeno](../../2014/integration-services/media/filefolder-small.gif "Pequeno ícone de pasta de arquivos") [recursos e tarefas do banco de dados](../../2014/database-engine/database-engine-features-and-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="ffcc5-111">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Database Features and Tasks](../../2014/database-engine/database-engine-features-and-tasks.md)</span></span>

 <span data-ttu-id="ffcc5-112">![Ícone de pasta de arquivo pequeno](../../2014/integration-services/media/filefolder-small.gif "Pequeno ícone de pasta de arquivos") [referência técnica](../../2014/database-engine/technical-reference-database-engine.md)</span><span class="sxs-lookup"><span data-stu-id="ffcc5-112">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Technical Reference](../../2014/database-engine/technical-reference-database-engine.md)</span></span>

 <span data-ttu-id="ffcc5-113">![Ícone de pasta de arquivos pequena](../../2014/integration-services/media/filefolder-small.gif "Pequeno ícone de pasta de arquivos") [referência de Transact-SQL](/sql/t-sql/language-reference)</span><span class="sxs-lookup"><span data-stu-id="ffcc5-113">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Transact-SQL Reference](/sql/t-sql/language-reference)</span></span>

 <span data-ttu-id="ffcc5-114">![Ícone de pasta de arquivo pequeno](../../2014/integration-services/media/filefolder-small.gif "Pequeno ícone de pasta de arquivos") [referência XQuery](/sql/xquery/xquery-language-reference-sql-server)</span><span class="sxs-lookup"><span data-stu-id="ffcc5-114">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [XQuery Reference](/sql/xquery/xquery-language-reference-sql-server)</span></span>

## <a name="see-also"></a><span data-ttu-id="ffcc5-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ffcc5-115">See Also</span></span>
 [<span data-ttu-id="ffcc5-116">Central de Recursos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ffcc5-116">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=219676)


