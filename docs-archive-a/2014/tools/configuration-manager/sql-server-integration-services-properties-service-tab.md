---
title: Propriedades do SQL Server Integration Services (guia Serviço) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 37f0acd9-c96f-48fd-9b53-2ca0097af242
author: stevestein
ms.author: sstein
ms.openlocfilehash: a752bdeab3c99ac97445e3281d3165a2d8f79866
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582703"
---
# <a name="sql-server-integration-services-properties-service-tab"></a><span data-ttu-id="d7e44-102">Propriedades do SQL Server Integration Services (guia Serviço)</span><span class="sxs-lookup"><span data-stu-id="d7e44-102">SQL Server Integration Services Properties (Service Tab)</span></span>
  <span data-ttu-id="d7e44-103">Use a guia **Serviço**na caixa de diálogo [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]Propriedades**do** para exibir ou especificar as opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="d7e44-103">Use the **Service**tab on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d7e44-104">Opções</span><span class="sxs-lookup"><span data-stu-id="d7e44-104">Options</span></span>  
 <span data-ttu-id="d7e44-105">**Caminho Binário**</span><span class="sxs-lookup"><span data-stu-id="d7e44-105">**Binary Path**</span></span>  
 <span data-ttu-id="d7e44-106">Exibe o local dos arquivos de programas usados por este serviço.</span><span class="sxs-lookup"><span data-stu-id="d7e44-106">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="d7e44-107">**Controle de Erro**</span><span class="sxs-lookup"><span data-stu-id="d7e44-107">**Error Control**</span></span>  
 <span data-ttu-id="d7e44-108">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="d7e44-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="d7e44-109">Se o serviço não for iniciado durante a inicialização do computador, o programa de inicialização registrará o erro em log e exibirá uma caixa de mensagem pop-up, mas continuará a operação de inicialização.</span><span class="sxs-lookup"><span data-stu-id="d7e44-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="d7e44-110">Esse valor não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="d7e44-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="d7e44-111">**Código de Saída**</span><span class="sxs-lookup"><span data-stu-id="d7e44-111">**Exit Code**</span></span>  
 <span data-ttu-id="d7e44-112">O código de erro do Windows no [!INCLUDE[msCoName](../../includes/msconame-md.md)] que define todos os problemas encontrados na inicialização ou interrupção do serviço.</span><span class="sxs-lookup"><span data-stu-id="d7e44-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows error code defining any problems encountered in starting or stopping the service.</span></span> <span data-ttu-id="d7e44-113">Esta propriedade é definida como **ERROR_SERVICE_SPECIFIC_ERROR** (1066) quando o erro é exclusivo do serviço representado por essa classe, e as informações sobre o erro estão disponíveis na propriedade **ServiceSpecificExitCode** .</span><span class="sxs-lookup"><span data-stu-id="d7e44-113">This property is set to **ERROR_SERVICE_SPECIFIC_ERROR** (1066) when the error is unique to the service represented by this class, and information about the error is available in the **ServiceSpecificExitCode** property.</span></span> <span data-ttu-id="d7e44-114">O serviço define esse valor como NO_ERROR (0) quando está sendo executado, e novamente no término normal.</span><span class="sxs-lookup"><span data-stu-id="d7e44-114">The service sets this value to NO_ERROR (0) when running, and again upon normal termination.</span></span>  
  
 <span data-ttu-id="d7e44-115">**Nome do Host**</span><span class="sxs-lookup"><span data-stu-id="d7e44-115">**Host Name**</span></span>  
 <span data-ttu-id="d7e44-116">Exibe o nome do computador ou cluster que está executando o serviço [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7e44-116">Displays the name of the computer or cluster running the [!INCLUDE[ssIS](../../includes/ssis-md.md)] service.</span></span>  
  
 <span data-ttu-id="d7e44-117">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d7e44-117">**Name**</span></span>  
 <span data-ttu-id="d7e44-118">Indica o nome para exibição do serviço.</span><span class="sxs-lookup"><span data-stu-id="d7e44-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="d7e44-119">**ID do Processo**</span><span class="sxs-lookup"><span data-stu-id="d7e44-119">**Process ID**</span></span>  
 <span data-ttu-id="d7e44-120">Exibe a identificação do processo do Windows.</span><span class="sxs-lookup"><span data-stu-id="d7e44-120">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="d7e44-121">**Tipo de Serviço do SQL**</span><span class="sxs-lookup"><span data-stu-id="d7e44-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="d7e44-122">Exibe o tipo de serviço fornecido a processos de chamada.</span><span class="sxs-lookup"><span data-stu-id="d7e44-122">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="d7e44-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instala vários serviços.</span><span class="sxs-lookup"><span data-stu-id="d7e44-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="d7e44-124">**Modo Inicial**</span><span class="sxs-lookup"><span data-stu-id="d7e44-124">**Start Mode**</span></span>  
 <span data-ttu-id="d7e44-125">Defina este serviço com as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="d7e44-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="d7e44-126">Manual: este serviço não é iniciado automaticamente na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="d7e44-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="d7e44-127">Você deve iniciá-lo usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager ou outra ferramenta.</span><span class="sxs-lookup"><span data-stu-id="d7e44-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="d7e44-128">Automático: este serviço tenta ser iniciado na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="d7e44-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="d7e44-129">Desabilitado: este serviço não pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="d7e44-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="d7e44-130">**State**</span><span class="sxs-lookup"><span data-stu-id="d7e44-130">**State**</span></span>  
 <span data-ttu-id="d7e44-131">Indica se este serviço está sendo executado, se está parado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="d7e44-131">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="d7e44-132">" **...** " indica que há uma alteração de estado pendente.</span><span class="sxs-lookup"><span data-stu-id="d7e44-132">"**...**" indicates a state change is pending.</span></span>  
  
  
