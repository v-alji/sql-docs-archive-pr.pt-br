---
title: Iniciador do Daemon de Filtro de Texto Completo do SQL (guia Serviço) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 6aad7ebe-c4be-4d37-8536-61502f51faa2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8f0d9c76d7d92947dd17fe2ed6e912e3d6baa6bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582708"
---
# <a name="sql-full-text-filter-daemon-launcher-service-tab"></a><span data-ttu-id="ccf73-102">Iniciador do Daemon de Filtro de Texto Completo do SQL (guia Serviço)</span><span class="sxs-lookup"><span data-stu-id="ccf73-102">SQL Full-text Filter Daemon Launcher (Service Tab)</span></span>
  <span data-ttu-id="ccf73-103">A partir do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], o serviço do Iniciador do Daemon de Filtro de Texto Completo do SQL (Iniciador FDHOST) é usado pelo texto completo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ccf73-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text.</span></span> <span data-ttu-id="ccf73-104">Este serviço deverá estar em execução se você usar a pesquisa de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ccf73-104">This service must be running if you use full-text search.</span></span> <span data-ttu-id="ccf73-105">Para obter informações sobre os processos do host do daemon de filtro, consulte "Arquitetura da pesquisa de texto completo" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ccf73-105">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="ccf73-106">Use a guia **Serviço**na caixa de diálogo **Propriedades do Iniciador do Daemon de Filtro de Texto Completo do SQL** para exibir ou especificar as opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="ccf73-106">Use the **Service**tab on the **SQL Full-text Filter Daemon LauncherProperties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ccf73-107">Opções</span><span class="sxs-lookup"><span data-stu-id="ccf73-107">Options</span></span>  
 <span data-ttu-id="ccf73-108">**Caminho Binário**</span><span class="sxs-lookup"><span data-stu-id="ccf73-108">**Binary Path**</span></span>  
 <span data-ttu-id="ccf73-109">Lista o local dos arquivos de programas usados por este serviço.</span><span class="sxs-lookup"><span data-stu-id="ccf73-109">Lists the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="ccf73-110">**Controle de Erro**</span><span class="sxs-lookup"><span data-stu-id="ccf73-110">**Error Control**</span></span>  
 <span data-ttu-id="ccf73-111">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="ccf73-111">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="ccf73-112">Se o serviço não for iniciado durante a inicialização do computador, o programa de inicialização registrará o erro em log e exibirá uma caixa de mensagem pop-up, mas continuará a operação de inicialização.</span><span class="sxs-lookup"><span data-stu-id="ccf73-112">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="ccf73-113">Esse valor não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="ccf73-113">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="ccf73-114">**Código de Saída**</span><span class="sxs-lookup"><span data-stu-id="ccf73-114">**Exit Code**</span></span>  
 <span data-ttu-id="ccf73-115">Quando ocorre um erro, o número do erro é exibido nesta caixa.</span><span class="sxs-lookup"><span data-stu-id="ccf73-115">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="ccf73-116">Use esse número para solucionar problemas de falhas procurando-o na Base de Dados de Conhecimento [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou forneça o número à sua equipe de suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="ccf73-116">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="ccf73-117">**Nome do Host**</span><span class="sxs-lookup"><span data-stu-id="ccf73-117">**Host Name**</span></span>  
 <span data-ttu-id="ccf73-118">Exibe o nome do computador ou cluster que está executando o serviço [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccf73-118">Displays the name of the computer or cluster running the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="ccf73-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ccf73-119">**Name**</span></span>  
 <span data-ttu-id="ccf73-120">Indica o nome para exibição do serviço.</span><span class="sxs-lookup"><span data-stu-id="ccf73-120">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="ccf73-121">**ID do Processo**</span><span class="sxs-lookup"><span data-stu-id="ccf73-121">**Process ID**</span></span>  
 <span data-ttu-id="ccf73-122">Exibe a identificação do processo do Windows.</span><span class="sxs-lookup"><span data-stu-id="ccf73-122">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="ccf73-123">**Tipo de Serviço do SQL**</span><span class="sxs-lookup"><span data-stu-id="ccf73-123">**SQL Service Type**</span></span>  
 <span data-ttu-id="ccf73-124">Exibe o tipo de serviço fornecido a processos de chamada.</span><span class="sxs-lookup"><span data-stu-id="ccf73-124">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ccf73-125">instala vários serviços.</span><span class="sxs-lookup"><span data-stu-id="ccf73-125">installs several services.</span></span>  
  
 <span data-ttu-id="ccf73-126">**Modo Inicial**</span><span class="sxs-lookup"><span data-stu-id="ccf73-126">**Start Mode**</span></span>  
 <span data-ttu-id="ccf73-127">Defina este serviço com as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="ccf73-127">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="ccf73-128">Manual: este serviço não é iniciado automaticamente na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="ccf73-128">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="ccf73-129">Você deve iniciá-lo usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager ou outra ferramenta.</span><span class="sxs-lookup"><span data-stu-id="ccf73-129">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="ccf73-130">Automático: este serviço tenta ser iniciado na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="ccf73-130">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="ccf73-131">Desabilitado: este serviço não pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="ccf73-131">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="ccf73-132">**State**</span><span class="sxs-lookup"><span data-stu-id="ccf73-132">**State**</span></span>  
 <span data-ttu-id="ccf73-133">Indica se este serviço está sendo executado, se está parado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="ccf73-133">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="ccf73-134">" **...** " indica que há uma alteração de estado pendente.</span><span class="sxs-lookup"><span data-stu-id="ccf73-134">"**...**" indicates a state change is pending.</span></span>  
  
  
