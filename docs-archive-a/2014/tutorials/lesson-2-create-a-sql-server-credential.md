---
title: 'Lição 2: criar uma credencial de SQL Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 64f8805c-1ddc-4c96-a47c-22917d12e1ab
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e8b13c8d4d9e5937064cef5503ec64bfd6e4a2d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685998"
---
# <a name="lesson-2-create-a-sql-server-credential"></a><span data-ttu-id="ea250-102">Lição 2: Criar uma credencial do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ea250-102">Lesson 2: Create a SQL Server Credential</span></span>
  <span data-ttu-id="ea250-103">**Credencial:** Uma credencial do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] é um objeto usado para armazenar as informações de autenticação necessárias para se conectar a um recurso fora do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ea250-103">**Credential:** A [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="ea250-104">Aqui, os [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] processos de backup e restauração usam a credencial para autenticar o serviço de armazenamento de BLOBs do Azure.</span><span class="sxs-lookup"><span data-stu-id="ea250-104">Here, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="ea250-105">A Credencial armazena o nome da conta de armazenamento e os valores de **access key** da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="ea250-105">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="ea250-106">Depois que a credencial for criada, ela deverá ser especificada na opção WITH CREDENTIAL ao emitir instruções BACKUP/RESTORE.</span><span class="sxs-lookup"><span data-stu-id="ea250-106">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="ea250-107">Para obter mais informações sobre como exibir, copiar ou gerar novamente as **access keys**da conta de armazenamento, consulte [Chaves de acesso da conta de armazenamento](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="ea250-107">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="ea250-108">Para obter informações gerais sobre credenciais, consulte [credenciais](../relational-databases/security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="ea250-108">For general information about credentials, see [Credentials](../relational-databases/security/authentication-access/credentials-database-engine.md).</span></span>  
  
 <span data-ttu-id="ea250-109">Para obter informações, em outros exemplos em que as credenciais são usadas, consulte [criar um proxy de SQL Server Agent](../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="ea250-109">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ea250-110">Os requisitos para criar uma credencial de SQL Server descrito abaixo são específicos para SQL Server processos de backup ([SQL Server Backup para URL](../relational-databases/backup-restore/sql-server-backup-to-url.md)e [SQL Server Backup gerenciado para o Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span><span class="sxs-lookup"><span data-stu-id="ea250-110">The requirements for creating a SQL Server credential described below are specific to SQL Server backup processes ([SQL Server Backup to URL](../relational-databases/backup-restore/sql-server-backup-to-url.md), and [SQL Server Managed  Backup to Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span></span> <span data-ttu-id="ea250-111">O SQL Server, ao acessar o armazenamento do Azure para gravar ou ler backups, usa o nome da conta de armazenamento e as informações da tecla de acesso.</span><span class="sxs-lookup"><span data-stu-id="ea250-111">SQL Server, when accessing Azure storage to write or read backups uses the storage account name and access key information.</span></span>  <span data-ttu-id="ea250-112">Para obter mais informações sobre como criar credenciais para armazenar arquivos de banco de dados no armazenamento do Azure, consulte [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)</span><span class="sxs-lookup"><span data-stu-id="ea250-112">For more information on creating credentials for storing database files in Azure storage, see [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)</span></span>  
  
## <a name="create-a-sql-server-credential"></a><span data-ttu-id="ea250-113">Criar uma credencial do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ea250-113">Create a SQL Server Credential</span></span>  
 <span data-ttu-id="ea250-114">Para criar uma credencial do SQL Server, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ea250-114">To create a SQL Server Credential, use the following steps:</span></span>  
  
1.  <span data-ttu-id="ea250-115">Conecte-se ao SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="ea250-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="ea250-116">No Pesquisador de Objetos, conecte-se à instância do Mecanismo de Banco de Dados que tem o banco de dados AdventureWorks2012 instalado, ou use o banco de dados que você pretende usar neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="ea250-116">In Object Explorer, connect to the instance of Database Engine that has AdventureWorks2012 database installed, or use your own database you plan to use for this tutorial.</span></span>  
  
3.  <span data-ttu-id="ea250-117">Na barra de ferramentas **Padrão** , clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ea250-117">On the **Standard** tool bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="ea250-118">Copie e cole o exemplo a seguir na janela de consulta, e modifique conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ea250-118">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account (See Lesson 1)   
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account (See Lesson 1)  
  
    ```  
  
     <span data-ttu-id="ea250-119">![mapeando a conta de armazenamento para as credenciais do sql](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "mapeando a conta de armazenamento para as credenciais do sql")</span><span class="sxs-lookup"><span data-stu-id="ea250-119">![mapping storage account to sql credentials](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
5.  <span data-ttu-id="ea250-120">Verifique a instrução T-SQL e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="ea250-120">Verify the T-SQL statement and click **Execute**.</span></span>  
  
 <span data-ttu-id="ea250-121">Para obter mais informações sobre o serviço de armazenamento de BLOBs do Azure para conceitos e requisitos de backup, consulte [SQL Server Backup e restauração com o serviço de armazenamento de BLOBs do Azure](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="ea250-121">For more information about the Azure Blob storage service for backup concepts and requirements, see [SQL Server Backup and Restore with Azure Blob Storage Service](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="ea250-122">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="ea250-122">Next Lesson</span></span>  
 <span data-ttu-id="ea250-123">[Lição 3: gravar um backup de banco de dados completo no serviço de armazenamento de BLOBs do Azure](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="ea250-123">[Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span></span>  
  
  
