---
title: Conteúdos do dispositivo (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.bnrdevicecontents.f1
ms.assetid: 95e1902e-8c7a-4830-bdf9-1a6aca414a24
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c904718eca671b1965a95d0d400f3f6fa075b500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573138"
---
# <a name="device-contents-sql-server"></a><span data-ttu-id="fa13d-102">Conteúdos do dispositivo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fa13d-102">Device Contents (SQL Server)</span></span>
  <span data-ttu-id="fa13d-103">Use essa caixa de diálogo para exibir informações de backup.</span><span class="sxs-lookup"><span data-stu-id="fa13d-103">Use this dialog box to view the backup information.</span></span> <span data-ttu-id="fa13d-104">As informações descrevem o dispositivo, a mídia, o conjunto de mídias e o conjunto ou conjuntos de backups.</span><span class="sxs-lookup"><span data-stu-id="fa13d-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="fa13d-105">**Para usar o SQL Server Management Studio para exibir o conteúdo de um dispositivo de backup**</span><span class="sxs-lookup"><span data-stu-id="fa13d-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="fa13d-106">Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa13d-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="fa13d-107">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa13d-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="fa13d-108">Opções</span><span class="sxs-lookup"><span data-stu-id="fa13d-108">Options</span></span>  
 <span data-ttu-id="fa13d-109">**Mídia**</span><span class="sxs-lookup"><span data-stu-id="fa13d-109">**Media**</span></span>  
 <span data-ttu-id="fa13d-110">Um disco ou um conjunto de fitas nos quais as informações de backup estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="fa13d-110">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="fa13d-111">**Sequência de mídia**</span><span class="sxs-lookup"><span data-stu-id="fa13d-111">**Media sequence**</span></span>  
 <span data-ttu-id="fa13d-112">Relaciona o número de sequência de mídia; o número de sequência familiar e o identificador de espelhos, se houver.</span><span class="sxs-lookup"><span data-stu-id="fa13d-112">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="fa13d-113">Todas as mídias físicas de backup são marcadas com o número de sequência da mídia que indica a ordem de utilização da mídia.</span><span class="sxs-lookup"><span data-stu-id="fa13d-113">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="fa13d-114">A primeira mídia do backup é marcada com 1; a segunda (primeira fita de continuação) é marcada com 2, e assim sucessivamente.</span><span class="sxs-lookup"><span data-stu-id="fa13d-114">The initial backup medium is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="fa13d-115">Quando o conjunto de backups for restaurado, os números da sequência de mídias assegurarão que o operador que restaure o backup monte as mídias corretas na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="fa13d-115">When the backup set is restored, the media sequence numbers ensure that the operator that restores the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="fa13d-116">**Criado em**</span><span class="sxs-lookup"><span data-stu-id="fa13d-116">**Created on**</span></span>  
 <span data-ttu-id="fa13d-117">Exibe a data da mídia.</span><span class="sxs-lookup"><span data-stu-id="fa13d-117">Displays the media date.</span></span>  
  
 <span data-ttu-id="fa13d-118">**Conjunto de mídias**</span><span class="sxs-lookup"><span data-stu-id="fa13d-118">**Media Set**</span></span>  
 <span data-ttu-id="fa13d-119">Um conjunto de mídias é uma coleção ordenada de mídias de backup em que uma ou mais operações de backup foram gravadas, usando um número constante de dispositivos de backup.</span><span class="sxs-lookup"><span data-stu-id="fa13d-119">A media set is an ordered collection of backup media to which one or more backup operations have written using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="fa13d-120">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fa13d-120">**Name**</span></span>  
 <span data-ttu-id="fa13d-121">Exibe o nome do conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="fa13d-121">Displays the name of the media set.</span></span>  
  
 <span data-ttu-id="fa13d-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fa13d-122">**Description**</span></span>  
 <span data-ttu-id="fa13d-123">Exibe o conjunto de mídias de descrição.</span><span class="sxs-lookup"><span data-stu-id="fa13d-123">Displays the description media set.</span></span>  
  
 <span data-ttu-id="fa13d-124">**Contagem de família de mídia**</span><span class="sxs-lookup"><span data-stu-id="fa13d-124">**Media family count**</span></span>  
 <span data-ttu-id="fa13d-125">Exibe a conta de família de mídia.</span><span class="sxs-lookup"><span data-stu-id="fa13d-125">Displays the media family count.</span></span> <span data-ttu-id="fa13d-126">Cada conjunto de mídias é uma coleção de uma ou mais famílias de mídias.</span><span class="sxs-lookup"><span data-stu-id="fa13d-126">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="fa13d-127">Toda a saída de um determinado dispositivo de backup único (ou grupo de dispositivos de backup espelhados) forma uma única família de mídias.</span><span class="sxs-lookup"><span data-stu-id="fa13d-127">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="fa13d-128">Cada conjunto de mídias contém uma família para cada dispositivo separado (ou grupo de dispositivos espelhados); por exemplo, se um conjunto de mídias utiliza dois dispositivos de backup não espelhados, o mesmo terá duas famílias de mídias.</span><span class="sxs-lookup"><span data-stu-id="fa13d-128">Each media set contains one media family per separate device (or group of mirrored devices); for example, if a media set uses two nonmirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="fa13d-129">**Conjuntos de backup**</span><span class="sxs-lookup"><span data-stu-id="fa13d-129">**Backup sets**</span></span>  
 <span data-ttu-id="fa13d-130">Exibe as informações sobre o conjunto ou conjuntos de backup incluídos na mídia.</span><span class="sxs-lookup"><span data-stu-id="fa13d-130">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="fa13d-131">Um conjunto de backup é o resultado de uma operação de backup bem-sucedida, cujo conteúdo é distribuído entre as mídias em um conjunto de dispositivos de backup.</span><span class="sxs-lookup"><span data-stu-id="fa13d-131">A backup set is the result of a successful backup operation whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="fa13d-132">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="fa13d-132">Header</span></span>|<span data-ttu-id="fa13d-133">Valores</span><span class="sxs-lookup"><span data-stu-id="fa13d-133">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="fa13d-134">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fa13d-134">**Name**</span></span>|<span data-ttu-id="fa13d-135">O nome do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="fa13d-135">The name of the backup set.</span></span>|  
|<span data-ttu-id="fa13d-136">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fa13d-136">**Type**</span></span>|<span data-ttu-id="fa13d-137">O tipo de backup realizado: Total, Diferencial ou Log de Transações.</span><span class="sxs-lookup"><span data-stu-id="fa13d-137">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="fa13d-138">**Componente**</span><span class="sxs-lookup"><span data-stu-id="fa13d-138">**Component**</span></span>|<span data-ttu-id="fa13d-139">o componente de backup: Banco de dados, Arquivo ou *\<blank>* (para logs de transações).</span><span class="sxs-lookup"><span data-stu-id="fa13d-139">The backed-up component: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="fa13d-140">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="fa13d-140">**Server**</span></span>|<span data-ttu-id="fa13d-141">O nome da instância de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que realizou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="fa13d-141">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="fa13d-142">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="fa13d-142">**Database**</span></span>|<span data-ttu-id="fa13d-143">O nome do banco de dados cujo backup foi efetuado.</span><span class="sxs-lookup"><span data-stu-id="fa13d-143">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="fa13d-144">**Posição**</span><span class="sxs-lookup"><span data-stu-id="fa13d-144">**Position**</span></span>|<span data-ttu-id="fa13d-145">A posição do conjunto de backup no volume.</span><span class="sxs-lookup"><span data-stu-id="fa13d-145">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="fa13d-146">**Data**</span><span class="sxs-lookup"><span data-stu-id="fa13d-146">**Date**</span></span>|<span data-ttu-id="fa13d-147">A data e hora da conclusão da operação de backup, apresentadas na configuração regional do cliente.</span><span class="sxs-lookup"><span data-stu-id="fa13d-147">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="fa13d-148">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="fa13d-148">**Size**</span></span>|<span data-ttu-id="fa13d-149">O tamanho do conjunto de backup em bytes.</span><span class="sxs-lookup"><span data-stu-id="fa13d-149">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="fa13d-150">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="fa13d-150">**User Name**</span></span>|<span data-ttu-id="fa13d-151">O nome do usuário que realizou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="fa13d-151">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="fa13d-152">**Validade**</span><span class="sxs-lookup"><span data-stu-id="fa13d-152">**Expiration**</span></span>|<span data-ttu-id="fa13d-153">A data e hora de validade do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="fa13d-153">The date and time the backup set expires.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa13d-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fa13d-154">See Also</span></span>  
 [<span data-ttu-id="fa13d-155">Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa13d-155">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
