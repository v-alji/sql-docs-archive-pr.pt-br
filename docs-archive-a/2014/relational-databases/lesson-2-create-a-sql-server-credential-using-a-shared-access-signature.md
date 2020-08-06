---
title: 'Lição 3: criar uma credencial de SQL Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 29e57ebd-828f-4dff-b473-c10ab0b1c597
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 808438e544e3beb18b2e2afa9c399b5666277483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684727"
---
# <a name="lesson-3-create-a-sql-server-credential"></a><span data-ttu-id="3fda8-102">Lição 3: Criar uma credencial do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3fda8-102">Lesson 3: Create a SQL Server Credential</span></span>
  <span data-ttu-id="3fda8-103">Nesta lição, você criará uma credencial para armazenar informações de segurança usadas para acessar a conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="3fda8-103">In this lesson, you will create a credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="3fda8-104">Uma credencial do SQL Server é um objeto usado para armazenar as informações de autenticação necessárias para se conectar a um recurso fora do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3fda8-104">A SQL Server credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span> <span data-ttu-id="3fda8-105">A credencial armazena o caminho de URI do contêiner de armazenamento e os valores de chave de assinatura de acesso compartilhado.</span><span class="sxs-lookup"><span data-stu-id="3fda8-105">The credential stores the URI path of the storage container and the shared access signature key values.</span></span> <span data-ttu-id="3fda8-106">Para cada contêiner de armazenamento usado por um arquivo de dados ou de log, você deve criar uma Credencial do SQL Server cujo nome corresponda ao caminho do contêiner.</span><span class="sxs-lookup"><span data-stu-id="3fda8-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span>  
  
 <span data-ttu-id="3fda8-107">Para obter informações gerais sobre credenciais, consulte [credenciais &#40;Mecanismo de Banco de Dados&#41;](security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="3fda8-107">For general information about credentials, see [Credentials &#40;Database Engine&#41;](security/authentication-access/credentials-database-engine.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3fda8-108">Os requisitos para criar uma credencial de SQL Server descrito abaixo são específicos para o recurso [SQL Server arquivos de dados no Azure](databases/sql-server-data-files-in-microsoft-azure.md) .</span><span class="sxs-lookup"><span data-stu-id="3fda8-108">The requirements for creating a SQL Server credential described below are specific to the [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md) feature.</span></span> <span data-ttu-id="3fda8-109">Para obter informações sobre como criar credenciais para processos de backup no armazenamento do Azure, consulte [Lesson 2: Create a SQL Server Credential](../tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="3fda8-109">For information on creating credentials for backup processes in Azure storage, see [Lesson 2: Create a SQL Server Credential](../tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
 <span data-ttu-id="3fda8-110">Para criar uma Credencial do SQL Server, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3fda8-110">To create a SQL Server Credential, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3fda8-111">Conecte-se ao SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="3fda8-111">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="3fda8-112">No Pesquisador de Objetos, conecte-se à instância do Mecanismo de Banco de Dados instalado.</span><span class="sxs-lookup"><span data-stu-id="3fda8-112">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="3fda8-113">Na barra de ferramentas Padrão, clique em Nova Consulta.</span><span class="sxs-lookup"><span data-stu-id="3fda8-113">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="3fda8-114">Copie e cole o exemplo a seguir na janela de consulta, e modifique conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3fda8-114">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="3fda8-115">A instrução a seguir criará uma credencial SQL Server para armazenar o certificado de acesso compartilhado do seu contêiner de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="3fda8-115">The following statement will create a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
    ```sql  
  
    USE master  
    CREATE CREDENTIAL credentialname - this name should match the container path and it must start with https.   
       WITH IDENTITY='SHARED ACCESS SIGNATURE', -- this is a mandatory string and do not change it.   
       SECRET = 'sharedaccesssignature' -- this is the shared access signature key that you obtained in Lesson 2.   
    GO  
  
    ```  
  
     <span data-ttu-id="3fda8-116">Para obter informações detalhadas, consulte [criar credencial &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) em manuais online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3fda8-116">For detailed information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) in SQL Server Books Online.</span></span>  
  
5.  <span data-ttu-id="3fda8-117">Para ver todas as credenciais disponíveis, você pode executar a instrução a seguir na janela de consulta:</span><span class="sxs-lookup"><span data-stu-id="3fda8-117">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
    ```sql  
    SELECT * from sys.credentials  
    ```  
  
     <span data-ttu-id="3fda8-118">Para obter mais informações sobre sys. Credentials, consulte [Sys. credentials &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) em manuais online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3fda8-118">For more information on sys.credentials, see [sys.credentials &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="3fda8-119">**Próxima lição:**</span><span class="sxs-lookup"><span data-stu-id="3fda8-119">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="3fda8-120">Lição 4: Criar um banco de dados no Armazenamento do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="3fda8-120">Lesson 4: Create a database in Azure Storage</span></span>](lesson-3-database-backup-to-url.md)  
  
  
