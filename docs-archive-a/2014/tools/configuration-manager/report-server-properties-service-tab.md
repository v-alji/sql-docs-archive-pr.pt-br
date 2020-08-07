---
title: Propriedades do servidor de relatório (guia Serviço) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 2a2e1dbf-02b9-4893-aaf0-c0e4a2c9b4f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8d223234e5f53eb087650d0634eb09b520cd21e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575470"
---
# <a name="report-server-properties-service-tab"></a><span data-ttu-id="c3d66-102">Propriedades do servidor de relatório (guia Serviço)</span><span class="sxs-lookup"><span data-stu-id="c3d66-102">Report Server Properties (Service Tab)</span></span>
  <span data-ttu-id="c3d66-103">Este é o serviço Servidor de Relatório do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3d66-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server service.</span></span> <span data-ttu-id="c3d66-104">Os valores de propriedade em cinza claro não podem ser alterados com o uso deste aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c3d66-104">The property values in light gray cannot be changed by using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c3d66-105">Opções</span><span class="sxs-lookup"><span data-stu-id="c3d66-105">Options</span></span>  
 <span data-ttu-id="c3d66-106">**Caminho Binário**</span><span class="sxs-lookup"><span data-stu-id="c3d66-106">**Binary Path**</span></span>  
 <span data-ttu-id="c3d66-107">Exibe o local dos arquivos de programas usados por este serviço.</span><span class="sxs-lookup"><span data-stu-id="c3d66-107">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="c3d66-108">**Controle de Erro**</span><span class="sxs-lookup"><span data-stu-id="c3d66-108">**Error Control**</span></span>  
 <span data-ttu-id="c3d66-109">1 indica "SERVICE_ERROR_NORMAL".</span><span class="sxs-lookup"><span data-stu-id="c3d66-109">1 indicates "SERVICE_ERROR_NORMAL".</span></span> <span data-ttu-id="c3d66-110">Se o serviço não for iniciado durante a inicialização do computador, o programa de inicialização registrará o erro em log e exibirá uma caixa de mensagem pop-up, mas continuará a operação de inicialização.</span><span class="sxs-lookup"><span data-stu-id="c3d66-110">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="c3d66-111">Esse valor não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="c3d66-111">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="c3d66-112">**Código de Saída**</span><span class="sxs-lookup"><span data-stu-id="c3d66-112">**Exit Code**</span></span>  
 <span data-ttu-id="c3d66-113">Quando ocorre um erro, o número do erro é exibido nesta caixa.</span><span class="sxs-lookup"><span data-stu-id="c3d66-113">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="c3d66-114">Use esse número para solucionar problemas de falhas procurando-o na Base de Dados de Conhecimento [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou forneça o número à sua equipe de suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="c3d66-114">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="c3d66-115">**Nome do Host**</span><span class="sxs-lookup"><span data-stu-id="c3d66-115">**Host Name**</span></span>  
 <span data-ttu-id="c3d66-116">Exibe o nome do computador ou cluster que está executando a pesquisa de texto completo.</span><span class="sxs-lookup"><span data-stu-id="c3d66-116">Displays the name of the computer or cluster running the full text search.</span></span>  
  
 <span data-ttu-id="c3d66-117">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c3d66-117">**Name**</span></span>  
 <span data-ttu-id="c3d66-118">Indica o nome para exibição do serviço.</span><span class="sxs-lookup"><span data-stu-id="c3d66-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="c3d66-119">**ID do Processo**</span><span class="sxs-lookup"><span data-stu-id="c3d66-119">**Process ID**</span></span>  
 <span data-ttu-id="c3d66-120">Exibe a identificação do processo do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="c3d66-120">Displays the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows process ID.</span></span>  
  
 <span data-ttu-id="c3d66-121">**Tipo de Serviço do SQL**</span><span class="sxs-lookup"><span data-stu-id="c3d66-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="c3d66-122">Tipo de serviço fornecido a processos de chamada.</span><span class="sxs-lookup"><span data-stu-id="c3d66-122">Type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c3d66-123">instala vários serviços.</span><span class="sxs-lookup"><span data-stu-id="c3d66-123">installs several services.</span></span>  
  
 <span data-ttu-id="c3d66-124">**Modo Inicial**</span><span class="sxs-lookup"><span data-stu-id="c3d66-124">**Start Mode**</span></span>  
 <span data-ttu-id="c3d66-125">Defina este serviço com as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c3d66-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="c3d66-126">Manual: este serviço não é iniciado automaticamente na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="c3d66-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="c3d66-127">Você deve iniciá-lo usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager ou outra ferramenta.</span><span class="sxs-lookup"><span data-stu-id="c3d66-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="c3d66-128">Automático: este serviço tenta ser iniciado na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="c3d66-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="c3d66-129">Desabilitado: este serviço não pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="c3d66-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="c3d66-130">**State**</span><span class="sxs-lookup"><span data-stu-id="c3d66-130">**State**</span></span>  
 <span data-ttu-id="c3d66-131">Indica se este serviço está sendo executado, se está parado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="c3d66-131">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d66-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3d66-132">See Also</span></span>  
 [<span data-ttu-id="c3d66-133">Serviços do SQL Server</span><span class="sxs-lookup"><span data-stu-id="c3d66-133">SQL Server Services</span></span>](../../../2014/tools/configuration-manager/sql-server-services.md)  
  
  
