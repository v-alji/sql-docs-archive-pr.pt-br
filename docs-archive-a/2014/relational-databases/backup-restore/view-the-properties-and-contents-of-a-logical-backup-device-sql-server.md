---
title: Exibir as propriedades e o conteúdo de um dispositivo de backup lógico (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- displaying backup content
- viewing backup content
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
- backing up databases [SQL Server], properties
- displaying backup properties
- backup devices [SQL Server], viewing information
- viewing backup properties
- database backups [SQL Server], properties
ms.assetid: 3a309074-e816-454d-b6c3-fcfdde0cbf74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f2bdf41e3dbda079e3627ff7a7c1c3c78103b728
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681698"
---
# <a name="view-the-properties-and-contents-of-a-logical-backup-device-sql-server"></a><span data-ttu-id="194f0-102">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="194f0-102">View the Properties and Contents of a Logical Backup Device (SQL Server)</span></span>
  <span data-ttu-id="194f0-103">Este tópico descreve como exibir as propriedades e o conteúdo de um dispositivo de backup lógico no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="194f0-103">This topic describes how to view the properties and contents of a logical backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="194f0-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="194f0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="194f0-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="194f0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="194f0-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="194f0-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="194f0-107">**Para exibir as propriedades e o conteúdo de um dispositivo de backup lógico usando:**</span><span class="sxs-lookup"><span data-stu-id="194f0-107">**To view the properties and contents of a logical backup device, using:**</span></span>  
  
     [<span data-ttu-id="194f0-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="194f0-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="194f0-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="194f0-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="194f0-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="194f0-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="194f0-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="194f0-111">Security</span></span>  
 <span data-ttu-id="194f0-112">Para obter informações sobre segurança, veja [RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="194f0-112">For information about security, see [RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="194f0-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="194f0-113">Permissions</span></span>  
 <span data-ttu-id="194f0-114">No [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e em versões posteriores, a obtenção de informações sobre um conjunto ou dispositivo de backup exige a permissão CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="194f0-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="194f0-115">Para obter mais informações, veja [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="194f0-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="194f0-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="194f0-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="194f0-117">Para exibir as propriedades e o conteúdo de um dispositivo de backup lógico</span><span class="sxs-lookup"><span data-stu-id="194f0-117">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="194f0-118">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="194f0-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="194f0-119">Expanda **Objetos de Servidor**e expanda **Dispositivos de Backup**.</span><span class="sxs-lookup"><span data-stu-id="194f0-119">Expand **Server Objects**, and expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="194f0-120">Clique no dispositivo e clique com o botão direito do mouse em **Propriedades**, isso abre a caixa de diálogo **Dispositivo de Backup** .</span><span class="sxs-lookup"><span data-stu-id="194f0-120">Click the device and right-click **Properties**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="194f0-121">A página **Geral** exibe o nome de dispositivo e destino que são um dispositivo de fita ou um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="194f0-121">The **General** page displays the device name and destination, which is either a tape device or file path.</span></span>  
  
5.  <span data-ttu-id="194f0-122">No painel **Selecionar uma Página** , clique em **Conteúdo da Mídia**.</span><span class="sxs-lookup"><span data-stu-id="194f0-122">In the **Select a Page** pane, click **Media Contents**.</span></span>  
  
6.  <span data-ttu-id="194f0-123">O painel à direita exibe os seguintes painéis de propriedades:</span><span class="sxs-lookup"><span data-stu-id="194f0-123">The right-hand pane displays in the following properties panels:</span></span>  
  
    -   <span data-ttu-id="194f0-124">**Mídia**</span><span class="sxs-lookup"><span data-stu-id="194f0-124">**Media**</span></span>  
  
         <span data-ttu-id="194f0-125">Informações de sequência de mídia (o número de sequência de mídia, o número de sequência da família e o identificador de espelho, se houver) e a data e hora de criação da mídia.</span><span class="sxs-lookup"><span data-stu-id="194f0-125">Media sequence information (the media sequence number, the family sequence number, and the mirror identifier, if any) and the media creation date and time.</span></span>  
  
    -   <span data-ttu-id="194f0-126">**Conjunto de mídias**</span><span class="sxs-lookup"><span data-stu-id="194f0-126">**Media set**</span></span>  
  
         <span data-ttu-id="194f0-127">Informações do conjunto de mídias: nome e descrição do conjunto de mídias, se houver, e o número de famílias no conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="194f0-127">Media set information: the media set name and description, if any, and the number of families in the media set.</span></span>  
  
7.  <span data-ttu-id="194f0-128">A grade **Conjuntos de backups** exibe informações sobre o conteúdo do conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="194f0-128">The **Backup sets** grid displays information about the contents of the media set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="194f0-129">Para obter mais informações, consulte a [página Conteúdo da Mídia](backup-device-media-contents-page.md).</span><span class="sxs-lookup"><span data-stu-id="194f0-129">For more information, see [Media Contents Page](backup-device-media-contents-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="194f0-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="194f0-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="194f0-131">Para exibir as propriedades e o conteúdo de um dispositivo de backup lógico</span><span class="sxs-lookup"><span data-stu-id="194f0-131">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="194f0-132">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="194f0-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="194f0-133">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="194f0-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="194f0-134">Use a instrução [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="194f0-134">Use the [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) statement.</span></span> <span data-ttu-id="194f0-135">Este exemplo retorna informações sobre o dispositivo de backup lógico `AdvWrks2008R2Backup` .</span><span class="sxs-lookup"><span data-stu-id="194f0-135">This example returns information about the `AdvWrks2008R2Backup` logical backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE LABELONLY  
   FROM AdvWrks2008R2Backup ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="194f0-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="194f0-136">See Also</span></span>  
 <span data-ttu-id="194f0-137">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="194f0-137">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="194f0-138">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="194f0-138">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="194f0-139">[conjunto de backup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="194f0-139">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="194f0-140">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="194f0-140">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="194f0-141">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="194f0-141">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="194f0-142">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="194f0-142">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 [<span data-ttu-id="194f0-143">Dispositivos de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="194f0-143">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
