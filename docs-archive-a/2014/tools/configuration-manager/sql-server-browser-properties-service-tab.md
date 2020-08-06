---
title: Propriedades do SQL Server Browser (guia Serviço) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 98ace9b0-72d5-4b72-9b7b-11fbc490981a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 200e45648b94e26c5e808e9a817cfe01866e6a65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569799"
---
# <a name="sql-server-browser-properties-service-tab"></a><span data-ttu-id="e5545-102">Propriedades do Navegador do SQL Server (guia Serviço)</span><span class="sxs-lookup"><span data-stu-id="e5545-102">SQL Server Browser Properties (Service Tab)</span></span>
  <span data-ttu-id="e5545-103">O programa Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é executado como um serviço no servidor.</span><span class="sxs-lookup"><span data-stu-id="e5545-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> <span data-ttu-id="e5545-104">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser escuta as solicitações de entrada de recursos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e fornece informações sobre as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="e5545-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 <span data-ttu-id="e5545-105">Use a guia **Serviço** na caixa de diálogo **Propriedades do Navegador do SQL Server** para exibir as opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="e5545-105">Use the **Service** tab on the **SQL Server Browser Properties** dialog box to view the following options.</span></span> <span data-ttu-id="e5545-106">Todas as propriedades, exceto **Modo Inicial** , são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="e5545-106">All properties except **Start Mode** are read-only.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e5545-107">Opções</span><span class="sxs-lookup"><span data-stu-id="e5545-107">Options</span></span>  
 <span data-ttu-id="e5545-108">**Caminho Binário**</span><span class="sxs-lookup"><span data-stu-id="e5545-108">**Binary Path**</span></span>  
 <span data-ttu-id="e5545-109">Exibe o local dos arquivos de programas usados por este serviço.</span><span class="sxs-lookup"><span data-stu-id="e5545-109">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="e5545-110">**Controle de Erro**</span><span class="sxs-lookup"><span data-stu-id="e5545-110">**Error Control**</span></span>  
 <span data-ttu-id="e5545-111">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="e5545-111">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="e5545-112">Se o serviço não for iniciado durante a inicialização do computador, o programa de inicialização registrará o erro em log e exibirá uma caixa de mensagem pop-up, mas continuará a operação de inicialização.</span><span class="sxs-lookup"><span data-stu-id="e5545-112">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="e5545-113">Esse valor não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="e5545-113">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="e5545-114">**Código de Saída**</span><span class="sxs-lookup"><span data-stu-id="e5545-114">**Exit Code**</span></span>  
 <span data-ttu-id="e5545-115">Quando ocorre um erro, o número do erro é exibido nesta caixa.</span><span class="sxs-lookup"><span data-stu-id="e5545-115">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="e5545-116">Use esse número para solucionar problemas de falhas procurando-o na Base de Dados de Conhecimento [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou forneça o número à sua equipe de suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e5545-116">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="e5545-117">**Nome do Host**</span><span class="sxs-lookup"><span data-stu-id="e5545-117">**Host Name**</span></span>  
 <span data-ttu-id="e5545-118">Exibe o nome do computador ou do cluster que está executando o serviço do Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5545-118">Displays the name of the computer or cluster running the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="e5545-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e5545-119">**Name**</span></span>  
 <span data-ttu-id="e5545-120">Indica o nome para exibição do serviço.</span><span class="sxs-lookup"><span data-stu-id="e5545-120">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="e5545-121">**ID do Processo**</span><span class="sxs-lookup"><span data-stu-id="e5545-121">**Process ID**</span></span>  
 <span data-ttu-id="e5545-122">Exibe a identificação do processo do Windows.</span><span class="sxs-lookup"><span data-stu-id="e5545-122">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="e5545-123">**Tipo de Serviço**</span><span class="sxs-lookup"><span data-stu-id="e5545-123">**Service Type**</span></span>  
 <span data-ttu-id="e5545-124">Exibe o tipo de serviço fornecido a processos de chamada.</span><span class="sxs-lookup"><span data-stu-id="e5545-124">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e5545-125">instala vários serviços.</span><span class="sxs-lookup"><span data-stu-id="e5545-125">installs several services.</span></span>  
  
 <span data-ttu-id="e5545-126">**Modo Inicial**</span><span class="sxs-lookup"><span data-stu-id="e5545-126">**Start Mode**</span></span>  
 <span data-ttu-id="e5545-127">Defina este serviço com as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e5545-127">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="e5545-128">Manual: este serviço não é iniciado automaticamente na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="e5545-128">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="e5545-129">Você deve iniciá-lo usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager ou outra ferramenta.</span><span class="sxs-lookup"><span data-stu-id="e5545-129">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="e5545-130">Automático: este serviço tenta ser iniciado na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="e5545-130">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="e5545-131">Desabilitado: este serviço não pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="e5545-131">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="e5545-132">**State**</span><span class="sxs-lookup"><span data-stu-id="e5545-132">**State**</span></span>  
 <span data-ttu-id="e5545-133">Indica se este serviço está sendo executado, se está parado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="e5545-133">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="e5545-134">" **...** " indica que há uma alteração de estado pendente.</span><span class="sxs-lookup"><span data-stu-id="e5545-134">"**...**" indicates a state change is pending.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5545-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5545-135">See Also</span></span>  
 [<span data-ttu-id="e5545-136">Serviço Navegador do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5545-136">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
