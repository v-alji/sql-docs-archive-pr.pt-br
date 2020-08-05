---
title: 'Lição 4: executar uma restauração de um backup completo de banco de dados | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 580f76e6-9802-4abc-9043-db6de592c733
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9906ea14c2f76a49644a8f76fbd894adf8b9d500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572875"
---
# <a name="lesson-4-perform-a-restore-from-a-full-database-backup"></a><span data-ttu-id="19bd6-102">Lição 4: Executar uma restauração de um backup de banco de dados completo</span><span class="sxs-lookup"><span data-stu-id="19bd6-102">Lesson 4: Perform a Restore From a Full Database Backup</span></span>
  <span data-ttu-id="19bd6-103">Esta lição demonstra o uso de uma instrução tsql para executar uma restauração a partir de um backup de banco de dados completo criado na lição anterior.</span><span class="sxs-lookup"><span data-stu-id="19bd6-103">This lesson demonstrates the use of a tsql statement to perform a restore from a full database backup created in the previous lesson.</span></span>  
  
## <a name="perform-a-restore-of-a-database-backup"></a><span data-ttu-id="19bd6-104">Executar uma restauração a partir de um backup de banco de dados</span><span class="sxs-lookup"><span data-stu-id="19bd6-104">Perform a Restore of a Database Backup</span></span>  
 <span data-ttu-id="19bd6-105">Para restaurar um backup de banco de dados completo, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="19bd6-105">To restore a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="19bd6-106">Conecte-se ao [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19bd6-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="19bd6-107">No **Pesquisador de Objetos**, conecte-se à instância do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19bd6-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="19bd6-108">Na barra de menus Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="19bd6-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="19bd6-109">Copie e cole o exemplo a seguir na janela de consulta, e modifique conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="19bd6-109">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks2012   
    FROM URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    WITH CREDENTIAL = 'mycredential';  
    , STATS = 5 - use this to see monitor the progress  
    GO  
  
    ```  
  
5.  <span data-ttu-id="19bd6-110">Verifique a instrução T-SQL e clique em **executar**</span><span class="sxs-lookup"><span data-stu-id="19bd6-110">Verify the T-SQL statement and click **Execute**</span></span>  
  
### <a name="return-to-tutorials-portal"></a><span data-ttu-id="19bd6-111">Retorne ao portal Tutoriais</span><span class="sxs-lookup"><span data-stu-id="19bd6-111">Return to Tutorials Portal</span></span>  
 <span data-ttu-id="19bd6-112">[Tutorial: SQL Server Backup e restauração para o serviço de armazenamento de BLOBs do Azure](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="19bd6-112">[Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span></span>  
  
  
