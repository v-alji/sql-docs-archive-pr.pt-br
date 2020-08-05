---
title: Propriedades da rede | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LingerTimeout property
- EnableNagleAlgorithm property
- MinPendingAcceptExCount property
- MaxPendingSendCount property
- EnableBinaryXML property
- MinPendingReceiveCount property
- MaxCompletedReceiveCount property
- DisableNonblockingMode property
- RequestSizeThreshold property
- CompressionLevel property
- ReceiveBufferSize property
- EnableCompression property
- ServerSendTimeout property
- IPV4Support property
- MaxPendingReceiveCount property
- MaxPendingAcceptExCount property
- IPV6Support property
- MaxAllowedRequestSize property
- ServerReceiveTimeout property
- EnableLingerOnClose property
- InitialConnectTimeout property
- SendBufferSize property
- ScatterReceiveMultiplier property
- network properties [Analysis Services]
ms.assetid: ef4251e2-abe5-4c5b-9868-7549782d0244
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10ad5bbbcffdfc3d3c4fefe3111e4c4425919915
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573312"
---
# <a name="network-properties"></a><span data-ttu-id="404a6-102">Propriedades de rede</span><span class="sxs-lookup"><span data-stu-id="404a6-102">Network Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="404a6-103">oferece suporte às propriedades do servidor listadas nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="404a6-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="404a6-104">Para obter mais informações sobre as propriedades de servidor adicionais e como defini-las, consulte [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="404a6-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="404a6-105">**Aplica-se a:** modo de servidor multidimensional e tabular</span><span class="sxs-lookup"><span data-stu-id="404a6-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="general"></a><span data-ttu-id="404a6-106">Geral</span><span class="sxs-lookup"><span data-stu-id="404a6-106">General</span></span>  
 `ListenOnlyOnLocalConnections`  
 <span data-ttu-id="404a6-107">Uma propriedade Booleana que identifica a escuta apenas em conexões locais, por exemplo localhost.</span><span class="sxs-lookup"><span data-stu-id="404a6-107">A Boolean property that identifies whether to listen only on local connections, for example localhost.</span></span>  
  
## <a name="listener"></a><span data-ttu-id="404a6-108">Ouvinte</span><span class="sxs-lookup"><span data-stu-id="404a6-108">Listener</span></span>  
 `IPV4Support`  
 <span data-ttu-id="404a6-109">Uma propriedade de inteiro de 32 bits assinada que define o suporte ao protocolo IPv4.</span><span class="sxs-lookup"><span data-stu-id="404a6-109">A signed 32-bit integer property that defines support for IPv4 protocol.</span></span> <span data-ttu-id="404a6-110">Essa propriedade tem um dos valores listados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="404a6-110">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="404a6-111">Valor</span><span class="sxs-lookup"><span data-stu-id="404a6-111">Value</span></span>|<span data-ttu-id="404a6-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="404a6-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="404a6-113">*0*</span><span class="sxs-lookup"><span data-stu-id="404a6-113">*0*</span></span>|<span data-ttu-id="404a6-114">IPv4 desabilitado; os clientes não podem se conectar.</span><span class="sxs-lookup"><span data-stu-id="404a6-114">IPv4 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="404a6-115">*1*</span><span class="sxs-lookup"><span data-stu-id="404a6-115">*1*</span></span>|<span data-ttu-id="404a6-116">(Padrão) IPv4 necessário; servidor não será iniciado se não puder escutar IPv4.</span><span class="sxs-lookup"><span data-stu-id="404a6-116">(Default) IPv4 is required; server won't start if it cannot listen to IPv4.</span></span>|  
|<span data-ttu-id="404a6-117">*2*</span><span class="sxs-lookup"><span data-stu-id="404a6-117">*2*</span></span>|<span data-ttu-id="404a6-118">IPv4 é opcional; o servidor tenta escutar IPv4, mas será iniciado mesmo se não conseguir.</span><span class="sxs-lookup"><span data-stu-id="404a6-118">IPv4 is optional; server tries to listen to IPv4 but starts even if unable to.</span></span>|  
  
 `IPV6Support`  
 <span data-ttu-id="404a6-119">Uma propriedade de inteiro de 32 bits assinada que define o suporte ao protocolo IPv6.</span><span class="sxs-lookup"><span data-stu-id="404a6-119">A signed 32-bit integer property that defines support for IPv6 protocol.</span></span> <span data-ttu-id="404a6-120">Essa propriedade tem um dos valores listados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="404a6-120">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="404a6-121">Valor</span><span class="sxs-lookup"><span data-stu-id="404a6-121">Value</span></span>|<span data-ttu-id="404a6-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="404a6-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="404a6-123">*0*</span><span class="sxs-lookup"><span data-stu-id="404a6-123">*0*</span></span>|<span data-ttu-id="404a6-124">IPv6 desabilitado; os clientes não podem se conectar.</span><span class="sxs-lookup"><span data-stu-id="404a6-124">IPv6 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="404a6-125">*1*</span><span class="sxs-lookup"><span data-stu-id="404a6-125">*1*</span></span>|<span data-ttu-id="404a6-126">(Padrão) IPv6 necessário; servidor não será iniciado se não for possível escutar IPv6</span><span class="sxs-lookup"><span data-stu-id="404a6-126">(Default) IPv6 is required; server won't start if it cannot listen to IPv6.</span></span>|  
|<span data-ttu-id="404a6-127">*2*</span><span class="sxs-lookup"><span data-stu-id="404a6-127">*2*</span></span>|<span data-ttu-id="404a6-128">IPv6 é opcional; o servidor tenta escutar IPv6, mas será iniciado mesmo se não conseguir.</span><span class="sxs-lookup"><span data-stu-id="404a6-128">IPv6 is optional; server tries to listen to IPv6 but starts even if unable to.</span></span>|  
  
 `MaxAllowedRequestSize`  
 <span data-ttu-id="404a6-129">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-129">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RequestSizeThreshold`  
 <span data-ttu-id="404a6-130">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-130">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerReceiveTimeout`  
 <span data-ttu-id="404a6-131">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-131">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerSendTimeout`  
 <span data-ttu-id="404a6-132">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-132">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="requests"></a><span data-ttu-id="404a6-133">Requests</span><span class="sxs-lookup"><span data-stu-id="404a6-133">Requests</span></span>  
 `EnableBinaryXML`  
 <span data-ttu-id="404a6-134">Uma propriedade Booleana que especifica se o servidor reconhecerá solicitações xml em formato binário.</span><span class="sxs-lookup"><span data-stu-id="404a6-134">A Boolean property that specifies whether the server will recognize requests binary xml format.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="404a6-135">Uma propriedade Booleana que especifica se a compressão está habilitada para solicitações.</span><span class="sxs-lookup"><span data-stu-id="404a6-135">A Boolean property that specifies whether compression is enabled for requests.</span></span>  
  
## <a name="responses"></a><span data-ttu-id="404a6-136">Respostas</span><span class="sxs-lookup"><span data-stu-id="404a6-136">Responses</span></span>  
 `CompressionLevel`  
 <span data-ttu-id="404a6-137">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-137">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `EnableBinaryXML`  
 <span data-ttu-id="404a6-138">Uma propriedade Booleana que especifica se o servidor está habilitado para respostas xml binárias.</span><span class="sxs-lookup"><span data-stu-id="404a6-138">A Boolean property that specifies whether the server is enabled for binary xml responses.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="404a6-139">Uma propriedade Booleana que especifica se a compressão está habilitada para respostas a solicitações de cliente.</span><span class="sxs-lookup"><span data-stu-id="404a6-139">A Boolean property that specifies whether compression is enabled for responses to client requests.</span></span>  
  
## <a name="tcp"></a><span data-ttu-id="404a6-140">TCP</span><span class="sxs-lookup"><span data-stu-id="404a6-140">TCP</span></span>  
 `InitialConnectTimeout`  
 <span data-ttu-id="404a6-141">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxCompletedReceiveCount`  
 <span data-ttu-id="404a6-142">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingAcceptExCount`  
 <span data-ttu-id="404a6-143">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-143">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingReceiveCount`  
 <span data-ttu-id="404a6-144">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingSendCount`  
 <span data-ttu-id="404a6-145">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-145">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingAcceptExCount`  
 <span data-ttu-id="404a6-146">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingReceiveCount`  
 <span data-ttu-id="404a6-147">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ScatterReceiveMultiplier`  
 <span data-ttu-id="404a6-148">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ DisableNonblockingMode`  
 <span data-ttu-id="404a6-149">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ EnableLingerOnClose`  
 <span data-ttu-id="404a6-150">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\EnableNagleAlgorithm`  
 <span data-ttu-id="404a6-151">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ LingerTimeout`  
 <span data-ttu-id="404a6-152">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ ReceiveBufferSize`  
 <span data-ttu-id="404a6-153">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-153">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ SendBufferSize`  
 <span data-ttu-id="404a6-154">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="404a6-154">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404a6-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="404a6-155">See Also</span></span>  
 <span data-ttu-id="404a6-156">[Configurar propriedades do servidor no Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="404a6-156">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="404a6-157">Determina o Modo de Servidor de uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="404a6-157">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
