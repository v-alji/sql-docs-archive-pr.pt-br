---
title: Verificar arquivos em uso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccd65867-d4c0-43b2-8361-7fd41c6f79ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 51505b0dece146b7f6fcdf982e6f88a5715357e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573516"
---
# <a name="check-files-in-use"></a><span data-ttu-id="2e1df-102">Verificar arquivos em uso</span><span class="sxs-lookup"><span data-stu-id="2e1df-102">Check Files In Use</span></span>
  <span data-ttu-id="2e1df-103">Para evitar a necessidade de reiniciar o Windows após a instalação das atualizações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , use a página Verificar Arquivos em Uso para identificar processos que estão bloqueando arquivos necessários ao programa de Instalação de atualização do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e1df-103">To avoid restarting Windows after you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates, use the Check Files in Use page to identify processes that are locking files required by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] update Setup program.</span></span>  
  
 <span data-ttu-id="2e1df-104">Pare todos os aplicativos e serviços que façam conexões com as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo atualizado.</span><span class="sxs-lookup"><span data-stu-id="2e1df-104">Stop all applications and services that make connections to the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are being updated.</span></span> <span data-ttu-id="2e1df-105">Isso inclui parar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e1df-105">This includes stopping [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="2e1df-106">Se a Instalação determinar que arquivos estão bloqueados durante a instalação, talvez seja necessário reiniciar o computador após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="2e1df-106">If Setup determines that files are locked during installation, you might have to restart your computer after installation is completed.</span></span> <span data-ttu-id="2e1df-107">Se necessário, a Instalação solicitará que você reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="2e1df-107">If necessary, Setup prompts you to restart your computer.</span></span> <span data-ttu-id="2e1df-108">Se o programa de Instalação precisar parar um serviço durante a instalação, ele reiniciará o serviço após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="2e1df-108">If the Setup program must stop a service during installation, it will restart the service after installation is completed.</span></span>  
  
 <span data-ttu-id="2e1df-109">Para eliminar a necessidade de reiniciar o computador após a instalação, a Instalação exibirá uma lista de processos que estão bloqueando arquivos.</span><span class="sxs-lookup"><span data-stu-id="2e1df-109">To eliminate the requirement to restart your computer after installation, Setup displays a list of processes that are locking files.</span></span> <span data-ttu-id="2e1df-110">Pare ou termine os processos e os aplicativos na lista.</span><span class="sxs-lookup"><span data-stu-id="2e1df-110">Stop or end the processes and applications in the list.</span></span> <span data-ttu-id="2e1df-111">Em seguida, clique em **Atualizar verificação** para executar a verificação novamente.</span><span class="sxs-lookup"><span data-stu-id="2e1df-111">Then click **Refresh check** to rerun the check.</span></span> <span data-ttu-id="2e1df-112">Clique em **Parar verificação** para encerrar uma verificação que esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="2e1df-112">Click **Stop check** to end a check that is running.</span></span> <span data-ttu-id="2e1df-113">Se arquivos bloqueados não forem encontrados, a tabela estará vazia.</span><span class="sxs-lookup"><span data-stu-id="2e1df-113">If locked files are not found, the table is empty.</span></span> <span data-ttu-id="2e1df-114">Quando todos os processos bloqueados tiverem sido fechados ou parados, clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="2e1df-114">When all locked processes have been closed or stopped, click **Next** to continue.</span></span>  
  
 <span data-ttu-id="2e1df-115">A Instalação registra as informações nos arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="2e1df-115">Setup logs the information in the log files.</span></span> <span data-ttu-id="2e1df-116">Para obter mais informações sobre como exibir os arquivos de log, veja [Como exibir os arquivos de log da instalação do SQL Server](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) e [Como ler um arquivo de log da Instalação do SQL Server](https://go.microsoft.com/fwlink/?LinkID=134490).</span><span class="sxs-lookup"><span data-stu-id="2e1df-116">For more information about how to view the log files, see [View and Read SQL Server Setup Log Files](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) and [How to: Read a SQL Server Setup Log File](https://go.microsoft.com/fwlink/?LinkID=134490).</span></span>  
  
 <span data-ttu-id="2e1df-117">As seguintes informações estão incluídas no arquivo de log:</span><span class="sxs-lookup"><span data-stu-id="2e1df-117">The following information is included in the log file:</span></span>  
  
-   <span data-ttu-id="2e1df-118">Nome do processo</span><span class="sxs-lookup"><span data-stu-id="2e1df-118">Name of the process</span></span>  
  
-   <span data-ttu-id="2e1df-119">Nome do recurso do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e1df-119">Name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature</span></span>  
  
-   <span data-ttu-id="2e1df-120">Tipo de processo</span><span class="sxs-lookup"><span data-stu-id="2e1df-120">Process type</span></span>  
  
-   <span data-ttu-id="2e1df-121">Conta sob a qual o processo está sendo executado</span><span class="sxs-lookup"><span data-stu-id="2e1df-121">Account under which the process is running</span></span>  
  
-   <span data-ttu-id="2e1df-122">ID do Processo</span><span class="sxs-lookup"><span data-stu-id="2e1df-122">Process ID</span></span>  
  
-   <span data-ttu-id="2e1df-123">Nome do arquivo bloqueado</span><span class="sxs-lookup"><span data-stu-id="2e1df-123">Name of the file that is locked</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2e1df-124">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="2e1df-124">UI element list</span></span>  
  
|<span data-ttu-id="2e1df-125">Nome</span><span class="sxs-lookup"><span data-stu-id="2e1df-125">Name</span></span>|<span data-ttu-id="2e1df-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="2e1df-126">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2e1df-127">Processo</span><span class="sxs-lookup"><span data-stu-id="2e1df-127">Process</span></span>|<span data-ttu-id="2e1df-128">Exibe o nome completo do processo que está usando os arquivos a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="2e1df-128">Displays the full name of the process that is using the files to be updated.</span></span>|  
|<span data-ttu-id="2e1df-129">Type</span><span class="sxs-lookup"><span data-stu-id="2e1df-129">Type</span></span>|<span data-ttu-id="2e1df-130">Exibe o tipo de processo.</span><span class="sxs-lookup"><span data-stu-id="2e1df-130">Displays the type of process.</span></span>|  
|<span data-ttu-id="2e1df-131">Conta</span><span class="sxs-lookup"><span data-stu-id="2e1df-131">Account</span></span>|<span data-ttu-id="2e1df-132">Exibe a conta sob a qual o processo está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="2e1df-132">Displays the account under which the process is running.</span></span>|  
|<span data-ttu-id="2e1df-133">ID do Processo</span><span class="sxs-lookup"><span data-stu-id="2e1df-133">Process ID</span></span>|<span data-ttu-id="2e1df-134">Exibe a ID do processo.</span><span class="sxs-lookup"><span data-stu-id="2e1df-134">Displays the process ID.</span></span>|  
  
  
