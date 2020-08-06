---
title: Dispositivo de backup (página Conteúdo de Mídia) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.contents.f1
ms.assetid: 5fc7bd22-b6d8-4af1-8a58-2e7d0b994d08
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 07204b5e05ce9fc17e6ea23450066f9f58b7cf87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574738"
---
# <a name="backup-device-media-contents-page"></a><span data-ttu-id="da2e2-102">Dispositivo de backup (página Conteúdo da Mídia)</span><span class="sxs-lookup"><span data-stu-id="da2e2-102">Backup Device (Media Contents Page)</span></span>
  <span data-ttu-id="da2e2-103">Use a caixa de diálogo **Dispositivo de Backup** para exibir as informações de backup.</span><span class="sxs-lookup"><span data-stu-id="da2e2-103">Use the **Backup Device** dialog box to view the backup information.</span></span> <span data-ttu-id="da2e2-104">As informações descrevem o dispositivo, a mídia, o conjunto de mídias e o conjunto ou conjuntos de backups.</span><span class="sxs-lookup"><span data-stu-id="da2e2-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="da2e2-105">**Para usar o SQL Server Management Studio para exibir o conteúdo de um dispositivo de backup**</span><span class="sxs-lookup"><span data-stu-id="da2e2-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="da2e2-106">Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="da2e2-107">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="da2e2-108">Opções</span><span class="sxs-lookup"><span data-stu-id="da2e2-108">Options</span></span>  
 <span data-ttu-id="da2e2-109">Exiba as informações das mídias individuais, conjunto de mídias e os conjuntos de backup.</span><span class="sxs-lookup"><span data-stu-id="da2e2-109">View information about the individual media, media set, and backup sets.</span></span>  
  
 <span data-ttu-id="da2e2-110">**Mídia**</span><span class="sxs-lookup"><span data-stu-id="da2e2-110">**Media**</span></span>  
 <span data-ttu-id="da2e2-111">Um disco ou um conjunto de fitas nos quais as informações de backup estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="da2e2-111">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="da2e2-112">**Sequência de mídia**</span><span class="sxs-lookup"><span data-stu-id="da2e2-112">**Media sequence**</span></span>  
 <span data-ttu-id="da2e2-113">Relaciona o número de sequência de mídia; o número de sequência familiar e o identificador de espelhos, se houver.</span><span class="sxs-lookup"><span data-stu-id="da2e2-113">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="da2e2-114">Todas as mídias físicas de backup são marcadas com o número de sequência da mídia que indica a ordem de utilização da mídia.</span><span class="sxs-lookup"><span data-stu-id="da2e2-114">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="da2e2-115">A mídia inicial de backup é identificada com 1, a segunda (a primeira fita de continuação) é identificada com 2, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="da2e2-115">The initial backup media is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="da2e2-116">Quando o conjunto de backup é restaurado, os números sequenciais das mídias garantem que o operador que estiver restaurando o backup esteja montando a mídia correta na ordem apropriada.</span><span class="sxs-lookup"><span data-stu-id="da2e2-116">When the backup set is restored, the media sequence numbers ensure that the operator restoring the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="da2e2-117">**Criado em**</span><span class="sxs-lookup"><span data-stu-id="da2e2-117">**Created on**</span></span>  
 <span data-ttu-id="da2e2-118">Exibe a data e a hora da criação do conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="da2e2-118">Displays the creation date and time of the media set.</span></span>  
  
 <span data-ttu-id="da2e2-119">**Conjunto de mídias**</span><span class="sxs-lookup"><span data-stu-id="da2e2-119">**Media Set**</span></span>  
 <span data-ttu-id="da2e2-120">Um conjunto de mídias é uma coleção ordenada de mídias de backup no qual uma ou mais operações de backup foram gravadas usando um número constante de dispositivos de backup.</span><span class="sxs-lookup"><span data-stu-id="da2e2-120">A media set is an ordered collection of backup media to which one or more backup operations have written by using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="da2e2-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="da2e2-121">**Name**</span></span>  
 <span data-ttu-id="da2e2-122">Exibe o nome do conjunto de mídias, se houver.</span><span class="sxs-lookup"><span data-stu-id="da2e2-122">Displays the name of the media set, if any.</span></span>  
  
 <span data-ttu-id="da2e2-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="da2e2-123">**Description**</span></span>  
 <span data-ttu-id="da2e2-124">Exibe a descrição do conjunto de mídias, se houver.</span><span class="sxs-lookup"><span data-stu-id="da2e2-124">Displays the description of the media set, if any.</span></span>  
  
 <span data-ttu-id="da2e2-125">**Contagem de família de mídia**</span><span class="sxs-lookup"><span data-stu-id="da2e2-125">**Media family count**</span></span>  
 <span data-ttu-id="da2e2-126">Exibe o número de famílias no conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="da2e2-126">Displays the number of families in the media set.</span></span> <span data-ttu-id="da2e2-127">Cada conjunto de mídias é uma coleção de uma ou mais famílias de mídias.</span><span class="sxs-lookup"><span data-stu-id="da2e2-127">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="da2e2-128">Toda a saída de um determinado dispositivo de backup único (ou grupo de dispositivos de backup espelhados) forma uma única família de mídias.</span><span class="sxs-lookup"><span data-stu-id="da2e2-128">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="da2e2-129">Cada conjunto de mídias contém uma família para cada dispositivo separado (ou grupo de dispositivos espelhados); por exemplo, se um conjunto de mídias utiliza dois dispositivos de backup não espelhados, o mesmo terá duas famílias de mídias.</span><span class="sxs-lookup"><span data-stu-id="da2e2-129">Each media set contains one media family per separate device (or group of mirrored devices); for instance, if a media set uses two non-mirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="da2e2-130">**Conjuntos de backup**</span><span class="sxs-lookup"><span data-stu-id="da2e2-130">**Backup sets**</span></span>  
 <span data-ttu-id="da2e2-131">Exibe as informações sobre o conjunto ou conjuntos de backup incluídos na mídia.</span><span class="sxs-lookup"><span data-stu-id="da2e2-131">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="da2e2-132">Um conjunto de backup é o resultado de uma operação de backup bem-sucedida cujo conteúdo é distribuído entre as mídias em um conjunto de dispositivos de backup.</span><span class="sxs-lookup"><span data-stu-id="da2e2-132">A backup set is the result of a successful backup operation, whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="da2e2-133">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="da2e2-133">Header</span></span>|<span data-ttu-id="da2e2-134">Valores</span><span class="sxs-lookup"><span data-stu-id="da2e2-134">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="da2e2-135">**Nome**</span><span class="sxs-lookup"><span data-stu-id="da2e2-135">**Name**</span></span>|<span data-ttu-id="da2e2-136">O nome do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="da2e2-136">The name of the backup set.</span></span>|  
|<span data-ttu-id="da2e2-137">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="da2e2-137">**Type**</span></span>|<span data-ttu-id="da2e2-138">O objeto de backup: Banco de dados, Arquivo ou *\<blank>* (para logs de transações).</span><span class="sxs-lookup"><span data-stu-id="da2e2-138">The backed-up object: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="da2e2-139">**Componente**</span><span class="sxs-lookup"><span data-stu-id="da2e2-139">**Component**</span></span>|<span data-ttu-id="da2e2-140">O tipo de backup realizado: Total, Diferencial ou Log de Transações.</span><span class="sxs-lookup"><span data-stu-id="da2e2-140">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="da2e2-141">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="da2e2-141">**Server**</span></span>|<span data-ttu-id="da2e2-142">O nome da instância de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que realizou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="da2e2-142">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="da2e2-143">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="da2e2-143">**Database**</span></span>|<span data-ttu-id="da2e2-144">O nome do banco de dados cujo backup foi efetuado.</span><span class="sxs-lookup"><span data-stu-id="da2e2-144">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="da2e2-145">**Posição**</span><span class="sxs-lookup"><span data-stu-id="da2e2-145">**Position**</span></span>|<span data-ttu-id="da2e2-146">A posição do conjunto de backup no volume.</span><span class="sxs-lookup"><span data-stu-id="da2e2-146">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="da2e2-147">**Data**</span><span class="sxs-lookup"><span data-stu-id="da2e2-147">**Date**</span></span>|<span data-ttu-id="da2e2-148">A data e hora da conclusão da operação de backup, apresentadas na configuração regional do cliente.</span><span class="sxs-lookup"><span data-stu-id="da2e2-148">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="da2e2-149">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="da2e2-149">**Size**</span></span>|<span data-ttu-id="da2e2-150">O tamanho do conjunto de backup em bytes.</span><span class="sxs-lookup"><span data-stu-id="da2e2-150">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="da2e2-151">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="da2e2-151">**User Name**</span></span>|<span data-ttu-id="da2e2-152">O nome do usuário que realizou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="da2e2-152">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="da2e2-153">**Validade**</span><span class="sxs-lookup"><span data-stu-id="da2e2-153">**Expiration**</span></span>|<span data-ttu-id="da2e2-154">A data e hora de validade do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="da2e2-154">The date and time the backup set expires.</span></span>|  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="da2e2-155">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="da2e2-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="da2e2-156">Definir um dispositivo de backup lógico para um arquivo de disco &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-156">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="da2e2-157">Definir um dispositivo de backup lógico para uma unidade de fita &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-157">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="da2e2-158">Especificar um disco ou fita como destino de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-158">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="da2e2-159">Excluir um dispositivo de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-159">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="da2e2-160">Definir a data de validade em um backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-160">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="da2e2-161">Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-161">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="da2e2-162">Exibir os dados e arquivos de log em um conjunto de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-162">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="da2e2-163">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-163">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="da2e2-164">Restaurar um backup de um dispositivo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-164">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="da2e2-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="da2e2-165">See Also</span></span>  
 <span data-ttu-id="da2e2-166">[Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="da2e2-166">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="da2e2-167">Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da2e2-167">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
