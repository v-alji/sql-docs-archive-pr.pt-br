---
title: Propriedades do Analysis Server (guia Serviço) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 8dbe4bc5-6aa9-48ee-857e-0b4ea764b9cb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91200120d87224c8e7733b0ff41ed423d3086c34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685401"
---
# <a name="analysis-server-properties-service-tab"></a><span data-ttu-id="0ac69-102">Propriedades do Analysis Server (guia Serviço)</span><span class="sxs-lookup"><span data-stu-id="0ac69-102">Analysis Server Properties (Service Tab)</span></span>
  <span data-ttu-id="0ac69-103">Este serviço é o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ac69-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="0ac69-104">Ele deve estar sendo executado para que o [!INCLUDE[ssAS](../../includes/ssas-md.md)] funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="0ac69-104">This service must be running for [!INCLUDE[ssAS](../../includes/ssas-md.md)] to work properly.</span></span> <span data-ttu-id="0ac69-105">Os valores de propriedade em cinza claro não podem ser alterados com o uso deste aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0ac69-105">The property values in light gray cannot be changed using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ac69-106">Opções</span><span class="sxs-lookup"><span data-stu-id="0ac69-106">Options</span></span>  
 <span data-ttu-id="0ac69-107">**Caminho Binário**</span><span class="sxs-lookup"><span data-stu-id="0ac69-107">**Binary Path**</span></span>  
 <span data-ttu-id="0ac69-108">Exibe o local dos arquivos de programas usados por este serviço.</span><span class="sxs-lookup"><span data-stu-id="0ac69-108">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="0ac69-109">**Controle de Erro**</span><span class="sxs-lookup"><span data-stu-id="0ac69-109">**Error Control**</span></span>  
 <span data-ttu-id="0ac69-110">1 indica `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="0ac69-110">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="0ac69-111">Se o serviço não for iniciado durante a inicialização do computador, o programa de inicialização registrará o erro em log e exibirá uma caixa de mensagem pop-up, mas continuará a operação de inicialização.</span><span class="sxs-lookup"><span data-stu-id="0ac69-111">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="0ac69-112">Esse valor não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="0ac69-112">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="0ac69-113">**Código de Saída**</span><span class="sxs-lookup"><span data-stu-id="0ac69-113">**Exit Code**</span></span>  
 <span data-ttu-id="0ac69-114">Quando ocorre um erro, o número do erro é exibido nesta caixa.</span><span class="sxs-lookup"><span data-stu-id="0ac69-114">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="0ac69-115">Use esse número para solucionar problemas de falhas procurando-o na Base de Dados de Conhecimento [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou forneça o número à sua equipe de suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="0ac69-115">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="0ac69-116">**Nome do Host**</span><span class="sxs-lookup"><span data-stu-id="0ac69-116">**Host Name**</span></span>  
 <span data-ttu-id="0ac69-117">Exibe o nome do computador ou cluster que está executando o [!INCLUDE[ssAS](../../includes/ssas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ac69-117">Displays the name of the computer or cluster running [!INCLUDE[ssAS](../../includes/ssas-md.md)].</span></span>  
  
 <span data-ttu-id="0ac69-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0ac69-118">**Name**</span></span>  
 <span data-ttu-id="0ac69-119">Indica o nome para exibição do serviço.</span><span class="sxs-lookup"><span data-stu-id="0ac69-119">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="0ac69-120">**ID do Processo**</span><span class="sxs-lookup"><span data-stu-id="0ac69-120">**Process ID**</span></span>  
 <span data-ttu-id="0ac69-121">Exibe o número usado pelo [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows para manter o controle dos processos deste programa.</span><span class="sxs-lookup"><span data-stu-id="0ac69-121">Displays the number used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows to keep track of this program's processes.</span></span>  
  
 <span data-ttu-id="0ac69-122">**Tipo de Serviço do SQL**</span><span class="sxs-lookup"><span data-stu-id="0ac69-122">**SQL Service Type**</span></span>  
 <span data-ttu-id="0ac69-123">Exibe o tipo de serviço fornecido a processos de chamada.</span><span class="sxs-lookup"><span data-stu-id="0ac69-123">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="0ac69-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instala vários serviços.</span><span class="sxs-lookup"><span data-stu-id="0ac69-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="0ac69-125">**Modo Inicial**</span><span class="sxs-lookup"><span data-stu-id="0ac69-125">**Start Mode**</span></span>  
 <span data-ttu-id="0ac69-126">Defina este serviço com as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="0ac69-126">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="0ac69-127">Manual: este serviço não é iniciado automaticamente na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="0ac69-127">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="0ac69-128">Você deve iniciá-lo usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager ou outra ferramenta.</span><span class="sxs-lookup"><span data-stu-id="0ac69-128">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="0ac69-129">Automático: este serviço tenta ser iniciado na inicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="0ac69-129">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="0ac69-130">Desabilitado: este serviço não pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="0ac69-130">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="0ac69-131">**State**</span><span class="sxs-lookup"><span data-stu-id="0ac69-131">**State**</span></span>  
 <span data-ttu-id="0ac69-132">Indica se este serviço está sendo executado, se está parado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="0ac69-132">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
  
