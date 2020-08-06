---
title: Habilitar e configurar FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], enabling
ms.assetid: 78737e19-c65b-48d9-8fa9-aa6f1e1bce73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f6c0e505bd32636d045519b36e439bc21c7079d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568651"
---
# <a name="enable-and-configure-filestream"></a><span data-ttu-id="59a72-102">Habilitar e configurar FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="59a72-102">Enable and Configure FILESTREAM</span></span>
  <span data-ttu-id="59a72-103">Antes de começar a usar FILESTREAM, é necessário habilitá-lo na instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59a72-103">Before you can start to use FILESTREAM, you must enable FILESTREAM on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="59a72-104">Este tópico descreve como habilitar o FILESTREAM usando o SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="59a72-104">This topic describes how to enable FILESTREAM by using SQL Server Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59a72-105">Você não pode habilitar o FILESTREAM em uma versão de 32 bits do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sendo executada em um sistema operacional de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="59a72-105">You cannot enable FILESTREAM on a 32-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on a 64-bit operating system.</span></span>  
  
##  <a name="enabling-filestream"></a><a name="enabling"></a> <span data-ttu-id="59a72-106">Habilitando FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="59a72-106">Enabling FILESTREAM</span></span>  
  
#### <a name="to-enable-and-change-filestream-settings"></a><span data-ttu-id="59a72-107">Para habilitar e alterar configurações de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="59a72-107">To enable and change FILESTREAM settings</span></span>  
  
1.  <span data-ttu-id="59a72-108">No menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="59a72-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="59a72-109">Na lista de serviços, clique com o botão direito do mouse em **Serviços do SQL Server**e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="59a72-109">In the list of services, right-click **SQL Server Services**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="59a72-110">No snap-in **SQL Server Configuration Manager** , localize a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na qual deseja habilitar o FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="59a72-110">In the **SQL Server Configuration Manager** snap-in, locate the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to enable FILESTREAM.</span></span>  
  
4.  <span data-ttu-id="59a72-111">Clique com o botão direito do mouse na instância e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="59a72-111">Right-click the instance, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="59a72-112">Na caixa de diálogo **Propriedades do SQL Server** , clique na guia **FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="59a72-112">In the **SQL Server Properties** dialog box, click the **FILESTREAM** tab.</span></span>  
  
6.  <span data-ttu-id="59a72-113">Marque a caixa de seleção **Habilitar FILESTREAM para acesso a Transact-SQL** .</span><span class="sxs-lookup"><span data-stu-id="59a72-113">Select the **Enable FILESTREAM for Transact-SQL access** check box.</span></span>  
  
7.  <span data-ttu-id="59a72-114">Se você quiser ler e gravar dados FILESTREAM no Windows, clique em **Habilitar FILESTREAM para acesso de streaming de E/S de arquivos**.</span><span class="sxs-lookup"><span data-stu-id="59a72-114">If you want to read and write FILESTREAM data from Windows, click **Enable FILESTREAM for file I/O streaming access**.</span></span> <span data-ttu-id="59a72-115">Insira o nome do compartilhamento do Windows na caixa **Nome de Compartilhamento do Windows** .</span><span class="sxs-lookup"><span data-stu-id="59a72-115">Enter the name of the Windows share in the **Windows Share Name** box.</span></span>  
  
8.  <span data-ttu-id="59a72-116">Se os clientes remotos precisarem acessar os dados do FILESTREAM armazenados em seu compartilhamento, selecione **Permitir que os clientes remotos tenham acesso de streaming aos dados de FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="59a72-116">If remote clients must access the FILESTREAM data that is stored on this share, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span>  
  
9. <span data-ttu-id="59a72-117">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="59a72-117">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="59a72-118">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique em **Nova Consulta** para exibir o Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="59a72-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
11. <span data-ttu-id="59a72-119">No Editor de Consultas, insira o seguinte código [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="59a72-119">In Query Editor, enter the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
    ```sql  
    EXEC sp_configure filestream_access_level, 2  
    RECONFIGURE  
    ```  
  
12. <span data-ttu-id="59a72-120">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="59a72-120">Click **Execute**.</span></span>  
  
13. <span data-ttu-id="59a72-121">Reinicie o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59a72-121">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  

  
##  <a name="best-practices"></a><a name="best"></a> <span data-ttu-id="59a72-122">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="59a72-122">Best Practices</span></span>  
  
###  <a name="physical-configuration-and-maintenance"></a><a name="config"></a><span data-ttu-id="59a72-123">Configuração física e manutenção</span><span class="sxs-lookup"><span data-stu-id="59a72-123">Physical Configuration and Maintenance</span></span>  
 <span data-ttu-id="59a72-124">Ao configurar volumes de armazenamento de FILESTREAM, considere as seguintes diretrizes:</span><span class="sxs-lookup"><span data-stu-id="59a72-124">When you set up FILESTREAM storage volumes, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="59a72-125">Desative nomes de arquivos curtos em sistemas de computador FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="59a72-125">Turn off short file names on FILESTREAM computer systems.</span></span> <span data-ttu-id="59a72-126">Nomes de arquivos curtos precisam de significativamente mais tempo para serem criados.</span><span class="sxs-lookup"><span data-stu-id="59a72-126">Short file names take significantly longer to create.</span></span> <span data-ttu-id="59a72-127">Para desabilitar nomes de arquivos curtos, use o utilitário **fsutil** do Windows.</span><span class="sxs-lookup"><span data-stu-id="59a72-127">To disable short file names, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="59a72-128">Desfragmente regularmente os sistemas de computador FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="59a72-128">Regularly defragment FILESTREAM computer systems.</span></span>  
  
-   <span data-ttu-id="59a72-129">Use clusters de NTFS de 64 KB.</span><span class="sxs-lookup"><span data-stu-id="59a72-129">Use 64-KB NTFS clusters.</span></span> <span data-ttu-id="59a72-130">Volumes compactados devem ser definidos como clusters de NTFS de 4 KB.</span><span class="sxs-lookup"><span data-stu-id="59a72-130">Compressed volumes must be set to 4-KB NTFS clusters.</span></span>  
  
-   <span data-ttu-id="59a72-131">Desabilite a indexação em volumes de FILESTREAM e defina **disablelastaccess** . Para definir **disablelastaccess**, use o utilitário **fsutil** do Windows.</span><span class="sxs-lookup"><span data-stu-id="59a72-131">Disable indexing on FILESTREAM volumes and set **disablelastaccess** To set **disablelastaccess**, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="59a72-132">Desabilite a verificação antivírus de volumes FILESTREAM quando ela for desnecessária.</span><span class="sxs-lookup"><span data-stu-id="59a72-132">Disable antivirus scanning of FILESTREAM volumes when it is not unnecessary.</span></span> <span data-ttu-id="59a72-133">Se a verificação antivírus for necessária, evite políticas de configuração que excluirão automaticamente os arquivos incorretos.</span><span class="sxs-lookup"><span data-stu-id="59a72-133">If antivirus scanning is necessary, avoid setting policies that will automatically delete offending files.</span></span>  
  
-   <span data-ttu-id="59a72-134">Configure e ajuste o nível de RAID para tolerância a falhas e para o desempenho exigido por um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59a72-134">Set up and tune the RAID level for fault tolerance and the performance that is required by an application.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="59a72-135">Nível de RAID</span><span class="sxs-lookup"><span data-stu-id="59a72-135">RAID level</span></span>|<span data-ttu-id="59a72-136">Desempenho de gravação</span><span class="sxs-lookup"><span data-stu-id="59a72-136">Write performance</span></span>|<span data-ttu-id="59a72-137">Desempenho de leitura</span><span class="sxs-lookup"><span data-stu-id="59a72-137">Read performance</span></span>|<span data-ttu-id="59a72-138">Tolerância a falhas</span><span class="sxs-lookup"><span data-stu-id="59a72-138">Fault tolerance</span></span>|<span data-ttu-id="59a72-139">Comentários</span><span class="sxs-lookup"><span data-stu-id="59a72-139">Remarks</span></span>|  
|<span data-ttu-id="59a72-140">RAID 5</span><span class="sxs-lookup"><span data-stu-id="59a72-140">RAID 5</span></span>|<span data-ttu-id="59a72-141">Normal</span><span class="sxs-lookup"><span data-stu-id="59a72-141">Normal</span></span>|<span data-ttu-id="59a72-142">Normal</span><span class="sxs-lookup"><span data-stu-id="59a72-142">Normal</span></span>|<span data-ttu-id="59a72-143">Excelente</span><span class="sxs-lookup"><span data-stu-id="59a72-143">Excellent</span></span>|<span data-ttu-id="59a72-144">O desempenho é melhor do que o de um disco ou JBOD; e menor do que o do RAID 0 ou do RAID 5 com distribuição.</span><span class="sxs-lookup"><span data-stu-id="59a72-144">Performance is better than one disk or JBOD; and less than RAID 0 or RAID 5 with striping.</span></span>|  
|<span data-ttu-id="59a72-145">RAID 0</span><span class="sxs-lookup"><span data-stu-id="59a72-145">RAID 0</span></span>|<span data-ttu-id="59a72-146">Excelente</span><span class="sxs-lookup"><span data-stu-id="59a72-146">Excellent</span></span>|<span data-ttu-id="59a72-147">Excelente</span><span class="sxs-lookup"><span data-stu-id="59a72-147">Excellent</span></span>|<span data-ttu-id="59a72-148">Nenhum</span><span class="sxs-lookup"><span data-stu-id="59a72-148">None</span></span>||  
|<span data-ttu-id="59a72-149">RAID 5 + distribuição</span><span class="sxs-lookup"><span data-stu-id="59a72-149">RAID 5 + stripping</span></span>|<span data-ttu-id="59a72-150">Excelente</span><span class="sxs-lookup"><span data-stu-id="59a72-150">Excellent</span></span>|<span data-ttu-id="59a72-151">Excelente</span><span class="sxs-lookup"><span data-stu-id="59a72-151">Excellent</span></span>|<span data-ttu-id="59a72-152">Excelente</span><span class="sxs-lookup"><span data-stu-id="59a72-152">Excellent</span></span>|<span data-ttu-id="59a72-153">A opção mais cara.</span><span class="sxs-lookup"><span data-stu-id="59a72-153">Most expensive option.</span></span>|  
  

  
###  <a name="physical-database-design"></a><a name="database"></a><span data-ttu-id="59a72-154">Design de banco de dados físico</span><span class="sxs-lookup"><span data-stu-id="59a72-154">Physical Database Design</span></span>  
 <span data-ttu-id="59a72-155">Ao criar um banco de dados de FILESTREAM, considere as seguintes diretrizes:</span><span class="sxs-lookup"><span data-stu-id="59a72-155">When you design a FILESTREAM database, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="59a72-156">As colunas FILESTREAM devem ser acompanhadas por uma `uniqueidentifier` coluna rowguid correspondente.</span><span class="sxs-lookup"><span data-stu-id="59a72-156">FILESTREAM columns must be accompanied by a corresponding `uniqueidentifier`ROWGUID column.</span></span> <span data-ttu-id="59a72-157">Esses tipos de tabelas também devem ser acompanhados por um índice exclusivo.</span><span class="sxs-lookup"><span data-stu-id="59a72-157">These kinds of tables must also be accompanied by a unique index.</span></span> <span data-ttu-id="59a72-158">Normalmente esse índice não é um índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="59a72-158">Typically this index is not a clustered index.</span></span> <span data-ttu-id="59a72-159">Se a lógica corporativa do bancos de dados exigir um índice clusterizado, você precisará verificar se os valores armazenados no índice não são aleatórios.</span><span class="sxs-lookup"><span data-stu-id="59a72-159">If the databases business logic requires a clustered index, you have to make sure that the values stored in the index are not random.</span></span> <span data-ttu-id="59a72-160">Valores aleatórios farão com que o índice seja reorganizado toda vez que uma linha for adicionada ou removida da tabela.</span><span class="sxs-lookup"><span data-stu-id="59a72-160">Random values will cause the index to be reordered every time that a row is added or removed from the table.</span></span>  
  
-   <span data-ttu-id="59a72-161">Por razões de desempenho, grupos de arquivos e contêineres de FILESTREAM devem residir em volumes diferentes do sistema operacional, do banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , do log do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , do tempdb ou do arquivo de paginação.</span><span class="sxs-lookup"><span data-stu-id="59a72-161">For performance reasons, FILESTREAM filegroups and containers should reside on volumes other than the operating system, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log, tempdb, or paging file.</span></span>  
  
-   <span data-ttu-id="59a72-162">Gerenciamento e políticas de espaço não são diretamente suportados por FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="59a72-162">Space management and policies are not directly supported by FILESTREAM.</span></span> <span data-ttu-id="59a72-163">No entanto, você pode gerenciar espaço e aplicar políticas indiretamente atribuindo cada grupo de arquivos de FILESTREAM a um volume separado e usando os recursos do gerenciamento do volume.</span><span class="sxs-lookup"><span data-stu-id="59a72-163">However, you can manage space and apply policies indirectly by assigning each FILESTREAM filegroup to a separate volume and using the volume's management features.</span></span>  
  
  
