---
title: Serviço Gravador do SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- VDI [SQL Server]
- restoring [SQL Server], SQL Writer Service
- backups [SQL Server], while SQL Server running
- Volume Shadow Copy Service
- volume backups while running [SQL Server]
- Virtual Backup Device Interface [SQL Server]
- SQL Writer Service
- services [SQL Server], SQL Writer
- MSDE Writer
- VSS
ms.assetid: 0f299867-f499-4c2a-ad6f-b2ef1869381d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 310722c6617c7a2c9e0f384ec23ae371ab230536
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569638"
---
# <a name="sql-writer-service"></a><span data-ttu-id="bf693-102">Serviço do gravador do SQL</span><span class="sxs-lookup"><span data-stu-id="bf693-102">SQL Writer Service</span></span>
  <span data-ttu-id="bf693-103">O Serviço Gravador do SQL oferece funcionalidade adicional para fazer backup e restauração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio da estrutura do Serviço de Cópias de Sombra de Volume.</span><span class="sxs-lookup"><span data-stu-id="bf693-103">The SQL Writer Service provides added functionality for backup and restore of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the Volume Shadow Copy Service framework.</span></span>  
  
 <span data-ttu-id="bf693-104">O Serviço Gravador do SQL é instalado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bf693-104">The SQL Writer Service is installed automatically.</span></span> <span data-ttu-id="bf693-105">Deve estar em execução quando o aplicativo VSS (Volume Shadow Copy Service) pedir um backup ou uma restauração.</span><span class="sxs-lookup"><span data-stu-id="bf693-105">It must be running when the Volume Shadow Copy Service (VSS) application requests a backup or restore.</span></span> <span data-ttu-id="bf693-106">Para configurar o serviço, use o miniaplicativo [!INCLUDE[msCoName](../../includes/msconame-md.md)] do Windows Services.</span><span class="sxs-lookup"><span data-stu-id="bf693-106">To configure the service, use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Services applet.</span></span> <span data-ttu-id="bf693-107">O Serviço Gravador do SQL é instalado em todos os sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="bf693-107">The SQL Writer Service installs on all operating systems.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="bf693-108">Finalidade</span><span class="sxs-lookup"><span data-stu-id="bf693-108">Purpose</span></span>  
 <span data-ttu-id="bf693-109">Quando está em execução, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] bloqueia os arquivos de dados e tem acesso exclusivo a eles.</span><span class="sxs-lookup"><span data-stu-id="bf693-109">When running, [!INCLUDE[ssDE](../../includes/ssde-md.md)] locks and has exclusive access to the data files.</span></span> <span data-ttu-id="bf693-110">Quando o Serviço Gravador do SQL não está em execução, os programas de backup em execução no Windows não têm acesso aos arquivos de dados e os backups devem ser executados usando o backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf693-110">When the SQL Writer Service is not running, backup programs running in Windows do not have access to the data files, and backups must be performed using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup.</span></span>  
  
 <span data-ttu-id="bf693-111">Use o Serviço Gravador do SQL para permitir que os programas de backup do Windows copiem arquivos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enquanto o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver executando.</span><span class="sxs-lookup"><span data-stu-id="bf693-111">Use the SQL Writer Service to permit Windows backup programs to copy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data files while [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
## <a name="volume-shadow-copy-service"></a><span data-ttu-id="bf693-112">Serviço de cópias de sombra de volume</span><span class="sxs-lookup"><span data-stu-id="bf693-112">Volume Shadow Copy Service</span></span>  
 <span data-ttu-id="bf693-113">O VSS é um conjunto de APIs COM que implementa uma estrutura para permitir que backups dos volumes sejam feitos enquanto os aplicativos em um sistema continuam a gravar nos volumes.</span><span class="sxs-lookup"><span data-stu-id="bf693-113">The VSS is a set of COM APIs that implements a framework to allow volume backups to be performed while applications on a system continue to write to the volumes.</span></span> <span data-ttu-id="bf693-114">O VSS oferece uma interface consistente que permite a coordenação entre os aplicativos de usuário que atualizam dados em disco (gravadores) e os aplicativos de backup (solicitantes).</span><span class="sxs-lookup"><span data-stu-id="bf693-114">The VSS provides a consistent interface that allows coordination between user applications that update data on disk (writers) and those that back up applications (requestors).</span></span>  
  
 <span data-ttu-id="bf693-115">O VSS captura e copia imagens estáveis para backup em sistemas em execução, particularmente servidores, sem degradar indevidamente o desempenho e a estabilidade dos serviços que oferecem.</span><span class="sxs-lookup"><span data-stu-id="bf693-115">The VSS captures and copies stable images for backup on running systems, particularly servers, without unduly degrading the performance and stability of the services they provide.</span></span> <span data-ttu-id="bf693-116">Para obter mais informações sobre o VSS, consulte sua documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="bf693-116">For more information on the VSS, see your Windows documentation.</span></span>  
  
## <a name="virtual-backup-device-interface-vdi"></a><span data-ttu-id="bf693-117">VDI (Virtual Backup Device Interface)</span><span class="sxs-lookup"><span data-stu-id="bf693-117">Virtual Backup Device Interface (VDI)</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bf693-118">oferece uma API chamada VDI que permite que fornecedores de software independente integrem o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em seus produtos para dar suporte a operações de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="bf693-118">provides an API called Virtual Backup Device Interface (VDI) that enables independent software vendors to integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into their products for providing support for backup and restore operations.</span></span> <span data-ttu-id="bf693-119">Essas APIs são criadas para prover confiabilidade e desempenho máximos, e dão suporte a todas as funcionalidades de backup e de restauração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , inclusive todas as capacidades de backup hot e instantâneo.</span><span class="sxs-lookup"><span data-stu-id="bf693-119">These APIs are engineered to provide maximum reliability and performance, and support the full range of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore functionality, including the full range of hot and snapshot backup capabilities.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="bf693-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="bf693-120">Permissions</span></span>  
 <span data-ttu-id="bf693-121">O Serviço Gravador do SQL deve ser executado na conta **Sistema Local** .</span><span class="sxs-lookup"><span data-stu-id="bf693-121">The SQL Writer service must run under the **Local System** account.</span></span> <span data-ttu-id="bf693-122">O Serviço Gravador do SQL usa o logon **NT Service\SQLWriter** para se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf693-122">The SQL Writer service uses the **NT Service\SQLWriter** login to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bf693-123">O uso do logon **NT Service\SQLWriter** permite que o processo do Gravador do SQL seja executado no nível mais baixo de privilégio em uma conta designada como **nenhum logon**, que limita a vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="bf693-123">Using the **NT Service\SQLWriter** login allows the SQL Writer process to run at a lower privilege level in an account designated as **no login**, which limits vulnerability.</span></span> <span data-ttu-id="bf693-124">Se o serviço do Gravador do SQL estiver desabilitado, qualquer utilitário que confie em instantâneos do VSS, como o System Center Data Protection Manager, bem como em outros produtos de terceiros, será interrompido, ou pior, correrá o risco de obter backups de bancos de dados que não estavam consistentes.</span><span class="sxs-lookup"><span data-stu-id="bf693-124">If the SQL Writer service is disabled, then any utility which in relies on VSS snapshots, such as System Center Data Protection Manager, as well as some other 3rd-party products, would be broken, or worse, at risk of taking backups of databases which were not consistent.</span></span> <span data-ttu-id="bf693-125">Se nem o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o sistema em que é executado, nem o sistema host (no caso de uma máquina virtual), precisarem usar qualquer coisa além do backup de [!INCLUDE[tsql](../../includes/tsql-md.md)] , o serviço do Gravador do SQL poderá seguramente ser desabilitado e o logon será removido.</span><span class="sxs-lookup"><span data-stu-id="bf693-125">If neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the system it runs on, nor the host system (in the event of a virtual machine), need to use anything besides [!INCLUDE[tsql](../../includes/tsql-md.md)] backup, then the SQL Writer service can be safely disabled and the login removed.</span></span>  <span data-ttu-id="bf693-126">Observe que o serviço do Gravador do SQL pode ser chamado por um backup em nível de sistema ou de volume, seja o backup diretamente baseado em instantâneo ou não.</span><span class="sxs-lookup"><span data-stu-id="bf693-126">Note that the SQL Writer service may be invoked by a system or volume level backup, whether the backup is directly snapshot-based or not.</span></span> <span data-ttu-id="bf693-127">Alguns produtos de backup de sistema usam o VSS para evitar serem bloqueados por arquivos abertos ou bloqueados.</span><span class="sxs-lookup"><span data-stu-id="bf693-127">Some system backup products use VSS to avoid being blocked by open or locked files.</span></span> <span data-ttu-id="bf693-128">O Serviço Gravador do SQL precisa de permissões elevadas no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pois, no decorrer de suas atividades, ele congelará brevemente qualquer E/S para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf693-128">The SQL Writer service needs elevated permissions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because in the course of its activities it briefly freezes all I/O for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="features"></a><span data-ttu-id="bf693-129">Recursos</span><span class="sxs-lookup"><span data-stu-id="bf693-129">Features</span></span>  
 <span data-ttu-id="bf693-130">O Gravador do SQL dá suporte a:</span><span class="sxs-lookup"><span data-stu-id="bf693-130">SQL Writer supports:</span></span>  
  
-   <span data-ttu-id="bf693-131">Backup e restauração de banco de dados completos inclusive catálogos de texto completo</span><span class="sxs-lookup"><span data-stu-id="bf693-131">Full database backup and restore including full-text catalogs</span></span>  
  
-   <span data-ttu-id="bf693-132">Backup diferencial e restauração</span><span class="sxs-lookup"><span data-stu-id="bf693-132">Differential backup and restore</span></span>  
  
-   <span data-ttu-id="bf693-133">Restaurar e mover</span><span class="sxs-lookup"><span data-stu-id="bf693-133">Restore with move</span></span>  
  
-   <span data-ttu-id="bf693-134">Renomear banco de dados</span><span class="sxs-lookup"><span data-stu-id="bf693-134">Database rename</span></span>  
  
-   <span data-ttu-id="bf693-135">Backup somente cópia</span><span class="sxs-lookup"><span data-stu-id="bf693-135">Copy-only backup</span></span>  
  
-   <span data-ttu-id="bf693-136">Recuperação automática de instantâneo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="bf693-136">Auto-recovery of database snapshot</span></span>  
  
 <span data-ttu-id="bf693-137">O Gravador do SQL não dá suporte a:</span><span class="sxs-lookup"><span data-stu-id="bf693-137">SQL Writer does not support:</span></span>  
  
-   <span data-ttu-id="bf693-138">Backups de log</span><span class="sxs-lookup"><span data-stu-id="bf693-138">Log backups</span></span>  
  
-   <span data-ttu-id="bf693-139">Backup de arquivo e grupo de arquivos</span><span class="sxs-lookup"><span data-stu-id="bf693-139">File and filegroup backup</span></span>  
  
-   <span data-ttu-id="bf693-140">Restauração de página</span><span class="sxs-lookup"><span data-stu-id="bf693-140">Page restore</span></span>  
  
  
