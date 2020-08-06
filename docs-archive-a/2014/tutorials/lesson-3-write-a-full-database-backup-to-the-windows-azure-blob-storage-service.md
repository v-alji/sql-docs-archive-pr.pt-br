---
title: 'Lição 3: gravar um backup de banco de dados completo no serviço de armazenamento de BLOBs do Azure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 454c8296-64e9-46ed-b141-5ebfbc8a4fe2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 17e7e6b608d248a48cde52f1107bb910f06d64ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678376"
---
# <a name="lesson-3-write-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="d9157-102">Lição 3: Gravar um backup de banco de dados completo no serviço de Armazenamento de Blobs</span><span class="sxs-lookup"><span data-stu-id="d9157-102">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>
  <span data-ttu-id="d9157-103">Esta lição demonstra o uso da instrução TSQL para executar um backup de banco de dados completo no serviço de armazenamento de BLOBs do Azure.</span><span class="sxs-lookup"><span data-stu-id="d9157-103">This lesson demonstrates the use of tsql statement to perform a full database backup to Azure Blob storage service.</span></span>  
  
## <a name="perform-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="d9157-104">Executar um backup de banco de dados completo para o serviço de armazenamento de BLOBs do Azure</span><span class="sxs-lookup"><span data-stu-id="d9157-104">Perform a Full Database Backup to the Azure Blob Storage Service</span></span>  
 <span data-ttu-id="d9157-105">Para criar um backup de banco de dados completo, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d9157-105">To create a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="d9157-106">Conecte-se ao [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9157-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="d9157-107">No **Pesquisador de Objetos**, conecte-se à instância do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9157-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="d9157-108">Na barra de menus Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="d9157-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="d9157-109">Copie e cole o exemplo a seguir na janela de consulta, modifique conforme necessário e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="d9157-109">Copy and paste the following example into the query window, modify as needed, and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE[AdventureWorks2012]   
    TO URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    /* URL includes the endpoint for the BLOB service, followed by the container name, and the name of the backup file*/   
    WITH CREDENTIAL = 'mycredential';  
    /* name of the credential you created in the previous step */   
    GO  
  
    ```  
  
5.  <span data-ttu-id="d9157-110">No Pesquisador de Objetos, conecte-se ao armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="d9157-110">In the object explorer, connect to Azure Storage.</span></span> <span data-ttu-id="d9157-111">Procurar o contêiner e os arquivos de backup recém-criados.</span><span class="sxs-lookup"><span data-stu-id="d9157-111">Browse to find the container and the newly created backup files.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="d9157-112">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="d9157-112">Next Lesson</span></span>  
 <span data-ttu-id="d9157-113">[Lição 4: executar uma restauração de um backup de banco de dados completo](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md).</span><span class="sxs-lookup"><span data-stu-id="d9157-113">[Lesson 4: Perform a Restore From a Full Database Backup](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md).</span></span>  
  
  
