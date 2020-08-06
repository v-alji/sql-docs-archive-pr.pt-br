---
title: Dispositivo de backup (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.general.f1
ms.assetid: c557e37d-319e-4adb-a0c1-94189b15d2ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d73bdf3ce4b88214286b5f232924d811716a247e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570076"
---
# <a name="backup-device-general-page"></a><span data-ttu-id="37f82-102">Dispositivo de backup (página Geral)</span><span class="sxs-lookup"><span data-stu-id="37f82-102">Backup Device (General Page)</span></span>
  <span data-ttu-id="37f82-103">Use a página **Geral** para especificar ou exibir as propriedades gerais de um dispositivo de backup lógico.</span><span class="sxs-lookup"><span data-stu-id="37f82-103">Use the **General** page to specify or view the general properties of a logical backup device.</span></span>  
  
 <span data-ttu-id="37f82-104">**Para usar o SQL Server Management Studio para exibir o conteúdo de um dispositivo de backup**</span><span class="sxs-lookup"><span data-stu-id="37f82-104">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="37f82-105">Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-105">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="37f82-106">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-106">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="37f82-107">Opções</span><span class="sxs-lookup"><span data-stu-id="37f82-107">Options</span></span>  
 <span data-ttu-id="37f82-108">**Nome de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="37f82-108">**Device name**</span></span>  
 <span data-ttu-id="37f82-109">Exibe o nome de um dispositivo de backup lógico existente ou especifica o nome de um novo dispositivo de backup lógico.</span><span class="sxs-lookup"><span data-stu-id="37f82-109">View the name of an existing logical backup device or specify the name of a new logical backup device.</span></span>  
  
 <span data-ttu-id="37f82-110">**Fita**</span><span class="sxs-lookup"><span data-stu-id="37f82-110">**Tape**</span></span>  
 <span data-ttu-id="37f82-111">Exibe ou seleciona o dispositivo de fita de destino na lista **Fita** .</span><span class="sxs-lookup"><span data-stu-id="37f82-111">View or select the destination tape device in the **Tape** list.</span></span> <span data-ttu-id="37f82-112">Essa opção estará disponível apenas se uma unidade de fita for anexada ao computador que executa a instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f82-112">This option is available only if a tape drive is attached to the computer that is running the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37f82-113">Dispositivos de backup em fita em computadores remotos não são destinos de backup válidos.</span><span class="sxs-lookup"><span data-stu-id="37f82-113">Tape backup devices on remote computers are not valid backup destinations.</span></span>  
  
 <span data-ttu-id="37f82-114">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="37f82-114">**File**</span></span>  
 <span data-ttu-id="37f82-115">Exibe o arquivo de destino de um dispositivo de backup lógico existente ou especifica um arquivo de destino para um novo dispositivo de backup lógico.</span><span class="sxs-lookup"><span data-stu-id="37f82-115">View the destination file of an existing logical backup device, or specify a destination file for a new logical backup device.</span></span>  
  
-   <span data-ttu-id="37f82-116">O caminho do arquivo de backup é exibido para um dispositivo de backup lógico existente.</span><span class="sxs-lookup"><span data-stu-id="37f82-116">For an existing logical backup device, the path of the backup file is displayed.</span></span> <span data-ttu-id="37f82-117">O campo **Arquivo** não é editável e o botão Procurar está indisponível.</span><span class="sxs-lookup"><span data-stu-id="37f82-117">The **File** field is not editable, and the Browse button is unavailable.</span></span>  
  
-   <span data-ttu-id="37f82-118">Para um novo dispositivo de backup lógico, você deve fornecer o caminho do arquivo de backup para o qual está definindo o dispositivo de backup lógico.</span><span class="sxs-lookup"><span data-stu-id="37f82-118">For a new logical backup device, you must supply the path of the backup file for which you are defining the logical backup device.</span></span> <span data-ttu-id="37f82-119">Esse arquivo não precisa existir ainda.</span><span class="sxs-lookup"><span data-stu-id="37f82-119">This file does not have to exist yet.</span></span>  
  
     <span data-ttu-id="37f82-120">Para especificar um arquivo de backup local, você pode clicar no botão Procurar à direita da caixa de texto **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="37f82-120">To specify a local backup file, you can click the Browse button to the right of the **File** text box.</span></span> <span data-ttu-id="37f82-121">Então, na caixa de diálogo **Localizar Arquivos de Bancos de Dados** , será possível navegar para o local em unidades fixas no computador que executa a instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="37f82-121">Then, in the **Locate Database Files** dialog box, you can navigate to any location on any of the fixed drives on the computer running the server instance.</span></span> <span data-ttu-id="37f82-122">Se o arquivo de backup ainda não existir, você deve digitar o nome de arquivo que deseja usar no campo **Nome do arquivo** da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="37f82-122">If the backup file does not exist yet, you must enter the filename you want to use in the **File name** field of that dialog box.</span></span>  
  
     <span data-ttu-id="37f82-123">Como alternativa,´você pode editar o campo **Arquivo** manualmente para anular o caminho, nome de arquivo e extensão padrão.</span><span class="sxs-lookup"><span data-stu-id="37f82-123">Alternatively, you can edit the **File** field manually to override the default path, file name, and extension.</span></span> <span data-ttu-id="37f82-124">Para especificar um arquivo remoto como seu destino de backup, digite o nome da Convenção Universal de Nomenclatura (UNC) totalmente qualificada.</span><span class="sxs-lookup"><span data-stu-id="37f82-124">To specify a remote file as your backup destination, enter its fully qualified universal naming convention (UNC) name.</span></span> <span data-ttu-id="37f82-125">Para obter mais informações, consulte [Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="37f82-125">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="37f82-126">Backups de dados em uma rede podem estar sujeitos a erros de rede; assim, recomendamos que você verifique a operação de backup quando ela estiver concluída.</span><span class="sxs-lookup"><span data-stu-id="37f82-126">Backing up data over a network can be subject to network errors; therefore, we recommend that you verify the backup operation after it finishes.</span></span> <span data-ttu-id="37f82-127">Para obter mais informações, consulte [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="37f82-127">For more information, see [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37f82-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="37f82-128">Remarks</span></span>  
 <span data-ttu-id="37f82-129">Os backups em um conjunto de um ou mais dispositivos de backup compõem um único conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="37f82-129">The backups on a set of one or more backup devices compose a single media set.</span></span> <span data-ttu-id="37f82-130">Um *conjunto de mídias* é uma coleção ordenada de mídias de backup, fitas ou arquivos de disco, em que uma ou mais operações de backup foram gravadas, usando um número e tipo fixo de dispositivos de backup.</span><span class="sxs-lookup"><span data-stu-id="37f82-130">A *media set* is an ordered collection of backup media, tapes or disk files, to which one or more backup operations have written using a fixed type and number of backup devices.</span></span> <span data-ttu-id="37f82-131">Para obter informações sobre conjuntos de mídias, consulte [Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="37f82-131">For information about media sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="37f82-132">O dispositivo de backup físico, que corresponde a um dispositivo de backup lógico, é inicializado quando o primeiro backup no conjunto de mídia é escrito ao dispositivo de backup lógico.</span><span class="sxs-lookup"><span data-stu-id="37f82-132">The physical backup device corresponding to a logical backup device is initialized when the first backup in the media set is written to the logical backup device.</span></span> <span data-ttu-id="37f82-133">Se o dispositivo de backup físico for um arquivo que ainda não existe, ele será criado nesse momento.</span><span class="sxs-lookup"><span data-stu-id="37f82-133">If the physical backup device is a file that does not exist yet, it is created at that time.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="37f82-134">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="37f82-134">Related Tasks</span></span>  
  
-   [<span data-ttu-id="37f82-135">Definir um dispositivo de backup lógico para um arquivo de disco &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-135">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="37f82-136">Definir um dispositivo de backup lógico para uma unidade de fita &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-136">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="37f82-137">Especificar um disco ou fita como destino de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-137">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="37f82-138">Excluir um dispositivo de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-138">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="37f82-139">Definir a data de validade em um backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-139">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="37f82-140">Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-140">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="37f82-141">Exibir os dados e arquivos de log em um conjunto de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-141">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="37f82-142">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-142">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="37f82-143">Restaurar um backup de um dispositivo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-143">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="37f82-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="37f82-144">See Also</span></span>  
 <span data-ttu-id="37f82-145">[Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="37f82-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="37f82-146">Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="37f82-146">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
