---
title: Mover um banco de dados habilitado para FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], moving a FILESTREAM-enabled database
ms.assetid: dd4d270d-9283-431a-aa6b-e571fced1893
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79740ee86a89566113650865e3fd6ec54c7cb918
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678801"
---
# <a name="move-a-filestream-enabled-database"></a><span data-ttu-id="867a0-102">Mover um banco de dados habilitado para FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="867a0-102">Move a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="867a0-103">Este tópico mostra como mover um banco de dados habilitado para FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="867a0-103">This topic shows how to move a FILESTREAM-enabled database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="867a0-104">Os exemplos neste tópico requerem o banco de dados Archive que foi criado em [Criar um banco de dados habilitado para FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="867a0-104">The examples in this topic require the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
### <a name="to-move-a-filestream-enabled-database"></a><span data-ttu-id="867a0-105">Para mover um banco de dados habilitado para FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="867a0-105">To move a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="867a0-106">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique em **Nova Consulta** para abrir o Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="867a0-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="867a0-107">Copie o script [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir no Editor de Consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="867a0-107">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="867a0-108">Este script exibe o local dos arquivos físicos usados pelo banco de dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="867a0-108">This script displays the location of the physical database files that the FILESTREAM database uses.</span></span>  
  
    ```sql  
    USE Archive  
    GO  
    SELECT type_desc, name, physical_name from sys.database_files  
    ```  
  
3.  <span data-ttu-id="867a0-109">Copie o script [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir no Editor de Consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="867a0-109">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="867a0-110">Este código torna o banco de dados `Archive` offline.</span><span class="sxs-lookup"><span data-stu-id="867a0-110">This code takes the `Archive` database offline.</span></span>  
  
    ```sql  
    USE master  
    EXEC sp_detach_db Archive  
    GO  
    ```  
  
4.  <span data-ttu-id="867a0-111">Crie a pasta `C:\moved_location`e, em seguida, mova os arquivos e pastas listadas na etapa para ela.</span><span class="sxs-lookup"><span data-stu-id="867a0-111">Create the folder `C:\moved_location`, and then move the files and folders that are listed in step 2 into it.</span></span>  
  
5.  <span data-ttu-id="867a0-112">Copie o script [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir no Editor de Consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="867a0-112">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="867a0-113">Este script define o banco de dados `Archive` como online.</span><span class="sxs-lookup"><span data-stu-id="867a0-113">This script sets the `Archive` database online.</span></span>  
  
    ```sql  
    CREATE DATABASE Archive ON  
    PRIMARY ( NAME = Arch1,  
        FILENAME = 'c:\moved_location\archdat1.mdf'),  
    FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
        FILENAME = 'c:\moved_location\filestream1')  
    LOG ON  ( NAME = Archlog1,  
        FILENAME = 'c:\moved_location\archlog1.ldf')  
    FOR ATTACH  
    GO  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="867a0-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="867a0-114">See Also</span></span>  
 [<span data-ttu-id="867a0-115">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="867a0-115">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
