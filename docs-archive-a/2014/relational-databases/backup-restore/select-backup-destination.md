---
title: Selecionar destino do backup | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.selectbackupdest.f1
ms.assetid: f79e824b-1525-45de-8ede-513563af41b6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5ffd1d2529dd13e42689bcf168c972d757fb5499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581397"
---
# <a name="select-backup-destination"></a><span data-ttu-id="775c6-102">Selecionar destino do backup</span><span class="sxs-lookup"><span data-stu-id="775c6-102">Select Backup Destination</span></span>
  <span data-ttu-id="775c6-103">Use a caixa de diálogo **Selecionar Destino do Backup** para selecionar um dispositivo como seu destino de backup.</span><span class="sxs-lookup"><span data-stu-id="775c6-103">Use the **Select Backup Destination** dialog box to select a device as your backup destination.</span></span> <span data-ttu-id="775c6-104">Um destino de backup pode ser tanto um disco quanto um dispositivo de backup lógico.</span><span class="sxs-lookup"><span data-stu-id="775c6-104">A backup destination can be either a disk or a logical backup device.</span></span>  
  
 <span data-ttu-id="775c6-105">**Para usar o SQL Server Management Studio para fazer o backup de um banco de dados**</span><span class="sxs-lookup"><span data-stu-id="775c6-105">**To use SQL Server Management Studio to back up a database**</span></span>  
  
-   [<span data-ttu-id="775c6-106">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="775c6-106">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="775c6-107">Criar um backup diferencial de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="775c6-107">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="775c6-108">Fazer backup de arquivos e de grupos de arquivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="775c6-108">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="775c6-109">Fazer backup de um log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="775c6-109">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="775c6-110">Opções</span><span class="sxs-lookup"><span data-stu-id="775c6-110">Options</span></span>  
 <span data-ttu-id="775c6-111">As opções dessa caixa de diálogo dependem do fato de você estar selecionando um destino em disco ou em fita.</span><span class="sxs-lookup"><span data-stu-id="775c6-111">The options of this dialog box depend on whether you are selecting a destination on disk or on tape.</span></span>  
  
 <span data-ttu-id="775c6-112">**Destino em disco**</span><span class="sxs-lookup"><span data-stu-id="775c6-112">**Destination on disk**</span></span>  
 <span data-ttu-id="775c6-113">Para especificar um destino de backup, escolha uma das opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="775c6-113">To specify a backup destination, choose one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="775c6-114">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="775c6-114">**File name**</span></span>|<span data-ttu-id="775c6-115">Escolha esta opção para digitar na caixa de texto um arquivo local ou remoto como o destino de backup.</span><span class="sxs-lookup"><span data-stu-id="775c6-115">Choose this option to enter a local or remote file as the backup destination in the text box.</span></span><br /><br /> <span data-ttu-id="775c6-116">Para especificar um arquivo local, clique no botão Procurar à direita da caixa de texto e navegue para um arquivo nas unidades fixas do computador que está executando o servidor, ou digite diretamente o caminho completo e nome de arquivo; por exemplo, `C:\Program Files\Microsoft SQL Server\MSSQL\Backup\AdventureWorksBackup.bak`.</span><span class="sxs-lookup"><span data-stu-id="775c6-116">To specify a local file, click the browse button to the right of the text box and navigate to a file on the fixed drives of the computer running the server, or enter the full path and file name directly; for example, `C:\Program Files\Microsoft SQL Server\MSSQL\Backup\AdventureWorksBackup.bak`.</span></span><br /><br /> <span data-ttu-id="775c6-117">Para especificar um arquivo remoto como seu destino de backup, digite o nome da Convenção Universal de Nomenclatura (UNC) totalmente qualificada.</span><span class="sxs-lookup"><span data-stu-id="775c6-117">To specify a remote file as your backup destination, enter its fully qualified universal naming convention (UNC) name.</span></span> <span data-ttu-id="775c6-118">Para obter mais informações, consulte [Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="775c6-118">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span><br /><br /> <span data-ttu-id="775c6-119">**\*\* Importante \*\*** Backups de dados em uma rede podem estar sujeitos a erros de rede; assim, recomendamos que você verifique a operação de backup quando ela estiver concluída.</span><span class="sxs-lookup"><span data-stu-id="775c6-119">**\*\* Important \*\*** Backing up data over a network can be subject to network errors; therefore, we recommend that you verify the backup operation after it finishes.</span></span> <span data-ttu-id="775c6-120">Para obter mais informações, consulte [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="775c6-120">For more information, see [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span></span>|  
|<span data-ttu-id="775c6-121">**Dispositivo de backup**</span><span class="sxs-lookup"><span data-stu-id="775c6-121">**Backup device**</span></span>|<span data-ttu-id="775c6-122">Escolha esta opção para selecionar um dispositivo de backup lógico.</span><span class="sxs-lookup"><span data-stu-id="775c6-122">Choose this option to select a logical backup device.</span></span><br /><br /> <span data-ttu-id="775c6-123">Observação: para obter informações sobre como criar um dispositivo de backup em disco, consulte [Definir um dispositivo de backup lógico para um arquivo de disco &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="775c6-123">Note: For information about how to create a disk backup device, see [Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md).</span></span>|  
  
 <span data-ttu-id="775c6-124">**Destino em fita**</span><span class="sxs-lookup"><span data-stu-id="775c6-124">**Destination on tape**</span></span>  
 <span data-ttu-id="775c6-125">Especifique um destino de backup em uma unidade de fita conectada fisicamente ao computador que está executando o servidor (ou seja, a instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="775c6-125">Specify a backup destination on a tape drive physically connected to the computer running the server (that is, the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]).</span></span> <span data-ttu-id="775c6-126">Escolha uma das opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="775c6-126">Choose one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="775c6-127">**Unidade de fita**</span><span class="sxs-lookup"><span data-stu-id="775c6-127">**Tape drive**</span></span>|<span data-ttu-id="775c6-128">Escolha esta opção para selecionar uma unidade de fita como destino de backup da lista de unidades de fita conectadas fisicamente ao computador que está executando a instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="775c6-128">Choose this option to select a tape drive as the backup destination from the list of tape drives that are physically connected to the computer that is running the server instance.</span></span><br /><br /> <span data-ttu-id="775c6-129">Observação: Dispositivos de backup em fita em computadores remotos não são destinos de backup válidos.</span><span class="sxs-lookup"><span data-stu-id="775c6-129">Note: Tape backup devices on remote computers are not valid backup destinations.</span></span>|  
|<span data-ttu-id="775c6-130">**Dispositivo de backup**</span><span class="sxs-lookup"><span data-stu-id="775c6-130">**Backup device**</span></span>|<span data-ttu-id="775c6-131">Escolha esta opção para selecionar um dispositivo de backup lógico existente.</span><span class="sxs-lookup"><span data-stu-id="775c6-131">Choose this option to select an existing logical backup device.</span></span> <span data-ttu-id="775c6-132">Esses dispositivos de backup lógicos correspondem a unidades de fita conectadas fisicamente ao computador que está executando a instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="775c6-132">These logical backup devices correspond to tape drives that are physically connected to the computer that is running the server instance.</span></span><br /><br /> <span data-ttu-id="775c6-133">Observação: para obter informações sobre como criar um dispositivo de backup em fita, consulte [Definir um dispositivo de backup lógico para uma unidade de fita &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="775c6-133">Note: For information about how to create a tape backup device, see [Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="775c6-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="775c6-134">See Also</span></span>  
 <span data-ttu-id="775c6-135">[Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="775c6-135">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="775c6-136">Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="775c6-136">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
