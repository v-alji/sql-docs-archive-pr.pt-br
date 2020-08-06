---
title: Copiar bancos de dados para outros servidores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- servers [SQL Server], copying databases between
- bulk exporting [SQL Server], between servers
- database copying [SQL Server]
- migrating databases [SQL Server]
- moving databases
- copying databases
- bulk importing [SQL Server], between servers
ms.assetid: 978406d6-a3c8-4902-b1f4-4ced75234be5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bcde6185f25129596b4be7a150d4ee230c54c1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680476"
---
# <a name="copy-databases-to-other-servers"></a><span data-ttu-id="c185a-102">Copiar bancos de dados em outros servidores</span><span class="sxs-lookup"><span data-stu-id="c185a-102">Copy Databases to Other Servers</span></span>
  <span data-ttu-id="c185a-103">Às vezes é útil copiar um banco de dados de um computador em outro, seja para testar, verificar a consistência, desenvolver software, executar relatórios, criar um banco de dados espelho, ou, possivelmente, para tornar o banco de dados disponível para operações da ramificação remota.</span><span class="sxs-lookup"><span data-stu-id="c185a-103">It is sometimes useful to copy a database from one computer to another, whether for testing, checking consistency, developing software, running reports, creating a mirror database, or, possibly, to make the database available to remote-branch operations.</span></span>  
  
 <span data-ttu-id="c185a-104">Há vários modos de copiar um banco de dados:</span><span class="sxs-lookup"><span data-stu-id="c185a-104">There are several ways to copy a database:</span></span>  
  
-   <span data-ttu-id="c185a-105">Usando o Assistente para Copiar Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="c185a-105">Using the Copy Database Wizard</span></span>  
  
     <span data-ttu-id="c185a-106">Você pode usar o Assistente para Copiar Banco de Dados para copiar ou mover bancos de dados entre servidores ou para atualizar um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="c185a-106">You can use the Copy Database Wizard to copy or move databases between servers or to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to a later version.</span></span> <span data-ttu-id="c185a-107">Para obter mais informações, consulte [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c185a-107">For more information, see [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span></span>  
  
-   <span data-ttu-id="c185a-108">Restaurando um backup de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c185a-108">Restoring a database backup</span></span>  
  
     <span data-ttu-id="c185a-109">Para copiar um banco de dados inteiro, você pode usar as instruções BACKUP e RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c185a-109">To copy an entire database, you can use the BACKUP and RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="c185a-110">Normalmente, a restauração de um backup completo de um banco de dados é usada para copiar o banco de dados de um computador para outro por uma variedade de razões.</span><span class="sxs-lookup"><span data-stu-id="c185a-110">Typically, restoring a full backup of a database is used to copy the database from one computer to another for a variety of reasons.</span></span> <span data-ttu-id="c185a-111">Para obter informações sobre como usar o backup e a restauração para copiar um banco de dados, veja [Copiar bancos de dados com backup e restauração](copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="c185a-111">For information on using backup and restore to copy a database, see [Copy Databases with Backup and Restore](copy-databases-with-backup-and-restore.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c185a-112">Para definir um banco de dados espelho para espelhamento de banco de dados, é necessário restaurar o banco de dados sobre o servidor espelho por meio de RESTORE DATABASE *<database_name>* WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="c185a-112">To set up a mirror database for database mirroring, you must restore the database onto the mirror server by using RESTORE DATABASE *<database_name>* WITH NORECOVERY.</span></span> <span data-ttu-id="c185a-113">Para obter mais informações, veja [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c185a-113">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="c185a-114">Usando o Assistente para Gerar Scripts para publicar bancos de dados</span><span class="sxs-lookup"><span data-stu-id="c185a-114">Using the Generate Scripts Wizard to publish databases</span></span>  
  
     <span data-ttu-id="c185a-115">Você pode usar o Assistente para Gerar Scripts para transferir um banco de dados de um computador local para um provedor de hospedagem na Web.</span><span class="sxs-lookup"><span data-stu-id="c185a-115">You can use the Generate Scripts Wizard to transfer a database from a local computer to a Web hosting provider.</span></span> <span data-ttu-id="c185a-116">Para obter mais informações, veja [Assistente para Gerar e Publicar Scripts](../scripting/generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c185a-116">For more information, see [Generate and Publish Scripts Wizard](../scripting/generate-and-publish-scripts-wizard.md).</span></span>  
  
  
