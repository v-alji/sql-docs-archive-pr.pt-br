---
title: Compactação de backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], backup compression
- backup compression [SQL Server], about backup compression
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- backing up [SQL Server], backup compression
- backup compression [SQL Server]
ms.assetid: 05bc9c4f-3947-4dd4-b823-db77519bd4d2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3291a858d8ef037e7cca92eb2e6abb19aec4da8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570078"
---
# <a name="backup-compression-sql-server"></a><span data-ttu-id="e7e0d-102">Compactação de backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e7e0d-102">Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="e7e0d-103">Este tópico descreve a compactação dos backups do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , incluindo restrições, compensação de desempenho de backups compactados, a configuração da compactação de backup e a taxa de compactação.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-103">This topic describes the compression of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups, including restrictions, performance trade-off of compressing backups, the configuration of backup compression, and the compression ratio.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7e0d-104">Para obter informações sobre quais edições do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dão suporte à compactação de backup, consulte [recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="e7e0d-104">For information which editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support backup compression, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="e7e0d-105">Todas as edições do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou posterior podem restaurar um backup compactado.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-105">Every edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later can restore a compressed backup.</span></span>  
  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="e7e0d-106">Benefícios</span><span class="sxs-lookup"><span data-stu-id="e7e0d-106">Benefits</span></span>  
  
-   <span data-ttu-id="e7e0d-107">Como um backup compactado é menor do que um backup não compactado dos mesmos dados, a compactação de um backup normalmente requer menos operações de E/S do dispositivo e, portanto, normalmente aumenta significativamente a velocidade do backup.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-107">Because a compressed backup is smaller than an uncompressed backup of the same data, compressing a backup typically requires less device I/O and therefore usually increases backup speed significantly.</span></span>  
  
     <span data-ttu-id="e7e0d-108">Para obter mais informações, consulte [Impacto de desempenho dos backups compactados](#PerfImpact), posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-108">For more information, see [Performance Impact of Compressing Backups](#PerfImpact), later in this topic.</span></span>  
  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e7e0d-109">Restrições</span><span class="sxs-lookup"><span data-stu-id="e7e0d-109">Restrictions</span></span>  
 <span data-ttu-id="e7e0d-110">As restrições a seguir aplicam-se aos backups compactados:</span><span class="sxs-lookup"><span data-stu-id="e7e0d-110">The following restrictions apply to compressed backups:</span></span>  
  
-   <span data-ttu-id="e7e0d-111">Backups compactados e não compactados não podem coexistir em um conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-111">Compressed and uncompressed backups cannot co-exist in a media set.</span></span>  
  
-   <span data-ttu-id="e7e0d-112">Porém, as versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não podem ler os backups compactados.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-112">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot read compressed backups.</span></span>  
  
-   <span data-ttu-id="e7e0d-113">Backups NT não podem compartilhar uma fita com backups compactados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7e0d-113">NTbackups cannot share a tape with compressed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span>  
  
  
##  <a name="performance-impact-of-compressing-backups"></a><a name="PerfImpact"></a> <span data-ttu-id="e7e0d-114">Impacto de desempenho dos backups compactados</span><span class="sxs-lookup"><span data-stu-id="e7e0d-114">Performance Impact of Compressing Backups</span></span>  
 <span data-ttu-id="e7e0d-115">Por padrão, a compactação aumenta consideravelmente o uso da CPU, e o consumo adicional da CPU por parte do processo de compactação pode afetar negativamente as operações simultâneas.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-115">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="e7e0d-116">Portanto, convém criar backups compactados de baixa prioridade em uma sessão cujo uso da CPU é limitado pelo[Resource Governor](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="e7e0d-116">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="e7e0d-117">Para obter mais informações, consulte [Usar o Resource Governor para limitar o uso de CPU por meio de compactação de backup &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="e7e0d-117">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
 <span data-ttu-id="e7e0d-118">Para obter uma boa visão do desempenho de E/S do seu backup, é possível isolar o E/S do backup para ou dos dispositivos avaliando as seguintes classificações dos contadores de desempenho:</span><span class="sxs-lookup"><span data-stu-id="e7e0d-118">To obtain a good picture of your backup I/O performance, you can isolate the backup I/O to or from devices by evaluating the following sorts of performance counters:</span></span>  
  
-   <span data-ttu-id="e7e0d-119">Contadores de desempenho de E/S do Windows, como os contadores de disco físico</span><span class="sxs-lookup"><span data-stu-id="e7e0d-119">Windows I/O performance counters, such as the physical-disk counters</span></span>  
  
-   <span data-ttu-id="e7e0d-120">O contador de **Taxa de Transferência do Dispositivo em Bytes/s** do objeto [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md)</span><span class="sxs-lookup"><span data-stu-id="e7e0d-120">The **Device Throughput Bytes/sec** counter of the [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md) object</span></span>  
  
-   <span data-ttu-id="e7e0d-121">O contador **Taxa de Transferência de Backup/Restauração/s** do objeto [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md)</span><span class="sxs-lookup"><span data-stu-id="e7e0d-121">The **Backup/Restore Throughput/sec** counter of the [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md) object</span></span>  
  
 <span data-ttu-id="e7e0d-122">Para obter informações sobre contadores do Windows, consulte a ajuda do Windows.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-122">For information about Windows counters, see Windows help.</span></span> <span data-ttu-id="e7e0d-123">Para obter informações sobre como trabalhar com contadores SQL Server, consulte [Usar objetos do SQL Server](../performance-monitor/use-sql-server-objects.md).</span><span class="sxs-lookup"><span data-stu-id="e7e0d-123">For information about how to work with SQL Server counters, see [Use SQL Server Objects](../performance-monitor/use-sql-server-objects.md).</span></span>  
  
  
##  <a name="calculate-the-compression-ratio-of-a-compressed-backup"></a><a name="CompressionRatio"></a> <span data-ttu-id="e7e0d-124">Calcular a taxa de compactação de um backup compactado</span><span class="sxs-lookup"><span data-stu-id="e7e0d-124">Calculate the Compression Ratio of a Compressed Backup</span></span>  
 <span data-ttu-id="e7e0d-125">Para calcular a taxa de compactação de um backup, use os valores para o backup nas colunas **backup_size** e **compressed_backup_size** da tabela de histórico [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e7e0d-125">To calculate the compression ratio of a backup, use the values for the backup in the **backup_size** and **compressed_backup_size** columns of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) history table, as follows:</span></span>  
  
 <span data-ttu-id="e7e0d-126">**backup_size**:**compressed_backup_size**</span><span class="sxs-lookup"><span data-stu-id="e7e0d-126">**backup_size**:**compressed_backup_size**</span></span>  
  
 <span data-ttu-id="e7e0d-127">Por exemplo, uma taxa de compactação de 3:1 indica que você está economizando aproximadamente 66% de espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-127">For example, a 3:1 compression ratio indicates that you are saving about 66% on disk space.</span></span> <span data-ttu-id="e7e0d-128">Para consultar essas colunas, você pode usar a seguinte instrução Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="e7e0d-128">To query on these columns, you can use the following Transact-SQL statement:</span></span>  
  
```  
SELECT backup_size/compressed_backup_size FROM msdb..backupset;  
```  
  
 <span data-ttu-id="e7e0d-129">A taxa de compactação de um backup compactado depende dos dados que foram compactados.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-129">The compression ratio of a compressed backup depends on the data that has been compressed.</span></span> <span data-ttu-id="e7e0d-130">Uma variedade de fatores pode impactar na taxa de compactação obtida.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-130">A variety of factors can impact the compression ratio obtained.</span></span> <span data-ttu-id="e7e0d-131">Os principais fatores incluem:</span><span class="sxs-lookup"><span data-stu-id="e7e0d-131">Major factors include:</span></span>  
  
-   <span data-ttu-id="e7e0d-132">O tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-132">The type of data.</span></span>  
  
     <span data-ttu-id="e7e0d-133">Os dados de caractere compactam mais do que outros tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-133">Character data compresses more than other types of data.</span></span>  
  
-   <span data-ttu-id="e7e0d-134">A consistência dos dados entre as linhas em uma página.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-134">The consistency of the data among rows on a page.</span></span>  
  
     <span data-ttu-id="e7e0d-135">Normalmente, se uma página contém várias linhas com um campo contendo o mesmo valor, poderá ocorrer uma compactação significativa para esse valor.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-135">Typically, if a page contains several rows in which a field contains the same value, significant compression might occur for that value.</span></span> <span data-ttu-id="e7e0d-136">Por outro lado, para um banco de dados que contém dados aleatórios ou contém somente uma grande linha por página, um backup compactado pode ser tão grande quanto um backup não compactado.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-136">In contrast, for a database that contains random data or that contains only one large row per page, a compressed backup would be almost as large as an uncompressed backup.</span></span>  
  
-   <span data-ttu-id="e7e0d-137">Se os dados são criptografados.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-137">Whether the data is encrypted.</span></span>  
  
     <span data-ttu-id="e7e0d-138">A compactação de dados criptografados é significativamente menor do que a compactação de dados equivalentes não criptografados.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-138">Encrypted data compresses significantly less than equivalent unencrypted data.</span></span> <span data-ttu-id="e7e0d-139">Se criptografia transparente de dados for usada para criptografar um banco de dados inteiro, a compactação de backup talvez não reduza muito o tamanho, se reduzir.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-139">If transparent data encryption is used to encrypt an entire database, compressing backups might not reduce their size by much, if at all.</span></span>  
  
-   <span data-ttu-id="e7e0d-140">Se o banco de dados é compactado.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-140">Whether the database is compressed.</span></span>  
  
     <span data-ttu-id="e7e0d-141">Se o banco de dados for compactado, a compactação de backups poderá não reduzir muito o seu tamanho.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-141">If the database is compressed, compressing backups might not reduce their size by much, if at all.</span></span>  
  
  
##  <a name="allocation-of-space-for-the-backup-file"></a><a name="Allocation"></a> <span data-ttu-id="e7e0d-142">Alocação de espaço para o arquivo de backup</span><span class="sxs-lookup"><span data-stu-id="e7e0d-142">Allocation of Space for the Backup File</span></span>  
 <span data-ttu-id="e7e0d-143">Para backups compactados, o tamanho do arquivo de backup final depende de como os dados são compactáveis e isto é desconhecido antes da conclusão da operação de backup.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-143">For compressed backups, the size of the final backup file depends on how compressible the data is, and this is unknown before the backup operation finishes.</span></span>  <span data-ttu-id="e7e0d-144">Portanto, por padrão, ao fazer backup de um banco de dados usando compactação, o Mecanismo de Banco de Dados usa um algoritmo de pré-alocação para o arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-144">Therefore, by default, when backing up a database using compression, the Database Engine uses a pre-allocation algorithm for the backup file.</span></span> <span data-ttu-id="e7e0d-145">Este algoritmo pré-aloca um percentual predefinido do tamanho do banco de dados para o arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-145">This algorithm pre-allocates a predefined percentage of the size of the database for the backup file.</span></span> <span data-ttu-id="e7e0d-146">Se for necessário mais espaço durante a operação de backup, o Mecanismo de Banco de Dados crescerá o arquivo.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-146">If more space is needed during the backup operation, the Database Engine grows the file.</span></span> <span data-ttu-id="e7e0d-147">Se o tamanho final for menor que o espaço alocado, no final da operação de backup, o Mecanismo de Banco de Dados reduzirá o arquivo para o tamanho final real do backup.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-147">If the final size is less than the allocated space, at the end of the backup operation, the Database Engine shrinks the file to the actual final size of the backup.</span></span>  
  
 <span data-ttu-id="e7e0d-148">Para permitir que o arquivo de backup somente cresça conforme o necessário para alcançar seu tamanho final, use o sinalizador de rastreamento 3042.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-148">To allow the backup file to grow only as needed to reach its final size, use trace flag 3042.</span></span> <span data-ttu-id="e7e0d-149">O sinalizador de rastreamento 3042 faz a operação de backup ignorar o algoritmo padrão de pré-alocação da compactação de backup.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-149">Trace flag 3042 causes the backup operation to bypass the default backup compression pre-allocation algorithm.</span></span> <span data-ttu-id="e7e0d-150">Este sinalizador de rastreamento será útil se você precisar salvar em espaço alocando somente o tamanho real necessário para o backup compactado.</span><span class="sxs-lookup"><span data-stu-id="e7e0d-150">This trace flag is useful if you need to save on space by allocating only the actual size required for the compressed backup.</span></span> <span data-ttu-id="e7e0d-151">Porém, usar este sinalizador de rastreamento pode causar uma pequena penalidade de desempenho (um possível aumento na duração da operação de backup).</span><span class="sxs-lookup"><span data-stu-id="e7e0d-151">However, using this trace flag might cause a slight performance penalty (a possible increase in the duration of the backup operation).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e7e0d-152">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="e7e0d-152">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e7e0d-153">Configurar compactação de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e7e0d-153">Configure Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
-   [<span data-ttu-id="e7e0d-154">Exibir ou configurar a opção de configuração de servidor backup compression default</span><span class="sxs-lookup"><span data-stu-id="e7e0d-154">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
-   [<span data-ttu-id="e7e0d-155">Usar o Resource Governor para limitar o uso de CPU por meio de compactação de backup &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e7e0d-155">Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;</span></span>](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [<span data-ttu-id="e7e0d-156">DBCC TRACEON &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e7e0d-156">DBCC TRACEON &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-transact-sql)  
  
-   [<span data-ttu-id="e7e0d-157">DBCC TRACEOFF &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e7e0d-157">DBCC TRACEOFF &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceoff-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="e7e0d-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7e0d-158">See Also</span></span>  
 <span data-ttu-id="e7e0d-159">[Visão geral do backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e7e0d-159">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="e7e0d-160">Sinalizadores de rastreamento &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e7e0d-160">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
