---
title: Propriedades do SQL Server (guia Serviço) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e4ae0c6b-6fd8-4325-b54e-1758fc659958
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5822a02d5631e0d0e9318b20a1dcee87b8a4ded1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684964"
---
# <a name="sql-server-properties-service-tab"></a><span data-ttu-id="ea0ea-102">Propriedades do SQL Server (guia Serviço)</span><span class="sxs-lookup"><span data-stu-id="ea0ea-102">SQL Server Properties (Service Tab)</span></span>
  <span data-ttu-id="ea0ea-103">Use a guia **Serviço**na caixa de diálogo **Propriedades de MSSQLSERVER** para exibir ou especificar as opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-103">Use the **Service**tab on the **MSSQLSERVER Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ea0ea-104">Opções</span><span class="sxs-lookup"><span data-stu-id="ea0ea-104">Options</span></span>  
 <span data-ttu-id="ea0ea-105">**Caminho Binário**</span><span class="sxs-lookup"><span data-stu-id="ea0ea-105">**Binary Path**</span></span>  
 <span data-ttu-id="ea0ea-106">Lista o local dos arquivos de programas usados por este serviço.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-106">Lists the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="ea0ea-107">**Controle de Erro**</span><span class="sxs-lookup"><span data-stu-id="ea0ea-107">**Error Control**</span></span>  
 <span data-ttu-id="ea0ea-108">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="ea0ea-109">Se o serviço não for iniciado durante a inicialização do computador, o programa de inicialização registrará o erro em log e exibirá uma caixa de mensagem pop-up, mas continuará a operação de inicialização.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="ea0ea-110">Esse valor não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="ea0ea-111">**Código de Saída**</span><span class="sxs-lookup"><span data-stu-id="ea0ea-111">**Exit Code**</span></span>  
 <span data-ttu-id="ea0ea-112">Quando ocorre um erro, o número do erro é exibido nesta caixa.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-112">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="ea0ea-113">Use esse número para solucionar problemas de falhas procurando-o na Base de Dados de Conhecimento [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou forneça o número à sua equipe de suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-113">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="ea0ea-114">**Nome do Host**</span><span class="sxs-lookup"><span data-stu-id="ea0ea-114">**Host Name**</span></span>  
 <span data-ttu-id="ea0ea-115">Exibe o nome do computador ou cluster que está executando o serviço [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea0ea-115">Displays the name of the computer or cluster running the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="ea0ea-116">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ea0ea-116">**Name**</span></span>  
 <span data-ttu-id="ea0ea-117">Indica o nome para exibição do serviço.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-117">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="ea0ea-118">**ID do Processo**</span><span class="sxs-lookup"><span data-stu-id="ea0ea-118">**Process ID**</span></span>  
 <span data-ttu-id="ea0ea-119">Exibe a identificação do processo do Windows.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-119">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="ea0ea-120">**Tipo de Serviço**</span><span class="sxs-lookup"><span data-stu-id="ea0ea-120">**Service Type**</span></span>  
 <span data-ttu-id="ea0ea-121">Exibe o tipo de serviço fornecido a processos de chamada.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-121">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ea0ea-122">instala vários serviços.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-122">installs several services.</span></span>  
  
 <span data-ttu-id="ea0ea-123">**Modo Inicial**</span><span class="sxs-lookup"><span data-stu-id="ea0ea-123">**Start Mode**</span></span>  
 <span data-ttu-id="ea0ea-124">Defina este serviço com as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="ea0ea-124">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="ea0ea-125">Manual: este serviço não é iniciado automaticamente na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-125">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="ea0ea-126">Você deve iniciá-lo usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager ou outra ferramenta.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-126">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="ea0ea-127">Automático: este serviço tenta ser iniciado na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-127">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="ea0ea-128">Desabilitado: este serviço não pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-128">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="ea0ea-129">**State**</span><span class="sxs-lookup"><span data-stu-id="ea0ea-129">**State**</span></span>  
 <span data-ttu-id="ea0ea-130">Indica se este serviço está sendo executado, se está parado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-130">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="ea0ea-131">" **...** " indica que há uma alteração de estado pendente.</span><span class="sxs-lookup"><span data-stu-id="ea0ea-131">"**...**" indicates a state change is pending.</span></span>  
  
  
