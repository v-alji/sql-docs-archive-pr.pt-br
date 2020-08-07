---
title: 'Lição 7: mover seus arquivos de dados para o armazenamento do Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 26aa534a-afe7-4a14-b99f-a9184fc699bd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 753863d7b8b8d8fa554f1579bee6837c525efd9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576372"
---
# <a name="lesson-7-move-your-data-files-to-azure-storage"></a><span data-ttu-id="cfb25-102">Lição 7: Migrar seus arquivos de dados para o Armazenamento do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="cfb25-102">Lesson 7: Move your data files to Azure Storage</span></span>
  <span data-ttu-id="cfb25-103">Nesta lição, você aprenderá a mover seus arquivos de dados para o armazenamento do Azure (mas não sua instância de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="cfb25-103">In this lesson, you will learn how to move your data files to Azure Storage (but not your SQL Server instance).</span></span> <span data-ttu-id="cfb25-104">Para acompanhar esta lição, você não precisará concluir as lições 4, 5 e 6.</span><span class="sxs-lookup"><span data-stu-id="cfb25-104">To follow this lesson, you do not need to complete Lesson 4, 5, and 6.</span></span>  
  
 <span data-ttu-id="cfb25-105">Para mover seus arquivos de dados para o armazenamento do Azure, você pode usar a `ALTER DATABASE` instrução, pois ajuda a alterar o local dos arquivos de dados.</span><span class="sxs-lookup"><span data-stu-id="cfb25-105">To move your data files to Azure Storage, you can use the `ALTER DATABASE` statement as it helps to change the location of the data files.</span></span>  
  
 <span data-ttu-id="cfb25-106">Esta lição supõe que você já concluiu as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="cfb25-106">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="cfb25-107">Você tem uma conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="cfb25-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="cfb25-108">Você criou um contêiner em sua conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="cfb25-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="cfb25-109">Você criou uma política em um contêiner com direitos de leitura, gravação e lista.</span><span class="sxs-lookup"><span data-stu-id="cfb25-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="cfb25-110">Você também gerou uma chave de SAS.</span><span class="sxs-lookup"><span data-stu-id="cfb25-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="cfb25-111">Você criou uma credencial do SQL Server no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="cfb25-111">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="cfb25-112">Em seguida, use as seguintes etapas para mover seus arquivos de dados para o armazenamento do Azure:</span><span class="sxs-lookup"><span data-stu-id="cfb25-112">Next, use the following steps to move your data files to Azure Storage:</span></span>  
  
1.  <span data-ttu-id="cfb25-113">Primeiro, crie um banco de dados de teste no computador de origem e adicione alguns dados a ele.</span><span class="sxs-lookup"><span data-stu-id="cfb25-113">First, create a test database in the source machine and add some data to it.</span></span>  
  
    ```sql  
  
    USE master;   
    CREATE DATABASE TestDB1Alter;   
    GO   
    USE TestDB1Alter;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
2.  <span data-ttu-id="cfb25-114">Execute o código a seguir:</span><span class="sxs-lookup"><span data-stu-id="cfb25-114">Run the following code:</span></span>  
  
    ```sql  
  
    -- In the following statement, modify the path specified in FILENAME to   
    -- the new location of the file in Azure Storage container.   
    ALTER DATABASE TestDB1Alter    
        MODIFY FILE ( NAME = TestDB1Alter,    
                    FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontaineralter/TestDB1AlterData.mdf');   
    GO  
  
    ```  
  
3.  <span data-ttu-id="cfb25-115">Quando você executar isso, verá esta mensagem: "o arquivo" TestDB1Alter "foi modificado no catálogo do sistema.</span><span class="sxs-lookup"><span data-stu-id="cfb25-115">When you run this, you will see this message: "The file "TestDB1Alter" has been modified in the system catalog.</span></span> <span data-ttu-id="cfb25-116">O novo caminho será usado na próxima vez que o banco de dados for iniciado. "</span><span class="sxs-lookup"><span data-stu-id="cfb25-116">The new path will be used the next time the database is started."</span></span>  
  
4.  <span data-ttu-id="cfb25-117">Em seguida, defina o banco de dados offline.</span><span class="sxs-lookup"><span data-stu-id="cfb25-117">Then, set the database offline.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET OFFLINE;   
    GO  
  
    ```  
  
5.  <span data-ttu-id="cfb25-118">Agora, você precisa copiar os arquivos de dados para o armazenamento do Azure usando um dos seguintes métodos: [ferramenta AzCopy](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [colocar página](https://msdn.microsoft.com/library/azure/ee691975.aspx), [referência da biblioteca de cliente de armazenamento](https://msdn.microsoft.com/library/azure/dn261237.aspx)ou uma ferramenta de Gerenciador de armazenamento de terceiros.</span><span class="sxs-lookup"><span data-stu-id="cfb25-118">Now, you need to copy the data files to Azure Storage by using one of the following methods: [AzCopy Tool](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [Put Page](https://msdn.microsoft.com/library/azure/ee691975.aspx), [Storage Client Library Reference](https://msdn.microsoft.com/library/azure/dn261237.aspx), or a third-party storage explorer tool.</span></span>  
  
     <span data-ttu-id="cfb25-119">**Importante:** Ao usar esse novo aprimoramento, sempre certifique-se de criar um blob de páginas não um blob de blocos.</span><span class="sxs-lookup"><span data-stu-id="cfb25-119">**Important:** When using this new enhancement, always make sure that you create a page blob not a block blob.</span></span>  
  
6.  <span data-ttu-id="cfb25-120">Em seguida, defina o banco de dados online.</span><span class="sxs-lookup"><span data-stu-id="cfb25-120">Then, set the database online.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET ONLINE;   
    GO  
  
    ```  
  
 <span data-ttu-id="cfb25-121">**Próxima lição:**</span><span class="sxs-lookup"><span data-stu-id="cfb25-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="cfb25-122">Lição 8. Restaurar um banco de dados no armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="cfb25-122">Lesson 8. Restore a database to Azure Storage</span></span>](lesson-7-restore-a-database-to-a-point-in-time.md)  
  
  
