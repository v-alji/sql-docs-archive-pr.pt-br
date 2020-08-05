---
title: MSSQLSERVER_33085 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33085 (Database Engine error)
ms.assetid: c27b8d1d-668a-4ba8-8b61-25a5ebbc5485
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d774ab115c2d0ddbbd7b35c7e32db17e39fcb2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573062"
---
# <a name="mssqlserver_33085"></a><span data-ttu-id="ed7e2-102">MSSQLSERVER_33085</span><span class="sxs-lookup"><span data-stu-id="ed7e2-102">MSSQLSERVER_33085</span></span>
    
## <a name="details"></a><span data-ttu-id="ed7e2-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ed7e2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ed7e2-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ed7e2-104">Product Name</span></span>|<span data-ttu-id="ed7e2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed7e2-105">SQL Server</span></span>|  
|<span data-ttu-id="ed7e2-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ed7e2-106">Event ID</span></span>|<span data-ttu-id="ed7e2-107">33085</span><span class="sxs-lookup"><span data-stu-id="ed7e2-107">33085</span></span>|  
|<span data-ttu-id="ed7e2-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ed7e2-108">Event Source</span></span>|<span data-ttu-id="ed7e2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ed7e2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ed7e2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ed7e2-110">Component</span></span>|<span data-ttu-id="ed7e2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ed7e2-111">SQLEngine</span></span>|  
|<span data-ttu-id="ed7e2-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ed7e2-112">Symbolic Name</span></span>|<span data-ttu-id="ed7e2-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="ed7e2-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span></span>|  
|<span data-ttu-id="ed7e2-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ed7e2-114">Message Text</span></span>|<span data-ttu-id="ed7e2-115">Não é possível encontrar um ou mais métodos na biblioteca de provedor criptográfica '%. \* ls.'</span><span class="sxs-lookup"><span data-stu-id="ed7e2-115">One or more methods cannot be found in cryptographic provider library '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ed7e2-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="ed7e2-116">Explanation</span></span>  
 <span data-ttu-id="ed7e2-117">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pôde usar o provedor criptográfico listado na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="ed7e2-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was unable to use the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="ed7e2-118">O provedor criptográfico não deu suporte a um método exigido.</span><span class="sxs-lookup"><span data-stu-id="ed7e2-118">The cryptographic provider did not support a required method.</span></span> <span data-ttu-id="ed7e2-119">O estado do erro indica qual método não foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="ed7e2-119">The state of the error indicates which method was not found.</span></span>  
  
|<span data-ttu-id="ed7e2-120">Estado</span><span class="sxs-lookup"><span data-stu-id="ed7e2-120">State</span></span>|<span data-ttu-id="ed7e2-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="ed7e2-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ed7e2-122">1</span><span class="sxs-lookup"><span data-stu-id="ed7e2-122">1</span></span>|<span data-ttu-id="ed7e2-123">SqlCryptInitializeProvider</span><span class="sxs-lookup"><span data-stu-id="ed7e2-123">SqlCryptInitializeProvider</span></span>|  
|<span data-ttu-id="ed7e2-124">2</span><span class="sxs-lookup"><span data-stu-id="ed7e2-124">2</span></span>|<span data-ttu-id="ed7e2-125">SqlCryptFreeProvider</span><span class="sxs-lookup"><span data-stu-id="ed7e2-125">SqlCryptFreeProvider</span></span>|  
|<span data-ttu-id="ed7e2-126">3</span><span class="sxs-lookup"><span data-stu-id="ed7e2-126">3</span></span>|<span data-ttu-id="ed7e2-127">SqlCryptOpenSession</span><span class="sxs-lookup"><span data-stu-id="ed7e2-127">SqlCryptOpenSession</span></span>|  
|<span data-ttu-id="ed7e2-128">4</span><span class="sxs-lookup"><span data-stu-id="ed7e2-128">4</span></span>|<span data-ttu-id="ed7e2-129">SqlCryptCloseSession</span><span class="sxs-lookup"><span data-stu-id="ed7e2-129">SqlCryptCloseSession</span></span>|  
|<span data-ttu-id="ed7e2-130">5</span><span class="sxs-lookup"><span data-stu-id="ed7e2-130">5</span></span>|<span data-ttu-id="ed7e2-131">SqlCryptGetProviderInfo</span><span class="sxs-lookup"><span data-stu-id="ed7e2-131">SqlCryptGetProviderInfo</span></span>|  
|<span data-ttu-id="ed7e2-132">6</span><span class="sxs-lookup"><span data-stu-id="ed7e2-132">6</span></span>|<span data-ttu-id="ed7e2-133">SqlCryptGetNextAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="ed7e2-133">SqlCryptGetNextAlgorithmId</span></span>|  
|<span data-ttu-id="ed7e2-134">7</span><span class="sxs-lookup"><span data-stu-id="ed7e2-134">7</span></span>|<span data-ttu-id="ed7e2-135">SqlCryptGetAlgorithmInfo</span><span class="sxs-lookup"><span data-stu-id="ed7e2-135">SqlCryptGetAlgorithmInfo</span></span>|  
|<span data-ttu-id="ed7e2-136">8</span><span class="sxs-lookup"><span data-stu-id="ed7e2-136">8</span></span>|<span data-ttu-id="ed7e2-137">SqlCryptCreateKey</span><span class="sxs-lookup"><span data-stu-id="ed7e2-137">SqlCryptCreateKey</span></span>|  
|<span data-ttu-id="ed7e2-138">9</span><span class="sxs-lookup"><span data-stu-id="ed7e2-138">9</span></span>|<span data-ttu-id="ed7e2-139">SqlCryptDropKey</span><span class="sxs-lookup"><span data-stu-id="ed7e2-139">SqlCryptDropKey</span></span>|  
|<span data-ttu-id="ed7e2-140">10</span><span class="sxs-lookup"><span data-stu-id="ed7e2-140">10</span></span>|<span data-ttu-id="ed7e2-141">SqlCryptGetNextKeyId</span><span class="sxs-lookup"><span data-stu-id="ed7e2-141">SqlCryptGetNextKeyId</span></span>|  
|<span data-ttu-id="ed7e2-142">11</span><span class="sxs-lookup"><span data-stu-id="ed7e2-142">11</span></span>|<span data-ttu-id="ed7e2-143">SqlCryptGetKeyInfoByKeyId</span><span class="sxs-lookup"><span data-stu-id="ed7e2-143">SqlCryptGetKeyInfoByKeyId</span></span>|  
|<span data-ttu-id="ed7e2-144">12</span><span class="sxs-lookup"><span data-stu-id="ed7e2-144">12</span></span>|<span data-ttu-id="ed7e2-145">SqlCryptGetKeyInfoByThumb</span><span class="sxs-lookup"><span data-stu-id="ed7e2-145">SqlCryptGetKeyInfoByThumb</span></span>|  
|<span data-ttu-id="ed7e2-146">13</span><span class="sxs-lookup"><span data-stu-id="ed7e2-146">13</span></span>|<span data-ttu-id="ed7e2-147">SqlCryptGetKeyInfoByName</span><span class="sxs-lookup"><span data-stu-id="ed7e2-147">SqlCryptGetKeyInfoByName</span></span>|  
|<span data-ttu-id="ed7e2-148">14</span><span class="sxs-lookup"><span data-stu-id="ed7e2-148">14</span></span>|<span data-ttu-id="ed7e2-149">SqlCryptExportKey</span><span class="sxs-lookup"><span data-stu-id="ed7e2-149">SqlCryptExportKey</span></span>|  
|<span data-ttu-id="ed7e2-150">15</span><span class="sxs-lookup"><span data-stu-id="ed7e2-150">15</span></span>|<span data-ttu-id="ed7e2-151">SqlCryptImportKey</span><span class="sxs-lookup"><span data-stu-id="ed7e2-151">SqlCryptImportKey</span></span>|  
|<span data-ttu-id="ed7e2-152">16</span><span class="sxs-lookup"><span data-stu-id="ed7e2-152">16</span></span>|<span data-ttu-id="ed7e2-153">SqlCryptEncrypt</span><span class="sxs-lookup"><span data-stu-id="ed7e2-153">SqlCryptEncrypt</span></span>|  
|<span data-ttu-id="ed7e2-154">17</span><span class="sxs-lookup"><span data-stu-id="ed7e2-154">17</span></span>|<span data-ttu-id="ed7e2-155">SqlCryptDecrypt</span><span class="sxs-lookup"><span data-stu-id="ed7e2-155">SqlCryptDecrypt</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="ed7e2-156">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ed7e2-156">User Action</span></span>  
 <span data-ttu-id="ed7e2-157">Contate o provedor criptográfico para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ed7e2-157">Contact the cryptographic provider for more information.</span></span>  
  
  
