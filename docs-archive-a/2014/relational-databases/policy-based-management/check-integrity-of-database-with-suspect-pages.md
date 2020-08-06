---
title: Verificar a integridade do banco de dados com páginas suspeitas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3b1ec9fe-f6c5-46f7-aa63-6e671be1572d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cc1f87917c78f34ec7722fa21a1a67fda40a8c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678726"
---
# <a name="check-integrity-of-database-with-suspect-pages"></a><span data-ttu-id="ec14b-102">Verificar a integridade do banco de dados com páginas suspeitas</span><span class="sxs-lookup"><span data-stu-id="ec14b-102">Check Integrity of Database with Suspect Pages</span></span>
  <span data-ttu-id="ec14b-103">Esta regra verifica os bancos de dados de usuários que têm o status do banco de dados definido como suspeito.</span><span class="sxs-lookup"><span data-stu-id="ec14b-103">This rule checks for user databases that have the database status set to suspect.</span></span> <span data-ttu-id="ec14b-104">Quando o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] lê uma página do banco de dados que contém um erro 824, a página é considerada suspeita, sua ID é registrada na tabela suspect_pages do msdb e o banco de dados que a contém é definido como suspeito.</span><span class="sxs-lookup"><span data-stu-id="ec14b-104">When the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] reads a database page that contains an 824 error, the page is considered suspect, its page ID is recorded in the suspect_pages table in msdb, and the database that contains the page is set to suspect.</span></span>  
  
 <span data-ttu-id="ec14b-105">O erro 824 indica que um erro de consistência lógico foi detectado durante uma operação de leitura.</span><span class="sxs-lookup"><span data-stu-id="ec14b-105">Error 824 indicates that a logical consistency error was detected during a read operation.</span></span> <span data-ttu-id="ec14b-106">Esse erro frequentemente indica a corrupção de dados causada por um componente de subsistema de E/S defeituoso.</span><span class="sxs-lookup"><span data-stu-id="ec14b-106">This error frequently indicates data corruption caused by a faulty I/O subsystem component.</span></span> <span data-ttu-id="ec14b-107">Este é um erro grave que ameaça a integridade do banco de dados e deve ser corrigido imediatamente.</span><span class="sxs-lookup"><span data-stu-id="ec14b-107">This is a severe error condition that threatens database integrity and must be corrected immediately.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="ec14b-108">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="ec14b-108">Best Practices Recommendations</span></span>  
  
-   <span data-ttu-id="ec14b-109">Revise o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para obter os detalhes do erro 824 para esse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ec14b-109">Review the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the details of the 824 error for this database.</span></span>  
  
-   <span data-ttu-id="ec14b-110">Execute uma verificação de consistência completa do banco de dados ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="ec14b-110">Complete a full database consistency check ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).</span></span>  
  
-   <span data-ttu-id="ec14b-111">Implemente as ações de usuário definidas em [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397).</span><span class="sxs-lookup"><span data-stu-id="ec14b-111">Implement the user actions that are defined in [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397).</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="ec14b-112">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="ec14b-112">For More Information</span></span>  
 [<span data-ttu-id="ec14b-113">Gerenciar a tabela suspect_pages &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec14b-113">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
