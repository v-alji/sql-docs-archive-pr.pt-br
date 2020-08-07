---
title: MSSQLSERVER_8992 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8992 (Database Engine error)
ms.assetid: 68467e6a-09d8-478f-8bd9-3bb09453ada3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adcf914accab43202cf148fe852b334c9b078287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584142"
---
# <a name="mssqlserver_8992"></a><span data-ttu-id="310b2-102">MSSQLSERVER_8992</span><span class="sxs-lookup"><span data-stu-id="310b2-102">MSSQLSERVER_8992</span></span>
    
## <a name="details"></a><span data-ttu-id="310b2-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="310b2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="310b2-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="310b2-104">Product Name</span></span>|<span data-ttu-id="310b2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="310b2-105">SQL Server</span></span>|  
|<span data-ttu-id="310b2-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="310b2-106">Event ID</span></span>|<span data-ttu-id="310b2-107">8992</span><span class="sxs-lookup"><span data-stu-id="310b2-107">8992</span></span>|  
|<span data-ttu-id="310b2-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="310b2-108">Event Source</span></span>|<span data-ttu-id="310b2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="310b2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="310b2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="310b2-110">Component</span></span>|<span data-ttu-id="310b2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="310b2-111">SQLEngine</span></span>|  
|<span data-ttu-id="310b2-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="310b2-112">Symbolic Name</span></span>|<span data-ttu-id="310b2-113">DBCC3_CHECK_CATALOG</span><span class="sxs-lookup"><span data-stu-id="310b2-113">DBCC3_CHECK_CATALOG</span></span>|  
|<span data-ttu-id="310b2-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="310b2-114">Message Text</span></span>|<span data-ttu-id="310b2-115">Verifique a mensagem do catálogo ERROR Nível LEVEL Estado STATE: MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="310b2-115">Check Catalog Msg ERROR Level LEVEL State STATE: MESSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="310b2-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="310b2-116">Explanation</span></span>  
 <span data-ttu-id="310b2-117">DBCC CHECKCATALOG ou DBCC CHECKDB localizou uma inconsistência nas tabelas de metadados do sistema para o objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="310b2-117">DBCC CHECKCATALOG or DBCC CHECKDB found an inconsistency in the system metadata tables for the specified object.</span></span> <span data-ttu-id="310b2-118">Isto é, há uma inconsistência entre a ID do objeto registrado e o objeto especificado na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="310b2-118">That is, there is an inconsistency between the recorded object ID and the object specified in error message.</span></span>  
  
 <span data-ttu-id="310b2-119">Esse erro pode ocorrer quando uma ou mais tabelas do sistema foram atualizadas manualmente de uma maneira que cria uma inconsistência nos metadados do sistema.</span><span class="sxs-lookup"><span data-stu-id="310b2-119">This error can occur when one or more system tables has been manually updated in a way that creates an inconsistency in the system metadata.</span></span> <span data-ttu-id="310b2-120">Por exemplo, um usuário pode ter excluído manualmente um objeto da tabela **sysobjects** sem remover as linhas associadas em outras tabelas como **sysindexes** e **syscolumns**.</span><span class="sxs-lookup"><span data-stu-id="310b2-120">For example, a user may have manually deleted an object from the **sysobjects** table without removing associated rows in other tables such as **sysindexes** and **syscolumns**.</span></span>  
  
 <span data-ttu-id="310b2-121">Esse erro pode ocorrer ao executar DBCC CHECKDB em um banco de dados que foi atualizado do SQL Server 2000 para o SQL Server 2005 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="310b2-121">This error can occur when running DBCC CHECKDB against a database that has been upgraded from SQL Server 2000 to SQL Server 2005 or later.</span></span> <span data-ttu-id="310b2-122">No SQL Server 2000, o DBCC CHECKDB não incluía a funcionalidade DBCC CHECKCATALOG, portanto o erro não seria capturado antes da atualização a menos que DBCC CHECKCATALOG fosse executado especificamente no banco de dados no SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="310b2-122">In SQL Server 2000, DBCC CHECKDB did not include DBCC CHECKCATALOG functionality, so the error would not be caught before upgrade unless DBCC CHECKCATALOG was specifically executed against the database in SQL Server 2000.</span></span>  
  
 <span data-ttu-id="310b2-123">Você pode consultar quaisquer um dos erros a seguir em conjunto com o erro 8992:</span><span class="sxs-lookup"><span data-stu-id="310b2-123">You may see any of the following errors in conjunction with error 8992:</span></span>  
  
 <span data-ttu-id="310b2-124">Mensagem 3851 - Linha inválida (%ls) encontrada na tabela do sistema sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="310b2-124">Msg 3851 - An invalid row (%ls) was found in the system table sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="310b2-125">Mensagem 3852 - Linha (%ls) em sys.%ls%ls sem linha correspondente (%ls) em sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="310b2-125">Msg 3852 - Row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="310b2-126">3853 - Atributo (%ls) da linha (%ls) em sys.%ls%ls sem linha correspondente (%ls) em sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="310b2-126">3853 - Attribute (%ls) of row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="310b2-127">3854 - Atributo (%ls) da linha (%ls) em sys.%ls%ls com linha correspondente (%ls) inválida em sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="310b2-127">3854 - Attribute (%ls) of row (%ls) in sys.%ls%ls has a matching row (%ls) in sys.%ls%ls that is invalid.</span></span>  
  
 <span data-ttu-id="310b2-128">3855 - Atributo (%ls) existente sem uma linha (%ls) em sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="310b2-128">3855 - Attribute (%ls) exists without a row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="310b2-129">3856 - O atributo (%ls) existe, mas não deveria, para a linha (%ls) em sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="310b2-129">3856 - Attribute (%ls) exists but should not for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="310b2-130">3857 - O atributo (%ls) é necessário, mas não existe para a linha (%ls) em sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="310b2-130">3857 - The attribute (%ls) is required but is missing for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="310b2-131">3858 - O atributo (%ls) da linha (%ls) em sys.%ls%ls tem um valor inválido.</span><span class="sxs-lookup"><span data-stu-id="310b2-131">3858 - The attribute (%ls) of row (%ls) in sys.%ls%ls has an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="310b2-132">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="310b2-132">User Action</span></span>  
  
### <a name="drop-and-re-create-the-specified-object"></a><span data-ttu-id="310b2-133">Descartar e recriar o objeto especificado</span><span class="sxs-lookup"><span data-stu-id="310b2-133">Drop and Re-create the Specified Object</span></span>  
 <span data-ttu-id="310b2-134">Se possível, descarte e recrie o objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="310b2-134">If possible, drop and recreate the specified object.</span></span> <span data-ttu-id="310b2-135">Por exemplo, se o objeto for um procedimento armazenado ou um tipo definido pelo usuário, a recriação do objeto poderá resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="310b2-135">For example, if the object is a stored procedure or user-defined type, recreating the object may resolve the problem.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="310b2-136">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="310b2-136">Restore from Backup</span></span>  
 <span data-ttu-id="310b2-137">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="310b2-137">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span> <span data-ttu-id="310b2-138">Essa ação só será aplicável se o backup não contiver o erro de metadados.</span><span class="sxs-lookup"><span data-stu-id="310b2-138">This action is only applicable if the backup does not contain the metadata error.</span></span>  
  
### <a name="export-the-data-to-a-new-database"></a><span data-ttu-id="310b2-139">Exportar os dados para um novo banco de dados</span><span class="sxs-lookup"><span data-stu-id="310b2-139">Export the Data to a New Database</span></span>  
 <span data-ttu-id="310b2-140">Se o backup também contiver a inconsistência de metadados, você precisará criar um novo banco de dados e exportar o conteúdo do banco de dados existente para o novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="310b2-140">If the backup also contains the metadata inconsistency, you need to create a new database and export the contents of the existing database to the new database.</span></span>  
  
### <a name="dbcc-checkdb-cannot-repair-this-error"></a><span data-ttu-id="310b2-141">DBCC CHECKDB não pode reparar este erro</span><span class="sxs-lookup"><span data-stu-id="310b2-141">DBCC CHECKDB Cannot Repair This Error</span></span>  
 <span data-ttu-id="310b2-142">Esse erro não pode ser reparado.</span><span class="sxs-lookup"><span data-stu-id="310b2-142">This error cannot be repaired.</span></span>  <span data-ttu-id="310b2-143">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="310b2-143">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
### <a name="do-not-manually-update-system-tables"></a><span data-ttu-id="310b2-144">Não atualizar manualmente tabelas do sistema</span><span class="sxs-lookup"><span data-stu-id="310b2-144">Do Not Manually Update System Tables</span></span>  
 <span data-ttu-id="310b2-145">Não faça atualizações manuais em tabelas do sistema.</span><span class="sxs-lookup"><span data-stu-id="310b2-145">Do not make manual updates to system tables.</span></span> <span data-ttu-id="310b2-146">O SQL Server não oferece suporte a alterações manuais em bancos de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="310b2-146">SQL Server does not support any manual changes to system databases.</span></span> <span data-ttu-id="310b2-147">Se você atualizar uma tabela do sistema em um banco de dados do SQL Server, dois eventos (ID de evento 17659 e ID de evento 3859) serão registrados em log.</span><span class="sxs-lookup"><span data-stu-id="310b2-147">If you update a system table in a SQL Server database, two events (event ID 17659 and event ID 3859) are logged.</span></span> <span data-ttu-id="310b2-148">Para obter mais informações, consulte o artigo KB 2688307, "ID de evento 17659 e ID de evento 3859 são registrados em log quando você atualiza tabelas do sistema em um banco de dados do SQL Server".</span><span class="sxs-lookup"><span data-stu-id="310b2-148">For more information, see KB article 2688307, "Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="310b2-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="310b2-149">See Also</span></span>  
 [<span data-ttu-id="310b2-150">A ID de evento 17659 e a ID de evento 3859 são registradas em log quando você atualiza tabelas do sistema em um banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="310b2-150">Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database</span></span>](https://support.microsoft.com/kb/2688307/EN-US)  
  
  
