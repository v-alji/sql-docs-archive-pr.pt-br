---
title: Banco de dados de recursos| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system objects [SQL Server]
- read-only databases
- mssqlsystemresource.mdf file
- Resource database [SQL Server]
ms.assetid: d592b2b4-bc36-4eb9-9385-8fe4dff0dced
author: stevestein
ms.author: sstein
ms.openlocfilehash: cca2f9e1ff6069a608beb1df1880b37e15f4e869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573098"
---
# <a name="resource-database"></a><span data-ttu-id="58a32-102">Banco de dados de recursos</span><span class="sxs-lookup"><span data-stu-id="58a32-102">Resource Database</span></span>
  <span data-ttu-id="58a32-103">O banco de dados Recurso é um banco de dados somente leitura que contém todos os objetos de sistema inclusos no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58a32-103">The Resource database is a read-only database that contains all the system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="58a32-104">objetos do sistema como sys.objects, são fisicamente persistentes no banco de dados Resource, mas aparecem logicamente no esquema sys de cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="58a32-104">system objects, such as sys.objects, are physically persisted in the Resource database, but they logically appear in the sys schema of every database.</span></span> <span data-ttu-id="58a32-105">O banco de dados Recurso não contém dados de usuário ou metadados de usuário.</span><span class="sxs-lookup"><span data-stu-id="58a32-105">The Resource database does not contain user data or user metadata.</span></span>  
  
 <span data-ttu-id="58a32-106">O banco de dados Recurso torna a atualização para uma nova versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] um procedimento mais fácil e mais rápido.</span><span class="sxs-lookup"><span data-stu-id="58a32-106">The Resource database makes upgrading to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] an easier and faster procedure.</span></span> <span data-ttu-id="58a32-107">Em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a atualização exigia remover e criar objetos do sistema.</span><span class="sxs-lookup"><span data-stu-id="58a32-107">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], upgrading required dropping and creating system objects.</span></span> <span data-ttu-id="58a32-108">Como o arquivo de banco de dados Recurso contém todos os objetos de sistema, agora, uma atualização é obtida simplesmente pela cópia do único arquivo de banco de dados Recurso no servidor local.</span><span class="sxs-lookup"><span data-stu-id="58a32-108">Because the Resource database file contains all system objects, an upgrade is now accomplished simply by copying the single Resource database file to the local server.</span></span>  
  
## <a name="physical-properties-of-resource"></a><span data-ttu-id="58a32-109">Propriedades físicas de Resource</span><span class="sxs-lookup"><span data-stu-id="58a32-109">Physical Properties of Resource</span></span>  
 <span data-ttu-id="58a32-110">Os nomes dos arquivos físicos do banco de dados do Recurso são mssqlsystemresource.mdf e mssqlsystemresource.ldf.</span><span class="sxs-lookup"><span data-stu-id="58a32-110">The physical file names of the Resource database are mssqlsystemresource.mdf and mssqlsystemresource.ldf.</span></span> <span data-ttu-id="58a32-111">Esses arquivos estão localizados em \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\ e não devem ser movidos.</span><span class="sxs-lookup"><span data-stu-id="58a32-111">These files are located in \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\ and should not be moved.</span></span> <span data-ttu-id="58a32-112">Cada instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tem um e apenas um arquivo mssqlsystemresource.mdf associado, e as instâncias não compartilham esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="58a32-112">Each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one and only one associated mssqlsystemresource.mdf file, and instances do not share this file.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="58a32-113">Atualizações e service packs às vezes fornecem um novo banco de dados recurso que é instalado na pasta BINN.</span><span class="sxs-lookup"><span data-stu-id="58a32-113">Upgrades and service packs sometimes provide a new resource database which is installed to the BINN folder.</span></span> <span data-ttu-id="58a32-114">Alterar o local do banco de dados do recurso não é suportado nem recomendado.</span><span class="sxs-lookup"><span data-stu-id="58a32-114">Changing the location of the resource database is not supported or recommended.</span></span>  
  
## <a name="backing-up-and-restoring-the-resource-database"></a><span data-ttu-id="58a32-115">Fazendo backup e restaurando o banco de dados de recursos</span><span class="sxs-lookup"><span data-stu-id="58a32-115">Backing Up and Restoring the Resource Database</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="58a32-116">não pode fazer backup do banco de dados Resource.</span><span class="sxs-lookup"><span data-stu-id="58a32-116">cannot back up the Resource database.</span></span> <span data-ttu-id="58a32-117">Você pode executar seu próprio backup baseado em arquivo ou baseado em disco ao tratar o arquivo mssqlsystemresource.mdf como se ele fosse um arquivo binário (.EXE), em vez de um arquivo de banco de dados, mas você não pode usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para restaurar seus backups.</span><span class="sxs-lookup"><span data-stu-id="58a32-117">You can perform your own file-based or a disk-based backup by treating the mssqlsystemresource.mdf file as if it were a binary (.EXE) file, rather than a database file, but you cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to restore your backups.</span></span> <span data-ttu-id="58a32-118">Só é possível restaurar uma cópia de backup do mssqlsystemresource.mdf manualmente, e você deve ter cuidado para não sobrescrever o atual banco de dados  Recurso com uma versão desatualizada ou potencialmente insegura.</span><span class="sxs-lookup"><span data-stu-id="58a32-118">Restoring a backup copy of mssqlsystemresource.mdf can only be done manually, and you must be careful not to overwrite the current Resource database with an out-of-date or potentially insecure version.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="58a32-119">Depois de restaurar um backup do mssqlsystemresource.mdf, você deve reaplicar qualquer atualização subsequente.</span><span class="sxs-lookup"><span data-stu-id="58a32-119">After restoring a backup of mssqlsystemresource.mdf, you must reapply any subsequent updates.</span></span>  
  
## <a name="accessing-the-resource-database"></a><span data-ttu-id="58a32-120">Acessando o banco de dados Resource</span><span class="sxs-lookup"><span data-stu-id="58a32-120">Accessing the Resource Database</span></span>  
 <span data-ttu-id="58a32-121">O banco de dados Recurso só deve ser modificado por ou sob a orientação de um especialista do Serviço de Suporte Técnico da Microsoft (CSS).</span><span class="sxs-lookup"><span data-stu-id="58a32-121">The Resource database should only be modified by or at the direction of a Microsoft Customer Support Services (CSS) specialist.</span></span> <span data-ttu-id="58a32-122">A ID do banco de dados de  Recursos será sempre 32767.</span><span class="sxs-lookup"><span data-stu-id="58a32-122">The ID of the Resource database is always 32767.</span></span> <span data-ttu-id="58a32-123">Outros valores importantes associados ao banco de dados de Recursos são o número da versão e a última vez em que o banco de dados foi atualizado.</span><span class="sxs-lookup"><span data-stu-id="58a32-123">Other important values associated with the Resource database are the version number and the last time that the database was updated.</span></span>  
  
 <span data-ttu-id="58a32-124">**Para determinar o número de versão do banco de dados** Resource **, use**:</span><span class="sxs-lookup"><span data-stu-id="58a32-124">**To determine the version number of the** Resource **database, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceVersion');  
GO  
```  
  
 <span data-ttu-id="58a32-125">**Para determinar quando o banco de dados** Resource **foi atualizado pela última vez, use**:</span><span class="sxs-lookup"><span data-stu-id="58a32-125">**To determine when the** Resource **database was last updated, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceLastUpdateDateTime');  
GO  
```  
  
 <span data-ttu-id="58a32-126">**Para acessar definições SQL dos objetos de sistema, utilize a função OBJECT_DEFINITION:**</span><span class="sxs-lookup"><span data-stu-id="58a32-126">**To access SQL definitions of system objects, use the OBJECT_DEFINITION function:**</span></span>  
  
```  
SELECT OBJECT_DEFINITION(OBJECT_ID('sys.objects'));  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="58a32-127">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="58a32-127">Related Content</span></span>  
 [<span data-ttu-id="58a32-128">Bancos de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="58a32-128">System Databases</span></span>](system-databases.md)  
  
 [<span data-ttu-id="58a32-129">Conexão de diagnóstico para administradores de banco de dados</span><span class="sxs-lookup"><span data-stu-id="58a32-129">Diagnostic Connection for Database Administrators</span></span>](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md)  
  
 [<span data-ttu-id="58a32-130">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="58a32-130">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
 [<span data-ttu-id="58a32-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="58a32-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
  
 [<span data-ttu-id="58a32-132">Iniciar o SQL Server no modo de usuário único</span><span class="sxs-lookup"><span data-stu-id="58a32-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
